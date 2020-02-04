---
title: 'Lync Server 2013: Gestione di categorie, chat room e componenti aggiuntivi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing categories, rooms, and add-ins
ms:assetid: a9807031-7369-4a51-9369-6f09bec24141
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412799(v=OCS.15)
ms:contentKeyID: 48185100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89d7caadc6ccc4bd7c1030a3e7020129be14a68f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-categories-rooms-and-add-ins-in-lync-server-2013"></a><span data-ttu-id="7cf1b-102">Gestione di categorie, chat room e componenti aggiuntivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cf1b-102">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cf1b-103">_**Argomento Ultima modifica:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="7cf1b-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="7cf1b-104">Nel pannello di controllo di Lync Server 2013 o tramite i cmdlet di Windows PowerShell gli amministratori della chat persistente possono usare la pagina della **chat persistente** per creare categorie e componenti aggiuntivi. Per la gestione delle chat room permanenti, gli amministratori possono usare i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7cf1b-104">In Lync Server 2013 Control Panel, or by using Windows PowerShell cmdlets, Persistent Chat Administrators can use the **Persistent Chat** page to create categories and add-ins. For managing Persistent Chat rooms, Administrators can use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="7cf1b-105">In alternativa, se l'amministratore della chat persistente è anche abilitato per SIP, può usare il client Lync per avviare una pagina Web per creare e gestire chat room.</span><span class="sxs-lookup"><span data-stu-id="7cf1b-105">Alternatively, if the Persistent Chat administrator is also SIP-enabled, they can use the Lync client to launch a web page to create and manage chat rooms.</span></span>

<span data-ttu-id="7cf1b-106">Gli argomenti seguenti descrivono come creare e usare le categorie e le chat room.</span><span class="sxs-lookup"><span data-stu-id="7cf1b-106">The following topics describe how to create and work with categories and chat rooms.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7cf1b-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="7cf1b-107">In This Section</span></span>

  - [<span data-ttu-id="7cf1b-108">Creazione o modifica di una nuova categoria in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cf1b-108">Creating or editing a new category in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-category.md)

  - [<span data-ttu-id="7cf1b-109">Creazione o modifica di una nuova chat room in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cf1b-109">Creating or editing a new room in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-room.md)

  - [<span data-ttu-id="7cf1b-110">Creazione di nuovi componenti aggiuntivi per le chat room in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cf1b-110">Creating new add-ins for rooms in Lync Server 2013</span></span>](lync-server-2013-creating-new-add-ins-for-rooms.md)

  - [<span data-ttu-id="7cf1b-111">Impostazione degli utenti autorizzati a inserire messaggi in una chat room auditorium in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cf1b-111">Setting who can post messages in an auditorium chat room in Lync Server 2013</span></span>](lync-server-2013-setting-who-can-post-messages-in-an-auditorium-chat-room.md)

  - [<span data-ttu-id="7cf1b-112">Disabilitazione o abilitazione di una chat room in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cf1b-112">Disabling or enabling a chat room in Lync Server 2013</span></span>](lync-server-2013-disabling-or-enabling-a-chat-room.md)

  - [<span data-ttu-id="7cf1b-113">Spostamento di una chat room da una categoria all'altra in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cf1b-113">Moving a chat room from one category to another in Lync Server 2013</span></span>](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)

  - [<span data-ttu-id="7cf1b-114">Eliminazione di una chat room o una categoria in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cf1b-114">Deleting a chat room or category in Lync Server 2013</span></span>](lync-server-2013-deleting-a-chat-room-or-category.md)

  - [<span data-ttu-id="7cf1b-115">Eliminazione di un messaggio o dei messaggi obsoleti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cf1b-115">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>](lync-server-2013-deleting-a-message-or-purging-obsolete-messages.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

