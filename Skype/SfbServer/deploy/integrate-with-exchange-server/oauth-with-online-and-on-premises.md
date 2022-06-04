---
title: Integrazione tra Skype for Business Online ed Exchange Server
ms.reviewer: cbland
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/17/2022
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: La configurazione dell'autenticazione OAuth tra Exchange locale e Skype for Business Online abilita le funzionalità di Integrazione di Skype for Business ed Exchange descritte in Supporto delle funzionalità.
ms.openlocfilehash: 0b312dfde144f12a9c2db523ce4526153b445d59
ms.sourcegitcommit: e3931446943684db155bb3edf7d7e52d41775013
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2022
ms.locfileid: "65886643"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Configurare l'integrazione e OAuth tra Skype for Business Online ed Exchange Server 

La configurazione dell'integrazione tra Exchange Server e Skype for Business Online abilita le funzionalità di Integrazione di Skype for Business ed Exchange descritte in [Supporto delle funzionalità](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).

Questo argomento si applica all'integrazione con Exchange Server 2013 fino al 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Tempo stimato per il completamento di questa attività: 15 minuti

-  Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per visualizzare le autorizzazioni necessarie, vedere l'argomento [Autorizzazioni per l'infrastruttura di Exchange e Shell](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help) .

- Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere [Tasti di scelta rapida nell'interfaccia di amministrazione di Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

- Per informazioni sulla compatibilità, vedere [Compatibilità di Skype for Business con le app di Office](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Configurare l'integrazione tra Exchange Server e O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Passaggio 1: Configurare l'autenticazione OAuth tra Exchange Server e O365

Seguire questa procedura nell'articolo seguente:

[Configurazione dell'autenticazione OAuth tra organizzazioni Exchange ed Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Passaggio 2: Creare un nuovo account utente di posta elettronica per l'applicazione Skype for Business Online Partner

Questo passaggio viene eseguito nel server Exchange. Creerà un utente di posta elettronica e gli assegnerà i diritti di ruolo di gestione appropriati. Questo account verrà quindi usato nel passaggio successivo.

Specificare un dominio verificato per l'organizzazione di Exchange. Questo dominio deve essere lo stesso dominio usato come dominio SMTP primario usato per gli account di Exchange locali. Questo dominio è indicato come \<your Verified Domain\> nella procedura seguente. \<DomainControllerFQDN\> Deve inoltre essere il nome di dominio completo di un controller di dominio.

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Questo comando nasconderà il nuovo utente di posta elettronica dagli elenchi di indirizzi.

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Questi due comandi successivi assegneranno il ruolo di gestione UserApplication e ArchiveApplication a questo nuovo account.

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Passaggio 3: Creare e abilitare un'applicazione partner per Skype for Business Online 

Creare una nuova applicazione partner e usare l'account appena creato. Eseguire il comando seguente in Exchange PowerShell nella propria organizzazione Exchange locale.

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>Passaggio 4: Esportare il certificato di autorizzazione locale

Eseguire uno script di PowerShell per esportare il certificato di autorizzazione locale, che verrà importato nell'organizzazione Skype for Business Online nel passaggio successivo.

Salvare il testo seguente in un file di script di PowerShell denominato, ad esempio, ExportAuthCert.ps1.

```powershell
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false) {
    md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

In Exchange PowerShell nell'organizzazione di Exchange locale eseguire lo script di PowerShell appena creato. Ad esempio: .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Passaggio 5: Caricare il certificato di autorizzazione locale in Azure Active Directory ACS

Usare quindi Windows PowerShell per caricare il certificato di autorizzazione locale esportato nel passaggio precedente in Azure Active Directory Access Control Services (ACS). A tale scopo, è necessario che i cmdlet di Azure Active Directory Module per Windows PowerShell siano già installati. Se non è installato, passare a per [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) installare il modulo di Azure Active Directory per Windows PowerShell. Completare la procedura seguente dopo l'installazione del modulo di Azure Active Directory per Windows PowerShell.

1. Fare clic sul collegamento **Modulo di Azure Active Directory per Windows PowerShell** per aprire un'area di lavoro di Windows PowerShell in cui sono installati i cmdlet di Azure AD. Tutti i comandi in questo passaggio verranno eseguiti usando Windows PowerShell per la console di Azure Active Directory.

2. Salvare il testo seguente in un file di script di PowerShell denominato, ad esempio  `UploadAuthCert.ps1`.

   ```powershell
   Connect-MsolService
   Import-Module MSOnline
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile)
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert)
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000"
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. Eseguire lo script di PowerShell creato nel passaggio precedente. Esempio:  `.\UploadAuthCert.ps1`

4. Dopo avere avviato lo script, viene visualizzata una finestra di dialogo relativa alle credenziali. Immettere le credenziali per l'account amministratore tenant dell'organizzazione di Microsoft Online Azure AD. Dopo aver eseguito lo script, lasciare aperta la sessione di Windows PowerShell per Azure AD. Questa verrà utilizzata per eseguire uno script di PowerShell nel prossimo passaggio.

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>Passaggio 6: Verificare che il certificato sia stato caricato nell'entità servizio Skype for Business
1. In PowerShell aperto e autenticato in Azure Active Directory, eseguire le operazioni seguenti

   ```powershell
   Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
   ```
2. Premere INVIO quando viene richiesto ReturnKeyValues
3. Verificare di visualizzare una chiave elencata con i dati di inizio e fine corrispondenti alle date di inizio e fine del certificato Oauth di Exchange

### <a name="verify-your-success"></a>Verificare l'esito positivo

Verificare che la configurazione sia corretta verificando che alcune delle funzionalità funzionino correttamente. 

1. Verificare che gli utenti di Skype for Business con il servizio Cloud Voicemail, in un'organizzazione con una configurazione ibrida di Exchange Server, possano modificare correttamente i messaggi di saluto della segreteria telefonica.

2. Verificare che la cronologia delle conversazioni per i client mobili sia visibile nella cartella Cronologia conversazioni di Outlook.

3. Verificare che i messaggi di chat archiviati vengano depositati nella cassetta postale locale dell'utente nella cartella Purges usando [EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor).

In alternativa, esaminare il traffico. Il traffico in un handshake OAuth è molto particolare (e non è simile all'autenticazione di base), in particolare intorno alle aree di autenticazione, in cui si inizierà a visualizzare il traffico dell'autorità di certificazione simile al seguente: 00000004-0000-0ff1-ce00-00000000000@ (a volte con un /prima dell'accesso @), nei token che vengono passati. Non verrà visualizzato un nome utente o una password, ovvero il punto di OAuth. Ma vedrai l'emittente "Office", in questo caso "4" è Skype for Business, e l'area di autenticazione della tua sottoscrizione.

Se si vuole essere certi di usare correttamente OAuth, assicurarsi di sapere cosa aspettarsi e sapere come dovrebbe essere il traffico. Ecco [quindi cosa aspettarsi](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), ecco un esempio piuttosto standard [di traffico OAuth in un'applicazione Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (davvero utile da leggere, anche se non usa i token di aggiornamento) e ci sono estensioni Fiddler che ti consentiranno di esaminare il tuo JWT OAuth (token Web JSON).

Di seguito è riportato un [esempio di configurazione,](/archive/blogs/kaevans/updated-fiddler-oauth-inspector) ma è possibile usare qualsiasi strumento di traccia di rete che si vuole eseguire questo processo.

## <a name="related-topics"></a>Argomenti correlati

[Configurazione dell'autenticazione OAuth tra organizzazioni Exchange ed Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
