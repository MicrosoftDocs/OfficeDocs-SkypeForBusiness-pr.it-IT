---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contiene le modifiche dell'appartenenza ai gruppi (membri aggiunti e rimossi) che non sono ancora state elaborate dai passaggi successivi di sincronizzazione dei servizi di dominio Active Directory.
ms.openlocfilehash: c7e965658c9e351a7a2d079921b7abe8166b48ad
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814074"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="abf27-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="abf27-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="abf27-104">tblPrincipalMemberDifference contiene le modifiche dell'appartenenza ai gruppi (membri aggiunti e rimossi) che non sono ancora state elaborate dai passaggi successivi di sincronizzazione dei servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="abf27-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="abf27-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="abf27-105">**Columns**</span></span>

|<span data-ttu-id="abf27-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="abf27-106">**Column**</span></span>|<span data-ttu-id="abf27-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="abf27-107">**Type**</span></span>|<span data-ttu-id="abf27-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="abf27-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="abf27-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="abf27-109">prinGuid</span></span>  <br/> |<span data-ttu-id="abf27-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="abf27-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="abf27-111">GUID principale del gruppo modificato.</span><span class="sxs-lookup"><span data-stu-id="abf27-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="abf27-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="abf27-112">memberADPath</span></span>  <br/> |<span data-ttu-id="abf27-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="abf27-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="abf27-114">Nome distinto del membro.</span><span class="sxs-lookup"><span data-stu-id="abf27-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="abf27-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="abf27-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="abf27-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="abf27-116">bit, not null</span></span>  <br/> |<span data-ttu-id="abf27-117">False se il membro è stato aggiunto.</span><span class="sxs-lookup"><span data-stu-id="abf27-117">False if the member was added.</span></span> <span data-ttu-id="abf27-118">True se il membro è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="abf27-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="abf27-119">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="abf27-119">**Key**</span></span>

|<span data-ttu-id="abf27-120">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="abf27-120">**Column**</span></span>|<span data-ttu-id="abf27-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="abf27-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="abf27-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="abf27-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="abf27-123">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="abf27-123">Primary key.</span></span>  <br/> |
   

