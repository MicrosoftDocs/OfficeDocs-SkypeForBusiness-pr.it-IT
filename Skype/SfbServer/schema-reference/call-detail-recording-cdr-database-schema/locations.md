---
title: Tabella Locations in Skype for Business Server 2015
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
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Ogni record rappresenta un riferimento di posizione in una chiamata di emergenza, ad esempio in una chiamata al servizio 118.
ms.openlocfilehash: b177e79217f8586d7655b2a4645a603bd8e2f97f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821516"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="23a7d-103">Tabella Locations in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="23a7d-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="23a7d-104">Ogni record rappresenta un riferimento di posizione in una chiamata di emergenza, ad esempio in una chiamata al servizio 118.</span><span class="sxs-lookup"><span data-stu-id="23a7d-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="23a7d-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="23a7d-105">**Column**</span></span>|<span data-ttu-id="23a7d-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="23a7d-106">**Data Type**</span></span>|<span data-ttu-id="23a7d-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="23a7d-107">**Key/Index**</span></span>|<span data-ttu-id="23a7d-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="23a7d-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="23a7d-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="23a7d-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="23a7d-110">datetime</span><span class="sxs-lookup"><span data-stu-id="23a7d-110">datetime</span></span>  <br/> |<span data-ttu-id="23a7d-111">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="23a7d-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="23a7d-112">Data e ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="23a7d-112">Time of session request.</span></span> <span data-ttu-id="23a7d-113">Valore utilizzato insieme a **SessionIdSeq** per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="23a7d-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="23a7d-114">Per ulteriori informazioni, vedere la tabella [Dialogs in Skype for Business Server 2015.](dialogs.md)</span><span class="sxs-lookup"><span data-stu-id="23a7d-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="23a7d-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="23a7d-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="23a7d-116">int</span><span class="sxs-lookup"><span data-stu-id="23a7d-116">int</span></span>  <br/> |<span data-ttu-id="23a7d-117">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="23a7d-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="23a7d-118">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="23a7d-118">ID number to identify the session.</span></span> <span data-ttu-id="23a7d-119">Valore utilizzato insieme a **SessionIdTime** per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="23a7d-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="23a7d-120">Per ulteriori informazioni, vedere la tabella [Dialogs in Skype for Business Server 2015.](dialogs.md)</span><span class="sxs-lookup"><span data-stu-id="23a7d-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="23a7d-121">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="23a7d-121">**Location**</span></span> <br/> |<span data-ttu-id="23a7d-122">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="23a7d-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="23a7d-123">Posizione della chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="23a7d-123">Location of emergency call.</span></span>  <br/> |
   

