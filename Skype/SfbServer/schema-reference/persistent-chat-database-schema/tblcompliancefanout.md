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
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout contiene tutti i server che hanno elaborato un evento di conformità.
ms.openlocfilehash: 1d2dfc99619e0669a08db33dbacc75930053f0dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194694"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="ac198-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="ac198-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="ac198-104">tblComplianceFanout contiene tutti i server che hanno elaborato un evento di conformità.</span><span class="sxs-lookup"><span data-stu-id="ac198-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="ac198-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="ac198-105">**Columns**</span></span>

|<span data-ttu-id="ac198-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="ac198-106">**Column**</span></span>|<span data-ttu-id="ac198-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ac198-107">**Type**</span></span>|<span data-ttu-id="ac198-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ac198-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ac198-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="ac198-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="ac198-110">int</span><span class="sxs-lookup"><span data-stu-id="ac198-110">int</span></span>  <br/> |<span data-ttu-id="ac198-111">ID evento.</span><span class="sxs-lookup"><span data-stu-id="ac198-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="ac198-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="ac198-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="ac198-113">int</span><span class="sxs-lookup"><span data-stu-id="ac198-113">int</span></span>  <br/> |<span data-ttu-id="ac198-114">Identità del server (corrispondente alla tabella tblServerIdentity. serverID).</span><span class="sxs-lookup"><span data-stu-id="ac198-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="ac198-115">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="ac198-115">**Key**</span></span>

|<span data-ttu-id="ac198-116">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="ac198-116">**Column**</span></span>|<span data-ttu-id="ac198-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ac198-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ac198-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="ac198-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="ac198-119">Chiave esterna con ricerca nella tabella tblComplianceData. cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="ac198-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

