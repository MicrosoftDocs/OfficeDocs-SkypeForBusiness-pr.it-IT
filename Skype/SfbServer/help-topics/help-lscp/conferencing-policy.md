---
title: Criteri conferenza
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
description: Il criterio di conferenza definisce le caratteristiche e le funzionalità disponibili agli utenti durante una conferenza, detta anche riunione.
ms.openlocfilehash: 6d69c463a9aa8a1e151b0787dfbfebf4e24fb693
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115366"
---
# <a name="conferencing-policy"></a><span data-ttu-id="efd42-103">Criteri conferenza</span><span class="sxs-lookup"><span data-stu-id="efd42-103">Conferencing Policy</span></span>

<span data-ttu-id="efd42-104">Il criterio di conferenza definisce le caratteristiche e le funzionalità disponibili agli utenti durante una conferenza, detta anche riunione.</span><span class="sxs-lookup"><span data-stu-id="efd42-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span>

<span data-ttu-id="efd42-105">I criteri di conferenza includono il criterio globale e, facoltativamente, uno o più criteri per sito e utente:</span><span class="sxs-lookup"><span data-stu-id="efd42-105">Conferencing policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="efd42-106">**Criteri globali:** Il criterio globale viene creato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="efd42-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="efd42-107">È possibile modificare il criterio globale, ma non eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="efd42-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="efd42-108">Se si tenta di rimuoverlo, tutte le impostazioni verranno ripristinate ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="efd42-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="efd42-109">**Criteri sito (facoltativo):** È possibile creare uno o più criteri di conferenza del sito, ognuno dei quali si applica a un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="efd42-109">**Site policies (optional):** You can create one or more site conferencing policies, each of which applies to a specific site.</span></span> <span data-ttu-id="efd42-110">I criteri sito prevalgono sul criterio globale.</span><span class="sxs-lookup"><span data-stu-id="efd42-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="efd42-111">**Criteri utente (facoltativo):** È possibile creare uno o più criteri di conferenza utente, ognuno dei quali si applica a un utente o a un gruppo di utenti specifico.</span><span class="sxs-lookup"><span data-stu-id="efd42-111">**User policies (optional):** You can create one or more user conferencing policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="efd42-112">I criteri utente hanno la priorità sul criterio globale e sui criteri sito.</span><span class="sxs-lookup"><span data-stu-id="efd42-112">User policies override the global policy and site policies.</span></span>

<span data-ttu-id="efd42-113">La pagina **Criteri conferenza** mostra tutti i criteri di conferenza definiti per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="efd42-113">The **Conferencing Policy** page displays a list of all the conferencing policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="efd42-114">Attività eseguibili</span><span class="sxs-lookup"><span data-stu-id="efd42-114">Tasks you can perform</span></span>

<span data-ttu-id="efd42-115">Nella pagina **Criteri percorso** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="efd42-115">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="efd42-116">Creare un nuovo criteri di conferenza sito o di conferenza utente</span><span class="sxs-lookup"><span data-stu-id="efd42-116">Create a new site conferencing policy or user conferencing policy</span></span>

- <span data-ttu-id="efd42-117">Modificare il criterio globale o un criterio sito o utente esistente</span><span class="sxs-lookup"><span data-stu-id="efd42-117">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="efd42-118">Eliminare un criterio sito o utente</span><span class="sxs-lookup"><span data-stu-id="efd42-118">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="efd42-119">Riferimento all'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="efd42-119">UI Reference</span></span>

<span data-ttu-id="efd42-120">Nell'elenco seguente sono descritti i comandi della pagina.</span><span class="sxs-lookup"><span data-stu-id="efd42-120">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="efd42-121">**Nuovo** Avvia un nuovo criterio di conferenza del sito o criteri di conferenza utente.</span><span class="sxs-lookup"><span data-stu-id="efd42-121">**New** Starts a new site conferencing policy or user conferencing policy.</span></span>

- <span data-ttu-id="efd42-122">**Modifica** Apre il criterio di conferenza selezionato per modificarlo, seleziona tutti i criteri conferenza nell'elenco o elimina il criterio sito o il criterio utente selezionato.</span><span class="sxs-lookup"><span data-stu-id="efd42-122">**Edit** Opens the selected conferencing policy to edit it, selects all conferencing policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="efd42-123">Per il criterio globale, **Elimina** consente di riportare le impostazioni ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="efd42-123">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="efd42-124">**Aggiorna** Aggiorna l'elenco dei criteri conferenza.</span><span class="sxs-lookup"><span data-stu-id="efd42-124">**Refresh** Refreshes the list of conferencing policies.</span></span>

<span data-ttu-id="efd42-125">L'elenco seguente descrive i campi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="efd42-125">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="efd42-126">**Nome** Identifica il criterio di conferenza.</span><span class="sxs-lookup"><span data-stu-id="efd42-126">**Name** Identifies the conferencing policy.</span></span>

- <span data-ttu-id="efd42-127">**Ambito** Identifica l'ambito dei criteri di conferenza: globale, sito o utente.</span><span class="sxs-lookup"><span data-stu-id="efd42-127">**Scope** Identifies the scope of the conferencing policy: global, site, or user.</span></span>

- <span data-ttu-id="efd42-128">**Collaborazione dati** Selezionato se il criterio di conferenza specifica che la collaborazione dati è consentita nelle conferenze.</span><span class="sxs-lookup"><span data-stu-id="efd42-128">**Data collaboration** Checked if the conferencing policy specifies that data collaboration is allowed in conferences.</span></span>

- <span data-ttu-id="efd42-129">**Condivisione applicazioni** Selezionato se il criterio di conferenza specifica che la condivisione delle applicazioni è consentita nelle conferenze.</span><span class="sxs-lookup"><span data-stu-id="efd42-129">**Application sharing** Checked if the conferencing policy specifies that application sharing is allowed in conferences.</span></span>

- <span data-ttu-id="efd42-130">**Audio** Selezionato se il criterio di conferenza specifica che l'audio è consentito nelle conferenze.</span><span class="sxs-lookup"><span data-stu-id="efd42-130">**Audio** Checked if the conferencing policy specifies that audio is allowed in conferences.</span></span>

- <span data-ttu-id="efd42-131">**Video** Selezionato se il criterio di conferenza specifica che il video è consentito nelle conferenze.</span><span class="sxs-lookup"><span data-stu-id="efd42-131">**Video** Checked if the conferencing policy specifies that video is allowed in conferences.</span></span>

- <span data-ttu-id="efd42-132">**PSTN** Selezionato se il criterio di conferenza specifica che le conferenze telefoniche con accesso esterno PSTN sono consentite.</span><span class="sxs-lookup"><span data-stu-id="efd42-132">**PSTN** Checked if the conferencing policy specifies that PSTN dial-in conferencing is allowed.</span></span>

- <span data-ttu-id="efd42-133">**Registrazione** Selezionato se il criterio di conferenza specifica che la registrazione è consentita nelle conferenze.</span><span class="sxs-lookup"><span data-stu-id="efd42-133">**Recording** Checked if the conferencing policy specifies that recording is allowed in conferences.</span></span>

<span data-ttu-id="efd42-134">Per informazioni dettagliate sulle caratteristiche e sulle funzionalità di conferenza, vedere [Overview of Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-conferencing) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="efd42-134">For details about conferencing features and capabilities, see [Overview of Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-conferencing) in the Planning documentation.</span></span> <span data-ttu-id="efd42-135">Per informazioni dettagliate sull'uso dei criteri di conferenza, vedere [Conferencing Policies](/previous-versions/office/lync-server-2013/lync-server-2013-conferencing-policies) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="efd42-135">For details about working with conferencing policies, see [Conferencing Policies](/previous-versions/office/lync-server-2013/lync-server-2013-conferencing-policies) in the Operations documentation.</span></span>