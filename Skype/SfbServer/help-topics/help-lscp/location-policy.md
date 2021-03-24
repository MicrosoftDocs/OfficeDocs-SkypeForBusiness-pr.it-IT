---
title: Criteri percorso
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
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: I criteri percorso determinano se i servizi di emergenza avanzati sono abilitati e come vengono utilizzati, oltre a definire come vengono utilizzate le informazioni percorso per utenti e contatti.
ms.openlocfilehash: 4a5cf1ab5ec17681adef9b03cab06bed04285628
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099702"
---
# <a name="location-policy"></a><span data-ttu-id="30035-103">Criteri percorso</span><span class="sxs-lookup"><span data-stu-id="30035-103">Location Policy</span></span>

<span data-ttu-id="30035-104">I criteri percorso determinano se i servizi di emergenza avanzati sono abilitati e come vengono utilizzati, oltre a definire come vengono utilizzate le informazioni percorso per utenti e contatti.</span><span class="sxs-lookup"><span data-stu-id="30035-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

<span data-ttu-id="30035-105">I criteri percorso includono un criterio globale e, facoltativamente, uno o più criteri sito e utente:</span><span class="sxs-lookup"><span data-stu-id="30035-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="30035-106">**Criteri globali:** Il criterio globale viene creato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="30035-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="30035-107">È possibile modificare il criterio globale, ma non eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="30035-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="30035-108">Se si tenta di rimuoverlo, tutte le impostazioni verranno ripristinate ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="30035-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="30035-109">**Criteri sito (facoltativo):** È possibile creare uno o più criteri percorso sito, ognuno dei quali si applica a un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="30035-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="30035-110">I criteri sito prevalgono sul criterio globale.</span><span class="sxs-lookup"><span data-stu-id="30035-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="30035-111">**Criteri utente (facoltativo):** È possibile creare uno o più criteri percorso utente, ognuno dei quali si applica a un utente o a un gruppo di utenti specifico.</span><span class="sxs-lookup"><span data-stu-id="30035-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="30035-112">I criteri utente prevalgono sul criteri globale e i criteri sito.</span><span class="sxs-lookup"><span data-stu-id="30035-112">User policies override the global policy and site policies.</span></span>

> [!NOTE]
> <span data-ttu-id="30035-113">È inoltre possibile assegnare criteri percorso a siti di rete, ovvero gruppi di subnet.</span><span class="sxs-lookup"><span data-stu-id="30035-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="30035-114">I criteri percorso assegnati a siti di rete hanno la precedenza su tutti gli altri criteri utente.</span><span class="sxs-lookup"><span data-stu-id="30035-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="30035-115">Per informazioni dettagliate sull'assegnazione dei criteri percorso ai siti di rete tramite i cmdlet, vedere [Add a location policy to a network site in Skype for Business Server 2015.](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md)</span><span class="sxs-lookup"><span data-stu-id="30035-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="30035-116">Per informazioni dettagliate sull'utilizzo del Pannello di controllo di Skype for Business Server per assegnare un criterio percorso a un sito di rete, vedere [Configuring Network Sites.](/previous-versions/office/lync-server-2013/lync-server-2013-creating-or-modifying-network-sites)</span><span class="sxs-lookup"><span data-stu-id="30035-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](/previous-versions/office/lync-server-2013/lync-server-2013-creating-or-modifying-network-sites).</span></span>

<span data-ttu-id="30035-117">Nella pagina **Criteri percorso** viene visualizzato un elenco di tutti i criteri percorso definiti per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="30035-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="30035-118">Attività eseguibili</span><span class="sxs-lookup"><span data-stu-id="30035-118">Tasks you can perform</span></span>

<span data-ttu-id="30035-119">Nella pagina **Criteri percorso** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="30035-119">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="30035-120">Creare un nuovo criterio percorso sito o utente</span><span class="sxs-lookup"><span data-stu-id="30035-120">Create a new site location policy or user location policy</span></span>

- <span data-ttu-id="30035-121">Modificare il criterio globale o un criterio sito o utente esistente</span><span class="sxs-lookup"><span data-stu-id="30035-121">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="30035-122">Eliminare un criterio sito o utente</span><span class="sxs-lookup"><span data-stu-id="30035-122">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="30035-123">Riferimento all'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="30035-123">UI Reference</span></span>

<span data-ttu-id="30035-124">Nell'elenco seguente sono descritti i comandi della pagina.</span><span class="sxs-lookup"><span data-stu-id="30035-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="30035-125">**Nuovo** Avvia un nuovo criterio percorso sito o criteri percorso utente.</span><span class="sxs-lookup"><span data-stu-id="30035-125">**New** Starts a new site location policy or user location policy.</span></span>

- <span data-ttu-id="30035-126">**Modifica** Apre il criterio percorso selezionato per modificarlo, seleziona tutti i criteri percorso nell'elenco o elimina il criterio sito o il criterio utente selezionato.</span><span class="sxs-lookup"><span data-stu-id="30035-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="30035-127">Per il criterio globale, **Elimina** consente di riportare le impostazioni ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="30035-127">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="30035-128">**Aggiorna** Aggiorna l'elenco dei criteri percorso.</span><span class="sxs-lookup"><span data-stu-id="30035-128">**Refresh** Refreshes the list of location policies.</span></span>

<span data-ttu-id="30035-129">L'elenco seguente descrive i campi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="30035-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="30035-130">**Nome** Identifica il criterio percorso.</span><span class="sxs-lookup"><span data-stu-id="30035-130">**Name** Identifies the location policy.</span></span>

- <span data-ttu-id="30035-131">**Ambito** Identifica l'ambito dei criteri percorso: globale, sito o utente.</span><span class="sxs-lookup"><span data-stu-id="30035-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>

- <span data-ttu-id="30035-132">**E9-1-1** Selezionato se gli utenti assegnati a questo criterio percorso sono abilitati per E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="30035-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>

- <span data-ttu-id="30035-133">**Posizione** Specifica se agli utenti viene richiesto di immettere o meno le informazioni sulla posizione quando il client si registra con Skype for Business Server in una nuova posizione e se visualizzano una dichiarazione di non responsabilità se ignorano il prompt senza immettere le informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="30035-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>

- <span data-ttu-id="30035-134">**Utilizzo PSTN** Specifica l'utilizzo pstN (Public Switched Telephone Network) utilizzato per determinare la route vocale utilizzata per instradare le chiamate di emergenza dai client che utilizzano questo profilo.</span><span class="sxs-lookup"><span data-stu-id="30035-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>

- <span data-ttu-id="30035-135">**Numero E9-1-1** Specifica il numero composto per raggiungere i servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="30035-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="30035-136">**Maschera E9-1-1** Specifica un numero composto da un utente che viene quindi convertito nel numero di chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="30035-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>

<span data-ttu-id="30035-137">Per informazioni dettagliate VoIP aziendale funzionalità e funzionalità del servizio di emergenza, vedere [Overview of E9-1-1](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="30035-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1) in the Planning documentation.</span></span> <span data-ttu-id="30035-138">Per informazioni dettagliate sull'utilizzo di criteri percorso, vedere [Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="30035-138">For details about working with location policies, see [Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information) in the Operations documentation.</span></span>