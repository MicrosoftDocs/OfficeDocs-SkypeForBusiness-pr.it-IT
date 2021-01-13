---
title: Tabella ConferenceUris in Skype for Business Server 2015
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
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: La tabella ConferenceUris è una tabella di supporto in cui viene archiviato un elenco dei diversi URI conferenza che hanno partecipato a sessioni di conferenze registrate nel database. Ogni record della tabella rappresenta un URI conferenza.
ms.openlocfilehash: f439c828460f06067105f8f2da493616c223ed85
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816136"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="64f0f-104">Tabella ConferenceUris in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="64f0f-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="64f0f-p102">La tabella ConferenceUris è una tabella di supporto in cui viene archiviato un elenco dei diversi URI conferenza che hanno partecipato a sessioni di conferenze registrate nel database. Ogni record della tabella rappresenta un URI conferenza.</span><span class="sxs-lookup"><span data-stu-id="64f0f-p102">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database. Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="64f0f-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="64f0f-107">**Column**</span></span>|<span data-ttu-id="64f0f-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="64f0f-108">**Data Type**</span></span>|<span data-ttu-id="64f0f-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="64f0f-109">**Key/Index**</span></span>|<span data-ttu-id="64f0f-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="64f0f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="64f0f-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="64f0f-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="64f0f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="64f0f-112">datetime</span></span>  <br/> |<span data-ttu-id="64f0f-113">Principale</span><span class="sxs-lookup"><span data-stu-id="64f0f-113">Primary</span></span>  <br/> |<span data-ttu-id="64f0f-114">Timestamp, utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="64f0f-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="64f0f-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="64f0f-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="64f0f-116">int</span><span class="sxs-lookup"><span data-stu-id="64f0f-116">int</span></span>  <br/> |<span data-ttu-id="64f0f-117">Principale</span><span class="sxs-lookup"><span data-stu-id="64f0f-117">Primary</span></span>  <br/> |<span data-ttu-id="64f0f-118">Numero univoco che identifica l'URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="64f0f-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="64f0f-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="64f0f-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="64f0f-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="64f0f-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="64f0f-121">URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="64f0f-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="64f0f-122">**Checksum**</span><span class="sxs-lookup"><span data-stu-id="64f0f-122">**Checksum**</span></span> <br/> |<span data-ttu-id="64f0f-123">int</span><span class="sxs-lookup"><span data-stu-id="64f0f-123">int</span></span>  <br/> ||<span data-ttu-id="64f0f-p103">Checksum di ConferenceUri. Utilizzato per aumentare la velocità delle ricerche nel database.</span><span class="sxs-lookup"><span data-stu-id="64f0f-p103">Checksum of ConferenceUri. Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="64f0f-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="64f0f-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="64f0f-127">int</span><span class="sxs-lookup"><span data-stu-id="64f0f-127">int</span></span>  <br/> |<span data-ttu-id="64f0f-128">Stranieri</span><span class="sxs-lookup"><span data-stu-id="64f0f-128">Foreign</span></span>  <br/> |<span data-ttu-id="64f0f-129">Tipo di URI, ad esempio conf:chat per la conferenza di messaggistica istantanea o conf:audio-video per la conferenza audio e video.</span><span class="sxs-lookup"><span data-stu-id="64f0f-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="64f0f-130">Per ulteriori informazioni, vedere la tabella [tabella UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="64f0f-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

