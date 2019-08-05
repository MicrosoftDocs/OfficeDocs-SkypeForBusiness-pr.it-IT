---
title: Criteri percorso
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: I criteri percorso determinano se il servizio Enhanced 9-1-1 (E9-1-1) è abilitato e come viene usato, nonché come vengono usate le informazioni sulla posizione per utenti e contatti.
ms.openlocfilehash: cb28dd60793da6681f2a8db71cf40ce8a5eda6fc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194434"
---
# <a name="location-policy"></a><span data-ttu-id="7d11d-103">Criteri percorso</span><span class="sxs-lookup"><span data-stu-id="7d11d-103">Location Policy</span></span>

<span data-ttu-id="7d11d-104">I criteri percorso determinano se il servizio Enhanced 9-1-1 (E9-1-1) è abilitato e come viene usato, nonché come vengono usate le informazioni sulla posizione per utenti e contatti.</span><span class="sxs-lookup"><span data-stu-id="7d11d-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

<span data-ttu-id="7d11d-105">I criteri percorso includono un criterio globale e, facoltativamente, uno o più criteri sito e utente:</span><span class="sxs-lookup"><span data-stu-id="7d11d-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="7d11d-106">**Criteri globali:** Il criterio globale viene creato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7d11d-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="7d11d-107">È possibile modificare il criterio globale, ma non eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="7d11d-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="7d11d-108">Se si tenta di rimuoverlo, tutte le impostazioni verranno ripristinate ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="7d11d-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="7d11d-109">**Criteri sito (facoltativo):** È possibile creare uno o più criteri per la posizione del sito, ognuno dei quali si applica a un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="7d11d-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="7d11d-110">I criteri sito prevalgono sul criterio globale.</span><span class="sxs-lookup"><span data-stu-id="7d11d-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="7d11d-111">**Criteri utente (facoltativo):** È possibile creare uno o più criteri posizione utente, ognuno dei quali si applica a un utente o un gruppo di utenti specifico.</span><span class="sxs-lookup"><span data-stu-id="7d11d-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="7d11d-112">I criteri utente prevalgono sui criteri globale e i criteri sito.</span><span class="sxs-lookup"><span data-stu-id="7d11d-112">User policies override the global policy and site policies.</span></span>

> [!NOTE]
> <span data-ttu-id="7d11d-113">È inoltre possibile assegnare criteri percorso a siti di rete, ovvero gruppi di subnet.</span><span class="sxs-lookup"><span data-stu-id="7d11d-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="7d11d-114">I criteri percorso assegnati a siti di rete hanno la precedenza su tutti gli altri criteri utente.</span><span class="sxs-lookup"><span data-stu-id="7d11d-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="7d11d-115">Per informazioni dettagliate sull'assegnazione di criteri di posizione ai siti di rete tramite cmdlet, vedere [aggiungere un criterio di posizione a un sito di rete in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="7d11d-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="7d11d-116">Per informazioni dettagliate sull'uso del pannello di controllo di Skype for Business Server per assegnare un criterio di posizione a un sito di rete, vedere [configurazione dei siti di rete](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span><span class="sxs-lookup"><span data-stu-id="7d11d-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span></span>

<span data-ttu-id="7d11d-117">Nella pagina **Criteri percorso** viene visualizzato un elenco di tutti i criteri percorso definiti per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7d11d-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="7d11d-118">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="7d11d-118">Tasks you can perform</span></span>

<span data-ttu-id="7d11d-119">Nella pagina **Criteri percorso** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="7d11d-119">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="7d11d-120">Creare un nuovo criterio percorso sito o utente</span><span class="sxs-lookup"><span data-stu-id="7d11d-120">Create a new site location policy or user location policy</span></span>

- <span data-ttu-id="7d11d-121">Modificare il criterio globale o un criterio sito o utente esistente</span><span class="sxs-lookup"><span data-stu-id="7d11d-121">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="7d11d-122">Eliminare un criterio sito o utente</span><span class="sxs-lookup"><span data-stu-id="7d11d-122">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="7d11d-123">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="7d11d-123">UI Reference</span></span>

<span data-ttu-id="7d11d-124">L'elenco seguente descrive i comandi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="7d11d-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="7d11d-125">**Nuovo** Avvia un nuovo criterio della posizione del sito o dei criteri di posizione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="7d11d-125">**New** Starts a new site location policy or user location policy.</span></span>

- <span data-ttu-id="7d11d-126">**Modifica** Apre il criterio della posizione selezionata per modificarlo, seleziona tutti i criteri di posizione nell'elenco o Elimina i criteri del sito o i criteri utente selezionati.</span><span class="sxs-lookup"><span data-stu-id="7d11d-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7d11d-127">Per il criterio globale, il comando **Elimina** ripristina le impostazioni ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="7d11d-127">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="7d11d-128">**Aggiornare** Aggiorna l'elenco dei criteri di posizione.</span><span class="sxs-lookup"><span data-stu-id="7d11d-128">**Refresh** Refreshes the list of location policies.</span></span>

<span data-ttu-id="7d11d-129">L'elenco seguente descrive i campi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="7d11d-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="7d11d-130">**Nome** Identifica il criterio di posizione.</span><span class="sxs-lookup"><span data-stu-id="7d11d-130">**Name** Identifies the location policy.</span></span>

- <span data-ttu-id="7d11d-131">**Ambito** Identifica l'ambito dei criteri di posizione: globale, sito o utente.</span><span class="sxs-lookup"><span data-stu-id="7d11d-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>

- <span data-ttu-id="7d11d-132">**E9-1-1** Verificare se gli utenti assegnati a questo criterio di posizione sono abilitati per E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="7d11d-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>

- <span data-ttu-id="7d11d-133">**Posizione** Specifica se viene chiesto o meno agli utenti di immettere le informazioni sulla posizione quando il loro client esegue la registrazione con Skype for Business Server in una nuova posizione e se viene respinto il messaggio senza immettere le informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="7d11d-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>

- <span data-ttu-id="7d11d-134">**Uso PSTN** Specifica l'utilizzo PSTN (Public Switched Telephone Network) usato per determinare la route vocale usata per instradare chiamate di emergenza da client che usano questo profilo.</span><span class="sxs-lookup"><span data-stu-id="7d11d-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>

- <span data-ttu-id="7d11d-135">**Numero E9-1-1** Specifica il numero composto per raggiungere i servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="7d11d-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="7d11d-136">**Maschera E9-1-1** Specifica un numero che un utente compone e quindi tradotto nel numero di chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="7d11d-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>

<span data-ttu-id="7d11d-137">Per informazioni dettagliate sulle funzionalità e le funzionalità del servizio di emergenza VoIP aziendale, vedere [Panoramica di E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="7d11d-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="7d11d-138">Per informazioni dettagliate sull'uso dei criteri percorso, vedere [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="7d11d-138">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


