---
title: Tabella ConferenceUris in Skype for Business Server 2015
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
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: La tabella ConfereneUris è una tabella di supporto in cui è archiviato un elenco dei vari URI di conferenza che hanno partecipato a sessioni di conferenza registrate nel database. Ogni record nella tabella rappresenta un URI di conferenza.
ms.openlocfilehash: f1e95cce4fedf26477973a4fba6a9d3a32288f92
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815314"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="b53f3-104">Tabella ConferenceUris in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b53f3-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b53f3-105">La tabella ConfereneUris è una tabella di supporto in cui è archiviato un elenco dei vari URI di conferenza che hanno partecipato a sessioni di conferenza registrate nel database.</span><span class="sxs-lookup"><span data-stu-id="b53f3-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="b53f3-106">Ogni record nella tabella rappresenta un URI di conferenza.</span><span class="sxs-lookup"><span data-stu-id="b53f3-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="b53f3-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="b53f3-107">**Column**</span></span>|<span data-ttu-id="b53f3-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="b53f3-108">**Data Type**</span></span>|<span data-ttu-id="b53f3-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="b53f3-109">**Key/Index**</span></span>|<span data-ttu-id="b53f3-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="b53f3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b53f3-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="b53f3-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="b53f3-112">DateTime</span><span class="sxs-lookup"><span data-stu-id="b53f3-112">datetime</span></span>  <br/> |<span data-ttu-id="b53f3-113">Principale</span><span class="sxs-lookup"><span data-stu-id="b53f3-113">Primary</span></span>  <br/> |<span data-ttu-id="b53f3-114">Indicatore di data e ora, interno usato.</span><span class="sxs-lookup"><span data-stu-id="b53f3-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="b53f3-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="b53f3-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="b53f3-116">int</span><span class="sxs-lookup"><span data-stu-id="b53f3-116">int</span></span>  <br/> |<span data-ttu-id="b53f3-117">Principale</span><span class="sxs-lookup"><span data-stu-id="b53f3-117">Primary</span></span>  <br/> |<span data-ttu-id="b53f3-118">Numero univoco che identifica questo URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="b53f3-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="b53f3-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="b53f3-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="b53f3-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b53f3-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="b53f3-121">URI conferenza.</span><span class="sxs-lookup"><span data-stu-id="b53f3-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="b53f3-122">**Checksum**</span><span class="sxs-lookup"><span data-stu-id="b53f3-122">**Checksum**</span></span> <br/> |<span data-ttu-id="b53f3-123">int</span><span class="sxs-lookup"><span data-stu-id="b53f3-123">int</span></span>  <br/> ||<span data-ttu-id="b53f3-124">Checksum di ConferenceUri.</span><span class="sxs-lookup"><span data-stu-id="b53f3-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="b53f3-125">Usato per aumentare la velocità delle ricerche nel database.</span><span class="sxs-lookup"><span data-stu-id="b53f3-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="b53f3-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="b53f3-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="b53f3-127">int</span><span class="sxs-lookup"><span data-stu-id="b53f3-127">int</span></span>  <br/> |<span data-ttu-id="b53f3-128">Esterna</span><span class="sxs-lookup"><span data-stu-id="b53f3-128">Foreign</span></span>  <br/> |<span data-ttu-id="b53f3-129">Tipo di URI, ad esempio conf: chat per la conferenza di messaggistica istantanea o conf: audio-video per conferenze audio/video.</span><span class="sxs-lookup"><span data-stu-id="b53f3-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="b53f3-130">Per altre informazioni, vedere la tabella [tabella UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="b53f3-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

