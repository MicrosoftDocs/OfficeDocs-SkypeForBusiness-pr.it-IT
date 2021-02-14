---
title: Tabella ConferenceMessageCount in Skype for Business Server
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
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Ogni record in questa tabella rappresenta un utente in una conferenza di messaggistica istantanea e include il numero di messaggi inviati da tale utente. Ogni conferenza è rappresentata da più record in questa tabella. un record per ogni utente.
ms.openlocfilehash: b931b45915fc12fb01ea36f81bee62f36914e903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813276"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e8161-104">Tabella ConferenceMessageCount in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e8161-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e8161-105">Ogni record in questa tabella rappresenta un utente in una conferenza di messaggistica istantanea e include il numero di messaggi inviati da tale utente.</span><span class="sxs-lookup"><span data-stu-id="e8161-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="e8161-106">Ogni conferenza è rappresentata da più record in questa tabella. un record per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="e8161-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="e8161-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="e8161-107">**Column**</span></span>|<span data-ttu-id="e8161-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="e8161-108">**Data Type**</span></span>|<span data-ttu-id="e8161-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="e8161-109">**Key/Index**</span></span>|<span data-ttu-id="e8161-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="e8161-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e8161-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="e8161-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="e8161-112">datetime</span><span class="sxs-lookup"><span data-stu-id="e8161-112">datetime</span></span>  <br/> |<span data-ttu-id="e8161-113">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="e8161-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e8161-114">Data e ora dell'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e8161-114">Time of conference instance.</span></span> <span data-ttu-id="e8161-115">Utilizzato insieme a **SessionIdSeq** per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e8161-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="e8161-116">Per altre informazioni, vedere la tabella Conferenze [in Skype for Business Server 2015.](conferences.md)</span><span class="sxs-lookup"><span data-stu-id="e8161-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e8161-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="e8161-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="e8161-118">int</span><span class="sxs-lookup"><span data-stu-id="e8161-118">int</span></span>  <br/> |<span data-ttu-id="e8161-119">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="e8161-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e8161-120">Numero ID per identificare l'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e8161-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="e8161-121">Utilizzato insieme a **SessionIdTime** per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e8161-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="e8161-122">Per altre informazioni, vedere la tabella Conferenze [in Skype for Business Server 2015.](conferences.md)</span><span class="sxs-lookup"><span data-stu-id="e8161-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e8161-123">**UserId**</span><span class="sxs-lookup"><span data-stu-id="e8161-123">**UserId**</span></span> <br/> |<span data-ttu-id="e8161-124">int</span><span class="sxs-lookup"><span data-stu-id="e8161-124">int</span></span>  <br/> |<span data-ttu-id="e8161-125">Esterna</span><span class="sxs-lookup"><span data-stu-id="e8161-125">Foreign</span></span>  <br/> |<span data-ttu-id="e8161-126">Numero univoco che identifica l'utente, a cui viene fatto riferimento dalla [tabella Utenti.](users.md)</span><span class="sxs-lookup"><span data-stu-id="e8161-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="e8161-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="e8161-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="e8161-128">smallint</span><span class="sxs-lookup"><span data-stu-id="e8161-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="e8161-129">Numero di messaggi inviati dall'utente durante questa conferenza.</span><span class="sxs-lookup"><span data-stu-id="e8161-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

