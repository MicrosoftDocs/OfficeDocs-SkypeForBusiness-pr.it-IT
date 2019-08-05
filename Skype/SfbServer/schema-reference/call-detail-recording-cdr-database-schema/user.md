---
title: Visualizzazione utente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: La visualizzazione utente archivia le informazioni sugli utenti che hanno partecipato a chiamate o sessioni che hanno record nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 2fe0ba4748a776a8f17065a3c5db21d34bd6340d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194730"
---
# <a name="user-view"></a><span data-ttu-id="79399-104">Visualizzazione utente</span><span class="sxs-lookup"><span data-stu-id="79399-104">User view</span></span>
 
<span data-ttu-id="79399-105">La visualizzazione utente archivia le informazioni sugli utenti che hanno partecipato a chiamate o sessioni che hanno record nel database.</span><span class="sxs-lookup"><span data-stu-id="79399-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="79399-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79399-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="79399-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="79399-107">**Column**</span></span>|<span data-ttu-id="79399-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="79399-108">**Data Type**</span></span>|<span data-ttu-id="79399-109">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="79399-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="79399-110">UserId</span><span class="sxs-lookup"><span data-stu-id="79399-110">UserId</span></span>  <br/> |<span data-ttu-id="79399-111">int</span><span class="sxs-lookup"><span data-stu-id="79399-111">int</span></span>  <br/> |<span data-ttu-id="79399-112">Numero univoco che identifica questo utente.</span><span class="sxs-lookup"><span data-stu-id="79399-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="79399-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="79399-113">UserUri</span></span>  <br/> |<span data-ttu-id="79399-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="79399-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="79399-115">URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="79399-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="79399-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="79399-116">TenantKey</span></span>  <br/> |<span data-ttu-id="79399-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="79399-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="79399-118">Tenant dell'utente.</span><span class="sxs-lookup"><span data-stu-id="79399-118">Tenant of user.</span></span> <span data-ttu-id="79399-119">Per altre informazioni, vedere la [tabella tenant](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="79399-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="79399-120">UriType</span><span class="sxs-lookup"><span data-stu-id="79399-120">UriType</span></span>  <br/> |<span data-ttu-id="79399-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="79399-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="79399-122">Tipo di URI utente.</span><span class="sxs-lookup"><span data-stu-id="79399-122">Type of user URI.</span></span> <span data-ttu-id="79399-123">Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="79399-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

