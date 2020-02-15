---
title: 'Lync Server 2013: impostazione del supporto per riunioni di grandi dimensioni'
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
ms.openlocfilehash: 8970d616d78cbfdafa591b58f123918cd20e0040
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="b2b46-102">Configurazione del supporto per le riunioni di grandi dimensioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2b46-102">Setting up support for large meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2b46-103">_**Ultimo argomento modificato:** 2014-05-12_</span><span class="sxs-lookup"><span data-stu-id="b2b46-103">_**Topic Last Modified:** 2014-05-12_</span></span>

<span data-ttu-id="b2b46-104">Il supporto di un gran numero di riunioni fino a 1000 utenti richiede la creazione di una topologia appropriata, il rispetto di prerequisiti hardware e software e la configurazione idonea dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="b2b46-104">Supporting large meetings of up to 1000 users requires creating an appropriate topology, meeting hardware and software prerequisites, and configuring the environment appropriately.</span></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="b2b46-105">Requisiti della topologia</span><span class="sxs-lookup"><span data-stu-id="b2b46-105">Topology Requirements</span></span>

<span data-ttu-id="b2b46-106">Una singola riunione di grandi dimensioni richiede almeno un front end server e un server back-end.</span><span class="sxs-lookup"><span data-stu-id="b2b46-106">A single large meeting requires at least one Front End Server and one Back End Server.</span></span> <span data-ttu-id="b2b46-107">Tuttavia, per garantire una disponibilità elevata, è consigliabile disporre di un pool di due front end server con server back-end con mirroring.</span><span class="sxs-lookup"><span data-stu-id="b2b46-107">However, to provide high availability, we recommend a two Front End Server pool with mirrored Back End Servers.</span></span>

<span data-ttu-id="b2b46-108">L'account dell'utente che ospita le riunioni di grandi dimensioni deve trovarsi in questo pool.</span><span class="sxs-lookup"><span data-stu-id="b2b46-108">The user who hosts the large meetings must have their user account homed in this pool.</span></span> <span data-ttu-id="b2b46-109">Non è tuttavia consigliabile ospitare altri account utente in questo pool.</span><span class="sxs-lookup"><span data-stu-id="b2b46-109">However, we do not recommend that you host other user accounts in this pool.</span></span> <span data-ttu-id="b2b46-110">Usarlo invece solo per le riunioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="b2b46-110">Instead, use it only for the large meetings.</span></span> <span data-ttu-id="b2b46-111">È preferibile creare un account utente speciale in questo pool da usare solo per ospitare riunioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="b2b46-111">The best practice is to create a special user account in this pool to be used only to host large meetings.</span></span> <span data-ttu-id="b2b46-112">Poiché l'impostazione di una riunione di grandi dimensioni è ottimizzata per le prestazioni, utilizzarla come utente normale potrebbe avere problemi come l'impossibilità di promuovere una sessione P2P a una riunione quando è coinvolto un endpoint PSTN.</span><span class="sxs-lookup"><span data-stu-id="b2b46-112">Since the large meeting setting is optimized for performance, using it as a normal user could have problems such as the inability to promote a P2P session to a meeting when a PSTN endpoint is involved.</span></span>

<span data-ttu-id="b2b46-113">La gestione di un pool con esattamente due server Front End richiede alcune considerazioni speciali.</span><span class="sxs-lookup"><span data-stu-id="b2b46-113">Managing a pool with exactly two Front End Servers requires some special considerations.</span></span> <span data-ttu-id="b2b46-114">Per ulteriori informazioni, vedere [topologie e componenti per Front End Server, messaggistica istantanea e presenza in Lync server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="b2b46-114">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="b2b46-115">Inoltre, se si desidera fornire facoltativamente il backup e il failover del ripristino di emergenza per il pool utilizzato per le riunioni di grandi dimensioni, è possibile associarlo a un pool di dati di installazione analogo, in un data center diverso.</span><span class="sxs-lookup"><span data-stu-id="b2b46-115">Additionally, if you want to optionally provide disaster recovery backup and failover for the pool used for large meetings, you can pair it with a similarly set up dedicated pool in a different data center.</span></span> <span data-ttu-id="b2b46-116">Per informazioni dettagliate, vedere [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="b2b46-116">For details, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<span data-ttu-id="b2b46-117">![Configurazione del pool di riunioni di grandi dimensioni](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Configurazione del pool di riunioni di grandi dimensioni")</span><span class="sxs-lookup"><span data-stu-id="b2b46-117">![Large Meetings pool configuration](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Large Meetings pool configuration")</span></span>

<span data-ttu-id="b2b46-118">Note aggiuntive sulla topologia:</span><span class="sxs-lookup"><span data-stu-id="b2b46-118">Additional notes about the topology include:</span></span>

  - <span data-ttu-id="b2b46-119">È necessaria una condivisione file per l'archiviazione del contenuto delle riunioni e, se il server di archiviazione è distribuito e abilitato, per l'archiviazione dei file di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b2b46-119">A file share is required for storing meeting content and, if Archiving Server is deployed and enabled, for storing the archiving files.</span></span> <span data-ttu-id="b2b46-120">La condivisione di file può essere dedicata al pool oppure corrispondere a quella usata da un altro pool nello stesso sito di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b2b46-120">The file share can be dedicated to the pool or can be the same file share used by another pool at the site in which the pool is deployed.</span></span> <span data-ttu-id="b2b46-121">Per informazioni dettagliate sulla configurazione della condivisione file, vedere [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span><span class="sxs-lookup"><span data-stu-id="b2b46-121">For details about configuring the file share, see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>

  - <span data-ttu-id="b2b46-122">È necessario un server Office Web Apps per abilitare la funzionalità di presentazione di PowerPoint nelle riunioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="b2b46-122">A Office Web Apps Server is required for enabling the PowerPoint presentation functionality in large meetings.</span></span> <span data-ttu-id="b2b46-123">Il server Office Web Apps può essere dedicato al pool di riunioni di grandi dimensioni oppure può essere lo stesso server Office Web Apps utilizzato da altri pool nel sito in cui è distribuito il pool dedicato.</span><span class="sxs-lookup"><span data-stu-id="b2b46-123">The Office Web Apps Server can be dedicated to the large meeting pool or, it can be the same Office Web Apps Server used by other pools at the site in which the dedicated pool is deployed.</span></span>

  - <span data-ttu-id="b2b46-124">Il bilanciamento del carico dei Front End Server richiede il bilanciamento del carico hardware per il traffico HTTP (ad esempio, il download del contenuto della riunione).</span><span class="sxs-lookup"><span data-stu-id="b2b46-124">Load balancing of the Front End Servers requires hardware load balancing for the HTTP traffic (such as meeting content download).</span></span> <span data-ttu-id="b2b46-125">Per il traffico SIP è consigliato il bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="b2b46-125">DNS load balancing is recommended for SIP traffic.</span></span> <span data-ttu-id="b2b46-126">Per informazioni dettagliate, vedere [requisiti per il bilanciamento del carico per Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2b46-126">For details see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="b2b46-127">Se si desidera utilizzare il Monitoring Server per il pool di riunioni di grandi dimensioni dedicato, è consigliabile utilizzare il Monitoring Server e il relativo database condiviso in tutti i pool Front End Server della distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b2b46-127">If you want to use Monitoring Server for the dedicated large-meeting pool, we recommend using the Monitoring Server and its database that are shared across all of the Front End Server pools in your Lync Server deployment.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements"></a><span data-ttu-id="b2b46-128">Requisiti hardware e software</span><span class="sxs-lookup"><span data-stu-id="b2b46-128">Hardware and Software Requirements</span></span>

<span data-ttu-id="b2b46-129">I requisiti hardware per i server in un pool di riunioni di grandi dimensioni dedicato sono uguali a quelli degli altri server Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2b46-129">The hardware requirements for servers in a dedicated large-meeting pool are the same as for your other Lync Server 2013 servers.</span></span> <span data-ttu-id="b2b46-130">Per informazioni dettagliate sui requisiti hardware, vedere "[piattaforme hardware server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="b2b46-130">For details about hardware requirements, see "[Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="b2b46-131">I server in un pool di riunioni di grandi dimensioni dedicato devono soddisfare tutti i requisiti software di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2b46-131">Servers in a dedicated large-meeting pool must meet all Lync Server 2013 software requirements.</span></span> <span data-ttu-id="b2b46-132">Per informazioni dettagliate sui requisiti software, vedere la documentazione seguente:</span><span class="sxs-lookup"><span data-stu-id="b2b46-132">For details about software requirements, please see the following documentation:</span></span>

  - [<span data-ttu-id="b2b46-133">Supporto del sistema operativo per server e strumenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2b46-133">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="b2b46-134">Supporto software per database in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2b46-134">Database software support in Lync Server 2013</span></span>](lync-server-2013-database-software-support.md)

  - [<span data-ttu-id="b2b46-135">Requisiti software aggiuntivi per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2b46-135">Additional software requirements for Lync Server 2013</span></span>](lync-server-2013-additional-software-requirements.md)

<span data-ttu-id="b2b46-136">Inoltre, sia Lync Server 2013 sia tutti i client di Lync Server 2013 devono avere gli aggiornamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="b2b46-136">Additionally, both Lync Server 2013 and all Lync Server 2013 clients must have the latest updates.</span></span>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="b2b46-137">Requisiti di configurazione</span><span class="sxs-lookup"><span data-stu-id="b2b46-137">Configuration Requirements</span></span>

<span data-ttu-id="b2b46-p110">È consigliabile creare un nuovo criteri di conferenza specifico per le riunioni di grandi dimensioni e quindi assegnare il criterio di conferenza agli utenti ospitati in un pool dedicato a riunioni di grandi dimensioni. Configurare il criterio per conferenze con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b2b46-p110">We recommend creating a new conferencing policy specifically for large meetings, and then assigning the conferencing policy to the users who are homed on the dedicated large-meeting pool. Configure the conferencing policy using the following settings:</span></span>

  - <span data-ttu-id="b2b46-p111">Impostare l'opzione **MaxMeetingSize** su **1000**. Il valore predefinito è **250**.</span><span class="sxs-lookup"><span data-stu-id="b2b46-p111">Set the **MaxMeetingSize** option to **1000**. (The default is **250**.)</span></span>

  - <span data-ttu-id="b2b46-142">Impostare l'opzione **AllowLargeMeetings** su **True**.</span><span class="sxs-lookup"><span data-stu-id="b2b46-142">Set the **AllowLargeMeetings** option to **True**.</span></span>

  - <span data-ttu-id="b2b46-143">Impostare l'opzione **EnableAppDesktopSharing** su **None**.</span><span class="sxs-lookup"><span data-stu-id="b2b46-143">Set the **EnableAppDesktopSharing** option to **None**.</span></span>

  - <span data-ttu-id="b2b46-144">Impostare l'opzione **AllowUserToScheduleMeetingsWithAppSharing** su **False**.</span><span class="sxs-lookup"><span data-stu-id="b2b46-144">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>

  - <span data-ttu-id="b2b46-145">Impostare l'opzione **AllowSharedNotes** su **False**.</span><span class="sxs-lookup"><span data-stu-id="b2b46-145">Set the **AllowSharedNotes** option to **False**.</span></span>

  - <span data-ttu-id="b2b46-146">Impostare l'opzione **AllowAnnotations** su **False**.</span><span class="sxs-lookup"><span data-stu-id="b2b46-146">Set the **AllowAnnotations** option to **False**.</span></span>

  - <span data-ttu-id="b2b46-147">Impostare l'opzione **DisablePowerPointAnnotations** su **True**.</span><span class="sxs-lookup"><span data-stu-id="b2b46-147">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>

  - <span data-ttu-id="b2b46-148">Impostare l'opzione **AllowMultiview** su **False**.</span><span class="sxs-lookup"><span data-stu-id="b2b46-148">Set the **AllowMultiview** option to **False**.</span></span>

  - <span data-ttu-id="b2b46-149">Impostare l'opzione **EnableMultiviewJoin** su **False**.</span><span class="sxs-lookup"><span data-stu-id="b2b46-149">Set the **EnableMultiviewJoin** option to **False**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b2b46-150">Il supporto per le riunioni di grandi dimensioni dell'utente 1000 in Lync Server 2013 richiede che l'impostazione <STRONG>AllowLargeMeetings</STRONG> nei criteri di conferenza per l'utilità di pianificazione riunione sia impostata su true.</span><span class="sxs-lookup"><span data-stu-id="b2b46-150">The support for 1000 user large meetings in Lync Server 2013 requires the <STRONG>AllowLargeMeetings</STRONG> setting in the conferencing policy for the meeting scheduler to be set to true.</span></span> <span data-ttu-id="b2b46-151">Quando questa impostazione è impostata su true, l'esperienza di Lync sarà ottimizzata per riunioni di grandi dimensioni quando gli utenti partecipano a tale riunione.</span><span class="sxs-lookup"><span data-stu-id="b2b46-151">When this setting is set to true, the Lync experience will be optimized for extra large meetings when users joins such meeting.</span></span> <span data-ttu-id="b2b46-152">In particolare, in una riunione di grandi dimensioni, Lync non mostrerà l'iniziale o l'aggiornamento dell'elenco dei partecipanti alla riunione completo, che è un collo di bottiglia delle prestazioni sia per il client che per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2b46-152">Specifically, in a large meeting, Lync will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Lync Server 2013.</span></span> <span data-ttu-id="b2b46-153">Lync, invece, visualizzerà solo le informazioni sull'utente e l'elenco dei relatori della riunione.</span><span class="sxs-lookup"><span data-stu-id="b2b46-153">Instead, Lync will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="b2b46-154">Lync continuerà a visualizzare correttamente il numero totale di partecipanti disponibili nelle riunioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="b2b46-154">Lync will still properly shows total number of participants available in the large meetings.</span></span>



</div>

<span data-ttu-id="b2b46-155">Ad eccezione dell'impostazione **Dimensione massima riunione**, tutti gli altri criteri di conferenza specificati qui sono necessari per disabilitare le funzionalità di conferenza non necessarie in riunioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="b2b46-155">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>

<span data-ttu-id="b2b46-156">Inoltre, è necessario configurare il pool di riunioni di grandi dimensioni dedicato in modo che ogni utente di Lync Server 2013 che è ospitato nel pool e responsabile della gestione della pianificazione delle riunioni disponga delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="b2b46-156">Additionally, you need to configure the dedicated large-meeting pool so that each Lync Server 2013 user that is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="b2b46-157">A tale scopo, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="b2b46-157">To do this, do the following:</span></span>

  - <span data-ttu-id="b2b46-p114">Impostare l'opzione **Designa come relatore** a **Nessuno**. In genere, uno o pochi altri utenti tra tutti i partecipanti a una riunione di grandi dimensioni sono relatori, pertanto i partecipanti non devono essere automaticamente ammessi a riunioni di grandi dimensioni come relatori. I relatori dovrebbero invece essere designati in modo esplicito al momento di pianificare la riunione oppure durante la riunione stessa.</span><span class="sxs-lookup"><span data-stu-id="b2b46-p114">Set the **Designate as presenter** option to **None**. Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters. Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>

  - <span data-ttu-id="b2b46-161">Accertarsi che la casella di controllo **Tipo di conferenza assegnato per impostazione predefinita** non sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="b2b46-161">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="b2b46-162">Questa impostazione consente di controllare se il componente aggiuntivo per riunioni online per Lync 2013 Pianifica sempre le conferenze utilizzando la conferenza assegnata dall'organizzatore, il che significa che le riunioni pianificate hanno lo stesso URL di join e le informazioni audio.</span><span class="sxs-lookup"><span data-stu-id="b2b46-162">This setting controls whether the Online Meeting Add-in for Lync 2013 always schedules conferences using the organizer’s assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="b2b46-163">In scenari di collaborazione di piccoli gruppi, l'assegnazione di un tipo di conferenza funziona bene perché ognuno dispone di una conferenza individuale assegnata e l'URL di accesso e le informazioni audio consentono di agevolare un più rapido accesso alla riunione.</span><span class="sxs-lookup"><span data-stu-id="b2b46-163">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="b2b46-164">Tuttavia, in scenari con riunioni di grandi dimensioni, il personale di queste ultime pianifica le riunioni più grandi con un singolo set di credenziali utente, e quindi offre URL di accesso e informazioni sull'audio al richiedente il meeting.</span><span class="sxs-lookup"><span data-stu-id="b2b46-164">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="b2b46-165">In questo caso, l'uso di un URL diverso per accedere a ogni riunione funziona bene.</span><span class="sxs-lookup"><span data-stu-id="b2b46-165">In this case, using a different URL to join each meeting works better.</span></span>

  - <span data-ttu-id="b2b46-166">Accettarsi che la casella di controllo **Consenti utenti anonimi per impostazione predefinita** non è selezionata a meno che non sia necessario.</span><span class="sxs-lookup"><span data-stu-id="b2b46-166">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="b2b46-167">Questa impostazione influisce sul tipo di accesso alle riunioni predefinito programmato dal componente aggiuntivo per riunioni online per Lync 2013 quando non si utilizza una conferenza assegnata.</span><span class="sxs-lookup"><span data-stu-id="b2b46-167">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Lync 2013 when not using an assigned conference.</span></span> <span data-ttu-id="b2b46-168">L'opzione appropriata per questa impostazione dipende dalle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2b46-168">The appropriate option for this setting depends on your organization’s needs.</span></span> <span data-ttu-id="b2b46-169">Se la maggior parte delle riunioni di grandi dimensioni nell'organizzazione è interna, non selezionare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="b2b46-169">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="b2b46-170">Se per la maggior parte delle riunioni di grandi dimensioni è prevista la partecipazione di  utenti esterni, selezionare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="b2b46-170">If most large meetings require that external users be able to join, select this option.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

