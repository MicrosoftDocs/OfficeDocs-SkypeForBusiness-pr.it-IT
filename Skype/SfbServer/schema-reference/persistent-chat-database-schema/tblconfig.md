---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contiene alcune configurazioni non supportate del server Chat persistente, in una riga.
ms.openlocfilehash: 614e4e6514d695777c39a9d76482f775bd1a0981
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809736"
---
# <a name="tblconfig"></a><span data-ttu-id="5d7c1-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="5d7c1-103">tblConfig</span></span>
 
<span data-ttu-id="5d7c1-104">tblConfig contiene alcune configurazioni non supportate del server Chat persistente, in una riga.</span><span class="sxs-lookup"><span data-stu-id="5d7c1-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="5d7c1-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="5d7c1-105">**Columns**</span></span>

|<span data-ttu-id="5d7c1-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="5d7c1-106">**Column**</span></span>|<span data-ttu-id="5d7c1-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5d7c1-107">**Type**</span></span>|<span data-ttu-id="5d7c1-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="5d7c1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5d7c1-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="5d7c1-109">configLabel</span></span>  <br/> |<span data-ttu-id="5d7c1-110">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="5d7c1-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="5d7c1-111">Contiene "pool."</span><span class="sxs-lookup"><span data-stu-id="5d7c1-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="5d7c1-112">configContent</span><span class="sxs-lookup"><span data-stu-id="5d7c1-112">configContent</span></span>  <br/> |<span data-ttu-id="5d7c1-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="5d7c1-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="5d7c1-114">Contenuto della configurazione.</span><span class="sxs-lookup"><span data-stu-id="5d7c1-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="5d7c1-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="5d7c1-115">configPoolID</span></span>  <br/> |<span data-ttu-id="5d7c1-116">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="5d7c1-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="5d7c1-117">ID univoco dell'istanza di database.</span><span class="sxs-lookup"><span data-stu-id="5d7c1-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="5d7c1-118">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="5d7c1-118">**Key**</span></span>

|<span data-ttu-id="5d7c1-119">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="5d7c1-119">**Column**</span></span>|<span data-ttu-id="5d7c1-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="5d7c1-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5d7c1-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="5d7c1-121">configLabel</span></span>  <br/> |<span data-ttu-id="5d7c1-122">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="5d7c1-122">Primary key.</span></span>  <br/> |
   

