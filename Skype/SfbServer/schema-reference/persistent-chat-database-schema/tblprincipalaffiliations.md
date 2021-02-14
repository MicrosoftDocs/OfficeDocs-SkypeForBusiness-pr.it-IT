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
description: tblPrincipalAffiliations contiene le affiliazioni principali che descrivono le appartenenze ai percorsi, inclusi i gruppi di sicurezza di Servizi di dominio Active Directory, nei contenitori di Active Directory e nei domini.
ms.openlocfilehash: 149bb1b4603fa0f0e1909298659b881000464275
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815866"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="36e3c-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="36e3c-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="36e3c-104">tblPrincipalAffiliations contiene le affiliazioni principali che descrivono le appartenenze ai percorsi, inclusi i gruppi di sicurezza di Servizi di dominio Active Directory, nei contenitori di Active Directory e nei domini.</span><span class="sxs-lookup"><span data-stu-id="36e3c-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="36e3c-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="36e3c-105">**Columns**</span></span>

|<span data-ttu-id="36e3c-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="36e3c-106">**Column**</span></span>|<span data-ttu-id="36e3c-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="36e3c-107">**Type**</span></span>|<span data-ttu-id="36e3c-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="36e3c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="36e3c-109">principalID</span><span class="sxs-lookup"><span data-stu-id="36e3c-109">principalID</span></span>  <br/> |<span data-ttu-id="36e3c-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="36e3c-110">int, not null</span></span>  <br/> |<span data-ttu-id="36e3c-111">ID dell'entità affiliata.</span><span class="sxs-lookup"><span data-stu-id="36e3c-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="36e3c-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="36e3c-112">affiliationID</span></span>  <br/> |<span data-ttu-id="36e3c-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="36e3c-113">int, not null</span></span>  <br/> |<span data-ttu-id="36e3c-p101">ID dell'entità che rappresenta l'affiliazione. Ogni entità prevede anche un'auto-affiliazione (eccetto system-user-types).</span><span class="sxs-lookup"><span data-stu-id="36e3c-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="36e3c-116">index</span><span class="sxs-lookup"><span data-stu-id="36e3c-116">index</span></span>  <br/> |<span data-ttu-id="36e3c-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="36e3c-117">int, not null</span></span>  <br/> |<span data-ttu-id="36e3c-118">Indice.</span><span class="sxs-lookup"><span data-stu-id="36e3c-118">Index.</span></span> <span data-ttu-id="36e3c-119">Il valore per le auto-affiliazioni è -1 e per le altre affiliazioni aumenta in sequenza da 1 all'interno di ogni \<principalID, affiliationId\> contenitore.</span><span class="sxs-lookup"><span data-stu-id="36e3c-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="36e3c-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="36e3c-120">updatedBy</span></span>  <br/> |<span data-ttu-id="36e3c-121">int, not null</span><span class="sxs-lookup"><span data-stu-id="36e3c-121">int, not null</span></span>  <br/> |<span data-ttu-id="36e3c-p103">Entità che ha effettuato l'ultimo aggiornamento. Viene utilizzato in genere il valore 1, che indica la sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="36e3c-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="36e3c-124">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="36e3c-124">**Keys**</span></span>

|<span data-ttu-id="36e3c-125">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="36e3c-125">**Columns**</span></span>|<span data-ttu-id="36e3c-126">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="36e3c-126">**Description**</span></span>|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |<span data-ttu-id="36e3c-127">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="36e3c-127">Primary key.</span></span>  <br/> |
|<span data-ttu-id="36e3c-128">principalID</span><span class="sxs-lookup"><span data-stu-id="36e3c-128">principalID</span></span>  <br/> |<span data-ttu-id="36e3c-129">Chiave esterna con ricerca nella tabella tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="36e3c-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="36e3c-130">affiliationID</span><span class="sxs-lookup"><span data-stu-id="36e3c-130">affiliationID</span></span>  <br/> |<span data-ttu-id="36e3c-131">Chiave esterna con ricerca nella tabella tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="36e3c-131">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

