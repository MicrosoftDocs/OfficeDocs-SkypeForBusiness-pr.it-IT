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
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Ogni record in questa tabella rappresenta un utente in una conferenza di messaggistica istantanea e include il numero di messaggi inviati dall'utente. Ogni conferenza è rappresentata da più record in questa tabella. un record per ogni utente.
ms.openlocfilehash: ef343536c34b3bd27d71ee37813e4b4e65156094
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194837"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="67cb3-104">Tabella ConferenceMessageCount in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="67cb3-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="67cb3-105">Ogni record in questa tabella rappresenta un utente in una conferenza di messaggistica istantanea e include il numero di messaggi inviati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="67cb3-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="67cb3-106">Ogni conferenza è rappresentata da più record in questa tabella. un record per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="67cb3-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="67cb3-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="67cb3-107">**Column**</span></span>|<span data-ttu-id="67cb3-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="67cb3-108">**Data Type**</span></span>|<span data-ttu-id="67cb3-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="67cb3-109">**Key/Index**</span></span>|<span data-ttu-id="67cb3-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="67cb3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="67cb3-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="67cb3-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="67cb3-112">DateTime</span><span class="sxs-lookup"><span data-stu-id="67cb3-112">datetime</span></span>  <br/> |<span data-ttu-id="67cb3-113">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="67cb3-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="67cb3-114">Ora dell'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="67cb3-114">Time of conference instance.</span></span> <span data-ttu-id="67cb3-115">Usato in combinazione con **SessionIdSeq** per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="67cb3-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="67cb3-116">Per altre informazioni, vedere la [tabella conferenze in Skype for Business Server 2015](conferences.md) .</span><span class="sxs-lookup"><span data-stu-id="67cb3-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="67cb3-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="67cb3-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="67cb3-118">int</span><span class="sxs-lookup"><span data-stu-id="67cb3-118">int</span></span>  <br/> |<span data-ttu-id="67cb3-119">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="67cb3-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="67cb3-120">Numero ID per identificare l'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="67cb3-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="67cb3-121">Usato in combinazione con **SessionIdTime** per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="67cb3-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="67cb3-122">Per altre informazioni, vedere la [tabella conferenze in Skype for Business Server 2015](conferences.md) .</span><span class="sxs-lookup"><span data-stu-id="67cb3-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="67cb3-123">**UserId**</span><span class="sxs-lookup"><span data-stu-id="67cb3-123">**UserId**</span></span> <br/> |<span data-ttu-id="67cb3-124">int</span><span class="sxs-lookup"><span data-stu-id="67cb3-124">int</span></span>  <br/> |<span data-ttu-id="67cb3-125">Esterna</span><span class="sxs-lookup"><span data-stu-id="67cb3-125">Foreign</span></span>  <br/> |<span data-ttu-id="67cb3-126">Numero univoco che identifica l'utente, a cui viene fatto riferimento dalla [tabella utenti](users.md).</span><span class="sxs-lookup"><span data-stu-id="67cb3-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="67cb3-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="67cb3-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="67cb3-128">smallint</span><span class="sxs-lookup"><span data-stu-id="67cb3-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="67cb3-129">Numero di messaggi inviati dall'utente durante questa conferenza.</span><span class="sxs-lookup"><span data-stu-id="67cb3-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

