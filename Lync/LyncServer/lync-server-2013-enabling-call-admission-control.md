---
title: 'Lync Server 2013: abilitazione del controllo di ammissione alle chiamate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20cd0f7792f8db2cf1b2d817bfe79ed6d6b16fce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="df154-102">Abilitazione del controllo di ammissione alle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df154-102">Enabling call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df154-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="df154-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="df154-104">Il servizio Controllo di ammissione di chiamata è una rete di aree, siti e subnet che consentono di applicare restrizioni alle trasmissioni audio e video in base alla larghezza di banda disponibile.</span><span class="sxs-lookup"><span data-stu-id="df154-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="df154-105">Dopo aver configurato la rete CAC, è necessario abilitare CAC per applicare le limitazioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="df154-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="df154-106">Per eseguire questa operazione, è possibile usare il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="df154-106">You can use Lync Server Control Panel to do this.</span></span>

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a><span data-ttu-id="df154-107">Per abilitare CAC dal pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="df154-107">To enable CAC from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="df154-108">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="df154-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="df154-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="df154-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="df154-110">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="df154-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="df154-111">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **globale**.</span><span class="sxs-lookup"><span data-stu-id="df154-111">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="df154-112">Nella pagina **globale** fare clic sulla configurazione **globale** .</span><span class="sxs-lookup"><span data-stu-id="df154-112">On the **Global** page, click the **Global** configuration.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="df154-113">Solo una rete può essere configurata per qualsiasi distribuzione di Microsoft Lync Server 2013, quindi non ci saranno mai più configurazioni di rete nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="df154-113">Only one network can be configured for any Microsoft Lync Server 2013 deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="df154-114">Non è possibile rinominare la configurazione globale.</span><span class="sxs-lookup"><span data-stu-id="df154-114">You cannot rename the Global configuration.</span></span>

    
    </div>

5.  <span data-ttu-id="df154-115">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="df154-115">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="df154-116">Nella pagina **Modifica impostazioni globali** selezionare la casella di **controllo Abilita l'ammissione alle chiamate** e quindi fare clic su **conferma**.</span><span class="sxs-lookup"><span data-stu-id="df154-116">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="df154-117">Quando si fa clic su **commit**, si esegue un test della configurazione.</span><span class="sxs-lookup"><span data-stu-id="df154-117">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="df154-118">La finestra di dialogo **Modifica impostazioni globali** viene chiusa, tornando alla pagina **globale** .</span><span class="sxs-lookup"><span data-stu-id="df154-118">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="df154-119">Verrà visualizzato un messaggio di avviso in caso di errori o incongruenze individuati nella configurazione di rete che ne impediscono il corretto funzionamento, ad esempio se ogni area geografica non è connessa a tutte le altre aree geografiche tramite una route interregion.</span><span class="sxs-lookup"><span data-stu-id="df154-119">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="df154-120">Se si apportano modifiche alla configurazione di rete, è possibile eseguire di nuovo il controllo di convalida aprendo la configurazione globale e facendo clic su **commit**.</span><span class="sxs-lookup"><span data-stu-id="df154-120">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="df154-121">Non è necessario disabilitare prima CAC: tenere selezionata la casella di controllo e fare clic su **conferma**.</span><span class="sxs-lookup"><span data-stu-id="df154-121">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="df154-122">Puoi eseguire questa operazione in qualsiasi momento senza apportare modifiche alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="df154-122">You can do this at any time without making any configuration changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="df154-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df154-123">See Also</span></span>


[<span data-ttu-id="df154-124">Panoramica del controllo di ammissione alle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df154-124">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="df154-125">Pianificazione del servizio Controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df154-125">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="df154-126">Configurare il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df154-126">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="df154-127">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="df154-127">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[<span data-ttu-id="df154-128">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="df154-128">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[<span data-ttu-id="df154-129">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="df154-129">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

