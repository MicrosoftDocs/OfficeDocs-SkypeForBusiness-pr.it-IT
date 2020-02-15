---
title: 'Lync Server 2013: creare la progettazione della topologia iniziale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed95696dc0acad9030615f8a031672f8abf3a136
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a><span data-ttu-id="c8ec3-102">Creare la progettazione della topologia iniziale per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8ec3-102">Create the initial topology design for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8ec3-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c8ec3-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c8ec3-104">Dopo aver completato l'installazione di Lync Server 2013, strumento di pianificazione, è possibile avviare lo strumento di pianificazione e iniziare a progettare l'infrastruttura di Lync Server 2013 proposta.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-104">After you have finished installing the Lync Server 2013, Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Lync Server 2013 infrastructure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8ec3-105">Lo strumento di pianificazione è uno strumento basato su procedure guidate con guide dettagliate per informare il processo decisionale nella progettazione dei siti e della topologia.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-105">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="c8ec3-106">Questo argomento non è una guida esaustiva, ma è sufficiente per iniziare a utilizzare lo strumento di pianificazione nelle sessioni di progettazione.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-106">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="c8ec3-107">Per iniziare a utilizzare lo strumento di pianificazione e creare un progetto iniziale</span><span class="sxs-lookup"><span data-stu-id="c8ec3-107">To get started using the Planning Tool and create the initial design</span></span>

1.  <span data-ttu-id="c8ec3-108">Avviare lo Strumento di pianificazione di Lync Server 2013: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Strumento di pianificazione**.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-108">Start the Lync Server 2013, Planning Tool: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Planning Tool**.</span></span>

2.  <span data-ttu-id="c8ec3-109">Dopo che lo strumento di pianificazione è stato avviato, viene visualizzata la pagina **Benvenuto allo strumento di pianificazione per Microsoft Lync Server 2013** .</span><span class="sxs-lookup"><span data-stu-id="c8ec3-109">After the Planning Tool has started, the **Welcome to the Planning Tool for Microsoft Lync Server 2013** page appears.</span></span> <span data-ttu-id="c8ec3-110">Per iniziare la progettazione, scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8ec3-110">Choose one of the following options to begin your design:</span></span>
    
      - <span data-ttu-id="c8ec3-111">**Opzione 1:**   iniziare a fare clic su **Introduzione** fornisce una serie specifica di domande sull'intervista con selezioni rilevanti per definire i criteri.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-111">**Option 1: Get Started**   Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="c8ec3-112">Dopo aver completato la sezione iniziale del questionario di **Per iniziare**, passare alla sezione **Progetta siti** per definire l'architettura dei siti.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-112">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="c8ec3-113">Per completare questa opzione, procedere al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-113">To complete this option, proceed to step 3.</span></span>
    
      - <span data-ttu-id="c8ec3-114">**Opzione 2: la progettazione dei siti**   che fanno clic su **siti di progettazione** nella pagina di benvenuto ignora le domande relative all'intervista presentate nella sezione **Introduzione** .</span><span class="sxs-lookup"><span data-stu-id="c8ec3-114">**Option 2: Design Sites**   Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="c8ec3-115">Le informazioni che sarebbero state raccolte rispondendo alle domande di intervista nella sezione **Introduzione** sono impostate su valori predefiniti con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-115">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="c8ec3-116">Facendo clic su **siti di progettazione**, il progettista esperto può ignorare l'intervista iniziale e modificare i valori predefiniti, in base alle esigenze, nella pagina iniziale dei **siti centrali** .</span><span class="sxs-lookup"><span data-stu-id="c8ec3-116">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="c8ec3-117">Per completare questa opzione, ignorare i passaggi da 3 a 5 e iniziare dal passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-117">To complete this option, skip over steps 3-5 and start at step 6.</span></span>
    
      - <span data-ttu-id="c8ec3-118">**Opzione 3: visualizzare la topologia**   salvata se è stata già completata e salvata una topologia mediante l'utilizzo precedente dello strumento di pianificazione, è possibile ignorare la maggior parte di questi passaggi e iniziare aprendo e visualizzando la topologia.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-118">**Option 3: Display Your Saved Topology**   If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="c8ec3-119">È inoltre possibile apportare modifiche e aggiornamenti alla topologia, salvarla nuovamente e quindi esportarla in Microsoft Excel o Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-119">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="c8ec3-120">Per completare questa opzione, ignorare i passaggi da 3 a 12 e iniziare dal passaggio 13.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-120">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3.  <span data-ttu-id="c8ec3-121">Fare **clic su inizia per** iniziare a progettare la topologia di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-121">Click **Get Started** to begin designing your Lync Server 2013 topology.</span></span>

4.  <span data-ttu-id="c8ec3-122">Rispondere alle domande di ogni sezione selezionando i criteri appropriati per il progetto e quindi fare clic su **Avanti** per passare alla pagina successiva della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-122">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page.</span></span> <span data-ttu-id="c8ec3-123">Fare clic su **indietro** per apportare modifiche alle pagine precedenti.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-123">Click **Back** to make changes on previous pages.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="c8ec3-124">Ogni pagina contiene una descrizione dei criteri di selezione e alcuni consigli in base alle procedure preferite e alla pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-124">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="c8ec3-125">Se si desiderano ulteriori dettagli, <STRONG>fare clic su ulteriori informazioni</STRONG> per leggere i dati dettagliati dalla documentazione relativa alla pianificazione di Lync Server 2013 nel sito Web Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-125">If you require additional details, click <STRONG>Learn more</STRONG> to read detailed information from the Lync Server 2013 Planning documentation on the Microsoft TechNet website.</span></span> <span data-ttu-id="c8ec3-126">Per accedere a questo sito Web, è necessario disporre di connettività Internet.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-126">You must have Internet connectivity to access the Microsoft TechNet website.</span></span>

    
    </div>

5.  <span data-ttu-id="c8ec3-127">Selezionare le opzioni appropriate per la progettazione.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-127">Select the appropriate options for your design.</span></span> <span data-ttu-id="c8ec3-128">Dopo la definizione dei criteri iniziali, verrà visualizzata la conferma del completamento della panoramica iniziale.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-128">After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6.  <span data-ttu-id="c8ec3-129">Fare clic su **progetta siti** per definire il sito centrale.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-129">Click **Design Sites** to define your central site.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8ec3-130">Ogni topologia di Lync Server 2013 avrà almeno un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-130">Each Lync Server 2013 topology will have at least one central site.</span></span> <span data-ttu-id="c8ec3-131">La struttura può disporre di un unico sito centrale, un sito centrale con un numero di siti di succursale, un numero di siti centrali o un numero di siti centrali con siti di succursale associati a ogni sito centrale.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-131">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

    
    </div>

7.  <span data-ttu-id="c8ec3-132">In **nome sito**Digitare il nome che identificherà questo sito centrale.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-132">In **Site Name**, type the name that will identify this central site.</span></span>

8.  <span data-ttu-id="c8ec3-133">Negli **utenti di Site homed**Digitare il numero previsto di utenti simultanei locali che verranno ospitati in questo sito centrale.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-133">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9.  <span data-ttu-id="c8ec3-134">Negli **utenti cloud homed**Digitare il numero previsto di utenti simultanei online che verranno ospitati in questo sito centrale.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-134">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="c8ec3-135">Modificare le selezioni per la collaborazione online, gli utenti, la voce, le opzioni di distribuzione aggiuntive o le applicazioni server, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-135">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c8ec3-136">A questo punto della struttura è possibile selezionare o deselezionare solo le opzioni per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-136">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="c8ec3-137">Tuttavia, è possibile configurare altre opzioni in una fase successiva dello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-137">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="c8ec3-138">Alcune opzioni non sono disponibili e non possono essere deselezionate.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-138">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="c8ec3-139">Inoltre, può essere necessario deselezionare un'opzione per deselezionarne un'altra.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-139">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="c8ec3-140">Ad esempio, se si deseleziona l'opzione VoIP <STRONG>aziendale</STRONG> in voce, vengono cancellate anche le opzioni del <STRONG>gruppo di risposta</STRONG>, <STRONG>annuncio</STRONG>e <STRONG>parcheggio di chiamata</STRONG> in applicazioni server (tutte funzionalità di VoIP aziendale).</span><span class="sxs-lookup"><span data-stu-id="c8ec3-140">For example, if you clear the <STRONG>Enterprise Voice</STRONG> option under Voice, then the <STRONG>Response Group</STRONG>, <STRONG>Announcement</STRONG>, and <STRONG>Call Park</STRONG> options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

    
    </div>

11. <span data-ttu-id="c8ec3-141">Dopo aver definito il nome del sito e il numero di utenti, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-141">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="c8ec3-142">Nelle pagine seguenti sono disponibili informazioni su domini SIP, Impostazioni conferenza, impostazioni vocali e infrastruttura, messaggistica unificata di Exchange, accesso utente esterno, impostazioni chat persistente, impostazioni client, opzioni di collocazione e siti di succursale.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-142">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="c8ec3-143">Rispondere a queste domande nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-143">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="c8ec3-144">L'ultima domanda richiede se si desidera creare un altro sito centrale.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-144">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="c8ec3-145">Se si seleziona **Sì**, lo strumento di pianificazione torna alla pagina siti centrali.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-145">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="c8ec3-146">Se si seleziona **No**, fare clic su **Avanti**e quindi su **Disegna** per visualizzare la visualizzazione Topologia globale di alto livello.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-146">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="c8ec3-147">Per visualizzare una topologia esistente, fare clic su **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-147">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="c8ec3-148">Fare clic sul file XML che corrisponde alla topologia salvata in precedenza e quindi su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-148">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="c8ec3-149">Nello strumento di pianificazione viene visualizzata la pagina della topologia globale.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-149">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="c8ec3-150">È ora possibile avviare la modifica, l'aggiornamento o la modifica della topologia utilizzando gli strumenti disponibili nello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="c8ec3-150">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c8ec3-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8ec3-151">See Also</span></span>


[<span data-ttu-id="c8ec3-152">Modifica della progettazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8ec3-152">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

