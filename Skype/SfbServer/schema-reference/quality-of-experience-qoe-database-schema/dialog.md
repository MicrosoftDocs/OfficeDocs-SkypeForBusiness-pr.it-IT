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
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: La tabella di finestra di dialogo è una tabella di supporto; ogni record rappresenta una finestra di dialogo SIP (Session Initiation Protocol).
ms.openlocfilehash: e6bbaa3c40ebf53c5fd9fc410acca7779128bf39
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194622"
---
# <a name="dialog-table"></a><span data-ttu-id="d9b91-103">Tabella Dialog</span><span class="sxs-lookup"><span data-stu-id="d9b91-103">Dialog table</span></span>
 
<span data-ttu-id="d9b91-104">La tabella di finestra di dialogo è una tabella di supporto; ogni record rappresenta una finestra di dialogo SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="d9b91-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="d9b91-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="d9b91-105">**Column**</span></span>|<span data-ttu-id="d9b91-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="d9b91-106">**Data Type**</span></span>|<span data-ttu-id="d9b91-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="d9b91-107">**Key/Index**</span></span>|<span data-ttu-id="d9b91-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="d9b91-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d9b91-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="d9b91-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="d9b91-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="d9b91-110">datetime</span></span>  <br/> |<span data-ttu-id="d9b91-111">Principale</span><span class="sxs-lookup"><span data-stu-id="d9b91-111">Primary</span></span>  <br/> |<span data-ttu-id="d9b91-112">Ora in cui l'agente QoE (Quality of Excellence) riceve il primo report da chiamante o chiamato.</span><span class="sxs-lookup"><span data-stu-id="d9b91-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="d9b91-113">Usato in combinazione con SessionSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="d9b91-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="d9b91-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="d9b91-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="d9b91-115">int</span><span class="sxs-lookup"><span data-stu-id="d9b91-115">int</span></span>  <br/> |<span data-ttu-id="d9b91-116">Principale</span><span class="sxs-lookup"><span data-stu-id="d9b91-116">Primary</span></span>  <br/> |<span data-ttu-id="d9b91-117">Numero di sequenza per distinguere le sessioni quando hanno lo stesso ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="d9b91-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="d9b91-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="d9b91-118">**DialogID**</span></span> <br/> |<span data-ttu-id="d9b91-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d9b91-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="d9b91-120">ID finestra di dialogo univoco globale.</span><span class="sxs-lookup"><span data-stu-id="d9b91-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="d9b91-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="d9b91-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="d9b91-122">int</span><span class="sxs-lookup"><span data-stu-id="d9b91-122">int</span></span>  <br/> |<span data-ttu-id="d9b91-123">Indice</span><span class="sxs-lookup"><span data-stu-id="d9b91-123">index</span></span>  <br/> |<span data-ttu-id="d9b91-124">Checksum dell'ID della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="d9b91-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

