---
title: Configurazione di un'applicazione partner locale per Lync Server 2013
description: Configurazione di un'applicazione partner locale per Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring an on-premises partner application for Lync Server 2013
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204975(v=OCS.15)
ms:contentKeyID: 48184412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0401634c6cb7afc451652ffbaf55cdc01a7ca89
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570922"
---
# <a name="configuring-an-on-premises-partner-application-for-microsoft-lync-server-2013"></a><span data-ttu-id="ef2ac-103">Configurazione di un'applicazione partner locale per Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef2ac-103">Configuring an on-premises partner application for Microsoft Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef2ac-104">_**Ultimo argomento modificato:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="ef2ac-104">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="ef2ac-105">Dopo aver assegnato il certificato OAuthTokenIssuer, è necessario configurare le applicazioni partner di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ef2ac-105">After you have assigned the OAuthTokenIssuer certificate you must then configure your Microsoft Lync Server 2013 partner applications.</span></span> <span data-ttu-id="ef2ac-106">La procedura per la discussione configura sia Microsoft Exchange Server 2013 che Microsoft SharePoint per fungere da applicazioni partner. Per configurare un'applicazione partner locale, è necessario iniziare copiando lo script di Windows PowerShell seguente e incollando il codice nel blocco note (o in qualsiasi altro editor di testo):</span><span class="sxs-lookup"><span data-stu-id="ef2ac-106">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and Microsoft SharePoint to act as partner applications.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>

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
      
                 New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
                }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="ef2ac-107">Dopo aver copiato il codice, salvare lo script utilizzando un. Estensione di file PS1, ad esempio C: \\ scripts \\ServerToServerAuth.ps1).</span><span class="sxs-lookup"><span data-stu-id="ef2ac-107">After copying the code, save the script using a .PS1 file extension (for example, C:\\Scripts\\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="ef2ac-108">Tenere presente che, prima di eseguire lo script, è necessario sostituire gli URL dei metadati https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 e http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx gli URL dei metadati utilizzati rispettivamente dai server Exchange 2013 e SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ef2ac-108">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="ef2ac-109">Per informazioni su come identificare l'URL dei metadati del prodotto rispettivo, vedere la documentazione del prodotto per Exchange 2013 e SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ef2ac-109">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>

<span data-ttu-id="ef2ac-110">Nell'ultima riga dello script si potrà notare che il cmdlet di Set-CsOAuthConfiguration viene chiamato con questa sintassi:</span><span class="sxs-lookup"><span data-stu-id="ef2ac-110">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="ef2ac-p103">Dato che il parametro Realm non è stato utilizzato per la chiamata di Set-CsOAuthConfiguration, l'area di autenticazione verrà impostata automaticamente sul nome di dominio completo (FQDN) dell'organizzazione (ad esempio, litwareinc.com). Se il nome dell'area di autenticazione è diverso dal nome dell'organizzazione, è necessario includere il nome dell'area di autenticazione nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="ef2ac-p103">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com). If your realm name is different from your organization name then you should include the realm name, like this:</span></span>

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

<span data-ttu-id="ef2ac-113">Dopo aver apportato queste modifiche, è possibile eseguire lo script e configurare sia Exchange 2013 che SharePoint come applicazioni partner, eseguendo il file di script all'interno di Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ef2ac-113">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="ef2ac-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ef2ac-114">For example:</span></span>

    C:\Scripts\ServerToServerAuth.ps1

<span data-ttu-id="ef2ac-115">Si noti che è possibile eseguire questo script anche se non sono installati sia Exchange 2013 che SharePoint Server:, non si verificherà alcun problema se, ad esempio, si configura SharePoint Server come applicazione partner anche se non è installato SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="ef2ac-115">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>

<span data-ttu-id="ef2ac-116">Quando si esegue lo script potrebbe essere visualizzato un messaggio di errore simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ef2ac-116">When you run this script you might receive an error message similar to the following:</span></span>

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

<span data-ttu-id="ef2ac-p105">Questo messaggio di errore indica in genere uno di due problemi: 1) uno degli URL specificati nello script non è valido (ovvero uno degli URL dei metadati non è corretto) oppure 2) non è possibile contattare uno degli URL dei metadati. In questi casi, verificare che gli URL siano corretti e accessibili, quindi rieseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="ef2ac-p105">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted. If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>

<span data-ttu-id="ef2ac-119">Dopo aver creato l'applicazione partner per Lync Server 2013, è necessario configurare Lync Server come applicazione partner per Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="ef2ac-119">After creating the partner application for Lync Server 2013 you must then configure Lync Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="ef2ac-120">È possibile configurare le applicazioni partner per Exchange 2013 eseguendo lo script Configure-EnterprisePartnerApplication.ps1; è sufficiente specificare l'URL dei metadati per Lync Server e indicare che Lync Server è la nuova applicazione partner.</span><span class="sxs-lookup"><span data-stu-id="ef2ac-120">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Lync Server and indicate that Lync Server is the new partner application.</span></span>

<span data-ttu-id="ef2ac-121">Per configurare Lync Server come applicazione partner per Exchange, aprire Exchange Management Shell ed eseguire un comando simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="ef2ac-121">To configure Lync Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

</div>

<span> </span>

</div>

</div>

</div>

