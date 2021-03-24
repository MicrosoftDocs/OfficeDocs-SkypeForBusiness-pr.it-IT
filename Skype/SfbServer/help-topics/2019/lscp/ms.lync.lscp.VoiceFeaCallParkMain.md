---
title: Parcheggio di chiamata
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: Quando una chiamata è parcheggiata, viene trasferita a un numero temporaneo in cui la chiamata viene mantenuta fino a quando qualcuno non la recupera o si verifica il timeout. È necessario configurare una tabella con gli intervalli di numeri di interno che si stanno riservando per le chiamate parcheggiate. Questi interni devono essere virtuali (ossia interni a cui non è assegnato alcun utente o telefono). Ogni pool che esegue l'applicazione Parcheggio di chiamata può avere uno o più intervalli di estensioni. Tali intervalli devono essere univoci nell'intera distribuzione.
ms.openlocfilehash: b7926c10424fd5902fdc43e6c0fccadb45e61f79
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097072"
---
# <a name="call-park"></a><span data-ttu-id="5bfb6-106">Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="5bfb6-106">Call Park</span></span>

<span data-ttu-id="5bfb6-107">Quando una chiamata è parcheggiata, viene trasferita a un numero temporaneo in cui la chiamata viene mantenuta fino a quando qualcuno non la recupera o si verifica il timeout. È necessario configurare una tabella con gli intervalli di numeri di interno che si stanno riservando per le chiamate parcheggiate.</span><span class="sxs-lookup"><span data-stu-id="5bfb6-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="5bfb6-108">Questi interni devono essere virtuali (ossia interni a cui non è assegnato alcun utente o telefono).</span><span class="sxs-lookup"><span data-stu-id="5bfb6-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="5bfb6-109">Ogni pool che esegue l'applicazione Parcheggio di chiamata può avere uno o più intervalli di estensioni.</span><span class="sxs-lookup"><span data-stu-id="5bfb6-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="5bfb6-110">Tali intervalli devono essere univoci nell'intera distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5bfb6-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="5bfb6-111">Nella **pagina Parcheggio di** chiamata viene visualizzato un elenco di tutti gli intervalli di numeri del parcheggio di chiamata definiti per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5bfb6-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="5bfb6-112">Attività eseguibili</span><span class="sxs-lookup"><span data-stu-id="5bfb6-112">Tasks you can perform</span></span>

<span data-ttu-id="5bfb6-113">Nella pagina **Parcheggio di chiamata** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="5bfb6-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="5bfb6-114">Creare un nuovo intervallo di numeri</span><span class="sxs-lookup"><span data-stu-id="5bfb6-114">Create a new number range</span></span>

- <span data-ttu-id="5bfb6-115">Modificare un intervallo di numeri esistente</span><span class="sxs-lookup"><span data-stu-id="5bfb6-115">Change an existing number range</span></span>

- <span data-ttu-id="5bfb6-116">Eliminare un intervallo di numeri</span><span class="sxs-lookup"><span data-stu-id="5bfb6-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="5bfb6-117">Riferimento all'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="5bfb6-117">UI Reference</span></span>

<span data-ttu-id="5bfb6-118">Nell'elenco seguente sono descritti i comandi della pagina.</span><span class="sxs-lookup"><span data-stu-id="5bfb6-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="5bfb6-119">**Nuovo** Avvia un nuovo intervallo di numeri del parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="5bfb6-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="5bfb6-120">**Modifica** Apre l'intervallo di numeri selezionato per la modifica, seleziona tutti gli intervalli di numeri nell'elenco o elimina l'intervallo di numeri selezionato.</span><span class="sxs-lookup"><span data-stu-id="5bfb6-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="5bfb6-121">**Aggiorna** Aggiorna l'elenco degli intervalli di numeri.</span><span class="sxs-lookup"><span data-stu-id="5bfb6-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="5bfb6-122">L'elenco seguente descrive i campi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="5bfb6-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="5bfb6-123">**Nome** Nome univoco che identifica l'intervallo di numeri.</span><span class="sxs-lookup"><span data-stu-id="5bfb6-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="5bfb6-124">**Intervallo iniziale** Numero iniziale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="5bfb6-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="5bfb6-125">**Intervallo finale** Numero finale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="5bfb6-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="5bfb6-126">**Destinazione** Nome di dominio completo (FQDN) o ID servizio del servizio applicazione che ospita l'applicazione Parcheggio di chiamata per l'intervallo di numeri.</span><span class="sxs-lookup"><span data-stu-id="5bfb6-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="5bfb6-127">Per informazioni dettagliate sulle funzionalità e sulle funzionalità del parcheggio di chiamata, vedere [Plan for Call Park in Skype for Business.](../../../plan-your-deployment/enterprise-voice-solution/call-park.md)</span><span class="sxs-lookup"><span data-stu-id="5bfb6-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="5bfb6-128">Per informazioni dettagliate sull'utilizzo degli intervalli di numeri del parcheggio di chiamata, vedere [Configure Phone Number Extensions for Parking Calls.](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls)</span><span class="sxs-lookup"><span data-stu-id="5bfb6-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls).</span></span>