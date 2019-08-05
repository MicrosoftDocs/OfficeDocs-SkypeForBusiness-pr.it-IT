---
title: Tabella Locations in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Ogni record rappresenta un riferimento di posizione in una chiamata di emergenza, ad esempio una chiamata E9-1-1.
ms.openlocfilehash: 28054419187b8f23348396f52ec147b06eee2136
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194786"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="7080b-103">Tabella Locations in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7080b-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7080b-104">Ogni record rappresenta un riferimento di posizione in una chiamata di emergenza, ad esempio una chiamata E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="7080b-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="7080b-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="7080b-105">**Column**</span></span>|<span data-ttu-id="7080b-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="7080b-106">**Data Type**</span></span>|<span data-ttu-id="7080b-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="7080b-107">**Key/Index**</span></span>|<span data-ttu-id="7080b-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="7080b-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7080b-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="7080b-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="7080b-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="7080b-110">datetime</span></span>  <br/> |<span data-ttu-id="7080b-111">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="7080b-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="7080b-112">Ora della richiesta della sessione.</span><span class="sxs-lookup"><span data-stu-id="7080b-112">Time of session request.</span></span> <span data-ttu-id="7080b-113">Usato in combinazione con **SessionIdSeq** per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="7080b-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="7080b-114">Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) .</span><span class="sxs-lookup"><span data-stu-id="7080b-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="7080b-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="7080b-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="7080b-116">int</span><span class="sxs-lookup"><span data-stu-id="7080b-116">int</span></span>  <br/> |<span data-ttu-id="7080b-117">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="7080b-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="7080b-118">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="7080b-118">ID number to identify the session.</span></span> <span data-ttu-id="7080b-119">Usato in combinazione con **SessionIdTime** per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="7080b-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="7080b-120">Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) .</span><span class="sxs-lookup"><span data-stu-id="7080b-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="7080b-121">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="7080b-121">**Location**</span></span> <br/> |<span data-ttu-id="7080b-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="7080b-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="7080b-123">Posizione della chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="7080b-123">Location of emergency call.</span></span>  <br/> |
   

