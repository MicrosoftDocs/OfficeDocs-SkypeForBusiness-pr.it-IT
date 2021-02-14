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
description: La creazione e la gestione delle chat room di Persistent Chat sono molto più semplici con l'uso corretto delle categorie. Un amministratore di Persistent Chat può definire AllowedMembers e Creators per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti delle chat room che verranno applicati a tutte le chat room create nella categoria. Gli amministratori di Persistent Chat creano e gestiscono categorie utilizzando il Pannello di controllo o Windows PowerShell cmdlet.
ms.openlocfilehash: 8c45a16f88bf20ab973927e17807b3241f20e942
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829136"
---
# <a name="select-allowed-members"></a><span data-ttu-id="5641a-105">Selezionare membri consentiti</span><span class="sxs-lookup"><span data-stu-id="5641a-105">Select Allowed Members</span></span>

<span data-ttu-id="5641a-106">La creazione e la gestione delle chat room di Persistent Chat sono molto più semplici con l'uso corretto delle categorie.</span><span class="sxs-lookup"><span data-stu-id="5641a-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="5641a-107">Un amministratore di Persistent Chat può definire **AllowedMembers** e **Creators** per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti delle chat room che verranno applicati a tutte le chat room create nella categoria.</span><span class="sxs-lookup"><span data-stu-id="5641a-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="5641a-108">Gli amministratori di Persistent Chat creano e gestiscono categorie utilizzando il Pannello di controllo o Windows PowerShell cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5641a-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="5641a-109">Utenti, unità organizzative e gruppi di utenti identificati come creatori della categoria sono gli unici individui e gruppi a cui è consentito creare chat nella categoria.</span><span class="sxs-lookup"><span data-stu-id="5641a-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="5641a-110">Dopo aver creato la categoria, possono scegliere utenti, unità organizzative e gruppi di utenti nell'elenco **AllowedMembers** della categoria come responsabili e membri della chat room per gestire e partecipare alla chat room.</span><span class="sxs-lookup"><span data-stu-id="5641a-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="5641a-111">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="5641a-111">Tasks that you can perform</span></span>

<span data-ttu-id="5641a-112">Nella pagina **Selezionare i membri consentiti** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="5641a-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="5641a-113">Configurare le categorie</span><span class="sxs-lookup"><span data-stu-id="5641a-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="5641a-114">Nuove caratteristiche del server chat persistente</span><span class="sxs-lookup"><span data-stu-id="5641a-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="5641a-115">Per informazioni dettagliate sulle diverse procedure che è possibile eseguire utilizzando il Pannello di controllo di Skype for Business Server, vedere [Gestire Skype for Business Server 2015.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="5641a-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="5641a-116">Per configurare le categorie delle chat room</span><span class="sxs-lookup"><span data-stu-id="5641a-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="5641a-117">In Appartenenza,  nella sezione Membri consentiti aggiungere o rimuovere utenti e altre entità di Servizi di dominio Active Directory (utenti, gruppi di distribuzione, unità organizzative e così via) che possono essere aggiunti come membri delle chat room appartenenti alla categoria.</span><span class="sxs-lookup"><span data-stu-id="5641a-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="5641a-118">Le entità consentite da una categoria possono cercare le chat della categoria (a meno che la chat non sia nascosta, caso in cui solo i membri della chat possono cercarla nella directory).</span><span class="sxs-lookup"><span data-stu-id="5641a-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="5641a-119">Per informazioni dettagliate sulle caratteristiche e sulle funzionalità del server Chat persistente, vedere [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="5641a-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="5641a-120">Per informazioni dettagliate sull'utilizzo delle configurazioni del server Chat persistente, vedere [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) nella documentazione relativa alla distribuzione e [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="5641a-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="5641a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5641a-121">See also</span></span>

[<span data-ttu-id="5641a-122">Informazioni sull'appartenenza di chat persistente</span><span class="sxs-lookup"><span data-stu-id="5641a-122">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
