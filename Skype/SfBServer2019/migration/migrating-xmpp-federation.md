---
title: Migrazione della federazione di XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Le versioni precedenti hanno fornito un gateway XMPP (Extensible Messaging and Presence Protocol) che poteva essere distribuito come ruolo del server separato per consentire la federazione con le distribuzioni XMPP. La funzionalità XMPP non è più disponibile & deprecata in Skype for Business Server 2019. Se si desidera continuare con la funzionalità XMPP, che può essere utilizzata in un ambiente di coesistenza con la versione legacy (Skype for Business Server 2015/ Lync Server 2013). La funzionalità XMPP viene installata in due parti: come proxy XMPP eseguito nel server perimetrale legacy e nel gateway XMPP eseguito nel Front End Server legacy.'
ms.openlocfilehash: 71b6c213450f51ea4b3fe1f351e22dbb992ce8ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752648"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="c0a98-106">Migrazione della federazione di XMPP</span><span class="sxs-lookup"><span data-stu-id="c0a98-106">Migrating XMPP federation</span></span>

<span data-ttu-id="c0a98-107">Le versioni precedenti hanno fornito un gateway XMPP (Extensible Messaging and Presence Protocol) che poteva essere distribuito come ruolo del server separato per consentire la federazione con le distribuzioni XMPP.</span><span class="sxs-lookup"><span data-stu-id="c0a98-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="c0a98-108">La funzionalità XMPP non è più disponibile ed è deprecata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c0a98-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="c0a98-109">Se si desidera continuare con la funzionalità XMPP, è possibile farlo in un ambiente di coesistenza con una versione legacy (Skype for Business Server 2015 o Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="c0a98-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="c0a98-110">La funzionalità XMPP viene installata in due parti: come proxy XMPP eseguito nel server perimetrale legacy e nel gateway XMPP eseguito nel Front End Server legacy.</span><span class="sxs-lookup"><span data-stu-id="c0a98-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="c0a98-111">Dal punto di vista della migrazione, gli utenti che desiderano utilizzare la funzionalità XMPP devono rimanere nel server legacy e non devono essere spostati in un pool di Skype for Business Server 2019, ma continuare a usare il gateway XMPP legacy.</span><span class="sxs-lookup"><span data-stu-id="c0a98-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="c0a98-112">Ciò è possibile solo quando il partner federato XMPP è configurato in Skype for Business Server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c0a98-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="c0a98-113">Non è consigliabile eseguire la migrazione del server perimetrale legacy a Skype for Business Server 2019 se si desidera continuare con la funzionalità XMPP.</span><span class="sxs-lookup"><span data-stu-id="c0a98-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="c0a98-114">Tuttavia, è possibile avere la coesistenza del server perimetrale legacy (con proxy XMPP) e del server perimetrale Skype for Business 2019.</span><span class="sxs-lookup"><span data-stu-id="c0a98-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

