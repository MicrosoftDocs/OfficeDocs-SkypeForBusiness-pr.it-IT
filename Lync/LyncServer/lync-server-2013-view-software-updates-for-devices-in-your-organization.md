---
title: "Lync Server 2013: visualizzare gli aggiornamenti software per i dispositivi nell'organizzazione"
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
ms.openlocfilehash: ce1940f92860d5ccd2d66c53a0a4da16cebada24
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a><span data-ttu-id="3e31d-102">Visualizzare gli aggiornamenti software per i dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e31d-102">View software updates for devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e31d-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3e31d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3e31d-104">Con Lync Server 2013, è possibile utilizzare il servizio Web aggiornamento dispositivi per visualizzare e gestire gli aggiornamenti software per i dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3e31d-104">With Lync Server 2013, you use Device Update Web service to view and manage software updates for your organization’s devices.</span></span> <span data-ttu-id="3e31d-105">Questi aggiornamenti sono disponibili nei file CAB (Cabinet) del sito Web del supporto tecnico Microsoft [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091)all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="3e31d-105">These updates are available in .cab (cabinet) files from the Microsoft Support website at [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091).</span></span> <span data-ttu-id="3e31d-106">Dopo aver scaricato il file CAB, eseguire il cmdlet **Import-CSDeviceUpdate** per importare le regole di aggiornamento dei dispositivi dal file CAB.</span><span class="sxs-lookup"><span data-stu-id="3e31d-106">After you download the .cab file, run the **Import-CSDeviceUpdate** cmdlet to import the device update rules from the .cab file.</span></span> <span data-ttu-id="3e31d-107">Per informazioni dettagliate sul cmdlet **Import-CSDeviceUpdate** , vedere [Import-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3e31d-107">For details about the **Import-CSDeviceUpdate** cmdlet, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="3e31d-108">Prima di distribuire un nuovo aggiornamento nell'organizzazione, verificarne il corretto funzionamento su un dispositivo di test.</span><span class="sxs-lookup"><span data-stu-id="3e31d-108">Before deploying a new update to your organization, verify that it functions correctly on a test device.</span></span>



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a><span data-ttu-id="3e31d-109">Per visualizzare gli aggiornamenti software per i dispositivi per comunicazioni unificate</span><span class="sxs-lookup"><span data-stu-id="3e31d-109">To view software updates for UC devices</span></span>

1.  <span data-ttu-id="3e31d-110">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3e31d-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3e31d-111">Nel [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091)sito Web del supporto tecnico Microsoft, scaricare il file CAB in un percorso su un computer Lync Server 2013, ad esempio C:\\Updates\\UCUpdates. cab.</span><span class="sxs-lookup"><span data-stu-id="3e31d-111">From the Microsoft Support website at [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091), download the .cab file to a location on a Lync Server 2013 computer (for example, C:\\Updates\\UCUpdates.cab).</span></span>

3.  <span data-ttu-id="3e31d-112">Importare le regole di aggiornamento dei dispositivi dal file\\ucupdates\\. cab C: Updates eseguendo uno dei cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e31d-112">Import the device update rules from the C:\\Updates\\UCUpdates.cab file by running one of the following cmdlets:</span></span>
    
      - <span data-ttu-id="3e31d-113">Se il file CAB si trova sullo stesso computer sul quale è in esecuzione il servizio da aggiornare (service:Redmond-websvc-2), eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="3e31d-113">If the .cab file is located on the same computer as the one running the service to be updated (service:Redmond-websvc-2), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - <span data-ttu-id="3e31d-114">Se il file CAB si trova su un computer diverso da quello sul quale è in esecuzione il servizio da aggiornare (service:Redmond-websvc-3), eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="3e31d-114">If the .cab file is located on a different computer than the one running the service to be updated (service:Redmond-websvc-3), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  <span data-ttu-id="3e31d-115">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e31d-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3e31d-116">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3e31d-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

5.  <span data-ttu-id="3e31d-117">Sulla barra di spostamento sinistra fare clic su **Client** e quindi su **Aggiornamento dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="3e31d-117">In the left navigation bar, click **Clients**, and then click **Device Update**.</span></span>

6.  <span data-ttu-id="3e31d-118">Nella pagina **Aggiornamento dispositivi** fare clic su un aggiornamento nell'elenco ed eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e31d-118">On the **Device Update** page, click an update in the list, and then do one of the following:</span></span>
    
      - <span data-ttu-id="3e31d-p103">**Annullare un aggiornamento in sospeso.** Per impedire che l'aggiornamento selezionato venga distribuito nei dispositivi dell'organizzazione, fare clic sul menu **Azione** e quindi su **Annulla aggiornamenti in sospeso**.</span><span class="sxs-lookup"><span data-stu-id="3e31d-p103">**Cancel a pending update.** To prevent the selected update from being deployed to your organization’s devices, click the **Action** menu, and then click **Cancel pending updates**.</span></span>
    
      - <span data-ttu-id="3e31d-p104">**Approvare un aggiornamento.** Per consentire la distribuzione dell'aggiornamento selezionato nei dispositivi dell'organizzazione, fare clic sul menu **Azione** e quindi su **Approva**.</span><span class="sxs-lookup"><span data-stu-id="3e31d-p104">**Approve an update.** To allow the selected update to be deployed to your organization’s devices, click the **Action** menu, and then click **Approve**.</span></span>
    
      - <span data-ttu-id="3e31d-p105">**Ripristinare un aggiornamento.** Per consentire la distribuzione di un aggiornamento approvato in precedenza nei dispositivi dell'organizzazione, fare clic sul menu **Azione** e quindi su **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="3e31d-p105">**Restore an update.** To allow a previously approved update to be deployed to your organization’s devices, click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3e31d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e31d-125">See Also</span></span>


[<span data-ttu-id="3e31d-126">Gestione di dispositivi, telefoni e applicazioni client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e31d-126">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

