---
title: 'Lync Server 2013: Panoramica del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Persistent Chat Server
ms:assetid: 23f7c886-304d-495a-ae70-3cbb44241acd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425717(v=OCS.15)
ms:contentKeyID: 48183622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cd18a5943332f8c612ba10b74317666d609d558
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="46f06-102">Panoramica del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46f06-102">Overview of Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46f06-103">_**Ultimo argomento modificato:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="46f06-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="46f06-104">Lync Server 2013, il server Chat persistente consente agli utenti di partecipare a conversazioni a più parti, basate su argomenti che persistono nel tempo.</span><span class="sxs-lookup"><span data-stu-id="46f06-104">Lync Server 2013, Persistent Chat Server enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="46f06-105">Il server Chat persistente può aiutare l'organizzazione a eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="46f06-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="46f06-106">Migliorare le comunicazioni tra team interfunzionali distribuiti in zone geografiche diverse.</span><span class="sxs-lookup"><span data-stu-id="46f06-106">Improve communication between geographically dispersed and cross-functional teams.</span></span> <span data-ttu-id="46f06-107">Utilizzando la chat persistente, i team possono condividere in modo efficiente informazioni, idee e decisioni tra loro.</span><span class="sxs-lookup"><span data-stu-id="46f06-107">By using Persistent Chat, teams can efficiently share information, ideas, and decisions with one another.</span></span> <span data-ttu-id="46f06-108">I messaggi inviati alle chat room (Forum di discussione) possono essere salvati (ovvero possono essere disponibili nel tempo), in modo che le persone provenienti da diverse località e reparti possano partecipare, anche quando non sono contemporaneamente online.</span><span class="sxs-lookup"><span data-stu-id="46f06-108">The messages posted to chat rooms (discussion forums) can persist (that is, can be available over time), so that people from different locations and departments can participate, even when they are not simultaneously online.</span></span> <span data-ttu-id="46f06-109">Quando un utente si connette a una chat room, la chat (un numero configurabile di messaggi di cronologia chat) viene caricata automaticamente nella chat room per fornire all'utente un contesto per la conversazione.</span><span class="sxs-lookup"><span data-stu-id="46f06-109">When a user connects to a chat room, backchat (a configurable number of chat-history messages) is automatically loaded in the chat room to give the user a context for the conversation.</span></span>

  - <span data-ttu-id="46f06-110">Migliorare la capacità di analisi delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="46f06-110">Improve information awareness.</span></span> <span data-ttu-id="46f06-111">Utilizzando i filtri sul fianco del client, gli utenti possono definire condizioni, ad esempio parole chiave nel contenuto del messaggio o il valore del campo "da" in un messaggio, per ricevere una notifica quando tali condizioni sono soddisfatte nei messaggi istantanei o nei messaggi di chat in chat persistente.</span><span class="sxs-lookup"><span data-stu-id="46f06-111">By using client-side filters, users can define conditions—such as keywords in message content, or the value of the "from" field in a message—to receive notification when those conditions are met in Persistent Chat instant messages or chat room messages.</span></span> <span data-ttu-id="46f06-112">In questo modo, gli utenti possono rimanere aggiornati sul contenuto che più gli interessa.</span><span class="sxs-lookup"><span data-stu-id="46f06-112">This way, users can stay up-to-date with the content that interests them most.</span></span>

  - <span data-ttu-id="46f06-113">Migliorare le comunicazioni con l'organizzazione estesa.</span><span class="sxs-lookup"><span data-stu-id="46f06-113">Improve communication with their extended organization.</span></span> <span data-ttu-id="46f06-114">Semplificando la collaborazione su argomenti di lunga durata con altri utenti dell'organizzazione e fornendo un posto persistente per la condivisione delle informazioni, la chat persistente contribuisce a migliorare la comunicazione.</span><span class="sxs-lookup"><span data-stu-id="46f06-114">By making it easy to collaborate over long-running topics with others in the organization, and by providing a persistent place to share information, Persistent Chat helps improve communication.</span></span>

  - <span data-ttu-id="46f06-115">Ridurre il sovraccarico di informazioni.</span><span class="sxs-lookup"><span data-stu-id="46f06-115">Reduce information overload.</span></span> <span data-ttu-id="46f06-116">Gli utenti possono seguire le chat room e i messaggi di maggiore interesse utilizzando filtri sul fianco del client e possono aggiungere chat room che desiderano seguire nell'elenco dei contatti.</span><span class="sxs-lookup"><span data-stu-id="46f06-116">Users can follow chat rooms and messages of most interest by using client-side filters, and can add chat rooms they want to follow to their contact list.</span></span>

  - <span data-ttu-id="46f06-117">Migliorare la diffusione di conoscenze e informazioni importanti.</span><span class="sxs-lookup"><span data-stu-id="46f06-117">Increase dispersion of important knowledge and information.</span></span> <span data-ttu-id="46f06-118">È possibile includere nelle conversazioni documenti e collegamenti disponibili per tutto il team.</span><span class="sxs-lookup"><span data-stu-id="46f06-118">Documents and links can be included within conversations for access by all the team.</span></span> <span data-ttu-id="46f06-119">Attraverso l'invio di domande a un team più esteso, gli utenti possono beneficiare delle risposte fornite da esperti di materie specifiche.</span><span class="sxs-lookup"><span data-stu-id="46f06-119">By posting questions to a broader team, users can benefit from responses by subject matter experts.</span></span> <span data-ttu-id="46f06-120">L'integrazione con altri sistemi informativi consente di comunicare facilmente i dati dell'organizzazione a gruppi di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="46f06-120">Integration with other information systems enables important organizational data to be easily communicated to large groups.</span></span>

<span data-ttu-id="46f06-121">Per abilitare le chat room in Lync Server 2013, distribuire Lync Server 2013 Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="46f06-121">To enable chat rooms in Lync Server 2013, deploy Lync Server 2013 Persistent Chat.</span></span> <span data-ttu-id="46f06-122">Per informazioni sull'abilitazione delle chat room, vedere la Guida di <https://go.microsoft.com/fwlink/p/?linkid=270945>Persistent Chat all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="46f06-122">For information about enabling chat rooms, see the Persistent Chat Help at <https://go.microsoft.com/fwlink/p/?linkid=270945>.</span></span> <span data-ttu-id="46f06-123">Se gli utenti sono abilitati per Lync Server e il supporto di Lync Server è distribuito, gli utenti possono installare e utilizzare Lync 2013 Persistent Chat per fornire il supporto per la chat room.</span><span class="sxs-lookup"><span data-stu-id="46f06-123">If users are enabled for Lync Server, and Lync Server support is deployed, users can install and use Lync 2013 Persistent Chat to provide chat room support.</span></span>

<span data-ttu-id="46f06-124">Se l'organizzazione è tenuta a seguire le normative di conformità, è possibile distribuire il servizio di conformità di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="46f06-124">If your organization is required to follow compliance regulations, you can optionally deploy Persistent Chat Compliance service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

