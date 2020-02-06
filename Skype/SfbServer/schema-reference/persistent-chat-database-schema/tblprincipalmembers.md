---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contiene le appartenenze principali.
ms.openlocfilehash: c56ab16f96322cb295c4eff6fc63e01ba887dd22
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813944"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="90f00-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="90f00-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="90f00-104">tblPrincipalMembers contiene le appartenenze principali.</span><span class="sxs-lookup"><span data-stu-id="90f00-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="90f00-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="90f00-105">**Columns**</span></span>

|<span data-ttu-id="90f00-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="90f00-106">**Column**</span></span>|<span data-ttu-id="90f00-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="90f00-107">**Type**</span></span>|<span data-ttu-id="90f00-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="90f00-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="90f00-109">prinID</span><span class="sxs-lookup"><span data-stu-id="90f00-109">prinID</span></span>  <br/> |<span data-ttu-id="90f00-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="90f00-110">int, not null</span></span>  <br/> |<span data-ttu-id="90f00-111">ID entità.</span><span class="sxs-lookup"><span data-stu-id="90f00-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="90f00-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="90f00-112">memberADPath</span></span>  <br/> |<span data-ttu-id="90f00-113">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="90f00-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="90f00-114">Nome distinto di un membro.</span><span class="sxs-lookup"><span data-stu-id="90f00-114">Distinguished name of a member.</span></span> <span data-ttu-id="90f00-115">Un membro non deve essere un oggetto Principal (nella tabella tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="90f00-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="90f00-116">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="90f00-116">**Keys**</span></span>

|<span data-ttu-id="90f00-117">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="90f00-117">**Column**</span></span>|<span data-ttu-id="90f00-118">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="90f00-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="90f00-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="90f00-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="90f00-120">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="90f00-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="90f00-121">prinID</span><span class="sxs-lookup"><span data-stu-id="90f00-121">prinID</span></span>  <br/> |<span data-ttu-id="90f00-122">Chiave esterna con ricerca in tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="90f00-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

