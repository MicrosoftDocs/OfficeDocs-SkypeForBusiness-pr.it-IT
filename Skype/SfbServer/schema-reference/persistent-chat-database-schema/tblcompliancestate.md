---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contiene informazioni sullo stato della conformità a livello di pool.
ms.openlocfilehash: 82c775b315976b0e5b112c476a41a8f5adc6a24c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809726"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="f1b59-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="f1b59-103">tblComplianceState</span></span>
 
<span data-ttu-id="f1b59-104">tblComplianceState contiene informazioni sullo stato della conformità a livello di pool.</span><span class="sxs-lookup"><span data-stu-id="f1b59-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="f1b59-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="f1b59-105">**Columns**</span></span>

|<span data-ttu-id="f1b59-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="f1b59-106">**Column**</span></span>|<span data-ttu-id="f1b59-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f1b59-107">**Type**</span></span>|<span data-ttu-id="f1b59-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f1b59-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f1b59-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="f1b59-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="f1b59-110">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="f1b59-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="f1b59-111">ID dell'ultimo evento di conformità elaborato.</span><span class="sxs-lookup"><span data-stu-id="f1b59-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="f1b59-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="f1b59-112">activeServerID</span></span>  <br/> |<span data-ttu-id="f1b59-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="f1b59-113">int, not null</span></span>  <br/> |<span data-ttu-id="f1b59-114">ID del server di conformità che detiene il blocco esclusivo sul database, o -1 se assente.</span><span class="sxs-lookup"><span data-stu-id="f1b59-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="f1b59-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="f1b59-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="f1b59-116">datetime2, not null</span><span class="sxs-lookup"><span data-stu-id="f1b59-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="f1b59-117">Ora di scadenza del blocco (se activeServerID è diverso da  -1).</span><span class="sxs-lookup"><span data-stu-id="f1b59-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

