---
title: Configurare l'autenticazione da server a server per un ambiente ibrido di Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: "Riepilogo: configurare l'autenticazione da server a server per un ambiente ibrido di Skype for Business Server."
ms.openlocfilehash: 2879a1acc35a2c8928a95af913476c26028d6e6c
ms.sourcegitcommit: 1721acdd507591d16a4e766b390b997979d985e5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "37305772"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Configurare l'autenticazione da server a server per un ambiente ibrido di Skype for Business Server.

**Riepilogo:** Configurare l'autenticazione da server a server per l'ambiente ibrido di Skype for Business Server.

In una configurazione ibrida, alcuni utenti sono ospitati in un'installazione locale di Skype for Business Server mentre altri utenti si trovano nella versione di Office 365 di Skype for Business Server. Per configurare l'autenticazione da server a server in un ambiente ibrido, è prima di tutto necessario configurare l'installazione locale di Skype for Business Server per considerare attendibile il server di autorizzazione di Office 365. Il passaggio iniziale di questo processo può essere eseguito eseguendo il seguente script di Skype for Business Server Management Shell:

```
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

Tieni presente che il nome dell'area di autenticazione per un tenant è in genere diverso rispetto al nome dell'organizzazione; il nome Realm è infatti quasi sempre uguale all'ID tenant. Per questo motivo, la prima riga nello script viene usata per restituire il valore della proprietà ID tenant per il tenant specificato (in questo caso fabrikam.com) e quindi assegnare il nome alla variabile $TenantId:

```
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

Per eseguire questo script, è necessario aver installato il modulo di PowerShell di Skype for business online e connettersi al tenant con questo modulo. Se non sono stati installati questi cmdlet, lo script non riuscirà perché il cmdlet Get-CsTenant non sarà disponibile. Al termine dell'esecuzione dello script, è necessario configurare una relazione di trust tra Skype for Business Server e il server di autorizzazione e una seconda relazione di trust tra Exchange 2013/2016 e il server di autorizzazione. Questa operazione può essere eseguita solo usando i cmdlet dei Microsoft Online Services.

> [!NOTE]
> Se non sono stati installati i cmdlet dei Microsoft Online Services, sarà necessario installarlo dal repository di PowerShell con il cmdlet `install-module MSOnline`. Informazioni dettagliate per l'installazione e l'uso del modulo Microsoft Online Services si trovano nel sito Web di Office 365. Queste istruzioni spiegano anche come configurare Single Sign-on, Federation e la sincronizzazione tra Office 365 e Active Directory. 



Dopo aver configurato Office 365 e dopo aver creato le entità di servizio di Office 365 per Skype for Business Server ed Exchange 2013, sarà necessario registrare le credenziali con queste entità di servizio. Per eseguire questa operazione, devi prima ottenere un certificato X. 509 Base64 salvato come. File CER. Questo certificato verrà quindi applicato alle entità di servizio di Office 365.

Dopo aver ottenuto il certificato X. 509, aprire la console di PowerShell e importare il modulo Microsoft online di Windows PowerShell contenente i cmdlet che possono essere usati per gestire le entità di servizio:

```
Import-Module MSOnline
```

Quando il modulo è stato importato, digitare il comando seguente e quindi premere INVIO per connettersi a Office 365:

```
Connect-MsolService
```

Dopo aver premuto INVIO, verrà visualizzata una finestra di dialogo credenziali. Immettere il nome utente e la password di Office 365 nella finestra di dialogo e quindi fare clic su OK.

Non appena si è connessi a Office 365, è possibile eseguire il comando seguente per restituire informazioni sulle entità di servizio:

```
Get-MsolServicePrincipal
```

È consigliabile recuperare informazioni simili a quelle per tutte le entità di servizio:

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

Il passaggio successivo consiste nell'importare, codificare e assegnare il certificato X. 509. Per importare e codificare il certificato, usare i comandi di Windows PowerShell seguenti, in modo da specificare il percorso completo del file. File CER quando si chiama il metodo di importazione:

```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

Dopo aver importato e codificato il certificato, è possibile assegnare il certificato alle entità di servizio di Office 365. A questo scopo, USA prima di tutto Get-MsolServicePrincipal viene per recuperare il valore della proprietà AppPrincipalId sia per Skype for Business Server che per le entità dei servizi di Microsoft Exchange. il valore della proprietà AppPrincipalId verrà usato per identificare l'entità del servizio a cui è stato assegnato il certificato. Con il valore della proprietà AppPrincipalId per Skype for Business Server in mano, usa il comando seguente per assegnare il certificato alla versione Skype for business online:

```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Devi quindi ripetere il comando, questa volta usando il valore della proprietà AppPrincipalId per Exchange 2013.

Se in seguito è necessario eliminare il certificato, ad esempio se è scaduto, è possibile eseguire prima di tutto il recupero di KeyId per il certificato:

```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

Il comando restituirà dati come questo:

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

È quindi possibile eliminare il certificato usando un comando simile al seguente:

```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

Oltre ad assegnare un certificato, è necessario configurare anche l'entità del servizio Exchange Online e configurare la versione locale degli URL dei servizi Web esterni di Skype for Business Server come entità di servizio di Office 365. Questa operazione può essere eseguita eseguendo i due comandi seguenti. 

Nell'esempio seguente, Pool1ExternalWebFQDN.contoso.com è l'URL dei servizi Web esterni per il pool di Skype for Business Server. È consigliabile ripetere questi passaggi per aggiungere tutti gli URL dei servizi Web esterni nella distribuzione.

```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
