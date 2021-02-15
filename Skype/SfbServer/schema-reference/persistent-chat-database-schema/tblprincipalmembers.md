---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: Nella tabella tblPrincipalMembers sono contenute le appartenenze principali.
ms.openlocfilehash: 93a012ea82acf071a28752eb79682866c0faa418
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831596"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="571e3-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="571e3-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="571e3-104">Nella tabella tblPrincipalMembers sono contenute le appartenenze principali.</span><span class="sxs-lookup"><span data-stu-id="571e3-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="571e3-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="571e3-105">**Columns**</span></span>

|<span data-ttu-id="571e3-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="571e3-106">**Column**</span></span>|<span data-ttu-id="571e3-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="571e3-107">**Type**</span></span>|<span data-ttu-id="571e3-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="571e3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="571e3-109">prinID</span><span class="sxs-lookup"><span data-stu-id="571e3-109">prinID</span></span>  <br/> |<span data-ttu-id="571e3-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="571e3-110">int, not null</span></span>  <br/> |<span data-ttu-id="571e3-111">ID dell'entità.</span><span class="sxs-lookup"><span data-stu-id="571e3-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="571e3-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="571e3-112">memberADPath</span></span>  <br/> |<span data-ttu-id="571e3-113">nvarchar (384), non null</span><span class="sxs-lookup"><span data-stu-id="571e3-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="571e3-p101">Nome distinto di un membro. Non è necessario che un membro sia un'entità (nella tabella tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="571e3-p101">Distinguished name of a member. A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="571e3-116">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="571e3-116">**Keys**</span></span>

|<span data-ttu-id="571e3-117">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="571e3-117">**Column**</span></span>|<span data-ttu-id="571e3-118">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="571e3-118">**Description**</span></span>|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |<span data-ttu-id="571e3-119">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="571e3-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="571e3-120">prinID</span><span class="sxs-lookup"><span data-stu-id="571e3-120">prinID</span></span>  <br/> |<span data-ttu-id="571e3-121">Chiave esterna con ricerca nella tabella tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="571e3-121">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

