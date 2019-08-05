---
title: Selezionare i membri consentiti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: La creazione e la gestione di chat room persistenti è molto più semplice con l'uso corretto delle categorie. Un amministratore della chat persistente può definire AllowedMembers e creatori per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti della chat room che verranno applicati a tutte le chat room create nella categoria. Gli amministratori della chat persistente creano e gestiscono categorie usando il pannello di controllo o i cmdlet di Windows PowerShell.
ms.openlocfilehash: dedc022853738ad02b4da2ce0ab2cdc7ccbee576
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189440"
---
# <a name="select-allowed-members"></a><span data-ttu-id="85122-105">Selezionare i membri consentiti</span><span class="sxs-lookup"><span data-stu-id="85122-105">Select Allowed Members</span></span>

<span data-ttu-id="85122-106">La creazione e la gestione di chat room persistenti è molto più semplice con l'uso corretto delle categorie.</span><span class="sxs-lookup"><span data-stu-id="85122-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="85122-107">Un amministratore della chat persistente può definire **AllowedMembers** e **creatori** per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti della chat room che verranno applicati a tutte le chat room create nella categoria.</span><span class="sxs-lookup"><span data-stu-id="85122-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="85122-108">Gli amministratori della chat persistente creano e gestiscono categorie usando il pannello di controllo o i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85122-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="85122-109">Gli utenti, le unità organizzative e i gruppi di utenti identificati come creatori della categoria sono gli unici autorizzati a creare chat room nella categoria.</span><span class="sxs-lookup"><span data-stu-id="85122-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="85122-110">Dopo aver creato la categoria, possono scegliere utenti, unità organizzative e gruppi di utenti dall'elenco di **AllowedMembers** della categoria come Manager e membri della chat room per gestire e partecipare alla sala.</span><span class="sxs-lookup"><span data-stu-id="85122-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="85122-111">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="85122-111">Tasks that you can perform</span></span>

<span data-ttu-id="85122-112">Nella pagina **Selezionare i membri consentiti** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="85122-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="85122-113">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="85122-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="85122-114">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="85122-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="85122-115">Per informazioni dettagliate sulle diverse procedure che è possibile eseguire tramite il pannello di controllo di Skype for Business Server, vedere [gestire Skype for Business server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="85122-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="85122-116">Per configurare le categorie delle chat room</span><span class="sxs-lookup"><span data-stu-id="85122-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="85122-117">In **appartenenza**, nella sezione **consentiti membri** , aggiungere o rimuovere utenti e altre entità di servizi di dominio Active Directory (utenti, gruppi di distribuzione, unità organizzative e così via) che sono autorizzati ad essere aggiunti come membri delle chat room appartenenza alla categoria.</span><span class="sxs-lookup"><span data-stu-id="85122-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="85122-118">Le entità consentite da una categoria possono cercare le chat della categoria (a meno che la chat non sia nascosta, caso in cui solo i membri della chat possono cercarla nella directory).</span><span class="sxs-lookup"><span data-stu-id="85122-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="85122-119">Per informazioni dettagliate sulle funzionalità e le funzionalità del server di chat persistente, vedere [Panoramica del server di chat persistente](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="85122-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="85122-120">Per informazioni dettagliate sull'uso delle configurazioni del server di chat persistente, vedere [configurazione del server di chat persistente](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) nella documentazione di distribuzione e [gestione di Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="85122-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="85122-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85122-121">See also</span></span>

[<span data-ttu-id="85122-122">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="85122-122">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
