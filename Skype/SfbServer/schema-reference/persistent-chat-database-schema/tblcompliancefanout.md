---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout include i server che hanno elaborato un evento di conformità.
ms.openlocfilehash: 75e232cd464a2199b490e555c0fab79ded119c94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809796"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="136bf-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="136bf-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="136bf-104">tblComplianceFanout include i server che hanno elaborato un evento di conformità.</span><span class="sxs-lookup"><span data-stu-id="136bf-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="136bf-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="136bf-105">**Columns**</span></span>

|<span data-ttu-id="136bf-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="136bf-106">**Column**</span></span>|<span data-ttu-id="136bf-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="136bf-107">**Type**</span></span>|<span data-ttu-id="136bf-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="136bf-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="136bf-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="136bf-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="136bf-110">int</span><span class="sxs-lookup"><span data-stu-id="136bf-110">int</span></span>  <br/> |<span data-ttu-id="136bf-111">ID evento.</span><span class="sxs-lookup"><span data-stu-id="136bf-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="136bf-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="136bf-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="136bf-113">int</span><span class="sxs-lookup"><span data-stu-id="136bf-113">int</span></span>  <br/> |<span data-ttu-id="136bf-114">Identità del server (corrispondente alla tabella tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="136bf-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="136bf-115">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="136bf-115">**Key**</span></span>

|<span data-ttu-id="136bf-116">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="136bf-116">**Column**</span></span>|<span data-ttu-id="136bf-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="136bf-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="136bf-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="136bf-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="136bf-119">Chiave esterna con ricerca nella tabella tblComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="136bf-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

