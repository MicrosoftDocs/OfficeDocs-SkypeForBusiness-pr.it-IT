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
description: La creazione e la gestione delle chat room di Persistent Chat sono molto più semplici con l'uso corretto delle categorie. Un amministratore di Persistent Chat può definire AllowedMembers e Creators per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti delle chat room che verranno applicati a tutte le chat room create nella categoria. Gli amministratori di Persistent Chat creano e gestiscono categorie utilizzando il Pannello di controllo di Skype for Business Server o Windows PowerShell cmdlet.
ms.openlocfilehash: 9fc8bf615de02a4c9eefcd204c832c5c8691eb7e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821956"
---
# <a name="select-creators"></a><span data-ttu-id="3b214-105">Selezionare creatori</span><span class="sxs-lookup"><span data-stu-id="3b214-105">Select Creators</span></span>

<span data-ttu-id="3b214-106">La creazione e la gestione delle chat room di Persistent Chat sono molto più semplici con l'uso corretto delle categorie.</span><span class="sxs-lookup"><span data-stu-id="3b214-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="3b214-107">Un amministratore di Persistent Chat può definire **AllowedMembers** e **Creators** per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti delle chat room che verranno applicati a tutte le chat room create nella categoria.</span><span class="sxs-lookup"><span data-stu-id="3b214-107">A Persistent Chat administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="3b214-108">Gli amministratori di Persistent Chat creano e gestiscono categorie utilizzando il Pannello di controllo di Skype for Business Server o Windows PowerShell cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3b214-108">Persistent Chat administrators create and manage categories by using Skype for Business Server Control Panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="3b214-109">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="3b214-109">Tasks that you can perform</span></span>

<span data-ttu-id="3b214-110">Nella pagina **Seleziona creatori**, è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b214-110">You can perform the following tasks on the **Select Creators** page:</span></span>

- [<span data-ttu-id="3b214-111">Configurare le categorie</span><span class="sxs-lookup"><span data-stu-id="3b214-111">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="3b214-112">Nuove caratteristiche del server chat persistente</span><span class="sxs-lookup"><span data-stu-id="3b214-112">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="3b214-113">Per informazioni dettagliate sulle diverse procedure che è possibile eseguire utilizzando il Pannello di controllo di Skype for Business Server, vedere [Gestire Skype for Business Server 2015.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="3b214-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="3b214-114">Per configurare le categorie delle chat room</span><span class="sxs-lookup"><span data-stu-id="3b214-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="3b214-115">In **Appartenenza,** nella **sezione Creators,** aggiungere o rimuovere utenti e altre entità di Active Directory associate ai creatori della categoria.</span><span class="sxs-lookup"><span data-stu-id="3b214-115">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="3b214-116">Per creatore si intende un utente con autorizzazioni per la creazione di chat room e l'assegnazione di membri e responsabili delle chat.</span><span class="sxs-lookup"><span data-stu-id="3b214-116">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>



<span data-ttu-id="3b214-117">Per informazioni dettagliate sulle caratteristiche e sulle funzionalità del server Chat persistente, vedere [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="3b214-117">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="3b214-118">Per informazioni dettagliate sull'utilizzo delle configurazioni del server Chat persistente, vedere [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) nella documentazione relativa alla distribuzione e [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="3b214-118">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b214-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b214-119">See also</span></span>

[<span data-ttu-id="3b214-120">Informazioni sull'appartenenza di chat persistente</span><span class="sxs-lookup"><span data-stu-id="3b214-120">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

[<span data-ttu-id="3b214-121">Utilizzo di categorie per l'amministrazione del server chat persistente</span><span class="sxs-lookup"><span data-stu-id="3b214-121">Using Categories to Administer Persistent Chat Server</span></span>](https://technet.microsoft.com/library/dfcb3ad1-da90-467e-b08c-f4e68673b7b5.aspx)

[<span data-ttu-id="3b214-122">Spostamento di una chat room da una categoria all'altra</span><span class="sxs-lookup"><span data-stu-id="3b214-122">Moving a Chat Room from One Category to Another</span></span>](https://technet.microsoft.com/library/7e93b8f6-5a18-4476-a432-3918e01bcfa6.aspx)

[<span data-ttu-id="3b214-123">Creazione o modifica di una nuova chat room</span><span class="sxs-lookup"><span data-stu-id="3b214-123">Creating or Editing a New Room</span></span>](https://technet.microsoft.com/library/aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4.aspx)
