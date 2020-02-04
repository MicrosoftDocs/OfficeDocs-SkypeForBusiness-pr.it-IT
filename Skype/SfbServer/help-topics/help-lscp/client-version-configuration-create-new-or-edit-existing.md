---
title: Configurazione della versione client crea nuovi o modifica esistenti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
description: Le impostazioni di configurazione della versione client vengono utilizzate per attivare o disattivare il controllo della versione client. La configurazione della versione client globale viene installata con Skype for Business Server e viene usata per abilitare o disabilitare il controllo della versione client per l'intera distribuzione del server. Se la configurazione globale è abilitata, tutti i criteri relativi alla versione client disponibili verranno applicati quando gli utenti tentano l'accesso. Se non si desidera che venga eseguito il controllo della versione client, è possibile disabilitare la configurazione globale della versione client.
ms.openlocfilehash: f970053cb359fb0735535720da7c8310e015ac37
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41686960"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a><span data-ttu-id="19836-106">Configurazione versione client: crearne una nuova o modificarne una esistente</span><span class="sxs-lookup"><span data-stu-id="19836-106">Client Version Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="19836-107">Le impostazioni di configurazione della versione client vengono utilizzate per attivare o disattivare il controllo della versione client.</span><span class="sxs-lookup"><span data-stu-id="19836-107">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="19836-108">La configurazione della versione client globale viene installata con Skype for Business Server e viene usata per abilitare o disabilitare il controllo della versione client per l'intera distribuzione del server.</span><span class="sxs-lookup"><span data-stu-id="19836-108">The Global client version configuration installs with Skype for Business Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="19836-109">Se la configurazione globale è abilitata, tutti i criteri relativi alla versione client disponibili verranno applicati quando gli utenti tentano l'accesso.</span><span class="sxs-lookup"><span data-stu-id="19836-109">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="19836-110">Se non si desidera che venga eseguito il controllo della versione client, è possibile disabilitare la configurazione globale della versione client.</span><span class="sxs-lookup"><span data-stu-id="19836-110">You can disable the Global client version configuration if you do not want any client version control to occur.</span></span>

<span data-ttu-id="19836-p103">È inoltre possibile creare configurazioni della versione client specifiche di sito, per poter abilitare o disabilitare il controllo della versione client in base al sito. Le configurazioni specifiche di sito hanno la precedenza sulla configurazione globale.</span><span class="sxs-lookup"><span data-stu-id="19836-p103">You can also create site-specific client version configurations, allowing you to enable or disable client version control by site. Site-specific configurations take precedence over the Global configuration.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="19836-113">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="19836-113">Tasks you can perform</span></span>

<span data-ttu-id="19836-114">Nella pagina **Nuova configurazione versione client** o **Modifica configurazione versione client** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="19836-114">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="19836-115">Aggiungere o modificare il nome della configurazione della versione client.</span><span class="sxs-lookup"><span data-stu-id="19836-115">Add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="19836-116">Abilitare o disabilitare il controllo della versione client a livello globale o in base al sito.</span><span class="sxs-lookup"><span data-stu-id="19836-116">Enable or disable client version control globally or for the specific site.</span></span>

- <span data-ttu-id="19836-117">Aggiungere o modificare l'azione predefinita per la configurazione della versione client.</span><span class="sxs-lookup"><span data-stu-id="19836-117">Add or modify the default action for the client version configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="19836-118">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="19836-118">UI Reference</span></span>

<span data-ttu-id="19836-119">Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="19836-119">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="19836-120">**Ambito** Identifica l'ambito (globale o sito) della configurazione della versione client.</span><span class="sxs-lookup"><span data-stu-id="19836-120">**Scope** Identifies the scope (Global or Site) of the client version configuration.</span></span>

- <span data-ttu-id="19836-121">**Nome** È possibile aggiungere o modificare il nome della configurazione della versione client.</span><span class="sxs-lookup"><span data-stu-id="19836-121">**Name** You can add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="19836-122">**Abilitare il controllo della versione** È possibile abilitare o disabilitare il controllo della versione client a livello globale o per il sito, a seconda dell'ambito della configurazione.</span><span class="sxs-lookup"><span data-stu-id="19836-122">**Enable version control** You can enable or disable client version control globally or for the site, depending on the scope of the configuration.</span></span>

- <span data-ttu-id="19836-123">**Azione predefinita** Puoi selezionare l'azione predefinita che verrà applicata quando un utente tenta di accedere usando un'applicazione client per cui non esistono criteri di versione client specifici.</span><span class="sxs-lookup"><span data-stu-id="19836-123">**Default action** You can select the default action that will be applied when a user attempts to log on using a client application for which there is no specific client version policy.</span></span> <span data-ttu-id="19836-124">Le opzioni disponibili sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="19836-124">You have the following options:</span></span>

  - <span data-ttu-id="19836-125">**Consenti** Consente al client di accedere se la versione client non corrisponde a un filtro nell'elenco dei criteri di versione client.</span><span class="sxs-lookup"><span data-stu-id="19836-125">**Allow** Allows the client to log on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="19836-126">**Blocco** Impedisce che il client acceda se la versione client non corrisponde a un filtro nell'elenco dei criteri di versione client.</span><span class="sxs-lookup"><span data-stu-id="19836-126">**Block** Prevents the client from logging on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="19836-127">**Blocco con URL** Impedisce che il client acceda se la versione client non corrisponde a un filtro nell'elenco dei criteri di versione client e include un messaggio di errore contenente un URL in cui è possibile scaricare un nuovo client.</span><span class="sxs-lookup"><span data-stu-id="19836-127">**Block with URL** Prevents the client from logging on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="19836-128">**Consenti con URL** Consente al client di accedere se la versione client non corrisponde a un filtro nell'elenco dei criteri di versione client e include un messaggio di errore contenente un URL in cui è possibile scaricare un nuovo client.</span><span class="sxs-lookup"><span data-stu-id="19836-128">**Allow with URL** Allows the client to log on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="19836-129">**URL** Se è stato selezionato **blocca con URL** o **Consenti con URL**, è possibile specificare l'URL di download del client da includere nel messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="19836-129">**URL** If you selected **Block with URL** or **Allow with URL**, you can specify the client download URL to include in the error message.</span></span>

<span data-ttu-id="19836-p105">Per informazioni dettagliate su interoperabilità tra client e versioni client, vedere [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso delle configurazioni delle versioni client, vedere [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="19836-p105">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

