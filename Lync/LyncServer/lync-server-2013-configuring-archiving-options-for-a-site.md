---
title: 'Lync Server 2013: configurazione delle opzioni di archiviazione per un sito'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14b0e29a2796c23c13a16bfb3e8a202a0a535aaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978064"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a><span data-ttu-id="da08f-102">Configurazione delle opzioni di archiviazione per un sito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da08f-102">Configuring Archiving options for a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da08f-103">_**Argomento Ultima modifica:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="da08f-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="da08f-104">È possibile specificare le opzioni di archiviazione da applicare a siti specifici creando e configurando le opzioni in una configurazione di archiviazione per ognuno di questi siti.</span><span class="sxs-lookup"><span data-stu-id="da08f-104">You can specify Archiving options to be applied to specific sites by creating and configuring options in an Archiving configuration for each of those sites.</span></span> <span data-ttu-id="da08f-105">Una configurazione del sito sostituisce la configurazione globale, ma solo per il sito specificato nella configurazione del sito.</span><span class="sxs-lookup"><span data-stu-id="da08f-105">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> <span data-ttu-id="da08f-106">Le configurazioni del pool eseguono l'override delle configurazioni sito</span><span class="sxs-lookup"><span data-stu-id="da08f-106">Pool configurations override site configurations</span></span>

<span data-ttu-id="da08f-107">Per informazioni dettagliate sul funzionamento delle configurazioni di archiviazione, ad esempio la gerarchia per le configurazioni globali, del sito e del pool, vedere funzionamento dell' [archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, nella documentazione di distribuzione o nelle operazioni.</span><span class="sxs-lookup"><span data-stu-id="da08f-107">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="da08f-108">Devi specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="da08f-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="da08f-109">Per abilitare l'archiviazione, è necessario specificare i criteri di archiviazione per controllare l'archiviazione delle comunicazioni interne ed esterne a livello globale e, se necessario, ai livelli di sito e utente.</span><span class="sxs-lookup"><span data-stu-id="da08f-109">To enable archiving, you must specify archiving policies to control the archiving of internal and external communications at the global level and, if appropriate, at site and user levels.</span></span> <span data-ttu-id="da08f-110">Se si configurano i criteri a livello di utente, è necessario assegnare i criteri utente anche a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="da08f-110">If you configure user-level policies, you must also assign the user policies to specific users.</span></span> <span data-ttu-id="da08f-111">Per informazioni dettagliate sulla creazione e la configurazione dei criteri di archiviazione, vedere <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">gestione dell'archiviazione delle comunicazioni interne ed esterne in Lync Server 2013</A> nella documentazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="da08f-111">For details about creating and configuring archiving policies, see <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a><span data-ttu-id="da08f-112">Per configurare le opzioni di archiviazione a livello di sito</span><span class="sxs-lookup"><span data-stu-id="da08f-112">To configure archiving options at the site level</span></span>

1.  <span data-ttu-id="da08f-113">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="da08f-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="da08f-114">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da08f-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="da08f-115">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server 2013, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="da08f-115">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="da08f-116">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="da08f-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="da08f-117">Nella pagina **Configurazione archiviazione** fare clic su **nuovo**e quindi su **configurazione sito**.</span><span class="sxs-lookup"><span data-stu-id="da08f-117">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>

5.  <span data-ttu-id="da08f-118">In **Seleziona un sito**selezionare il sito da configurare per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="da08f-118">In **Select a Site**, select the site to be configured for archiving.</span></span>

6.  <span data-ttu-id="da08f-119">In **nuova impostazione archiviazione**, nella casella di riepilogo a discesa **Impostazioni archiviazione** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="da08f-119">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="da08f-120">Per abilitare l'archiviazione solo per le sessioni di messaggistica istantanea (IM), fare clic su **Archivia sessioni**istantanee.</span><span class="sxs-lookup"><span data-stu-id="da08f-120">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="da08f-121">Per abilitare l'archiviazione sia per le sessioni di messaggistica istantanea che per le conferenze, fare clic su **Archivia messaggistica istantanea e sessioni di conferenza Web**.</span><span class="sxs-lookup"><span data-stu-id="da08f-121">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="da08f-122">Per disabilitare l'archiviazione per il criterio, fare clic su **Disattiva archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="da08f-122">To disable archiving for the policy, click **Disable archiving**.</span></span>

7.  <span data-ttu-id="da08f-123">Anche in **nuove impostazioni di archiviazione**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="da08f-123">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="da08f-124">Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca messaggistica istantanea o servizi di conferenza Web se l'archiviazione non riesce** .</span><span class="sxs-lookup"><span data-stu-id="da08f-124">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="da08f-125">Per usare Microsoft Exchange Server per archiviare i dati di archiviazione, fare clic sulla casella di controllo **integrazione di Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="da08f-125">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="da08f-126">Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita l'eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="da08f-126">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="da08f-127">Per specificare l'eliminazione dopo un determinato numero di giorni, fare clic su **Elimina dati di archiviazione esportati e archivia dati archiviati dopo la durata massima (giorni)** e quindi specificare il numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="da08f-127">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="da08f-128">Per limitare l'eliminazione all'archiviazione dei dati esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.</span><span class="sxs-lookup"><span data-stu-id="da08f-128">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="da08f-129">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="da08f-129">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

