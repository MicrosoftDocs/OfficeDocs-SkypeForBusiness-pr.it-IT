---
title: Tabella User
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La tabella utente è una tabella di supporto in cui è archiviato un elenco dei vari utenti che hanno partecipato a sessioni registrate nel database. Ogni record nella tabella rappresenta un solo utente.
ms.openlocfilehash: a9f72793d3b287406b1b3b7e1ad360e7f5abc598
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194571"
---
# <a name="user-table"></a><span data-ttu-id="29de8-104">Tabella User</span><span class="sxs-lookup"><span data-stu-id="29de8-104">User table</span></span>
 
<span data-ttu-id="29de8-105">La tabella utente è una tabella di supporto in cui è archiviato un elenco dei vari utenti che hanno partecipato a sessioni registrate nel database.</span><span class="sxs-lookup"><span data-stu-id="29de8-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="29de8-106">Ogni record nella tabella rappresenta un solo utente.</span><span class="sxs-lookup"><span data-stu-id="29de8-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="29de8-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="29de8-107">**Column**</span></span>|<span data-ttu-id="29de8-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="29de8-108">**Data Type**</span></span>|<span data-ttu-id="29de8-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="29de8-109">**Key/Index**</span></span>|<span data-ttu-id="29de8-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="29de8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="29de8-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="29de8-111">**UserKey**</span></span> <br/> |<span data-ttu-id="29de8-112">int</span><span class="sxs-lookup"><span data-stu-id="29de8-112">int</span></span>  <br/> |<span data-ttu-id="29de8-113">Principale</span><span class="sxs-lookup"><span data-stu-id="29de8-113">Primary</span></span>  <br/> |<span data-ttu-id="29de8-114">Numero univoco che identifica questo utente.</span><span class="sxs-lookup"><span data-stu-id="29de8-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="29de8-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="29de8-115">**URI**</span></span> <br/> |<span data-ttu-id="29de8-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="29de8-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="29de8-117">Univoci</span><span class="sxs-lookup"><span data-stu-id="29de8-117">Unique</span></span>  <br/> |<span data-ttu-id="29de8-118">Stringa URI.</span><span class="sxs-lookup"><span data-stu-id="29de8-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="29de8-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="29de8-119">**URIType**</span></span> <br/> |<span data-ttu-id="29de8-120">int</span><span class="sxs-lookup"><span data-stu-id="29de8-120">int</span></span>  <br/> ||<span data-ttu-id="29de8-121">1 è un tipo URI sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="29de8-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="29de8-122">2 è l'URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="29de8-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="29de8-123">4 è l'URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="29de8-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="29de8-124">8 è l'URI del telefono.</span><span class="sxs-lookup"><span data-stu-id="29de8-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="29de8-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="29de8-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="29de8-126">int</span><span class="sxs-lookup"><span data-stu-id="29de8-126">int</span></span>  <br/> |<span data-ttu-id="29de8-127">Esterna</span><span class="sxs-lookup"><span data-stu-id="29de8-127">Foreign</span></span>  <br/> |<span data-ttu-id="29de8-128">Tenant dell'utente, a cui si fa riferimento dalla tabella tenant.</span><span class="sxs-lookup"><span data-stu-id="29de8-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="29de8-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="29de8-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="29de8-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="29de8-130">datetime</span></span>  <br/> ||<span data-ttu-id="29de8-131">Indicatore di data e ora più recente quando l'utente ha ricevuto una chiamata audio scadente.</span><span class="sxs-lookup"><span data-stu-id="29de8-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="29de8-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="29de8-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="29de8-133">DateTime</span><span class="sxs-lookup"><span data-stu-id="29de8-133">datetime</span></span>  <br/> ||<span data-ttu-id="29de8-134">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="29de8-134">For internal use only.</span></span>  <br/> |
   

