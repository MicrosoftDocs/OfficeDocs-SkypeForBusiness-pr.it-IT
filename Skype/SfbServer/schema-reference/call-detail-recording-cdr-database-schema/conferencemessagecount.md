---
title: Tabella ConferenceMessageCount in Skype for Business Server 2015
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
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Ogni record in questa tabella rappresenta un utente in una conferenza di messaggistica istantanea e include il numero di messaggi inviati dall'utente. Ogni conferenza è rappresentata da più record in questa tabella. un record per ogni utente.
ms.openlocfilehash: 66651f798d627ef4ea783c4ecf4e7cb8f1adab81
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815374"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="6fbe4-104">Tabella ConferenceMessageCount in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6fbe4-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6fbe4-105">Ogni record in questa tabella rappresenta un utente in una conferenza di messaggistica istantanea e include il numero di messaggi inviati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="6fbe4-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="6fbe4-106">Ogni conferenza è rappresentata da più record in questa tabella. un record per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="6fbe4-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="6fbe4-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="6fbe4-107">**Column**</span></span>|<span data-ttu-id="6fbe4-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="6fbe4-108">**Data Type**</span></span>|<span data-ttu-id="6fbe4-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="6fbe4-109">**Key/Index**</span></span>|<span data-ttu-id="6fbe4-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="6fbe4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6fbe4-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="6fbe4-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="6fbe4-112">DateTime</span><span class="sxs-lookup"><span data-stu-id="6fbe4-112">datetime</span></span>  <br/> |<span data-ttu-id="6fbe4-113">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="6fbe4-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="6fbe4-114">Ora dell'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="6fbe4-114">Time of conference instance.</span></span> <span data-ttu-id="6fbe4-115">Usato in combinazione con **SessionIdSeq** per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="6fbe4-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="6fbe4-116">Per altre informazioni, vedere la [tabella conferenze in Skype for Business Server 2015](conferences.md) .</span><span class="sxs-lookup"><span data-stu-id="6fbe4-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6fbe4-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="6fbe4-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="6fbe4-118">int</span><span class="sxs-lookup"><span data-stu-id="6fbe4-118">int</span></span>  <br/> |<span data-ttu-id="6fbe4-119">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="6fbe4-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="6fbe4-120">Numero ID per identificare l'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="6fbe4-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="6fbe4-121">Usato in combinazione con **SessionIdTime** per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="6fbe4-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="6fbe4-122">Per altre informazioni, vedere la [tabella conferenze in Skype for Business Server 2015](conferences.md) .</span><span class="sxs-lookup"><span data-stu-id="6fbe4-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6fbe4-123">**UserId**</span><span class="sxs-lookup"><span data-stu-id="6fbe4-123">**UserId**</span></span> <br/> |<span data-ttu-id="6fbe4-124">int</span><span class="sxs-lookup"><span data-stu-id="6fbe4-124">int</span></span>  <br/> |<span data-ttu-id="6fbe4-125">Esterna</span><span class="sxs-lookup"><span data-stu-id="6fbe4-125">Foreign</span></span>  <br/> |<span data-ttu-id="6fbe4-126">Numero univoco che identifica l'utente, a cui viene fatto riferimento dalla [tabella utenti](users.md).</span><span class="sxs-lookup"><span data-stu-id="6fbe4-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="6fbe4-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="6fbe4-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="6fbe4-128">smallint</span><span class="sxs-lookup"><span data-stu-id="6fbe4-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="6fbe4-129">Numero di messaggi inviati dall'utente durante questa conferenza.</span><span class="sxs-lookup"><span data-stu-id="6fbe4-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

