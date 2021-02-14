---
title: Configurare i componenti aggiuntivi per le chat room di Persistent Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Riepilogo: informazioni su come configurare i componenti aggiuntivi per le chat room del server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 1aca54f3db1229527256d1e2801cb057f4f79387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815082"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="efa45-103">Configurare i componenti aggiuntivi per le chat room di Persistent Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="efa45-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="efa45-104">**Riepilogo:** Informazioni su come configurare i componenti aggiuntivi per le chat room del server Chat persistente in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="efa45-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="efa45-105">I componenti aggiuntivi vengono utilizzati per estendere l'esperienza in-room associando gli URL alle chat room.</span><span class="sxs-lookup"><span data-stu-id="efa45-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="efa45-106">Questi URL vengono visualizzati nel riquadro di estendibilità della conversazione client.</span><span class="sxs-lookup"><span data-stu-id="efa45-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="efa45-107">Un componente aggiuntivo tipico può includere un URL che punta a un'applicazione Silverlight che intercetta quando un titolo azionario viene pubblicato in una chat room e mostra la cronologia delle azioni nel riquadro di estendibilità.</span><span class="sxs-lookup"><span data-stu-id="efa45-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="efa45-108">Tra gli altri esempi c'è l'integrazione di un URL OneNote 2013 nella chat room in forma di componente aggiuntivo, per includere un contesto condiviso, ad esempio "Di facile riconoscibilità" o "Argomento del giorno".</span><span class="sxs-lookup"><span data-stu-id="efa45-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="efa45-109">Prima che gli utenti possano visualizzare un componente aggiuntivo nel client, è necessario aggiungerlo all'elenco dei componenti aggiuntivi registrati e i responsabili o i creatori di chat room devono associare le chat room al componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="efa45-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
> [!NOTE]
> <span data-ttu-id="efa45-110">La chat persistente è disponibile in Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="efa45-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="efa45-111">Le stesse funzionalità sono disponibili in Teams.</span><span class="sxs-lookup"><span data-stu-id="efa45-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="efa45-112">Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="efa45-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="efa45-113">Se è necessario usare Chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità a Teams o continuare a usare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="efa45-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="efa45-114">Configurare i componenti aggiuntivi per le chat room utilizzando il Pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="efa45-114">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="efa45-115">Per configurare i componenti aggiuntivi per le chat room utilizzando il Pannello di controllo:</span><span class="sxs-lookup"><span data-stu-id="efa45-115">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="efa45-116">Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="efa45-116">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="efa45-117">Dal menu **Start** seleziona il Pannello di controllo di Skype for Business Server o apri una finestra del browser e quindi immetti l'URL di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="efa45-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="efa45-118">Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="efa45-118">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="efa45-119">Per più distribuzioni di pool di server Chat persistente, selezionare il pool appropriato nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="efa45-119">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="efa45-120">Nella pagina **Componente aggiuntivo** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="efa45-120">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="efa45-121">In **Selezionare un servizio** selezionare il servizio corrispondente al pool di server Chat persistente in cui è necessario creare il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="efa45-121">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="efa45-122">I componenti aggiuntivi non possono essere spostati da un pool all'altro o condivisi tra diversi pool.</span><span class="sxs-lookup"><span data-stu-id="efa45-122">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="efa45-123">In **Nuovo componente aggiuntivo** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="efa45-123">In **New Add-in**, do the following:</span></span>
    
   - <span data-ttu-id="efa45-124">In **Nome** specificare un nome per il nuovo componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="efa45-124">In **Name**, specify a name for the new add-in.</span></span>
    
   - <span data-ttu-id="efa45-125">In **URL** specificare l'URL da associare al componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="efa45-125">In **URL**, specify the URL to be associated with the add-in.</span></span> <span data-ttu-id="efa45-126">Gli URL sono limitati ai protocolli http e https.</span><span class="sxs-lookup"><span data-stu-id="efa45-126">URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="efa45-127">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="efa45-127">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="efa45-128">Configurare i componenti aggiuntivi utilizzando Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="efa45-128">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="efa45-129">È possibile configurare i componenti aggiuntivi per le chat room utilizzando i cmdlet Windows PowerShell seguenti.</span><span class="sxs-lookup"><span data-stu-id="efa45-129">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets.</span></span> <span data-ttu-id="efa45-130">Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri disponibili, vedere [Skype for Business Server 2015 Management Shell.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="efa45-130">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="efa45-131">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="efa45-131">**Cmdlet**</span></span>|<span data-ttu-id="efa45-132">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="efa45-132">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="efa45-133">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="efa45-133">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="efa45-134">Creare un nuovo componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="efa45-134">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="efa45-135">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="efa45-135">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="efa45-136">Configurare le impostazioni per un componente aggiuntivo esistente</span><span class="sxs-lookup"><span data-stu-id="efa45-136">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="efa45-137">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="efa45-137">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="efa45-138">Recuperare informazioni sui componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="efa45-138">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="efa45-139">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="efa45-139">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="efa45-140">Rimuovere un componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="efa45-140">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="efa45-141">Creare un nuovo componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="efa45-141">Create a new add-in</span></span>

<span data-ttu-id="efa45-142">È possibile creare un nuovo componente aggiuntivo utilizzando il cmdlet **New-CsPersistentChatAddin.**</span><span class="sxs-lookup"><span data-stu-id="efa45-142">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="efa45-143">Ad esempio, il comando seguente crea un nuovo componente aggiuntivo (con il nome ITPersistentChatAddin) per il pool atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="efa45-143">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="efa45-144">Il parametro URL e il valore del parametro http://atl-cs-001.contoso.com/itchat specificano il percorso della pagina Web del componente aggiuntivo:</span><span class="sxs-lookup"><span data-stu-id="efa45-144">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="efa45-145">Configurare le impostazioni per un componente aggiuntivo esistente</span><span class="sxs-lookup"><span data-stu-id="efa45-145">Configure settings for an existing add-in</span></span>

<span data-ttu-id="efa45-146">È possibile configurare le impostazioni per un componente aggiuntivo esistente utilizzando il cmdlet **Set-CsPersistentChatAddIn.**</span><span class="sxs-lookup"><span data-stu-id="efa45-146">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="efa45-147">Ad esempio, il comando seguente modifica l'URL assegnato al componente aggiuntivo di Persistent Chat ITPersistentChatAddin.</span><span class="sxs-lookup"><span data-stu-id="efa45-147">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="efa45-148">In questo caso, l'URL viene modificato in http://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="efa45-148">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="efa45-149">Recuperare informazioni sui componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="efa45-149">Retrieve information about add-ins</span></span>

<span data-ttu-id="efa45-150">È possibile ottenere informazioni sui componenti aggiuntivi utilizzando il cmdlet **Get-CsPersistentChatAddin.**</span><span class="sxs-lookup"><span data-stu-id="efa45-150">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet.</span></span> <span data-ttu-id="efa45-151">Ad esempio, il comando seguente restituisce informazioni su tutti i componenti aggiuntivi di Persistent Chat configurati per l'utilizzo nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="efa45-151">For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="efa45-152">Rimuovere un componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="efa45-152">Remove an add-in</span></span>

<span data-ttu-id="efa45-153">È possibile rimuovere un componente aggiuntivo utilizzando il cmdlet **Remove-CsPersistentChatAddIn.**</span><span class="sxs-lookup"><span data-stu-id="efa45-153">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="efa45-154">Ad esempio, il comando seguente rimuove il componente aggiuntivo di Persistent Chat ITChatAddin trovato nel pool atl-cs-001.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="efa45-154">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


