---
title: tblSiopWhiteList
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList è l'elenco dei componenti aggiuntivi registrati che possono essere associati ai nodi.
ms.openlocfilehash: ae287a1a32b09ce309c688dac2a042913383a263
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812114"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="136fe-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="136fe-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="136fe-104">tblSiopWhiteList è l'elenco dei componenti aggiuntivi registrati che possono essere associati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="136fe-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="136fe-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="136fe-105">**Columns**</span></span>

|<span data-ttu-id="136fe-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="136fe-106">**Column**</span></span>|<span data-ttu-id="136fe-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="136fe-107">**Type**</span></span>|<span data-ttu-id="136fe-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="136fe-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="136fe-109">siopID</span><span class="sxs-lookup"><span data-stu-id="136fe-109">siopID</span></span>  <br/> |<span data-ttu-id="136fe-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="136fe-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="136fe-111">GUID del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="136fe-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="136fe-112">siopName</span><span class="sxs-lookup"><span data-stu-id="136fe-112">siopName</span></span>  <br/> |<span data-ttu-id="136fe-113">nvarchar (50), not null</span><span class="sxs-lookup"><span data-stu-id="136fe-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="136fe-114">Nome visualizzato del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="136fe-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="136fe-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="136fe-115">siopUrl</span></span>  <br/> |<span data-ttu-id="136fe-116">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="136fe-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="136fe-117">URL del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="136fe-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="136fe-118">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="136fe-118">**Key**</span></span>

|<span data-ttu-id="136fe-119">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="136fe-119">**Column**</span></span>|<span data-ttu-id="136fe-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="136fe-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="136fe-121">siopID</span><span class="sxs-lookup"><span data-stu-id="136fe-121">siopID</span></span>  <br/> |<span data-ttu-id="136fe-122">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="136fe-122">Primary key.</span></span>  <br/> |
   

