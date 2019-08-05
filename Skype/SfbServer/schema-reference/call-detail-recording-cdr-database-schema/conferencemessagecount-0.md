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
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: La visualizzazione ConferenceMessageCount archivia le informazioni sul numero di messaggi inviati da un utente a una conferenza. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 890a5912c6f828f614fbff89627c94c4e12ba7e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194840"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="761b0-104">Visualizzazione ConferenceMessageCount</span><span class="sxs-lookup"><span data-stu-id="761b0-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="761b0-105">La visualizzazione ConferenceMessageCount archivia le informazioni sul numero di messaggi inviati da un utente a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="761b0-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="761b0-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="761b0-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="761b0-107">La visualizzazione ConferenceMessageCount contiene tutte le colonne della [visualizzazione ConferenceSessionDetails](conferencesessiondetails.md) , oltre alle colonne elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="761b0-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="761b0-108">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="761b0-108">**Column**</span></span>|<span data-ttu-id="761b0-109">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="761b0-109">**Data Type**</span></span>|<span data-ttu-id="761b0-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="761b0-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="761b0-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="761b0-111">**UserUri**</span></span> <br/> |<span data-ttu-id="761b0-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="761b0-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="761b0-113">URI dell'utente che ha inviato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="761b0-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="761b0-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="761b0-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="761b0-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="761b0-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="761b0-116">Tipo di URI dell'utente che ha inviato i messaggi.</span><span class="sxs-lookup"><span data-stu-id="761b0-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="761b0-117">Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="761b0-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="761b0-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="761b0-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="761b0-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="761b0-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="761b0-120">Tenant dell'utente che ha inviato i messaggi.</span><span class="sxs-lookup"><span data-stu-id="761b0-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="761b0-121">Per altre informazioni, vedere la [tabella tenant](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="761b0-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="761b0-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="761b0-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="761b0-123">smallint</span><span class="sxs-lookup"><span data-stu-id="761b0-123">smallint</span></span>  <br/> |<span data-ttu-id="761b0-124">Numero di messaggi inviati dall'utente durante la sessione di conferenza.</span><span class="sxs-lookup"><span data-stu-id="761b0-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

