---
title: 'Lync Server 2013: visualizzare lo stato dei servizi in esecuzione in un computer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View the status of services running on a computer
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48185804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2745263bc4a179c9d99bf525aebe72b0cf299e9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a><span data-ttu-id="15f11-102">Visualizzare lo stato dei servizi in esecuzione in un computer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15f11-102">View the status of services running on a computer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15f11-103">_**Ultimo argomento modificato:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="15f11-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="15f11-104">È possibile utilizzare il pannello di controllo di Lync Server 2013 per visualizzare tutti i servizi in esecuzione in un computer specifico nella topologia di Lync Server e visualizzare lo stato di ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="15f11-104">You can use Lync Server 2013 Control Panel to view all the services that are running on a specific computer in your Lync Server topology and see the status of each service.</span></span>

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="15f11-105">Per visualizzare lo stato dei servizi in esecuzione in un computer</span><span class="sxs-lookup"><span data-stu-id="15f11-105">To view the status of services running on a computer</span></span>

1.  <span data-ttu-id="15f11-106">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="15f11-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="15f11-107">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="15f11-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="15f11-108">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="15f11-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="15f11-109">Sulla barra di spostamento sinistra fare clic su **Topologia**.</span><span class="sxs-lookup"><span data-stu-id="15f11-109">In the left navigation bar, click **Topology**.</span></span>

4.  <span data-ttu-id="15f11-110">Nella pagina **Stato** ordinare l'elenco oppure effettuare una ricerca per trovare il computer desiderato e fare clic sul nome del computer.</span><span class="sxs-lookup"><span data-stu-id="15f11-110">On the **Status** page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>

5.  <span data-ttu-id="15f11-111">Effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15f11-111">Do any of the following:</span></span>
    
      - <span data-ttu-id="15f11-112">Per visualizzare lo stato più recente dei servizi in esecuzione sul computer, fare clic su **Ottieni stato servizio**.</span><span class="sxs-lookup"><span data-stu-id="15f11-112">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    
      - <span data-ttu-id="15f11-113">Per visualizzare un elenco di servizi specifici in esecuzione sul computer e lo stato di ogni servizio, fare clic su **Proprietà** e quindi su **Chiudi** per tornare all'elenco.</span><span class="sxs-lookup"><span data-stu-id="15f11-113">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="15f11-114">Visualizzazione dello stato del servizio tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="15f11-114">Viewing Service Status by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="15f11-115">È inoltre possibile visualizzare lo stato del servizio utilizzando Windows PowerShell e il cmdlet **Get-CsWindowsService** .</span><span class="sxs-lookup"><span data-stu-id="15f11-115">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="15f11-116">È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15f11-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="15f11-117">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="15f11-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-service-status"></a><span data-ttu-id="15f11-118">Per visualizzare lo stato del servizio</span><span class="sxs-lookup"><span data-stu-id="15f11-118">To view service status</span></span>

  - <span data-ttu-id="15f11-119">Per visualizzare lo stato del servizio in un computer, digitare un comando simile al seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="15f11-119">To view service status on a computer, type a command similar to the following in the Lync Server Management Shell and then press Enter:</span></span>
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    <span data-ttu-id="15f11-120">Il comando restituisce informazioni simili a quelle riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="15f11-120">This command returns information similar to the following:</span></span>
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

</div>

<span data-ttu-id="15f11-121">Per informazioni dettagliate, vedere [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span><span class="sxs-lookup"><span data-stu-id="15f11-121">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="15f11-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15f11-122">See Also</span></span>


[<span data-ttu-id="15f11-123">Gestione di dispositivi, telefoni e applicazioni client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15f11-123">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

