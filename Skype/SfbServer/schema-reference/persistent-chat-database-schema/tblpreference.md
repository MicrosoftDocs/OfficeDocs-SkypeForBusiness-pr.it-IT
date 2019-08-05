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
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contiene le preferenze client degli utenti. Questa operazione viene in genere usata dai client precedenti a Lync 2013.
ms.openlocfilehash: b646bbe65c8090295c070a4fdc88b8339a62e4ab
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194675"
---
# <a name="tblpreference"></a><span data-ttu-id="d8afa-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="d8afa-104">tblPreference</span></span>

<span data-ttu-id="d8afa-105">tblPreference contiene le preferenze client degli utenti.</span><span class="sxs-lookup"><span data-stu-id="d8afa-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="d8afa-106">Questa operazione viene in genere usata dai client precedenti a Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d8afa-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="d8afa-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d8afa-107">**Columns**</span></span>


| <span data-ttu-id="d8afa-108">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="d8afa-108">**Column**</span></span>            | <span data-ttu-id="d8afa-109">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d8afa-109">**Type**</span></span>                        | <span data-ttu-id="d8afa-110">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d8afa-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="d8afa-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="d8afa-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="d8afa-112">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="d8afa-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="d8afa-113">Etichetta con un formato, ad esempio \<: URI SIP utente\></span><span class="sxs-lookup"><span data-stu-id="d8afa-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="d8afa-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="d8afa-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="d8afa-115">int, not null</span><span class="sxs-lookup"><span data-stu-id="d8afa-115">int, not null</span></span>  <br/>            | <span data-ttu-id="d8afa-116">Un numero sequenziale (per etichetta) per scopi di controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="d8afa-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="d8afa-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="d8afa-117">prefContent</span></span>  <br/>    | <span data-ttu-id="d8afa-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="d8afa-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="d8afa-119">Contenuto codificato.</span><span class="sxs-lookup"><span data-stu-id="d8afa-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="d8afa-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="d8afa-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="d8afa-121">int, not null</span><span class="sxs-lookup"><span data-stu-id="d8afa-121">int, not null</span></span>  <br/>            | <span data-ttu-id="d8afa-122">ID dell'entità che ha aggiornato la preferenza.</span><span class="sxs-lookup"><span data-stu-id="d8afa-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="d8afa-123">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="d8afa-123">**Key**</span></span>

|<span data-ttu-id="d8afa-124">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="d8afa-124">**Column**</span></span>|<span data-ttu-id="d8afa-125">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d8afa-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d8afa-126">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="d8afa-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="d8afa-127">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="d8afa-127">Primary key.</span></span>  <br/> |


