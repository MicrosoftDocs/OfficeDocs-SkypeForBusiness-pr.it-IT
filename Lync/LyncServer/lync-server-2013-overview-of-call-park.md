---
title: 'Lync Server 2013: Panoramica di Call Park'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2d6f6b8f0f6a91e75071c7d103cf4bff3b4be1f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a><span data-ttu-id="951c5-102">Panoramica di Call Park in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="951c5-102">Overview of Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="951c5-103">_**Argomento Ultima modifica:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="951c5-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="951c5-104">L'applicazione Call Park di Lync Server 2013 consente agli utenti di VoIP aziendale di eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="951c5-104">The Lync Server 2013 Call Park application lets Enterprise Voice users do any of the following:</span></span>

  - <span data-ttu-id="951c5-105">Inserire una chiamata in attesa e quindi recuperare la chiamata dallo stesso telefono o da un altro telefono.</span><span class="sxs-lookup"><span data-stu-id="951c5-105">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>

  - <span data-ttu-id="951c5-106">Inserire una chiamata in attesa per trasferirla in un reparto o in un'area generale, ad esempio in un reparto vendite o in un magazzino in cui è presente un telefono con area comune.</span><span class="sxs-lookup"><span data-stu-id="951c5-106">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>

  - <span data-ttu-id="951c5-107">Mettere una chiamata in attesa e mantenere il telefono di risposta originale gratuito per altre chiamate.</span><span class="sxs-lookup"><span data-stu-id="951c5-107">Put a call on hold and keep the original answering phone free for other calls.</span></span>

<span data-ttu-id="951c5-108">Quando un utente parcheggia una chiamata, Lync Server trasferisce la chiamata a un numero temporaneo, detto *orbita*, in cui la chiamata viene mantenuta fino a quando non viene recuperata o il timeout viene riattivato. Lync Server invia l'orbita all'utente che ha parcheggiato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="951c5-108">When a user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until it is retrieved or it times out. Lync Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="951c5-109">Per recuperare la chiamata parcheggiata, l'utente può selezionare il numero dell'orbita oppure fare clic sul collegamento orbita o sul pulsante nella finestra di conversazione.</span><span class="sxs-lookup"><span data-stu-id="951c5-109">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span>

<span data-ttu-id="951c5-110">L'utente che ha parcheggiato una chiamata può segnalare a qualcuno di recuperare la chiamata usando un meccanismo esterno, ad esempio messaggistica istantanea (IM) o un sistema di paging, per comunicare il numero dell'orbita a qualcun altro.</span><span class="sxs-lookup"><span data-stu-id="951c5-110">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else.</span></span> <span data-ttu-id="951c5-111">L'utente che ha parcheggiato la chiamata può uscire dalla finestra di conversazione per ricevere una notifica quando viene recuperata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="951c5-111">The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>

<span data-ttu-id="951c5-112">Poiché gli intervalli di Orbit sono univoci a livello globale, è possibile recuperare le chiamate da qualsiasi sito di Lync Server o telefono PBX se il routing è configurato in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="951c5-112">Because orbit ranges are globally unique, it is possible to retrieve calls from any Lync Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="951c5-113">Se non si recupera la chiamata entro un periodo di tempo configurabile, la chiamata torna alla persona che l'ha parcheggiata.</span><span class="sxs-lookup"><span data-stu-id="951c5-113">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="951c5-114">Se la persona non risponde alla risponderia, la chiamata viene trasferita a una destinazione di fallback, ad esempio a un operatore, se configurata.</span><span class="sxs-lookup"><span data-stu-id="951c5-114">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="951c5-115">È possibile configurare il numero di volte in cui la chiamata squilla prima di essere trasferita da uno a dieci volte.</span><span class="sxs-lookup"><span data-stu-id="951c5-115">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="951c5-116">Se non si risponde a una chiamata trasferita, la chiamata viene disconnessa.</span><span class="sxs-lookup"><span data-stu-id="951c5-116">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="951c5-117">L'orbita viene liberata quando la chiamata viene recuperata o disconnessa.</span><span class="sxs-lookup"><span data-stu-id="951c5-117">The orbit is freed when the call is retrieved or disconnected.</span></span>

<span data-ttu-id="951c5-118">Quando si distribuisce Call Park, è necessario riservare intervalli di numeri di interno per le chiamate di parcheggio.</span><span class="sxs-lookup"><span data-stu-id="951c5-118">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="951c5-119">Queste estensioni devono essere estensioni virtuali: estensioni che non hanno un utente o un telefono assegnato.</span><span class="sxs-lookup"><span data-stu-id="951c5-119">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="951c5-120">Si configura quindi la tabella Orbit di Call Park con gli intervalli di numeri di interno e si specifica quale servizio applicazione ospita l'applicazione di parcheggio di chiamata che gestisce ogni intervallo.</span><span class="sxs-lookup"><span data-stu-id="951c5-120">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="951c5-121">Ogni pool Front end include una tabella di parcheggio di chiamata nel server back-end corrispondente usato per gestire le chiamate parcheggiate nel pool.</span><span class="sxs-lookup"><span data-stu-id="951c5-121">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="951c5-122">L'elenco di intervalli orbit è archiviato in Central Management store e viene usato per instradare le orbite al pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="951c5-122">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="951c5-123">Ogni pool di Lync Server in cui è distribuita e configurata l'applicazione Parcheggio di chiamata può avere uno o più intervalli di orbita.</span><span class="sxs-lookup"><span data-stu-id="951c5-123">Each Lync Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="951c5-124">Gli intervalli di Orbit devono essere univoci a livello globale in tutta la distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="951c5-124">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<span data-ttu-id="951c5-125">Si configurano anche altre impostazioni di Call Park, ad esempio dove vengono reindirizzate le chiamate se si verificano il timeout e se la persona del telefono sente la musica durante il parcheggio.</span><span class="sxs-lookup"><span data-stu-id="951c5-125">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked.</span></span> <span data-ttu-id="951c5-126">È anche possibile specificare il file musicale da riprodurre mentre la chiamata è in attesa.</span><span class="sxs-lookup"><span data-stu-id="951c5-126">You can also specify the music file to play while the call is on hold.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="951c5-127">I file musicali personalizzati per il parcheggio delle chiamate non vengono sottoposto a backup come parte del processo di ripristino di emergenza di Lync Server 2013 e andranno perduti se i file caricati nel pool sono danneggiati, danneggiati o eliminati.</span><span class="sxs-lookup"><span data-stu-id="951c5-127">Customized music-on-hold files for Call Park are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="951c5-128">Mantieni sempre una copia di backup separata dei file personalizzati di musica in attesa caricati per Call Park.</span><span class="sxs-lookup"><span data-stu-id="951c5-128">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="951c5-129">L'applicazione Call Park è un componente di Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="951c5-129">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="951c5-130">Quando si distribuisce VoIP aziendale, l'applicazione Call Park viene installata e attivata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="951c5-130">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="951c5-131">Prima di poter usare Call Park, tuttavia, l'amministratore di VoIP aziendale deve configurarlo e abilitarlo per gli utenti tramite il criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="951c5-131">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

