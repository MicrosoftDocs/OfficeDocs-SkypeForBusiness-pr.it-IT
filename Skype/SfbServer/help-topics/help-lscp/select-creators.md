---
title: Selezionare i creatori
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectCreators
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8d9ed6f-22ba-470e-b0b4-0da3cea5e961
description: La creazione e la gestione di chat room persistenti è molto più semplice con l'uso corretto delle categorie. Un amministratore della chat persistente può definire AllowedMembers e creatori per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti della chat room che verranno applicati a tutte le chat room create nella categoria. Gli amministratori della chat persistente creano e gestiscono categorie usando il pannello di controllo di Skype for Business Server o i cmdlet di Windows PowerShell.
ms.openlocfilehash: 6fc3feb4465f1ad55d369ed736ea277853aadc13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194504"
---
# <a name="select-creators"></a><span data-ttu-id="24064-105">Selezionare i creatori</span><span class="sxs-lookup"><span data-stu-id="24064-105">Select Creators</span></span>

<span data-ttu-id="24064-106">La creazione e la gestione di chat room persistenti è molto più semplice con l'uso corretto delle categorie.</span><span class="sxs-lookup"><span data-stu-id="24064-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="24064-107">Un amministratore della chat persistente può definire **AllowedMembers** e **creatori** per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti della chat room che verranno applicati a tutte le chat room create nella categoria.</span><span class="sxs-lookup"><span data-stu-id="24064-107">A Persistent Chat administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="24064-108">Gli amministratori della chat persistente creano e gestiscono categorie usando il pannello di controllo di Skype for Business Server o i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="24064-108">Persistent Chat administrators create and manage categories by using Skype for Business Server Control Panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="24064-109">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="24064-109">Tasks that you can perform</span></span>

<span data-ttu-id="24064-110">Nella pagina **Selezionare i creatori** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="24064-110">You can perform the following tasks on the **Select Creators** page:</span></span>

- [<span data-ttu-id="24064-111">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="24064-111">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="24064-112">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="24064-112">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="24064-113">Per informazioni dettagliate sulle diverse procedure che è possibile eseguire tramite il pannello di controllo di Skype for Business Server, vedere [gestire Skype for Business server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="24064-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="24064-114">Per configurare le categorie delle chat room</span><span class="sxs-lookup"><span data-stu-id="24064-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="24064-115">In **appartenenza**, nella sezione **Creators** , aggiungere o rimuovere utenti e altre entità Active Directory associate agli autori per la categoria.</span><span class="sxs-lookup"><span data-stu-id="24064-115">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="24064-116">Per creatore si intende un utente con autorizzazioni per la creazione di chat room e l'assegnazione di membri e responsabili delle chat.</span><span class="sxs-lookup"><span data-stu-id="24064-116">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>



<span data-ttu-id="24064-117">Per informazioni dettagliate sulle funzionalità e le funzionalità del server di chat persistente, vedere [Panoramica del server di chat persistente](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="24064-117">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="24064-118">Per informazioni dettagliate sull'uso delle configurazioni del server di chat persistente, vedere [configurazione del server di chat persistente](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) nella documentazione di distribuzione e [gestione di Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="24064-118">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="24064-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24064-119">See also</span></span>

[<span data-ttu-id="24064-120">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="24064-120">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

[<span data-ttu-id="24064-121">Uso delle categorie per amministrare il server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="24064-121">Using Categories to Administer Persistent Chat Server</span></span>](https://technet.microsoft.com/library/dfcb3ad1-da90-467e-b08c-f4e68673b7b5.aspx)

[<span data-ttu-id="24064-122">Spostamento di una chat room da una categoria a un'altra</span><span class="sxs-lookup"><span data-stu-id="24064-122">Moving a Chat Room from One Category to Another</span></span>](https://technet.microsoft.com/library/7e93b8f6-5a18-4476-a432-3918e01bcfa6.aspx)

[<span data-ttu-id="24064-123">Creazione o modifica di una nuova sala</span><span class="sxs-lookup"><span data-stu-id="24064-123">Creating or Editing a New Room</span></span>](https://technet.microsoft.com/library/aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4.aspx)
