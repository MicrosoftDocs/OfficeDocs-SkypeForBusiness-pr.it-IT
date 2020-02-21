---
title: 'Lync Server 2013: abilitare il controllo di ammissione di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call admission control
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398642(v=OCS.15)
ms:contentKeyID: 48184650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc2b31e399ba43f9e6b02ea66466da74e39d63a8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="29133-102">Abilitare il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29133-102">Enable call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29133-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="29133-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="29133-104">Dopo aver configurato le impostazioni di rete per la distribuzione del servizio Controllo di ammissione di chiamata, è necessario abilitare il servizio per rendere effettivi i criteri relativi alla larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="29133-104">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>

<span data-ttu-id="29133-105">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="29133-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="29133-106">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="29133-106">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [<span data-ttu-id="29133-107">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="29133-107">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [<span data-ttu-id="29133-108">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="29133-108">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a><span data-ttu-id="29133-109">Per abilitare il servizio Controllo di ammissione di chiamata tramite Management Shell</span><span class="sxs-lookup"><span data-stu-id="29133-109">To enable call admission control by using Management Shell</span></span>

1.  <span data-ttu-id="29133-110">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="29133-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="29133-p101">Eseguire il cmdlet Set-CsNetworkConfiguration per abilitare il servizio Controllo di ammissione di chiamata nella rete. Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="29133-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    <span data-ttu-id="29133-113">Se si desidera disabilitare il servizio Controllo di ammissione di chiamata nella rete, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="29133-113">If you want to disable CAC in your network, run the following:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a><span data-ttu-id="29133-114">Per abilitare il servizio Controllo di ammissione di chiamata tramite il Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="29133-114">To enable call admission control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="29133-115">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29133-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="29133-116">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="29133-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="29133-117">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="29133-117">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="29133-118">Fare clic sul pulsante di spostamento **Globale**.</span><span class="sxs-lookup"><span data-stu-id="29133-118">Click the **Global** navigation button.</span></span>

4.  <span data-ttu-id="29133-119">Fare clic su **Globale** nell'elenco e quindi scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="29133-119">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="29133-120">Nella pagina **Modifica impostazioni globali** selezionare la casella di controllo **Abilita il controllo di ammissione di chiamata**.</span><span class="sxs-lookup"><span data-stu-id="29133-120">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="29133-121">Se si desidera disabilitare il servizio Controllo di ammissione di chiamata in tutta la distribuzione, deselezionare questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="29133-121">If you want to disable call admission control throughout your deployment, clear this check box.</span></span>

    
    </div>

6.  <span data-ttu-id="29133-122">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="29133-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

