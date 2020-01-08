---
title: 'Lync Server 2013: considerazioni sulla migrazione per le riunioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67816dd8f2b9d8be3862994c735040c703bd2231
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a><span data-ttu-id="87908-102">Considerazioni sulla migrazione per le riunioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87908-102">Migration considerations for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87908-103">_**Argomento Ultima modifica:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="87908-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="87908-104">In questa sezione sono illustrati gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="87908-104">The following topics are discussed in this section:</span></span>

  - <span data-ttu-id="87908-105">Modifiche alle riunioni in Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87908-105">Changes to meetings in Microsoft Lync Server 2013</span></span>

  - <span data-ttu-id="87908-106">Migrazione degli utenti in base alle esigenze di conferenza</span><span class="sxs-lookup"><span data-stu-id="87908-106">Migrating users based on their conferencing needs</span></span>

  - <span data-ttu-id="87908-107">Migrazione di riunioni e contenuto delle riunioni esistenti</span><span class="sxs-lookup"><span data-stu-id="87908-107">Migrating existing meetings and meeting content</span></span>

  - <span data-ttu-id="87908-108">Esperienza utente durante la migrazione a Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="87908-108">User experience during Lync Server 2010 migration</span></span>

  - <span data-ttu-id="87908-109">Esperienza utente durante la migrazione a Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="87908-109">User Experience during Office Communications Server 2007 R2 migration</span></span>

  - <span data-ttu-id="87908-110">Compatibilità di Microsoft Lync 2013 con le riunioni nelle versioni precedenti del server</span><span class="sxs-lookup"><span data-stu-id="87908-110">Microsoft Lync 2013 compatibility with meetings on earlier server versions</span></span>

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a><span data-ttu-id="87908-111">Modifiche alle riunioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87908-111">Changes to Meetings in Lync Server 2013</span></span>

<span data-ttu-id="87908-112">**Caratteristiche di Lync Server 2013.**    Lync Server 2013 offre nuove caratteristiche di conferenza che diventano disponibili agli utenti dopo lo spostamento degli account in lync Server 2013 e l'accesso con il client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="87908-112">**Lync Server 2013 features.**   Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="87908-113">Le nuove caratteristiche sono descritte in [nuove caratteristiche di conferenza in Lync server 2013](lync-server-2013-new-conferencing-features.md) e [novità per i client in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="87908-113">New features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="87908-114">**URL della riunione.**    Come in lync Server 2010, tutte le riunioni pianificate di recente in lync Server 2013 hanno un prefisso URL di https://e le riunioni esistenti migrano insieme agli account utente.</span><span class="sxs-lookup"><span data-stu-id="87908-114">**Meeting URL.**   As in Lync Server 2010, all newly scheduled meetings in Lync Server 2013 have a URL prefix of https:// and existing meetings migrate along with user accounts.</span></span> <span data-ttu-id="87908-115">Lync Server 2013 non supporta tuttavia la conferenza telefonica di Office Communications Server 2007 R2 (conf://URL prefix) o Web Conference (prefisso URL meet://).</span><span class="sxs-lookup"><span data-stu-id="87908-115">However, Lync Server 2013 does not support the Office Communications Server 2007 R2 conference call (conf:// URL prefix) or web conference (meet:// URL prefix).</span></span> <span data-ttu-id="87908-116">Per altre informazioni, vedere "migrazione delle riunioni da Office Communications Server 2007 R2" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="87908-116">See “Migrating Meetings from Office Communications Server 2007 R2” later in this topic for more information.</span></span>

<span data-ttu-id="87908-117">**Supporto client.**    A differenza di lync Server 2010, lync Server 2013 non supporta i client di Office Communicator per le conferenze.</span><span class="sxs-lookup"><span data-stu-id="87908-117">**Client support.**   Unlike Lync Server 2010, Lync Server 2013 does not support Office Communicator clients for conferencing.</span></span> <span data-ttu-id="87908-118">Non è possibile usare i client seguenti per partecipare alle riunioni pianificate tramite il componente aggiuntivo riunione online per Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="87908-118">You cannot use the following clients to join meetings scheduled through the Online Meeting Add-in for Lync 2013:</span></span>

  - <span data-ttu-id="87908-119">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="87908-119">Office Communicator 2007 R2</span></span>

  - <span data-ttu-id="87908-120">Assistente di Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="87908-120">Microsoft Office Communications Server 2007 R2 Attendant</span></span>

  - <span data-ttu-id="87908-121">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="87908-121">Office Communicator 2007</span></span>

  - <span data-ttu-id="87908-122">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="87908-122">Office Live Meeting 2007</span></span>

<span data-ttu-id="87908-123">Durante la migrazione, gli utenti di Office Communicator 2007 R2 devono usare Lync Web App 2013 per partecipare alle riunioni di Lync Server 2013 finché i client non vengono aggiornati.</span><span class="sxs-lookup"><span data-stu-id="87908-123">During migration, Office Communicator 2007 R2 users should use Lync Web App 2013 to join Lync Server 2013 meetings until their clients are upgraded.</span></span> <span data-ttu-id="87908-124">Tieni presente che gli utenti di Office Communicator 2007 R2 possono continuare a usare il client esistente in Lync Server 2013 per le funzionalità di presenza e messaggistica istantanea, ma le funzionalità di conferenza non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="87908-124">Note that Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a><span data-ttu-id="87908-125">Migrazione degli utenti in base alle esigenze di conferenza</span><span class="sxs-lookup"><span data-stu-id="87908-125">Migrating Users Based on Their Conferencing Needs</span></span>

<span data-ttu-id="87908-126">**Frequenti organizzatori della riunione.**    È consigliabile eseguire la migrazione delle riunioni frequenti degli organizzatori della riunione in modo che possano sfruttare le nuove funzionalità di lync Server 2013 e Lync 2013 descritte in [nuove funzionalità di conferenza in Lync Server 2013](lync-server-2013-new-conferencing-features.md) e [novità per i client in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="87908-126">**Frequent meeting organizers.**   Consider migrating frequent meeting organizers early in the process so that they can take advantage of the new Lync Server 2013 and Lync 2013 features outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="87908-127">**Utenti di Live Meeting.**    Se si esegue la migrazione da Office Communications Server 2007 R2 e si hanno gli utenti che hanno bisogno di funzionalità di conferenza Web specifiche per Live Meeting, in particolare il supporto per riunioni di grandi dimensioni e camere di break-out, sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="87908-127">**Live Meeting users.**   If you are migrating from Office Communications Server 2007 R2 and you have users who need web conferencing features specific to Live Meeting—particularly support for large meetings and break-out rooms—you have the following options:</span></span>

  - <span data-ttu-id="87908-128">Consigliare agli organizzatori di usare il servizio Live Meeting, se disponibile nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="87908-128">Advise organizers to use the Live Meeting service, if available in your organization.</span></span>

  - <span data-ttu-id="87908-129">Abbandonare gli organizzatori nella versione precedente di Office Communications Server, in modo che possano continuare a pianificare conferenze Web Live Meeting basate sul server.</span><span class="sxs-lookup"><span data-stu-id="87908-129">Leave the organizers homed on the earlier version of Office Communications Server, so they can continue to schedule server-based Live Meeting web conferences.</span></span>

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a><span data-ttu-id="87908-130">Migrazione di riunioni e contenuto delle riunioni esistenti</span><span class="sxs-lookup"><span data-stu-id="87908-130">Migrating Existing Meetings and Meeting Content</span></span>

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a><span data-ttu-id="87908-131">Migrazione di riunioni da Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="87908-131">Migrating Meetings from Lync Server 2010</span></span>

<span data-ttu-id="87908-132">Quando si sposta un utente da Lync Server 2010 a Lync Server 2013, le informazioni seguenti si spostano con l'account dell'utente:</span><span class="sxs-lookup"><span data-stu-id="87908-132">When you move a user from Lync Server 2010 to Lync Server 2013, the following information moves with the user’s account:</span></span>

  - <span data-ttu-id="87908-133">Riunioni già programmate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="87908-133">Meetings already scheduled by the user.</span></span> <span data-ttu-id="87908-134">Sono incluse le Conferencing Directories e i dati di conferenza.</span><span class="sxs-lookup"><span data-stu-id="87908-134">This includes conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="87908-135">PIN (Personal Identification Number) dell'utente.</span><span class="sxs-lookup"><span data-stu-id="87908-135">The user’s personal identification number (PIN).</span></span> <span data-ttu-id="87908-136">Il PIN corrente dell'utente continuerà a funzionare finché non scade o l'utente richiede un nuovo PIN.</span><span class="sxs-lookup"><span data-stu-id="87908-136">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="87908-137">Le informazioni dell'account utente seguenti, tuttavia, non vengono spostati nel nuovo server:</span><span class="sxs-lookup"><span data-stu-id="87908-137">However, the following user account information does not move to the new server:</span></span>

  - <span data-ttu-id="87908-138">Contenuto della riunione, ad esempio presentazioni di PowerPoint, contenuto della lavagna e dati del sondaggio</span><span class="sxs-lookup"><span data-stu-id="87908-138">Meeting content, for example PowerPoint presentations, whiteboard content, and poll data</span></span>

<span data-ttu-id="87908-139">Per trasferire il contenuto condiviso in riunioni, usa il parametro MoveMeetingContent del cmdlet Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="87908-139">To move the content that has been shared in meetings, use the MoveMeetingContent parameter of the Move-CsUser cmdlet.</span></span> <span data-ttu-id="87908-140">Per informazioni dettagliate sull'uso di questo cmdlet, vedere [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) nella documentazione dei cmdlet di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="87908-140">For details about using this cmdlet, see [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) in the Lync Server 2013 cmdlets documentation.</span></span>

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a><span data-ttu-id="87908-141">Migrazione di riunioni da Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="87908-141">Migrating Meetings from Office Communications Server 2007 R2</span></span>

<span data-ttu-id="87908-142">Le riunioni di Office Communications Server 2007 R2 sono chiamate conferenza (prefisso URL conf://) o conferenze Web (prefisso URL meet://).</span><span class="sxs-lookup"><span data-stu-id="87908-142">Office Communications Server 2007 R2 meetings are either conference calls (conf:// URL prefix) or web conferences (meet:// URL prefix).</span></span> <span data-ttu-id="87908-143">Lync Server 2013 non supporta queste conferenze precedenti di conf://e meet://e non vengono migrate insieme all'account utente.</span><span class="sxs-lookup"><span data-stu-id="87908-143">Lync Server 2013 does not support these earlier conf:// and meet:// conferences, and they are not migrated along with the user account.</span></span> <span data-ttu-id="87908-144">Dopo la migrazione, è consigliabile indicare agli utenti di aggiornare i collegamenti per tutte le riunioni online che hanno programmato.</span><span class="sxs-lookup"><span data-stu-id="87908-144">After migration, you should instruct users to update the links for any online meetings they have scheduled.</span></span> <span data-ttu-id="87908-145">Questa operazione può essere eseguita dopo l'installazione del client Lync 2013 aprendo un invito a una riunione pianificata, che aggiorna l'URL della riunione, e invia nuovamente l'invito ai partecipanti.</span><span class="sxs-lookup"><span data-stu-id="87908-145">They can do this after installing the Lync 2013 client by opening a scheduled meeting invitation—which updates the meeting URL—and resending the invitation to participants.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a><span data-ttu-id="87908-146">Esperienza utente durante la migrazione a Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="87908-146">User Experience during Lync Server 2010 Migration</span></span>

<span data-ttu-id="87908-147">Questa sezione fornisce un riepilogo dell'esperienza di conferenza degli utenti quando si esegue la migrazione da Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="87908-147">This section provides a summary of users’ conferencing experience when migrating from Lync 2010.</span></span> <span data-ttu-id="87908-148">Per altre informazioni sul modo in cui i client di Lync Server 2013 possono coesistere e interagire con le versioni precedenti del client e del server, vedere [interoperabilità client in lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="87908-148">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a><span data-ttu-id="87908-149">Partecipare a riunioni di Lync Server 2010 con un client Lync 2013</span><span class="sxs-lookup"><span data-stu-id="87908-149">Joining Lync Server 2010 Meetings with a Lync 2013 Client</span></span>

<span data-ttu-id="87908-150">Durante la migrazione da Lync Server 2010 può esistere un periodo di coesistenza quando gli utenti partecipano a riunioni Lync Server 2010 con un client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="87908-150">During migration from Lync Server 2010, there may be a period of coexistence when users join Lync Server 2010 meetings with a Lync 2013 client.</span></span> <span data-ttu-id="87908-151">Questi utenti possono accedere alle funzionalità client di Lync 2013 con le eccezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="87908-151">These users have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="87908-152">Nelle opzioni di gestione dei **partecipanti** , che sono accessibili puntando l'icona persone nella finestra della riunione, l'opzione **Nessuna messaggistica istantanea** non funziona.</span><span class="sxs-lookup"><span data-stu-id="87908-152">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="87908-153">La visualizzazione raccolta non funziona nelle conferenze video.</span><span class="sxs-lookup"><span data-stu-id="87908-153">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="87908-154">L'utente vede solo l'altoparlante attivo invece di tutti gli altoparlanti.</span><span class="sxs-lookup"><span data-stu-id="87908-154">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="87908-155">Nell'elenco delle opzioni **Scegli un layout** la **visualizzazione raccolta** non è disponibile</span><span class="sxs-lookup"><span data-stu-id="87908-155">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="87908-156">L'elenco dei partecipanti viene visualizzato per impostazione predefinita nelle videoconferenze.</span><span class="sxs-lookup"><span data-stu-id="87908-156">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="87908-157">Quando si fa clic con il pulsante destro del mouse su un utente nell'elenco dei partecipanti, le opzioni **di** gestione del **riflettore e del PIN delle** raccolte sono non disponibili.</span><span class="sxs-lookup"><span data-stu-id="87908-157">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a><span data-ttu-id="87908-158">Esperienza utente durante la migrazione a Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="87908-158">User Experience during Office Communications Server 2007 R2 Migration</span></span>

<span data-ttu-id="87908-159">Questa sezione fornisce un riepilogo dell'esperienza di conferenza degli utenti quando si esegue la migrazione da Office Communications Server 2007 R2, sia prima che dopo l'installazione di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="87908-159">This section provides a summary of users’ conferencing experience when migrating from Office Communications Server 2007 R2, both before and after Lync 2013 is installed.</span></span> <span data-ttu-id="87908-160">Per altre informazioni sul modo in cui i client di Lync Server 2013 possono coesistere e interagire con le versioni precedenti del client e del server, vedere [interoperabilità client in lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="87908-160">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a><span data-ttu-id="87908-161">Dopo la migrazione dell'account utente, prima dell'installazione di Lync 2013</span><span class="sxs-lookup"><span data-stu-id="87908-161">After User Account is Migrated, Before Lync 2013 Is Installed</span></span>

<span data-ttu-id="87908-162">Dopo la migrazione di un utente al server Lync Server 2013, ma prima dell'installazione di nuovi client, gli utenti di Office Communicator 2007 R2 possono continuare a usare il client esistente in Lync Server 2013 per le funzionalità di presenza e messaggistica istantanea, ma le funzionalità di conferenza non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="87908-162">After a user is migrated to the Lync Server 2013 server, but before new clients are installed, Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a><span data-ttu-id="87908-163">Dopo la migrazione dell'account utente, dopo l'installazione di Lync 2013</span><span class="sxs-lookup"><span data-stu-id="87908-163">After User Account is Migrated, After Lync 2013 Is Installed</span></span>

<span data-ttu-id="87908-164">Quando un utente migrato installa Lync 2013, viene installato anche il componente aggiuntivo riunione online per Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="87908-164">When a migrated user installs Lync 2013, the Online Meeting Add-in for Lync 2013 is installed too.</span></span> <span data-ttu-id="87908-165">Gli effetti sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="87908-165">This has the following effects:</span></span>

  - <span data-ttu-id="87908-166">Tutte le riunioni pianificate in seguito usano il nuovo formato della riunione, che usa un indirizzo https://anziché l'indirizzo di riunione Live di meet://Legacy.</span><span class="sxs-lookup"><span data-stu-id="87908-166">All subsequently scheduled meetings use the new meeting format, which uses an https:// address instead of the legacy meet:// Live Meeting address.</span></span>

  - <span data-ttu-id="87908-167">In una distribuzione gestita da IT di Lync 2013, l'amministratore ha la possibilità di disinstallare il componente aggiuntivo per le conferenze per Microsoft Office Outlook, usato per pianificare riunioni Live Meeting Server e basate su servizi.</span><span class="sxs-lookup"><span data-stu-id="87908-167">In an IT-managed deployment of Lync 2013, the administrator has the option of uninstalling the Conferencing Add-in for Microsoft Office Outlook, which is used to schedule Live Meeting server and service-based meetings.</span></span> <span data-ttu-id="87908-168">Potrebbe tuttavia essere necessario che gli utenti continuino a pianificare le riunioni del servizio Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="87908-168">However, you may have users who need to continue to schedule Live Meeting service meetings.</span></span> <span data-ttu-id="87908-169">In questo caso, puoi consentire a entrambi i componenti aggiuntivi di coesistere.</span><span class="sxs-lookup"><span data-stu-id="87908-169">In this case, you can allow both add-ins to coexist.</span></span>

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a><span data-ttu-id="87908-170">Riunioni con organizzazioni federate che usano client precedenti</span><span class="sxs-lookup"><span data-stu-id="87908-170">Meetings with Federated Organizations that Use Previous Clients</span></span>

<span data-ttu-id="87908-171">Gli utenti delle organizzazioni federate che usano Microsoft Office Communicator 2007 non possono partecipare alle riunioni di Lync Server 2013 nell'organizzazione se tali riunioni sono bloccate dall'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="87908-171">Users in federated organizations who are using Microsoft Office Communicator 2007 cannot join Lync Server 2013 meetings in your organization if those meetings are locked by the organizer.</span></span> <span data-ttu-id="87908-172">È necessario ripianificare queste riunioni in Lync Server 2013 in modo che quando i partecipanti federati partecipano alla riunione usando il nuovo URL della riunione https://, possono usare Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="87908-172">You have to reschedule these meetings in Lync Server 2013 so when federated participants join the meeting by using the new https:// meeting URL, they can use Lync Web App.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

