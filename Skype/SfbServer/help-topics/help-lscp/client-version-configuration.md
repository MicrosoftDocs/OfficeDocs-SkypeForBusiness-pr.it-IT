---
title: Configurazione della versione client
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
description: Oltre a specificare la versione dei client che si vuole supportare nell'ambiente, è anche possibile specificare un'azione predefinita per i client che non hanno già un criterio di versione definito. In questo modo puoi limitare le versioni client usate nell'ambiente, che possono aiutarti a controllare i costi associati al supporto di più versioni client.
ms.openlocfilehash: 3f223cbf90f76aab38cdb443d96dabd3d7797079
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195120"
---
# <a name="client-version-configuration"></a><span data-ttu-id="0d2a9-104">Configurazione della versione client</span><span class="sxs-lookup"><span data-stu-id="0d2a9-104">Client Version Configuration</span></span>

<span data-ttu-id="0d2a9-105">Oltre a specificare la versione dei client che si vuole supportare nell'ambiente, è anche possibile specificare un'azione predefinita per i client che non hanno già un criterio di versione definito.</span><span class="sxs-lookup"><span data-stu-id="0d2a9-105">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="0d2a9-106">In questo modo puoi limitare le versioni client usate nell'ambiente, che possono aiutarti a controllare i costi associati al supporto di più versioni client.</span><span class="sxs-lookup"><span data-stu-id="0d2a9-106">This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="0d2a9-107">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="0d2a9-107">Tasks you can perform</span></span>

<span data-ttu-id="0d2a9-108">Nella pagina **Configurazione versione client** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d2a9-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="0d2a9-109">Modificare la configurazione della versione client predefinita ( **globale**).</span><span class="sxs-lookup"><span data-stu-id="0d2a9-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="0d2a9-110">Creare la configurazione della versione client per un determinato sito.</span><span class="sxs-lookup"><span data-stu-id="0d2a9-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="0d2a9-111">Abilitare e disabilitare le configurazioni di versione client esistenti.</span><span class="sxs-lookup"><span data-stu-id="0d2a9-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="0d2a9-112">Poiché gli utenti anonimi non sono associati a un sito, gli utenti anonimi sono interessati solo dai criteri a livello globale.</span><span class="sxs-lookup"><span data-stu-id="0d2a9-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="0d2a9-113">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="0d2a9-113">UI Reference</span></span>

<span data-ttu-id="0d2a9-114">Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="0d2a9-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="0d2a9-115">**Nuovo** È possibile creare una configurazione della versione client per un determinato sito.</span><span class="sxs-lookup"><span data-stu-id="0d2a9-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="0d2a9-116">**Modifica** È possibile modificare le opzioni di qualsiasi criterio di versione client.</span><span class="sxs-lookup"><span data-stu-id="0d2a9-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="0d2a9-117">Usando questa voce, è possibile scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d2a9-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="0d2a9-118">**Mostra dettagli** Questa opzione apre una finestra di dialogo in cui è possibile modificare le opzioni per la configurazione di una versione client.</span><span class="sxs-lookup"><span data-stu-id="0d2a9-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="0d2a9-119">**Seleziona tutto** Questa opzione consente di selezionare tutte le configurazioni della versione client nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0d2a9-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="0d2a9-120">**Eliminare** Questa opzione consente di eliminare tutte le configurazioni della versione client selezionata.</span><span class="sxs-lookup"><span data-stu-id="0d2a9-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="0d2a9-121">**Aggiornare** È possibile aggiornare l'elenco di configurazione della versione client per verificare lo stato delle opzioni di tutte le configurazioni della versione client.</span><span class="sxs-lookup"><span data-stu-id="0d2a9-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="0d2a9-p104">Per informazioni dettagliate su interoperabilità tra client e versioni client, vedere [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso delle configurazioni delle versioni client, vedere [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="0d2a9-p104">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

