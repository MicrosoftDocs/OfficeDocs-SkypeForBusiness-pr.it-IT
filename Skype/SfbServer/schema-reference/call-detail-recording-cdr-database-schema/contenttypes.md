---
title: Tabella ContentTypes in Skype for Business Server 2015
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
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: La tabella ContentTypes è una tabella di supporto in cui è archiviato un elenco dei tipi di contenuto usati nelle sessioni peer-to-peer e nelle sessioni di conferenza. Ogni record nella tabella rappresenta un tipo di contenuto.
ms.openlocfilehash: 6dadf7de0107005cca751e27f0c0250bc8f9f03a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815304"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="2634b-104">Tabella ContentTypes in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2634b-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2634b-105">La tabella ContentTypes è una tabella di supporto in cui è archiviato un elenco dei tipi di contenuto usati nelle sessioni peer-to-peer e nelle sessioni di conferenza.</span><span class="sxs-lookup"><span data-stu-id="2634b-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="2634b-106">Ogni record nella tabella rappresenta un tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="2634b-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="2634b-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="2634b-107">**Column**</span></span>|<span data-ttu-id="2634b-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="2634b-108">**Data Type**</span></span>|<span data-ttu-id="2634b-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="2634b-109">**Key/Index**</span></span>|<span data-ttu-id="2634b-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="2634b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2634b-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="2634b-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="2634b-112">int</span><span class="sxs-lookup"><span data-stu-id="2634b-112">int</span></span>  <br/> |<span data-ttu-id="2634b-113">Principale</span><span class="sxs-lookup"><span data-stu-id="2634b-113">Primary</span></span>  <br/> |<span data-ttu-id="2634b-114">Numero univoco che identifica il tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="2634b-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="2634b-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="2634b-115">**ContentType**</span></span> <br/> |<span data-ttu-id="2634b-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2634b-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="2634b-117">Nome tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="2634b-117">Content type name.</span></span>  <br/> |
   

