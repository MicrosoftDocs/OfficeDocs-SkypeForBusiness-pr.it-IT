---
title: 'Lync Server 2013: Panoramica del parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acb507ddf7fc47714781e83da0fa77d093f193c0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a><span data-ttu-id="3b601-102">Panoramica del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b601-102">Overview of Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b601-103">_**Ultimo argomento modificato:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="3b601-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="3b601-104">L'applicazione di parcheggio di chiamata Lync Server 2013 consente agli utenti di VoIP aziendale di eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b601-104">The Lync Server 2013 Call Park application lets Enterprise Voice users do any of the following:</span></span>

  - <span data-ttu-id="3b601-105">Mettere una chiamata in attesa e quindi recuperare la chiamata dallo stesso telefono o da uno diverso.</span><span class="sxs-lookup"><span data-stu-id="3b601-105">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>

  - <span data-ttu-id="3b601-106">Mettere una chiamata in attesa per trasferirla a un altro reparto o a un'altra area generale, ad esempio a un reparto vendite o un magazzino in cui è presente un telefono di area comune.</span><span class="sxs-lookup"><span data-stu-id="3b601-106">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>

  - <span data-ttu-id="3b601-107">Mettere una chiamata in attesa e mantenere libero per altre chiamate il telefono originale da cui si è risposto alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="3b601-107">Put a call on hold and keep the original answering phone free for other calls.</span></span>

<span data-ttu-id="3b601-108">Quando un utente effettua una chiamata, Lync Server trasferisce la chiamata a un numero temporaneo, denominato *orbita*, in cui la chiamata viene mantenuta fino a quando non viene recuperata o non viene rilasciata. Lync Server invia l'orbita all'utente che ha parcheggiato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="3b601-108">When a user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until it is retrieved or it times out. Lync Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="3b601-109">Per recuperare la chiamata parcheggiata, l'utente può comporre il codice orbit o fare clic sul collegamento o il pulsante del codice orbit nella finestra Conversazione.</span><span class="sxs-lookup"><span data-stu-id="3b601-109">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span>

<span data-ttu-id="3b601-p102">L'utente che ha eseguito il parcheggio di una chiamata può indicare a qualcun altro di recuperare la chiamata utilizzando un meccanismo esterno, ad esempio un sistema di messaggistica istantanea o di paging, per comunicare il codice orbit a un altro utente. L'utente che ha eseguito il parcheggio della chiamata può lasciare aperta la finestra Conversazione per ricevere una notifica quando la chiamata viene recuperata.</span><span class="sxs-lookup"><span data-stu-id="3b601-p102">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else. The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>

<span data-ttu-id="3b601-112">Poiché gli intervalli di Orbit sono univoci a livello globale, è possibile recuperare le chiamate da qualsiasi sito Lync Server o telefono PBX se il routing è configurato in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="3b601-112">Because orbit ranges are globally unique, it is possible to retrieve calls from any Lync Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="3b601-113">Se nessuno recupera la chiamata entro una quantità di tempo configurabile, la chiamata viene nuovamente indirizzata alla persona che ne ha eseguito il parcheggio.</span><span class="sxs-lookup"><span data-stu-id="3b601-113">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="3b601-114">Se tale persona non risponde alla richiamata, la chiamata viene trasferita a una destinazione di fallback, ad esempio a un operatore, se questa impostazione è configurata.</span><span class="sxs-lookup"><span data-stu-id="3b601-114">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="3b601-115">È possibile configurare da uno a dieci il numero di volte per cui consentire una richiamata prima che la chiamata venga trasferita.</span><span class="sxs-lookup"><span data-stu-id="3b601-115">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="3b601-116">Se nessuno risponde a una chiamata trasferita, questa viene disconnessa.</span><span class="sxs-lookup"><span data-stu-id="3b601-116">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="3b601-117">Il codice orbit viene liberato quando la chiamata viene recuperata o disconnessa.</span><span class="sxs-lookup"><span data-stu-id="3b601-117">The orbit is freed when the call is retrieved or disconnected.</span></span>

<span data-ttu-id="3b601-118">Quando si distribuisce il parcheggio di chiamata, è necessario riservare intervalli di numeri di interno (codici orbit) per il parcheggio delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="3b601-118">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="3b601-119">Tali numeri devono essere interni virtuali, ovvero numeri a cui non sono assegnati utenti o telefoni.</span><span class="sxs-lookup"><span data-stu-id="3b601-119">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="3b601-120">È quindi necessario configurare la tabella dei codici orbit del parcheggio di chiamata con gli intervalli di interni e specificare il servizio applicazione che ospita l'applicazione Parcheggio di chiamata che gestisce ogni intervallo.</span><span class="sxs-lookup"><span data-stu-id="3b601-120">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="3b601-121">Ogni pool Front End include una tabella di parcheggio di chiamata nel server di back-end corrispondente utilizzato per gestire le chiamate parcheggiate nel pool.</span><span class="sxs-lookup"><span data-stu-id="3b601-121">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="3b601-122">L'elenco degli intervalli di Orbit è memorizzato nell'archivio di gestione centrale e viene utilizzato per instradare le orbite al pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3b601-122">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="3b601-123">Ogni pool di Lync Server in cui viene distribuita e configurata l'applicazione Parcheggio di chiamata può disporre di uno o più intervalli di Orbit.</span><span class="sxs-lookup"><span data-stu-id="3b601-123">Each Lync Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="3b601-124">Gli intervalli di Orbit devono essere univoci a livello globale nella distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3b601-124">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<span data-ttu-id="3b601-p105">È anche possibile configurare altre impostazioni di parcheggio chiamata, ad esempio la destinazione di reindirizzamento delle chiamate in caso di timeout e se usare la musica di attesa durante il parcheggio. È anche possibile specificare il file musicale da riprodurre mentre la chiamata è in attesa.</span><span class="sxs-lookup"><span data-stu-id="3b601-p105">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked. You can also specify the music file to play while the call is on hold.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3b601-127">I file musicali personalizzati per il parcheggio di chiamata non vengono sottoposti a backup come parte del processo di ripristino di emergenza di Lync Server 2013 e andranno persi se i file caricati nel pool sono danneggiati, danneggiati o eliminati.</span><span class="sxs-lookup"><span data-stu-id="3b601-127">Customized music-on-hold files for Call Park are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="3b601-128">Mantenere sempre una copia di backup distinta dei file di musica di attesa personalizzati caricati per il parcheggio chiamate.</span><span class="sxs-lookup"><span data-stu-id="3b601-128">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="3b601-p107">L'applicazione Parcheggio di chiamata è un componente di VoIP aziendale. Quando si distribuisce VoIP aziendale, l'applicazione Parcheggio di chiamata viene installata e attivata automaticamente. Prima di poter utilizzare l'applicazione Parcheggio di chiamata, tuttavia, l'amministratore di VoIP aziendale deve configurarla e abilitarla per gli utenti tramite criteri vocali.</span><span class="sxs-lookup"><span data-stu-id="3b601-p107">The Call Park application is a component of Enterprise Voice. When you deploy Enterprise Voice, the Call Park application is installed and activated automatically. Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

