---
title: Configurare l'autenticazione da server a server per un Skype for Business Server ibrido
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: "Riepilogo: configurare l'autenticazione da server a server per un Skype for Business Server ibrido."
ms.openlocfilehash: 0a5060f9f40b7887de0b9afefa0b8f43f65f76120d430db01eaf32095af66f84
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315722"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Configurare l'autenticazione da server a server per un Skype for Business Server ibrido.

**Riepilogo:** Configurare l'autenticazione da server a server per Skype for Business Server ibrido.

In una configurazione ibrida, alcuni utenti sono ospitati in un'installazione locale di Skype for Business Server mentre altri utenti sono ospitati nella versione Microsoft 365 o Office 365 di Skype for Business Server. Per configurare l'autenticazione da server a server in un ambiente ibrido, è innanzitutto necessario configurare l'installazione locale di Skype for Business Server per considerare attendibile il server di autorizzazione. Il passaggio iniziale di questo processo può essere eseguito eseguendo il seguente script Skype for Business Server Management Shell:

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId

$sts = Get-CsOAuthServer microsoft.sts -ErrorAction SilentlyContinue

   if ($sts -eq $null)
      {
         New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
      }
   else
      {
         if ($sts.MetadataUrl -ne  "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1")
            {
               Remove-CsOAuthServer microsoft.sts
               New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
            }
        }

$exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue

if ($exch -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer
    }
else
    {
       if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.exchange
             New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer 
          }
       else
          {
             Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full -UseOAuthServer
          }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Tenere a mente che il nome dell'area di autenticazione di un tenant è solitamente diverso da quello dell'organizzazione. Quasi mai il nome dell'area di autenticazione corrisponde a quello dell'ID del tenant. Per questo motivo, la prima riga dello script è utilizzata per restituire il valore della proprietà TenantId del tenant specificato (in questo caso, fabrikam.com) e per poi assegnare il nome alla variabile $TenantId:

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

Per eseguire questo script, è necessario aver installato Skype for Business PowerShell online e connettersi al tenant con questo modulo. Se non sono stati installati questi cmdlet, lo script avrà esito negativo perché il cmdlet Get-CsTenant non sarà disponibile. Al termine dello script, è necessario configurare una relazione di trust tra Skype for Business Server e il server di autorizzazione e una seconda relazione di trust tra Exchange 2013/2016 e il server di autorizzazione. È possibile farlo soltanto attraverso i cmdlet di Microsoft Online Services.

> [!NOTE]
> Se i cmdlet di Microsoft Online Services non sono stati installati, sarà necessario installarlo dal repository powershell con il cmdlet `install-module MSOnline` . Informazioni dettagliate per l'installazione e l'Microsoft Online Services modulo sono disponibili nel Microsoft 365 web. Queste istruzioni illustrano anche come configurare single sign-on, federazione e sincronizzazione tra Microsoft 365 o Office 365 e Active Directory. 



Dopo aver configurato Microsoft 365 o Office 365 e dopo aver creato le entità servizio Microsoft 365 o Office 365 per Skype for Business Server e Exchange 2013, sarà necessario registrare le credenziali con queste entità servizio. A tale scopo, è innanzitutto necessario ottenere un certificato X.509 Base64 salvato come . File CER. Questo certificato verrà quindi applicato alle entità Microsoft 365 o Office 365 servizio.

Dopo aver ottenuto il certificato X.509, aprire la console di PowerShell e importare il modulo microsoft online Windows PowerShell contenente i cmdlet che possono essere utilizzati per gestire le entità servizio:

```PowerShell
Import-Module MSOnline
```

Dopo l'importazione del modulo, digitare il comando seguente e quindi premere INVIO:

```PowerShell
Connect-MsolService
```

A questo punto, viene visualizzata una finestra di dialogo delle credenziali. Immettere il Microsoft 365 o Office 365 utente e la password nella finestra di dialogo e quindi fare clic su OK.

Non appena si è connessi a Microsoft 365 o Office 365, è quindi possibile eseguire il comando seguente per restituire informazioni sulle entità servizio:

```PowerShell
Get-MsolServicePrincipal
```

Si dovrebbero ottenere informazioni simili alle seguenti, per tutti i nomi del servizio principale:

<pre>
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
</pre>

Il passaggio successivo consiste nell'importazione, codifica e assegnazione del certificato X.509. Per importare e codificare il certificato, utilizzare i comandi Windows PowerShell seguenti, assicurandoti di specificare il percorso completo del file . File CER quando si chiama il metodo Import:

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

Dopo aver importato e codificato il certificato, è possibile assegnarlo alle entità servizio Microsoft 365 o Office 365 servizio. A tale scopo, utilizzare innanzitutto il Get-MsolServicePrincipal per recuperare il valore della proprietà AppPrincipalId sia per il Skype for Business Server che per le entità servizio di Microsoft Exchange; il valore della proprietà AppPrincipalId verrà utilizzato per identificare l'entità servizio a cui viene assegnato il certificato. Con il valore della proprietà AppPrincipalId per Skype for Business Server, utilizzare il comando seguente per assegnare il certificato a Skype for Business online:

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Dovresti quindi ripetere il comando, questa volta usando il valore della proprietà AppPrincipalId per Exchange 2013.

Se in un secondo momento è necessario eliminare il certificato, ad esempio se è scaduto, è possibile farlo recuperando innanzitutto KeyId per il certificato:

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

Il comando restituisce dati simili ai seguenti:

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

È possibile eliminare il certificato utilizzando un comando simile al seguente:

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

Oltre ad assegnare un certificato, è inoltre necessario configurare l'entità servizio di Exchange Online e configurare la versione locale degli URL dei servizi Web esterni di Skype for Business Server come entità servizio Microsoft 365 o Office 365. Questa operazione può essere eseguita eseguendo i due comandi seguenti. 

Nell'esempio seguente, Pool1ExternalWebFQDN.contoso.com è l'URL dei servizi Web esterni per il pool Skype for Business Server pool. Ripetere questi passaggi per aggiungere tutti gli URL dei servizi Web esterni nella distribuzione.

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
