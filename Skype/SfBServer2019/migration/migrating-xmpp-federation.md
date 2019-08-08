---
title: Migrazione della Federazione XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: "Le versioni precedenti fornivano un gateway XMPP (Extensible Messaging and Presence Protocol) che poteva essere distribuito come ruolo server distinto per consentire la Federazione con le distribuzioni XMPP. La funzionalità XMPP non è più disponibile & deprecata in Skype for Business Server 2019. Se si vuole continuare a usare la funzionalità XMPP, è possibile avvalersi dell'ambiente coexitence con la versione legacy (Skype for Business Server 2015/Lync Server 2013). La funzionalità XMPP viene installata in due parti: come proxy XMPP che viene eseguito nel server perimetrale legacy e il gateway XMPP che viene eseguito nel server front-end legacy."
ms.openlocfilehash: 0c7c3dbb9c7cda4f6825f66326422dced85a9c3c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238137"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="23f99-106">Migrazione della Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="23f99-106">Migrating XMPP federation</span></span>

<span data-ttu-id="23f99-107">Le versioni precedenti fornivano un gateway XMPP (Extensible Messaging and Presence Protocol) che poteva essere distribuito come ruolo server distinto per consentire la Federazione con le distribuzioni XMPP.</span><span class="sxs-lookup"><span data-stu-id="23f99-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="23f99-108">La funzionalità XMPP non è più disponibile ed è deprecata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="23f99-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="23f99-109">Se si vuole continuare a usare la funzionalità XMPP, è possibile farlo in un ambiente di coesistenza con una versione legacy (Skype for Business Server 2015 o Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="23f99-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="23f99-110">La funzionalità XMPP viene installata in due parti: come proxy XMPP che viene eseguito nel server perimetrale legacy e il gateway XMPP che viene eseguito nel server front-end legacy.</span><span class="sxs-lookup"><span data-stu-id="23f99-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="23f99-111">Da una prospettiva di migrazione, gli utenti che vogliono avvalersi della funzionalità XMPP devono rimanere nel server legacy e non devono essere spostati in un pool di Skype for Business Server 2019, ma continuano a usare il gateway XMPP legacy.</span><span class="sxs-lookup"><span data-stu-id="23f99-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="23f99-112">Questo è possibile solo quando il partner federato XMPP è configurato in Skype for Business Server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="23f99-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="23f99-113">Non è consigliabile eseguire la migrazione del server perimetrale legacy a Skype for Business Server 2019 se si vuole continuare a usare la funzionalità XMPP.</span><span class="sxs-lookup"><span data-stu-id="23f99-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="23f99-114">Tuttavia, puoi avere la coesistenza del server perimetrale legacy (con proxy XMPP) e del server Edge di Skype for business 2019.</span><span class="sxs-lookup"><span data-stu-id="23f99-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

