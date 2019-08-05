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
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: La tabella ContentTypes è una tabella di supporto in cui è archiviato un elenco dei tipi di contenuto usati nelle sessioni peer-to-peer e nelle sessioni di conferenza. Ogni record nella tabella rappresenta un tipo di contenuto.
ms.openlocfilehash: b8422cbe95425ac79495c0506f4a94e70be3f9af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194822"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="61f2e-104">Tabella ContentTypes in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="61f2e-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="61f2e-105">La tabella ContentTypes è una tabella di supporto in cui è archiviato un elenco dei tipi di contenuto usati nelle sessioni peer-to-peer e nelle sessioni di conferenza.</span><span class="sxs-lookup"><span data-stu-id="61f2e-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="61f2e-106">Ogni record nella tabella rappresenta un tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="61f2e-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="61f2e-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="61f2e-107">**Column**</span></span>|<span data-ttu-id="61f2e-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="61f2e-108">**Data Type**</span></span>|<span data-ttu-id="61f2e-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="61f2e-109">**Key/Index**</span></span>|<span data-ttu-id="61f2e-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="61f2e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="61f2e-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="61f2e-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="61f2e-112">int</span><span class="sxs-lookup"><span data-stu-id="61f2e-112">int</span></span>  <br/> |<span data-ttu-id="61f2e-113">Principale</span><span class="sxs-lookup"><span data-stu-id="61f2e-113">Primary</span></span>  <br/> |<span data-ttu-id="61f2e-114">Numero univoco che identifica il tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="61f2e-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="61f2e-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="61f2e-115">**ContentType**</span></span> <br/> |<span data-ttu-id="61f2e-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f2e-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="61f2e-117">Nome tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="61f2e-117">Content type name.</span></span>  <br/> |
   

