---
title: Configurazione riunione
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
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
description: Le impostazioni di configurazione delle riunioni definiscono il tipo di conferenze (denominate anche riunioni) che gli utenti possono creare e controllano in che modo (o se) gli utenti anonimi e gli utenti delle conferenze telefoniche con accesso esterno possono partecipare a queste conferenze. Queste impostazioni si applicano solo alle riunioni pianificate. Non si applicano alle riunioni ad hoc create facendo clic sull'opzione Riunione ora nel client.
ms.openlocfilehash: e53297aaae7707f8cc0ae4821a97afb78e0382e2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099662"
---
# <a name="meeting-configuration"></a><span data-ttu-id="30e6d-105">Configurazione riunione</span><span class="sxs-lookup"><span data-stu-id="30e6d-105">Meeting Configuration</span></span>

<span data-ttu-id="30e6d-106">Le impostazioni di configurazione delle riunioni consentono di definire il tipo di conferenze (denominate anche "riunioni") che gli utenti possono creare e di controllare come (e se) gli utenti anonimi e gli utenti di conferenze telefoniche possono partecipare a queste conferenze.</span><span class="sxs-lookup"><span data-stu-id="30e6d-106">Meeting configuration settings define the type of conferences (also called "meetings") that users can create, and control how (or whether) anonymous users and dial-in conferencing users can join these conferences.</span></span> <span data-ttu-id="30e6d-107">Queste impostazioni si applicano solo alle riunioni pianificate.</span><span class="sxs-lookup"><span data-stu-id="30e6d-107">These settings only apply to scheduled meetings.</span></span> <span data-ttu-id="30e6d-108">Non si applicano alle riunioni ad hoc create facendo clic sull'opzione Riunione ora nel client.</span><span class="sxs-lookup"><span data-stu-id="30e6d-108">They do not apply to ad-hoc meetings created by clicking the Meet Now option in the client.</span></span>

<span data-ttu-id="30e6d-109">Le configurazioni delle riunioni si applicano a livello globale, di sito o di pool:</span><span class="sxs-lookup"><span data-stu-id="30e6d-109">Meeting configurations apply on the global, site, or pool level:</span></span>

- <span data-ttu-id="30e6d-110">**Configurazione riunione globale:** La configurazione della riunione globale viene creata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="30e6d-110">**Global meeting configuration:** The global meeting configuration is created by default.</span></span> <span data-ttu-id="30e6d-111">È possibile modificare la configurazione della riunione globale, ma non eliminarla.</span><span class="sxs-lookup"><span data-stu-id="30e6d-111">You can edit the global meeting configuration, but you cannot delete it.</span></span> <span data-ttu-id="30e6d-112">Se si tenta di rimuovere la configurazione della riunione globale, tutte le impostazioni vengono reimpostate ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="30e6d-112">If you try to remove the global meeting configuration, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="30e6d-113">**Configurazione riunione sito (facoltativo):** È possibile creare una o più configurazioni di riunioni del sito, ognuna delle quali si applica a un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="30e6d-113">**Site meeting configuration (optional):** You can create one or more site meeting configurations, each of which applies to a specific site.</span></span> <span data-ttu-id="30e6d-114">Le configurazioni sito prevalgono sulla configurazione globale.</span><span class="sxs-lookup"><span data-stu-id="30e6d-114">Site configurations override the global configuration.</span></span>

- <span data-ttu-id="30e6d-115">**Configurazione riunione pool (facoltativo):** È possibile creare una o più configurazioni di riunione del pool, ognuna delle quali si applica a un pool specifico.</span><span class="sxs-lookup"><span data-stu-id="30e6d-115">**Pool meeting configuration (optional):** You can create one or more pool meeting configurations, each of which applies to a specific pool.</span></span> <span data-ttu-id="30e6d-116">Le configurazioni pool prevalgono sulla configurazione globale e sulle configurazioni sito.</span><span class="sxs-lookup"><span data-stu-id="30e6d-116">Pool configurations override the global configuration and site configurations.</span></span>

<span data-ttu-id="30e6d-117">Nella pagina **Configurazione riunione** è presente un elenco di tutte le configurazioni riunione definite per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="30e6d-117">The **Meeting Configuration** page displays a list of all the meeting configurations that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="30e6d-118">Attività eseguibili</span><span class="sxs-lookup"><span data-stu-id="30e6d-118">Tasks you can perform</span></span>

<span data-ttu-id="30e6d-119">Nella pagina **Configurazione riunione** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="30e6d-119">You can perform the following tasks from the **Meeting Configuration** page:</span></span>

- <span data-ttu-id="30e6d-120">Creare una nuova configurazione riunione per sito o pool</span><span class="sxs-lookup"><span data-stu-id="30e6d-120">Create a new site meeting configuration or pool meeting configuration</span></span>

- <span data-ttu-id="30e6d-121">Modificare la configurazione globale o una configurazione sito o pool esistente</span><span class="sxs-lookup"><span data-stu-id="30e6d-121">Change the global configuration or an existing site configuration or pool configuration</span></span>

- <span data-ttu-id="30e6d-122">Eliminare una configurazione sito o pool</span><span class="sxs-lookup"><span data-stu-id="30e6d-122">Delete a site configuration or pool configuration</span></span>

## <a name="ui-reference"></a><span data-ttu-id="30e6d-123">Informazioni sull'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="30e6d-123">UI Reference</span></span>

<span data-ttu-id="30e6d-124">Nell'elenco seguente sono descritti i comandi della pagina.</span><span class="sxs-lookup"><span data-stu-id="30e6d-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="30e6d-125">**Nuovo** Avvia una nuova configurazione di riunione del sito o di riunione del pool.</span><span class="sxs-lookup"><span data-stu-id="30e6d-125">**New** Starts a new site meeting configuration or pool meeting configuration.</span></span>

- <span data-ttu-id="30e6d-126">**Modifica** Apre la configurazione di riunione selezionata per modificarla, seleziona tutte le configurazioni riunione nell'elenco o elimina la configurazione del sito o del pool selezionata.</span><span class="sxs-lookup"><span data-stu-id="30e6d-126">**Edit** Opens the selected meeting configuration to edit it, selects all meeting configurations in the list, or deletes the selected site configuration or pool configuration.</span></span>

    > [!NOTE]
    > <span data-ttu-id="30e6d-127">Per la configurazione riunione globale, l'opzione **Elimina** consente di riportare le impostazioni ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="30e6d-127">For the global meeting configuration, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="30e6d-128">**Aggiorna** Aggiorna l'elenco delle configurazioni delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="30e6d-128">**Refresh** Refreshes the list of meeting configurations.</span></span>

<span data-ttu-id="30e6d-129">L'elenco seguente descrive i campi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="30e6d-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="30e6d-130">**Nome** Identifica la configurazione della riunione.</span><span class="sxs-lookup"><span data-stu-id="30e6d-130">**Name** Identifies the meeting configuration.</span></span>

- <span data-ttu-id="30e6d-131">**Ambito** Identifica l'ambito della configurazione della riunione: globale, sito o pool.</span><span class="sxs-lookup"><span data-stu-id="30e6d-131">**Scope** Identifies the scope of the meeting configuration: global, site, or pool.</span></span>

<span data-ttu-id="30e6d-132">Per informazioni dettagliate sull'utilizzo di configurazioni riunioni, vedere [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="30e6d-132">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) in the Operations documentation.</span></span>