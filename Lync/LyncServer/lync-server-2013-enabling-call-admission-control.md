---
title: 'Lync Server 2013: abilitazione del controllo di ammissione di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 857dce2203bf9713676113ba4fa0e8b6f4ec5a60
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="1cd29-102">Abilitazione del controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1cd29-102">Enabling call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1cd29-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1cd29-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1cd29-104">Il servizio Controllo di ammissione di chiamata è una rete di aree, siti e subnet che consentono di applicare restrizioni relative alle trasmissioni audio e video in base alla larghezza di banda disponibile.</span><span class="sxs-lookup"><span data-stu-id="1cd29-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="1cd29-105">Dopo avere configurato tale rete, è necessario abilitare il servizio per applicare le limitazioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="1cd29-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="1cd29-106">Per eseguire questa operazione, è possibile utilizzare il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1cd29-106">You can use Lync Server Control Panel to do this.</span></span>

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a><span data-ttu-id="1cd29-107">Per abilitare il servizio di controllo di ammissione da Lync Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="1cd29-107">To enable CAC from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1cd29-108">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="1cd29-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1cd29-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1cd29-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1cd29-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1cd29-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1cd29-111">Sulla barra di spostamento sinistra fare clic su  \*\*Configurazione di rete \*\* e quindi su  \*\*Globale \*\*.</span><span class="sxs-lookup"><span data-stu-id="1cd29-111">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="1cd29-112">Nella pagina  \*\*Globale \*\* fare clic sulla scheda della configurazione  \*\*Globale \*\*.</span><span class="sxs-lookup"><span data-stu-id="1cd29-112">On the **Global** page, click the **Global** configuration.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1cd29-113">Solo una rete può essere configurata per qualsiasi distribuzione di Microsoft Lync Server 2013, quindi non vi sarà mai più di una configurazione di rete nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="1cd29-113">Only one network can be configured for any Microsoft Lync Server 2013 deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="1cd29-114">Non è possibile rinominare la configurazione globale.</span><span class="sxs-lookup"><span data-stu-id="1cd29-114">You cannot rename the Global configuration.</span></span>

    
    </div>

5.  <span data-ttu-id="1cd29-115">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="1cd29-115">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="1cd29-116">Nella pagina **Modifica Impostazioni globali** selezionare la casella di controllo **Abilita il controllo di ammissione di chiamata** e quindi fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="1cd29-116">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="1cd29-p104">Quando si fa clic su **Commit**, si esegue un test della configurazione. La finestra di dialogo **Modifica Impostazioni globali** si chiude e si torna alla pagina **Globale**. Si riceverà un avviso se nella configurazione di rete vengono rilevati eventuali errori o incongruenze che ne impediscono il corretto funzionamento, ad esempio se non tutte le aree sono connesse a tutte le altre aree mediante una route tra aree.</span><span class="sxs-lookup"><span data-stu-id="1cd29-p104">When you click **Commit**, you run a test of the configuration. The **Edit Global Settings** dialog box closes, returning you to the **Global** page. You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="1cd29-p105">Se si apportano modifiche alla configurazione di rete, sarà possibile eseguire di nuovo la convalida aprendo la configurazione globale e facendo clic su **Commit**. Non è necessario disabilitare prima il controllo di ammissione di chiamata, perciò lasciare selezionata la casella di controllo e fare clic su **Commit**. È possibile procedere in questo modo in qualsiasi momento senza apportare modifiche alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="1cd29-p105">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**. You do not need to disable CAC first: leave the check box checked and click **Commit**. You can do this at any time without making any configuration changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1cd29-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cd29-123">See Also</span></span>


[<span data-ttu-id="1cd29-124">Panoramica del controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1cd29-124">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="1cd29-125">Pianificazione del controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1cd29-125">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="1cd29-126">Configurare il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1cd29-126">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="1cd29-127">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="1cd29-127">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[<span data-ttu-id="1cd29-128">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="1cd29-128">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[<span data-ttu-id="1cd29-129">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="1cd29-129">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

