---
title: Configurazione della versione client creare nuovi o modificarne uno esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
description: Le impostazioni di configurazione della versione client vengono utilizzate per abilitare o disabilitare il controllo della versione client. La configurazione globale della versione client viene installata con Skype for Business Server e viene utilizzata per abilitare o disabilitare il controllo della versione client per l'intera distribuzione del server. Quando la configurazione globale è abilitata, tutti i criteri di versione client sul posto avranno effetto quando gli utenti tentano di eseguire l'accesso. È possibile disabilitare la configurazione della versione client globale se non si desidera che venga eseguito alcun controllo della versione client.
ms.openlocfilehash: 5567a4de26d29413c049126b90c907383916d71c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800506"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a><span data-ttu-id="56825-106">Configurazione delle versioni client: crearne una nuova o modificarne una esistente</span><span class="sxs-lookup"><span data-stu-id="56825-106">Client Version Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="56825-107">Le impostazioni di configurazione della versione client vengono utilizzate per abilitare o disabilitare il controllo della versione client.</span><span class="sxs-lookup"><span data-stu-id="56825-107">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="56825-108">La configurazione globale della versione client viene installata con Skype for Business Server e viene utilizzata per abilitare o disabilitare il controllo della versione client per l'intera distribuzione del server.</span><span class="sxs-lookup"><span data-stu-id="56825-108">The Global client version configuration installs with Skype for Business Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="56825-109">Quando la configurazione globale è abilitata, tutti i criteri di versione client sul posto avranno effetto quando gli utenti tentano di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="56825-109">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="56825-110">È possibile disabilitare la configurazione della versione client globale se non si desidera che venga eseguito alcun controllo della versione client.</span><span class="sxs-lookup"><span data-stu-id="56825-110">You can disable the Global client version configuration if you do not want any client version control to occur.</span></span>

<span data-ttu-id="56825-111">È inoltre possibile creare configurazioni di versione client specifiche del sito, che consentono di abilitare o disabilitare il controllo della versione client per sito.</span><span class="sxs-lookup"><span data-stu-id="56825-111">You can also create site-specific client version configurations, allowing you to enable or disable client version control by site.</span></span> <span data-ttu-id="56825-112">Le configurazioni specifiche del sito hanno la precedenza sulla configurazione globale.</span><span class="sxs-lookup"><span data-stu-id="56825-112">Site-specific configurations take precedence over the Global configuration.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="56825-113">Attività eseguibili</span><span class="sxs-lookup"><span data-stu-id="56825-113">Tasks you can perform</span></span>

<span data-ttu-id="56825-114">Nella pagina **Nuova configurazione versione client** o **Modifica configurazione versione client** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="56825-114">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="56825-115">Aggiungere o modificare il nome della configurazione della versione client.</span><span class="sxs-lookup"><span data-stu-id="56825-115">Add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="56825-116">Abilitare o disabilitare il controllo della versione client a livello globale o per il sito specifico.</span><span class="sxs-lookup"><span data-stu-id="56825-116">Enable or disable client version control globally or for the specific site.</span></span>

- <span data-ttu-id="56825-117">Aggiungere o modificare l'azione predefinita per la configurazione della versione client.</span><span class="sxs-lookup"><span data-stu-id="56825-117">Add or modify the default action for the client version configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="56825-118">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="56825-118">UI Reference</span></span>

<span data-ttu-id="56825-119">Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="56825-119">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="56825-120">**Ambito** Identifica l'ambito (globale o sito) della configurazione della versione client.</span><span class="sxs-lookup"><span data-stu-id="56825-120">**Scope** Identifies the scope (Global or Site) of the client version configuration.</span></span>

- <span data-ttu-id="56825-121">**Nome** È possibile aggiungere o modificare il nome della configurazione della versione client.</span><span class="sxs-lookup"><span data-stu-id="56825-121">**Name** You can add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="56825-122">**Abilitare il controllo delle versioni** È possibile abilitare o disabilitare il controllo della versione client a livello globale o per il sito, a seconda dell'ambito della configurazione.</span><span class="sxs-lookup"><span data-stu-id="56825-122">**Enable version control** You can enable or disable client version control globally or for the site, depending on the scope of the configuration.</span></span>

- <span data-ttu-id="56825-123">**Azione predefinita** È possibile selezionare l'azione predefinita che verrà applicata quando un utente tenta di eseguire l'accesso utilizzando un'applicazione client per la quale non sono previsti criteri di versione client specifici.</span><span class="sxs-lookup"><span data-stu-id="56825-123">**Default action** You can select the default action that will be applied when a user attempts to log on using a client application for which there is no specific client version policy.</span></span> <span data-ttu-id="56825-124">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="56825-124">You have the following options:</span></span>

  - <span data-ttu-id="56825-125">**Consenti** Consente al client di eseguire l'accesso se la versione del client non corrisponde ad alcun filtro nell'elenco dei criteri versione client.</span><span class="sxs-lookup"><span data-stu-id="56825-125">**Allow** Allows the client to log on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="56825-126">**Blocca** Impedisce l'accesso del client se la versione client non corrisponde ad alcun filtro nell'elenco dei criteri versione client.</span><span class="sxs-lookup"><span data-stu-id="56825-126">**Block** Prevents the client from logging on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="56825-127">**Blocca con URL** Impedisce al client di eseguire l'accesso se la versione client non corrisponde ad alcun filtro nell'elenco dei criteri versione client e include un messaggio di errore contenente un URL in cui è possibile scaricare un client più recente.</span><span class="sxs-lookup"><span data-stu-id="56825-127">**Block with URL** Prevents the client from logging on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="56825-128">**Consenti con URL** Consente al client di eseguire l'accesso se la versione client non corrisponde ad alcun filtro nell'elenco dei criteri versione client e include un messaggio di errore contenente un URL in cui è possibile scaricare un client più recente.</span><span class="sxs-lookup"><span data-stu-id="56825-128">**Allow with URL** Allows the client to log on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="56825-129">**URL** Se è stata selezionata l'opzione **blocca con URL** o **Consenti con URL**, è possibile specificare l'URL di download del client da includere nel messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="56825-129">**URL** If you selected **Block with URL** or **Allow with URL**, you can specify the client download URL to include in the error message.</span></span>

<span data-ttu-id="56825-130">Per informazioni dettagliate su interoperabilità tra client e versioni client, vedere [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="56825-130">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="56825-131">Per informazioni dettagliate sull'uso delle configurazioni delle versioni client, vedere [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="56825-131">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

