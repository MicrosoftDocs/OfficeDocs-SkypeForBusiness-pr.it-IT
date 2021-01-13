---
title: Componente aggiuntivo Persistent Chat
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: È possibile utilizzare la sezione componente aggiuntivo della pagina Chat persistente per associare gli URL alle chat room persistente. Questi URL vengono visualizzati nel client nella chat room del riquadro Extensibility di conversazione. Un amministratore deve aggiungere componenti aggiuntivi all'elenco dei componenti aggiuntivi registrati e i responsabili/creatori della chat devono associare le camere a uno dei componenti aggiuntivi registrati prima che gli utenti possano visualizzare questo aggiornamento nel client.
ms.openlocfilehash: 306cd54864400362a869db34d79f1fe6241d81ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803776"
---
# <a name="persistent-chat-add-in"></a><span data-ttu-id="cb3c7-105">Componente aggiuntivo di Chat persistente</span><span class="sxs-lookup"><span data-stu-id="cb3c7-105">Persistent Chat Add-in</span></span>

<span data-ttu-id="cb3c7-106">È possibile utilizzare la sezione **componente aggiuntivo** della pagina **chat persistente** per associare gli URL alle chat room persistente.</span><span class="sxs-lookup"><span data-stu-id="cb3c7-106">You can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="cb3c7-107">Questi URL vengono visualizzati nel client nella chat room del riquadro Extensibility di conversazione.</span><span class="sxs-lookup"><span data-stu-id="cb3c7-107">These URLs appear in the client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="cb3c7-108">Un amministratore deve aggiungere componenti aggiuntivi all'elenco dei componenti aggiuntivi registrati e i responsabili/creatori della chat devono associare le camere a uno dei componenti aggiuntivi registrati prima che gli utenti possano visualizzare questo aggiornamento nel client.</span><span class="sxs-lookup"><span data-stu-id="cb3c7-108">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators must associate rooms with one of the registered add-ins before users can see this upgrade in their client.</span></span>

<span data-ttu-id="cb3c7-109">I componenti aggiuntivi vengono utilizzati per estendere l'esperienza in chat.</span><span class="sxs-lookup"><span data-stu-id="cb3c7-109">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="cb3c7-110">Un componente aggiuntivo tipico potrebbe includere un URL che punta a un'applicazione Silverlight che intercetta quando un ticker di stock viene inserito in una chat room e visualizza la cronologia del magazzino nel riquadro Extensibility.</span><span class="sxs-lookup"><span data-stu-id="cb3c7-110">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="cb3c7-111">Tra gli altri esempi c'è l'integrazione di un URL OneNote 2013 nella chat room in forma di componente aggiuntivo, per includere un contesto condiviso, ad esempio "Di facile riconoscibilità" o "Argomento del giorno".</span><span class="sxs-lookup"><span data-stu-id="cb3c7-111">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<span data-ttu-id="cb3c7-112">Per creare componenti aggiuntivi per le chat room permanenti, vedere [configurare i componenti aggiuntivi per le chat room persistent in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="cb3c7-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span></span> <span data-ttu-id="cb3c7-113">Se si è un amministratore di chat persistente, è possibile creare componenti aggiuntivi utilizzando il pannello di controllo o i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb3c7-113">If you are a Persistent Chat Administrator, you can create add-ins by using the control panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="cb3c7-114">Attività eseguibili</span><span class="sxs-lookup"><span data-stu-id="cb3c7-114">Tasks that you can perform</span></span>

<span data-ttu-id="cb3c7-115">Nella pagina **Componente aggiuntivo** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="cb3c7-115">You can perform the following tasks on the **Add-in** page:</span></span>

- [<span data-ttu-id="cb3c7-116">Configurare i componenti aggiuntivi per le chat room permanenti in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cb3c7-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="cb3c7-117">Per configurare componenti aggiuntivi per chat room</span><span class="sxs-lookup"><span data-stu-id="cb3c7-117">To configure Add-ins for chat rooms</span></span>

<span data-ttu-id="cb3c7-118">Nei seguenti elenchi vengono descritti i menu, i comandi, i campi e le proprietà presenti sulla pagina.</span><span class="sxs-lookup"><span data-stu-id="cb3c7-118">The following lists describe the menus, command, fields, and properties on the page.</span></span>

1. <span data-ttu-id="cb3c7-119">Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator accedere a uno qualsiasi dei computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="cb3c7-119">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="cb3c7-120">Dal menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL di amministratore.</span><span class="sxs-lookup"><span data-stu-id="cb3c7-120">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="cb3c7-121">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo, vedere [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span><span class="sxs-lookup"><span data-stu-id="cb3c7-121">For details about the different methods that you can use to start the control panel, see [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span></span>

3. <span data-ttu-id="cb3c7-122">Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="cb3c7-122">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>

    <span data-ttu-id="cb3c7-123">Per più distribuzioni di pool di server Chat persistente, selezionare il pool appropriato dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="cb3c7-123">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4. <span data-ttu-id="cb3c7-124">Nella pagina **Componente aggiuntivo** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="cb3c7-124">On the **Add-in** page, click **New**.</span></span>

5. <span data-ttu-id="cb3c7-125">In **Seleziona un servizio** selezionare il servizio corrispondente al pool di server Chat persistente in cui è necessario creare il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="cb3c7-125">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="cb3c7-126">I componenti aggiuntivi non possono essere spostati da un pool all'altro o condivisi tra diversi pool.</span><span class="sxs-lookup"><span data-stu-id="cb3c7-126">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6. <span data-ttu-id="cb3c7-127">In **Nuovo componente aggiuntivo** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cb3c7-127">In **New Add-in**, do the following:</span></span>

   - <span data-ttu-id="cb3c7-128">In **Nome** specificare un nome per il nuovo componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="cb3c7-128">In **Name**, specify a name for the new add-in.</span></span>

   - <span data-ttu-id="cb3c7-p107">In **URL** specificare l'URL da associare al componente aggiuntivo. Gli URL sono limitati ai protocolli http e https.</span><span class="sxs-lookup"><span data-stu-id="cb3c7-p107">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7. <span data-ttu-id="cb3c7-131">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="cb3c7-131">Click **Commit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb3c7-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb3c7-132">See also</span></span>

<span data-ttu-id="cb3c7-133">Per informazioni dettagliate sulle funzionalità e sulle funzionalità del server Chat persistente, vedere [Plan for Persistent Chat Server in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)e [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="cb3c7-133">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>


