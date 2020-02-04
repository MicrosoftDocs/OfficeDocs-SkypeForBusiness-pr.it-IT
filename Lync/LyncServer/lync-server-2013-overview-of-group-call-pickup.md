---
title: 'Lync Server 2013: Panoramica del ritiro delle chiamate di gruppo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Group Call Pickup
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945623(v=OCS.15)
ms:contentKeyID: 51541466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0efc85b28a689b43d024d9996211a70dcd91cee0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="a9a7e-102">Panoramica del ritiro delle chiamate di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9a7e-102">Overview of Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9a7e-103">_**Argomento Ultima modifica:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="a9a7e-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="a9a7e-104">Raccolta di chiamate di gruppo, una nuova funzionalità degli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013, consente agli utenti di rispondere alle chiamate in arrivo ai propri colleghi dal proprio telefono.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-104">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="a9a7e-105">Questa nuova caratteristica aumenta la disponibilità della linea di un utente, consentendo ad altri utenti di rispondere a una chiamata in arrivo componendo un numero di gruppo di pick-up chiamata.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-105">This new feature increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="a9a7e-106">Quando viene distribuito il prelievo delle chiamate di gruppo, il numero di chiamate in arrivo indirizzate alla segreteria telefonica può essere notevolmente ridotto, particolarmente utile per le chiamate provenienti da clienti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-106">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>

<span data-ttu-id="a9a7e-107">La caratteristica raccolta chiamate di gruppo è stata progettata in particolare per le unità aziendali in ambienti Office aperti.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-107">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="a9a7e-108">Le chiamate in arrivo non sono di disturbo perché squillano solo nella destinazione prevista.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-108">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="a9a7e-109">Tuttavia, gli altri utenti che sentono l'anello possono comunque prendere la chiamata semplicemente componendo il numero di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-109">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span>

<span data-ttu-id="a9a7e-110">In ambienti in cui gli utenti non si trovano in un layout Office aperto o in cui gli utenti che condividono una responsabilità comune sono distribuiti geograficamente, la chiamata del team presenta la soluzione più appropriata.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-110">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="a9a7e-111">La differenza principale tra il pick-up delle chiamate di gruppo e la chiamata del team consiste nel fatto che, con il ritiro delle chiamate di gruppo, una chiamata in arrivo viene squillata solo nella destinazione desiderata, ma chiunque può comunque scegliere di rispondere chiamando un numero di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-111">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="a9a7e-112">Con la chiamata del team, la chiamata squilla in tutti i telefoni dei membri del team e qualsiasi utente del team può prendere il telefono per rispondere alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-112">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="a9a7e-113">Una differenza aggiuntiva tra il ritiro delle chiamate di gruppo e la chiamata del team consiste nel fatto che il ritiro delle chiamate di gruppo viene gestito da un amministratore tramite Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-113">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Lync Server.</span></span> <span data-ttu-id="a9a7e-114">Con la chiamata del team, gli utenti finali gestiscono la funzionalità usando il client Lync.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-114">With team call, end users manage the feature by using the Lync client.</span></span> <span data-ttu-id="a9a7e-115">Con il pick-up delle chiamate di gruppo, quindi, questo aspetto della gestione delle chiamate può essere centralizzato.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-115">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>

<span data-ttu-id="a9a7e-116">Il ritiro delle chiamate di gruppo viene compilato nell'applicazione Call Park.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-116">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="a9a7e-117">Quando si distribuisce il pickup di una chiamata di gruppo, è possibile configurare la tabella Orbit di Call Park con intervalli distinti di numeri di interno designati come numeri di gruppo di pick-up delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-117">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="a9a7e-118">Come i numeri delle orbite di Call Park, i numeri dei gruppi di pickup delle chiamate devono essere estensioni virtuali che non hanno un utente o un telefono assegnato.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-118">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="a9a7e-119">Ogni pool Front end in cui si distribuisce il pickup di una chiamata di gruppo può avere uno o più intervalli di numeri di gruppo di prelievo chiamate.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-119">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="a9a7e-120">Gli intervalli di numeri di gruppo devono essere univoci a livello globale in tutta la distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-120">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a9a7e-121">Gli intervalli di numeri designati come numeri di prelievo delle chiamate di gruppo nella tabella Orbit di parcheggio delle chiamate non possono essere gestiti o visualizzati tramite il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-121">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="a9a7e-122">L'unico modo per visualizzare tutti gli intervalli di numeri nella tabella Orbit di Call Park consiste nell'usare Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-122">The only way to see all the number ranges in the call park orbit table is to use Lync Server Management Shell.</span></span> <span data-ttu-id="a9a7e-123">Analogamente, l'unico modo per aggiungere, modificare o rimuovere i numeri di prelievo delle chiamate di gruppo consiste nell'usare Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-123">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Lync Server Management Shell.</span></span>



</div>

<span data-ttu-id="a9a7e-124">Dopo aver configurato i numeri dei gruppi di raccolta chiamate, assegnare gli utenti a un gruppo di raccolta chiamate.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-124">After you configure the call pickup group numbers, you assign users to a call pickup group.</span></span> <span data-ttu-id="a9a7e-125">Qualsiasi utente assegnato a un gruppo di raccolta chiamate può rispondere alle chiamate di altri utenti.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-125">Any user who is assigned to a call pickup group can have their calls answered by other users.</span></span> <span data-ttu-id="a9a7e-126">Quando una chiamata viene fornita a un utente assegnato a un gruppo di raccolta chiamate, qualsiasi altro utente che nota la chiamata può rispondere manualmente chiamando il numero del gruppo di raccolta chiamate.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-126">When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number.</span></span> <span data-ttu-id="a9a7e-127">L'utente che preleva la chiamata non deve necessariamente essere un membro del gruppo.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-127">The user who picks up the call does not need to be a member of the group.</span></span> <span data-ttu-id="a9a7e-128">Quando una chiamata viene rilevata da un altro utente, viene inviata una notifica al numero originariamente chiamato.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-128">When a call is picked up by another user, a notification is sent to the number originally called.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a9a7e-129">Un utente può essere un membro di un solo gruppo di raccolta chiamate.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-129">A user can be a member of only one call pickup group.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a9a7e-130">Anche se qualsiasi utente nella distribuzione di Lync Server può rispondere a una chiamata a un membro del gruppo di prelievo delle chiamate, la persona che risponde alla chiamata deve conoscere il numero del gruppo di pick-up chiamata corretto.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-130">Although any user in the Lync Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span>



</div>

<span data-ttu-id="a9a7e-131">Se un utente compone un numero di gruppo di pick-up chiamata per rispondere a una chiamata quando si squillano più telefoni nel gruppo, l'utente risponde alla chiamata che ha squillato il più a lungo.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-131">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>

<span data-ttu-id="a9a7e-132">Le impostazioni di chiamata simultanee funzionano per gli utenti che hanno un pick-up delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-132">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="a9a7e-133">Vale a dire che una chiamata effettuata a un utente che ha un pickup per la chiamata di gruppo suonerà per tutte le destinazioni configurate e un altro utente può rispondere alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-133">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="a9a7e-134">L'eccezione a questa regola è quando l'utente configura lo squillo simultaneo per chiamare tutti i membri del team.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-134">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>

<span data-ttu-id="a9a7e-135">Non è possibile usare il pick-up per rispondere ai tipi di chiamata seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9a7e-135">Group Call Pickup cannot be used to answer the following types of calls:</span></span>

  - <span data-ttu-id="a9a7e-136">Chiamate a una riga privata</span><span class="sxs-lookup"><span data-stu-id="a9a7e-136">Calls to a private line</span></span>

  - <span data-ttu-id="a9a7e-137">Chiamate di un contatto a cui sono stati assegnati gli amici e la relazione di privacy della famiglia</span><span class="sxs-lookup"><span data-stu-id="a9a7e-137">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="a9a7e-138">Un utente che fa parte di un gruppo di raccolta chiamate può impedire che determinate chiamate vengano recuperate tramite il ritiro delle chiamate di gruppo contrassegnando il contatto come contatto personale nel client Lync.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-138">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Lync client.</span></span> <span data-ttu-id="a9a7e-139">Per contrassegnare un contatto come contatto personale, impostare la relazione di privacy per il contatto con amici e familiari.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-139">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="a9a7e-140">Qualsiasi chiamata in arrivo da contatti con la relazione di privacy impostata su amici e familiari non può essere recuperata tramite raccolta chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-140">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span>

    
    </div>

  - <span data-ttu-id="a9a7e-141">Parte video delle chiamate audio/video</span><span class="sxs-lookup"><span data-stu-id="a9a7e-141">Video portion of audio/video calls</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a9a7e-142">Se un utente risponde a una chiamata audio/video, l'utente riceve solo l'audio.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-142">If a user answers an audio/video call, the user receives only the audio.</span></span> <span data-ttu-id="a9a7e-143">La chiamata di persona o la persona che risponde alla chiamata può escalation per l'aggiunta di un video.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-143">Either the person calling or the person answering the call can escalate the call to add video.</span></span>

    
    </div>

  - <span data-ttu-id="a9a7e-144">Chiamate di chiamata simultanee instradate ai membri delle chiamate del team</span><span class="sxs-lookup"><span data-stu-id="a9a7e-144">Simultaneous ringing calls that are routed to team call members</span></span>

  - <span data-ttu-id="a9a7e-145">Chiamate instradate a un delegato</span><span class="sxs-lookup"><span data-stu-id="a9a7e-145">Calls routed to a delegate</span></span>

  - <span data-ttu-id="a9a7e-146">Chiamate instradate a un gruppo di risposte</span><span class="sxs-lookup"><span data-stu-id="a9a7e-146">Calls routed to a response group</span></span>

<span data-ttu-id="a9a7e-147">I tipi di utenti seguenti non possono partecipare al ritiro delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-147">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="a9a7e-148">Vale a dire che non devono essere inclusi in un gruppo di raccolta chiamate di gruppo e non possono raccogliere le chiamate per gli utenti che hanno abilitato il pick-up delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-148">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>

  - <span data-ttu-id="a9a7e-149">Utenti residenti online in una distribuzione ibrida</span><span class="sxs-lookup"><span data-stu-id="a9a7e-149">Users who are homed online in a hybrid deployment</span></span>

  - <span data-ttu-id="a9a7e-150">Utenti non residenti in un pool di Lync Server 2013 con aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 in una distribuzione locale</span><span class="sxs-lookup"><span data-stu-id="a9a7e-150">Users who are not homed on a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>

<span data-ttu-id="a9a7e-151">Se non si risponde a una chiamata a un membro di un gruppo di raccolta chiamate, la chiamata viene instradata come specificato nelle impostazioni del client.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-151">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings.</span></span> <span data-ttu-id="a9a7e-152">Vale a dire che la chiamata passa alla segreteria telefonica o viene inoltrata a una destinazione diversa, come specificato nelle impostazioni del client.</span><span class="sxs-lookup"><span data-stu-id="a9a7e-152">That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

