---
title: 'Lync Server 2013: creare la struttura della topologia iniziale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 656e9605695fe7dab160469ffa9e9c5075ac807b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a><span data-ttu-id="de0b8-102">Creare la struttura della topologia iniziale per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de0b8-102">Create the initial topology design for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de0b8-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="de0b8-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="de0b8-104">Dopo aver completato l'installazione di Lync Server 2013, strumento di pianificazione, si è pronti per avviare lo strumento di pianificazione e iniziare a progettare l'infrastruttura di Lync Server 2013 proposta.</span><span class="sxs-lookup"><span data-stu-id="de0b8-104">After you have finished installing the Lync Server 2013, Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Lync Server 2013 infrastructure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="de0b8-105">Lo strumento di pianificazione è uno strumento basato su una procedura guidata con guide dettagliate per informare il processo decisionale nella progettazione di siti e topologia.</span><span class="sxs-lookup"><span data-stu-id="de0b8-105">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="de0b8-106">Questo argomento è inteso come guida esaustiva, ma semplicemente per iniziare a usare lo strumento pianificazione nelle sessioni di progettazione.</span><span class="sxs-lookup"><span data-stu-id="de0b8-106">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="de0b8-107">Per iniziare a usare lo strumento pianificazione e creare la struttura iniziale</span><span class="sxs-lookup"><span data-stu-id="de0b8-107">To get started using the Planning Tool and create the initial design</span></span>

1.  <span data-ttu-id="de0b8-108">Avviare Lync Server 2013, strumento di pianificazione: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **strumento di pianificazione**.</span><span class="sxs-lookup"><span data-stu-id="de0b8-108">Start the Lync Server 2013, Planning Tool: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Planning Tool**.</span></span>

2.  <span data-ttu-id="de0b8-109">Dopo l'avvio dello strumento di pianificazione, viene visualizzata la pagina **Benvenuto nello strumento di pianificazione per Microsoft Lync Server 2013** .</span><span class="sxs-lookup"><span data-stu-id="de0b8-109">After the Planning Tool has started, the **Welcome to the Planning Tool for Microsoft Lync Server 2013** page appears.</span></span> <span data-ttu-id="de0b8-110">Per iniziare la progettazione, scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="de0b8-110">Choose one of the following options to begin your design:</span></span>
    
      - <span data-ttu-id="de0b8-111">**Opzione 1:**   iniziare a fare **clic su per iniziare offre** una serie specifica di domande sulle interviste con selezioni rilevanti per definire i criteri.</span><span class="sxs-lookup"><span data-stu-id="de0b8-111">**Option 1: Get Started**   Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="de0b8-112">Dopo aver completato la sezione iniziale dell'intervista **introduttiva** , si procede in **siti di progettazione** per definire l'architettura del sito.</span><span class="sxs-lookup"><span data-stu-id="de0b8-112">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="de0b8-113">Per completare questa opzione, procedere con il passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="de0b8-113">To complete this option, proceed to step 3.</span></span>
    
      - <span data-ttu-id="de0b8-114">**Opzione 2: i siti**   di progettazione che fanno clic su **siti di progettazione** nella pagina di benvenuto ignorano le domande sull'intervista presentate nella sezione iniziare. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="de0b8-114">**Option 2: Design Sites**   Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="de0b8-115">Le informazioni che sarebbero state raccolte rispondendo alle domande sull'intervista nella sezione **Introduzione** sono impostate su valori predefiniti con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="de0b8-115">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="de0b8-116">Facendo clic su **siti di progettazione**, il progettista esperto può ignorare l'intervista iniziale e modificare i valori predefiniti, se necessario, nella pagina iniziale dei **siti centrali** .</span><span class="sxs-lookup"><span data-stu-id="de0b8-116">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="de0b8-117">Per completare questa opzione, saltare i passaggi 3-5 e iniziare dal passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="de0b8-117">To complete this option, skip over steps 3-5 and start at step 6.</span></span>
    
      - <span data-ttu-id="de0b8-118">**Opzione 3: visualizzare la topologia**   salvata se è già stata completata e salvata una topologia con l'uso precedente dello strumento di pianificazione, è possibile ignorare la maggior parte di questi passaggi e iniziare aprendo e visualizzando la topologia.</span><span class="sxs-lookup"><span data-stu-id="de0b8-118">**Option 3: Display Your Saved Topology**   If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="de0b8-119">È anche possibile apportare modifiche e aggiornamenti alla topologia, salvarla e quindi esportarla in Microsoft Excel o Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="de0b8-119">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="de0b8-120">Per completare questa opzione, saltare i passaggi 3-12 e iniziare dal passaggio 13.</span><span class="sxs-lookup"><span data-stu-id="de0b8-120">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3.  <span data-ttu-id="de0b8-121">Fare **clic su inizia per** iniziare a progettare la topologia di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de0b8-121">Click **Get Started** to begin designing your Lync Server 2013 topology.</span></span>

4.  <span data-ttu-id="de0b8-122">Rispondere a ogni sezione selezionando i criteri appropriati per la struttura e quindi fare clic su **Avanti** per passare alla pagina successiva della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="de0b8-122">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page.</span></span> <span data-ttu-id="de0b8-123">Fare clic su **indietro** per apportare modifiche alle pagine precedenti.</span><span class="sxs-lookup"><span data-stu-id="de0b8-123">Click **Back** to make changes on previous pages.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="de0b8-124">Ogni pagina contiene una descrizione dei criteri di selezione e suggerimenti basati sulle procedure preferite e sulla pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="de0b8-124">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="de0b8-125">Se sono necessari altri dettagli, fare clic su <STRONG>altre</STRONG> informazioni per leggere le istruzioni dettagliate della documentazione relativa alla pianificazione di Lync Server 2013 nel sito Web Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="de0b8-125">If you require additional details, click <STRONG>Learn more</STRONG> to read detailed information from the Lync Server 2013 Planning documentation on the Microsoft TechNet website.</span></span> <span data-ttu-id="de0b8-126">Per accedere al sito Web Microsoft TechNet è necessario disporre della connettività Internet.</span><span class="sxs-lookup"><span data-stu-id="de0b8-126">You must have Internet connectivity to access the Microsoft TechNet website.</span></span>

    
    </div>

5.  <span data-ttu-id="de0b8-127">Selezionare le opzioni appropriate per la progettazione.</span><span class="sxs-lookup"><span data-stu-id="de0b8-127">Select the appropriate options for your design.</span></span> <span data-ttu-id="de0b8-128">Dopo aver definito i criteri iniziali, una pagina confermerà che la panoramica delle caratteristiche è completa.</span><span class="sxs-lookup"><span data-stu-id="de0b8-128">After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6.  <span data-ttu-id="de0b8-129">Fare clic su **siti di progettazione** per definire il sito centrale.</span><span class="sxs-lookup"><span data-stu-id="de0b8-129">Click **Design Sites** to define your central site.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="de0b8-130">Ogni topologia di Lync Server 2013 avrà almeno un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="de0b8-130">Each Lync Server 2013 topology will have at least one central site.</span></span> <span data-ttu-id="de0b8-131">La progettazione può avere un singolo sito centrale, un sito centrale con numerosi siti di succursale, un numero di siti centrali o un numero di siti centrali con siti di succursale associati a ogni sito centrale.</span><span class="sxs-lookup"><span data-stu-id="de0b8-131">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

    
    </div>

7.  <span data-ttu-id="de0b8-132">In **nome sito**Digitare il nome che identificherà questo sito centrale.</span><span class="sxs-lookup"><span data-stu-id="de0b8-132">In **Site Name**, type the name that will identify this central site.</span></span>

8.  <span data-ttu-id="de0b8-133">Negli **utenti**ospitati nel sito digitare il numero previsto di utenti simultanei locali che verranno assegnati in questo sito centrale.</span><span class="sxs-lookup"><span data-stu-id="de0b8-133">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9.  <span data-ttu-id="de0b8-134">Negli **utenti cloud homed**Digitare il numero previsto di utenti concorrenti online che verranno assegnati in questo sito centrale.</span><span class="sxs-lookup"><span data-stu-id="de0b8-134">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="de0b8-135">Modificare le selezioni per la collaborazione online, gli utenti, la voce, le opzioni di distribuzione aggiuntive o le applicazioni server, se necessario.</span><span class="sxs-lookup"><span data-stu-id="de0b8-135">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="de0b8-136">A questo punto della struttura, è possibile selezionare o deselezionare solo le opzioni per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="de0b8-136">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="de0b8-137">È tuttavia possibile configurare altre opzioni in una fase successiva dello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="de0b8-137">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="de0b8-138">Esistono anche opzioni che non sono disponibili e non possono essere deselezionate.</span><span class="sxs-lookup"><span data-stu-id="de0b8-138">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="de0b8-139">Inoltre, potrebbe essere necessario cancellare un'opzione per cancellarne un'altra.</span><span class="sxs-lookup"><span data-stu-id="de0b8-139">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="de0b8-140">Se, ad esempio, si deseleziona l'opzione VoIP <STRONG>aziendale</STRONG> in Voice, vengono deselezionate anche le opzioni <STRONG>gruppo risposta</STRONG>, <STRONG>annuncio</STRONG>e <STRONG>parcheggio di chiamata</STRONG> in applicazioni server (tutte caratteristiche di Enterprise Voice).</span><span class="sxs-lookup"><span data-stu-id="de0b8-140">For example, if you clear the <STRONG>Enterprise Voice</STRONG> option under Voice, then the <STRONG>Response Group</STRONG>, <STRONG>Announcement</STRONG>, and <STRONG>Call Park</STRONG> options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

    
    </div>

11. <span data-ttu-id="de0b8-141">Dopo aver definito un nome di sito e un numero di utenti, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="de0b8-141">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="de0b8-142">Le pagine seguenti chiedono informazioni sui domini SIP, le impostazioni conferenza, le impostazioni vocali e l'infrastruttura, la messaggistica unificata di Exchange, l'accesso degli utenti esterni, le impostazioni della chat persistente, le impostazioni client, le opzioni di collocazione e i siti di filiale</span><span class="sxs-lookup"><span data-stu-id="de0b8-142">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="de0b8-143">Rispondere a queste domande in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="de0b8-143">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="de0b8-144">La domanda finale chiede se si vuole creare un altro sito centrale.</span><span class="sxs-lookup"><span data-stu-id="de0b8-144">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="de0b8-145">Se si seleziona **Sì**, lo strumento di pianificazione torna alla pagina siti centrali.</span><span class="sxs-lookup"><span data-stu-id="de0b8-145">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="de0b8-146">Se si seleziona **No**, fare clic su **Avanti**e quindi su **disegno** per visualizzare la visualizzazione Topologia globale di alto livello.</span><span class="sxs-lookup"><span data-stu-id="de0b8-146">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="de0b8-147">Per visualizzare una topologia esistente, fare clic su **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="de0b8-147">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="de0b8-148">Fare clic sul file XML che rappresenta la topologia salvata in precedenza e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="de0b8-148">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="de0b8-149">Lo strumento di pianificazione Visualizza la pagina della topologia globale.</span><span class="sxs-lookup"><span data-stu-id="de0b8-149">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="de0b8-150">Ora è possibile iniziare a modificare, aggiornare o modificare la topologia usando gli strumenti disponibili nello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="de0b8-150">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="de0b8-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de0b8-151">See Also</span></span>


[<span data-ttu-id="de0b8-152">Modifica della progettazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de0b8-152">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

