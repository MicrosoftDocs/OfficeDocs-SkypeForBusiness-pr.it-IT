---
title: Integrazione tra Skype for Business Online e il server Exchange
ms.reviewer: cbland
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: La configurazione dell'autenticazione OAuth tra Exchange locale e Skype for Business online abilita le funzionalità di integrazione di Skype for Business ed Exchange descritte in Supporto delle funzionalità.
ms.openlocfilehash: 342362926ad0af169acd6c9af4715008425e71c7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109712"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Configurare l'integrazione e OAuth tra Skype for Business online e Exchange Server 

La configurazione dell'integrazione tra il server Exchange e Skype for Business online abilita le funzionalità di integrazione di Skype for Business ed Exchange descritte in [Supporto delle funzionalità.](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)

Questo argomento si applica all'integrazione con Exchange Server 2013 fino al 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Tempo stimato per il completamento di questa attività: 15 minuti

-  Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere [l'argomento Autorizzazioni dell'infrastruttura di Exchange e Shell.](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help)

- Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere [Tasti di scelta rapida nell'interfaccia di amministrazione di Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

- Per informazioni sulla compatibilità, vedere [Compatibilità di Skype for Business con le app di Office.](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md)

## <a name="configure-integration-between-exchange-server-and-o365"></a>Configurare l'integrazione tra Exchange Server e O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Passaggio 1: Configurare l'autenticazione OAuth tra Exchange Server e O365

Eseguire la procedura descritta nell'articolo seguente:

[Configurazione dell'autenticazione OAuth tra organizzazioni Exchange ed Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Passaggio 2: Creare un nuovo account utente di posta per l'applicazione partner skype for business online

Questo passaggio viene eseguito sul server Exchange. Verrà creato un utente di posta elettronica e gli verranno assegnati i diritti di ruolo di gestione appropriati. Questo account verrà quindi utilizzato nel passaggio successivo.

Specificare un dominio verificato per l'organizzazione di Exchange. Questo dominio deve essere lo stesso utilizzato come dominio SMTP primario utilizzato per gli account di Exchange locali. Questo dominio viene indicato \<your Verified Domain\> nella procedura seguente. Deve inoltre \<DomainControllerFQDN\> essere il nome di dominio completo di un controller di dominio.

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Questo comando nasconderà il nuovo utente di posta dagli elenchi indirizzi.

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Questi due comandi successivi assegnano il ruolo di gestione UserApplication e ArchiveApplication a questo nuovo account.

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Passaggio 3: Creare e abilitare un'applicazione partner per Skype for Business online 

Crea una nuova applicazione partner e userà l'account appena creato. Eseguire il comando seguente in Exchange PowerShell nella propria organizzazione Exchange locale.

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>Passaggio 4: Esportare il certificato di autorizzazione locale

Eseguire uno script di PowerShell per esportare il certificato di autorizzazione locale, che verrà importato nell'organizzazione Skype for Business online nel passaggio successivo.

Salvare il testo seguente in un file di script di PowerShell denominato, ad esempio, ExportAuthCert.ps1.

```powershell
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false)
{
md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

In PowerShell di Exchange nell'organizzazione exchange locale, eseguire lo script di PowerShell appena creato. Ad esempio: .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Passaggio 5: Caricare il certificato di autorizzazione locale in ACS di Azure Active Directory

Successivamente, usare Windows PowerShell per caricare il certificato di autorizzazione locale esportato nel passaggio precedente in Azure Active Directory Access Control Services (ACS). A tale scopo, è necessario che il modulo di Azure Active Directory per Windows PowerShell cmdlet sia già installato. Se non è installato, passare a [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) per installare il modulo di Azure Active Directory per Windows PowerShell. Completare i passaggi seguenti dopo l'installazione del modulo di Azure Active Directory Windows PowerShell installazione.

1. Fare clic **sul collegamento Azure Active Directory Module for Windows PowerShell** per aprire un'Windows PowerShell di lavoro in cui sono installati i cmdlet di Azure AD. Tutti i comandi in questo passaggio verranno eseguiti usando la Windows PowerShell console di Azure Active Directory.

2. Salvare il testo seguente in un file script di PowerShell denominato, ad  `UploadAuthCert.ps1` esempio.

   ```powershell
   Connect-MsolService;
   Import-Module msonlineextended;
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject;
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile);
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert);
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. Eseguire lo script di PowerShell creato nel passaggio precedente. Esempio:  `.\UploadAuthCert.ps1`

4. Dopo avere avviato lo script, viene visualizzata una finestra di dialogo relativa alle credenziali. Immettere le credenziali per l'account di amministratore tenant dell'organizzazione di Microsoft Online Azure AD. Dopo aver eseguito lo script, lasciare aperta la Windows PowerShell per Azure AD. Questa verrà utilizzata per eseguire uno script di PowerShell nel prossimo passaggio.

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>Passaggio 6: verificare che il certificato sia stato caricato nell'entità servizio di Skype for Business
1. In PowerShell aperto e autenticato in Azure Active Directory, eseguire il comando seguente
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. Premere INVIO quando viene richiesto di specificare ReturnKeyValues
3. Verificare che sia presente una chiave elencata con la data di inizio e i dati di fine corrispondenti alle date di inizio e fine del certificato Oauth di Exchange

### <a name="verify-your-success"></a>Verificare l'esito positivo

Verificare che la configurazione sia corretta verificando che alcune funzionalità funzionino correttamente. 

1. Verificare che gli utenti di Skype for Business con il servizio Cloud Voicemail, in un'organizzazione con una configurazione Exchange Server ibrida, possano modificare correttamente i messaggi di saluto della segreteria telefonica.

2. Verificare che la cronologia delle conversazioni per i client mobili sia visibile nella cartella Cronologia conversazioni di Outlook.

3. Verificare che i messaggi di chat archiviati siano archiviati nella cassetta postale locale dell'utente nella cartella Ripuliture utilizzando [EWSEditor.](/archive/blogs/webdav_101/where-to-get-ewseditor)

In alternativa, esaminare il traffico. Il traffico in un handshake OAuth è veramente distintivo (e non è simile all'autenticazione di base), in particolare per le aree di autenticazione, in cui inizierai a vedere il traffico dell'autorità emittente simile al seguente: 000000004-0000-0ff1-ce00-00000000000000@ (a volte con un segno / prima del segno @), nei token che vengono passati. Non verrà visualizzato un nome utente o una password, che è il punto di OAuth. Tuttavia, verrà visualizzata l'autorità emittente di "Office", in questo caso "4" è Skype for Business, e l'area di autenticazione dell'abbonamento.

Se si desidera essere certi di aver utilizzato OAuth correttamente, assicurarsi di sapere cosa aspettarsi e conoscere l'aspetto del traffico. Ecco [](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)cosa aspettarsi, ecco un esempio piuttosto standard di traffico [OAuth in](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) un'applicazione Microsoft (molto utile da leggere, anche se non usa i token Refresh), e ci sono estensioni Fiddler che ti consentiranno di esaminare il token JWT OAuth (JSON Web Token).

Ecco un esempio [di configurazione di](/archive/blogs/kaevans/updated-fiddler-oauth-inspector), ma puoi usare qualsiasi strumento di traccia di rete che ti piace per eseguire questo processo.

## <a name="related-topics"></a>Argomenti correlati

[Configurazione dell'autenticazione OAuth tra organizzazioni Exchange ed Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)