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
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contiene un server di chat persistente che non supporta la configurazione, in una riga.
ms.openlocfilehash: 244eebcb88c67b521022f9d64888678f221d2369
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194690"
---
# <a name="tblconfig"></a><span data-ttu-id="5337c-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="5337c-103">tblConfig</span></span>
 
<span data-ttu-id="5337c-104">tblConfig contiene un server di chat persistente che non supporta la configurazione, in una riga.</span><span class="sxs-lookup"><span data-stu-id="5337c-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="5337c-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="5337c-105">**Columns**</span></span>

|<span data-ttu-id="5337c-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="5337c-106">**Column**</span></span>|<span data-ttu-id="5337c-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5337c-107">**Type**</span></span>|<span data-ttu-id="5337c-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="5337c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5337c-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="5337c-109">configLabel</span></span>  <br/> |<span data-ttu-id="5337c-110">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="5337c-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="5337c-111">Contiene "pool".</span><span class="sxs-lookup"><span data-stu-id="5337c-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="5337c-112">configContent</span><span class="sxs-lookup"><span data-stu-id="5337c-112">configContent</span></span>  <br/> |<span data-ttu-id="5337c-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="5337c-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="5337c-114">Contenuto della configurazione.</span><span class="sxs-lookup"><span data-stu-id="5337c-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="5337c-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="5337c-115">configPoolID</span></span>  <br/> |<span data-ttu-id="5337c-116">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="5337c-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="5337c-117">ID univoco dell'istanza del database.</span><span class="sxs-lookup"><span data-stu-id="5337c-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="5337c-118">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="5337c-118">**Key**</span></span>

|<span data-ttu-id="5337c-119">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="5337c-119">**Column**</span></span>|<span data-ttu-id="5337c-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="5337c-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5337c-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="5337c-121">configLabel</span></span>  <br/> |<span data-ttu-id="5337c-122">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="5337c-122">Primary key.</span></span>  <br/> |
   

