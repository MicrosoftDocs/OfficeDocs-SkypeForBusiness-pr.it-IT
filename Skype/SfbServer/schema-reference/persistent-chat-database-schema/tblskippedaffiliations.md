---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contiene le affiliazioni che non è stato possibile leggere (in genere a causa di errori di accesso ai servizi di dominio Active Directory).
ms.openlocfilehash: 481bf92a4014bf2af8e1c4794d1793f2c93e7c36
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194648"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="eba12-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="eba12-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="eba12-104">tblSkippedAffiliations contiene le affiliazioni che non è stato possibile leggere (in genere a causa di errori di accesso ai servizi di dominio Active Directory).</span><span class="sxs-lookup"><span data-stu-id="eba12-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="eba12-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="eba12-105">**Columns**</span></span>

|<span data-ttu-id="eba12-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="eba12-106">**Column**</span></span>|<span data-ttu-id="eba12-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="eba12-107">**Type**</span></span>|<span data-ttu-id="eba12-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="eba12-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="eba12-109">prinID</span><span class="sxs-lookup"><span data-stu-id="eba12-109">prinID</span></span>  <br/> |<span data-ttu-id="eba12-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="eba12-110">int, not null</span></span>  <br/> |<span data-ttu-id="eba12-111">ID entità.</span><span class="sxs-lookup"><span data-stu-id="eba12-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="eba12-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="eba12-112">affDescription</span></span>  <br/> |<span data-ttu-id="eba12-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="eba12-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="eba12-114">Stringa che identifica l'affiliazione.</span><span class="sxs-lookup"><span data-stu-id="eba12-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="eba12-115">Il formato è: GUID: _{0}_ uri: _{1}_> ID:_{2}_</span><span class="sxs-lookup"><span data-stu-id="eba12-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="eba12-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="eba12-116">updatedBy</span></span>  <br/> |<span data-ttu-id="eba12-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="eba12-117">int, not null</span></span>  <br/> |<span data-ttu-id="eba12-118">ID dell'entità che ha aggiornato la riga.</span><span class="sxs-lookup"><span data-stu-id="eba12-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="eba12-119">È sempre 1 (utente di sistema) perché Active Directory Sync è l'unica fonte per queste voci.</span><span class="sxs-lookup"><span data-stu-id="eba12-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="eba12-120">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="eba12-120">**Keys**</span></span>

|<span data-ttu-id="eba12-121">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="eba12-121">**Column(s)**</span></span>|<span data-ttu-id="eba12-122">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="eba12-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="eba12-123">\<prinID, affDescription\></span><span class="sxs-lookup"><span data-stu-id="eba12-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="eba12-124">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="eba12-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="eba12-125">prinID</span><span class="sxs-lookup"><span data-stu-id="eba12-125">prinID</span></span>  <br/> |<span data-ttu-id="eba12-126">Chiave esterna con ricerca nella tabella tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="eba12-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

