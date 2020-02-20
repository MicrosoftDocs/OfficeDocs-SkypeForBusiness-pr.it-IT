---
title: 'Lync Server 2013: Panoramica del prelievo delle chiamate di gruppo'
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
ms.openlocfilehash: 222d587f7c4972a8aee313d3d66da578cde08960
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="2c8d3-102">Panoramica del prelievo delle chiamate di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c8d3-102">Overview of Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c8d3-103">_**Ultimo argomento modificato:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="2c8d3-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="2c8d3-104">Prelievo delle chiamate di gruppo, una nuova caratteristica negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013, consente agli utenti di rispondere alle chiamate in arrivo ai propri colleghi tramite i propri telefoni.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-104">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="2c8d3-105">Questa nuova funzionalità aumenta la disponibilità della linea di un utente consentendo ad altri utenti di rispondere a una chiamata in arrivo componendo un numero di gruppo di prelievo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-105">This new feature increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="2c8d3-106">Quando viene distribuito il prelievo delle chiamate di gruppo, il numero di chiamate in arrivo instradate alla segreteria telefonica può essere ridotto significativamente, il che è particolarmente utile per le chiamate provenienti da clienti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-106">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>

<span data-ttu-id="2c8d3-107">La funzionalità di prelievo delle chiamate di gruppo è stata progettata in particolare per le unità aziendali in ambienti Office aperti.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-107">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="2c8d3-108">Le chiamate in arrivo non sono di disturbo perché squillano solo nella destinazione prevista.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-108">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="2c8d3-109">Tuttavia, gli altri utenti che ascoltano l'anello possono comunque prendere la chiamata semplicemente componendo il numero del gruppo.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-109">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span>

<span data-ttu-id="2c8d3-110">Negli ambienti in cui gli utenti non sono ubicati in un layout Open Office o in cui gli utenti che condividono una responsabilità comune sono distribuiti geograficamente, il team Call presenta la soluzione più adatta.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-110">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="2c8d3-111">La differenza principale tra il prelievo di chiamate di gruppo e la chiamata del team consiste nel fatto che, con il prelievo delle chiamate di gruppo, una chiamata in arrivo squilla solo nella destinazione prevista, ma chiunque può comunque scegliere di rispondere componendo un numero di gruppo.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-111">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="2c8d3-112">Con il team di chiamata, la chiamata squilla a tutti i telefoni dei membri del team e tutti gli utenti del team possono prendere il telefono per rispondere alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-112">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="2c8d3-113">Un'ulteriore differenza tra il prelievo di chiamate di gruppo e la chiamata del team è che il prelievo delle chiamate di gruppo è gestito da un amministratore, tramite Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-113">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Lync Server.</span></span> <span data-ttu-id="2c8d3-114">Con la chiamata del team, gli utenti finali gestiscono la funzionalità utilizzando il client Lync.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-114">With team call, end users manage the feature by using the Lync client.</span></span> <span data-ttu-id="2c8d3-115">Con il prelievo delle chiamate di gruppo, pertanto, questo aspetto della gestione delle chiamate può essere centralizzato.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-115">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>

<span data-ttu-id="2c8d3-116">Il prelievo delle chiamate di gruppo è basato sull'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-116">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="2c8d3-117">Quando si distribuisce il prelievo delle chiamate di gruppo, è possibile configurare la tabella orbit del parcheggio di chiamata con intervalli distinti di numeri di interno designati come numeri del gruppo di prelievo delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-117">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="2c8d3-118">Analogamente ai numeri dell'orbita del parcheggio di chiamata, i numeri del gruppo di prelievo delle chiamate devono essere estensioni virtuali a cui non è assegnato alcun utente o telefono.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-118">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="2c8d3-119">Ogni pool Front end in cui si distribuisce il prelievo delle chiamate di gruppo può avere uno o più intervalli di numeri del gruppo di prelievo delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-119">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="2c8d3-120">Gli intervalli di numeri di gruppo devono essere univoci a livello globale nella distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-120">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2c8d3-121">Gli intervalli di numeri designati come numeri di prelievo delle chiamate di gruppo nella tabella di orbit del parcheggio di chiamata non possono essere gestiti o visualizzati utilizzando il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-121">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="2c8d3-122">L'unico modo per visualizzare tutti gli intervalli di numeri nella tabella di orbit del parcheggio di chiamata è l'utilizzo di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-122">The only way to see all the number ranges in the call park orbit table is to use Lync Server Management Shell.</span></span> <span data-ttu-id="2c8d3-123">Analogamente, l'unico modo per aggiungere, modificare o rimuovere i numeri di prelievo delle chiamate di gruppo consiste nell'utilizzare Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-123">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Lync Server Management Shell.</span></span>



</div>

<span data-ttu-id="2c8d3-124">Dopo aver configurato i numeri del gruppo di prelievo delle chiamate, è possibile assegnare gli utenti a un gruppo di prelievo delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-124">After you configure the call pickup group numbers, you assign users to a call pickup group.</span></span> <span data-ttu-id="2c8d3-125">Tutti gli utenti a cui è assegnato un gruppo di prelievo di chiamata possono rispondere alle chiamate di altri utenti.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-125">Any user who is assigned to a call pickup group can have their calls answered by other users.</span></span> <span data-ttu-id="2c8d3-126">Quando una chiamata viene rilasciata a un utente assegnato a un gruppo di prelievo di chiamata, qualsiasi altro utente che nota la chiamata può rispondere manualmente componendo il numero del gruppo di prelievo delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-126">When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number.</span></span> <span data-ttu-id="2c8d3-127">L'utente che preleva la chiamata non deve necessariamente essere un membro del gruppo.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-127">The user who picks up the call does not need to be a member of the group.</span></span> <span data-ttu-id="2c8d3-128">Quando una chiamata viene rilevata da un altro utente, viene inviata una notifica al numero originariamente chiamato.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-128">When a call is picked up by another user, a notification is sent to the number originally called.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2c8d3-129">Un utente può essere membro di un solo gruppo di prelievo delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-129">A user can be a member of only one call pickup group.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2c8d3-130">Anche se qualsiasi utente nella distribuzione di Lync Server può rispondere a una chiamata a un membro del gruppo di prelievo di chiamata, la persona che risponde alla chiamata deve conoscere il numero del gruppo di prelievo di chiamata corretto da comporre.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-130">Although any user in the Lync Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span>



</div>

<span data-ttu-id="2c8d3-131">Se un utente compone un numero di gruppo di prelievo di chiamata per rispondere a una chiamata quando si squillano più telefoni del gruppo, l'utente risponde alla chiamata che ha squillato più a lungo.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-131">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>

<span data-ttu-id="2c8d3-132">Le impostazioni di squillo simultaneo funzioneranno per gli utenti che dispongono del prelievo delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-132">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="2c8d3-133">Vale a dire che una chiamata effettuata a un utente con prelievo di chiamata di gruppo suonerà per tutte le destinazioni configurate e un altro utente potrà rispondere alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-133">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="2c8d3-134">L'eccezione a questa regola è quella in cui l'utente configura lo squillo simultaneo per chiamare tutti i membri del team.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-134">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>

<span data-ttu-id="2c8d3-135">Non è possibile utilizzare il prelievo delle chiamate di gruppo per rispondere ai tipi di chiamate seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c8d3-135">Group Call Pickup cannot be used to answer the following types of calls:</span></span>

  - <span data-ttu-id="2c8d3-136">Chiamate a una riga privata</span><span class="sxs-lookup"><span data-stu-id="2c8d3-136">Calls to a private line</span></span>

  - <span data-ttu-id="2c8d3-137">Chiamate da un contatto a cui è stata assegnata la relazione amici e familiari sulla privacy</span><span class="sxs-lookup"><span data-stu-id="2c8d3-137">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="2c8d3-138">Un utente membro di un gruppo di prelievo di chiamata può impedire che determinate chiamate vengano recuperate tramite il prelievo delle chiamate di gruppo contrassegnando il contatto come contatto personale nel client Lync.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-138">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Lync client.</span></span> <span data-ttu-id="2c8d3-139">Per contrassegnare un contatto come contatto personale, impostare la relazione di privacy per il contatto con gli amici e la famiglia.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-139">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="2c8d3-140">Qualsiasi chiamata in arrivo da contatti con la relazione di privacy impostata su amici e familiari non può essere recuperata tramite il prelievo delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-140">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span>

    
    </div>

  - <span data-ttu-id="2c8d3-141">Parte video delle chiamate audio/video</span><span class="sxs-lookup"><span data-stu-id="2c8d3-141">Video portion of audio/video calls</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2c8d3-142">Se un utente risponde a una chiamata audio/video, l'utente riceverà solo l'audio.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-142">If a user answers an audio/video call, the user receives only the audio.</span></span> <span data-ttu-id="2c8d3-143">La chiamata di persona o la persona che risponde alla chiamata può inoltrare la richiesta di aggiunta di un video.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-143">Either the person calling or the person answering the call can escalate the call to add video.</span></span>

    
    </div>

  - <span data-ttu-id="2c8d3-144">Chiamate di chiamata simultanee che vengono instradate ai membri delle chiamate del team</span><span class="sxs-lookup"><span data-stu-id="2c8d3-144">Simultaneous ringing calls that are routed to team call members</span></span>

  - <span data-ttu-id="2c8d3-145">Chiamate instradate a un delegato</span><span class="sxs-lookup"><span data-stu-id="2c8d3-145">Calls routed to a delegate</span></span>

  - <span data-ttu-id="2c8d3-146">Chiamate instradate a un Response Group</span><span class="sxs-lookup"><span data-stu-id="2c8d3-146">Calls routed to a response group</span></span>

<span data-ttu-id="2c8d3-147">I seguenti tipi di utenti non possono partecipare al ritiro delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-147">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="2c8d3-148">Vale a dire che non devono essere inclusi in un gruppo di prelievo di chiamata di gruppo e non possono rispondere alle chiamate per gli utenti che dispongono del prelievo di chiamata di gruppo abilitato.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-148">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>

  - <span data-ttu-id="2c8d3-149">Utenti ospitati online in una distribuzione ibrida</span><span class="sxs-lookup"><span data-stu-id="2c8d3-149">Users who are homed online in a hybrid deployment</span></span>

  - <span data-ttu-id="2c8d3-150">Utenti che non sono ospitati in un pool di Lync Server 2013 con aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 in una distribuzione locale</span><span class="sxs-lookup"><span data-stu-id="2c8d3-150">Users who are not homed on a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>

<span data-ttu-id="2c8d3-151">Se non si risponde a una chiamata a un membro di un gruppo di prelievo di chiamata, la chiamata viene instradata come specificato nelle impostazioni client.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-151">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings.</span></span> <span data-ttu-id="2c8d3-152">Vale a dire che la chiamata viene inviata alla segreteria telefonica o viene inoltrata a una destinazione diversa, come specificato nelle impostazioni del client.</span><span class="sxs-lookup"><span data-stu-id="2c8d3-152">That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

