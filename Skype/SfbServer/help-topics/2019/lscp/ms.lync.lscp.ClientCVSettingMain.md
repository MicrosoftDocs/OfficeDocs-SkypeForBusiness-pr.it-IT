---
title: Configurazione versione client
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
ROBOTS: NOINDEX, NOFOLLOW
description: Oltre a specificare la versione dei client che si desidera supportare nell'ambiente, è possibile specificare un'azione predefinita per i client per i quali non sono già stati definiti criteri delle versioni. In questo modo, è possibile limitare le versioni client usate nell'ambiente e ciò può contribuire a tenere sotto controllo i costi associati al supporto di più versioni client.
ms.openlocfilehash: d2d2a18928a31d136b52a90852836db93c01ffc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812316"
---
# <a name="client-version-configuration"></a><span data-ttu-id="439e1-104">Configurazione versione client</span><span class="sxs-lookup"><span data-stu-id="439e1-104">Client Version Configuration</span></span>

<span data-ttu-id="439e1-p102">Oltre a specificare la versione dei client che si desidera supportare nell'ambiente, è possibile specificare un'azione predefinita per i client per i quali non sono già stati definiti criteri delle versioni. In questo modo, è possibile limitare le versioni client usate nell'ambiente e ciò può contribuire a tenere sotto controllo i costi associati al supporto di più versioni client.</span><span class="sxs-lookup"><span data-stu-id="439e1-p102">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined. This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="439e1-107">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="439e1-107">Tasks you can perform</span></span>

<span data-ttu-id="439e1-108">Nella pagina **Configurazione versione client** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="439e1-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="439e1-109">Modificare la configurazione predefinita **(globale)** della versione client.</span><span class="sxs-lookup"><span data-stu-id="439e1-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="439e1-110">Creare una configurazione della versione client per un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="439e1-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="439e1-111">Abilitare e disabilitare le configurazioni delle versioni client esistenti.</span><span class="sxs-lookup"><span data-stu-id="439e1-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="439e1-112">Poiché gli utenti anonimi non sono associati a un sito, vengono loro applicati solo i criteri di livello globale.</span><span class="sxs-lookup"><span data-stu-id="439e1-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="439e1-113">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="439e1-113">UI Reference</span></span>

<span data-ttu-id="439e1-114">Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="439e1-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="439e1-115">**Nuovo** È possibile creare una configurazione della versione client per un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="439e1-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="439e1-116">**Modifica** È possibile modificare le opzioni di uno qualsiasi dei criteri versione client.</span><span class="sxs-lookup"><span data-stu-id="439e1-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="439e1-117">Usando questa voce, è possibile scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="439e1-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="439e1-118">**Mostra dettagli** Questa opzione consente di aprire una finestra di dialogo in cui è possibile modificare le opzioni per una configurazione della versione client.</span><span class="sxs-lookup"><span data-stu-id="439e1-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="439e1-119">**Seleziona tutto** Questa opzione consente di selezionare tutte le configurazioni delle versioni client nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="439e1-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="439e1-120">**Elimina** Questa opzione consente di eliminare tutte le configurazioni delle versioni client selezionate.</span><span class="sxs-lookup"><span data-stu-id="439e1-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="439e1-121">**Aggiorna** È possibile aggiornare l'elenco delle configurazioni delle versioni client per verificare lo stato delle opzioni di tutte le configurazioni delle versioni client.</span><span class="sxs-lookup"><span data-stu-id="439e1-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="439e1-122">Per informazioni dettagliate sull'interoperabilità tra client e versioni client, vedere [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="439e1-122">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="439e1-123">Per informazioni dettagliate sull'uso delle configurazioni delle versioni client, vedere [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="439e1-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

