---
title: 'Lync Server 2013: considerazioni sulla migrazione per le riunioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ec650c62b26775aeddf9f01ff8d455a6f6a7667
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a><span data-ttu-id="dfe13-102">Considerazioni sulla migrazione per le riunioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfe13-102">Migration considerations for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfe13-103">_**Ultimo argomento modificato:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="dfe13-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="dfe13-104">In questa sezione sono trattati gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="dfe13-104">The following topics are discussed in this section:</span></span>

  - <span data-ttu-id="dfe13-105">Modifiche apportate alle riunioni in Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfe13-105">Changes to meetings in Microsoft Lync Server 2013</span></span>

  - <span data-ttu-id="dfe13-106">Migrazione degli utenti in base alle esigenze per le conferenze</span><span class="sxs-lookup"><span data-stu-id="dfe13-106">Migrating users based on their conferencing needs</span></span>

  - <span data-ttu-id="dfe13-107">Migrazione di riunioni esistenti e del contenuto delle riunioni</span><span class="sxs-lookup"><span data-stu-id="dfe13-107">Migrating existing meetings and meeting content</span></span>

  - <span data-ttu-id="dfe13-108">Esperienza utente durante la migrazione di Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="dfe13-108">User experience during Lync Server 2010 migration</span></span>

  - <span data-ttu-id="dfe13-109">Esperienza utente durante la migrazione di Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="dfe13-109">User Experience during Office Communications Server 2007 R2 migration</span></span>

  - <span data-ttu-id="dfe13-110">Compatibilità di Microsoft Lync 2013 con riunioni nelle versioni precedenti del server</span><span class="sxs-lookup"><span data-stu-id="dfe13-110">Microsoft Lync 2013 compatibility with meetings on earlier server versions</span></span>

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a><span data-ttu-id="dfe13-111">Modifiche apportate alle riunioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfe13-111">Changes to Meetings in Lync Server 2013</span></span>

<span data-ttu-id="dfe13-112">**Funzionalità di Lync Server 2013.**    Lync Server 2013 fornisce nuove funzionalità di conferenza che diventano disponibili per gli utenti dopo lo spostamento degli account in lync Server 2013 ed eseguono l'accesso con il client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="dfe13-112">**Lync Server 2013 features.**   Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="dfe13-113">Le nuove funzionalità sono descritte in [nuove funzionalità di conferenza in Lync server 2013](lync-server-2013-new-conferencing-features.md) e [novità per i client in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="dfe13-113">New features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="dfe13-114">**URL riunione.**    Come in lync Server 2010, tutte le riunioni pianificate di recente in lync Server 2013 dispongono di un prefisso URL di https://e le riunioni esistenti vengono migrate insieme agli account utente.</span><span class="sxs-lookup"><span data-stu-id="dfe13-114">**Meeting URL.**   As in Lync Server 2010, all newly scheduled meetings in Lync Server 2013 have a URL prefix of https:// and existing meetings migrate along with user accounts.</span></span> <span data-ttu-id="dfe13-115">Tuttavia, Lync Server 2013 non supporta la chiamata di conferenza di Office Communications Server 2007 R2 (prefisso URL conf://) o la conferenza Web (prefisso URL meet://).</span><span class="sxs-lookup"><span data-stu-id="dfe13-115">However, Lync Server 2013 does not support the Office Communications Server 2007 R2 conference call (conf:// URL prefix) or web conference (meet:// URL prefix).</span></span> <span data-ttu-id="dfe13-116">Per ulteriori informazioni, vedere la sezione relativa alla migrazione di riunioni da Office Communications Server 2007 R2 più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="dfe13-116">See “Migrating Meetings from Office Communications Server 2007 R2” later in this topic for more information.</span></span>

<span data-ttu-id="dfe13-117">**Supporto client.**    A differenza di lync Server 2010, lync Server 2013 non supporta i client Office Communicator per le conferenze.</span><span class="sxs-lookup"><span data-stu-id="dfe13-117">**Client support.**   Unlike Lync Server 2010, Lync Server 2013 does not support Office Communicator clients for conferencing.</span></span> <span data-ttu-id="dfe13-118">Non è possibile utilizzare i client seguenti per partecipare a riunioni pianificate tramite il componente aggiuntivo per riunioni online per Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="dfe13-118">You cannot use the following clients to join meetings scheduled through the Online Meeting Add-in for Lync 2013:</span></span>

  - <span data-ttu-id="dfe13-119">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="dfe13-119">Office Communicator 2007 R2</span></span>

  - <span data-ttu-id="dfe13-120">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="dfe13-120">Microsoft Office Communications Server 2007 R2 Attendant</span></span>

  - <span data-ttu-id="dfe13-121">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="dfe13-121">Office Communicator 2007</span></span>

  - <span data-ttu-id="dfe13-122">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="dfe13-122">Office Live Meeting 2007</span></span>

<span data-ttu-id="dfe13-123">Durante la migrazione, gli utenti di Office Communicator 2007 R2 devono utilizzare Lync Web App 2013 per partecipare alle riunioni di Lync Server 2013 fino a quando non vengono aggiornati i client.</span><span class="sxs-lookup"><span data-stu-id="dfe13-123">During migration, Office Communicator 2007 R2 users should use Lync Web App 2013 to join Lync Server 2013 meetings until their clients are upgraded.</span></span> <span data-ttu-id="dfe13-124">Gli utenti di Office Communicator 2007 R2 possono continuare a utilizzare il client esistente con Lync Server 2013 per le funzionalità di messaggistica istantanea e presenza, ma le funzionalità di conferenza non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="dfe13-124">Note that Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a><span data-ttu-id="dfe13-125">Migrazione degli utenti in base alle esigenze per le conferenze</span><span class="sxs-lookup"><span data-stu-id="dfe13-125">Migrating Users Based on Their Conferencing Needs</span></span>

<span data-ttu-id="dfe13-126">**Organizzatori di riunioni frequenti.**    È consigliabile eseguire la migrazione degli organizzatori di riunioni frequenti all'inizio del processo, in modo che possano usufruire delle nuove funzionalità di lync Server 2013 e Lync 2013 descritte in [nuove funzionalità di conferenza in Lync Server 2013](lync-server-2013-new-conferencing-features.md) e [novità per i client in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="dfe13-126">**Frequent meeting organizers.**   Consider migrating frequent meeting organizers early in the process so that they can take advantage of the new Lync Server 2013 and Lync 2013 features outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="dfe13-127">**Utenti di Live Meeting.**    Se si esegue la migrazione da Office Communications Server 2007 R2 e si dispone di utenti che necessitano di funzionalità di Web Conferencing specifiche per Live Meeting, in particolare il supporto per riunioni di grandi dimensioni e le sale di disattivazione, sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dfe13-127">**Live Meeting users.**   If you are migrating from Office Communications Server 2007 R2 and you have users who need web conferencing features specific to Live Meeting—particularly support for large meetings and break-out rooms—you have the following options:</span></span>

  - <span data-ttu-id="dfe13-128">Consigliare agli organizzatori di utilizzare il servizio Live Meeting, se disponibile nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dfe13-128">Advise organizers to use the Live Meeting service, if available in your organization.</span></span>

  - <span data-ttu-id="dfe13-129">Lasciare gli organizzatori ospitati nella versione precedente di Office Communications Server, in modo che possano continuare a pianificare conferenze Web di Live Meeting basate su server.</span><span class="sxs-lookup"><span data-stu-id="dfe13-129">Leave the organizers homed on the earlier version of Office Communications Server, so they can continue to schedule server-based Live Meeting web conferences.</span></span>

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a><span data-ttu-id="dfe13-130">Migrazione di riunioni esistenti e del contenuto delle riunioni</span><span class="sxs-lookup"><span data-stu-id="dfe13-130">Migrating Existing Meetings and Meeting Content</span></span>

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a><span data-ttu-id="dfe13-131">Migrazione di riunioni da Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="dfe13-131">Migrating Meetings from Lync Server 2010</span></span>

<span data-ttu-id="dfe13-132">Quando si sposta un utente da Lync Server 2010 a Lync Server 2013, le informazioni seguenti vengono spostate con l'account dell'utente:</span><span class="sxs-lookup"><span data-stu-id="dfe13-132">When you move a user from Lync Server 2010 to Lync Server 2013, the following information moves with the user’s account:</span></span>

  - <span data-ttu-id="dfe13-133">Le riunioni già pianificate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="dfe13-133">Meetings already scheduled by the user.</span></span> <span data-ttu-id="dfe13-134">Sono incluse le directory di conferenza e i dati di conferenza.</span><span class="sxs-lookup"><span data-stu-id="dfe13-134">This includes conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="dfe13-135">Il PIN dell'utente.</span><span class="sxs-lookup"><span data-stu-id="dfe13-135">The user’s personal identification number (PIN).</span></span> <span data-ttu-id="dfe13-136">Il PIN corrente dell'utente continua a funzionare fino alla scadenza o alla richiesta di un nuovo PIN da parte dell'utente stesso.</span><span class="sxs-lookup"><span data-stu-id="dfe13-136">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="dfe13-137">Tuttavia, le seguenti informazioni sull'account utente non vengono spostate nel nuovo server:</span><span class="sxs-lookup"><span data-stu-id="dfe13-137">However, the following user account information does not move to the new server:</span></span>

  - <span data-ttu-id="dfe13-138">Contenuto delle riunioni, ad esempio presentazioni di PowerPoint, contenuto della lavagna e dati del sondaggio</span><span class="sxs-lookup"><span data-stu-id="dfe13-138">Meeting content, for example PowerPoint presentations, whiteboard content, and poll data</span></span>

<span data-ttu-id="dfe13-139">Per spostare il contenuto condiviso nelle riunioni, utilizzare il parametro MoveMeetingContent del cmdlet Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="dfe13-139">To move the content that has been shared in meetings, use the MoveMeetingContent parameter of the Move-CsUser cmdlet.</span></span> <span data-ttu-id="dfe13-140">Per informazioni dettagliate sull'utilizzo di questo cmdlet, vedere [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) nella documentazione relativa ai cmdlet di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dfe13-140">For details about using this cmdlet, see [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) in the Lync Server 2013 cmdlets documentation.</span></span>

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a><span data-ttu-id="dfe13-141">Migrazione di riunioni da Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="dfe13-141">Migrating Meetings from Office Communications Server 2007 R2</span></span>

<span data-ttu-id="dfe13-142">Le riunioni di Office Communications Server 2007 R2 sono chiamate conferenza (prefisso URL conf://) o conferenze Web (prefisso URL meet://).</span><span class="sxs-lookup"><span data-stu-id="dfe13-142">Office Communications Server 2007 R2 meetings are either conference calls (conf:// URL prefix) or web conferences (meet:// URL prefix).</span></span> <span data-ttu-id="dfe13-143">Lync Server 2013 non supporta queste conferenze precedenti di conf://e meet://e non vengono migrate insieme all'account utente.</span><span class="sxs-lookup"><span data-stu-id="dfe13-143">Lync Server 2013 does not support these earlier conf:// and meet:// conferences, and they are not migrated along with the user account.</span></span> <span data-ttu-id="dfe13-144">Dopo la migrazione, è necessario indicare agli utenti di aggiornare i collegamenti per eventuali riunioni online pianificate.</span><span class="sxs-lookup"><span data-stu-id="dfe13-144">After migration, you should instruct users to update the links for any online meetings they have scheduled.</span></span> <span data-ttu-id="dfe13-145">Dopo l'installazione del client Lync 2013, è possibile eseguire questa operazione dopo l'apertura di un invito a una riunione pianificata, che consente di aggiornare l'URL della riunione e l'invio di un invito ai partecipanti.</span><span class="sxs-lookup"><span data-stu-id="dfe13-145">They can do this after installing the Lync 2013 client by opening a scheduled meeting invitation—which updates the meeting URL—and resending the invitation to participants.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a><span data-ttu-id="dfe13-146">Esperienza utente durante la migrazione di Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="dfe13-146">User Experience during Lync Server 2010 Migration</span></span>

<span data-ttu-id="dfe13-147">In questa sezione viene fornito un riepilogo dell'esperienza Conferencing degli utenti durante la migrazione da Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="dfe13-147">This section provides a summary of users’ conferencing experience when migrating from Lync 2010.</span></span> <span data-ttu-id="dfe13-148">Per ulteriori informazioni sul modo in cui i client di Lync Server 2013 possono coesistere e interagire con le versioni precedenti del server e del client, vedere [interoperabilità dei client in lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="dfe13-148">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a><span data-ttu-id="dfe13-149">Partecipazione alle riunioni di Lync Server 2010 con un client Lync 2013</span><span class="sxs-lookup"><span data-stu-id="dfe13-149">Joining Lync Server 2010 Meetings with a Lync 2013 Client</span></span>

<span data-ttu-id="dfe13-150">Durante la migrazione da Lync Server 2010, potrebbe esistere un periodo di coesistenza quando gli utenti partecipano alle riunioni di Lync Server 2010 con un client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="dfe13-150">During migration from Lync Server 2010, there may be a period of coexistence when users join Lync Server 2010 meetings with a Lync 2013 client.</span></span> <span data-ttu-id="dfe13-151">Questi utenti possono accedere alle funzionalità client di Lync 2013 con le eccezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dfe13-151">These users have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="dfe13-152">Nelle opzioni di gestione dei **partecipanti** , che sono accessibili facendo riferimento all'icona persone nella finestra riunione, l'opzione **Nessuna riunione di messaggistica istantanea** non funziona.</span><span class="sxs-lookup"><span data-stu-id="dfe13-152">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="dfe13-153">La visualizzazione raccolta non funziona nelle conferenze video.</span><span class="sxs-lookup"><span data-stu-id="dfe13-153">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="dfe13-154">L'utente visualizza solo l'altoparlante attivo invece di tutti gli altoparlanti.</span><span class="sxs-lookup"><span data-stu-id="dfe13-154">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="dfe13-155">Nell'elenco delle opzioni **Seleziona un layout** , la **visualizzazione raccolta** non è disponibile</span><span class="sxs-lookup"><span data-stu-id="dfe13-155">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="dfe13-156">L'elenco dei partecipanti viene visualizzato per impostazione predefinita nelle conferenze video.</span><span class="sxs-lookup"><span data-stu-id="dfe13-156">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="dfe13-157">Quando si fa clic con il pulsante destro del mouse su un utente nell'elenco partecipanti, le opzioni di gestione del **blocco video e del** **pin per la raccolta** non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="dfe13-157">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a><span data-ttu-id="dfe13-158">Esperienza utente durante la migrazione di Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="dfe13-158">User Experience during Office Communications Server 2007 R2 Migration</span></span>

<span data-ttu-id="dfe13-159">In questa sezione viene fornito un riepilogo dell'esperienza Conferencing degli utenti durante la migrazione da Office Communications Server 2007 R2, sia prima che dopo l'installazione di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="dfe13-159">This section provides a summary of users’ conferencing experience when migrating from Office Communications Server 2007 R2, both before and after Lync 2013 is installed.</span></span> <span data-ttu-id="dfe13-160">Per ulteriori informazioni sul modo in cui i client di Lync Server 2013 possono coesistere e interagire con le versioni precedenti del server e del client, vedere [interoperabilità dei client in lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="dfe13-160">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a><span data-ttu-id="dfe13-161">Dopo la migrazione dell'account utente, prima dell'installazione di Lync 2013</span><span class="sxs-lookup"><span data-stu-id="dfe13-161">After User Account is Migrated, Before Lync 2013 Is Installed</span></span>

<span data-ttu-id="dfe13-162">Dopo la migrazione di un utente al server Lync Server 2013, ma prima dell'installazione di nuovi client, gli utenti di Office Communicator 2007 R2 possono continuare a utilizzare il client esistente con Lync Server 2013 per le funzionalità di presenza e messaggistica istantanea, ma non le funzionalità di conferenza supportato.</span><span class="sxs-lookup"><span data-stu-id="dfe13-162">After a user is migrated to the Lync Server 2013 server, but before new clients are installed, Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a><span data-ttu-id="dfe13-163">Dopo la migrazione dell'account utente, dopo l'installazione di Lync 2013</span><span class="sxs-lookup"><span data-stu-id="dfe13-163">After User Account is Migrated, After Lync 2013 Is Installed</span></span>

<span data-ttu-id="dfe13-164">Quando un utente migrato installa Lync 2013, viene installato anche il componente aggiuntivo per riunioni online per Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="dfe13-164">When a migrated user installs Lync 2013, the Online Meeting Add-in for Lync 2013 is installed too.</span></span> <span data-ttu-id="dfe13-165">I risultati sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="dfe13-165">This has the following effects:</span></span>

  - <span data-ttu-id="dfe13-166">Tutte le riunioni pianificate successivamente sono basate sul nuovo formato di riunione, che utilizza un indirizzo https:// anziché l'indirizzo legacy di Live Meeting meet://.</span><span class="sxs-lookup"><span data-stu-id="dfe13-166">All subsequently scheduled meetings use the new meeting format, which uses an https:// address instead of the legacy meet:// Live Meeting address.</span></span>

  - <span data-ttu-id="dfe13-167">In una distribuzione gestita da IT di Lync 2013, l'amministratore ha la possibilità di disinstallare il componente aggiuntivo per conferenze per Microsoft Office Outlook, che viene utilizzato per pianificare riunioni di Live Meeting Server e basati su servizi.</span><span class="sxs-lookup"><span data-stu-id="dfe13-167">In an IT-managed deployment of Lync 2013, the administrator has the option of uninstalling the Conferencing Add-in for Microsoft Office Outlook, which is used to schedule Live Meeting server and service-based meetings.</span></span> <span data-ttu-id="dfe13-168">Alcuni utenti tuttavia potrebbero dover continuare a pianificare le riunioni basate sul servizio Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="dfe13-168">However, you may have users who need to continue to schedule Live Meeting service meetings.</span></span> <span data-ttu-id="dfe13-169">In questo caso è possibile consentire la coesistenza di entrambi i componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="dfe13-169">In this case, you can allow both add-ins to coexist.</span></span>

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a><span data-ttu-id="dfe13-170">Riunioni con organizzazioni federate che utilizzano client precedenti</span><span class="sxs-lookup"><span data-stu-id="dfe13-170">Meetings with Federated Organizations that Use Previous Clients</span></span>

<span data-ttu-id="dfe13-171">Gli utenti di organizzazioni federative che utilizzano Microsoft Office Communicator 2007 non possono partecipare alle riunioni di Lync Server 2013 nell'organizzazione se tali riunioni sono bloccate dall'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="dfe13-171">Users in federated organizations who are using Microsoft Office Communicator 2007 cannot join Lync Server 2013 meetings in your organization if those meetings are locked by the organizer.</span></span> <span data-ttu-id="dfe13-172">È necessario ripianificare queste riunioni in Lync Server 2013 in modo che i partecipanti federati che partecipano alla riunione utilizzando il nuovo URL della riunione di https://possano utilizzare Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="dfe13-172">You have to reschedule these meetings in Lync Server 2013 so when federated participants join the meeting by using the new https:// meeting URL, they can use Lync Web App.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

