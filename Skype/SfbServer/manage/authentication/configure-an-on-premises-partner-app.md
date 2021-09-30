---
title: Configurare un'applicazione partner locale per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: "Riepilogo: configurare un'applicazione partner locale per Skype for Business Server."
ms.openlocfilehash: d0907d73d6a23c0a5b9a1f1725503b72c5bce993
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012620"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a>Configurare un'applicazione partner locale per Skype for Business Server
 
**Riepilogo:** Configurare un'applicazione partner locale per Skype for Business Server.
  
Dopo aver assegnato il certificato OAuthTokenIssuer, devi configurare le applicazioni Skype for Business Server partner. La procedura che sta per essere illustrata configura sia Microsoft Exchange Server 2013 che SharePoint di agire come applicazioni partner, che è facoltativo. Per configurare un'applicazione partner locale, è necessario innanzitutto copiare lo script di Windows PowerShell seguente e incollare il codice in Blocco note (o in qualsiasi altro editor di testo):
  
```PowerShell
if ((Get-CsPartnerApplication -ErrorAction SilentlyContinue) -ne $Null)
   {
       Remove-CsPartnerApplication app
   }

$exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
        
if ($exch -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
    }
else
    {
       if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.exchange
New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
           }
        else
           {
             Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full 
           }
     }

$shp = Get-CsPartnerApplication microsoft.sharepoint -ErrorAction SilentlyContinue
        
if ($shp -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
    }
else
    {
       if ($shp.ApplicationIdentifier -ne "00000003-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.sharepoint
  
             New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl https://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 -ApplicationTrustLevel Full 
           }
        else
           {
             Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
            }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Dopo aver copiato il codice, salvare lo script con estensione di file PS1 (ad esempio, C:\Script\AutServer-ServerAuth.ps1). Si noti che, prima di eseguire questo script, è necessario sostituire gli URL dei metadati e con gli URL dei metadati utilizzati rispettivamente dai server `https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1` `http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1` Exchange 2013 e SharePoint. Vedi la documentazione del prodotto per Exchange 2013 e SharePoint per informazioni su come identificare l'URL dei metadati del rispettivo prodotto.
  
Nell'ultima riga dello script si potrà notare che il cmdlet di Set-CsOAuthConfiguration viene chiamato con questa sintassi:
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Dato che il parametro Realm non è stato utilizzato per la chiamata di Set-CsOAuthConfiguration, l'area di autenticazione verrà impostata automaticamente sul nome di dominio completo (FQDN) dell'organizzazione (ad esempio, litwareinc.com). Se il nome dell'area di autenticazione è diverso dal nome dell'organizzazione, è necessario includere il nome dell'area di autenticazione nel modo seguente:
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

Dopo aver apportato queste modifiche, è possibile eseguire lo script e configurare sia Exchange 2013 che SharePoint come applicazioni partner eseguendo il file script dall'interno di Skype for Business Server Management Shell. Ad esempio:
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

Si noti che è possibile eseguire questo script anche se non sono installati Exchange 2013 e SharePoint Server:, non si verificheranno problemi se, ad esempio, si configura SharePoint Server come applicazione partner anche se non è installato SharePoint Server.
  
Quando si esegue lo script potrebbe essere visualizzato un messaggio di errore simile al seguente:
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

Questo messaggio di errore indica in genere uno di due problemi: 1) uno degli URL specificati nello script non è valido (ovvero uno degli URL dei metadati non è corretto) oppure 2) non è possibile contattare uno degli URL dei metadati. In questi casi, verificare che gli URL siano corretti e accessibili, quindi rieseguire lo script.
  
Dopo aver creato l'applicazione partner per Skype for Business Server è necessario configurare Skype for Business Server essere un'applicazione partner per Exchange 2013. È possibile configurare le applicazioni partner per Exchange 2013 eseguendo lo script Configure-EnterprisePartnerApplication.ps1; devi solo specificare l'URL dei metadati per Skype for Business Server e indicare che Skype for Business Server è la nuova applicazione partner. 
  
Per configurare Skype for Business Server come applicazione partner per Exchange, aprire Exchange Management Shell ed eseguire un comando simile al seguente
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


