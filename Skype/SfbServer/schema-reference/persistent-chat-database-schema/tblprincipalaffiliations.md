---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contiene le principali affiliazioni che descrivono le appartenenze in posizioni, inclusi i gruppi di sicurezza dei servizi di dominio Active Directory, in contenitori di Active Directory in domini.
ms.openlocfilehash: 542bcc333d815b0577aec1fb11d4070540150d3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814474"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="90a7b-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="90a7b-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="90a7b-104">tblPrincipalAffiliations contiene le principali affiliazioni che descrivono le appartenenze in posizioni, inclusi i gruppi di sicurezza dei servizi di dominio Active Directory, in contenitori di Active Directory in domini.</span><span class="sxs-lookup"><span data-stu-id="90a7b-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="90a7b-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="90a7b-105">**Columns**</span></span>

|<span data-ttu-id="90a7b-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="90a7b-106">**Column**</span></span>|<span data-ttu-id="90a7b-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="90a7b-107">**Type**</span></span>|<span data-ttu-id="90a7b-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="90a7b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="90a7b-109">principalID</span><span class="sxs-lookup"><span data-stu-id="90a7b-109">principalID</span></span>  <br/> |<span data-ttu-id="90a7b-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="90a7b-110">int, not null</span></span>  <br/> |<span data-ttu-id="90a7b-111">ID dell'oggetto Principal affiliato.</span><span class="sxs-lookup"><span data-stu-id="90a7b-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="90a7b-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="90a7b-112">affiliationID</span></span>  <br/> |<span data-ttu-id="90a7b-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="90a7b-113">int, not null</span></span>  <br/> |<span data-ttu-id="90a7b-114">ID dell'entità che rappresenta l'affiliazione.</span><span class="sxs-lookup"><span data-stu-id="90a7b-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="90a7b-115">Ogni entità (ad eccezione di System-User-Types) ha anche una propria affiliazione.</span><span class="sxs-lookup"><span data-stu-id="90a7b-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="90a7b-116">Indice</span><span class="sxs-lookup"><span data-stu-id="90a7b-116">index</span></span>  <br/> |<span data-ttu-id="90a7b-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="90a7b-117">int, not null</span></span>  <br/> |<span data-ttu-id="90a7b-118">Indice.</span><span class="sxs-lookup"><span data-stu-id="90a7b-118">Index.</span></span> <span data-ttu-id="90a7b-119">Il valore di self-Affiliations è-1 e per le altre affiliazioni aumenta sequenzialmente da 1 all'interno di ogni \<PrincipalId, affiliationId\> bucket.</span><span class="sxs-lookup"><span data-stu-id="90a7b-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="90a7b-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="90a7b-120">updatedBy</span></span>  <br/> |<span data-ttu-id="90a7b-121">int, not null</span><span class="sxs-lookup"><span data-stu-id="90a7b-121">int, not null</span></span>  <br/> |<span data-ttu-id="90a7b-122">Principal che ha eseguito l'aggiornamento più recente.</span><span class="sxs-lookup"><span data-stu-id="90a7b-122">Principal that did the latest update.</span></span> <span data-ttu-id="90a7b-123">Si tratta in genere di 1, che indica la sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="90a7b-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="90a7b-124">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="90a7b-124">**Keys**</span></span>

|<span data-ttu-id="90a7b-125">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="90a7b-125">**Columns**</span></span>|<span data-ttu-id="90a7b-126">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="90a7b-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="90a7b-127">\<principalID, index, affiliationID\></span><span class="sxs-lookup"><span data-stu-id="90a7b-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="90a7b-128">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="90a7b-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="90a7b-129">principalID</span><span class="sxs-lookup"><span data-stu-id="90a7b-129">principalID</span></span>  <br/> |<span data-ttu-id="90a7b-130">Chiave esterna con ricerca nella tabella tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="90a7b-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="90a7b-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="90a7b-131">affiliationID</span></span>  <br/> |<span data-ttu-id="90a7b-132">Chiave esterna con ricerca nella tabella tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="90a7b-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

