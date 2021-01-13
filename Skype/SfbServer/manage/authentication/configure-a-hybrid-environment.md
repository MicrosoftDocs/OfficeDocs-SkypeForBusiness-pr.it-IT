---
title: Configurare l'autenticazione da server a server per un ambiente ibrido di Skype for Business Server
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
description: "Sintesi: configurare l'autenticazione da server a server per un ambiente ibrido di Skype for Business Server."
ms.openlocfilehash: 6f4e11b54f0292b1ccb91ab486e2e638a4dcceb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828486"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Configurare l'autenticazione da server a server per un ambiente ibrido di Skype for Business Server.

**Riepilogo:** Configurare l'autenticazione da server a server per l'ambiente ibrido di Skype for Business Server.

In una configurazione ibrida, alcuni utenti sono ospitati in un'installazione locale di Skype for Business Server, mentre altri utenti sono ospitati nella versione Microsoft 365 o Office 365 di Skype for Business Server. Per configurare l'autenticazione da server a server in un ambiente ibrido, è innanzitutto necessario configurare l'installazione locale di Skype for Business Server in modo che consideri attendibile il server di autorizzazione. Il passaggio iniziale di questo processo può essere eseguito eseguendo il seguente script per la gestione di Skype for Business Server:

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

Per eseguire questo script, è necessario aver installato il modulo di PowerShell per Skype for business online e connettersi al tenant con questo modulo. Se i cmdlet non sono stati installati, lo script avrà esito negativo perché il cmdlet Get-CsTenant non sarà disponibile. Al termine dell'esecuzione dello script, è necessario configurare una relazione di trust tra Skype for Business Server e il server di autorizzazione, nonché una seconda relazione di trust tra Exchange 2013/2016 e il server di autorizzazione. È possibile farlo soltanto attraverso i cmdlet di Microsoft Online Services.

> [!NOTE]
> Se i cmdlet dei Microsoft Online Services non sono stati installati, sarà necessario installarlo dal repository di PowerShell con il cmdlet `install-module MSOnline` . Informazioni dettagliate per l'installazione e l'utilizzo del modulo dei Microsoft Online Services sono disponibili nel sito Web Microsoft 365. Queste istruzioni illustrano inoltre come configurare il servizio Single Sign-on, la Federazione e la sincronizzazione tra Microsoft 365 o Office 365 e Active Directory. 



Dopo aver configurato Microsoft 365 o Office 365 e dopo aver creato Microsoft 365 o le entità di servizio di Office 365 per Skype for Business Server e Exchange 2013, sarà necessario registrare le credenziali con queste entità di servizio. Per eseguire questa operazione, è innanzitutto necessario ottenere un certificato X. 509 Base64 salvato come a. File CER. Questo certificato verrà quindi applicato alle entità di servizio Microsoft 365 o Office 365.

Dopo aver ottenuto il certificato X. 509, aprire console PowerShell e importare il modulo Microsoft online di Windows PowerShell contenente i cmdlet che è possibile utilizzare per gestire le entità di servizio:

```PowerShell
Import-Module MSOnline
```

Quando il modulo è stato importato, digitare il comando seguente e quindi premere INVIO:

```PowerShell
Connect-MsolService
```

A questo punto, viene visualizzata una finestra di dialogo delle credenziali. Immettere il nome utente e la password di Microsoft 365 o Office 365 nella finestra di dialogo e quindi fare clic su OK.

Non appena si è connessi a Microsoft 365 o Office 365, è possibile eseguire il comando seguente per restituire le informazioni sulle entità di servizio:

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

Il passaggio successivo consiste nell'importazione, codifica e assegnazione del certificato X.509. Per importare e codificare il certificato, utilizzare i seguenti comandi di Windows PowerShell, assicurandosi di specificare il percorso completo del file. File CER quando si chiama il metodo Import:

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

Dopo che il certificato è stato importato e codificato, è possibile assegnare il certificato alle entità di servizio Microsoft 365 o Office 365. A tale scopo, utilizzare prima la Get-MsolServicePrincipal per recuperare il valore della proprietà AppPrincipalId sia per le entità di servizio Skype for Business Server che di Microsoft Exchange. il valore della proprietà AppPrincipalId verrà utilizzato per identificare l'entità di servizio a cui è assegnato il certificato. Con il valore della proprietà AppPrincipalId per Skype for Business Server in mano, utilizzare il seguente comando per assegnare il certificato alla versione di Skype for business online:

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

È quindi necessario ripetere il comando, stavolta utilizzando il valore della proprietà AppPrincipalId per Exchange 2013.

Se in seguito è necessario eliminare il certificato, ad esempio se è scaduto, è possibile farlo recuperando prima il KeyId per il certificato:

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

Oltre all'assegnazione di un certificato, è necessario configurare anche l'entità servizio Exchange Online e configurare la versione locale degli URL dei servizi Web esterni di Skype for Business Server come entità di servizio Microsoft 365 o Office 365. Questa operazione può essere eseguita eseguendo i due comandi seguenti. 

Nell'esempio seguente, Pool1ExternalWebFQDN.contoso.com è l'URL dei servizi Web esterni per il pool di Skype for Business Server. È necessario ripetere questi passaggi per aggiungere tutti gli URL dei servizi Web esterni nella distribuzione.

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
