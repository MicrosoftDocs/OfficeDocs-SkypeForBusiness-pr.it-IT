---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout contiene tutti i server che hanno elaborato un evento di conformità.
ms.openlocfilehash: cdf455563ccfc971963144b9d4e848d5678cac80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814654"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="0cf64-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="0cf64-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="0cf64-104">tblComplianceFanout contiene tutti i server che hanno elaborato un evento di conformità.</span><span class="sxs-lookup"><span data-stu-id="0cf64-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="0cf64-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0cf64-105">**Columns**</span></span>

|<span data-ttu-id="0cf64-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="0cf64-106">**Column**</span></span>|<span data-ttu-id="0cf64-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0cf64-107">**Type**</span></span>|<span data-ttu-id="0cf64-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0cf64-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0cf64-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="0cf64-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="0cf64-110">int</span><span class="sxs-lookup"><span data-stu-id="0cf64-110">int</span></span>  <br/> |<span data-ttu-id="0cf64-111">ID evento.</span><span class="sxs-lookup"><span data-stu-id="0cf64-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="0cf64-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="0cf64-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="0cf64-113">int</span><span class="sxs-lookup"><span data-stu-id="0cf64-113">int</span></span>  <br/> |<span data-ttu-id="0cf64-114">Identità del server (corrispondente alla tabella tblServerIdentity. serverID).</span><span class="sxs-lookup"><span data-stu-id="0cf64-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="0cf64-115">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="0cf64-115">**Key**</span></span>

|<span data-ttu-id="0cf64-116">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="0cf64-116">**Column**</span></span>|<span data-ttu-id="0cf64-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0cf64-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0cf64-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="0cf64-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="0cf64-119">Chiave esterna con ricerca nella tabella tblComplianceData. cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="0cf64-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

