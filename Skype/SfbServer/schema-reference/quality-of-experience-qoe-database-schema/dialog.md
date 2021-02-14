---
title: Tabella Dialog
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: La tabella Dialog è una tabella di supporto. Ogni record rappresenta un dialogo SIP (Session Initiation Protocol).
ms.openlocfilehash: 05d9519c9aef20b8c82d904a9d5718a4de8c092c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815846"
---
# <a name="dialog-table"></a><span data-ttu-id="00504-103">Tabella Dialog</span><span class="sxs-lookup"><span data-stu-id="00504-103">Dialog table</span></span>
 
<span data-ttu-id="00504-104">La tabella Dialog è una tabella di supporto. Ogni record rappresenta un dialogo SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="00504-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="00504-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="00504-105">**Column**</span></span>|<span data-ttu-id="00504-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="00504-106">**Data Type**</span></span>|<span data-ttu-id="00504-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="00504-107">**Key/Index**</span></span>|<span data-ttu-id="00504-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="00504-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="00504-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="00504-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="00504-110">datetime</span><span class="sxs-lookup"><span data-stu-id="00504-110">datetime</span></span>  <br/> |<span data-ttu-id="00504-111">Principale</span><span class="sxs-lookup"><span data-stu-id="00504-111">Primary</span></span>  <br/> |<span data-ttu-id="00504-p101">Data/ora in cui l'agente QoE (Quality of Experience) riceve il primo rapporto dal chiamante o dal destinatario della chiamata. Valore utilizzato in combinazione con SessionSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="00504-p101">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee. Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="00504-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="00504-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="00504-115">int</span><span class="sxs-lookup"><span data-stu-id="00504-115">int</span></span>  <br/> |<span data-ttu-id="00504-116">Principale</span><span class="sxs-lookup"><span data-stu-id="00504-116">Primary</span></span>  <br/> |<span data-ttu-id="00504-117">Numero sequenziale per distinguere le sessioni con valore ConferenceDateTime identico.</span><span class="sxs-lookup"><span data-stu-id="00504-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="00504-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="00504-118">**DialogID**</span></span> <br/> |<span data-ttu-id="00504-119">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="00504-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="00504-120">ID del dialogo globalmente univoco.</span><span class="sxs-lookup"><span data-stu-id="00504-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="00504-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="00504-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="00504-122">int</span><span class="sxs-lookup"><span data-stu-id="00504-122">int</span></span>  <br/> |<span data-ttu-id="00504-123">index</span><span class="sxs-lookup"><span data-stu-id="00504-123">index</span></span>  <br/> |<span data-ttu-id="00504-124">Checksum dell'ID del dialogo.</span><span class="sxs-lookup"><span data-stu-id="00504-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

