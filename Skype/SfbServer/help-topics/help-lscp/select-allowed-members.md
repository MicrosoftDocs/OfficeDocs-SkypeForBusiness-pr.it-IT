---
title: Selezionare i membri consentiti
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: La creazione e la gestione delle chat room persistenti è molto più semplice con l'uso corretto delle categorie. Un amministratore di Persistent Chat può definire AllowedMembers e Creators per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti delle chat room che verranno applicati a tutte le chat room create nella categoria. Gli amministratori di Persistent Chat creano e gestiscono categorie utilizzando il pannello di controllo o Windows PowerShell cmdlet.
ms.openlocfilehash: 47abbec64f6799a85f3f6123a898eeae00becbdb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107992"
---
# <a name="select-allowed-members"></a><span data-ttu-id="210c5-105">Selezionare membri consentiti</span><span class="sxs-lookup"><span data-stu-id="210c5-105">Select Allowed Members</span></span>

<span data-ttu-id="210c5-106">La creazione e la gestione delle chat room persistenti è molto più semplice con l'uso corretto delle categorie.</span><span class="sxs-lookup"><span data-stu-id="210c5-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="210c5-107">Un amministratore di Persistent Chat può definire **AllowedMembers** e **Creators** per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti delle chat room che verranno applicati a tutte le chat room create nella categoria.</span><span class="sxs-lookup"><span data-stu-id="210c5-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="210c5-108">Gli amministratori di Persistent Chat creano e gestiscono categorie utilizzando il pannello di controllo o Windows PowerShell cmdlet.</span><span class="sxs-lookup"><span data-stu-id="210c5-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="210c5-109">Utenti, unità organizzative e gruppi di utenti identificati come creatori della categoria sono gli unici individui e gruppi a cui è consentito creare chat nella categoria.</span><span class="sxs-lookup"><span data-stu-id="210c5-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="210c5-110">Dopo aver creato la categoria, possono scegliere utenti, unità organizzative e gruppi di utenti dall'elenco **AllowedMembers** della categoria come responsabili e membri della chat room per gestire e partecipare alla chat room.</span><span class="sxs-lookup"><span data-stu-id="210c5-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="210c5-111">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="210c5-111">Tasks that you can perform</span></span>

<span data-ttu-id="210c5-112">Nella pagina **Selezionare i membri consentiti** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="210c5-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="210c5-113">Configurare le categorie</span><span class="sxs-lookup"><span data-stu-id="210c5-113">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="210c5-114">Nuove caratteristiche del server chat persistente</span><span class="sxs-lookup"><span data-stu-id="210c5-114">New Persistent Chat Server Features</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

<span data-ttu-id="210c5-115">Per informazioni dettagliate sulle diverse procedure che è possibile eseguire utilizzando il Pannello di controllo di Skype for Business Server, vedere [Manage Skype for Business Server 2015.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="210c5-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="210c5-116">Per configurare le categorie delle chat room</span><span class="sxs-lookup"><span data-stu-id="210c5-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="210c5-117">In Appartenenza  , nella sezione Membri consentiti, aggiungere o rimuovere gli utenti e altre entità di Servizi di dominio Active Directory (utenti, gruppi di distribuzione, unità organizzative e così via) che possono essere aggiunti come membri delle chat room appartenenti alla categoria.</span><span class="sxs-lookup"><span data-stu-id="210c5-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="210c5-118">Le entità consentite da una categoria possono cercare le chat della categoria (a meno che la chat non sia nascosta, caso in cui solo i membri della chat possono cercarla nella directory).</span><span class="sxs-lookup"><span data-stu-id="210c5-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="210c5-119">Per informazioni dettagliate sulle funzionalità e sulle funzionalità del server Chat persistente, vedere [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="210c5-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="210c5-120">Per informazioni dettagliate sull'utilizzo delle configurazioni del server Chat persistente, vedere [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) nella documentazione relativa alla distribuzione e [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="210c5-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="210c5-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="210c5-121">See also</span></span>

[<span data-ttu-id="210c5-122">Informazioni sull'appartenenza di chat persistente</span><span class="sxs-lookup"><span data-stu-id="210c5-122">Understanding Persistent Chat Membership</span></span>](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)