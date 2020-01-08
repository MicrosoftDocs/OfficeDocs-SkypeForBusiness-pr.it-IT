---
title: 'Lync Server 2013: abilitazione del monitoraggio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2b13028390328e93a9e90636962dedea8ea8ec9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-monitoring-in-lync-server-2013"></a><span data-ttu-id="9cd8f-102">Abilitazione del monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cd8f-102">Enabling monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cd8f-103">_**Argomento Ultima modifica:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="9cd8f-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="9cd8f-104">Anche se gli agenti di raccolta dati unificati vengono installati e attivati automaticamente in ogni server front-end, ciò non significa che si inizierà automaticamente a raccogliere i dati di monitoraggio nel momento in cui si completa l'installazione di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9cd8f-104">Although the unified data collection agents are automatically installed and activated on each Front End server, that does not mean that you will automatically begin to collect monitoring data the moment you finish installing Microsoft Lync Server 2013.</span></span> <span data-ttu-id="9cd8f-105">È invece necessario eseguire due operazioni: è necessario associare i server front-end/pool Front-end a un database di monitoraggio ed è necessario abilitare il monitoraggio della registrazione dei dettagli delle chiamate (CDR) e/o la qualità dell'esperienza (QoE) nell'ambito globale e/o nell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="9cd8f-105">Instead, you must do two things: you must associate your Front End servers/Front End pools with a monitoring database, and you must enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global scope and/or the site scope.</span></span>

<span data-ttu-id="9cd8f-106">Per istruzioni dettagliate sull'associazione di server front-end o pool Front-end a un database di monitoraggio, vedere l'argomento [associazione di un archivio di monitoraggio con un pool Front-end in Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) nella Guida alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9cd8f-106">For step-by-step instructions on associating Front End servers or Front End pools with a monitoring database, see the topic [Associating a monitoring store with a Front End pool in Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) in the Deployment guide.</span></span> <span data-ttu-id="9cd8f-107">Dopo aver effettuato queste associazioni e dopo la pubblicazione della nuova topologia di Lync Server, non sarà ancora possibile raccogliere i dati di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="9cd8f-107">After these associations have been made, and after your new Lync Server topology has been published, you will still not be able to collect monitoring data.</span></span> <span data-ttu-id="9cd8f-108">Questo perché, per impostazione predefinita, sia la raccolta di dati CDR che QoE è disabilitata durante l'installazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9cd8f-108">That's because, by default, both CDR and QoE data collection is disabled when you install Lync Server 2013.</span></span>

<span data-ttu-id="9cd8f-109">Per avviare la raccolta dei dati, è necessario abilitare il monitoraggio CDR e/o QoE.</span><span class="sxs-lookup"><span data-stu-id="9cd8f-109">In order to begin data collection you will need to enable CDR and/or QoE monitoring.</span></span> <span data-ttu-id="9cd8f-110">(Si noti che non è necessario abilitare il monitoraggio CDR e QoE, se si preferisce, è possibile abilitare un tipo di monitoraggio lasciando l'altro tipo disabilitato). Per abilitare il monitoraggio CDR nell'ambito globale, eseguire il comando seguente dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="9cd8f-110">(Note that you do not have to enable both CDR and QoE monitoring; if you prefer, you can enable one type of monitoring while leaving the other type disabled.) To enable CDR monitoring at the global scope run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="9cd8f-111">In alternativa, è possibile abilitare il monitoraggio CDR dall'interno del pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9cd8f-111">Alternatively, you can enable CDR monitoring from within the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="9cd8f-112">Nel pannello di controllo di Lync Server completare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="9cd8f-112">From within the Lync Server Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="9cd8f-113">Fare clic su **monitoraggio**.</span><span class="sxs-lookup"><span data-stu-id="9cd8f-113">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="9cd8f-114">Nella scheda **registrazione dettagli chiamata** fare doppio clic sull'impostazione **globale** .</span><span class="sxs-lookup"><span data-stu-id="9cd8f-114">On the **Call Detail Recording** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="9cd8f-115">Nel riquadro **Impostazioni registrazione dettagli chiamata (CDR)** selezionare **Abilita monitoraggio di CDRS** e quindi fare clic su **commit**.</span><span class="sxs-lookup"><span data-stu-id="9cd8f-115">In the **Edit Call Detail Recording (CDR) Setting** pane, select **Enable monitoring of CDRs** and then click **Commit**.</span></span>

<span data-ttu-id="9cd8f-116">Per abilitare il monitoraggio QoE nell'ambito globale, eseguire questo comando dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="9cd8f-116">To enable QoE monitoring at the global scope, run this command from within the Lync Server Management Shell:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

<span data-ttu-id="9cd8f-117">Se si preferisce, è anche possibile abilitare il monitoraggio QoE dall'interno del pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9cd8f-117">If you prefer, you can also enable QoE monitoring from within the Lync Server Control Panel.</span></span> <span data-ttu-id="9cd8f-118">Nel pannello di controllo completare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="9cd8f-118">From within the Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="9cd8f-119">Fare clic su **monitoraggio**.</span><span class="sxs-lookup"><span data-stu-id="9cd8f-119">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="9cd8f-120">Nella scheda **qualità di dati esperienza** fare doppio clic sull'impostazione **globale** .</span><span class="sxs-lookup"><span data-stu-id="9cd8f-120">On the **Quality of Experience Data** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="9cd8f-121">Nel riquadro **Impostazioni modifica qualità dell'esperienza (QoE)** selezionare Abilita il **monitoraggio dei dati QoE** e quindi fare clic su **commit**.</span><span class="sxs-lookup"><span data-stu-id="9cd8f-121">In the **Edit Quality of Experience (QoE) Setting** pane, select **Enable monitoring of QoE data** and then click **Commit**.</span></span>

<span data-ttu-id="9cd8f-122">Come indicato, gli esempi precedenti consentono il monitoraggio nell'ambito globale; in altre altre, abilitano il monitoraggio CDR e QoE in tutta l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9cd8f-122">As noted, the preceding examples enable monitoring at the global scope; that is, they enable CDR and QoE monitoring throughout your organization.</span></span> <span data-ttu-id="9cd8f-123">In alternativa, è possibile creare impostazioni di configurazione CDR e QoE separate nell'ambito del sito e quindi abilitare o disabilitare il monitoraggio in modo selettivo per ogni sito.</span><span class="sxs-lookup"><span data-stu-id="9cd8f-123">Alternatively, you can create separate CDR and QoE configuration settings at the site scope, and then selectively enable or disable monitoring for each site.</span></span> <span data-ttu-id="9cd8f-124">Ad esempio, è possibile abilitare il monitoraggio CDR per il sito Redmond, ma disabilitare il monitoraggio CDR per il sito di Dublino.</span><span class="sxs-lookup"><span data-stu-id="9cd8f-124">For example, you could enable CDR monitoring for your Redmond site, yet disable CDR monitoring for your Dublin site.</span></span> <span data-ttu-id="9cd8f-125">Per altre informazioni sulla gestione delle impostazioni di configurazione del monitoraggio, vedere l'argomento Guida alla distribuzione [configurazione della registrazione dei dettagli delle chiamate e della qualità delle impostazioni dell'esperienza in Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span><span class="sxs-lookup"><span data-stu-id="9cd8f-125">For more information on managing your monitoring configuration settings, see the Deployment guide topic [Configuring call detail recording and Quality of Experience settings in Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

