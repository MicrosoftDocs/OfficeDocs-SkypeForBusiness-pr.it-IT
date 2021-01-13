---
title: Integrazione tra Skype for business online ed Exchange Server
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
description: La configurazione dell'autenticazione OAuth tra Exchange in locale e Skype for business online consente di abilitare le funzionalità di integrazione di Skype for business e di Exchange descritte in funzionalità di supporto.
ms.openlocfilehash: ac8bfe2f30e813e47a0256a68e4e81852d5bae68
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833976"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Configurare l'integrazione e OAuth tra Skype for business online ed Exchange Server 

La configurazione dell'integrazione tra Exchange Server e Skype for business online consente di abilitare le funzionalità di integrazione di Skype for business e Exchange descritte in [funzionalità di supporto](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).

Questo argomento si applica all'integrazione con Exchange Server 2013-2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Tempo stimato per il completamento di questa attività: 15 minuti

-  Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere l'argomento [Exchange and shell Infrastructure Permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) .

- Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere [Tasti di scelta rapida nell'interfaccia di amministrazione di Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

- Per informazioni sulla compatibilità, vedere [compatibilità di Skype for business con le app di Office](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Configurare l'integrazione tra Exchange Server e O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Passaggio 1: configurare l'autenticazione OAuth tra Exchange Server e O365

Eseguire la procedura illustrata nell'articolo seguente:

[Configurazione dell'autenticazione OAuth tra organizzazioni Exchange ed Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Passaggio 2: creare un nuovo account utente di posta elettronica per l'applicazione partner di Skype for business online

Questo passaggio viene effettuato sul server di Exchange. Creerà un utente di posta elettronica e gli assegnerà i diritti di ruolo di gestione corretti. Questo account verrà quindi utilizzato nel passaggio successivo.

Specificare un dominio verificato per l'organizzazione di Exchange. Questo dominio deve essere lo stesso dominio utilizzato come dominio SMTP primario utilizzato per gli account di Exchange locali. Questo dominio viene indicato \<your Verified Domain\> nella procedura seguente. Inoltre, il \<DomainControllerFQDN\> nome FQDN di un controller di dominio dovrebbe essere.

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Questo comando nasconderà il nuovo utente di posta elettronica dagli elenchi di indirizzi.

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Nei prossimi due comandi verrà assegnato il ruolo di gestione UserApplication e ArchiveApplication a questo nuovo account.

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Passaggio 3: creare e abilitare un'applicazione partner per Skype for business online 

Creare una nuova applicazione partner e utilizzare l'account appena creato. Eseguire il comando seguente in Exchange PowerShell nella propria organizzazione Exchange locale.

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>Passaggio 4: esportare il certificato di autorizzazione locale

Eseguire uno script di PowerShell per esportare il certificato di autorizzazione in locale, che verrà importato nell'organizzazione di Skype for business online nel prossimo passaggio.

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

In Exchange PowerShell nell'organizzazione di Exchange locale, eseguire lo script di PowerShell appena creato. Ad esempio: .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Passaggio 5: caricare il certificato di autorizzazione locale in Azure Active Directory ACS

Successivamente, utilizzare Windows PowerShell per caricare il certificato di autorizzazione in locale esportato nel passaggio precedente in Azure Active Directory Access Control Services (ACS). A tale scopo, è necessario che sia già installato il modulo di Azure Active Directory per i cmdlet di Windows PowerShell. Se non è installato, passare a [https://aka.ms/aadposh](https://aka.ms/aadposh) per installare il modulo di Azure Active Directory per Windows PowerShell. Completare i passaggi seguenti dopo l'installazione del modulo di Azure Active Directory per Windows PowerShell.

1. Fare clic sul collegamento di **Azure Active Directory Module per Windows PowerShell** per aprire un'area di lavoro di Windows PowerShell in cui sono installati i cmdlet di Azure ad. Tutti i comandi di questo passaggio verranno eseguiti utilizzando la console di Windows PowerShell per Azure Active Directory.

2. Salvare il testo seguente in un file di script di PowerShell denominato, ad esempio,  `UploadAuthCert.ps1` .

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

4. Dopo avere avviato lo script, viene visualizzata una finestra di dialogo relativa alle credenziali. Immettere le credenziali per l'account amministratore tenant dell'organizzazione di Microsoft Online Azure AD. Dopo aver eseguito lo script, lasciare aperta la sessione di Windows PowerShell per Azure AD. Questa verrà utilizzata per eseguire uno script di PowerShell nel prossimo passaggio.

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>Passaggio 6: verificare che il certificato sia stato caricato nell'entità servizio Skype for business
1. In PowerShell aperto e autenticato in Azure Active Directory, eseguire le operazioni seguenti
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. Quando richiesto per ReturnKeyValues, premere INVIO.
3. Verificare che venga visualizzata una chiave elencata con data di inizio e data di fine che corrisponde alle date di inizio e fine del certificato OAuth di Exchange

### <a name="verify-your-success"></a>Verificare l'esito positivo

Verificare che la configurazione sia corretta verificando che alcune delle funzionalità funzionino correttamente. 

1. Confermare che gli utenti di Skype for business con il servizio di segreteria cloud, in un'organizzazione con una configurazione ibrida del server Exchange, possano modificare correttamente i messaggi di saluto della segreteria telefonica.

2. Verificare che la cronologia delle conversazioni per i client mobili sia visibile nella cartella Cronologia conversazioni di Outlook.

3. Verificare che i messaggi di chat archiviati vengano depositati nella cassetta postale locale dell'utente nella cartella Purges mediante [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).

In alternativa, Guarda il traffico. Il traffico in un handshake OAuth è molto caratteristico (e non assomiglia all'autenticazione di base), in particolare attorno ai regni, in cui si inizierà a vedere il traffico dell'emittente simile al seguente: 00000004-0000-0FF1-CE00-000000000000 @ (a volte con un/prima del segno @), nei token che vengono passati. Non verrà visualizzato alcun nome utente o password, ovvero il punto di OAuth. Tuttavia, l'emittente ' Office '-in questo caso ' 4' è Skype for business-e l'area di sottoscrizione.

Se si desidera verificare che l'utilizzo di OAuth sia corretto, accertarsi di sapere cosa aspettarsi e sapere come dovrebbe essere il traffico. Pertanto, ecco [cosa aspettarsi](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), ecco un esempio piuttosto standard [di traffico OAuth in un'applicazione Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (è molto utile leggere, anche se non utilizza i token di aggiornamento), e ci sono estensioni Fiddler che consentono di esaminare il token OAuth JWT (JSON Web).

Di seguito è [riportato un esempio di impostazione di uno](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), ma è possibile utilizzare qualsiasi strumento di traccia di rete che si desidera intraprendere questo processo.

## <a name="related-topics"></a>Argomenti correlati

[Configurazione dell'autenticazione OAuth tra organizzazioni Exchange ed Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
