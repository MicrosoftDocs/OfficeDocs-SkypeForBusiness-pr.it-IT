---
title: Visualizzazione ConferenceMessageCount
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: La visualizzazione ConferenceMessageCount archivia le informazioni sul numero di messaggi inviati da un utente a una conferenza. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: a766e63fbca5c30cec3c3891c9ccfc2355f16d2d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815384"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="ac450-104">Visualizzazione ConferenceMessageCount</span><span class="sxs-lookup"><span data-stu-id="ac450-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="ac450-105">La visualizzazione ConferenceMessageCount archivia le informazioni sul numero di messaggi inviati da un utente a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="ac450-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="ac450-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ac450-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ac450-107">La visualizzazione ConferenceMessageCount contiene tutte le colonne della [visualizzazione ConferenceSessionDetails](conferencesessiondetails.md) , oltre alle colonne elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="ac450-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="ac450-108">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="ac450-108">**Column**</span></span>|<span data-ttu-id="ac450-109">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="ac450-109">**Data Type**</span></span>|<span data-ttu-id="ac450-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="ac450-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ac450-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="ac450-111">**UserUri**</span></span> <br/> |<span data-ttu-id="ac450-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ac450-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ac450-113">URI dell'utente che ha inviato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="ac450-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="ac450-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="ac450-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="ac450-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ac450-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ac450-116">Tipo di URI dell'utente che ha inviato i messaggi.</span><span class="sxs-lookup"><span data-stu-id="ac450-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="ac450-117">Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="ac450-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ac450-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="ac450-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="ac450-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="ac450-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="ac450-120">Tenant dell'utente che ha inviato i messaggi.</span><span class="sxs-lookup"><span data-stu-id="ac450-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="ac450-121">Per altre informazioni, vedere la [tabella tenant](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="ac450-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ac450-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="ac450-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="ac450-123">smallint</span><span class="sxs-lookup"><span data-stu-id="ac450-123">smallint</span></span>  <br/> |<span data-ttu-id="ac450-124">Numero di messaggi inviati dall'utente durante la sessione di conferenza.</span><span class="sxs-lookup"><span data-stu-id="ac450-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

