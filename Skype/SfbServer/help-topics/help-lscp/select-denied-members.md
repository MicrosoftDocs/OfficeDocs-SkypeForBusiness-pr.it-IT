---
title: Selezionare membri non consentiti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: Un amministratore della chat persistente può creare e gestire le categorie delle chat room. Nell'ambito della creazione e della gestione delle categorie di chat room, un amministratore della chat persistente può configurare le entità (gruppi/contenitori/utenti di servizi di dominio Active Directory) che hanno accesso a membri/creatori di chat room di una specifica categoria. Un amministratore della chat persistente può anche aggiungere DeniedMembers a una categoria e questi diventano esclusioni esplicite per l'elenco consentiti. DeniedMembers ignora le informazioni in AllowedMembers.
ms.openlocfilehash: bbf54bfb05a2c3a54c9515d77ae6fb93b22a62ec
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194502"
---
# <a name="select-denied-members"></a><span data-ttu-id="b65c9-106">Selezionare membri non consentiti</span><span class="sxs-lookup"><span data-stu-id="b65c9-106">Select Denied Members</span></span>

<span data-ttu-id="b65c9-107">Un amministratore della chat persistente può creare e gestire le categorie delle chat room.</span><span class="sxs-lookup"><span data-stu-id="b65c9-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="b65c9-108">Nell'ambito della creazione e della gestione delle categorie di chat room, un amministratore della chat persistente può configurare le entità (gruppi/contenitori/utenti di servizi di dominio Active Directory) che hanno accesso a membri/creatori di chat room di una specifica categoria.</span><span class="sxs-lookup"><span data-stu-id="b65c9-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="b65c9-109">Un amministratore della chat persistente può anche aggiungere DeniedMembers a una categoria e questi diventano esclusioni esplicite per l'elenco consentiti.</span><span class="sxs-lookup"><span data-stu-id="b65c9-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="b65c9-110">DeniedMembers ignora le informazioni in AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="b65c9-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="b65c9-111">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="b65c9-111">Tasks that you can perform</span></span>

<span data-ttu-id="b65c9-112">Nella pagina **Selezionare membri non consentiti** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="b65c9-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="b65c9-113">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="b65c9-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="b65c9-114">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="b65c9-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="b65c9-115">Per informazioni dettagliate sulle diverse procedure che è possibile eseguire tramite il pannello di controllo di Skype for Business Server, vedere [gestire Skype for Business server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="b65c9-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="b65c9-116">Per configurare le categorie delle chat room</span><span class="sxs-lookup"><span data-stu-id="b65c9-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="b65c9-117">In **appartenenza**, nella sezione **membri negati** , aggiungere o rimuovere utenti e altre entità Active Directory associate ai membri negati dalla sala.</span><span class="sxs-lookup"><span data-stu-id="b65c9-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="b65c9-118">Per informazioni dettagliate sulle funzionalità e le funzionalità del server di chat persistente, vedere [Panoramica del server di chat persistente](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="b65c9-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="b65c9-119">Per informazioni dettagliate sull'uso delle configurazioni del server di chat persistente, vedere [configurazione del server di chat persistente](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) nella documentazione di distribuzione e [gestione di Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="b65c9-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="b65c9-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b65c9-120">See also</span></span>

[<span data-ttu-id="b65c9-121">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="b65c9-121">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
