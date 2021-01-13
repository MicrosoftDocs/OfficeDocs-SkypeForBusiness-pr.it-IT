---
title: Visualizzazione ConferenceMessageCount
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: La vista ConferenceMessageCount archivia informazioni sul numero di messaggi inviati da un utente a una conferenza. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 8394ed37d4b85e8ec5fcda4234b4c28f4276fb17
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813296"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="2100e-104">Visualizzazione ConferenceMessageCount</span><span class="sxs-lookup"><span data-stu-id="2100e-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="2100e-105">La vista ConferenceMessageCount archivia informazioni sul numero di messaggi inviati da un utente a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="2100e-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="2100e-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2100e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2100e-107">La visualizzazione ConferenceMessageCount contiene tutte le colonne della [visualizzazione ConferenceSessionDetails](conferencesessiondetails.md) , oltre alle colonne elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="2100e-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="2100e-108">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="2100e-108">**Column**</span></span>|<span data-ttu-id="2100e-109">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="2100e-109">**Data Type**</span></span>|<span data-ttu-id="2100e-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="2100e-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2100e-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="2100e-111">**UserUri**</span></span> <br/> |<span data-ttu-id="2100e-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2100e-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="2100e-113">URI dell'utente che ha inviato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="2100e-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="2100e-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="2100e-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="2100e-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2100e-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="2100e-116">Tipo di URI dell'utente che ha inviato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="2100e-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="2100e-117">Per ulteriori informazioni, vedere la [tabella UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="2100e-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="2100e-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="2100e-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="2100e-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="2100e-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="2100e-120">Tenant dell'utente che ha inviato i messaggi.</span><span class="sxs-lookup"><span data-stu-id="2100e-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="2100e-121">Per ulteriori informazioni, vedere la [tabella tenant](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="2100e-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="2100e-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="2100e-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="2100e-123">smallint</span><span class="sxs-lookup"><span data-stu-id="2100e-123">smallint</span></span>  <br/> |<span data-ttu-id="2100e-124">Numero di messaggi inviati dall'utente durante la sessione di conferenza.</span><span class="sxs-lookup"><span data-stu-id="2100e-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

