---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contiene le modifiche apportate all'appartenenza ai gruppi (membri aggiunti e rimossi) che non sono state ancora elaborate dai successivi passaggi di sincronizzazione dei servizi di dominio Active Directory.
ms.openlocfilehash: 8fac76f1abfbd55d13d89c96bb23a6953d38edf9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809706"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="8f17a-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="8f17a-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="8f17a-104">tblPrincipalMemberDifference contiene le modifiche apportate all'appartenenza ai gruppi (membri aggiunti e rimossi) che non sono state ancora elaborate dai successivi passaggi di sincronizzazione dei servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8f17a-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="8f17a-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="8f17a-105">**Columns**</span></span>

|<span data-ttu-id="8f17a-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="8f17a-106">**Column**</span></span>|<span data-ttu-id="8f17a-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8f17a-107">**Type**</span></span>|<span data-ttu-id="8f17a-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="8f17a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8f17a-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="8f17a-109">prinGuid</span></span>  <br/> |<span data-ttu-id="8f17a-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="8f17a-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="8f17a-111">GUID entità del gruppo modificato.</span><span class="sxs-lookup"><span data-stu-id="8f17a-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="8f17a-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="8f17a-112">memberADPath</span></span>  <br/> |<span data-ttu-id="8f17a-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8f17a-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="8f17a-114">Nome distinto del membro.</span><span class="sxs-lookup"><span data-stu-id="8f17a-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="8f17a-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="8f17a-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="8f17a-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="8f17a-116">bit, not null</span></span>  <br/> |<span data-ttu-id="8f17a-p101">False se il membro è stato aggiunto. True se il membro è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="8f17a-p101">False if the member was added. True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="8f17a-119">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="8f17a-119">**Key**</span></span>

|<span data-ttu-id="8f17a-120">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="8f17a-120">**Column**</span></span>|<span data-ttu-id="8f17a-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="8f17a-121">**Description**</span></span>|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |<span data-ttu-id="8f17a-122">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="8f17a-122">Primary key.</span></span>  <br/> |
   

