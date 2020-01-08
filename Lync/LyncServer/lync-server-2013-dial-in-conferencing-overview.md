---
title: Panoramica delle conferenze telefoniche con accesso esterno di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 820c880d44a1ecede139a8d3caddf3f6c40e65a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="46b9b-102">Panoramica dei servizi di conferenza telefonica con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46b9b-102">Overview of dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46b9b-103">_**Argomento Ultima modifica:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="46b9b-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="46b9b-104">Se l'organizzazione dispone di utenti che devono partecipare a conferenze locali di Lync Server 2013 quando si trovano fuori sede o non hanno accesso a un computer, è possibile distribuire i servizi di conferenza telefonica con chiamata in modo che possano partecipare alla conferenza usando un telefono pubblico con commutazioni telefono di rete (PSTN).</span><span class="sxs-lookup"><span data-stu-id="46b9b-104">If your organization has users who need to attend Lync Server 2013 on-premises conferences when they are out of the office or do not have access to a computer, you can deploy dial-in conferencing so that they can join the conference by using a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="46b9b-105">I servizi di conferenza telefonica con accesso esterno sono una funzionalità facoltativa che è possibile configurare quando si distribuisce una conferenza di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="46b9b-105">Dial-in conferencing is an optional feature that you can configure when you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="46b9b-106">Anche se i servizi di conferenza telefonica con accesso esterno usano alcuni degli stessi componenti di Lync Server 2013 usati da Enterprise Voice, è possibile distribuire i servizi di conferenza telefonica con accesso esterno anche se non si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="46b9b-106">Although dial-in conferencing uses some of the same Lync Server 2013 components that Enterprise Voice uses, you can deploy dial-in conferencing even if you do not deploy Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46b9b-107">Se si distribuiscono i servizi di conferenza telefonica con accesso esterno, è necessario distribuirla in tutti i pool in cui si distribuiscono le conferenze di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="46b9b-107">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="46b9b-108">Non è necessario assegnare i numeri di accesso in tutti i pool, ma è necessario distribuire la caratteristica chiamata in ingresso in ogni pool.</span><span class="sxs-lookup"><span data-stu-id="46b9b-108">You do not need to assign access numbers in every pool, but you must deploy the dial-in feature in every pool.</span></span> <span data-ttu-id="46b9b-109">Questo requisito supporta la caratteristica nome registrato quando un utente chiama un numero di accesso da un pool per partecipare a una conferenza di Lync Server 2013 in un pool diverso.</span><span class="sxs-lookup"><span data-stu-id="46b9b-109">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

<span data-ttu-id="46b9b-110">Le conferenze devono essere abilitate per l'accesso esterno in criteri riunione.</span><span class="sxs-lookup"><span data-stu-id="46b9b-110">Conferences must be enabled for dial-in access in meeting policy.</span></span> <span data-ttu-id="46b9b-111">Per impostazione predefinita, le conferenze abilitate per l'accesso esterno includono le informazioni seguenti nell'invito alla conferenza:</span><span class="sxs-lookup"><span data-stu-id="46b9b-111">By default, conferences that are enabled for dial-in access include the following information in the conference invitation:</span></span>

  - <span data-ttu-id="46b9b-112">ID conferenza numerico che identifica la conferenza.</span><span class="sxs-lookup"><span data-stu-id="46b9b-112">A numeric conference ID that identifies the conference.</span></span>

  - <span data-ttu-id="46b9b-113">Uno o più numeri di accesso PSTN.</span><span class="sxs-lookup"><span data-stu-id="46b9b-113">One or more PSTN access numbers.</span></span>

  - <span data-ttu-id="46b9b-114">Un collegamento a una pagina delle impostazioni di conferenza telefonica con accesso esterno, che contiene un elenco completo dei numeri di Access con le lingue associate; una posizione per creare, reimpostare o sbloccare i numeri di identificazione personali (pin); e altre informazioni, ad esempio i controlli DTMF (Dual-Tone Multi-Frequency).</span><span class="sxs-lookup"><span data-stu-id="46b9b-114">A link to a Dial-in Conferencing Settings page, which contains a complete list of access numbers with their associated languages; a place to create, reset, or unblock personal identification numbers (PINs); and other information, such as dual-tone multi-frequency (DTMF) controls.</span></span>

<span data-ttu-id="46b9b-115">I servizi di conferenza telefonica con accesso esterno supportano utenti Enterprise e Anonymous.</span><span class="sxs-lookup"><span data-stu-id="46b9b-115">Dial-in conferencing supports both enterprise and anonymous users.</span></span> <span data-ttu-id="46b9b-116">Gli utenti aziendali hanno le credenziali dei servizi di dominio Active Directory e gli account di Lync Server 2013 all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="46b9b-116">Enterprise users have Active Directory Domain Services credentials and Lync Server 2013 accounts within their organization.</span></span> <span data-ttu-id="46b9b-117">Gli utenti anonimi non hanno credenziali aziendali all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="46b9b-117">Anonymous users do not have enterprise credentials within your organization.</span></span> <span data-ttu-id="46b9b-118">Nel contesto dei servizi di conferenza telefonica con accesso esterno, un utente dell'organizzazione di un partner federato che usa la rete PSTN per connettersi a una conferenza viene considerato come un utente anonimo.</span><span class="sxs-lookup"><span data-stu-id="46b9b-118">In the dial-in conferencing context, a user in a federated partner’s organization who uses the PSTN to connect to a conference is treated like an anonymous user.</span></span> <span data-ttu-id="46b9b-119">Per i servizi di conferenza telefonica con accesso esterno, a differenza di altri contesti, gli utenti federati non vengono autenticati.</span><span class="sxs-lookup"><span data-stu-id="46b9b-119">For dial-in conferencing, unlike other contexts, federated users are not authenticated.</span></span>

<span data-ttu-id="46b9b-120">Gli utenti aziendali o i responsabili delle conferenze che partecipano a una conferenza abilitata per la chiamata in accesso esterno compongono uno dei numeri di accesso alla conferenza e quindi viene richiesto di immettere l'ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="46b9b-120">Enterprise users or conference leaders who join a conference that is enabled for dial-in access dial one of the conference access numbers and then are prompted to enter the conference ID.</span></span> <span data-ttu-id="46b9b-121">Se una direttrice non è ancora entrata nella riunione, gli utenti possono immettere l'estensione UC (Unified Communications) o il numero di telefono completo e aggiungere o aspettare di essere ammessi da una direttrice.</span><span class="sxs-lookup"><span data-stu-id="46b9b-121">If a leader has not yet joined the meeting, users can either enter their unified communications (UC) extension (or full phone number) and PIN or wait to be admitted by a leader.</span></span> <span data-ttu-id="46b9b-122">L'organizzatore della riunione può partecipare alla riunione come leader immettendo solo il PIN.</span><span class="sxs-lookup"><span data-stu-id="46b9b-122">The Meeting organizer can join the meeting as a leader by entering just their PIN.</span></span> <span data-ttu-id="46b9b-123">Il server front-end usa la combinazione di numero di telefono completo o estensione e PIN per associare gli utenti aziendali in modo univoco alle credenziali di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="46b9b-123">The Front End Server uses the combination of full phone number or extension, and PIN, to uniquely map enterprise users to their Active Directory credentials.</span></span> <span data-ttu-id="46b9b-124">Di conseguenza, gli utenti dell'organizzazione vengono autenticati e identificati per nome nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="46b9b-124">As a result, enterprise users are authenticated and identified by name in the conference.</span></span> <span data-ttu-id="46b9b-125">Gli utenti aziendali possono anche assumere un ruolo di conferenza predefinito dall'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="46b9b-125">Enterprise users can also assume a conference role predefined by the organizer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46b9b-126">Gli utenti aziendali che effettuano la chiamata da un telefono Office IP o da Lync Server 2013 o Lync 2010 Attendant non vengono richiesti per il proprio numero di telefono perché sono già autenticati.</span><span class="sxs-lookup"><span data-stu-id="46b9b-126">Enterprise users who dial in from an office IP phone or from Lync Server 2013 or Lync 2010 Attendant are not prompted for their phone number because they are already authenticated.</span></span>



</div>

<span data-ttu-id="46b9b-127">Utenti anonimi che desiderano partecipare a una conferenza telefonica con accesso esterno, digitare un numero di Access per le conferenze e quindi viene richiesto di immettere l'ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="46b9b-127">Anonymous users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID.</span></span> <span data-ttu-id="46b9b-128">Anche agli utenti anonimi non autenticati viene richiesto di registrare il proprio nome.</span><span class="sxs-lookup"><span data-stu-id="46b9b-128">Unauthenticated anonymous users are also prompted to record their name.</span></span> <span data-ttu-id="46b9b-129">Il nome registrato identifica gli utenti non autenticati nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="46b9b-129">The recorded name identifies unauthenticated users in the conference.</span></span> <span data-ttu-id="46b9b-130">Gli utenti anonimi non sono ammessi alla conferenza fino a quando almeno un leader o un utente autenticato non partecipa e non è possibile assegnare loro un ruolo predefinito.</span><span class="sxs-lookup"><span data-stu-id="46b9b-130">Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46b9b-131">Gli utenti aziendali che scelgono di non immettere il proprio numero di telefono e il PIN non vengono autenticati.</span><span class="sxs-lookup"><span data-stu-id="46b9b-131">Enterprise users who choose not to enter their phone number and PIN are not authenticated.</span></span> <span data-ttu-id="46b9b-132">Viene richiesto di registrare il proprio nome e di essere trattati come utenti anonimi nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="46b9b-132">They are prompted to record their name and are treated as anonymous users in the conference.</span></span>



</div>

<span data-ttu-id="46b9b-133">In fase di pianificazione, l'organizzatore della riunione può scegliere di limitare l'accesso alla riunione rendendo la riunione chiusa o bloccata.</span><span class="sxs-lookup"><span data-stu-id="46b9b-133">At schedule time, the meeting organizer can choose to restrict access to the meeting by making the meeting closed or locked.</span></span> <span data-ttu-id="46b9b-134">In questo caso, gli utenti con accesso esterno vengono richiesti per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="46b9b-134">In this case, dial-in users are requested to authenticate.</span></span> <span data-ttu-id="46b9b-135">Se gli utenti con accesso esterno non riescono o scelgono di non eseguire l'autenticazione, vengono trasferiti nella sala di attesa.</span><span class="sxs-lookup"><span data-stu-id="46b9b-135">If dial-in users fail or choose not to authenticate, they are transferred to the lobby.</span></span> <span data-ttu-id="46b9b-136">Attendono nella sala di attesa fino a quando un leader non li accetta o li rifiuta oppure viene disconnesso.</span><span class="sxs-lookup"><span data-stu-id="46b9b-136">They wait in the lobby until a leader accepts or rejects them, or they time out and are disconnected.</span></span> <span data-ttu-id="46b9b-137">Gli utenti con accesso esterno sentono la musica se sono in attesa di essere ammessi alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="46b9b-137">Dial-in users hear music if they are waiting to be admitted to the conference.</span></span> <span data-ttu-id="46b9b-138">Dopo l'ammissione a una conferenza, gli utenti con accesso esterno possono partecipare alla parte audio della conferenza e possono esercitare i comandi DTMF (Dual-Tone Multi-Frequency) usando la tastiera del telefono.</span><span class="sxs-lookup"><span data-stu-id="46b9b-138">After they are admitted to a conference, dial-in users can participate in the audio portion of the conference and can exercise dual-tone multi-frequency (DTMF) commands by using the phone keypad.</span></span> <span data-ttu-id="46b9b-139">I responsabili delle connessioni telefoniche con accesso esterno possono esercitare i comandi DTMF per attivare o disattivare l'attivazione o disattivazione dei partecipanti, bloccare o sbloccare la conferenza, ammettere gli utenti nella sala di attesa e attivare o disattivare gli annunci di entrata e uscita.</span><span class="sxs-lookup"><span data-stu-id="46b9b-139">Dial-in leaders can exercise DTMF commands to turn participants' ability to unmute on or off, lock or unlock the conference, admit people from the lobby, and turn entry and exit announcements on or off.</span></span> <span data-ttu-id="46b9b-140">I responsabili possono anche usare un comando DTMF per ammettere tutti gli utenti della sala di attesa, che modificano le autorizzazioni della riunione per consentire a tutti i partecipanti di accedervi.</span><span class="sxs-lookup"><span data-stu-id="46b9b-140">Leaders can also use a DTMF command to admit everyone from the lobby, which changes the permissions of the meeting to allow anyone who subsequently joins.</span></span> <span data-ttu-id="46b9b-141">Tutti i partecipanti alla chiamata in accesso esterno possono esercitare i comandi DTMF per ascoltare la guida, ascoltare il roster della conferenza e disattivare l'audio.</span><span class="sxs-lookup"><span data-stu-id="46b9b-141">All dial-in participants can exercise DTMF commands to hear Help, listen to the conference roster, and mute themselves.</span></span>

<span data-ttu-id="46b9b-142">Partecipanti con accesso esterno (ovvero, indipendentemente dal fatto che abbiano o meno la chiamata dalla rete PSTN), ascoltare annunci personali durante la conferenza, ad esempio se sono stati riattivati o disattivati, la riunione è stata registrata o qualcuno sta aspettando nella sala di attesa.</span><span class="sxs-lookup"><span data-stu-id="46b9b-142">Dial-in participants (that is, whether or not they dial from the PSTN), hear personal announcements during the conference, such as whether they have been muted or unmuted, the meeting is being recorded, or someone is waiting in the lobby.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46b9b-143">Partecipanti che partecipano alla conferenza facendo clic su un collegamento invece di effettuare la chiamata in non si sentono annunci personali.</span><span class="sxs-lookup"><span data-stu-id="46b9b-143">Participants who join the conference by clicking a link instead of dialing in do not hear personal announcements.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

