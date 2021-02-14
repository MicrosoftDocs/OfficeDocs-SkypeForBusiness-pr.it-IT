---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: In tblComplianceParticipant sono inclusi i partecipanti correnti per canale e per server.
ms.openlocfilehash: c6aae3c1e7b13456708034512c6b68d67d6d1f92
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809746"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="1160f-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="1160f-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="1160f-104">In tblComplianceParticipant sono inclusi i partecipanti correnti per canale e per server.</span><span class="sxs-lookup"><span data-stu-id="1160f-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="1160f-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="1160f-105">**Columns**</span></span>

|<span data-ttu-id="1160f-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="1160f-106">**Column**</span></span>|<span data-ttu-id="1160f-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1160f-107">**Type**</span></span>|<span data-ttu-id="1160f-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1160f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1160f-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="1160f-109">channelUri</span></span>  <br/> |<span data-ttu-id="1160f-110">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="1160f-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="1160f-111">URI (Uniform Resource Identifier) del canale.</span><span class="sxs-lookup"><span data-stu-id="1160f-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="1160f-112">userId</span><span class="sxs-lookup"><span data-stu-id="1160f-112">userId</span></span>  <br/> |<span data-ttu-id="1160f-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="1160f-113">int, not null</span></span>  <br/> |<span data-ttu-id="1160f-114">ID dell'entità del partecipante (corrispondente alla tabella tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="1160f-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="1160f-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="1160f-115">joinedAt</span></span>  <br/> |<span data-ttu-id="1160f-116">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="1160f-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="1160f-117">Timestamp dell'evento di partecipazione.</span><span class="sxs-lookup"><span data-stu-id="1160f-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="1160f-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="1160f-118">partedAt</span></span>  <br/> |<span data-ttu-id="1160f-119">bigint</span><span class="sxs-lookup"><span data-stu-id="1160f-119">bigint</span></span>  <br/> |<span data-ttu-id="1160f-p101">Null se il partecipante sta ancora partecipando. Timestamp dell'evento di uscita dal canale, se not null.</span><span class="sxs-lookup"><span data-stu-id="1160f-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="1160f-122">Queste voci vengono rimosse alle fine quando tutti i convertitori hanno elaborato l'evento.</span><span class="sxs-lookup"><span data-stu-id="1160f-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="1160f-123">userUri</span><span class="sxs-lookup"><span data-stu-id="1160f-123">userUri</span></span>  <br/> |<span data-ttu-id="1160f-124">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="1160f-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="1160f-125">URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1160f-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="1160f-126">serverID</span><span class="sxs-lookup"><span data-stu-id="1160f-126">serverID</span></span>  <br/> |<span data-ttu-id="1160f-127">int</span><span class="sxs-lookup"><span data-stu-id="1160f-127">int</span></span>  <br/> |<span data-ttu-id="1160f-128">Identità del server (come nella tabella tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="1160f-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="1160f-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="1160f-129">sessionId</span></span>  <br/> |<span data-ttu-id="1160f-130">bigint</span><span class="sxs-lookup"><span data-stu-id="1160f-130">bigint</span></span>  <br/> |<span data-ttu-id="1160f-p102">Sessione del server. Numero casuale generato a ogni avvio di un servizio chat, utilizzato per distinguere le sessioni allo scopo di identificare i partecipanti orfani.</span><span class="sxs-lookup"><span data-stu-id="1160f-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="1160f-134">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1160f-134">**Key**</span></span>

|<span data-ttu-id="1160f-135">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="1160f-135">**Column**</span></span>|<span data-ttu-id="1160f-136">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1160f-136">**Description**</span></span>|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |<span data-ttu-id="1160f-137">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="1160f-137">Primary key.</span></span>  <br/> |
   

