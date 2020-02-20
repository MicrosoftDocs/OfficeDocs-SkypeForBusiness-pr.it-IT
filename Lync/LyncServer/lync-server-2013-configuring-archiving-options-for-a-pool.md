---
title: 'Lync Server 2013: configurazione delle opzioni di archiviazione per un pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a pool
ms:assetid: b7cb0fd8-3d31-4858-a75c-c66a7742556e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205200(v=OCS.15)
ms:contentKeyID: 48185230
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f59ad3c768db0ea133337b747c073ee2e0c56b1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-pool-in-lync-server-2013"></a><span data-ttu-id="ae726-102">Configurazione delle opzioni di archiviazione per un pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae726-102">Configuring Archiving options for a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae726-103">_**Ultimo argomento modificato:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="ae726-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="ae726-p101">È possibile specificare le opzioni di archiviazione da applicare a pool specifici creando e configurando le opzioni in una configurazione di archiviazione per ognuno di tali pool. La configurazione di un pool ha la priorità sulla configurazione globale e sulla configurazione del sito, ma solo per il pool specificato nella relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="ae726-p101">You can specify Archiving options to be applied to specific pools by creating and configuring options in an Archiving configuration for each of those pools. A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>

<span data-ttu-id="ae726-106">Per informazioni dettagliate sul funzionamento delle configurazioni di archiviazione, inclusa la gerarchia per le configurazioni globali, del sito e del pool, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="ae726-106">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ae726-107">Specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ae726-107">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="ae726-108">Per ulteriori informazioni, vedere <A href="lync-server-2013-configuring-archiving-options.md">configurazione delle opzioni di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ae726-108">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-pool-level"></a><span data-ttu-id="ae726-109">Per configurare le opzioni di archiviazione a livello di pool</span><span class="sxs-lookup"><span data-stu-id="ae726-109">To configure archiving options at the pool level</span></span>

1.  <span data-ttu-id="ae726-110">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="ae726-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ae726-111">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ae726-111">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="ae726-112">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server 2013, vedere [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ae726-112">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ae726-113">Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="ae726-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="ae726-114">Nella pagina **Configurazione archiviazione** fare clic su **Nuovo** e quindi su **Configurazione pool**.</span><span class="sxs-lookup"><span data-stu-id="ae726-114">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>

5.  <span data-ttu-id="ae726-115">In **Seleziona un servizio** selezionare il pool da configurare per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ae726-115">In **Select a Service**, select the pool to be configured for archiving.</span></span>

6.  <span data-ttu-id="ae726-116">In **Nuova impostazione di archiviazione** selezionare una delle opzioni di archiviazione seguenti nell'elenco a discesa **Impostazione di archiviazione**:</span><span class="sxs-lookup"><span data-stu-id="ae726-116">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="ae726-117">**Disabilita archiviazione**</span><span class="sxs-lookup"><span data-stu-id="ae726-117">**Disable archiving**</span></span>
    
      - <span data-ttu-id="ae726-118">**Archivia sessioni di messaggistica istantanea**</span><span class="sxs-lookup"><span data-stu-id="ae726-118">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="ae726-119">**Archivia sessioni di messaggistica istantanea e Web Conferencing**</span><span class="sxs-lookup"><span data-stu-id="ae726-119">**Archive IM and web conferencing sessions**</span></span>

7.  <span data-ttu-id="ae726-120">Sempre nella pagina **Nuova impostazione di archiviazione** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ae726-120">Also in **New Archiving Setting** page, do the following:</span></span>
    
      - <span data-ttu-id="ae726-121">Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca sessioni di messaggistica istantanea o Web Conferencing se l'archiviazione non riesce**.</span><span class="sxs-lookup"><span data-stu-id="ae726-121">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="ae726-122">Per utilizzare Microsoft Exchange Server per archiviare i dati di archiviazione, fare clic sulla casella di controllo **integrazione di Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="ae726-122">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="ae726-123">Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ae726-123">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="ae726-124">Per specificare l'eliminazione dopo un numero specifico di giorni, fare clic su **Elimina dati di archiviazione esportati e archiviati dopo durata massima (giorni)** e quindi specificare il numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="ae726-124">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="ae726-125">Per limitare l'eliminazione ai dati di archiviazione esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.</span><span class="sxs-lookup"><span data-stu-id="ae726-125">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="ae726-126">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="ae726-126">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

