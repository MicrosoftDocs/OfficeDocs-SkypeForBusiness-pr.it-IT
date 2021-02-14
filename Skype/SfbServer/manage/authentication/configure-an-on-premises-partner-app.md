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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: "Riepilogo: configurare un'applicazione partner locale per Skype for Business Server."
ms.openlocfilehash: 82db666dbbd94fdae8a99bca13954d33d6d5805f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828436"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a><span data-ttu-id="0bc93-103">Configurare un'applicazione partner locale per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0bc93-103">Configure an on-premises partner application for Skype for Business Server</span></span>
 
<span data-ttu-id="0bc93-104">**Riepilogo:** Configurare un'applicazione partner locale per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0bc93-104">**Summary:** Configure an on-premises partner application for Skype for Business Server.</span></span>
  
<span data-ttu-id="0bc93-105">Dopo aver assegnato il certificato OAuthTokenIssuer, è necessario configurare le applicazioni partner di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0bc93-105">After you have assigned the OAuthTokenIssuer certificate you must then configure your Skype for Business Server partner applications.</span></span> <span data-ttu-id="0bc93-106">La procedura che sta per essere discussa configura sia Microsoft Exchange Server 2013 che SharePoint per agire come applicazioni partner, operazione facoltativa. Per configurare un'applicazione partner locale, è necessario innanzitutto copiare lo script di Windows PowerShell seguente e incollare il codice nel Blocco note (o in qualsiasi altro editor di testo):</span><span class="sxs-lookup"><span data-stu-id="0bc93-106">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and SharePoint to act as partner applications, which is optional.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>
  
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

<span data-ttu-id="0bc93-107">Dopo aver copiato il codice, salvare lo script con estensione di file PS1 (ad esempio, C:\Script\AutServer-ServerAuth.ps1).</span><span class="sxs-lookup"><span data-stu-id="0bc93-107">After copying the code, save the script using a .PS1 file extension (for example, C:\Scripts\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="0bc93-108">Si noti che, prima di eseguire questo script, è necessario sostituire gli URL dei metadati e gli URL dei metadati utilizzati rispettivamente dai server https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 Exchange 2013 e SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0bc93-108">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="0bc93-109">Per informazioni su come identificare l'URL dei metadati del rispettivo prodotto, vedere la documentazione del prodotto per Exchange 2013 e SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0bc93-109">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>
  
<span data-ttu-id="0bc93-110">Nell'ultima riga dello script si potrà notare che il cmdlet di Set-CsOAuthConfiguration viene chiamato con questa sintassi:</span><span class="sxs-lookup"><span data-stu-id="0bc93-110">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="0bc93-p103">Dato che il parametro Realm non è stato utilizzato per la chiamata di Set-CsOAuthConfiguration, l'area di autenticazione verrà impostata automaticamente sul nome di dominio completo (FQDN) dell'organizzazione (ad esempio, litwareinc.com). Se il nome dell'area di autenticazione è diverso dal nome dell'organizzazione, è necessario includere il nome dell'area di autenticazione nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="0bc93-p103">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com). If your realm name is different from your organization name then you should include the realm name, like this:</span></span>
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

<span data-ttu-id="0bc93-113">Dopo aver apportato queste modifiche, è possibile eseguire lo script e configurare Sia Exchange 2013 che SharePoint come applicazioni partner eseguendo il file script da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0bc93-113">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="0bc93-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0bc93-114">For example:</span></span>
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

<span data-ttu-id="0bc93-115">Si noti che è possibile eseguire questo script anche se non sono installati sia Exchange 2013 che SharePoint Server: non si verificheranno problemi se, ad esempio, si configura SharePoint Server come applicazione partner anche se SharePoint Server non è installato.</span><span class="sxs-lookup"><span data-stu-id="0bc93-115">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>
  
<span data-ttu-id="0bc93-116">Quando si esegue lo script potrebbe essere visualizzato un messaggio di errore simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="0bc93-116">When you run this script you might receive an error message similar to the following:</span></span>
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

<span data-ttu-id="0bc93-p105">Questo messaggio di errore indica in genere uno di due problemi: 1) uno degli URL specificati nello script non è valido (ovvero uno degli URL dei metadati non è corretto) oppure 2) non è possibile contattare uno degli URL dei metadati. In questi casi, verificare che gli URL siano corretti e accessibili, quindi rieseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="0bc93-p105">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted. If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>
  
<span data-ttu-id="0bc93-119">Dopo aver creato l'applicazione partner per Skype for Business Server, è necessario configurare Skype for Business Server come applicazione partner per Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="0bc93-119">After creating the partner application for Skype for Business Server you must then configure Skype for Business Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="0bc93-120">È possibile configurare le applicazioni partner per Exchange 2013 eseguendo lo script Configure-EnterprisePartnerApplication.ps1; tutto quello che devi fare è specificare l'URL dei metadati per Skype for Business Server e indicare che Skype for Business Server è la nuova applicazione partner.</span><span class="sxs-lookup"><span data-stu-id="0bc93-120">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Skype for Business Server and indicate that Skype for Business Server is the new partner application.</span></span> 
  
<span data-ttu-id="0bc93-121">Per configurare Skype for Business Server come applicazione partner per Exchange, aprire Exchange Management Shell ed eseguire un comando simile al seguente</span><span class="sxs-lookup"><span data-stu-id="0bc93-121">To configure Skype for Business Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


