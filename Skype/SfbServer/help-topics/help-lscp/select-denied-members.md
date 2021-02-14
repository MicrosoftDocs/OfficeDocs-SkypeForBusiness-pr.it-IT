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
description: Un amministratore di Persistent Chat può creare e gestire categorie di chat room. Come parte della creazione e della gestione delle categorie di chat room, un amministratore di Persistent Chat può configurare entità (gruppi/contenitori/utenti di Servizi di dominio Active Directory) che hanno accesso come membri/creatori di chat room di una determinata categoria. Un amministratore di Persistent Chat può inoltre aggiungere membri non consentiti a una categoria che diventano esclusioni esplicite all'elenco dei membri consentiti. DeniedMembers ha la precedenza su ciò che è in AllowedMembers.
ms.openlocfilehash: c5f942723937fe2da28025fba5da1fc7ee121c83
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814576"
---
# <a name="select-denied-members"></a><span data-ttu-id="70533-106">Selezionare membri non consentiti</span><span class="sxs-lookup"><span data-stu-id="70533-106">Select Denied Members</span></span>

<span data-ttu-id="70533-107">Un amministratore di Persistent Chat può creare e gestire categorie di chat room.</span><span class="sxs-lookup"><span data-stu-id="70533-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="70533-108">Come parte della creazione e della gestione delle categorie di chat room, un amministratore di Persistent Chat può configurare entità (gruppi/contenitori/utenti di Servizi di dominio Active Directory) che hanno accesso come membri/creatori di chat room di una determinata categoria.</span><span class="sxs-lookup"><span data-stu-id="70533-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="70533-109">Un amministratore di Persistent Chat può inoltre aggiungere membri non consentiti a una categoria che diventano esclusioni esplicite all'elenco dei membri consentiti.</span><span class="sxs-lookup"><span data-stu-id="70533-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="70533-110">DeniedMembers ha la precedenza su ciò che è in AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="70533-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="70533-111">Attività eseguibili</span><span class="sxs-lookup"><span data-stu-id="70533-111">Tasks that you can perform</span></span>

<span data-ttu-id="70533-112">Nella pagina **Seleziona membri non consentiti** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="70533-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="70533-113">Configurare le categorie</span><span class="sxs-lookup"><span data-stu-id="70533-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="70533-114">Nuove caratteristiche del server chat persistente</span><span class="sxs-lookup"><span data-stu-id="70533-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="70533-115">Per informazioni dettagliate sulle diverse procedure che è possibile eseguire utilizzando il Pannello di controllo di Skype for Business Server, vedere [Gestire Skype for Business Server 2015.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="70533-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="70533-116">Per configurare le categorie delle chat room</span><span class="sxs-lookup"><span data-stu-id="70533-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="70533-117">In Appartenenza, **nella** sezione Membri non consentiti aggiungere o rimuovere utenti e altre entità di Active Directory associate ai membri negati dalla chat room.</span><span class="sxs-lookup"><span data-stu-id="70533-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="70533-118">Per informazioni dettagliate sulle caratteristiche e sulle funzionalità del server Chat persistente, vedere [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="70533-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="70533-119">Per informazioni dettagliate sull'utilizzo delle configurazioni del server Chat persistente, vedere [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) nella documentazione relativa alla distribuzione e [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="70533-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="70533-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70533-120">See also</span></span>

[<span data-ttu-id="70533-121">Informazioni sull'appartenenza di chat persistente</span><span class="sxs-lookup"><span data-stu-id="70533-121">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
