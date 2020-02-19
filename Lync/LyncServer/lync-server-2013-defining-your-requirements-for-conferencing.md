---
title: 'Lync Server 2013: definizione dei requisiti per le conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee3b7631a3c05fb497ee7fcdf37b6db984361845
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="8f5ff-102">Definizione dei requisiti per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f5ff-102">Defining your requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f5ff-103">_**Ultimo argomento modificato:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="8f5ff-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="8f5ff-p101">Per determinare le funzionalità di conferenza da distribuire, è necessario considerare le funzionalità che si desidera rendere disponibili agli utenti e le caratteristiche di larghezza di banda della rete. L'elenco di domande seguenti rappresenta una guida per il processo di pianificazione allo scopo di determinare le funzionalità di conferenza da distribuire, in base ai requisiti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-p101">When you are determining which conferencing capabilities to deploy, you need to consider the features that you want available to your users and your network bandwidth capabilities. The following list of questions guides you through the conferencing planning process to determine what features of conferencing you should deploy, based on your organization’s requirements.</span></span>

  - <span data-ttu-id="8f5ff-106">**Si desiderano abilitare le conferenze Web, che includono funzionalità di collaborazione sui documenti e condivisione di applicazioni?**</span><span class="sxs-lookup"><span data-stu-id="8f5ff-106">**Do you want to enable web conferencing, which includes document collaboration and application sharing?**</span></span>
    
    <span data-ttu-id="8f5ff-107">In caso affermativo, è necessario abilitare le conferenze per il pool Front end in Microsoft Lync Server 2013, Planning Tool o in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-107">If so, you must enable conferencing for your Front End pool in the Microsoft Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="8f5ff-108">L'abilitazione delle conferenze consente di abilitare sia le conferenze Web che le conferenze audio/video.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-108">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="8f5ff-109">Per la condivisione di applicazioni è richiesta e viene utilizzata più larghezza di banda di rete rispetto alla collaborazione sui documenti.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-109">Application sharing requires and uses more network bandwidth than document collaboration.</span></span> <span data-ttu-id="8f5ff-110">Lync Server 2013 fornisce un meccanismo di limitazione per controllare ogni sessione di condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-110">Lync Server 2013 provides a throttling mechanism to control each application sharing session.</span></span> <span data-ttu-id="8f5ff-111">Per impostazione predefinita, il limite è impostato su 1,5 Kb/secondo per ogni sessione.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-111">By default, this is set to 1.5 KB/second for each session.</span></span>
    
    <span data-ttu-id="8f5ff-112">Se non si desidera abilitare la condivisione di applicazioni, ma si desidera utilizzare la collaborazione sui documenti, è possibile abilitare le conferenze e utilizzare i criteri relativi alle riunioni per disabilitare la condivisione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-112">If you do not want to enable application sharing but you do want document collaboration, you can enable conferencing and use meeting policies to disable application sharing.</span></span> <span data-ttu-id="8f5ff-113">Per informazioni dettagliate sulla configurazione dei criteri di riunione, vedere [Conferencing Policies in Lync Server 2013](lync-server-2013-conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8f5ff-113">For details about configuring meeting policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md).</span></span>
    
    <span data-ttu-id="8f5ff-114">Per consentire agli utenti di condividere le presentazioni di PowerPoint, è necessario configurare il server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-114">To enable users to share PowerPoint presentations, you need to configure Office Web Apps Server.</span></span> <span data-ttu-id="8f5ff-115">Per informazioni dettagliate sulla configurazione del server Office Web Apps, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="8f5ff-115">For details about configuring Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="8f5ff-116">**Si desidera abilitare le conferenze audio/video?**</span><span class="sxs-lookup"><span data-stu-id="8f5ff-116">**Do you want to enable A/V conferencing?**</span></span>
    
    <span data-ttu-id="8f5ff-117">In caso affermativo, è necessario abilitare le conferenze per il pool Front end in Lync Server 2013, strumento di pianificazione o in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-117">If so, you must enable conferencing for your Front End pool in the Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="8f5ff-118">L'abilitazione delle conferenze consente di abilitare sia le conferenze Web che le conferenze audio/video.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-118">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="8f5ff-p107">Per le conferenze audio/video è richiesta e viene utilizzata maggiore larghezza di banda di rete rispetto alle conferenze Web (che includono le funzionalità di collaborazione sui documenti e condivisione di applicazioni). Se non si desidera abilitare le conferenze audio/video, ma si desidera abilitare le conferenze Web, è possibile abilitare le conferenze e utilizzare i criteri relativi alle riunioni per disabilitare le conferenze audio/video.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-p107">A/V conferencing requires and uses more network bandwidth than web conferencing (which includes document collaboration and application sharing). If you do not want to enable A/V conferencing but you do want to enable web conferencing, you can enable conferencing and use meeting policies to disable A/V conferences.</span></span>
    
    <span data-ttu-id="8f5ff-p108">Se si desidera abilitare le conferenze audio, ma non le conferenze video, è possibile abilitare le conferenze audio/video e utilizzare i criteri relativi alle riunioni per impedire le conferenze video. In alternativa, è possibile abilitare le conferenze audio/video e consentire solo a particolari utenti audio di avviare o partecipare a conferenze audio/video.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-p108">If you do want to enable audio conferences but not video conferences, you can enable A/V conferencing and use meeting policies to prevent video conferences. Alternatively, you can enable A/V conferencing and enable only certain users to start or participate in A/V conferences.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8f5ff-123">VoIP aziendale non è necessario per l'utilizzo di A/V Conferencing.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-123">Enterprise Voice is not required for you to use A/V conferencing.</span></span> <span data-ttu-id="8f5ff-124">Se si abilitano le conferenze audio/video, gli utenti possono aggiungere l'audio alle conferenze nel caso dispongano di dispositivi audio, anche se si utilizza una soluzione telefonica PBX.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-124">If you enable A/V conferencing, your users can add audio to their conferences if they have audio devices, even if you use a PBX for your telephone solution.</span></span>

    
    </div>

  - <span data-ttu-id="8f5ff-125">**Si desidera consentire agli utenti di partecipare alla parte audio delle conferenze quando si utilizza un telefono PSTN?**</span><span class="sxs-lookup"><span data-stu-id="8f5ff-125">**Do you want to enable users to join the audio portion of conferences when using a PSTN phone?**</span></span>
    
    <span data-ttu-id="8f5ff-p110">In caso affermativo, distribuire e abilitare le conferenze telefoniche con accesso esterno. Gli utenti invitati, sia all'interno che all'esterno dell'organizzazione, potranno quindi partecipare alla parte audio delle conferenze tramite un telefono PSTN.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-p110">If so, deploy and enable dial-in conferencing. Invited users, both inside and outside your organization, can then join the audio portion of conferences by using a PSTN phone.</span></span>

  - <span data-ttu-id="8f5ff-128">**Si desidera consentire agli utenti esterni con i client di Lync Server 2013 di partecipare ai tipi di conferenza abilitati?**</span><span class="sxs-lookup"><span data-stu-id="8f5ff-128">**Do you want to enable external users with Lync Server 2013 clients to join the types of conferences that you have enabled?**</span></span>
    
    <span data-ttu-id="8f5ff-129">In caso affermativo, è consigliabile distribuire server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-129">If so, you should deploy Edge Servers.</span></span> <span data-ttu-id="8f5ff-130">Consentendo la partecipazione esterna alle riunioni, è possibile massimizzare gli investimenti in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-130">By allowing external participation in meetings, you maximize your investment in Lync Server 2013.</span></span> <span data-ttu-id="8f5ff-131">Ad esempio, gli utenti con computer portatili con Lync Server 2013 possono partecipare a conferenze da qualsiasi luogo, a casa, in aeroporto o nei siti dei clienti.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-131">For example, users with laptops with Lync Server 2013 can join conferences from wherever they are—at home, in the airport, or at customer sites.</span></span>
    
    <span data-ttu-id="8f5ff-132">Con la distribuzione di server perimetrali, inoltre, è possibile creare relazioni federate con altre organizzazioni, ad esempio clienti o fornitori, e gli utenti di tali organizzazioni possono collaborare più facilmente con gli utenti della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-132">Additionally, with Edge Servers deployed you can create federated relationships with other organizations-such as your customers or vendors-and users from those organizations can more easily collaborate with your users.</span></span>
    
    <span data-ttu-id="8f5ff-133">Per informazioni dettagliate sulla distribuzione di server perimetrali, vedere [Planning for External User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) e [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="8f5ff-133">For details about deploying Edge Servers, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span> <span data-ttu-id="8f5ff-134">Per informazioni dettagliate sull'abilitazione dell'accesso esterno per il server Office Web Apps, vedere [pubblicazione di Office Web Apps Server in Lync server 2013 utilizzando un server proxy inverso](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span><span class="sxs-lookup"><span data-stu-id="8f5ff-134">For details about enabling external access for Office Web Apps Server, see [Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span></span>

  - <span data-ttu-id="8f5ff-135">**Si desidera controllare i client che possono partecipare alle riunioni di Lync Server 2013?**</span><span class="sxs-lookup"><span data-stu-id="8f5ff-135">**Do you want to control the clients that can join Lync Server 2013 meetings?**</span></span>
    
    <span data-ttu-id="8f5ff-136">In caso affermativo, è necessario configurare la pagina di partecipazione alle riunioni in modo che siano disponibili solo le opzioni client che si desidera supportare.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-136">If so, you should configure the meeting join page so that only the client options that you want to support are available.</span></span> <span data-ttu-id="8f5ff-137">Ogni volta che un utente fa clic su un collegamento per partecipare a una riunione pianificata, Lync Server 2013 rileva se un client è già installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-137">Each time a user clicks a link to join a scheduled meeting, Lync Server 2013 detects whether a client is already installed on the computer.</span></span> <span data-ttu-id="8f5ff-138">Viene quindi avviato il client predefinito e viene aperta la pagina di partecipazione alla riunione, che contiene i collegamenti per i client alternativi.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-138">It then starts the default client and opens the meeting join page, which contains links for alternate clients.</span></span> <span data-ttu-id="8f5ff-139">Nella pagina di partecipazione alle riunioni è sempre contenuta l'opzione per l'utilizzo di Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-139">The meeting join page always contains the option to use Microsoft Lync Web App.</span></span> <span data-ttu-id="8f5ff-140">Oltre a questa opzione, è possibile decidere se includere i collegamenti per il partecipante e le versioni precedenti di Communicator.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-140">In addition to this option, you can decide whether to include links for Attendee and previous versions of Communicator.</span></span> <span data-ttu-id="8f5ff-141">Per informazioni dettagliate, vedere [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span><span class="sxs-lookup"><span data-stu-id="8f5ff-141">For details, see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8f5ff-142">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="8f5ff-142">In This Section</span></span>

  - [<span data-ttu-id="8f5ff-143">Requisiti di Web Conferencing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f5ff-143">Web conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-requirements.md)

  - [<span data-ttu-id="8f5ff-144">Requisiti di a/V Conferencing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f5ff-144">A/V conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-a-v-conferencing-requirements.md)

  - [<span data-ttu-id="8f5ff-145">Requisiti per le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f5ff-145">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8f5ff-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f5ff-146">See Also</span></span>


[<span data-ttu-id="8f5ff-147">Pianificazione per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f5ff-147">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)  
[<span data-ttu-id="8f5ff-148">Elenco di controllo di distribuzione per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f5ff-148">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

