---
title: Tabella ConferenceMessageCount in Skype for Business Server 2015
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
description: Ogni record di questa tabella rappresenta un utente in una conferenza di messaggistica istantanea e include il numero di messaggi inviati dall'utente. Ogni conferenza è rappresentata da più record in questa tabella. un record per ogni utente.
ms.openlocfilehash: b931b45915fc12fb01ea36f81bee62f36914e903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813276"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="423c7-104">Tabella ConferenceMessageCount in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="423c7-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="423c7-105">Ogni record di questa tabella rappresenta un utente in una conferenza di messaggistica istantanea e include il numero di messaggi inviati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="423c7-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="423c7-106">Ogni conferenza è rappresentata da più record in questa tabella. un record per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="423c7-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="423c7-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="423c7-107">**Column**</span></span>|<span data-ttu-id="423c7-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="423c7-108">**Data Type**</span></span>|<span data-ttu-id="423c7-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="423c7-109">**Key/Index**</span></span>|<span data-ttu-id="423c7-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="423c7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="423c7-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="423c7-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="423c7-112">datetime</span><span class="sxs-lookup"><span data-stu-id="423c7-112">datetime</span></span>  <br/> |<span data-ttu-id="423c7-113">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="423c7-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="423c7-114">Data e ora dell'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="423c7-114">Time of conference instance.</span></span> <span data-ttu-id="423c7-115">Utilizzato insieme a **SessionIdSeq** per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="423c7-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="423c7-116">Per ulteriori informazioni, vedere la [tabella conferenze in Skype for Business Server 2015](conferences.md) .</span><span class="sxs-lookup"><span data-stu-id="423c7-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="423c7-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="423c7-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="423c7-118">int</span><span class="sxs-lookup"><span data-stu-id="423c7-118">int</span></span>  <br/> |<span data-ttu-id="423c7-119">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="423c7-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="423c7-120">Numero ID per identificare l'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="423c7-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="423c7-121">Utilizzato insieme a **SessionIdTime** per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="423c7-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="423c7-122">Per ulteriori informazioni, vedere la [tabella conferenze in Skype for Business Server 2015](conferences.md) .</span><span class="sxs-lookup"><span data-stu-id="423c7-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="423c7-123">**UserId**</span><span class="sxs-lookup"><span data-stu-id="423c7-123">**UserId**</span></span> <br/> |<span data-ttu-id="423c7-124">int</span><span class="sxs-lookup"><span data-stu-id="423c7-124">int</span></span>  <br/> |<span data-ttu-id="423c7-125">Stranieri</span><span class="sxs-lookup"><span data-stu-id="423c7-125">Foreign</span></span>  <br/> |<span data-ttu-id="423c7-126">Numero univoco che identifica l'utente, a cui viene fatto riferimento dalla [tabella users](users.md).</span><span class="sxs-lookup"><span data-stu-id="423c7-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="423c7-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="423c7-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="423c7-128">smallint</span><span class="sxs-lookup"><span data-stu-id="423c7-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="423c7-129">Il numero di messaggi inviati dall'utente durante la conferenza.</span><span class="sxs-lookup"><span data-stu-id="423c7-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

