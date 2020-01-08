---
title: 'Lync Server 2013: configurazione delle opzioni di archiviazione per un pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options for a pool
ms:assetid: b7cb0fd8-3d31-4858-a75c-c66a7742556e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205200(v=OCS.15)
ms:contentKeyID: 48185230
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae5547320a9af0f11870ad0dc92ba03e40d8af4f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-pool-in-lync-server-2013"></a><span data-ttu-id="954e5-102">Configurazione delle opzioni di archiviazione per un pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="954e5-102">Configuring Archiving options for a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="954e5-103">_**Argomento Ultima modifica:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="954e5-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="954e5-104">È possibile specificare le opzioni di archiviazione da applicare a pool specifici creando e configurando le opzioni in una configurazione di archiviazione per ognuno di questi pool.</span><span class="sxs-lookup"><span data-stu-id="954e5-104">You can specify Archiving options to be applied to specific pools by creating and configuring options in an Archiving configuration for each of those pools.</span></span> <span data-ttu-id="954e5-105">La configurazione del pool sostituisce la configurazione globale e la configurazione del sito, ma solo per il pool specificato nella configurazione del pool.</span><span class="sxs-lookup"><span data-stu-id="954e5-105">A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>

<span data-ttu-id="954e5-106">Per informazioni dettagliate sul funzionamento delle configurazioni di archiviazione, ad esempio la gerarchia per le configurazioni globali, del sito e del pool, vedere funzionamento dell' [archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, nella documentazione di distribuzione o nelle operazioni.</span><span class="sxs-lookup"><span data-stu-id="954e5-106">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="954e5-107">Devi specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="954e5-107">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="954e5-108">Per informazioni dettagliate, vedere <A href="lync-server-2013-configuring-archiving-options.md">configurazione delle opzioni di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="954e5-108">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-pool-level"></a><span data-ttu-id="954e5-109">Per configurare le opzioni di archiviazione a livello di pool</span><span class="sxs-lookup"><span data-stu-id="954e5-109">To configure archiving options at the pool level</span></span>

1.  <span data-ttu-id="954e5-110">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="954e5-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="954e5-111">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="954e5-111">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="954e5-112">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server 2013, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="954e5-112">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="954e5-113">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="954e5-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="954e5-114">Nella pagina **Configurazione archiviazione** fare clic su **nuovo**e quindi su **Configurazione pool**.</span><span class="sxs-lookup"><span data-stu-id="954e5-114">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>

5.  <span data-ttu-id="954e5-115">In **Seleziona un servizio**selezionare il pool da configurare per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="954e5-115">In **Select a Service**, select the pool to be configured for archiving.</span></span>

6.  <span data-ttu-id="954e5-116">In **nuova impostazione archiviazione**selezionare una delle opzioni di archiviazione seguenti nell'elenco a discesa **Impostazioni archiviazione** :</span><span class="sxs-lookup"><span data-stu-id="954e5-116">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="954e5-117">**Disabilita archiviazione**</span><span class="sxs-lookup"><span data-stu-id="954e5-117">**Disable archiving**</span></span>
    
      - <span data-ttu-id="954e5-118">**Archivia sessioni di messaggistica istantanea**</span><span class="sxs-lookup"><span data-stu-id="954e5-118">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="954e5-119">**Archivia sessioni di messaggistica istantanea e Web Conferencing**</span><span class="sxs-lookup"><span data-stu-id="954e5-119">**Archive IM and web conferencing sessions**</span></span>

7.  <span data-ttu-id="954e5-120">Anche nella pagina **nuova impostazione archiviazione** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="954e5-120">Also in **New Archiving Setting** page, do the following:</span></span>
    
      - <span data-ttu-id="954e5-121">Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca messaggistica istantanea o servizi di conferenza Web se l'archiviazione non riesce** .</span><span class="sxs-lookup"><span data-stu-id="954e5-121">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="954e5-122">Per usare Microsoft Exchange Server per archiviare i dati di archiviazione, fare clic sulla casella di controllo **integrazione di Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="954e5-122">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="954e5-123">Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita l'eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="954e5-123">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="954e5-124">Per specificare l'eliminazione dopo un determinato numero di giorni, fare clic su **Elimina dati di archiviazione esportati e archivia dati archiviati dopo la durata massima (giorni)** e quindi specificare il numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="954e5-124">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="954e5-125">Per limitare l'eliminazione all'archiviazione dei dati esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.</span><span class="sxs-lookup"><span data-stu-id="954e5-125">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="954e5-126">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="954e5-126">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

