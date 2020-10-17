---
title: 'Lync Server 2013: visualizzare le informazioni sulle regole di aggiornamento dei dispositivi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79fef5d58116da6b8cbc07ce2b16f3dd4f6b28ac
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506383"
---
# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="42134-102">Visualizzare informazioni sulle regole di aggiornamento dei dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42134-102">View information about Device Update rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42134-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="42134-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="42134-104">Visualizzare i dettagli sulle regole di aggiornamento dei dispositivi che sono già state importate, tra cui il tipo, il modello e la marca dei dispositivi a cui si applica l'aggiornamento; versione e tipo di aggiornamento; e le impostazioni locali e il pool per l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="42134-104">View details about device update rules that have already been imported, including the type, model, and brand of devices the update applies to; version and type of update; and locale and pool for the update.</span></span> <span data-ttu-id="42134-105">Le informazioni sono disponibili per tutte le regole di aggiornamento dei dispositivi importate, ovvero quelle che sono in attesa di approvazione, distribuite (approvate), richiamate (ripristinate) e quelle che si è deciso di non utilizzare (reset).</span><span class="sxs-lookup"><span data-stu-id="42134-105">Information is available for all imported device update rules—those that are pending approval, deployed (approved), recalled (restored), and those you’ve decided not to use (reset).</span></span> <span data-ttu-id="42134-106">Accedere a queste informazioni dal pannello di controllo di Lync Server o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42134-106">Access this information from either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42134-107">Per informazioni dettagliate sull'importazione, l'approvazione, la reimpostazione, il ripristino e la rimozione di regole, vedere gli argomenti elencati in informazioni sulle <A href="lync-server-2013-device-update-rules.md">regole di aggiornamento dei dispositivi in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="42134-107">For details about how to import, approve, reset, restore, and remove rules, see the topics listed at <A href="lync-server-2013-device-update-rules.md">Device Update rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="42134-108">Per visualizzare le regole di aggiornamento dei dispositivi tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="42134-108">To view device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="42134-109">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="42134-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="42134-110">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42134-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="42134-111">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="42134-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="42134-112">Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento **Aggiorna dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="42134-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span> <span data-ttu-id="42134-113">Le regole importate sono elencate nella pagina **aggiornamento dispositivi** .</span><span class="sxs-lookup"><span data-stu-id="42134-113">Imported rules are listed on the **Device Update** page.</span></span>

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="42134-114">Visualizzazione delle regole di aggiornamento dei dispositivi tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="42134-114">Viewing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="42134-115">Informazioni dettagliate su tutte le regole di aggiornamento dei dispositivi possono essere visualizzate anche utilizzando Windows PowerShell e il cmdlet **Get-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="42134-115">Detailed information about all your device update rules can also be viewed by using Windows PowerShell and the **Get-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="42134-116">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42134-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42134-117">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="42134-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a><span data-ttu-id="42134-118">Per visualizzare tutte le regole di aggiornamento dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="42134-118">To view all your device update rules</span></span>

  - <span data-ttu-id="42134-119">Il comando seguente restituisce informazioni su tutte le regole di aggiornamento dei dispositivi configurate per l'utilizzo nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="42134-119">The following command returns information about all the device updates rules configured for use in your organization:</span></span>
    
        Get-CsDeviceUpdateRule
    
    <span data-ttu-id="42134-120">Il comando restituisce informazioni simili alle seguenti per ogni regola di aggiornamento del dispositivo:</span><span class="sxs-lookup"><span data-stu-id="42134-120">The command returns information similar to the following for each of your device update rules:</span></span>
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

</div>

<div>

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a><span data-ttu-id="42134-121">Per visualizzare tutte le regole di aggiornamento dei dispositivi in uno specifico server Web</span><span class="sxs-lookup"><span data-stu-id="42134-121">To view all the device update rules on a specific web server</span></span>

  - <span data-ttu-id="42134-122">Per visualizzare le regole di aggiornamento dei dispositivi in un computer specifico, utilizzare il parametro Filter seguito dall'identità del server e dal carattere jolly ( \* ).</span><span class="sxs-lookup"><span data-stu-id="42134-122">To view the device update rules on a specific computer, use the Filter parameter followed by the server Identity and the wildcard character (\*).</span></span> <span data-ttu-id="42134-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="42134-123">For example:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

<span data-ttu-id="42134-124">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="42134-124">For details, see the Help topic for the [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

