---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contiene le affiliazioni principali che descrivono le appartenenze nelle posizioni, inclusi i gruppi di sicurezza di servizi di dominio Active Directory, in contenitori di Active Directory, in domini.
ms.openlocfilehash: 149bb1b4603fa0f0e1909298659b881000464275
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815866"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="16e7a-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="16e7a-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="16e7a-104">tblPrincipalAffiliations contiene le affiliazioni principali che descrivono le appartenenze nelle posizioni, inclusi i gruppi di sicurezza di servizi di dominio Active Directory, in contenitori di Active Directory, in domini.</span><span class="sxs-lookup"><span data-stu-id="16e7a-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="16e7a-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="16e7a-105">**Columns**</span></span>

|<span data-ttu-id="16e7a-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="16e7a-106">**Column**</span></span>|<span data-ttu-id="16e7a-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="16e7a-107">**Type**</span></span>|<span data-ttu-id="16e7a-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="16e7a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="16e7a-109">principalID</span><span class="sxs-lookup"><span data-stu-id="16e7a-109">principalID</span></span>  <br/> |<span data-ttu-id="16e7a-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="16e7a-110">int, not null</span></span>  <br/> |<span data-ttu-id="16e7a-111">ID dell'entità affiliata.</span><span class="sxs-lookup"><span data-stu-id="16e7a-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="16e7a-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="16e7a-112">affiliationID</span></span>  <br/> |<span data-ttu-id="16e7a-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="16e7a-113">int, not null</span></span>  <br/> |<span data-ttu-id="16e7a-p101">ID dell'entità che rappresenta l'affiliazione. Ogni entità prevede anche un'auto-affiliazione (eccetto system-user-types).</span><span class="sxs-lookup"><span data-stu-id="16e7a-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="16e7a-116">Indice</span><span class="sxs-lookup"><span data-stu-id="16e7a-116">index</span></span>  <br/> |<span data-ttu-id="16e7a-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="16e7a-117">int, not null</span></span>  <br/> |<span data-ttu-id="16e7a-118">Indice.</span><span class="sxs-lookup"><span data-stu-id="16e7a-118">Index.</span></span> <span data-ttu-id="16e7a-119">Il valore di self-Affiliates è-1 e per le altre affiliazioni aumenta sequenzialmente da 1 all'interno di ogni \<principalID, affiliationId\> bucket.</span><span class="sxs-lookup"><span data-stu-id="16e7a-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="16e7a-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="16e7a-120">updatedBy</span></span>  <br/> |<span data-ttu-id="16e7a-121">int, not null</span><span class="sxs-lookup"><span data-stu-id="16e7a-121">int, not null</span></span>  <br/> |<span data-ttu-id="16e7a-p103">Entità che ha effettuato l'ultimo aggiornamento. Viene utilizzato in genere il valore 1, che indica la sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="16e7a-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="16e7a-124">**Chiavi**</span><span class="sxs-lookup"><span data-stu-id="16e7a-124">**Keys**</span></span>

|<span data-ttu-id="16e7a-125">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="16e7a-125">**Columns**</span></span>|<span data-ttu-id="16e7a-126">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="16e7a-126">**Description**</span></span>|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |<span data-ttu-id="16e7a-127">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="16e7a-127">Primary key.</span></span>  <br/> |
|<span data-ttu-id="16e7a-128">principalID</span><span class="sxs-lookup"><span data-stu-id="16e7a-128">principalID</span></span>  <br/> |<span data-ttu-id="16e7a-129">Chiave esterna con ricerca nella tabella tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="16e7a-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="16e7a-130">affiliationID</span><span class="sxs-lookup"><span data-stu-id="16e7a-130">affiliationID</span></span>  <br/> |<span data-ttu-id="16e7a-131">Chiave esterna con ricerca nella tabella tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="16e7a-131">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

