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
ms.openlocfilehash: 71b856b4c5199acacd0ed7a3fdf41ed5ab92f59d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="da7ae-102">Panoramica del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da7ae-102">Overview of Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da7ae-103">_**Argomento Ultima modifica:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="da7ae-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="da7ae-104">Lync Server 2013, il server di chat persistente consente agli utenti di partecipare a conversazioni multiparte, basate su argomenti che persistono nel tempo.</span><span class="sxs-lookup"><span data-stu-id="da7ae-104">Lync Server 2013, Persistent Chat Server enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="da7ae-105">Il server di chat persistente può aiutare l'organizzazione a eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="da7ae-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="da7ae-106">Migliorare la comunicazione tra team geograficamente dispersivi e interfunzionali.</span><span class="sxs-lookup"><span data-stu-id="da7ae-106">Improve communication between geographically dispersed and cross-functional teams.</span></span> <span data-ttu-id="da7ae-107">Usando la chat persistente, i team possono condividere efficacemente informazioni, idee e decisioni tra loro.</span><span class="sxs-lookup"><span data-stu-id="da7ae-107">By using Persistent Chat, teams can efficiently share information, ideas, and decisions with one another.</span></span> <span data-ttu-id="da7ae-108">I messaggi inviati alle chat room (Forum di discussione) possono essere mantenuti (ovvero possono essere disponibili nel tempo), in modo che gli utenti provenienti da sedi e reparti diversi possano partecipare, anche quando non sono contemporaneamente online.</span><span class="sxs-lookup"><span data-stu-id="da7ae-108">The messages posted to chat rooms (discussion forums) can persist (that is, can be available over time), so that people from different locations and departments can participate, even when they are not simultaneously online.</span></span> <span data-ttu-id="da7ae-109">Quando un utente si connette a una chat room, il backchat (un numero configurabile di messaggi della cronologia chat) viene caricato automaticamente nella chat room per consentire all'utente un contesto per la conversazione.</span><span class="sxs-lookup"><span data-stu-id="da7ae-109">When a user connects to a chat room, backchat (a configurable number of chat-history messages) is automatically loaded in the chat room to give the user a context for the conversation.</span></span>

  - <span data-ttu-id="da7ae-110">Migliorare la consapevolezza delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="da7ae-110">Improve information awareness.</span></span> <span data-ttu-id="da7ae-111">Usando i filtri sul lato client, gli utenti possono definire condizioni, ad esempio parole chiave nel contenuto del messaggio o il valore del campo "da" in un messaggio, per ricevere una notifica quando tali condizioni vengono soddisfatte in messaggi istantanei o messaggi della chat room permanenti.</span><span class="sxs-lookup"><span data-stu-id="da7ae-111">By using client-side filters, users can define conditions—such as keywords in message content, or the value of the "from" field in a message—to receive notification when those conditions are met in Persistent Chat instant messages or chat room messages.</span></span> <span data-ttu-id="da7ae-112">In questo modo, gli utenti possono tenersi aggiornati con il contenuto che più li interessa.</span><span class="sxs-lookup"><span data-stu-id="da7ae-112">This way, users can stay up-to-date with the content that interests them most.</span></span>

  - <span data-ttu-id="da7ae-113">Migliorare la comunicazione con l'organizzazione estesa.</span><span class="sxs-lookup"><span data-stu-id="da7ae-113">Improve communication with their extended organization.</span></span> <span data-ttu-id="da7ae-114">Semplificando la collaborazione per gli argomenti a esecuzione prolungata con altri utenti dell'organizzazione e fornendo una posizione persistente per condividere informazioni, la chat persistente aiuta a migliorare la comunicazione.</span><span class="sxs-lookup"><span data-stu-id="da7ae-114">By making it easy to collaborate over long-running topics with others in the organization, and by providing a persistent place to share information, Persistent Chat helps improve communication.</span></span>

  - <span data-ttu-id="da7ae-115">Ridurre il sovraccarico di informazioni.</span><span class="sxs-lookup"><span data-stu-id="da7ae-115">Reduce information overload.</span></span> <span data-ttu-id="da7ae-116">Gli utenti possono seguire le chat room e i messaggi di maggiore interesse usando filtri lato client e possono aggiungere chat room che vogliono seguire all'elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="da7ae-116">Users can follow chat rooms and messages of most interest by using client-side filters, and can add chat rooms they want to follow to their contact list.</span></span>

  - <span data-ttu-id="da7ae-117">Aumentare la dispersione di conoscenze e informazioni importanti.</span><span class="sxs-lookup"><span data-stu-id="da7ae-117">Increase dispersion of important knowledge and information.</span></span> <span data-ttu-id="da7ae-118">I documenti e i collegamenti possono essere inclusi nelle conversazioni per l'accesso da parte di tutto il team.</span><span class="sxs-lookup"><span data-stu-id="da7ae-118">Documents and links can be included within conversations for access by all the team.</span></span> <span data-ttu-id="da7ae-119">Inviando domande a un team più ampio, gli utenti possono trarre vantaggio dalle risposte degli esperti in materia.</span><span class="sxs-lookup"><span data-stu-id="da7ae-119">By posting questions to a broader team, users can benefit from responses by subject matter experts.</span></span> <span data-ttu-id="da7ae-120">L'integrazione con altri sistemi informativi consente di comunicare facilmente i dati dell'organizzazione a gruppi di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="da7ae-120">Integration with other information systems enables important organizational data to be easily communicated to large groups.</span></span>

<span data-ttu-id="da7ae-121">Per abilitare le chat room in Lync Server 2013, distribuire la chat persistente di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da7ae-121">To enable chat rooms in Lync Server 2013, deploy Lync Server 2013 Persistent Chat.</span></span> <span data-ttu-id="da7ae-122">Per informazioni sull'abilitazione delle chat room, vedere la Guida di <http://go.microsoft.com/fwlink/p/?linkid=270945>chat persistente in.</span><span class="sxs-lookup"><span data-stu-id="da7ae-122">For information about enabling chat rooms, see the Persistent Chat Help at <http://go.microsoft.com/fwlink/p/?linkid=270945>.</span></span> <span data-ttu-id="da7ae-123">Se gli utenti sono abilitati per Lync Server e il supporto di Lync Server è distribuito, gli utenti possono installare e usare la chat persistente di Lync 2013 per consentire il supporto di chat room.</span><span class="sxs-lookup"><span data-stu-id="da7ae-123">If users are enabled for Lync Server, and Lync Server support is deployed, users can install and use Lync 2013 Persistent Chat to provide chat room support.</span></span>

<span data-ttu-id="da7ae-124">Se l'organizzazione è tenuta a seguire le regole di conformità, è possibile distribuire facoltativamente il servizio di conformità della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="da7ae-124">If your organization is required to follow compliance regulations, you can optionally deploy Persistent Chat Compliance service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

