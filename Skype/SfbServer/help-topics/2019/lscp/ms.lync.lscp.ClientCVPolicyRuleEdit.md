---
title: Regola versione client
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: I criteri versione client sono composti da una serie di regole versione client, che definiscono le azioni che dovrebbero essere eseguite quando gli utenti tentano di eseguire l'accesso con specifici client o versioni client.
ms.openlocfilehash: a461dad500f0c7d3095ef56483a6b592cec6c20d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109622"
---
# <a name="client-version-rule"></a><span data-ttu-id="7d360-104">Regola versione client</span><span class="sxs-lookup"><span data-stu-id="7d360-104">Client Version Rule</span></span>

<span data-ttu-id="7d360-p102">I criteri versione client sono composti da una serie di regole versione client, che definiscono le azioni che dovrebbero essere eseguite quando gli utenti tentano di eseguire l'accesso con specifici client o versioni client.</span><span class="sxs-lookup"><span data-stu-id="7d360-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="7d360-107">Attività eseguibili</span><span class="sxs-lookup"><span data-stu-id="7d360-107">Tasks you can perform</span></span>

<span data-ttu-id="7d360-108">Nella pagina **Nuova configurazione versione client** o **Modifica configurazione versione client** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="7d360-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="7d360-109">Aggiungere nuove regole a un criterio versione client.</span><span class="sxs-lookup"><span data-stu-id="7d360-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="7d360-110">Modificare le regole che costituiscono un criterio versione client esistente</span><span class="sxs-lookup"><span data-stu-id="7d360-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="7d360-111">Informazioni sull'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="7d360-111">UI Reference</span></span>

<span data-ttu-id="7d360-112">Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="7d360-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="7d360-113">**Agente utente** È possibile selezionare un tipo di client dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="7d360-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="7d360-114">Nella tabella seguente vengono definiti i codici agente utente.</span><span class="sxs-lookup"><span data-stu-id="7d360-114">The following table defines user agent codes.</span></span> <span data-ttu-id="7d360-115">Questo elenco include tipi di client legacy, alcuni dei quali non sono più supportati.</span><span class="sxs-lookup"><span data-stu-id="7d360-115">This list includes legacy client types, some of which are no longer supported.</span></span>

|<span data-ttu-id="7d360-116">**Nome client**</span><span class="sxs-lookup"><span data-stu-id="7d360-116">**Client Name**</span></span>|<span data-ttu-id="7d360-117">**Agente utente**</span><span class="sxs-lookup"><span data-stu-id="7d360-117">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7d360-118">Lync 2013, Lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="7d360-118">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="7d360-119">OC</span><span class="sxs-lookup"><span data-stu-id="7d360-119">OC</span></span>  <br/> |
|<span data-ttu-id="7d360-120">Lync Web App, Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="7d360-120">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="7d360-121">CWA</span><span class="sxs-lookup"><span data-stu-id="7d360-121">CWA</span></span>  <br/> |
|<span data-ttu-id="7d360-122">Lync Phone Edition, Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="7d360-122">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="7d360-123">OCPhone</span><span class="sxs-lookup"><span data-stu-id="7d360-123">OCPhone</span></span>  <br/> |
|<span data-ttu-id="7d360-124">Piattaforma Communicator Phone Edition</span><span class="sxs-lookup"><span data-stu-id="7d360-124">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="7d360-125">CPE</span><span class="sxs-lookup"><span data-stu-id="7d360-125">CPE</span></span>  <br/> |
|<span data-ttu-id="7d360-126">Piattaforma Unified Communications</span><span class="sxs-lookup"><span data-stu-id="7d360-126">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="7d360-127">UCCP</span><span class="sxs-lookup"><span data-stu-id="7d360-127">UCCP</span></span>  <br/> |
|<span data-ttu-id="7d360-128">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="7d360-128">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="7d360-129">AOC</span><span class="sxs-lookup"><span data-stu-id="7d360-129">AOC</span></span>  <br/> |
|<span data-ttu-id="7d360-130">Componente aggiuntivo Live Meeting</span><span class="sxs-lookup"><span data-stu-id="7d360-130">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="7d360-131">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="7d360-131">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="7d360-132">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="7d360-132">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="7d360-133">LMC</span><span class="sxs-lookup"><span data-stu-id="7d360-133">LMC</span></span>  <br/> |
|<span data-ttu-id="7d360-134">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="7d360-134">Windows Messenger</span></span>  <br/> |<span data-ttu-id="7d360-135">WM</span><span class="sxs-lookup"><span data-stu-id="7d360-135">WM</span></span>  <br/> |
|<span data-ttu-id="7d360-136">Client di comunicazione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="7d360-136">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="7d360-137">RTC</span><span class="sxs-lookup"><span data-stu-id="7d360-137">RTC</span></span>  <br/> |
|<span data-ttu-id="7d360-138">Lync 2010 per iPad</span><span class="sxs-lookup"><span data-stu-id="7d360-138">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="7d360-139">iPadLync</span><span class="sxs-lookup"><span data-stu-id="7d360-139">iPadLync</span></span>  <br/> |
|<span data-ttu-id="7d360-140">Lync 2010 per iPhone</span><span class="sxs-lookup"><span data-stu-id="7d360-140">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="7d360-141">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="7d360-141">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="7d360-142">Lync 2010 per Windows Phone</span><span class="sxs-lookup"><span data-stu-id="7d360-142">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="7d360-143">WPLync</span><span class="sxs-lookup"><span data-stu-id="7d360-143">WPLync</span></span>  <br/> |
|<span data-ttu-id="7d360-144">Lync 2010 per Nokia</span><span class="sxs-lookup"><span data-stu-id="7d360-144">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="7d360-145">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="7d360-145">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="7d360-146">Lync 2010 per Android</span><span class="sxs-lookup"><span data-stu-id="7d360-146">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="7d360-147">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="7d360-147">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="7d360-148">Servizio Dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="7d360-148">Mobility service</span></span>  <br/> |<span data-ttu-id="7d360-149">McxService</span><span class="sxs-lookup"><span data-stu-id="7d360-149">McxService</span></span>  <br/> |

- <span data-ttu-id="7d360-150">**Numero di versione** È possibile specificare i numeri di versione per i campi seguenti oppure utilizzare caratteri jolly per indicare il numero di versione del client.</span><span class="sxs-lookup"><span data-stu-id="7d360-150">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="7d360-151">**Versione principale** Specifica il numero corrispondente alla versione principale del client.</span><span class="sxs-lookup"><span data-stu-id="7d360-151">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="7d360-152">**Versione secondaria** Specifica il numero corrispondente alla versione secondaria del client.</span><span class="sxs-lookup"><span data-stu-id="7d360-152">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="7d360-153">**Build** Specifica il numero di build corrispondente alla versione principale e secondaria del client.</span><span class="sxs-lookup"><span data-stu-id="7d360-153">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="7d360-154">**Aggiornamento** Specifica il numero corrispondente alla versione aggiornata del client.</span><span class="sxs-lookup"><span data-stu-id="7d360-154">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="7d360-155">**Operazione di confronto** È possibile specificare l'operazione di corrispondenza per la versione client specificata nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="7d360-155">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="7d360-156">Sono disponibili le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7d360-156">The following operations are available:</span></span>

  - <span data-ttu-id="7d360-157">**Corrispondente a**</span><span class="sxs-lookup"><span data-stu-id="7d360-157">**Same as**</span></span>

  - <span data-ttu-id="7d360-158">**Diverso da**</span><span class="sxs-lookup"><span data-stu-id="7d360-158">**Is not**</span></span>

  - <span data-ttu-id="7d360-159">**Più recente di**</span><span class="sxs-lookup"><span data-stu-id="7d360-159">**Newer than**</span></span>

  - <span data-ttu-id="7d360-160">**Più recente di o corrispondente a**</span><span class="sxs-lookup"><span data-stu-id="7d360-160">**Newer than or same as**</span></span>

  - <span data-ttu-id="7d360-161">**Meno recente di**</span><span class="sxs-lookup"><span data-stu-id="7d360-161">**Older than**</span></span>

  - <span data-ttu-id="7d360-162">**Meno recente di o corrispondente a**</span><span class="sxs-lookup"><span data-stu-id="7d360-162">**Older than or same as**</span></span>

- <span data-ttu-id="7d360-163">**Azione** È possibile specificare l'azione da eseguire quando vengono soddisfatti i criteri nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="7d360-163">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="7d360-164">Sono disponibili le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7d360-164">The following actions are available:</span></span>

  - <span data-ttu-id="7d360-165">**Consenti** Consente al client di accedere.</span><span class="sxs-lookup"><span data-stu-id="7d360-165">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="7d360-166">**Consenti e aggiorna** Consente al client di accedere e ricevere aggiornamenti da Windows Server Update Service o Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="7d360-166">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="7d360-167">Questa azione è disponibile solo se si seleziona l'agente utente **OC**.</span><span class="sxs-lookup"><span data-stu-id="7d360-167">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7d360-168">Se si seleziona questa azione, verrà visualizzata una notifica al successivo accesso degli utenti a Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="7d360-168">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="7d360-169">La notifica indica che è disponibile un aggiornamento, anche se non sono stati ancora rilasciati aggiornamenti per Windows Server Update Service o Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="7d360-169">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="7d360-170">Per evitare confusione, è consigliabile scegliere questa azione solo quando vengono resi disponibili gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="7d360-170">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="7d360-171">**Consenti con URL** Consente al client di eseguire l'accesso e visualizza un messaggio che indica dove scaricare un'altra versione client.</span><span class="sxs-lookup"><span data-stu-id="7d360-171">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="7d360-172">L'URL viene specificato nel campo **URL**.</span><span class="sxs-lookup"><span data-stu-id="7d360-172">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="7d360-173">**Blocco** Impedisce al client di accedere.</span><span class="sxs-lookup"><span data-stu-id="7d360-173">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="7d360-174">**Blocco e aggiornamento** Impedisce al client di eseguire l'accesso e consente al client di ricevere gli aggiornamenti da Windows Server Update Service o Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="7d360-174">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="7d360-175">Questa azione è disponibile solo se si seleziona l'agente utente **OC**.</span><span class="sxs-lookup"><span data-stu-id="7d360-175">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="7d360-p110">**Blocca con URL** Impedisce al client di eseguire l'accesso e visualizza un messaggio sulla posizione da cui scaricare un'altra versione client. L'URL viene specificato nel campo **URL**.</span><span class="sxs-lookup"><span data-stu-id="7d360-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="7d360-178">Per informazioni dettagliate sull'interoperabilità tra client e versioni client, vedere [Client Interoperability](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="7d360-178">For details about interoperability among clients and client versions, see [Client Interoperability](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="7d360-179">Per informazioni dettagliate sull'uso delle configurazioni delle versioni client, vedere [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="7d360-179">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) in the Operations documentation.</span></span>