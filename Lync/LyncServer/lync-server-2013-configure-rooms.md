---
title: 'Lync Server 2013: configurare le chat room'
description: 'Lync Server 2013: configurare le chat room.'
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
ms.openlocfilehash: e9f5b2ece8cf436fe69c000da73871cb92686d82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542772"
---
# <a name="configure-rooms-in-lync-server-2013"></a><span data-ttu-id="e4b79-103">Configurare le chat room in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4b79-103">Configure rooms in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4b79-104">_**Ultimo argomento modificato:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="e4b79-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="e4b79-105">La configurazione delle chat room permanenti è in genere gestita dagli utenti o da altri team centrali tramite l'interfaccia della riga di comando di Windows PowerShell. un amministratore in genere non gestisce le chat room.</span><span class="sxs-lookup"><span data-stu-id="e4b79-105">Configuring Persistent Chat rooms is commonly handled by users or other central teams by using Windows PowerShell command-line interface; an administrator typically does not manage chat rooms.</span></span> <span data-ttu-id="e4b79-106">Tuttavia, se è necessario creare e gestire le chat room, è possibile utilizzare l'interfaccia della riga di comando di Windows PowerShell oppure aggiungere se stessi come membri di una chat room e utilizzare il client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e4b79-106">However, if you have to create and manage chat rooms, you can use the Windows PowerShell command-line interface, or add yourself as a member to a chat room and use the Lync 2013 client.</span></span>

<span data-ttu-id="e4b79-107">Per informazioni dettagliate sulla configurazione delle chat room tramite l'interfaccia della riga di comando di Windows PowerShell, vedere la sezione "gestione sala" in [configurazione del server Chat persistente tramite i cmdlet di Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="e4b79-107">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<div>

## <a name="managing-data-in-chat-rooms"></a><span data-ttu-id="e4b79-108">Gestione dei dati nelle chat room</span><span class="sxs-lookup"><span data-stu-id="e4b79-108">Managing Data in Chat Rooms</span></span>

<span data-ttu-id="e4b79-109">Il server Chat persistente consente agli utenti di collaborare inviando messaggi nelle chat room permanenti.</span><span class="sxs-lookup"><span data-stu-id="e4b79-109">Persistent Chat Server lets users collaborate by posting messages into Persistent Chat rooms.</span></span> <span data-ttu-id="e4b79-110">I dati restano sul server, e i membri della chat room possono accedere ai dati, compresi quelli della cronologia.</span><span class="sxs-lookup"><span data-stu-id="e4b79-110">The data is persisted on the server, and members of the room can have access to the data, including historical data.</span></span> <span data-ttu-id="e4b79-111">Tuttavia, utenti con ruoli diversi avranno un tipo di accesso diverso ai dati sul server, come illustrato nell'elenco di seguito.</span><span class="sxs-lookup"><span data-stu-id="e4b79-111">However, users with different roles have different access to the persisted data, as outlined in the following list.</span></span>

  - <span data-ttu-id="e4b79-p103">Gli amministratori possono eliminare dalla chat room il contenuto meno recente, ad esempio il contenuto pubblicato prima di una certa data, affinché il database non raggiunga dimensioni troppo elevate. Possono inoltre eliminare o spostare messaggi considerati inappropriati per una particolare chat room.</span><span class="sxs-lookup"><span data-stu-id="e4b79-p103">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large. Or, they can remove or replace messages that are considered inappropriate for a particular chat room.</span></span>

  - <span data-ttu-id="e4b79-114">Gli utenti finali, compresi gli autori dei messaggi, non possono eliminare il contenuto da una chat room.</span><span class="sxs-lookup"><span data-stu-id="e4b79-114">End users, including message authors, cannot delete content from any chat room.</span></span>

  - <span data-ttu-id="e4b79-p104">I gestori di chat room possono disattivare le chat room, ma non eliminarle. Solo gli amministratori possono eliminare una chat room dopo che è stata creata.</span><span class="sxs-lookup"><span data-stu-id="e4b79-p104">Chat room managers can disable rooms, but cannot delete rooms. Only administrators can delete a chat room after it has been created.</span></span>

<span data-ttu-id="e4b79-117">Dopo avere eliminato un messaggio, non è possibile annullare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="e4b79-117">When a message is deleted, you cannot undo the action.</span></span> <span data-ttu-id="e4b79-118">Tuttavia, se esiste un backup, è possibile ripristinare i messaggi eliminati.</span><span class="sxs-lookup"><span data-stu-id="e4b79-118">However, deleted messages can be restored if there is a backup.</span></span> <span data-ttu-id="e4b79-119">Se un server di conformità di Persistent Chat è abilitato, i messaggi obsoleti vengono salvati nel database di conformità.</span><span class="sxs-lookup"><span data-stu-id="e4b79-119">If a Persistent Chat Compliance server is enabled, old messages are persisted in the compliance database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e4b79-120">L'utilizzo di questo tipo di dati della chat room si applica all'applicazione API del server di chat persistente di Lync Server 2013, ad eccezione del caso in cui è coinvolto il ruolo di amministratore.</span><span class="sxs-lookup"><span data-stu-id="e4b79-120">This chat room data usage applies to the Lync Server 2013, Persistent Chat Server API application, except for the case when the administrator role is involved.</span></span> <span data-ttu-id="e4b79-121">L'API del server Chat persistente non può essere utilizzata per eseguire le operazioni dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="e4b79-121">The Persistent Chat Server API cannot be used to do any of the administrator’s operations.</span></span> <span data-ttu-id="e4b79-122">È necessario eseguire queste operazioni in Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e4b79-122">You must perform these operations in the Lync Server Management Shell.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

