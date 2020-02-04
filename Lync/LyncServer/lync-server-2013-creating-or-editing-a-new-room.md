---
title: 'Lync Server 2013: Creazione o modifica di una nuova chat room'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bd0fdbce300f417764e093fec3acb8705b2d17b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a><span data-ttu-id="88b49-102">Creazione o modifica di una nuova chat room in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88b49-102">Creating or editing a new room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88b49-103">_**Argomento Ultima modifica:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="88b49-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="88b49-104">La configurazione delle chat room permanenti viene comunemente gestita dagli utenti; un amministratore della chat persistente in genere non configura né gestisce le chat room.</span><span class="sxs-lookup"><span data-stu-id="88b49-104">Configuring Persistent Chat rooms is commonly handled by users; a Persistent Chat administrator typically does not configure or manage chat rooms.</span></span> <span data-ttu-id="88b49-105">I cmdlet di Windows PowerShell per la gestione delle sale sono disponibili solo per gli amministratori di **CsPersistentChatAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="88b49-105">Windows PowerShell cmdlets to manage rooms are available only to **CsPersistentChatAdministrator** Administrators.</span></span>

<span data-ttu-id="88b49-106">Gli utenti che sono **creatori** in una determinata categoria possono usare il client Lync per creare e gestire le sale.</span><span class="sxs-lookup"><span data-stu-id="88b49-106">Users who are **Creators** in any given category can use the Lync client to create and manage rooms.</span></span> <span data-ttu-id="88b49-107">Gli utenti designati come responsabili di una chat room possono anche eseguire la gestione della sala, ad esempio modificare le proprietà della sala o l'appartenenza.</span><span class="sxs-lookup"><span data-stu-id="88b49-107">Users who have been designated as managers for a specific chat room can also perform ongoing management of the room, such as editing the room properties or membership.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="88b49-108">Gli amministratori della chat persistente possono essere anche creatori e non sono soggetti alle restrizioni imposte ai creatori.</span><span class="sxs-lookup"><span data-stu-id="88b49-108">Persistent Chat administrators can also be Creators, and they are not subject to the restrictions placed on Creators.</span></span>



</div>

<span data-ttu-id="88b49-109">Facoltativamente, se si è un amministratore di chat persistente, è possibile usare un'interfaccia utente per creare e gestire le chat room anziché i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88b49-109">Optionally, if you are a Persistent Chat administrator, you can employ a user interface to create and manage chat rooms instead of using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="88b49-110">A tale scopo, abilitare SIP per un amministratore per il server di chat persistente e quindi usare il client Lync per creare e gestire chat room.</span><span class="sxs-lookup"><span data-stu-id="88b49-110">To do this, SIP-enable an administrator for Persistent Chat Server, and then use the Lync client to create and manage chat rooms.</span></span>

<span data-ttu-id="88b49-111">Se si vuole creare un flusso di lavoro personalizzato per la gestione delle room per gli utenti, è possibile impostare la proprietà **RoomManagementUrl** sulla configurazione del server di chat persistente per reindirizzare gli utenti alla soluzione personalizzata dal client Lync.</span><span class="sxs-lookup"><span data-stu-id="88b49-111">If you want to create a custom room management workflow for your users, you can set the **RoomManagementUrl** property on your Persistent Chat Server configuration to redirect users to your custom solution from the Lync client.</span></span>

<span data-ttu-id="88b49-112">Per informazioni dettagliate sulla configurazione delle chat room tramite l'interfaccia della riga di comando di Windows PowerShell, vedere "gestione sala" nella [configurazione del server di chat persistente usando i cmdlet di Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="88b49-112">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="88b49-113">Per informazioni dettagliate sulla configurazione delle chat room, vedere [configurare le sale in Lync Server 2013](lync-server-2013-configure-rooms.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="88b49-113">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88b49-114">Il server di chat persistente consente agli utenti di creare e gestire chat room per un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="88b49-114">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="88b49-115">Gli utenti non possono tuttavia creare o gestire chat room in altri siti all'interno della stessa topologia.</span><span class="sxs-lookup"><span data-stu-id="88b49-115">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="88b49-116">Assicurati di specificare i creatori e i responsabili della chat room per tutti i siti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="88b49-116">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="88b49-117">Gli utenti ospitati in un dispositivo Survivable Branch di Lync Server non riescono a creare nuove chat room o a visualizzare la scheda della sala per le camere esistenti.</span><span class="sxs-lookup"><span data-stu-id="88b49-117">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

