---
title: Lync Server 2013 VoIP aziendale
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
ms.openlocfilehash: 39179f1db1c547081e059d9b3ee275c924621cab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533173"
---
# <a name="enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="59665-102">VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59665-102">Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59665-103">_**Ultimo argomento modificato:** 2015-04-08_</span><span class="sxs-lookup"><span data-stu-id="59665-103">_**Topic Last Modified:** 2015-04-08_</span></span>

<span data-ttu-id="59665-104">Con VoIP aziendale, Lync Server offre una voce autonoma che offre un protocollo Voice over Internet Protocol per migliorare o sostituire i sistemi PBX (Private Branch Exchange) tradizionali.</span><span class="sxs-lookup"><span data-stu-id="59665-104">With Enterprise Voice, Lync Server delivers a stand-alone Voice over Internet Protocol (VoIP) offering to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="59665-105">Gli utenti di VoIP aziendale possono chiamare i colleghi sulla rete VoIP o sul sistema PBX dell'organizzazione, nonché numeri di telefono tradizionali all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="59665-105">Enterprise Voice users can call colleagues on your organization’s VoIP network or PBX, and they can call traditional phone numbers outside your organization.</span></span> <span data-ttu-id="59665-106">La soluzione VoIP aziendale include funzionalità di chiamata comuni quali la risposta, l'inoltro, il trasferimento, la conservazione, la deviazione, la liberazione e il parco e la chiamata avanzata 9-1-1 (E9-1-1) (il servizio E9-1-1 è disponibile solo negli Stati Uniti). VoIP aziendale supporta anche una vasta gamma di dispositivi IP e USB correnti e meno recenti.</span><span class="sxs-lookup"><span data-stu-id="59665-106">The Enterprise Voice solution includes common calling features such as answer, forward, transfer, hold, divert, release and park, and Enhanced 9-1-1 (E9-1-1) calling (E9-1-1 is available only in the United States.) Enterprise Voice also supports a broad range of current and older IP and USB devices.</span></span>

<div>

## <a name="placing-and-receiving-calls"></a><span data-ttu-id="59665-107">Effettuare e ricevere chiamate</span><span class="sxs-lookup"><span data-stu-id="59665-107">Placing and Receiving Calls</span></span>

<span data-ttu-id="59665-108">Utilizzando Lync, gli utenti possono effettuare chiamate digitando un nome o un numero di telefono sulla propria tastiera oppure utilizzando un tastierino numerico visualizzato sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="59665-108">Using Lync, users can place calls by typing a name or phone number on their keyboard, or using a dial pad displayed on their screen.</span></span> <span data-ttu-id="59665-109">Gli utenti possono anche avviare le chiamate direttamente dall'elenco dei contatti.</span><span class="sxs-lookup"><span data-stu-id="59665-109">Users can also initiate calls directly from their Contacts list.</span></span> <span data-ttu-id="59665-110">È inoltre possibile distribuire i dispositivi Lync Phone Edition, che sono dispositivi telefonici IP autonomi forniti da Microsoft Partners.</span><span class="sxs-lookup"><span data-stu-id="59665-110">You can also deploy Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

<span data-ttu-id="59665-111">Gli utenti possono disporre di più dispositivi telefonici registrati con Lync Server e possono passare facilmente tra di essi.</span><span class="sxs-lookup"><span data-stu-id="59665-111">Users can have multiple phone devices registered with Lync Server, and can switch between them easily.</span></span>

<span data-ttu-id="59665-112">Vengono avvisati in caso di chiamate in arrivo su tutti i dispositivi contemporaneamente, mediante suonerie personalizzabili sui dispositivi telefonici IP e una notifica simile a un messaggio istantaneo sul PC.</span><span class="sxs-lookup"><span data-stu-id="59665-112">Users are alerted to incoming calls on all their devices simultaneously, with customizable ringtones on IP phone devices and a notification similar to an instant message on their PC.</span></span>

<span data-ttu-id="59665-113">Gli utenti possono inoltre impostare un singolo numero di telefono che si connette al telefono da tavolo, al PC e al cellulare, in modo da essere raggiungibili in qualsiasi luogo.</span><span class="sxs-lookup"><span data-stu-id="59665-113">Users can also set a single telephone number that connects to their desk phone, PC and mobile phone, so they can be reached no matter where they are.</span></span>

</div>

<div>

## <a name="basic-call-features"></a><span data-ttu-id="59665-114">Funzionalità di chiamata di base</span><span class="sxs-lookup"><span data-stu-id="59665-114">Basic Call Features</span></span>

<span data-ttu-id="59665-p103">Durante una chiamata, un utente può rispondere ad altre chiamate in arrivo o avviare chiamate in uscita mentre la chiamata attiva esistente viene automaticamente messa in attesa. Le chiamate possono essere trasferite da un utente all'altro, direttamente o dopo che il primo utente ha parlato in privato con il secondo. Gli utenti possono inoltre trasferire le chiamate a un altro dispositivo, ad esempio possono trasferire una chiamata attiva al loro cellulare mentre varcano la porta del proprio ufficio.</span><span class="sxs-lookup"><span data-stu-id="59665-p103">While on a call, a user can answer additional incoming calls or initiate outgoing calls, and the existing active call is automatically put on hold. Calls can be transferred from one user to another, either directly or after the first user speaks privately with the second user. Users can also transfer calls to another device; for example, they could transfer an active call to their mobile phone as they walk out the door of their office.</span></span>

</div>

<div>

## <a name="richer-communications"></a><span data-ttu-id="59665-118">Comunicazioni più complete</span><span class="sxs-lookup"><span data-stu-id="59665-118">Richer Communications</span></span>

<span data-ttu-id="59665-119">Quando si parla a un altro utente con Lync, gli utenti possono aggiungere facilmente testo, video o condivisione del desktop alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="59665-119">When talking to another user with Lync, users can easily add text, video, or desktop sharing to the call.</span></span> <span data-ttu-id="59665-120">La funzionalità do-not-disturb è integrata con le impostazioni di presenza in Lync.</span><span class="sxs-lookup"><span data-stu-id="59665-120">The Do-Not-Disturb feature is integrated with the presence settings in Lync.</span></span>

<span data-ttu-id="59665-121">Con la messaggistica unificata di Exchange (UM), Lync e Lync Server si integrano con Microsoft Exchange Server 2013 e Microsoft Outlook 2013.</span><span class="sxs-lookup"><span data-stu-id="59665-121">With Exchange Unified Messaging (UM), Lync and Lync Server integrate with Microsoft Exchange Server 2013 and Microsoft Outlook 2013.</span></span> <span data-ttu-id="59665-122">Gli utenti possono vedere se dispongono di una nuova segreteria telefonica sia nella finestra di Lync sia nella posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="59665-122">Users can see if they have new voice mail both in their Lync window and in email.</span></span> <span data-ttu-id="59665-123">Mentre è aperto il programma di posta elettronica, possono fare clic per riprodurre l'audio della segreteria telefonica in un messaggio di posta elettronica o visualizzare una trascrizione del messaggio della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="59665-123">While in email they can click to play the voice mail audio in an email message, or view a transcript of the voice mail message.</span></span>

</div>

<div>

## <a name="advanced-calling-features"></a><span data-ttu-id="59665-124">Funzionalità di chiamata avanzate</span><span class="sxs-lookup"><span data-stu-id="59665-124">Advanced Calling Features</span></span>

<span data-ttu-id="59665-125">VoIP aziendale include anche diverse funzionalità di chiamata avanzate, ad esempio la delega delle chiamate di Lync, la chiamata di Team, il prelievo di chiamate di gruppo e i Response Group.</span><span class="sxs-lookup"><span data-stu-id="59665-125">Enterprise Voice includes several advanced calling features as well, such as Lync call delegation, team calling, Group Call Pickup, and Response Groups.</span></span>

<span data-ttu-id="59665-126">La delega delle chiamate di Lync consente agli utenti di delegare la gestione delle chiamate a uno **Tools** o più assistenti, accedendo alle \> **Options** \> **impostazioni delle opzioni di inoltro delle chiamate**degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="59665-126">Lync call delegation enables users to delegate call handling to one or more assistants, by going to **Tools** \> **Options** \> **Call Forwarding Settings**.</span></span> <span data-ttu-id="59665-127">Consente inoltre di eseguire più attività di chiamata per conto dell'utente, ad esempio la selezione delle chiamate, l'esecuzione di chiamate e l'avvio delle conferenze.</span><span class="sxs-lookup"><span data-stu-id="59665-127">The delegate can perform multiple calling tasks on behalf of the user, including screening calls, placing calls, and initiating conferences.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="59665-128">È possibile cercare un'altra caratteristica denominata in modo simile, la delega del calendario di Lync.</span><span class="sxs-lookup"><span data-stu-id="59665-128">You may be looking for another similarly named feature, Lync calendar delegation.</span></span> <span data-ttu-id="59665-129">Non richiede la funzionalità VoIP aziendale e consente agli utenti di pianificare riunioni di Lync Online da Outlook.</span><span class="sxs-lookup"><span data-stu-id="59665-129">It doesn't require the Enterprise Voice feature and does allow users to schedule online Lync meetings from Outlook.</span></span> <span data-ttu-id="59665-130">Se si è venuti a trovare le informazioni, è consigliabile consultare <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> per informazioni sull'abilitazione della sincronizzazione dei delegati di Exchange.</span><span class="sxs-lookup"><span data-stu-id="59665-130">If you've come here looking for that info, we recommend checking out <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> for information on enabling Exchange delegate sync.</span></span>



</div>

<span data-ttu-id="59665-131">Il team Calling consente a un utente di effettuare chiamate in entrata contemporaneamente squillare i telefoni dei compagni di squadra in modo che tutti i membri del team possano rispondere alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="59665-131">Team calling enables a user to have incoming calls simultaneously ring the phones of teammates so that anyone on the team can answer the call.</span></span>

<span data-ttu-id="59665-132">Prelievo delle chiamate di gruppo, una nuova caratteristica negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013, consente agli utenti di rispondere alle chiamate in arrivo ai propri colleghi tramite i propri telefoni.</span><span class="sxs-lookup"><span data-stu-id="59665-132">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="59665-133">Il prelievo delle chiamate di gruppo è diverso dalla chiamata del team principalmente in quanto una chiamata in arrivo squilla solo nel telefono del destinatario previsto, ma qualsiasi altro utente può scegliere di rispondere componendo un numero di gruppo di prelievo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="59665-133">Group Call Pickup differs from team calling primarily in that an incoming call rings only at the intended recipient's phone, but any other user can choose to answer it by dialing a call pickup group number.</span></span>

<span data-ttu-id="59665-p109">I Response Group possono essere impostati per l'accodamento e il routing intelligente delle chiamate agli agenti designati. Gli usi comuni includono l'helpdesk IT, le hotline delle risorse umane e altri centri di contatto interni.</span><span class="sxs-lookup"><span data-stu-id="59665-p109">Response Groups can be set up for queuing and intelligently routing calls to designated agents. Common uses include IT helpdesks, human resources hotlines, and other internal contact centers.</span></span>

</div>

<div>

## <a name="enterprise-voice-administration"></a><span data-ttu-id="59665-136">Amministrazione VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="59665-136">Enterprise Voice Administration</span></span>

<span data-ttu-id="59665-137">Lync Server utilizza gli standard e le interfacce pubblicate per interagire con l'infrastruttura esistente.</span><span class="sxs-lookup"><span data-stu-id="59665-137">Lync Server uses standards and published interfaces to interoperate with existing infrastructure.</span></span> <span data-ttu-id="59665-138">Supporta sia le opzioni gateway che SIP, ad esempio il trunking SIP, per l'interconnessione con i sistemi IP PBX e le reti PSTN, in modo da consentire la migrazione graduale degli utenti a VoIP aziendale, riducendo al tempo stesso le interruzioni.</span><span class="sxs-lookup"><span data-stu-id="59665-138">It supports both gateway and SIP options (such as SIP trunking) for interconnection to IP PBX systems and the PSTN networks, so that you can migrate users to Enterprise Voice over time, while minimizing disruption.</span></span> <span data-ttu-id="59665-139">Lync Server supporta codec tradizionali quali G. 711, G. 722 e G. 723.1 per l'interoperabilità con le soluzioni VoIP tradizionali.</span><span class="sxs-lookup"><span data-stu-id="59665-139">Lync Server supports traditional codecs such as G.711, G.722, and G.723.1 for interoperability with traditional VoIP solutions.</span></span>

<span data-ttu-id="59665-140">Con il controllo di ammissione di chiamata (CAC), gli amministratori possono impostare limiti per la quantità di traffico vocale e video di Lync Server eseguito sui collegamenti di rete vincolati e specificare l'azione da eseguire se una nuova chiamata supera il limite.</span><span class="sxs-lookup"><span data-stu-id="59665-140">With call admission control (CAC), administrators can set limits on the amount of Lync Server voice and video traffic carried on constrained network links, and specify the action to be taken if a new call would exceed the limit.</span></span> <span data-ttu-id="59665-141">Le azioni possono includere il routing con un percorso alternativo o il rifiuto della chiamata.</span><span class="sxs-lookup"><span data-stu-id="59665-141">The actions could include routing by an alternate path, or refusing the call.</span></span>

<span data-ttu-id="59665-142">Lync Server è compatibile con Survivable Branch Appliance di terze parti per fornire servizi di chiamata locali e la connessione alla rete PSTN nelle succursali, in caso di errore WAN nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="59665-142">Lync Server works with third-party Survivable Branch Appliances to provide local calling services and connection to PSTN at branch offices, in case of WAN failure at the central site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

