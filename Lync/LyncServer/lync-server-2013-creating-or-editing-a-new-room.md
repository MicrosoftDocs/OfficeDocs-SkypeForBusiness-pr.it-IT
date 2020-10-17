---
title: 'Lync Server 2013: creazione o modifica di una nuova chat room'
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
ms.openlocfilehash: a6f0abaf45034918873a17adc8a0f396ddc5d6fb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516843"
---
# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a><span data-ttu-id="1248b-102">Creazione o modifica di una nuova sala in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1248b-102">Creating or editing a new room in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1248b-103">_**Ultimo argomento modificato:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="1248b-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="1248b-104">La configurazione delle chat room permanenti è in genere gestita dagli utenti. un amministratore di chat persistente in genere non configura o gestisce le chat room.</span><span class="sxs-lookup"><span data-stu-id="1248b-104">Configuring Persistent Chat rooms is commonly handled by users; a Persistent Chat administrator typically does not configure or manage chat rooms.</span></span> <span data-ttu-id="1248b-105">I cmdlet di Windows PowerShell per la gestione delle chat sono disponibili solo per gli amministratori di **ruolo CsPersistentChatAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="1248b-105">Windows PowerShell cmdlets to manage rooms are available only to **CsPersistentChatAdministrator** Administrators.</span></span>

<span data-ttu-id="1248b-106">Gli utenti che sono **creatori** di una determinata categoria possono utilizzare il client Lync per creare e gestire le chat room.</span><span class="sxs-lookup"><span data-stu-id="1248b-106">Users who are **Creators** in any given category can use the Lync client to create and manage rooms.</span></span> <span data-ttu-id="1248b-107">Gli utenti designati come responsabili di una specifica chat room possono inoltre occuparsi della gestione continuata della chat room, ad esempio modificandone le proprietà o i membri.</span><span class="sxs-lookup"><span data-stu-id="1248b-107">Users who have been designated as managers for a specific chat room can also perform ongoing management of the room, such as editing the room properties or membership.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="1248b-108">Gli amministratori di chat persistente possono anche essere creatori e non sono soggetti alle restrizioni applicate ai creatori.</span><span class="sxs-lookup"><span data-stu-id="1248b-108">Persistent Chat administrators can also be Creators, and they are not subject to the restrictions placed on Creators.</span></span>



</div>

<span data-ttu-id="1248b-109">Facoltativamente, se si è un amministratore di chat persistente, è possibile utilizzare un'interfaccia utente per creare e gestire le chat room invece di usare i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1248b-109">Optionally, if you are a Persistent Chat administrator, you can employ a user interface to create and manage chat rooms instead of using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="1248b-110">A tale scopo, abilitare SIP un amministratore per il server Chat persistente e quindi utilizzare il client Lync per creare e gestire le chat room.</span><span class="sxs-lookup"><span data-stu-id="1248b-110">To do this, SIP-enable an administrator for Persistent Chat Server, and then use the Lync client to create and manage chat rooms.</span></span>

<span data-ttu-id="1248b-111">Se si desidera creare un flusso di lavoro per la gestione delle sale personalizzato per gli utenti, è possibile impostare la proprietà **RoomManagementUrl** nella configurazione del server Chat persistente per reindirizzare gli utenti alla soluzione personalizzata dal client Lync.</span><span class="sxs-lookup"><span data-stu-id="1248b-111">If you want to create a custom room management workflow for your users, you can set the **RoomManagementUrl** property on your Persistent Chat Server configuration to redirect users to your custom solution from the Lync client.</span></span>

<span data-ttu-id="1248b-112">Per informazioni dettagliate sulla configurazione delle chat room tramite l'interfaccia della riga di comando di Windows PowerShell, vedere la sezione "gestione sala" in [configurazione del server Chat persistente tramite i cmdlet di Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="1248b-112">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="1248b-113">Per informazioni dettagliate sulla configurazione delle chat room, vedere [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1248b-113">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1248b-114">Il server Chat persistente consente agli utenti di creare e gestire la chat room per un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="1248b-114">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="1248b-115">Tuttavia, gli utenti non possono creare o gestire chat room su altri siti all'interno della stessa topologia.</span><span class="sxs-lookup"><span data-stu-id="1248b-115">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="1248b-116">Assicurarsi di specificare i creatori e i responsabili delle chat room per tutti i siti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1248b-116">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1248b-117">Gli utenti ospitati in un Survivable Branch Appliance di Lync Server non sono in grado di creare nuove chat room o di visualizzare la scheda sala per le sale esistenti.</span><span class="sxs-lookup"><span data-stu-id="1248b-117">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

