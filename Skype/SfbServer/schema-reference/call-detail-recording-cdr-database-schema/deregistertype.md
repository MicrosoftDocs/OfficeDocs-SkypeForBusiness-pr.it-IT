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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La tabella DeRegisterType è una tabella statica in cui è archiviato l'elenco dei possibili tipi di deregistri degli utenti, ad esempio "client avviato", "Registrazione scaduta" o "client smesso di rispondere".
ms.openlocfilehash: ae9afafe91336b1e5c74fd0a854e2975a3b4ba8e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815294"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="1715b-103">Tabella DeRegisterType in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1715b-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1715b-104">La tabella DeRegisterType è una tabella statica in cui è archiviato l'elenco dei possibili tipi di deregistri degli utenti, ad esempio "client avviato", "Registrazione scaduta" o "client smesso di rispondere".</span><span class="sxs-lookup"><span data-stu-id="1715b-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="1715b-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="1715b-105">**Column**</span></span>|<span data-ttu-id="1715b-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="1715b-106">**Data Type**</span></span>|<span data-ttu-id="1715b-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="1715b-107">**Key/Index**</span></span>|<span data-ttu-id="1715b-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="1715b-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1715b-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="1715b-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="1715b-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="1715b-110">tinyint</span></span>  <br/> |<span data-ttu-id="1715b-111">Principale</span><span class="sxs-lookup"><span data-stu-id="1715b-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="1715b-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="1715b-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="1715b-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1715b-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="1715b-114">Valori consentiti:</span><span class="sxs-lookup"><span data-stu-id="1715b-114">Allowed values:</span></span> <br/>  <span data-ttu-id="1715b-115">0--sconosciuto</span><span class="sxs-lookup"><span data-stu-id="1715b-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="1715b-116">1--annullamento della registrazione avviata dal client</span><span class="sxs-lookup"><span data-stu-id="1715b-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="1715b-117">2--Registrazione scaduta</span><span class="sxs-lookup"><span data-stu-id="1715b-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="1715b-118">3-client arrestato</span><span class="sxs-lookup"><span data-stu-id="1715b-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="1715b-119">4--attributi utente modificati</span><span class="sxs-lookup"><span data-stu-id="1715b-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="1715b-120">5-modifica del registrar preferito</span><span class="sxs-lookup"><span data-stu-id="1715b-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="1715b-121">6--client legacy in modalità Survival</span><span class="sxs-lookup"><span data-stu-id="1715b-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

