---
title: 'Lync Server 2013: Configurare le chat room'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06fea4fcda27eaedd671d833a4f53ed0ddec67c6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a><span data-ttu-id="9a6a3-102">Configurare le chat room in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a6a3-102">Configure rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a6a3-103">_**Argomento Ultima modifica:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="9a6a3-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="9a6a3-104">La configurazione delle chat room permanenti viene comunemente gestita dagli utenti o da altri team centrali usando l'interfaccia della riga di comando di Windows PowerShell; un amministratore in genere non gestisce le chat room.</span><span class="sxs-lookup"><span data-stu-id="9a6a3-104">Configuring Persistent Chat rooms is commonly handled by users or other central teams by using Windows PowerShell command-line interface; an administrator typically does not manage chat rooms.</span></span> <span data-ttu-id="9a6a3-105">Tuttavia, se è necessario creare e gestire chat room, è possibile usare l'interfaccia della riga di comando di Windows PowerShell oppure aggiungersi come membro di una chat room e usare il client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9a6a3-105">However, if you have to create and manage chat rooms, you can use the Windows PowerShell command-line interface, or add yourself as a member to a chat room and use the Lync 2013 client.</span></span>

<span data-ttu-id="9a6a3-106">Per informazioni dettagliate sulla configurazione delle chat room tramite l'interfaccia della riga di comando di Windows PowerShell, vedere "gestione sala" nella [configurazione del server di chat persistente usando i cmdlet di Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="9a6a3-106">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<div>

## <a name="managing-data-in-chat-rooms"></a><span data-ttu-id="9a6a3-107">Gestione dei dati nelle chat room</span><span class="sxs-lookup"><span data-stu-id="9a6a3-107">Managing Data in Chat Rooms</span></span>

<span data-ttu-id="9a6a3-108">Il server di chat persistente consente agli utenti di collaborare pubblicando messaggi in chat room permanenti.</span><span class="sxs-lookup"><span data-stu-id="9a6a3-108">Persistent Chat Server lets users collaborate by posting messages into Persistent Chat rooms.</span></span> <span data-ttu-id="9a6a3-109">I dati vengono mantenuti nel server e i membri della sala possono avere accesso ai dati, inclusi i dati cronologici.</span><span class="sxs-lookup"><span data-stu-id="9a6a3-109">The data is persisted on the server, and members of the room can have access to the data, including historical data.</span></span> <span data-ttu-id="9a6a3-110">Tuttavia, gli utenti con ruoli diversi hanno accesso diverso ai dati persistenti, come illustrato nell'elenco seguente.</span><span class="sxs-lookup"><span data-stu-id="9a6a3-110">However, users with different roles have different access to the persisted data, as outlined in the following list.</span></span>

  - <span data-ttu-id="9a6a3-111">Gli amministratori possono eliminare il contenuto precedente, ad esempio il contenuto postato prima di una determinata data, da qualsiasi chat room per evitare che il database cresca troppo grande.</span><span class="sxs-lookup"><span data-stu-id="9a6a3-111">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="9a6a3-112">In alternativa, è possibile rimuovere o sostituire i messaggi considerati inappropriati per una particolare chat room.</span><span class="sxs-lookup"><span data-stu-id="9a6a3-112">Or, they can remove or replace messages that are considered inappropriate for a particular chat room.</span></span>

  - <span data-ttu-id="9a6a3-113">Gli utenti finali, inclusi gli autori dei messaggi, non possono eliminare il contenuto da qualsiasi chat room.</span><span class="sxs-lookup"><span data-stu-id="9a6a3-113">End users, including message authors, cannot delete content from any chat room.</span></span>

  - <span data-ttu-id="9a6a3-114">I responsabili delle chat room possono disabilitare le camere, ma non possono eliminare le camere.</span><span class="sxs-lookup"><span data-stu-id="9a6a3-114">Chat room managers can disable rooms, but cannot delete rooms.</span></span> <span data-ttu-id="9a6a3-115">Solo gli amministratori possono eliminare una chat room dopo che è stata creata.</span><span class="sxs-lookup"><span data-stu-id="9a6a3-115">Only administrators can delete a chat room after it has been created.</span></span>

<span data-ttu-id="9a6a3-116">Quando un messaggio viene eliminato, non è possibile annullare l'azione.</span><span class="sxs-lookup"><span data-stu-id="9a6a3-116">When a message is deleted, you cannot undo the action.</span></span> <span data-ttu-id="9a6a3-117">Tuttavia, i messaggi eliminati possono essere ripristinati se è presente un backup.</span><span class="sxs-lookup"><span data-stu-id="9a6a3-117">However, deleted messages can be restored if there is a backup.</span></span> <span data-ttu-id="9a6a3-118">Se è abilitato un server di conformità della chat persistente, i vecchi messaggi vengono mantenuti nel database di conformità.</span><span class="sxs-lookup"><span data-stu-id="9a6a3-118">If a Persistent Chat Compliance server is enabled, old messages are persisted in the compliance database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a6a3-119">L'utilizzo dei dati delle chat room si applica a Lync Server 2013, l'applicazione API del server di chat persistente, fatta eccezione per il caso in cui è coinvolto il ruolo di amministratore.</span><span class="sxs-lookup"><span data-stu-id="9a6a3-119">This chat room data usage applies to the Lync Server 2013, Persistent Chat Server API application, except for the case when the administrator role is involved.</span></span> <span data-ttu-id="9a6a3-120">Non è possibile usare l'API del server di chat persistente per eseguire le operazioni dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="9a6a3-120">The Persistent Chat Server API cannot be used to do any of the administrator’s operations.</span></span> <span data-ttu-id="9a6a3-121">È necessario eseguire queste operazioni in Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9a6a3-121">You must perform these operations in the Lync Server Management Shell.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

