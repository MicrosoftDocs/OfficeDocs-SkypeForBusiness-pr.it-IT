---
title: Tabella ContentTypes in Skype for Business Server 2015
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
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: La tabella ContentTypes è una tabella di supporto in cui è archiviato un elenco dei tipi di contenuto utilizzati sia nelle sessioni peer-to-peer che nelle sessioni di conferenze. Ogni record della tabella rappresenta un tipo di contenuto.
ms.openlocfilehash: 461631c8fc824a23f0e4b22b65a3cbc8cf6a2c73
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816086"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e91d0-104">Tabella ContentTypes in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e91d0-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e91d0-p102">La tabella ContentTypes è una tabella di supporto in cui è archiviato un elenco dei tipi di contenuto utilizzati sia nelle sessioni peer-to-peer che nelle sessioni di conferenze. Ogni record della tabella rappresenta un tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="e91d0-p102">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions. Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="e91d0-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="e91d0-107">**Column**</span></span>|<span data-ttu-id="e91d0-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="e91d0-108">**Data Type**</span></span>|<span data-ttu-id="e91d0-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="e91d0-109">**Key/Index**</span></span>|<span data-ttu-id="e91d0-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="e91d0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e91d0-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="e91d0-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="e91d0-112">int</span><span class="sxs-lookup"><span data-stu-id="e91d0-112">int</span></span>  <br/> |<span data-ttu-id="e91d0-113">Principale</span><span class="sxs-lookup"><span data-stu-id="e91d0-113">Primary</span></span>  <br/> |<span data-ttu-id="e91d0-114">Numero univoco che identifica il tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="e91d0-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="e91d0-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="e91d0-115">**ContentType**</span></span> <br/> |<span data-ttu-id="e91d0-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e91d0-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="e91d0-117">Nome del tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="e91d0-117">Content type name.</span></span>  <br/> |
   

