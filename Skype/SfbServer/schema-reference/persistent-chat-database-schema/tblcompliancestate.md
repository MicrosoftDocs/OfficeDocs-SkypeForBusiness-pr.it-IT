---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contiene informazioni sullo stato di conformità a livello di pool.
ms.openlocfilehash: 1c5571d7150c3859978f8d217f0264f67ee993d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194692"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="3bf49-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="3bf49-103">tblComplianceState</span></span>
 
<span data-ttu-id="3bf49-104">tblComplianceState contiene informazioni sullo stato di conformità a livello di pool.</span><span class="sxs-lookup"><span data-stu-id="3bf49-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="3bf49-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="3bf49-105">**Columns**</span></span>

|<span data-ttu-id="3bf49-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="3bf49-106">**Column**</span></span>|<span data-ttu-id="3bf49-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3bf49-107">**Type**</span></span>|<span data-ttu-id="3bf49-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3bf49-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3bf49-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="3bf49-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="3bf49-110">bigint e non null</span><span class="sxs-lookup"><span data-stu-id="3bf49-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="3bf49-111">ID dell'evento di conformità elaborato più recente.</span><span class="sxs-lookup"><span data-stu-id="3bf49-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="3bf49-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="3bf49-112">activeServerID</span></span>  <br/> |<span data-ttu-id="3bf49-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="3bf49-113">int, not null</span></span>  <br/> |<span data-ttu-id="3bf49-114">ID del server di conformità che contiene il blocco esclusivo nel database oppure-1 se nessuno.</span><span class="sxs-lookup"><span data-stu-id="3bf49-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="3bf49-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="3bf49-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="3bf49-116">datetime2, not null</span><span class="sxs-lookup"><span data-stu-id="3bf49-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="3bf49-117">Blocca ora di scadenza (se activeServerID non è-1).</span><span class="sxs-lookup"><span data-stu-id="3bf49-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

