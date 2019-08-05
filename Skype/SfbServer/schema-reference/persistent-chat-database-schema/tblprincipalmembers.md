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
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contiene le appartenenze principali.
ms.openlocfilehash: 12c3bf86b7416665f0f2355af0bfc9f98e3c1f1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194662"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="766a9-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="766a9-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="766a9-104">tblPrincipalMembers contiene le appartenenze principali.</span><span class="sxs-lookup"><span data-stu-id="766a9-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="766a9-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="766a9-105">**Columns**</span></span>

|<span data-ttu-id="766a9-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="766a9-106">**Column**</span></span>|<span data-ttu-id="766a9-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="766a9-107">**Type**</span></span>|<span data-ttu-id="766a9-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="766a9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="766a9-109">prinID</span><span class="sxs-lookup"><span data-stu-id="766a9-109">prinID</span></span>  <br/> |<span data-ttu-id="766a9-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="766a9-110">int, not null</span></span>  <br/> |<span data-ttu-id="766a9-111">ID entità.</span><span class="sxs-lookup"><span data-stu-id="766a9-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="766a9-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="766a9-112">memberADPath</span></span>  <br/> |<span data-ttu-id="766a9-113">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="766a9-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="766a9-114">Nome distinto di un membro.</span><span class="sxs-lookup"><span data-stu-id="766a9-114">Distinguished name of a member.</span></span> <span data-ttu-id="766a9-115">Un membro non deve essere un oggetto Principal (nella tabella tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="766a9-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="766a9-116">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="766a9-116">**Keys**</span></span>

|<span data-ttu-id="766a9-117">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="766a9-117">**Column**</span></span>|<span data-ttu-id="766a9-118">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="766a9-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="766a9-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="766a9-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="766a9-120">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="766a9-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="766a9-121">prinID</span><span class="sxs-lookup"><span data-stu-id="766a9-121">prinID</span></span>  <br/> |<span data-ttu-id="766a9-122">Chiave esterna con ricerca in tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="766a9-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

