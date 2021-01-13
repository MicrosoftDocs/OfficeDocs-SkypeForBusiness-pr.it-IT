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
description: Quando una chiamata viene parcheggiata, viene trasferita a un numero temporaneo in cui la chiamata viene mantenuta finché un utente non lo recupera o non si verifica il timeout. È necessario configurare una tabella con gli intervalli di numeri di interno che si desidera riservare per le chiamate parcheggiate. Questi interni devono essere virtuali (ossia interni a cui non è assegnato alcun utente o telefono). Ogni pool che esegue l'applicazione Parcheggio di chiamata può disporre di uno o più intervalli di estensioni. Tali intervalli devono essere univoci nell'intera distribuzione.
ms.openlocfilehash: 679e13cdeb6ef6cf614f5703f5711e86fa1c8c59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812166"
---
# <a name="call-park"></a><span data-ttu-id="e3883-106">Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="e3883-106">Call Park</span></span>

<span data-ttu-id="e3883-107">Quando una chiamata viene parcheggiata, viene trasferita a un numero temporaneo in cui la chiamata viene mantenuta finché un utente non lo recupera o non si verifica il timeout. È necessario configurare una tabella con gli intervalli di numeri di interno che si desidera riservare per le chiamate parcheggiate.</span><span class="sxs-lookup"><span data-stu-id="e3883-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="e3883-108">Questi interni devono essere virtuali (ossia interni a cui non è assegnato alcun utente o telefono).</span><span class="sxs-lookup"><span data-stu-id="e3883-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="e3883-109">Ogni pool che esegue l'applicazione Parcheggio di chiamata può disporre di uno o più intervalli di estensioni.</span><span class="sxs-lookup"><span data-stu-id="e3883-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="e3883-110">Tali intervalli devono essere univoci nell'intera distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e3883-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="e3883-111">Nella pagina **parcheggio di chiamata** viene visualizzato un elenco di tutti gli intervalli di numeri del parcheggio di chiamata definiti per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e3883-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="e3883-112">Attività eseguibili</span><span class="sxs-lookup"><span data-stu-id="e3883-112">Tasks you can perform</span></span>

<span data-ttu-id="e3883-113">Nella pagina **Parcheggio di chiamata** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3883-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="e3883-114">Creare un nuovo intervallo di numeri</span><span class="sxs-lookup"><span data-stu-id="e3883-114">Create a new number range</span></span>

- <span data-ttu-id="e3883-115">Modificare un intervallo di numeri esistente</span><span class="sxs-lookup"><span data-stu-id="e3883-115">Change an existing number range</span></span>

- <span data-ttu-id="e3883-116">Eliminare un intervallo di numeri</span><span class="sxs-lookup"><span data-stu-id="e3883-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="e3883-117">Riferimento all'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="e3883-117">UI Reference</span></span>

<span data-ttu-id="e3883-118">Nell'elenco seguente sono descritti i comandi della pagina.</span><span class="sxs-lookup"><span data-stu-id="e3883-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="e3883-119">**Nuovo** Avvia un nuovo intervallo di numeri del parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e3883-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="e3883-120">**Modifica** Consente di aprire l'intervallo di numeri selezionato per la modifica, di selezionare tutti gli intervalli di numeri nell'elenco oppure di eliminare l'intervallo di numeri selezionato.</span><span class="sxs-lookup"><span data-stu-id="e3883-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="e3883-121">**Aggiorna** Aggiorna l'elenco di intervalli di numeri.</span><span class="sxs-lookup"><span data-stu-id="e3883-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="e3883-122">L'elenco seguente descrive i campi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="e3883-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="e3883-123">**Nome** Nome univoco che identifica l'intervallo di numeri.</span><span class="sxs-lookup"><span data-stu-id="e3883-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="e3883-124">**Intervallo di avvio** Il numero iniziale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="e3883-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="e3883-125">**Intervallo finale** Numero finale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="e3883-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="e3883-126">**Destinazione** Il nome di dominio completo (FQDN) o l'ID del servizio dell'applicazione che ospita l'applicazione Parcheggio di chiamata per l'intervallo di numeri.</span><span class="sxs-lookup"><span data-stu-id="e3883-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="e3883-127">Per informazioni dettagliate sulle funzionalità e sulle funzionalità del parcheggio di chiamata, vedere [pianificare il parcheggio di chiamata in Skype for business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="e3883-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="e3883-128">Per informazioni dettagliate sull'utilizzo di intervalli di numeri di parcheggio di chiamata, vedere [Configure Phone Number Extensions for parcheggio](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)calls.</span><span class="sxs-lookup"><span data-stu-id="e3883-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


