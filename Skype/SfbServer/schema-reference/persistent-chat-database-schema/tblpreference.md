---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contiene le preferenze client degli utenti. Questa operazione viene in genere usata dai client precedenti a Lync 2013.
ms.openlocfilehash: 426a9f6aebe6cc6e510e2a75093b9210d3a0ba46
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814554"
---
# <a name="tblpreference"></a><span data-ttu-id="6e037-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="6e037-104">tblPreference</span></span>

<span data-ttu-id="6e037-105">tblPreference contiene le preferenze client degli utenti.</span><span class="sxs-lookup"><span data-stu-id="6e037-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="6e037-106">Questa operazione viene in genere usata dai client precedenti a Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6e037-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="6e037-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="6e037-107">**Columns**</span></span>


| <span data-ttu-id="6e037-108">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="6e037-108">**Column**</span></span>            | <span data-ttu-id="6e037-109">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6e037-109">**Type**</span></span>                        | <span data-ttu-id="6e037-110">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6e037-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="6e037-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="6e037-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="6e037-112">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="6e037-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="6e037-113">Etichetta con un formato, ad esempio \<: URI SIP utente\></span><span class="sxs-lookup"><span data-stu-id="6e037-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="6e037-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="6e037-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="6e037-115">int, not null</span><span class="sxs-lookup"><span data-stu-id="6e037-115">int, not null</span></span>  <br/>            | <span data-ttu-id="6e037-116">Un numero sequenziale (per etichetta) per scopi di controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="6e037-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="6e037-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="6e037-117">prefContent</span></span>  <br/>    | <span data-ttu-id="6e037-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="6e037-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="6e037-119">Contenuto codificato.</span><span class="sxs-lookup"><span data-stu-id="6e037-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="6e037-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="6e037-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="6e037-121">int, not null</span><span class="sxs-lookup"><span data-stu-id="6e037-121">int, not null</span></span>  <br/>            | <span data-ttu-id="6e037-122">ID dell'entità che ha aggiornato la preferenza.</span><span class="sxs-lookup"><span data-stu-id="6e037-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="6e037-123">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="6e037-123">**Key**</span></span>

|<span data-ttu-id="6e037-124">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="6e037-124">**Column**</span></span>|<span data-ttu-id="6e037-125">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6e037-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6e037-126">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="6e037-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="6e037-127">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="6e037-127">Primary key.</span></span>  <br/> |


