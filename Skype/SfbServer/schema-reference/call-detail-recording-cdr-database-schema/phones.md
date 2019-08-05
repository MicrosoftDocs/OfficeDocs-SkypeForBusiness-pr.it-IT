---
title: Tabella Phones
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: La tabella telefoni è una tabella di supporto. Ogni record nella tabella archivia le informazioni relative a un numero di telefono coinvolto in chiamate VoIP che includono record nel database.
ms.openlocfilehash: 684586f21b16c785bcc75458e5330c42aad2ccb4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194763"
---
# <a name="phones-table"></a><span data-ttu-id="5f9ea-104">Tabella Phones</span><span class="sxs-lookup"><span data-stu-id="5f9ea-104">Phones table</span></span>
 
<span data-ttu-id="5f9ea-105">La tabella telefoni è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="5f9ea-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="5f9ea-106">Ogni record nella tabella archivia le informazioni relative a un numero di telefono coinvolto in chiamate VoIP che includono record nel database.</span><span class="sxs-lookup"><span data-stu-id="5f9ea-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="5f9ea-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="5f9ea-107">**Column**</span></span>|<span data-ttu-id="5f9ea-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="5f9ea-108">**Data Type**</span></span>|<span data-ttu-id="5f9ea-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="5f9ea-109">**Key/Index**</span></span>|<span data-ttu-id="5f9ea-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="5f9ea-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5f9ea-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="5f9ea-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="5f9ea-112">int</span><span class="sxs-lookup"><span data-stu-id="5f9ea-112">int</span></span>  <br/> |<span data-ttu-id="5f9ea-113">Principale</span><span class="sxs-lookup"><span data-stu-id="5f9ea-113">Primary</span></span>  <br/> |<span data-ttu-id="5f9ea-114">Numero univoco che identifica il telefono.</span><span class="sxs-lookup"><span data-stu-id="5f9ea-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="5f9ea-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="5f9ea-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="5f9ea-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5f9ea-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="5f9ea-117">Numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="5f9ea-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="5f9ea-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="5f9ea-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="5f9ea-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="5f9ea-119">dateTime</span></span>  <br/> ||<span data-ttu-id="5f9ea-120">Indicatore di data e ora (solo per uso interno).</span><span class="sxs-lookup"><span data-stu-id="5f9ea-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="5f9ea-121">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f9ea-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

