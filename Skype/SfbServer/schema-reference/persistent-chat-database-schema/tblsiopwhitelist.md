---
title: tblSiopWhiteList
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList è l'elenco dei componenti aggiuntivi registrati che possono essere associati ai nodi.
ms.openlocfilehash: cf7a727bd34e5c6f29f5bf0b203411983c90ae53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831486"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="eed55-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="eed55-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="eed55-104">tblSiopWhiteList è l'elenco dei componenti aggiuntivi registrati che possono essere associati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="eed55-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="eed55-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="eed55-105">**Columns**</span></span>

|<span data-ttu-id="eed55-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="eed55-106">**Column**</span></span>|<span data-ttu-id="eed55-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="eed55-107">**Type**</span></span>|<span data-ttu-id="eed55-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="eed55-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="eed55-109">siopID</span><span class="sxs-lookup"><span data-stu-id="eed55-109">siopID</span></span>  <br/> |<span data-ttu-id="eed55-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="eed55-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="eed55-111">GUID del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="eed55-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="eed55-112">siopName</span><span class="sxs-lookup"><span data-stu-id="eed55-112">siopName</span></span>  <br/> |<span data-ttu-id="eed55-113">nvarchar (50), not null</span><span class="sxs-lookup"><span data-stu-id="eed55-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="eed55-114">Nome visualizzato del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="eed55-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="eed55-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="eed55-115">siopUrl</span></span>  <br/> |<span data-ttu-id="eed55-116">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="eed55-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="eed55-117">URL del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="eed55-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="eed55-118">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="eed55-118">**Key**</span></span>

|<span data-ttu-id="eed55-119">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="eed55-119">**Column**</span></span>|<span data-ttu-id="eed55-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="eed55-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="eed55-121">siopID</span><span class="sxs-lookup"><span data-stu-id="eed55-121">siopID</span></span>  <br/> |<span data-ttu-id="eed55-122">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="eed55-122">Primary key.</span></span>  <br/> |
   

