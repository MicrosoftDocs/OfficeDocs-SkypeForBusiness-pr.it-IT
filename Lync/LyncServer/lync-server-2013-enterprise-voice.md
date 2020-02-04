---
title: 'Lync Server 2013: VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e62224a7187c54222364045d0ac7b1aa70bccb9c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="138d7-102">VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="138d7-102">Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="138d7-103">_**Argomento Ultima modifica:** 2015-04-08_</span><span class="sxs-lookup"><span data-stu-id="138d7-103">_**Topic Last Modified:** 2015-04-08_</span></span>

<span data-ttu-id="138d7-104">Con Enterprise Voice, Lync Server offre una funzionalità VoIP (Voice over Internet Protocol) autonoma che consente di migliorare o sostituire sistemi PBX (Private Branch Exchange) tradizionali.</span><span class="sxs-lookup"><span data-stu-id="138d7-104">With Enterprise Voice, Lync Server delivers a stand-alone Voice over Internet Protocol (VoIP) offering to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="138d7-105">Gli utenti di Enterprise Voice possono chiamare i colleghi della rete VoIP o del PBX dell'organizzazione e possono chiamare i numeri di telefono tradizionali all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="138d7-105">Enterprise Voice users can call colleagues on your organization’s VoIP network or PBX, and they can call traditional phone numbers outside your organization.</span></span> <span data-ttu-id="138d7-106">La soluzione VoIP aziendale include funzionalità di chiamata comuni, ad esempio risposta, inoltrare, trasferire, tenere, deviare, rilasciare e parcheggiare e la chiamata di 9-1-1 (E9-1-1) avanzata (E9-1-1 è disponibile solo negli Stati Uniti). Enterprise Voice supporta inoltre una vasta gamma di dispositivi IP e USB correnti e meno recenti.</span><span class="sxs-lookup"><span data-stu-id="138d7-106">The Enterprise Voice solution includes common calling features such as answer, forward, transfer, hold, divert, release and park, and Enhanced 9-1-1 (E9-1-1) calling (E9-1-1 is available only in the United States.) Enterprise Voice also supports a broad range of current and older IP and USB devices.</span></span>

<div>

## <a name="placing-and-receiving-calls"></a><span data-ttu-id="138d7-107">Immissione e ricezione di chiamate</span><span class="sxs-lookup"><span data-stu-id="138d7-107">Placing and Receiving Calls</span></span>

<span data-ttu-id="138d7-108">L'uso di Lync consente agli utenti di effettuare chiamate digitando un nome o un numero di telefono sulla tastiera oppure usando una tastierina telefonica visualizzata sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="138d7-108">Using Lync, users can place calls by typing a name or phone number on their keyboard, or using a dial pad displayed on their screen.</span></span> <span data-ttu-id="138d7-109">Gli utenti possono anche avviare chiamate direttamente dall'elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="138d7-109">Users can also initiate calls directly from their Contacts list.</span></span> <span data-ttu-id="138d7-110">È anche possibile distribuire i dispositivi Lync Phone Edition, che sono dispositivi IP autonomi forniti da Microsoft partner.</span><span class="sxs-lookup"><span data-stu-id="138d7-110">You can also deploy Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

<span data-ttu-id="138d7-111">Gli utenti possono avere più dispositivi telefonici registrati con Lync Server e possono passare facilmente tra di essi.</span><span class="sxs-lookup"><span data-stu-id="138d7-111">Users can have multiple phone devices registered with Lync Server, and can switch between them easily.</span></span>

<span data-ttu-id="138d7-112">Gli utenti vengono avvisati delle chiamate in arrivo su tutti i loro dispositivi contemporaneamente, con suonerie personalizzabili su dispositivi telefonici IP e una notifica simile a un messaggio istantaneo nel PC.</span><span class="sxs-lookup"><span data-stu-id="138d7-112">Users are alerted to incoming calls on all their devices simultaneously, with customizable ringtones on IP phone devices and a notification similar to an instant message on their PC.</span></span>

<span data-ttu-id="138d7-113">Gli utenti possono anche impostare un singolo numero di telefono che si connette al telefono da tavolo, al PC e al cellulare, in modo che possano essere raggiunti ovunque si trovino.</span><span class="sxs-lookup"><span data-stu-id="138d7-113">Users can also set a single telephone number that connects to their desk phone, PC and mobile phone, so they can be reached no matter where they are.</span></span>

</div>

<div>

## <a name="basic-call-features"></a><span data-ttu-id="138d7-114">Funzionalità di base delle chiamate</span><span class="sxs-lookup"><span data-stu-id="138d7-114">Basic Call Features</span></span>

<span data-ttu-id="138d7-115">Durante una chiamata, un utente può rispondere alle chiamate in arrivo aggiuntive o avviare le chiamate in uscita e la chiamata attiva esistente viene inserita automaticamente in attesa.</span><span class="sxs-lookup"><span data-stu-id="138d7-115">While on a call, a user can answer additional incoming calls or initiate outgoing calls, and the existing active call is automatically put on hold.</span></span> <span data-ttu-id="138d7-116">Le chiamate possono essere trasferite da un utente a un altro, direttamente o dopo che il primo utente parla in privato con il secondo utente.</span><span class="sxs-lookup"><span data-stu-id="138d7-116">Calls can be transferred from one user to another, either directly or after the first user speaks privately with the second user.</span></span> <span data-ttu-id="138d7-117">Gli utenti possono anche trasferire le chiamate a un altro dispositivo; ad esempio, potrebbero trasferire una chiamata attiva al proprio telefono cellulare mentre camminano fuori dalla porta del loro ufficio.</span><span class="sxs-lookup"><span data-stu-id="138d7-117">Users can also transfer calls to another device; for example, they could transfer an active call to their mobile phone as they walk out the door of their office.</span></span>

</div>

<div>

## <a name="richer-communications"></a><span data-ttu-id="138d7-118">Comunicazioni più avanzate</span><span class="sxs-lookup"><span data-stu-id="138d7-118">Richer Communications</span></span>

<span data-ttu-id="138d7-119">Quando si parla a un altro utente con Lync, gli utenti possono aggiungere facilmente testo, video o condivisione desktop alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="138d7-119">When talking to another user with Lync, users can easily add text, video, or desktop sharing to the call.</span></span> <span data-ttu-id="138d7-120">La caratteristica do-not-disturb è integrata con le impostazioni di presenza in Lync.</span><span class="sxs-lookup"><span data-stu-id="138d7-120">The Do-Not-Disturb feature is integrated with the presence settings in Lync.</span></span>

<span data-ttu-id="138d7-121">Con la messaggistica UNIFICAta di Exchange, Lync e Lync Server si integrano con Microsoft Exchange Server 2013 e Microsoft Outlook 2013.</span><span class="sxs-lookup"><span data-stu-id="138d7-121">With Exchange Unified Messaging (UM), Lync and Lync Server integrate with Microsoft Exchange Server 2013 and Microsoft Outlook 2013.</span></span> <span data-ttu-id="138d7-122">Gli utenti possono vedere se sono presenti nuovi messaggi vocali nella finestra di Lync e nella posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="138d7-122">Users can see if they have new voice mail both in their Lync window and in email.</span></span> <span data-ttu-id="138d7-123">Durante la posta elettronica, è possibile fare clic per riprodurre l'audio della segreteria telefonica in un messaggio di posta elettronica o visualizzare una trascrizione del messaggio della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="138d7-123">While in email they can click to play the voice mail audio in an email message, or view a transcript of the voice mail message.</span></span>

</div>

<div>

## <a name="advanced-calling-features"></a><span data-ttu-id="138d7-124">Funzionalità per le chiamate avanzate</span><span class="sxs-lookup"><span data-stu-id="138d7-124">Advanced Calling Features</span></span>

<span data-ttu-id="138d7-125">Enterprise Voice include diverse funzionalità di chiamata avanzate, ad esempio la delega delle chiamate di Lync, le chiamate di Team, il pick-up delle chiamate di gruppo e i gruppi di risposta.</span><span class="sxs-lookup"><span data-stu-id="138d7-125">Enterprise Voice includes several advanced calling features as well, such as Lync call delegation, team calling, Group Call Pickup, and Response Groups.</span></span>

<span data-ttu-id="138d7-126">La delega delle chiamate di Lync consente agli utenti di delegare la gestione delle chiamate a uno o più assistenti, passando alle **impostazioni di inoltro delle chiamate delle** **Opzioni** \> **degli strumenti** \> .</span><span class="sxs-lookup"><span data-stu-id="138d7-126">Lync call delegation enables users to delegate call handling to one or more assistants, by going to **Tools** \> **Options** \> **Call Forwarding Settings**.</span></span> <span data-ttu-id="138d7-127">Il delegato può eseguire più attività di chiamata per conto dell'utente, incluse le chiamate di selezione, l'immissione di chiamate e l'avvio di conferenze.</span><span class="sxs-lookup"><span data-stu-id="138d7-127">The delegate can perform multiple calling tasks on behalf of the user, including screening calls, placing calls, and initiating conferences.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="138d7-128">Potrebbe essere alla ricerca di un'altra caratteristica denominata in modo simile, delegazione del calendario Lync.</span><span class="sxs-lookup"><span data-stu-id="138d7-128">You may be looking for another similarly named feature, Lync calendar delegation.</span></span> <span data-ttu-id="138d7-129">Non richiede la funzionalità VoIP aziendale e consente agli utenti di pianificare riunioni di Lync Online da Outlook.</span><span class="sxs-lookup"><span data-stu-id="138d7-129">It doesn't require the Enterprise Voice feature and does allow users to schedule online Lync meetings from Outlook.</span></span> <span data-ttu-id="138d7-130">Se sei qui per cercare queste informazioni, ti consigliamo di verificare <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> per informazioni su come abilitare la sincronizzazione dei delegati di Exchange.</span><span class="sxs-lookup"><span data-stu-id="138d7-130">If you've come here looking for that info, we recommend checking out <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> for information on enabling Exchange delegate sync.</span></span>



</div>

<span data-ttu-id="138d7-131">La chiamata in team consente a un utente di avere chiamate in arrivo squillare simultaneamente i telefoni dei membri del team in modo che tutti gli utenti possano rispondere alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="138d7-131">Team calling enables a user to have incoming calls simultaneously ring the phones of teammates so that anyone on the team can answer the call.</span></span>

<span data-ttu-id="138d7-132">Raccolta di chiamate di gruppo, una nuova funzionalità degli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013, consente agli utenti di rispondere alle chiamate in arrivo ai propri colleghi dal proprio telefono.</span><span class="sxs-lookup"><span data-stu-id="138d7-132">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="138d7-133">Il ritiro delle chiamate di gruppo è diverso da quello delle chiamate in team principalmente in quanto una chiamata in arrivo squilla solo presso il telefono del destinatario previsto, ma qualsiasi altro utente può scegliere di rispondere chiamando un numero del gruppo di selezione chiamata.</span><span class="sxs-lookup"><span data-stu-id="138d7-133">Group Call Pickup differs from team calling primarily in that an incoming call rings only at the intended recipient's phone, but any other user can choose to answer it by dialing a call pickup group number.</span></span>

<span data-ttu-id="138d7-134">I gruppi di risposta possono essere configurati per l'accodamento e il routing intelligente delle chiamate agli agenti designati.</span><span class="sxs-lookup"><span data-stu-id="138d7-134">Response Groups can be set up for queuing and intelligently routing calls to designated agents.</span></span> <span data-ttu-id="138d7-135">Gli usi comuni includono helpdesk IT, hotline risorse umane e altri centri di contatto interni.</span><span class="sxs-lookup"><span data-stu-id="138d7-135">Common uses include IT helpdesks, human resources hotlines, and other internal contact centers.</span></span>

</div>

<div>

## <a name="enterprise-voice-administration"></a><span data-ttu-id="138d7-136">Amministrazione di VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="138d7-136">Enterprise Voice Administration</span></span>

<span data-ttu-id="138d7-137">Lync Server usa standard e interfacce pubblicate per interagire con l'infrastruttura esistente.</span><span class="sxs-lookup"><span data-stu-id="138d7-137">Lync Server uses standards and published interfaces to interoperate with existing infrastructure.</span></span> <span data-ttu-id="138d7-138">Supporta sia le opzioni di gateway che SIP, ad esempio il trunking SIP, per l'interconnessione ai sistemi IP PBX e le reti PSTN, in modo da poter eseguire la migrazione degli utenti a Enterprise Voice nel tempo, riducendo al minimo le interruzioni.</span><span class="sxs-lookup"><span data-stu-id="138d7-138">It supports both gateway and SIP options (such as SIP trunking) for interconnection to IP PBX systems and the PSTN networks, so that you can migrate users to Enterprise Voice over time, while minimizing disruption.</span></span> <span data-ttu-id="138d7-139">Lync Server supporta codec tradizionali come G. 711, G. 722 e G. 723.1 per l'interoperabilità con le tradizionali soluzioni VoIP.</span><span class="sxs-lookup"><span data-stu-id="138d7-139">Lync Server supports traditional codecs such as G.711, G.722, and G.723.1 for interoperability with traditional VoIP solutions.</span></span>

<span data-ttu-id="138d7-140">Con il controllo di ammissione alle chiamate (CAC), gli amministratori possono impostare limiti per la quantità di traffico vocale e video di Lync Server eseguito sui collegamenti di rete vincolati e specificare l'azione da eseguire se una nuova chiamata supera il limite.</span><span class="sxs-lookup"><span data-stu-id="138d7-140">With call admission control (CAC), administrators can set limits on the amount of Lync Server voice and video traffic carried on constrained network links, and specify the action to be taken if a new call would exceed the limit.</span></span> <span data-ttu-id="138d7-141">Le azioni possono includere il routing in base a un percorso alternativo o rifiutare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="138d7-141">The actions could include routing by an alternate path, or refusing the call.</span></span>

<span data-ttu-id="138d7-142">Lync Server funziona con gli elettrodomestici Survivable di terze parti per ottenere servizi di chiamata locali e la connessione a PSTN presso le filiali, in caso di errore WAN nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="138d7-142">Lync Server works with third-party Survivable Branch Appliances to provide local calling services and connection to PSTN at branch offices, in case of WAN failure at the central site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

