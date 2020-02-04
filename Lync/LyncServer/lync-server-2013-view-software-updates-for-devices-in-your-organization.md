---
title: "Lync Server 2013: visualizzare gli aggiornamenti software per i dispositivi dell'organizzazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9a969aac4559f02ee7d05f36bece84e40f65aca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a><span data-ttu-id="2d30f-102">Visualizzare gli aggiornamenti software per i dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d30f-102">View software updates for devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d30f-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2d30f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2d30f-104">Con Lync Server 2013 si usa servizio Web Update per visualizzare e gestire gli aggiornamenti software per i dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2d30f-104">With Lync Server 2013, you use Device Update Web service to view and manage software updates for your organization’s devices.</span></span> <span data-ttu-id="2d30f-105">Questi aggiornamenti sono disponibili nei file CAB (Cabinet) dal sito Web del supporto tecnico Microsoft [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="2d30f-105">These updates are available in .cab (cabinet) files from the Microsoft Support website at [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091).</span></span> <span data-ttu-id="2d30f-106">Dopo aver scaricato il file CAB, eseguire il cmdlet **Import-CSDeviceUpdate** per importare le regole di aggiornamento dei dispositivi dal file CAB.</span><span class="sxs-lookup"><span data-stu-id="2d30f-106">After you download the .cab file, run the **Import-CSDeviceUpdate** cmdlet to import the device update rules from the .cab file.</span></span> <span data-ttu-id="2d30f-107">Per informazioni dettagliate sul cmdlet **Import-CSDeviceUpdate** , vedere [Import-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2d30f-107">For details about the **Import-CSDeviceUpdate** cmdlet, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="2d30f-108">Prima di distribuire un nuovo aggiornamento all'organizzazione, verificare che funzioni correttamente in un dispositivo di test.</span><span class="sxs-lookup"><span data-stu-id="2d30f-108">Before deploying a new update to your organization, verify that it functions correctly on a test device.</span></span>



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a><span data-ttu-id="2d30f-109">Per visualizzare gli aggiornamenti software per i dispositivi UC</span><span class="sxs-lookup"><span data-stu-id="2d30f-109">To view software updates for UC devices</span></span>

1.  <span data-ttu-id="2d30f-110">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="2d30f-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2d30f-111">Dal sito Web del supporto tecnico [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)Microsoft, scaricare il file CAB in una posizione in un computer Lync Server 2013, ad esempio C:\\Updates\\UCUpdates. cab.</span><span class="sxs-lookup"><span data-stu-id="2d30f-111">From the Microsoft Support website at [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091), download the .cab file to a location on a Lync Server 2013 computer (for example, C:\\Updates\\UCUpdates.cab).</span></span>

3.  <span data-ttu-id="2d30f-112">Importare le regole di aggiornamento del dispositivo dal file\\C\\: Updates UCUpdates. cab eseguendo uno dei cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d30f-112">Import the device update rules from the C:\\Updates\\UCUpdates.cab file by running one of the following cmdlets:</span></span>
    
      - <span data-ttu-id="2d30f-113">Se il file CAB si trova nello stesso computer di quello in cui è in esecuzione il servizio da aggiornare (servizio: Redmond-websvc-2), eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="2d30f-113">If the .cab file is located on the same computer as the one running the service to be updated (service:Redmond-websvc-2), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - <span data-ttu-id="2d30f-114">Se il file CAB si trova in un computer diverso da quello in cui è in esecuzione il servizio da aggiornare (servizio: Redmond-websvc-3), eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="2d30f-114">If the .cab file is located on a different computer than the one running the service to be updated (service:Redmond-websvc-3), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  <span data-ttu-id="2d30f-115">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2d30f-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2d30f-116">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2d30f-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

5.  <span data-ttu-id="2d30f-117">Sulla barra di spostamento sinistra fare clic su **client**e quindi su **aggiornamento dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="2d30f-117">In the left navigation bar, click **Clients**, and then click **Device Update**.</span></span>

6.  <span data-ttu-id="2d30f-118">Nella pagina **aggiornamento dispositivi** fare clic su un aggiornamento nell'elenco e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d30f-118">On the **Device Update** page, click an update in the list, and then do one of the following:</span></span>
    
      - <span data-ttu-id="2d30f-119">**Annullare un aggiornamento in sospeso.**</span><span class="sxs-lookup"><span data-stu-id="2d30f-119">**Cancel a pending update.**</span></span> <span data-ttu-id="2d30f-120">Per impedire la distribuzione dell'aggiornamento selezionato nei dispositivi dell'organizzazione, fare clic sul menu **azione** e quindi su **Annulla aggiornamenti in sospeso**.</span><span class="sxs-lookup"><span data-stu-id="2d30f-120">To prevent the selected update from being deployed to your organization’s devices, click the **Action** menu, and then click **Cancel pending updates**.</span></span>
    
      - <span data-ttu-id="2d30f-121">**Approvare un aggiornamento.**</span><span class="sxs-lookup"><span data-stu-id="2d30f-121">**Approve an update.**</span></span> <span data-ttu-id="2d30f-122">Per consentire la distribuzione dell'aggiornamento selezionato nei dispositivi dell'organizzazione, fare clic sul menu **azione** e quindi su **approva**.</span><span class="sxs-lookup"><span data-stu-id="2d30f-122">To allow the selected update to be deployed to your organization’s devices, click the **Action** menu, and then click **Approve**.</span></span>
    
      - <span data-ttu-id="2d30f-123">**Ripristinare un aggiornamento.**</span><span class="sxs-lookup"><span data-stu-id="2d30f-123">**Restore an update.**</span></span> <span data-ttu-id="2d30f-124">Per consentire la distribuzione di un aggiornamento approvato in precedenza nei dispositivi dell'organizzazione, fare clic sul menu **azione** e quindi su **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="2d30f-124">To allow a previously approved update to be deployed to your organization’s devices, click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2d30f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d30f-125">See Also</span></span>


[<span data-ttu-id="2d30f-126">Gestione di dispositivi, telefoni e applicazioni client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d30f-126">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

