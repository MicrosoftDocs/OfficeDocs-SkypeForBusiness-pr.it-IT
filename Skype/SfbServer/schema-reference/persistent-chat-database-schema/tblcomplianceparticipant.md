---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contiene i partecipanti correnti per canale e per server.
ms.openlocfilehash: 8f4b90cd7e8949451c2b6c1b9bc3cfabbab826e9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814644"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="560ca-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="560ca-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="560ca-104">tblComplianceParticipant contiene i partecipanti correnti per canale e per server.</span><span class="sxs-lookup"><span data-stu-id="560ca-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="560ca-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="560ca-105">**Columns**</span></span>

|<span data-ttu-id="560ca-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="560ca-106">**Column**</span></span>|<span data-ttu-id="560ca-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="560ca-107">**Type**</span></span>|<span data-ttu-id="560ca-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="560ca-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="560ca-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="560ca-109">channelUri</span></span>  <br/> |<span data-ttu-id="560ca-110">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="560ca-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="560ca-111">URI (Uniform Resource Identifier) del canale.</span><span class="sxs-lookup"><span data-stu-id="560ca-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="560ca-112">userId</span><span class="sxs-lookup"><span data-stu-id="560ca-112">userId</span></span>  <br/> |<span data-ttu-id="560ca-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="560ca-113">int, not null</span></span>  <br/> |<span data-ttu-id="560ca-114">ID principale del partecipante (corrispondente alla tabella tblPrincipal. prinID).</span><span class="sxs-lookup"><span data-stu-id="560ca-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="560ca-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="560ca-115">joinedAt</span></span>  <br/> |<span data-ttu-id="560ca-116">bigint e non null</span><span class="sxs-lookup"><span data-stu-id="560ca-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="560ca-117">Indicatore di data e ora dell'evento Joining.</span><span class="sxs-lookup"><span data-stu-id="560ca-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="560ca-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="560ca-118">partedAt</span></span>  <br/> |<span data-ttu-id="560ca-119">bigint</span><span class="sxs-lookup"><span data-stu-id="560ca-119">bigint</span></span>  <br/> |<span data-ttu-id="560ca-120">Null se i partecipanti sono ancora Uniti.</span><span class="sxs-lookup"><span data-stu-id="560ca-120">Null if participant is still joined.</span></span> <span data-ttu-id="560ca-121">L'indicatore di data e ora del canale che lascia l'evento se non è null.</span><span class="sxs-lookup"><span data-stu-id="560ca-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="560ca-122">Queste voci vengono infine rimosse quando tutti i traduttori elaborano l'evento.</span><span class="sxs-lookup"><span data-stu-id="560ca-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="560ca-123">userUri</span><span class="sxs-lookup"><span data-stu-id="560ca-123">userUri</span></span>  <br/> |<span data-ttu-id="560ca-124">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="560ca-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="560ca-125">URI utente.</span><span class="sxs-lookup"><span data-stu-id="560ca-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="560ca-126">serverID</span><span class="sxs-lookup"><span data-stu-id="560ca-126">serverID</span></span>  <br/> |<span data-ttu-id="560ca-127">int</span><span class="sxs-lookup"><span data-stu-id="560ca-127">int</span></span>  <br/> |<span data-ttu-id="560ca-128">Identità del server (come nella tabella tblServerIdentity. serverID).</span><span class="sxs-lookup"><span data-stu-id="560ca-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="560ca-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="560ca-129">sessionId</span></span>  <br/> |<span data-ttu-id="560ca-130">bigint</span><span class="sxs-lookup"><span data-stu-id="560ca-130">bigint</span></span>  <br/> |<span data-ttu-id="560ca-131">Sessione del server.</span><span class="sxs-lookup"><span data-stu-id="560ca-131">Server session.</span></span> <span data-ttu-id="560ca-132">Si tratta di un numero casuale generato ogni volta che viene avviato un servizio chat.</span><span class="sxs-lookup"><span data-stu-id="560ca-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="560ca-133">Viene usato per distinguere le sessioni allo scopo di identificare i partecipanti orfani.</span><span class="sxs-lookup"><span data-stu-id="560ca-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="560ca-134">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="560ca-134">**Key**</span></span>

|<span data-ttu-id="560ca-135">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="560ca-135">**Column**</span></span>|<span data-ttu-id="560ca-136">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="560ca-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="560ca-137">\<channelUri, userId, joinedAt\></span><span class="sxs-lookup"><span data-stu-id="560ca-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="560ca-138">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="560ca-138">Primary key.</span></span>  <br/> |
   

