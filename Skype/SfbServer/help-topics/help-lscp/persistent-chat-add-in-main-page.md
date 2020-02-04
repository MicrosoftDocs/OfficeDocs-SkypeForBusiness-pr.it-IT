---
title: Pagina principale del componente aggiuntivo Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: È possibile usare la sezione componente aggiuntivo della pagina della chat persistente per associare gli URL alle chat room permanenti. Questi URL verranno visualizzati nel riquadro di estendibilità delle conversazioni della chat room del client. Perché gli utenti possano visualizzare questo aggiornamento nel proprio client, l'amministratore deve aggiungere componenti aggiuntivi all'elenco dei componenti aggiuntivi registrati, mentre i responsabili/creatori della chat room devono associare chat a uno dei componenti aggiuntivi registrati.
ms.openlocfilehash: 0fe522b440a3f99973ecafa04a9ef7a7cbc3962a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699971"
---
# <a name="persistent-chat-add-in-main-page"></a><span data-ttu-id="3e47f-105">Pagina principale del componente aggiuntivo Chat persistente</span><span class="sxs-lookup"><span data-stu-id="3e47f-105">Persistent Chat Add-in Main Page</span></span>

<span data-ttu-id="3e47f-106">È possibile usare la sezione **componente aggiuntivo** della pagina della **chat persistente** per associare gli URL alle chat room permanenti.</span><span class="sxs-lookup"><span data-stu-id="3e47f-106">You can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="3e47f-107">Questi URL verranno visualizzati nel riquadro di estendibilità delle conversazioni della chat room del client.</span><span class="sxs-lookup"><span data-stu-id="3e47f-107">These URLs appear in the client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="3e47f-108">Perché gli utenti possano visualizzare questo aggiornamento nel proprio client, l'amministratore deve aggiungere componenti aggiuntivi all'elenco dei componenti aggiuntivi registrati, mentre i responsabili/creatori della chat room devono associare chat a uno dei componenti aggiuntivi registrati.</span><span class="sxs-lookup"><span data-stu-id="3e47f-108">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators must associate rooms with one of the registered add-ins before users can see this upgrade in their client.</span></span>

<span data-ttu-id="3e47f-109">I componenti aggiuntivi sono usati per ampliare l'esperienza all'interno della chat.</span><span class="sxs-lookup"><span data-stu-id="3e47f-109">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="3e47f-110">Un componente aggiuntivo tipico può includere un URL che punta a un'applicazione Silverlight che intercetta quando un ticker del titolo viene inserito in una chat room e Mostra la cronologia del titolo nel riquadro estensibilità.</span><span class="sxs-lookup"><span data-stu-id="3e47f-110">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="3e47f-111">Altri esempi sono l'incorporamento di un URL di OneNote 2013 nella chat room come componente aggiuntivo per includere contenuto condiviso, ad esempio "In primo piano" o "Argomento del giorno".</span><span class="sxs-lookup"><span data-stu-id="3e47f-111">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<span data-ttu-id="3e47f-112">Per creare componenti aggiuntivi per le chat room permanenti, vedere [configurare i componenti aggiuntivi per le chat room permanenti in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="3e47f-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span></span> <span data-ttu-id="3e47f-113">Se si è un amministratore della chat persistente, è possibile creare componenti aggiuntivi usando il pannello di controllo o i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e47f-113">If you are a Persistent Chat Administrator, you can create add-ins by using the control panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="3e47f-114">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="3e47f-114">Tasks you can perform</span></span>

<span data-ttu-id="3e47f-115">Nella pagina **Componente aggiuntivo** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e47f-115">You can perform the following tasks on the **Add-in** page:</span></span>

- [<span data-ttu-id="3e47f-116">Configurare i componenti aggiuntivi per le chat room di Chat persistente</span><span class="sxs-lookup"><span data-stu-id="3e47f-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="3e47f-117">Per configurare componenti aggiuntivi per le chat room</span><span class="sxs-lookup"><span data-stu-id="3e47f-117">To configure Add-ins for chat rooms</span></span>

<span data-ttu-id="3e47f-118">Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="3e47f-118">The following lists describe the menus, command, fields, and properties on the page.</span></span>

1. <span data-ttu-id="3e47f-119">Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a un qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3e47f-119">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="3e47f-120">Nel menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="3e47f-120">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="3e47f-121">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il Pannello di controllo, vedere [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span><span class="sxs-lookup"><span data-stu-id="3e47f-121">For details about the different methods that you can use to start control panel, see [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span></span>

3. <span data-ttu-id="3e47f-122">Sulla barra di spostamento sinistra fare clic su **Chat persistente** e quindi su **Componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="3e47f-122">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>

    <span data-ttu-id="3e47f-123">Per più distribuzioni di pool di server di chat persistenti, selezionare il pool appropriato nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="3e47f-123">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4. <span data-ttu-id="3e47f-124">Nella pagina **Componente aggiuntivo** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="3e47f-124">On the **Add-in** page, click **New**.</span></span>

5. <span data-ttu-id="3e47f-125">In **Seleziona un servizio**selezionare il servizio corrispondente al pool del server di chat persistente in cui è necessario creare il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="3e47f-125">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="3e47f-126">I componenti aggiuntivi non possono essere spostati da un pool a un altro o condivisi da pool diversi.</span><span class="sxs-lookup"><span data-stu-id="3e47f-126">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6. <span data-ttu-id="3e47f-127">In **Nuovo componente aggiuntivo** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e47f-127">In **New Add-in**, do the following:</span></span>

   - <span data-ttu-id="3e47f-128">In **Nome** specificare un nome per il nuovo componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="3e47f-128">In **Name**, specify a name for the new add-in.</span></span>

   - <span data-ttu-id="3e47f-p107">In **URL** specificare l'URL da associare al componente aggiuntivo. Gli URL devono limitarsi ai protocolli http e https.</span><span class="sxs-lookup"><span data-stu-id="3e47f-p107">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7. <span data-ttu-id="3e47f-131">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="3e47f-131">Click **Commit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e47f-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e47f-132">See also</span></span>

<span data-ttu-id="3e47f-133">Per informazioni dettagliate sulle funzionalità e le funzionalità del server di chat persistente, vedere [pianificare il server di chat persistente in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [distribuire il server di chat persistente in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)e [gestire il server di chat persistente in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="3e47f-133">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>


