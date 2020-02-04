---
title: Numero di telefono non assegnato
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
description: I numeri non assegnati sono numeri di telefono validi per l'organizzazione ma non assegnati a un utente o un telefono. La tabella dei numeri non assegnati identifica come si desidera gestire le chiamata a numeri non assegnati.
ms.openlocfilehash: 47b3e424bee6405def80874d4cb74c20c8051c36
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699301"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="2b83b-104">Numero di telefono non assegnato</span><span class="sxs-lookup"><span data-stu-id="2b83b-104">Unassigned Phone Number</span></span>

<span data-ttu-id="2b83b-p102">I numeri non assegnati sono numeri di telefono validi per l'organizzazione ma non assegnati a un utente o un telefono. La tabella dei numeri non assegnati identifica come si desidera gestire le chiamata a numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="2b83b-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

<span data-ttu-id="2b83b-p103">La configurazione della tabella dei numeri non assegnati dipende dall'utilizzo previsto di questa. È possibile configurare la tabella con tutti gli interni validi dell'organizzazione, solo con gli interni non assegnati o con una combinazione di numeri di entrambi i tipi. La tabella dei numeri non assegnati può includere sia numeri assegnati che numeri non assegnati ma viene chiamata solo se un chiamante compone un numero non assegnato. Se nella tabella dei numeri non assegnati si inseriscono tutti gli interni validi, è possibile specificare l'azione da eseguire quando un utente lascia l'organizzazione, senza alcuna necessità di riconfigurare la tabella. Se nella tabella si inseriscono interni non assegnati, è possibile personalizzare l'azione da eseguire per numeri specifici. Se ad esempio si modifica l'interno del servizio di assistenza clienti, è possibile inserire il vecchio numero nella tabella e assegnarlo a un annuncio in cui viene indicato il nuovo numero.</span><span class="sxs-lookup"><span data-stu-id="2b83b-p103">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b83b-113">Prima di configurare la tabella dei numeri non assegnati è necessario che sia definito almeno un annuncio o che sia impostato un Operatore automatico di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="2b83b-113">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="2b83b-114">Nella pagina **Numero non assegnato** viene visualizzato un elenco degli intervalli di numeri non assegnati definiti per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2b83b-114">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="2b83b-115">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="2b83b-115">Tasks you can perform</span></span>

<span data-ttu-id="2b83b-116">Nella pagina **Numero non assegnato** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b83b-116">You can perform the following tasks from the **Unassigned Number** page:</span></span>

- <span data-ttu-id="2b83b-117">Creare un nuovo intervallo di numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="2b83b-117">Create a new unassigned number range</span></span>

- <span data-ttu-id="2b83b-118">Modificare un intervallo di numeri non assegnati esistente</span><span class="sxs-lookup"><span data-stu-id="2b83b-118">Change an existing unassigned number range</span></span>

- <span data-ttu-id="2b83b-119">Eliminare un intervallo di numeri non assegnato</span><span class="sxs-lookup"><span data-stu-id="2b83b-119">Delete an unassigned number range</span></span>

- <span data-ttu-id="2b83b-120">Modificare l'ordine degli intervalli di numeri non assegnati, per determinare quale azione applicare per prima a una chiamata in arrivo corrispondente a un numero non assegnato.</span><span class="sxs-lookup"><span data-stu-id="2b83b-120">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="2b83b-121">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="2b83b-121">UI Reference</span></span>

<span data-ttu-id="2b83b-122">L'elenco seguente descrive i comandi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="2b83b-122">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="2b83b-123">**Nuovo** Avvia un nuovo intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="2b83b-123">**New** Starts a new unassigned number range.</span></span>

- <span data-ttu-id="2b83b-124">**Modifica** Apre l'intervallo di numeri non assegnati selezionato per la modifica, seleziona tutti gli intervalli di numeri non assegnati nell'elenco o Elimina l'intervallo di numeri non assegnati selezionato.</span><span class="sxs-lookup"><span data-stu-id="2b83b-124">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>

- <span data-ttu-id="2b83b-125">**Spostati verso l'alto** Sposta l'intervallo di numeri non assegnati selezionato in alto nell'elenco in modo che Skype for Business Server la trovi prima e applichi l'azione specificata prima di applicare le azioni specificate per altri intervalli nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2b83b-125">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b83b-126">Skype for Business Server cerca nella tabella numeri non assegnati dall'alto verso il basso e usa il primo intervallo che corrisponde al numero non assegnato.</span><span class="sxs-lookup"><span data-stu-id="2b83b-126">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="2b83b-127">Se, ad esempio, per un intervallo è specificata un'azione "ultimo tentativo", assicurarsi che tale intervallo si trovi alla fine dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2b83b-127">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

- <span data-ttu-id="2b83b-128">**Spostarsi verso il basso** Sposta l'intervallo di numeri non assegnati selezionato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2b83b-128">**Move down** Moves the selected unassigned number range down in the list.</span></span>

- <span data-ttu-id="2b83b-129">**Commit all** Salva tutte le modifiche apportate agli intervalli di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="2b83b-129">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2b83b-130">Questo comando consente di salvare tutte le modifiche eseguite nelle pagine **Nuovo numero non assegnato** e **Modifica numero non assegnato**.</span><span class="sxs-lookup"><span data-stu-id="2b83b-130">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>

- <span data-ttu-id="2b83b-131">**Aggiornare** Aggiorna l'elenco degli intervalli di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="2b83b-131">**Refresh** Refreshes the list of unassigned number ranges.</span></span>

<span data-ttu-id="2b83b-132">L'elenco seguente descrive i campi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="2b83b-132">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="2b83b-133">**Nome** Nome univoco che identifica l'intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="2b83b-133">**Name** The unique name that identifies the unassigned number range.</span></span>

- <span data-ttu-id="2b83b-134">**Stato** Mostra quali intervalli di numeri sono stati salvati nel database e quali no.</span><span class="sxs-lookup"><span data-stu-id="2b83b-134">**State** Shows which number ranges have been saved to the database and which have not.</span></span>

- <span data-ttu-id="2b83b-135">**Intervallo di inizio** Numero iniziale dell'intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="2b83b-135">**Start range** The beginning number of the unassigned number range.</span></span>

- <span data-ttu-id="2b83b-136">**Intervallo di fine** Numero finale dell'intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="2b83b-136">**End range** The ending number of the unassigned number range.</span></span>

- <span data-ttu-id="2b83b-137">**Destinazione** ID servizio del servizio applicazione che ospita l'applicazione di annuncio che gestirà le chiamate in arrivo in questo intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="2b83b-137">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

- <span data-ttu-id="2b83b-138">**Annuncio** L'annuncio che verrà riprodotto per questo intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="2b83b-138">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>

<span data-ttu-id="2b83b-139">Per informazioni dettagliate sulle caratteristiche e le funzionalità degli annunci, vedere [pianificare l'applicazione di annunci in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2b83b-139">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="2b83b-140">Per informazioni dettagliate sull'utilizzo di intervalli di numeri non assegnati, vedere [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="2b83b-140">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


