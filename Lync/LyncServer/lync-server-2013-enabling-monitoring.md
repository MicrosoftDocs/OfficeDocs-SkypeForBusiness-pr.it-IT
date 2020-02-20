---
title: 'Lync Server 2013: attivazione del monitoraggio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f07ea86bfeb9bd13f8fb3c4f34d114af075e6150
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-monitoring-in-lync-server-2013"></a><span data-ttu-id="7eccf-102">Abilitazione del monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7eccf-102">Enabling monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7eccf-103">_**Ultimo argomento modificato:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="7eccf-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="7eccf-104">Anche se gli agenti di raccolta dati unificati vengono installati e attivati automaticamente su ogni Front End Server, ciò non significa che si inizierà automaticamente a raccogliere i dati di monitoraggio nel momento in cui si termina l'installazione di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7eccf-104">Although the unified data collection agents are automatically installed and activated on each Front End server, that does not mean that you will automatically begin to collect monitoring data the moment you finish installing Microsoft Lync Server 2013.</span></span> <span data-ttu-id="7eccf-105">Al contrario, è necessario eseguire due operazioni: associare Front End Server e pool Front End a un database di monitoraggio e abilitare il monitoraggio di registrazione dettagli chiamata e/o QoE nell'ambito globale e/o del sito.</span><span class="sxs-lookup"><span data-stu-id="7eccf-105">Instead, you must do two things: you must associate your Front End servers/Front End pools with a monitoring database, and you must enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global scope and/or the site scope.</span></span>

<span data-ttu-id="7eccf-106">Per istruzioni dettagliate sull'associazione di front end server o pool Front end a un database di monitoraggio, vedere l'argomento [associazione di un archivio di monitoraggio con un pool Front end in Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) nella Guida alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7eccf-106">For step-by-step instructions on associating Front End servers or Front End pools with a monitoring database, see the topic [Associating a monitoring store with a Front End pool in Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) in the Deployment guide.</span></span> <span data-ttu-id="7eccf-107">Dopo aver completato queste associazioni e dopo aver pubblicato la nuova topologia di Lync Server, non è ancora possibile raccogliere dati di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="7eccf-107">After these associations have been made, and after your new Lync Server topology has been published, you will still not be able to collect monitoring data.</span></span> <span data-ttu-id="7eccf-108">Ciò è dovuto al fatto che, per impostazione predefinita, sia la raccolta di dati CDR che QoE è disabilitata quando si installa Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7eccf-108">That's because, by default, both CDR and QoE data collection is disabled when you install Lync Server 2013.</span></span>

<span data-ttu-id="7eccf-109">Per iniziare la raccolta dei dati, è necessario abilitare il monitoraggio di registrazione dettagli chiamata e/o QoE.</span><span class="sxs-lookup"><span data-stu-id="7eccf-109">In order to begin data collection you will need to enable CDR and/or QoE monitoring.</span></span> <span data-ttu-id="7eccf-110">Tenere presente che non è necessario abilitare il monitoraggio di CDR e QoE, se si preferisce, è possibile abilitare un tipo di monitoraggio lasciando l'altro tipo disabilitato. Per abilitare il monitoraggio CDR nell'ambito globale, eseguire il comando riportato di seguito dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="7eccf-110">(Note that you do not have to enable both CDR and QoE monitoring; if you prefer, you can enable one type of monitoring while leaving the other type disabled.) To enable CDR monitoring at the global scope run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="7eccf-111">In alternativa, è possibile abilitare il monitoraggio di registrazione dettagli chiamata dall'interno del pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7eccf-111">Alternatively, you can enable CDR monitoring from within the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="7eccf-112">Nel pannello di controllo di Lync Server, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="7eccf-112">From within the Lync Server Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="7eccf-113">Fare clic su **Monitoraggio**.</span><span class="sxs-lookup"><span data-stu-id="7eccf-113">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="7eccf-114">Nella scheda **Registrazione dettagli chiamata** fare doppio clic sull'impostazione **Globale**.</span><span class="sxs-lookup"><span data-stu-id="7eccf-114">On the **Call Detail Recording** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="7eccf-115">Nel riquadro **Modifica impostazione di registrazione dettagli chiamata** selezionare **Abilita monitoraggio registrazioni dettagli chiamata** e fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="7eccf-115">In the **Edit Call Detail Recording (CDR) Setting** pane, select **Enable monitoring of CDRs** and then click **Commit**.</span></span>

<span data-ttu-id="7eccf-116">Per abilitare il monitoraggio QoE nell'ambito globale, eseguire questo comando dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="7eccf-116">To enable QoE monitoring at the global scope, run this command from within the Lync Server Management Shell:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

<span data-ttu-id="7eccf-117">Se si preferisce, è anche possibile abilitare il monitoraggio QoE dall'interno del pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7eccf-117">If you prefer, you can also enable QoE monitoring from within the Lync Server Control Panel.</span></span> <span data-ttu-id="7eccf-118">Dal Pannello di controllo, completare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="7eccf-118">From within the Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="7eccf-119">Fare clic su **Monitoraggio**.</span><span class="sxs-lookup"><span data-stu-id="7eccf-119">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="7eccf-120">Nella scheda **Dati QoE** fare doppio clic sull'impostazione **Globale**.</span><span class="sxs-lookup"><span data-stu-id="7eccf-120">On the **Quality of Experience Data** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="7eccf-121">Nel riquadro **Modifica impostazione QoE** selezionare **Abilita monitoraggio dei dati QoE** e fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="7eccf-121">In the **Edit Quality of Experience (QoE) Setting** pane, select **Enable monitoring of QoE data** and then click **Commit**.</span></span>

<span data-ttu-id="7eccf-122">Come si può notare, negli esempi precedenti il monitoraggio viene abilitato nell'ambito globale, ciò significa che il monitoraggio di registrazione dettagli chiamata e QoE viene abilitato per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7eccf-122">As noted, the preceding examples enable monitoring at the global scope; that is, they enable CDR and QoE monitoring throughout your organization.</span></span> <span data-ttu-id="7eccf-123">In alternativa, è possibile creare impostazioni di configurazione di registrazione dettagli chiamata e QoE nell'ambito del sito, quindi abilitare o disabilitare in modo selettivo per ogni sito.</span><span class="sxs-lookup"><span data-stu-id="7eccf-123">Alternatively, you can create separate CDR and QoE configuration settings at the site scope, and then selectively enable or disable monitoring for each site.</span></span> <span data-ttu-id="7eccf-124">Ad esempio, è possibile abilitare il monitoraggio di registrazione dettagli chiamata per il sito di Parigi, ma disabilitarlo per il sito di Milano.</span><span class="sxs-lookup"><span data-stu-id="7eccf-124">For example, you could enable CDR monitoring for your Redmond site, yet disable CDR monitoring for your Dublin site.</span></span> <span data-ttu-id="7eccf-125">Per ulteriori informazioni sulla gestione delle impostazioni di configurazione del monitoraggio, vedere l'argomento relativo alla distribuzione delle [impostazioni di registrazione dettagli chiamata e qualità delle esperienze in Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span><span class="sxs-lookup"><span data-stu-id="7eccf-125">For more information on managing your monitoring configuration settings, see the Deployment guide topic [Configuring call detail recording and Quality of Experience settings in Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

