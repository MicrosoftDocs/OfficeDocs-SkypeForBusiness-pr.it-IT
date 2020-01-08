---
title: 'Lync Server 2013: Definizione dei requisiti per le conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60193673efff29ec877626a9c5c18be23507e6fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="7758d-102">Definizione dei requisiti per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7758d-102">Defining your requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7758d-103">_**Argomento Ultima modifica:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="7758d-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="7758d-104">Quando si determina quali funzionalità di conferenza distribuire, è necessario prendere in considerazione le funzionalità che si desidera siano disponibili per gli utenti e le funzionalità di larghezza di banda della rete.</span><span class="sxs-lookup"><span data-stu-id="7758d-104">When you are determining which conferencing capabilities to deploy, you need to consider the features that you want available to your users and your network bandwidth capabilities.</span></span> <span data-ttu-id="7758d-105">L'elenco seguente di domande guida l'utente attraverso il processo di pianificazione dei servizi di conferenza per determinare quali funzionalità di conferenza è necessario distribuire, in base ai requisiti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7758d-105">The following list of questions guides you through the conferencing planning process to determine what features of conferencing you should deploy, based on your organization’s requirements.</span></span>

  - <span data-ttu-id="7758d-106">**Si desidera abilitare le conferenze Web, che includono la collaborazione tra documenti e la condivisione di applicazioni?**</span><span class="sxs-lookup"><span data-stu-id="7758d-106">**Do you want to enable web conferencing, which includes document collaboration and application sharing?**</span></span>
    
    <span data-ttu-id="7758d-107">In questo caso, è necessario abilitare i servizi di conferenza per il pool Front-end in Microsoft Lync Server 2013, strumento di pianificazione o generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="7758d-107">If so, you must enable conferencing for your Front End pool in the Microsoft Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="7758d-108">Quando si Abilita la conferenza, è possibile abilitare sia le conferenze Web che le conferenze A/V.</span><span class="sxs-lookup"><span data-stu-id="7758d-108">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="7758d-109">La condivisione delle applicazioni richiede e usa più larghezza di banda della collaborazione tra documenti.</span><span class="sxs-lookup"><span data-stu-id="7758d-109">Application sharing requires and uses more network bandwidth than document collaboration.</span></span> <span data-ttu-id="7758d-110">Lync Server 2013 offre un meccanismo di limitazione per controllare ogni sessione di condivisione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7758d-110">Lync Server 2013 provides a throttling mechanism to control each application sharing session.</span></span> <span data-ttu-id="7758d-111">Per impostazione predefinita, questa opzione è impostata su 1,5 KB/secondo per ogni sessione.</span><span class="sxs-lookup"><span data-stu-id="7758d-111">By default, this is set to 1.5 KB/second for each session.</span></span>
    
    <span data-ttu-id="7758d-112">Se non si vuole abilitare la condivisione delle applicazioni ma si vuole collaborare con i documenti, è possibile abilitare i servizi di conferenza e usare i criteri di riunione per disabilitare la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="7758d-112">If you do not want to enable application sharing but you do want document collaboration, you can enable conferencing and use meeting policies to disable application sharing.</span></span> <span data-ttu-id="7758d-113">Per informazioni dettagliate sulla configurazione dei criteri di riunione, vedere [criteri di conferenza in Lync Server 2013](lync-server-2013-conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7758d-113">For details about configuring meeting policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md).</span></span>
    
    <span data-ttu-id="7758d-114">Per consentire agli utenti di condividere presentazioni di PowerPoint, è necessario configurare Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="7758d-114">To enable users to share PowerPoint presentations, you need to configure Office Web Apps Server.</span></span> <span data-ttu-id="7758d-115">Per informazioni dettagliate sulla configurazione di Office Web Apps Server, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="7758d-115">For details about configuring Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="7758d-116">**Si desidera abilitare una conferenza telefonica A/V?**</span><span class="sxs-lookup"><span data-stu-id="7758d-116">**Do you want to enable A/V conferencing?**</span></span>
    
    <span data-ttu-id="7758d-117">In questo caso, è necessario abilitare i servizi di conferenza per il pool Front-end in Lync Server 2013, strumento di pianificazione o generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="7758d-117">If so, you must enable conferencing for your Front End pool in the Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="7758d-118">Quando si Abilita la conferenza, è possibile abilitare sia le conferenze Web che le conferenze A/V.</span><span class="sxs-lookup"><span data-stu-id="7758d-118">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="7758d-119">A/V Conferencing richiede e usa più larghezza di banda della rete rispetto alle conferenze Web (che includono la collaborazione tra documenti e la condivisione delle applicazioni).</span><span class="sxs-lookup"><span data-stu-id="7758d-119">A/V conferencing requires and uses more network bandwidth than web conferencing (which includes document collaboration and application sharing).</span></span> <span data-ttu-id="7758d-120">Se non si vuole abilitare servizi di conferenza A/V ma si vuole abilitare le conferenze Web, è possibile abilitare i servizi di conferenza e usare i criteri di riunione per disabilitare le riunioni a/V.</span><span class="sxs-lookup"><span data-stu-id="7758d-120">If you do not want to enable A/V conferencing but you do want to enable web conferencing, you can enable conferencing and use meeting policies to disable A/V conferences.</span></span>
    
    <span data-ttu-id="7758d-121">Se si vuole abilitare le conferenze audio ma non le conferenze video, è possibile abilitare servizi di conferenza a/V e usare i criteri di riunione per evitare videoconferenze.</span><span class="sxs-lookup"><span data-stu-id="7758d-121">If you do want to enable audio conferences but not video conferences, you can enable A/V conferencing and use meeting policies to prevent video conferences.</span></span> <span data-ttu-id="7758d-122">In alternativa, puoi abilitare i servizi di conferenza A/V e consentire solo a determinati utenti di avviare o partecipare a conferenze A/V.</span><span class="sxs-lookup"><span data-stu-id="7758d-122">Alternatively, you can enable A/V conferencing and enable only certain users to start or participate in A/V conferences.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7758d-123">Enterprise Voice non è necessaria per l'uso di servizi di conferenza A/V.</span><span class="sxs-lookup"><span data-stu-id="7758d-123">Enterprise Voice is not required for you to use A/V conferencing.</span></span> <span data-ttu-id="7758d-124">Se si abilita una conferenza telefonica A/V, gli utenti possono aggiungere audio alle loro conferenze se hanno dispositivi audio, anche se si usa un PBX per la soluzione telefono.</span><span class="sxs-lookup"><span data-stu-id="7758d-124">If you enable A/V conferencing, your users can add audio to their conferences if they have audio devices, even if you use a PBX for your telephone solution.</span></span>

    
    </div>

  - <span data-ttu-id="7758d-125">**Si vuole consentire agli utenti di partecipare alla parte audio delle conferenze quando si usa un telefono PSTN?**</span><span class="sxs-lookup"><span data-stu-id="7758d-125">**Do you want to enable users to join the audio portion of conferences when using a PSTN phone?**</span></span>
    
    <span data-ttu-id="7758d-126">In caso affermativo, distribuire e abilitare i servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="7758d-126">If so, deploy and enable dial-in conferencing.</span></span> <span data-ttu-id="7758d-127">Gli utenti invitati, sia all'interno che all'esterno dell'organizzazione, possono quindi partecipare alla parte audio delle conferenze usando un telefono PSTN.</span><span class="sxs-lookup"><span data-stu-id="7758d-127">Invited users, both inside and outside your organization, can then join the audio portion of conferences by using a PSTN phone.</span></span>

  - <span data-ttu-id="7758d-128">**Si desidera consentire agli utenti esterni con i client di Lync Server 2013 di partecipare ai tipi di conferenza abilitati?**</span><span class="sxs-lookup"><span data-stu-id="7758d-128">**Do you want to enable external users with Lync Server 2013 clients to join the types of conferences that you have enabled?**</span></span>
    
    <span data-ttu-id="7758d-129">In questo caso, devi distribuire Edge Server.</span><span class="sxs-lookup"><span data-stu-id="7758d-129">If so, you should deploy Edge Servers.</span></span> <span data-ttu-id="7758d-130">Consentendo la partecipazione esterna alle riunioni, è possibile massimizzare l'investimento in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7758d-130">By allowing external participation in meetings, you maximize your investment in Lync Server 2013.</span></span> <span data-ttu-id="7758d-131">Ad esempio, gli utenti con computer portatili con Lync Server 2013 possono partecipare a conferenze ovunque si trovino, a casa, in aeroporto o nei siti del cliente.</span><span class="sxs-lookup"><span data-stu-id="7758d-131">For example, users with laptops with Lync Server 2013 can join conferences from wherever they are—at home, in the airport, or at customer sites.</span></span>
    
    <span data-ttu-id="7758d-132">Inoltre, con i server perimetrali distribuiti è possibile creare relazioni federate con altre organizzazioni, ad esempio i clienti o i fornitori, e gli utenti di tali organizzazioni possono collaborare più facilmente con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="7758d-132">Additionally, with Edge Servers deployed you can create federated relationships with other organizations-such as your customers or vendors-and users from those organizations can more easily collaborate with your users.</span></span>
    
    <span data-ttu-id="7758d-133">Per informazioni dettagliate sulla distribuzione di Edge Server, vedere [pianificazione per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) e [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="7758d-133">For details about deploying Edge Servers, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span> <span data-ttu-id="7758d-134">Per informazioni dettagliate sull'abilitazione dell'accesso esterno per il server Office Web Apps, vedere [pubblicazione di Office Web Apps Server in Lync server 2013 con un server proxy inverso](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span><span class="sxs-lookup"><span data-stu-id="7758d-134">For details about enabling external access for Office Web Apps Server, see [Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span></span>

  - <span data-ttu-id="7758d-135">**Si desidera controllare i client che possono partecipare alle riunioni di Lync Server 2013?**</span><span class="sxs-lookup"><span data-stu-id="7758d-135">**Do you want to control the clients that can join Lync Server 2013 meetings?**</span></span>
    
    <span data-ttu-id="7758d-136">In questo caso, devi configurare la pagina di partecipazione alla riunione in modo che siano disponibili solo le opzioni client che vuoi supportare.</span><span class="sxs-lookup"><span data-stu-id="7758d-136">If so, you should configure the meeting join page so that only the client options that you want to support are available.</span></span> <span data-ttu-id="7758d-137">Ogni volta che un utente fa clic su un collegamento per partecipare a una riunione pianificata, Lync Server 2013 rileva se un client è già installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="7758d-137">Each time a user clicks a link to join a scheduled meeting, Lync Server 2013 detects whether a client is already installed on the computer.</span></span> <span data-ttu-id="7758d-138">Avvia quindi il client predefinito e apre la pagina di partecipazione alla riunione, che contiene i collegamenti per i client alternativi.</span><span class="sxs-lookup"><span data-stu-id="7758d-138">It then starts the default client and opens the meeting join page, which contains links for alternate clients.</span></span> <span data-ttu-id="7758d-139">La pagina di partecipazione alla riunione contiene sempre l'opzione per l'uso di Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="7758d-139">The meeting join page always contains the option to use Microsoft Lync Web App.</span></span> <span data-ttu-id="7758d-140">Oltre a questa opzione, è possibile decidere se includere i collegamenti per il partecipante e le versioni precedenti di Communicator.</span><span class="sxs-lookup"><span data-stu-id="7758d-140">In addition to this option, you can decide whether to include links for Attendee and previous versions of Communicator.</span></span> <span data-ttu-id="7758d-141">Per informazioni dettagliate, vedere [configurazione della pagina di partecipazione alla riunione in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span><span class="sxs-lookup"><span data-stu-id="7758d-141">For details, see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7758d-142">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="7758d-142">In This Section</span></span>

  - [<span data-ttu-id="7758d-143">Requisiti per i servizi di conferenza Web in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7758d-143">Web conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-requirements.md)

  - [<span data-ttu-id="7758d-144">Requisiti di conferenza a/V in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7758d-144">A/V conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-a-v-conferencing-requirements.md)

  - [<span data-ttu-id="7758d-145">Requisiti per i servizi di conferenza telefonica con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7758d-145">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7758d-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7758d-146">See Also</span></span>


[<span data-ttu-id="7758d-147">Pianificazione dei servizi di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7758d-147">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)  
[<span data-ttu-id="7758d-148">Elenco di controllo di distribuzione per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7758d-148">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

