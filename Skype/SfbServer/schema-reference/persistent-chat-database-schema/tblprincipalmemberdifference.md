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
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contiene le modifiche dell'appartenenza ai gruppi (membri aggiunti e rimossi) che non sono ancora state elaborate dai passaggi successivi di sincronizzazione dei servizi di dominio Active Directory.
ms.openlocfilehash: 18d0f3f5c8700db0bb81470f5ee90851e8d277ad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194668"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="ccb14-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="ccb14-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="ccb14-104">tblPrincipalMemberDifference contiene le modifiche dell'appartenenza ai gruppi (membri aggiunti e rimossi) che non sono ancora state elaborate dai passaggi successivi di sincronizzazione dei servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ccb14-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="ccb14-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="ccb14-105">**Columns**</span></span>

|<span data-ttu-id="ccb14-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="ccb14-106">**Column**</span></span>|<span data-ttu-id="ccb14-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ccb14-107">**Type**</span></span>|<span data-ttu-id="ccb14-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ccb14-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ccb14-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="ccb14-109">prinGuid</span></span>  <br/> |<span data-ttu-id="ccb14-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="ccb14-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="ccb14-111">GUID principale del gruppo modificato.</span><span class="sxs-lookup"><span data-stu-id="ccb14-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="ccb14-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="ccb14-112">memberADPath</span></span>  <br/> |<span data-ttu-id="ccb14-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ccb14-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="ccb14-114">Nome distinto del membro.</span><span class="sxs-lookup"><span data-stu-id="ccb14-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="ccb14-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="ccb14-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="ccb14-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="ccb14-116">bit, not null</span></span>  <br/> |<span data-ttu-id="ccb14-117">False se il membro è stato aggiunto.</span><span class="sxs-lookup"><span data-stu-id="ccb14-117">False if the member was added.</span></span> <span data-ttu-id="ccb14-118">True se il membro è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="ccb14-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="ccb14-119">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="ccb14-119">**Key**</span></span>

|<span data-ttu-id="ccb14-120">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="ccb14-120">**Column**</span></span>|<span data-ttu-id="ccb14-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ccb14-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ccb14-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="ccb14-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="ccb14-123">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="ccb14-123">Primary key.</span></span>  <br/> |
   

