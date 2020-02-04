---
title: 'Lync Server 2013: abilitare il controllo di ammissione alle chiamate'
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
ms.openlocfilehash: 1776cc173d7ddec50aae34e8316844d14f67b009
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="f07cb-102">Abilitare il controllo di ammissione alle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f07cb-102">Enable call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f07cb-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="f07cb-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="f07cb-104">Dopo aver configurato le impostazioni di rete per la distribuzione del controllo di ammissione alle chiamate, è necessario abilitare CAC per applicare i criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="f07cb-104">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>

<span data-ttu-id="f07cb-105">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="f07cb-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="f07cb-106">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="f07cb-106">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [<span data-ttu-id="f07cb-107">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="f07cb-107">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [<span data-ttu-id="f07cb-108">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="f07cb-108">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a><span data-ttu-id="f07cb-109">Per abilitare il controllo di ammissione di chiamata tramite Management Shell</span><span class="sxs-lookup"><span data-stu-id="f07cb-109">To enable call admission control by using Management Shell</span></span>

1.  <span data-ttu-id="f07cb-110">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f07cb-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f07cb-111">Eseguire il cmdlet Set-CsNetworkConfiguration per abilitare CAC nella rete.</span><span class="sxs-lookup"><span data-stu-id="f07cb-111">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network.</span></span> <span data-ttu-id="f07cb-112">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="f07cb-112">For example, run:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    <span data-ttu-id="f07cb-113">Se si vuole disabilitare CAC nella rete, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f07cb-113">If you want to disable CAC in your network, run the following:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a><span data-ttu-id="f07cb-114">Per abilitare il controllo di ammissione alle chiamate usando il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="f07cb-114">To enable call admission control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f07cb-115">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f07cb-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f07cb-116">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f07cb-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="f07cb-117">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="f07cb-117">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="f07cb-118">Fare clic sul pulsante di spostamento **globale** .</span><span class="sxs-lookup"><span data-stu-id="f07cb-118">Click the **Global** navigation button.</span></span>

4.  <span data-ttu-id="f07cb-119">Fare clic su **globale** nell'elenco e quindi selezionare **Mostra dettagli** dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="f07cb-119">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="f07cb-120">Nella pagina **Modifica impostazioni globali** selezionare la casella di **controllo Abilita l'ammissione alle chiamate** .</span><span class="sxs-lookup"><span data-stu-id="f07cb-120">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f07cb-121">Se si vuole disabilitare il controllo di ammissione delle chiamate durante la distribuzione, deselezionare questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="f07cb-121">If you want to disable call admission control throughout your deployment, clear this check box.</span></span>

    
    </div>

6.  <span data-ttu-id="f07cb-122">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f07cb-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

