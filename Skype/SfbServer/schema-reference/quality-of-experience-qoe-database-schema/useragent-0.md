---
title: Visualizzazione UserAgent
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: Nella visualizzazione UserAgent vengono archiviate le informazioni relative agli agenti utente coinvolti in sessioni con record nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 90db61df5bd947b101823172602103e47d4182a9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800016"
---
# <a name="useragent-view"></a><span data-ttu-id="b6b6a-104">Visualizzazione UserAgent</span><span class="sxs-lookup"><span data-stu-id="b6b6a-104">UserAgent view</span></span>
 
<span data-ttu-id="b6b6a-105">Nella visualizzazione UserAgent vengono archiviate le informazioni relative agli agenti utente coinvolti in sessioni con record nel database.</span><span class="sxs-lookup"><span data-stu-id="b6b6a-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="b6b6a-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6b6a-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="b6b6a-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="b6b6a-107">**Column**</span></span>|<span data-ttu-id="b6b6a-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="b6b6a-108">**Data Type**</span></span>|<span data-ttu-id="b6b6a-109">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="b6b6a-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b6b6a-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="b6b6a-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="b6b6a-111">int</span><span class="sxs-lookup"><span data-stu-id="b6b6a-111">int</span></span>  <br/> |<span data-ttu-id="b6b6a-112">Numero univoco che identifica l'agente utente.</span><span class="sxs-lookup"><span data-stu-id="b6b6a-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="b6b6a-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="b6b6a-113">UserAgent</span></span>  <br/> |<span data-ttu-id="b6b6a-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b6b6a-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b6b6a-115">Stringa dell'agente utente.</span><span class="sxs-lookup"><span data-stu-id="b6b6a-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="b6b6a-116">UAType</span><span class="sxs-lookup"><span data-stu-id="b6b6a-116">UAType</span></span>  <br/> |<span data-ttu-id="b6b6a-117">smallint</span><span class="sxs-lookup"><span data-stu-id="b6b6a-117">smallint</span></span>  <br/> |<span data-ttu-id="b6b6a-118">Tipo di agente utente.</span><span class="sxs-lookup"><span data-stu-id="b6b6a-118">Type of user agent.</span></span> <span data-ttu-id="b6b6a-119">Per ulteriori dettagli, vedere la tabella [UserAgent.](useragent.md)</span><span class="sxs-lookup"><span data-stu-id="b6b6a-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="b6b6a-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="b6b6a-120">UACategory</span></span>  <br/> |<span data-ttu-id="b6b6a-121">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="b6b6a-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="b6b6a-p104">Categoria a cui appartiene l'agente utente. Ad esempio, l'agente utente Conferencing_Attendant_1.0 appartiene alla categoria (UACategory) CAA.</span><span class="sxs-lookup"><span data-stu-id="b6b6a-p104">Category that the user agent belongs to. For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

