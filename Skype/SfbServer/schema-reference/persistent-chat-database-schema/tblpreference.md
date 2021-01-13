---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contiene le preferenze client degli utenti. Questo è in genere utilizzato dai client precedenti a Lync 2013.
ms.openlocfilehash: 96cd017dd67a05f3240269f5bdcbd23f30fffd28
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815906"
---
# <a name="tblpreference"></a><span data-ttu-id="8f0dc-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="8f0dc-104">tblPreference</span></span>

<span data-ttu-id="8f0dc-105">tblPreference contiene le preferenze client degli utenti.</span><span class="sxs-lookup"><span data-stu-id="8f0dc-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="8f0dc-106">Questo è in genere utilizzato dai client precedenti a Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8f0dc-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="8f0dc-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="8f0dc-107">**Columns**</span></span>


| <span data-ttu-id="8f0dc-108">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="8f0dc-108">**Column**</span></span>            | <span data-ttu-id="8f0dc-109">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8f0dc-109">**Type**</span></span>                        | <span data-ttu-id="8f0dc-110">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="8f0dc-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="8f0dc-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="8f0dc-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="8f0dc-112">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="8f0dc-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="8f0dc-113">Etichetta con un formato, ad esempio: \<user sip uri\></span><span class="sxs-lookup"><span data-stu-id="8f0dc-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="8f0dc-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="8f0dc-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="8f0dc-115">int, not null</span><span class="sxs-lookup"><span data-stu-id="8f0dc-115">int, not null</span></span>  <br/>            | <span data-ttu-id="8f0dc-116">Un numero sequenziale (per etichetta) per scopi di controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="8f0dc-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="8f0dc-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="8f0dc-117">prefContent</span></span>  <br/>    | <span data-ttu-id="8f0dc-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="8f0dc-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="8f0dc-119">Contenuto codificato.</span><span class="sxs-lookup"><span data-stu-id="8f0dc-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="8f0dc-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="8f0dc-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="8f0dc-121">int, not null</span><span class="sxs-lookup"><span data-stu-id="8f0dc-121">int, not null</span></span>  <br/>            | <span data-ttu-id="8f0dc-122">ID dell'entità che ha aggiornato la preferenza.</span><span class="sxs-lookup"><span data-stu-id="8f0dc-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="8f0dc-123">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="8f0dc-123">**Key**</span></span>

|<span data-ttu-id="8f0dc-124">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="8f0dc-124">**Column**</span></span>|<span data-ttu-id="8f0dc-125">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="8f0dc-125">**Description**</span></span>|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |<span data-ttu-id="8f0dc-126">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="8f0dc-126">Primary key.</span></span>  <br/> |


