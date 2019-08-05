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
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList è l'elenco dei componenti aggiuntivi registrati che possono essere associati ai nodi.
ms.openlocfilehash: 3277ec3a2d4fe11000b2eda60fa2327547c77d2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194651"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="8264f-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="8264f-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="8264f-104">tblSiopWhiteList è l'elenco dei componenti aggiuntivi registrati che possono essere associati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="8264f-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="8264f-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="8264f-105">**Columns**</span></span>

|<span data-ttu-id="8264f-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="8264f-106">**Column**</span></span>|<span data-ttu-id="8264f-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8264f-107">**Type**</span></span>|<span data-ttu-id="8264f-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="8264f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8264f-109">siopID</span><span class="sxs-lookup"><span data-stu-id="8264f-109">siopID</span></span>  <br/> |<span data-ttu-id="8264f-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="8264f-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="8264f-111">GUID del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="8264f-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="8264f-112">siopName</span><span class="sxs-lookup"><span data-stu-id="8264f-112">siopName</span></span>  <br/> |<span data-ttu-id="8264f-113">nvarchar (50), not null</span><span class="sxs-lookup"><span data-stu-id="8264f-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="8264f-114">Nome visualizzato del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="8264f-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="8264f-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="8264f-115">siopUrl</span></span>  <br/> |<span data-ttu-id="8264f-116">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="8264f-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="8264f-117">URL del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="8264f-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="8264f-118">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="8264f-118">**Key**</span></span>

|<span data-ttu-id="8264f-119">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="8264f-119">**Column**</span></span>|<span data-ttu-id="8264f-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="8264f-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8264f-121">siopID</span><span class="sxs-lookup"><span data-stu-id="8264f-121">siopID</span></span>  <br/> |<span data-ttu-id="8264f-122">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="8264f-122">Primary key.</span></span>  <br/> |
   

