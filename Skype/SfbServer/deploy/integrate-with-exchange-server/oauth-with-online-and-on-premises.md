---
title: Integrazione tra Skype for business online ed Exchange Server
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
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
description: La configurazione dell'autenticazione OAuth tra Exchange in locale e Skype for business online consente le funzionalità di integrazione di Skype for business e Exchange descritte nel supporto delle funzionalità.
ms.openlocfilehash: b673332ea4c4428e68d6434c4638cbc78aa0ba7d
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797047"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Configurare l'integrazione e il protocollo OAuth tra Skype for business online ed Exchange Server 

La configurazione dell'integrazione tra Exchange Server e Skype for business online consente le caratteristiche di integrazione di Skype for business e Exchange descritte nel [supporto delle funzionalità](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).

Questo argomento si applica all'integrazione con Exchange Server 2013 a 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Cosa occorre sapere prima di iniziare?

- Tempo stimato per completare l'attività: 15 minuti

-  Per eseguire questa procedura o procedure, è necessario disporre delle autorizzazioni assegnate. Per vedere quali autorizzazioni sono necessarie, vedere l'argomento [Autorizzazioni infrastruttura Shell e Exchange](https://go.microsoft.com/fwlink/p/?LinkId=746511) .

- Per informazioni sulle scelte rapide da tastiera che possono essere applicate alle procedure descritte in questo argomento, vedere [scelte rapide da tastiera nell'interfaccia di amministrazione di Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

- Per informazioni sulla compatibilità, vedere [compatibilità con Skype for business con le app di Office](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Configurare l'integrazione tra Exchange Server e Office 365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Passaggio 1: configurare l'autenticazione OAuth tra Exchange Server e Office 365

Eseguire la procedura descritta nell'articolo seguente:

[Configurare l'autenticazione OAuth tra le organizzazioni Exchange e Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Passaggio 2: creare un nuovo account utente di posta elettronica per l'applicazione partner di Skype for business online

Questo passaggio viene eseguito nel server Exchange. Creerà un utente di posta elettronica e gli assegnerà i diritti appropriati per il ruolo di gestione. Questo account verrà quindi usato nel passaggio successivo.

Specificare un dominio verificato per l'organizzazione di Exchange. Questo dominio deve essere lo stesso dominio usato come dominio SMTP principale usato per gli account di Exchange locali. Questo dominio viene indicato come \<dominio\> verificato nella procedura seguente. Inoltre, \<DomainControllerFQDN\> deve essere il nome di dominio completo di un domain controller.

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Questo comando consente di nascondere il nuovo utente di posta elettronica dagli elenchi di indirizzi.

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Questi due comandi successivi assegnerà il ruolo di gestione di UserApplication e ArchiveApplication al nuovo account.

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Passaggio 3: creare e abilitare un'applicazione partner per Skype for business online 

Crea una nuova applicazione partner e userà l'account appena creato. Eseguire il comando seguente in PowerShell di Exchange nell'organizzazione di Exchange locale.

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>Passaggio 4: esportare il certificato di autorizzazione locale

Eseguire uno script di PowerShell per esportare il certificato di autorizzazione locale, che verrà importato nell'organizzazione di Skype for business online nel prossimo passaggio.

Salvare il testo seguente in un file di script di PowerShell denominato, ad esempio, ExportAuthCert. ps1.

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

In PowerShell di Exchange nell'organizzazione di Exchange locale eseguire lo script di PowerShell appena creato. Ad esempio: .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Passaggio 5: caricare il certificato di autorizzazione locale in Azure Active Directory ACS

Utilizzare quindi Windows PowerShell per caricare il certificato di autorizzazione locale esportato nel passaggio precedente in Azure Active Directory Access Control Services (ACS). A questo scopo, è necessario che il modulo Azure Active Directory per i cmdlet di Windows PowerShell sia già installato. Se non è installato, accedere [https://aka.ms/aadposh](https://aka.ms/aadposh) a per installare il modulo di Azure Active Directory per Windows PowerShell. Completare la procedura seguente dopo l'installazione del modulo di Azure Active Directory per Windows PowerShell.

1. Fare clic sul collegamento al **modulo di Azure Active Directory per Windows PowerShell** per aprire un'area di lavoro di Windows PowerShell in cui sono installati i cmdlet di Azure ad. Tutti i comandi in questo passaggio verranno eseguiti usando la console di Windows PowerShell per Azure Active Directory.

2. Salvare il testo seguente in un file di script di PowerShell denominato, ad `UploadAuthCert.ps1`esempio.

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

3. Eseguire lo script di PowerShell creato nel passaggio precedente. Per esempio:`.\UploadAuthCert.ps1`

4. Dopo aver avviato lo script, viene visualizzata una finestra di dialogo credenziali. Immettere le credenziali per l'account di amministratore del tenant dell'organizzazione di Microsoft Online Azure AD. Dopo aver eseguito lo script, lascia aperta la sessione di Windows PowerShell per Azure AD. Verrà usato per eseguire uno script di PowerShell nel passaggio successivo.

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>Passaggio 6: verificare che il certificato sia stato caricato nell'entità del servizio Skype for business
1. In PowerShell aperto e autenticato in Azure Active Directory eseguire le operazioni seguenti
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. Premere INVIO quando richiesto per ReturnKeyValues
3. Confermare la visualizzazione di una chiave elencata con i dati di inizio e di fine corrispondenti alle date di inizio e di fine del certificato OAuth di Exchange

### <a name="verify-your-success"></a>Verificare il successo

Verificare che la configurazione sia corretta verificando che alcune delle caratteristiche funzionino correttamente. 

1. Verificare che gli utenti di Skype for business con il servizio cloud voicemail, in un'organizzazione con configurazione ibrida di Exchange Server, possano modificare correttamente i messaggi di saluto della segreteria telefonica.

2. Verificare che la cronologia delle conversazioni per i client mobili sia visibile nella cartella Cronologia conversazioni di Outlook.

3. Verificare che i messaggi di chat archiviati vengano depositati nella cassetta postale dell'utente locale nella cartella Purges con [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).

In alternativa, esamina il traffico. Il traffico in un handshake OAuth è davvero distintivo (e non ha l'aspetto dell'autenticazione di base), in particolare intorno ai regni, in cui si inizierà a vedere il traffico dell'emittente che ha un aspetto simile al seguente: 00000004-0000-0FF1-CE00-000000000000 @ (a volte con un/prima del simbolo @), nei token passati. Non verrà visualizzato un nome utente o una password, ovvero il punto di OAuth. Ma vedrai l'emittente "Office", in questo caso "4", Skype for business, e l'ambito dell'abbonamento.

Per assicurarsi che si stia usando OAuth, accertarsi di sapere cosa aspettarsi e sapere come dovrebbe essere il traffico. Ecco [cosa aspettarsi](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), ecco un esempio abbastanza standard [di traffico OAuth in un'applicazione Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (molto utile da leggere, anche se non usa i token di aggiornamento) e sono disponibili estensioni di Fiddler che consentono di esaminare il token Web OAuth JWT.

Ecco un [esempio di impostazione di uno](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), ma è possibile usare qualsiasi strumento di analisi della rete che si vuole intraprendere in questo processo.

## <a name="related-topics"></a>Argomenti correlati

[Configurare l'autenticazione OAuth tra le organizzazioni Exchange e Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
