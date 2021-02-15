---
title: Visualizzazione utente
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: Nella Visualizzazione utente sono archiviate le informazioni relative agli utenti che hanno partecipato a chiamate o sessioni con record nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 03af849f9185d90d1c7888c1946b47ee2ef38db4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831696"
---
# <a name="user-view"></a><span data-ttu-id="a505f-104">Visualizzazione utente</span><span class="sxs-lookup"><span data-stu-id="a505f-104">User view</span></span>
 
<span data-ttu-id="a505f-105">Nella Visualizzazione utente sono archiviate le informazioni relative agli utenti che hanno partecipato a chiamate o sessioni con record nel database.</span><span class="sxs-lookup"><span data-stu-id="a505f-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="a505f-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a505f-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="a505f-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="a505f-107">**Column**</span></span>|<span data-ttu-id="a505f-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="a505f-108">**Data Type**</span></span>|<span data-ttu-id="a505f-109">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="a505f-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a505f-110">UserId</span><span class="sxs-lookup"><span data-stu-id="a505f-110">UserId</span></span>  <br/> |<span data-ttu-id="a505f-111">int</span><span class="sxs-lookup"><span data-stu-id="a505f-111">int</span></span>  <br/> |<span data-ttu-id="a505f-112">Numero univoco che identifica l'utente.</span><span class="sxs-lookup"><span data-stu-id="a505f-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="a505f-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="a505f-113">UserUri</span></span>  <br/> |<span data-ttu-id="a505f-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="a505f-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="a505f-115">Uri dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a505f-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="a505f-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="a505f-116">TenantKey</span></span>  <br/> |<span data-ttu-id="a505f-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="a505f-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="a505f-118">Tenant dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a505f-118">Tenant of user.</span></span> <span data-ttu-id="a505f-119">Per ulteriori [informazioni, vedere](tenants.md) la tabella Tenants.</span><span class="sxs-lookup"><span data-stu-id="a505f-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a505f-120">UriType</span><span class="sxs-lookup"><span data-stu-id="a505f-120">UriType</span></span>  <br/> |<span data-ttu-id="a505f-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a505f-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a505f-122">Tipo dell'URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a505f-122">Type of user URI.</span></span> <span data-ttu-id="a505f-123">Per altre [informazioni, vedi la tabella UriTypes.](uritypes.md)</span><span class="sxs-lookup"><span data-stu-id="a505f-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

