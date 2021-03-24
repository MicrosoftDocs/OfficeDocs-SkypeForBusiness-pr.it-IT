---
title: Selezionare i creatori
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
- ms.lync.lscp.SelectCreators
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8d9ed6f-22ba-470e-b0b4-0da3cea5e961
description: La creazione e la gestione delle chat room persistenti è molto più semplice con l'uso corretto delle categorie. Un amministratore di Persistent Chat può definire AllowedMembers e Creators per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti delle chat room che verranno applicati a tutte le chat room create nella categoria. Gli amministratori di Persistent Chat creano e gestiscono categorie utilizzando il Pannello di controllo di Skype for Business Server o Windows PowerShell cmdlet.
ms.openlocfilehash: 7d98ff058251b8bd14eb37a0ae5ba633f5a99c48
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107952"
---
# <a name="select-creators"></a><span data-ttu-id="e00f4-105">Selezionare creatori</span><span class="sxs-lookup"><span data-stu-id="e00f4-105">Select Creators</span></span>

<span data-ttu-id="e00f4-106">La creazione e la gestione delle chat room persistenti è molto più semplice con l'uso corretto delle categorie.</span><span class="sxs-lookup"><span data-stu-id="e00f4-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="e00f4-107">Un amministratore di Persistent Chat può definire **AllowedMembers** e **Creators** per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti delle chat room che verranno applicati a tutte le chat room create nella categoria.</span><span class="sxs-lookup"><span data-stu-id="e00f4-107">A Persistent Chat administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="e00f4-108">Gli amministratori di Persistent Chat creano e gestiscono categorie utilizzando il Pannello di controllo di Skype for Business Server o Windows PowerShell cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e00f4-108">Persistent Chat administrators create and manage categories by using Skype for Business Server Control Panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="e00f4-109">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="e00f4-109">Tasks that you can perform</span></span>

<span data-ttu-id="e00f4-110">Nella pagina **Seleziona creatori**, è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="e00f4-110">You can perform the following tasks on the **Select Creators** page:</span></span>

- [<span data-ttu-id="e00f4-111">Configurare le categorie</span><span class="sxs-lookup"><span data-stu-id="e00f4-111">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="e00f4-112">Nuove caratteristiche del server chat persistente</span><span class="sxs-lookup"><span data-stu-id="e00f4-112">New Persistent Chat Server Features</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

<span data-ttu-id="e00f4-113">Per informazioni dettagliate sulle diverse procedure che è possibile eseguire utilizzando il Pannello di controllo di Skype for Business Server, vedere [Manage Skype for Business Server 2015.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="e00f4-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="e00f4-114">Per configurare le categorie delle chat room</span><span class="sxs-lookup"><span data-stu-id="e00f4-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="e00f4-115">In **Appartenenza,** nella **sezione Creatori,** aggiungere o rimuovere utenti e altre entità di Active Directory associate ai creatori per la categoria.</span><span class="sxs-lookup"><span data-stu-id="e00f4-115">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="e00f4-116">Per creatore si intende un utente con autorizzazioni per la creazione di chat room e l'assegnazione di membri e responsabili delle chat.</span><span class="sxs-lookup"><span data-stu-id="e00f4-116">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>



<span data-ttu-id="e00f4-117">Per informazioni dettagliate sulle funzionalità e sulle funzionalità del server Chat persistente, vedere [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="e00f4-117">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="e00f4-118">Per informazioni dettagliate sull'utilizzo delle configurazioni del server Chat persistente, vedere [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) nella documentazione relativa alla distribuzione e [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="e00f4-118">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="e00f4-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e00f4-119">See also</span></span>

[<span data-ttu-id="e00f4-120">Informazioni sull'appartenenza di chat persistente</span><span class="sxs-lookup"><span data-stu-id="e00f4-120">Understanding Persistent Chat Membership</span></span>](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)

[<span data-ttu-id="e00f4-121">Utilizzo di categorie per l'amministrazione del server chat persistente</span><span class="sxs-lookup"><span data-stu-id="e00f4-121">Using Categories to Administer Persistent Chat Server</span></span>](/previous-versions/office/lync-server-2013/using-categories-to-administer-persistent-chat-server)

[<span data-ttu-id="e00f4-122">Spostamento di una chat room da una categoria all'altra</span><span class="sxs-lookup"><span data-stu-id="e00f4-122">Moving a Chat Room from One Category to Another</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-moving-a-chat-room-from-one-category-to-another)

[<span data-ttu-id="e00f4-123">Creazione o modifica di una nuova chat room</span><span class="sxs-lookup"><span data-stu-id="e00f4-123">Creating or Editing a New Room</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-creating-or-editing-a-new-room)