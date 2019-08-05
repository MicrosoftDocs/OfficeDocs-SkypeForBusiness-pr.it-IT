---
title: Tabella DeRegisterType in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La tabella DeRegisterType è una tabella statica in cui è archiviato l'elenco dei possibili tipi di deregistri degli utenti, ad esempio "client avviato", "Registrazione scaduta" o "client smesso di rispondere".
ms.openlocfilehash: 794f8f98ffe20cd69b63fd2084fee38ed055d40f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194821"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="09517-103">Tabella DeRegisterType in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="09517-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="09517-104">La tabella DeRegisterType è una tabella statica in cui è archiviato l'elenco dei possibili tipi di deregistri degli utenti, ad esempio "client avviato", "Registrazione scaduta" o "client smesso di rispondere".</span><span class="sxs-lookup"><span data-stu-id="09517-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="09517-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="09517-105">**Column**</span></span>|<span data-ttu-id="09517-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="09517-106">**Data Type**</span></span>|<span data-ttu-id="09517-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="09517-107">**Key/Index**</span></span>|<span data-ttu-id="09517-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="09517-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="09517-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="09517-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="09517-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="09517-110">tinyint</span></span>  <br/> |<span data-ttu-id="09517-111">Principale</span><span class="sxs-lookup"><span data-stu-id="09517-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="09517-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="09517-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="09517-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="09517-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="09517-114">Valori consentiti:</span><span class="sxs-lookup"><span data-stu-id="09517-114">Allowed values:</span></span> <br/>  <span data-ttu-id="09517-115">0--sconosciuto</span><span class="sxs-lookup"><span data-stu-id="09517-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="09517-116">1--annullamento della registrazione avviata dal client</span><span class="sxs-lookup"><span data-stu-id="09517-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="09517-117">2--Registrazione scaduta</span><span class="sxs-lookup"><span data-stu-id="09517-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="09517-118">3-client arrestato</span><span class="sxs-lookup"><span data-stu-id="09517-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="09517-119">4--attributi utente modificati</span><span class="sxs-lookup"><span data-stu-id="09517-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="09517-120">5-modifica del registrar preferito</span><span class="sxs-lookup"><span data-stu-id="09517-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="09517-121">6--client legacy in modalità Survival</span><span class="sxs-lookup"><span data-stu-id="09517-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

