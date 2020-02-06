---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contiene un server di chat persistente che non supporta la configurazione, in una riga.
ms.openlocfilehash: f79af00d6a9f97f0ce0836684a284779be662c1d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814624"
---
# <a name="tblconfig"></a><span data-ttu-id="8980c-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="8980c-103">tblConfig</span></span>
 
<span data-ttu-id="8980c-104">tblConfig contiene un server di chat persistente che non supporta la configurazione, in una riga.</span><span class="sxs-lookup"><span data-stu-id="8980c-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="8980c-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="8980c-105">**Columns**</span></span>

|<span data-ttu-id="8980c-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="8980c-106">**Column**</span></span>|<span data-ttu-id="8980c-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8980c-107">**Type**</span></span>|<span data-ttu-id="8980c-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="8980c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8980c-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="8980c-109">configLabel</span></span>  <br/> |<span data-ttu-id="8980c-110">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="8980c-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="8980c-111">Contiene "pool".</span><span class="sxs-lookup"><span data-stu-id="8980c-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="8980c-112">configContent</span><span class="sxs-lookup"><span data-stu-id="8980c-112">configContent</span></span>  <br/> |<span data-ttu-id="8980c-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="8980c-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="8980c-114">Contenuto della configurazione.</span><span class="sxs-lookup"><span data-stu-id="8980c-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="8980c-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="8980c-115">configPoolID</span></span>  <br/> |<span data-ttu-id="8980c-116">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="8980c-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="8980c-117">ID univoco dell'istanza del database.</span><span class="sxs-lookup"><span data-stu-id="8980c-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="8980c-118">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="8980c-118">**Key**</span></span>

|<span data-ttu-id="8980c-119">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="8980c-119">**Column**</span></span>|<span data-ttu-id="8980c-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="8980c-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8980c-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="8980c-121">configLabel</span></span>  <br/> |<span data-ttu-id="8980c-122">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="8980c-122">Primary key.</span></span>  <br/> |
   

