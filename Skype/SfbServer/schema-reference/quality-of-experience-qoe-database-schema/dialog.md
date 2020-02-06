---
title: Tabella Dialog
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: La tabella di finestra di dialogo è una tabella di supporto; ogni record rappresenta una finestra di dialogo SIP (Session Initiation Protocol).
ms.openlocfilehash: 85d4a9f16a88db386565c065161eedeb61fba913
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809534"
---
# <a name="dialog-table"></a><span data-ttu-id="d5f53-103">Tabella Dialog</span><span class="sxs-lookup"><span data-stu-id="d5f53-103">Dialog table</span></span>
 
<span data-ttu-id="d5f53-104">La tabella di finestra di dialogo è una tabella di supporto; ogni record rappresenta una finestra di dialogo SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="d5f53-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="d5f53-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="d5f53-105">**Column**</span></span>|<span data-ttu-id="d5f53-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="d5f53-106">**Data Type**</span></span>|<span data-ttu-id="d5f53-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="d5f53-107">**Key/Index**</span></span>|<span data-ttu-id="d5f53-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="d5f53-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d5f53-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="d5f53-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="d5f53-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="d5f53-110">datetime</span></span>  <br/> |<span data-ttu-id="d5f53-111">Principale</span><span class="sxs-lookup"><span data-stu-id="d5f53-111">Primary</span></span>  <br/> |<span data-ttu-id="d5f53-112">Ora in cui l'agente QoE (Quality of Excellence) riceve il primo report da chiamante o chiamato.</span><span class="sxs-lookup"><span data-stu-id="d5f53-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="d5f53-113">Usato in combinazione con SessionSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="d5f53-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="d5f53-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="d5f53-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="d5f53-115">int</span><span class="sxs-lookup"><span data-stu-id="d5f53-115">int</span></span>  <br/> |<span data-ttu-id="d5f53-116">Principale</span><span class="sxs-lookup"><span data-stu-id="d5f53-116">Primary</span></span>  <br/> |<span data-ttu-id="d5f53-117">Numero di sequenza per distinguere le sessioni quando hanno lo stesso ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="d5f53-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="d5f53-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="d5f53-118">**DialogID**</span></span> <br/> |<span data-ttu-id="d5f53-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d5f53-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="d5f53-120">ID finestra di dialogo univoco globale.</span><span class="sxs-lookup"><span data-stu-id="d5f53-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="d5f53-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="d5f53-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="d5f53-122">int</span><span class="sxs-lookup"><span data-stu-id="d5f53-122">int</span></span>  <br/> |<span data-ttu-id="d5f53-123">Indice</span><span class="sxs-lookup"><span data-stu-id="d5f53-123">index</span></span>  <br/> |<span data-ttu-id="d5f53-124">Checksum dell'ID della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="d5f53-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

