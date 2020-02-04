---
title: Parcheggio di chiamata
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: Quando una chiamata viene parcheggiata, viene trasferita a un numero temporaneo in cui la chiamata viene mantenuta fino a quando non viene recuperata o eliminata. È necessario configurare una tabella con gli intervalli di numeri di interno che si stanno riservando per le chiamate parcheggiate. Questi interni devono essere virtuali (ossia interni a cui non è assegnato alcun utente o telefono). Ogni pool che esegue l'applicazione Call Park può avere uno o più intervalli di estensioni. Tali intervalli devono essere univoci nell'intera distribuzione.
ms.openlocfilehash: 1a7417ab525f8471b730dc177a993c3458750a3f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700301"
---
# <a name="call-park"></a><span data-ttu-id="e1351-106">Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="e1351-106">Call Park</span></span>

<span data-ttu-id="e1351-107">Quando una chiamata viene parcheggiata, viene trasferita a un numero temporaneo in cui la chiamata viene mantenuta fino a quando non viene recuperata o eliminata. È necessario configurare una tabella con gli intervalli di numeri di interno che si stanno riservando per le chiamate parcheggiate.</span><span class="sxs-lookup"><span data-stu-id="e1351-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="e1351-108">Questi interni devono essere virtuali (ossia interni a cui non è assegnato alcun utente o telefono).</span><span class="sxs-lookup"><span data-stu-id="e1351-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="e1351-109">Ogni pool che esegue l'applicazione Call Park può avere uno o più intervalli di estensioni.</span><span class="sxs-lookup"><span data-stu-id="e1351-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="e1351-110">Tali intervalli devono essere univoci nell'intera distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e1351-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="e1351-111">Nella pagina del **parco chiamate** viene visualizzato un elenco di tutti gli intervalli di numeri di parcheggio di chiamata definiti per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e1351-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="e1351-112">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="e1351-112">Tasks you can perform</span></span>

<span data-ttu-id="e1351-113">Nella pagina **Parcheggio di chiamata** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1351-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="e1351-114">Creare un nuovo intervallo di numeri</span><span class="sxs-lookup"><span data-stu-id="e1351-114">Create a new number range</span></span>

- <span data-ttu-id="e1351-115">Modificare un intervallo di numeri esistente</span><span class="sxs-lookup"><span data-stu-id="e1351-115">Change an existing number range</span></span>

- <span data-ttu-id="e1351-116">Eliminare un intervallo di numeri</span><span class="sxs-lookup"><span data-stu-id="e1351-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="e1351-117">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="e1351-117">UI Reference</span></span>

<span data-ttu-id="e1351-118">L'elenco seguente descrive i comandi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="e1351-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="e1351-119">**Nuovo** Avvia un nuovo intervallo di numeri di parcheggio per le chiamate.</span><span class="sxs-lookup"><span data-stu-id="e1351-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="e1351-120">**Modifica** Apre l'intervallo di numeri selezionato per la modifica, seleziona tutti gli intervalli di numeri nell'elenco o Elimina l'intervallo di numeri selezionato.</span><span class="sxs-lookup"><span data-stu-id="e1351-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="e1351-121">**Aggiornare** Aggiorna l'elenco di intervalli di numeri.</span><span class="sxs-lookup"><span data-stu-id="e1351-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="e1351-122">L'elenco seguente descrive i campi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="e1351-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="e1351-123">**Nome** Nome univoco che identifica l'intervallo di numeri.</span><span class="sxs-lookup"><span data-stu-id="e1351-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="e1351-124">**Intervallo di inizio** Numero iniziale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="e1351-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="e1351-125">**Intervallo di fine** Numero finale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="e1351-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="e1351-126">**Destinazione** Nome di dominio completo (FQDN) o ID servizio del servizio applicazione che ospita l'applicazione Call Park per l'intervallo di numeri.</span><span class="sxs-lookup"><span data-stu-id="e1351-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="e1351-127">Per informazioni dettagliate sulle caratteristiche e le funzionalità di Call Park, vedere [pianificare il parcheggio delle chiamate in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="e1351-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="e1351-128">Per informazioni dettagliate sull'uso degli intervalli di numeri di Call Park, vedere [configurare le estensioni dei numeri di telefono per le chiamate di parcheggio](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span><span class="sxs-lookup"><span data-stu-id="e1351-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


