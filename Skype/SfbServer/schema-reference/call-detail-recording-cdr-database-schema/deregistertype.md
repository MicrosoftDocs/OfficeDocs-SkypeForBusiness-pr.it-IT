---
title: Tabella DeRegisterType in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La tabella DeRegisterType è una tabella statica in cui è archiviato l'elenco dei possibili tipi di annullamento della registrazione dell'utente, ad esempio "avviato dal client", "registrazione scaduta" o "client ha smesso di rispondere".
ms.openlocfilehash: 388aebc1ac180e1298addd54859cff6759b28be0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816076"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="70e46-103">Tabella DeRegisterType in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="70e46-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="70e46-104">La tabella DeRegisterType è una tabella statica in cui è archiviato l'elenco dei possibili tipi di annullamento della registrazione dell'utente, ad esempio "avviato dal client", "registrazione scaduta" o "client ha smesso di rispondere".</span><span class="sxs-lookup"><span data-stu-id="70e46-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="70e46-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="70e46-105">**Column**</span></span>|<span data-ttu-id="70e46-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="70e46-106">**Data Type**</span></span>|<span data-ttu-id="70e46-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="70e46-107">**Key/Index**</span></span>|<span data-ttu-id="70e46-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="70e46-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="70e46-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="70e46-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="70e46-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="70e46-110">tinyint</span></span>  <br/> |<span data-ttu-id="70e46-111">Principale</span><span class="sxs-lookup"><span data-stu-id="70e46-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="70e46-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="70e46-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="70e46-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="70e46-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="70e46-114">Valori consentiti:</span><span class="sxs-lookup"><span data-stu-id="70e46-114">Allowed values:</span></span> <br/>  <span data-ttu-id="70e46-115">0 - Sconosciuto</span><span class="sxs-lookup"><span data-stu-id="70e46-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="70e46-116">1 - Annullamento della registrazione avviato dal client</span><span class="sxs-lookup"><span data-stu-id="70e46-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="70e46-117">2 - Registrazione scaduta</span><span class="sxs-lookup"><span data-stu-id="70e46-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="70e46-118">3 - Arresto anomalo del client</span><span class="sxs-lookup"><span data-stu-id="70e46-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="70e46-119">4 - Attributi utente modificati</span><span class="sxs-lookup"><span data-stu-id="70e46-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="70e46-120">5 - Registrar preferito modificato</span><span class="sxs-lookup"><span data-stu-id="70e46-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="70e46-121">6 - Client legacy in modalità di sopravvivenza</span><span class="sxs-lookup"><span data-stu-id="70e46-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

