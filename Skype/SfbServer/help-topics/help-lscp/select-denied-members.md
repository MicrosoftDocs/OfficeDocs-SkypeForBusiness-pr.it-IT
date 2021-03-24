---
title: Selezionare membri non consentiti
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
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: Un amministratore di Persistent Chat può creare e gestire categorie di chat room. Come parte della creazione e della gestione delle categorie di chat room, un amministratore di Persistent Chat può configurare entità (gruppi/contenitori/utenti di Servizi di dominio Active Directory) che hanno accesso per essere membri/creatori di chat room di una determinata categoria. Un amministratore di Persistent Chat può anche aggiungere DeniedMembers a una categoria e questi diventano esclusioni esplicite all'elenco di elementi consentiti. DeniedMembers esegue l'override di ciò che è in AllowedMembers.
ms.openlocfilehash: 5a31716c2fae15c6216ed050b543673479415a76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107962"
---
# <a name="select-denied-members"></a><span data-ttu-id="33b4a-106">Selezionare membri non consentiti</span><span class="sxs-lookup"><span data-stu-id="33b4a-106">Select Denied Members</span></span>

<span data-ttu-id="33b4a-107">Un amministratore di Persistent Chat può creare e gestire categorie di chat room.</span><span class="sxs-lookup"><span data-stu-id="33b4a-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="33b4a-108">Come parte della creazione e della gestione delle categorie di chat room, un amministratore di Persistent Chat può configurare entità (gruppi/contenitori/utenti di Servizi di dominio Active Directory) che hanno accesso per essere membri/creatori di chat room di una determinata categoria.</span><span class="sxs-lookup"><span data-stu-id="33b4a-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="33b4a-109">Un amministratore di Persistent Chat può anche aggiungere DeniedMembers a una categoria e questi diventano esclusioni esplicite all'elenco di elementi consentiti.</span><span class="sxs-lookup"><span data-stu-id="33b4a-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="33b4a-110">DeniedMembers esegue l'override di ciò che è in AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="33b4a-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="33b4a-111">Attività eseguibili</span><span class="sxs-lookup"><span data-stu-id="33b4a-111">Tasks that you can perform</span></span>

<span data-ttu-id="33b4a-112">Nella pagina **Seleziona membri non consentiti** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="33b4a-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="33b4a-113">Configurare le categorie</span><span class="sxs-lookup"><span data-stu-id="33b4a-113">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="33b4a-114">Nuove caratteristiche del server chat persistente</span><span class="sxs-lookup"><span data-stu-id="33b4a-114">New Persistent Chat Server Features</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

<span data-ttu-id="33b4a-115">Per informazioni dettagliate sulle diverse procedure che è possibile eseguire utilizzando il Pannello di controllo di Skype for Business Server, vedere [Manage Skype for Business Server 2015.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="33b4a-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="33b4a-116">Per configurare le categorie delle chat room</span><span class="sxs-lookup"><span data-stu-id="33b4a-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="33b4a-117">In **Appartenenza**, nella **sezione Membri** negati aggiungere o rimuovere utenti e altre entità di Active Directory associate ai membri negati dalla chat room.</span><span class="sxs-lookup"><span data-stu-id="33b4a-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="33b4a-118">Per informazioni dettagliate sulle funzionalità e sulle funzionalità del server Chat persistente, vedere [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="33b4a-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="33b4a-119">Per informazioni dettagliate sull'utilizzo delle configurazioni del server Chat persistente, vedere [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) nella documentazione relativa alla distribuzione e [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="33b4a-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="33b4a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33b4a-120">See also</span></span>

[<span data-ttu-id="33b4a-121">Informazioni sull'appartenenza di chat persistente</span><span class="sxs-lookup"><span data-stu-id="33b4a-121">Understanding Persistent Chat Membership</span></span>](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)