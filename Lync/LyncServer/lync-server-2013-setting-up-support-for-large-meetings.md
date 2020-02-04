---
title: 'Lync Server 2013: configurazione del supporto per riunioni di grandi dimensioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e8331c28d5bd06e6a3f7d9dab2fba7db334cd00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="dc3f0-102">Configurazione del supporto per riunioni di grandi dimensioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc3f0-102">Setting up support for large meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc3f0-103">_**Argomento Ultima modifica:** 2014-05-12_</span><span class="sxs-lookup"><span data-stu-id="dc3f0-103">_**Topic Last Modified:** 2014-05-12_</span></span>

<span data-ttu-id="dc3f0-104">Il supporto di riunioni di grandi dimensioni per gli utenti fino a 1000 richiede la creazione di una topologia appropriata, la riunione dei prerequisiti hardware e software e la configurazione appropriata dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-104">Supporting large meetings of up to 1000 users requires creating an appropriate topology, meeting hardware and software prerequisites, and configuring the environment appropriately.</span></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="dc3f0-105">Requisiti di topologia</span><span class="sxs-lookup"><span data-stu-id="dc3f0-105">Topology Requirements</span></span>

<span data-ttu-id="dc3f0-106">Una singola riunione di grandi dimensioni richiede almeno un server front-end e un server back-end.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-106">A single large meeting requires at least one Front End Server and one Back End Server.</span></span> <span data-ttu-id="dc3f0-107">Tuttavia, per ottenere una disponibilità elevata, è consigliabile un pool di due front end server con server back-end con mirroring.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-107">However, to provide high availability, we recommend a two Front End Server pool with mirrored Back End Servers.</span></span>

<span data-ttu-id="dc3f0-108">L'utente che ospita le riunioni di grandi dimensioni deve avere il proprio account utente ospitato in questo pool.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-108">The user who hosts the large meetings must have their user account homed in this pool.</span></span> <span data-ttu-id="dc3f0-109">Tuttavia, non è consigliabile ospitare altri account utente in questo pool.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-109">However, we do not recommend that you host other user accounts in this pool.</span></span> <span data-ttu-id="dc3f0-110">Usalo invece solo per le riunioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-110">Instead, use it only for the large meetings.</span></span> <span data-ttu-id="dc3f0-111">La procedura consigliata consiste nel creare un account utente speciale in questo pool da usare solo per ospitare riunioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-111">The best practice is to create a special user account in this pool to be used only to host large meetings.</span></span> <span data-ttu-id="dc3f0-112">Dato che l'impostazione di grande riunione è ottimizzata per le prestazioni, l'uso di un utente normale può avere problemi come l'incapacità di promuovere una sessione P2P a una riunione quando è coinvolto un endpoint PSTN.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-112">Since the large meeting setting is optimized for performance, using it as a normal user could have problems such as the inability to promote a P2P session to a meeting when a PSTN endpoint is involved.</span></span>

<span data-ttu-id="dc3f0-113">La gestione di un pool con esattamente due server front-end richiede alcune considerazioni particolari.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-113">Managing a pool with exactly two Front End Servers requires some special considerations.</span></span> <span data-ttu-id="dc3f0-114">Per altre informazioni, vedere [topologie e componenti per i server front-end, la messaggistica istantanea e la presenza in Lync server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="dc3f0-114">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="dc3f0-115">Inoltre, se si vuole specificare facoltativamente il backup e il failover del ripristino di emergenza per il pool usato per riunioni di grandi dimensioni, è possibile associarlo a un pool di dati in un altro Data Center.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-115">Additionally, if you want to optionally provide disaster recovery backup and failover for the pool used for large meetings, you can pair it with a similarly set up dedicated pool in a different data center.</span></span> <span data-ttu-id="dc3f0-116">Per informazioni dettagliate, vedere [pianificazione per l'elevata disponibilità e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="dc3f0-116">For details, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<span data-ttu-id="dc3f0-117">![Configurazione di pool per riunioni di grandi dimensioni](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Configurazione di pool per riunioni di grandi dimensioni")</span><span class="sxs-lookup"><span data-stu-id="dc3f0-117">![Large Meetings pool configuration](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Large Meetings pool configuration")</span></span>

<span data-ttu-id="dc3f0-118">Altre note sulla topologia includono:</span><span class="sxs-lookup"><span data-stu-id="dc3f0-118">Additional notes about the topology include:</span></span>

  - <span data-ttu-id="dc3f0-119">È necessaria una condivisione file per archiviare il contenuto della riunione e, se il server di archiviazione è distribuito e abilitato, per l'archiviazione dei file di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-119">A file share is required for storing meeting content and, if Archiving Server is deployed and enabled, for storing the archiving files.</span></span> <span data-ttu-id="dc3f0-120">La condivisione file può essere dedicata al pool o può essere la stessa condivisione di file usata da un altro pool nel sito in cui è distribuito il pool.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-120">The file share can be dedicated to the pool or can be the same file share used by another pool at the site in which the pool is deployed.</span></span> <span data-ttu-id="dc3f0-121">Per informazioni dettagliate sulla configurazione della condivisione file, vedere [configurare l'archiviazione dei file per Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span><span class="sxs-lookup"><span data-stu-id="dc3f0-121">For details about configuring the file share, see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>

  - <span data-ttu-id="dc3f0-122">È necessario un server Office Web Apps per abilitare la funzionalità presentazione di PowerPoint in riunioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-122">A Office Web Apps Server is required for enabling the PowerPoint presentation functionality in large meetings.</span></span> <span data-ttu-id="dc3f0-123">Il server Office Web Apps può essere dedicato al grande pool di riunioni oppure può essere lo stesso server di Office Web Apps usato da altri pool nel sito in cui è distribuito il pool dedicato.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-123">The Office Web Apps Server can be dedicated to the large meeting pool or, it can be the same Office Web Apps Server used by other pools at the site in which the dedicated pool is deployed.</span></span>

  - <span data-ttu-id="dc3f0-124">Il bilanciamento del carico dei server front-end richiede il bilanciamento del carico hardware per il traffico HTTP, ad esempio il download del contenuto della riunione.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-124">Load balancing of the Front End Servers requires hardware load balancing for the HTTP traffic (such as meeting content download).</span></span> <span data-ttu-id="dc3f0-125">Il bilanciamento del carico DNS è consigliato per il traffico SIP.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-125">DNS load balancing is recommended for SIP traffic.</span></span> <span data-ttu-id="dc3f0-126">Per informazioni dettagliate, vedere [requisiti di bilanciamento del carico per Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc3f0-126">For details see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="dc3f0-127">Se si vuole usare il server di monitoraggio per il pool di grandi riunioni dedicato, è consigliabile usare il server di monitoraggio e il relativo database condivisi in tutti i pool di server front-end della distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-127">If you want to use Monitoring Server for the dedicated large-meeting pool, we recommend using the Monitoring Server and its database that are shared across all of the Front End Server pools in your Lync Server deployment.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements"></a><span data-ttu-id="dc3f0-128">Requisiti hardware e software</span><span class="sxs-lookup"><span data-stu-id="dc3f0-128">Hardware and Software Requirements</span></span>

<span data-ttu-id="dc3f0-129">I requisiti hardware per i server in un pool di grandi riunioni dedicato sono gli stessi per gli altri server di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-129">The hardware requirements for servers in a dedicated large-meeting pool are the same as for your other Lync Server 2013 servers.</span></span> <span data-ttu-id="dc3f0-130">Per informazioni dettagliate sui requisiti hardware, vedere "[piattaforme hardware server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="dc3f0-130">For details about hardware requirements, see "[Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="dc3f0-131">I server in un pool di grandi riunioni dedicato devono soddisfare tutti i requisiti software di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-131">Servers in a dedicated large-meeting pool must meet all Lync Server 2013 software requirements.</span></span> <span data-ttu-id="dc3f0-132">Per informazioni dettagliate sui requisiti software, vedere la documentazione seguente:</span><span class="sxs-lookup"><span data-stu-id="dc3f0-132">For details about software requirements, please see the following documentation:</span></span>

  - [<span data-ttu-id="dc3f0-133">Supporto del sistema operativo per server e strumenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc3f0-133">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="dc3f0-134">Supporto per il software di database in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc3f0-134">Database software support in Lync Server 2013</span></span>](lync-server-2013-database-software-support.md)

  - [<span data-ttu-id="dc3f0-135">Requisiti software aggiuntivi per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc3f0-135">Additional software requirements for Lync Server 2013</span></span>](lync-server-2013-additional-software-requirements.md)

<span data-ttu-id="dc3f0-136">Inoltre, sia Lync Server 2013 che tutti i client Lync Server 2013 devono avere gli aggiornamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-136">Additionally, both Lync Server 2013 and all Lync Server 2013 clients must have the latest updates.</span></span>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="dc3f0-137">Requisiti di configurazione</span><span class="sxs-lookup"><span data-stu-id="dc3f0-137">Configuration Requirements</span></span>

<span data-ttu-id="dc3f0-138">È consigliabile creare un nuovo criterio di conferenza in modo specifico per riunioni di grandi dimensioni e quindi assegnare i criteri per i servizi di conferenza agli utenti residenti nel pool di grandi riunioni dedicato.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-138">We recommend creating a new conferencing policy specifically for large meetings, and then assigning the conferencing policy to the users who are homed on the dedicated large-meeting pool.</span></span> <span data-ttu-id="dc3f0-139">Configurare i criteri di conferenza con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc3f0-139">Configure the conferencing policy using the following settings:</span></span>

  - <span data-ttu-id="dc3f0-140">Impostare l'opzione **MaxMeetingSize** su **1000**.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-140">Set the **MaxMeetingSize** option to **1000**.</span></span> <span data-ttu-id="dc3f0-141">(Il valore predefinito è **250**).</span><span class="sxs-lookup"><span data-stu-id="dc3f0-141">(The default is **250**.)</span></span>

  - <span data-ttu-id="dc3f0-142">Imposta l'opzione **AllowLargeMeetings** su **true**.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-142">Set the **AllowLargeMeetings** option to **True**.</span></span>

  - <span data-ttu-id="dc3f0-143">Impostare l'opzione **EnableAppDesktopSharing** su **None**.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-143">Set the **EnableAppDesktopSharing** option to **None**.</span></span>

  - <span data-ttu-id="dc3f0-144">Imposta l'opzione **AllowUserToScheduleMeetingsWithAppSharing** su **false**.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-144">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>

  - <span data-ttu-id="dc3f0-145">Imposta l'opzione **AllowSharedNotes** su **false**.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-145">Set the **AllowSharedNotes** option to **False**.</span></span>

  - <span data-ttu-id="dc3f0-146">Imposta l'opzione **AllowAnnotations** su **false**.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-146">Set the **AllowAnnotations** option to **False**.</span></span>

  - <span data-ttu-id="dc3f0-147">Imposta l'opzione **DisablePowerPointAnnotations** su **true**.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-147">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>

  - <span data-ttu-id="dc3f0-148">Imposta l'opzione **AllowMultiview** su **false**.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-148">Set the **AllowMultiview** option to **False**.</span></span>

  - <span data-ttu-id="dc3f0-149">Imposta l'opzione **EnableMultiviewJoin** su **false**.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-149">Set the **EnableMultiviewJoin** option to **False**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dc3f0-150">Il supporto per le riunioni di grandi dimensioni dell'utente di 1000 in Lync Server 2013 richiede l'impostazione di <STRONG>AllowLargeMeetings</STRONG> nei criteri di conferenza per l'utilità di pianificazione della riunione per essere impostata su true.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-150">The support for 1000 user large meetings in Lync Server 2013 requires the <STRONG>AllowLargeMeetings</STRONG> setting in the conferencing policy for the meeting scheduler to be set to true.</span></span> <span data-ttu-id="dc3f0-151">Quando questa impostazione è impostata su true, l'esperienza di Lync sarà ottimizzata per riunioni extra di grandi dimensioni quando gli utenti partecipano a tale riunione.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-151">When this setting is set to true, the Lync experience will be optimized for extra large meetings when users joins such meeting.</span></span> <span data-ttu-id="dc3f0-152">In particolare, in una riunione di grandi dimensioni, Lync non visualizzerà l'iniziale o l'aggiornamento dell'elenco dei partecipanti a una riunione completa, ovvero un collo di bottiglia delle prestazioni sia per il client che per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-152">Specifically, in a large meeting, Lync will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Lync Server 2013.</span></span> <span data-ttu-id="dc3f0-153">Lync visualizzerà invece solo le informazioni sull'utente e l'elenco di relatori della riunione.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-153">Instead, Lync will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="dc3f0-154">Lync mostrerà ancora correttamente il numero totale di partecipanti disponibili nelle riunioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-154">Lync will still properly shows total number of participants available in the large meetings.</span></span>



</div>

<span data-ttu-id="dc3f0-155">Fatta eccezione per le **dimensioni massime della riunione** , tutte le altre impostazioni dei criteri di conferenza specificate in questo articolo sono necessarie per disabilitare le funzionalità di conferenza che non sono necessarie in riunioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-155">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>

<span data-ttu-id="dc3f0-156">Inoltre, è necessario configurare il pool di grandi riunioni dedicato in modo che ogni utente di Lync Server 2013 ospitato nel pool e responsabile della gestione della pianificazione della riunione disponga delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-156">Additionally, you need to configure the dedicated large-meeting pool so that each Lync Server 2013 user that is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="dc3f0-157">Per eseguire questa operazione, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc3f0-157">To do this, do the following:</span></span>

  - <span data-ttu-id="dc3f0-158">Impostare l'opzione **designa come relatore** su **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-158">Set the **Designate as presenter** option to **None**.</span></span> <span data-ttu-id="dc3f0-159">In genere, uno o pochi utenti di tutti i partecipanti a una riunione di grandi dimensioni sono relatori, quindi i partecipanti non devono essere ammessi automaticamente alle riunioni di grandi dimensioni come relatori.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-159">Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters.</span></span> <span data-ttu-id="dc3f0-160">Al contrario, i relatori devono essere designati in modo esplicito al momento della riunione o essere promossi esplicitamente durante la riunione di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-160">Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>

  - <span data-ttu-id="dc3f0-161">Verificare che la casella **di controllo tipo di conferenza assegnata per impostazione predefinita** non sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-161">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="dc3f0-162">Questa impostazione controlla se il componente aggiuntivo riunione online per Lync 2013 Pianifica sempre le conferenze con la conferenza assegnata dell'organizzatore, in modo che le riunioni pianificate abbiano lo stesso URL di join e le informazioni audio.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-162">This setting controls whether the Online Meeting Add-in for Lync 2013 always schedules conferences using the organizer’s assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="dc3f0-163">Negli scenari di collaborazione in piccoli gruppi, il tipo di conferenza assegnata funziona bene perché ognuno ha una propria conferenza assegnata individualmente e l'URL di join costante e le informazioni audio contribuiscono a facilitare l'Unione delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-163">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="dc3f0-164">Nello scenario della riunione di grandi dimensioni, tuttavia, il personale di supporto per le riunioni di grandi dimensioni pianifica le riunioni di grandi dimensioni con un singolo set di credenziali utente e quindi fornisce URL di join e informazioni audio ai richiedenti della riunione.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-164">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="dc3f0-165">In questo caso, l'uso di un URL diverso per partecipare a una riunione funziona meglio.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-165">In this case, using a different URL to join each meeting works better.</span></span>

  - <span data-ttu-id="dc3f0-166">Verificare che la casella **di controllo Ammetti gli utenti anonimi per impostazione predefinita** non sia selezionata, a meno che non sia obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-166">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="dc3f0-167">Questa impostazione ha effetto sul tipo di accesso alle riunioni predefinito programmato dal componente aggiuntivo riunione online per Lync 2013 quando non si usa una conferenza assegnata.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-167">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Lync 2013 when not using an assigned conference.</span></span> <span data-ttu-id="dc3f0-168">L'opzione appropriata per questa impostazione dipende dalle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-168">The appropriate option for this setting depends on your organization’s needs.</span></span> <span data-ttu-id="dc3f0-169">Se la maggior parte delle riunioni di grandi dimensioni per l'organizzazione è riunioni interne, non selezionare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-169">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="dc3f0-170">Se la maggior parte delle riunioni di grandi dimensioni richiede che gli utenti esterni possano partecipare, selezionare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-170">If most large meetings require that external users be able to join, select this option.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

