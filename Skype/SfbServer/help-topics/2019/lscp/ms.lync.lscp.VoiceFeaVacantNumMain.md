---
title: Numero di telefono non assegnato
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: I numeri non assegnati sono numeri di telefono validi per l'organizzazione ma non assegnati a un utente o un telefono. La tabella dei numeri non assegnati identifica come si desidera gestire le chiamata a numeri non assegnati.
ms.openlocfilehash: 2b2c8637e1fa44d8852465b21d2cf494442978b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830136"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="1207d-104">Numero di telefono non assegnato</span><span class="sxs-lookup"><span data-stu-id="1207d-104">Unassigned Phone Number</span></span>

> [!NOTE]
> <span data-ttu-id="1207d-105">La messaggistica unificata di Exchange rimane disponibile in Skype for Business Server 2019 quando si integra Skype for Business 2019 con Exchange 2013 o Exchange 2016.</span><span class="sxs-lookup"><span data-stu-id="1207d-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="1207d-106">A causa dei cambiamenti nel supporto in Exchange 2019, l'integrazione della messaggistica unificata di Exchange viene de-enfatizzata a favore delle funzionalità cloud voicemail e cloud Operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="1207d-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="1207d-p103">I numeri non assegnati sono numeri di telefono validi per l'organizzazione ma non assegnati a un utente o un telefono. La tabella dei numeri non assegnati identifica come si desidera gestire le chiamata a numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="1207d-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

<span data-ttu-id="1207d-p104">La modalità di configurazione della tabella dei numeri non assegnati dipende dal modo in cui si intende utilizzare tale tabella. È possibile configurare la tabella con tutti gli interni validi dell'organizzazione, solo con gli interni non assegnati o con una combinazione di numeri di entrambi i tipi. La tabella dei numeri non assegnati può includere sia numeri assegnati che numeri non assegnati, ma viene richiamata solo se un chiamante compone un numero non assegnato. Se nella tabella dei numeri non assegnati si inseriscono tutti gli interni validi, è possibile specificare l'azione da eseguire quando un utente lascia l'organizzazione, senza alcuna necessità di riconfigurare la tabella. Se nella tabella si inseriscono interni non assegnati, è possibile personalizzare l'azione da eseguire per numeri specifici. Se, ad esempio, si modifica l'interno del servizio di assistenza clienti, è possibile inserire il vecchio numero nella tabella e assegnarlo a un annuncio in cui viene indicato il nuovo numero.</span><span class="sxs-lookup"><span data-stu-id="1207d-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1207d-115">Prima di configurare la tabella dei numeri non assegnati è necessario che sia definito almeno un annuncio o che sia impostato un Operatore automatico di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="1207d-115">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="1207d-116">Nella pagina **Numero non assegnato** viene visualizzato un elenco degli intervalli di numeri non assegnati definiti per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1207d-116">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="1207d-117">Attività eseguibili</span><span class="sxs-lookup"><span data-stu-id="1207d-117">Tasks you can perform</span></span>

<span data-ttu-id="1207d-118">Nella pagina **Numero non assegnato** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="1207d-118">You can perform the following tasks from the **Unassigned Number** page:</span></span>

- <span data-ttu-id="1207d-119">Creare un nuovo intervallo di numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="1207d-119">Create a new unassigned number range</span></span>

- <span data-ttu-id="1207d-120">Modificare un intervallo di numeri non assegnati esistente</span><span class="sxs-lookup"><span data-stu-id="1207d-120">Change an existing unassigned number range</span></span>

- <span data-ttu-id="1207d-121">Eliminare un intervallo di numeri non assegnato</span><span class="sxs-lookup"><span data-stu-id="1207d-121">Delete an unassigned number range</span></span>

- <span data-ttu-id="1207d-122">Modificare l'ordine degli intervalli di numeri non assegnati, per determinare quale azione applicare per prima a una chiamata in arrivo corrispondente a un numero non assegnato.</span><span class="sxs-lookup"><span data-stu-id="1207d-122">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="1207d-123">Informazioni sull'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="1207d-123">UI Reference</span></span>

<span data-ttu-id="1207d-124">Nell'elenco seguente sono descritti i comandi della pagina.</span><span class="sxs-lookup"><span data-stu-id="1207d-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="1207d-125">**Nuovo** Avvia un nuovo intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="1207d-125">**New** Starts a new unassigned number range.</span></span>

- <span data-ttu-id="1207d-126">**Modifica** Apre l'intervallo di numeri non assegnati selezionato per la modifica, seleziona tutti gli intervalli di numeri non assegnati nell'elenco oppure elimina l'intervallo di numeri non assegnati selezionato.</span><span class="sxs-lookup"><span data-stu-id="1207d-126">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>

- <span data-ttu-id="1207d-127">**Sposta su** Sposta l'intervallo di numeri non assegnati selezionato verso l'alto nell'elenco in modo che Skype for Business Server lo trovi più rapidamente e applii l'azione specificata prima di applicare le azioni specificate per altri intervalli nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="1207d-127">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1207d-128">Skype for Business Server cerca la tabella dei numeri non assegnati dall'alto verso il basso e utilizza il primo intervallo che corrisponde al numero non assegnato.</span><span class="sxs-lookup"><span data-stu-id="1207d-128">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="1207d-129">Se, ad esempio, per un intervallo è specificata un'azione "ultimo tentativo", assicurarsi che tale intervallo si trovi alla fine dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="1207d-129">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

- <span data-ttu-id="1207d-130">**Sposta giù** Sposta l'intervallo di numeri non assegnati selezionato verso il basso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="1207d-130">**Move down** Moves the selected unassigned number range down in the list.</span></span>

- <span data-ttu-id="1207d-131">**Conferma tutto** Salva tutte le modifiche apportate agli intervalli di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="1207d-131">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1207d-132">Questo comando consente di salvare tutte le modifiche eseguite nelle pagine **Nuovo numero non assegnato** e **Modifica numero non assegnato**.</span><span class="sxs-lookup"><span data-stu-id="1207d-132">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>

- <span data-ttu-id="1207d-133">**Aggiorna** Aggiorna l'elenco degli intervalli di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="1207d-133">**Refresh** Refreshes the list of unassigned number ranges.</span></span>

<span data-ttu-id="1207d-134">L'elenco seguente descrive i campi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="1207d-134">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="1207d-135">**Name** Nome univoco che identifica l'intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="1207d-135">**Name** The unique name that identifies the unassigned number range.</span></span>

- <span data-ttu-id="1207d-136">**Stato** Mostra quali intervalli di numeri sono stati salvati nel database e quali no.</span><span class="sxs-lookup"><span data-stu-id="1207d-136">**State** Shows which number ranges have been saved to the database and which have not.</span></span>

- <span data-ttu-id="1207d-137">**Intervallo iniziale** Numero iniziale dell'intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="1207d-137">**Start range** The beginning number of the unassigned number range.</span></span>

- <span data-ttu-id="1207d-138">**Intervallo di fine** Numero finale dell'intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="1207d-138">**End range** The ending number of the unassigned number range.</span></span>

- <span data-ttu-id="1207d-139">**Destinazione** ID del servizio applicazione che ospita l'applicazione Annuncio che gestirà le chiamate in arrivo a questo intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="1207d-139">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

- <span data-ttu-id="1207d-140">**Annuncio** Annuncio che verrà riprodotto per questo intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="1207d-140">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>

<span data-ttu-id="1207d-141">Per informazioni dettagliate sulle funzionalità e sulle funzionalità degli annunci, vedere [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="1207d-141">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="1207d-142">Per informazioni dettagliate sull'utilizzo di intervalli di numeri non assegnati, vedere [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="1207d-142">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


