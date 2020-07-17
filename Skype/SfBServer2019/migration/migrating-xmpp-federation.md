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
description: "Le versioni precedenti fornivano un gateway XMPP (Extensible Messaging and Presence Protocol) che potrebbe essere distribuito come ruolo server separato per consentire la Federazione con le distribuzioni XMPP. La funzionalità XMPP non è più disponibile & deprecata in Skype for Business Server 2019. Se si desidera proseguire con la funzionalità XMPP, è possibile avvalersi dell'ambiente coexitence con la versione legacy (Skype for Business Server 2015/Lync Server 2013). La funzionalità XMPP è installata in due parti: come proxy XMPP che viene eseguito nel server perimetrale legacy e il gateway XMPP in esecuzione nel front end server legacy."
ms.openlocfilehash: 71b6c213450f51ea4b3fe1f351e22dbb992ce8ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752648"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="eb60c-106">Migrazione della federazione di XMPP</span><span class="sxs-lookup"><span data-stu-id="eb60c-106">Migrating XMPP federation</span></span>

<span data-ttu-id="eb60c-107">Le versioni precedenti fornivano un gateway XMPP (Extensible Messaging and Presence Protocol) che potrebbe essere distribuito come ruolo server separato per consentire la Federazione con le distribuzioni XMPP.</span><span class="sxs-lookup"><span data-stu-id="eb60c-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="eb60c-108">La funzionalità XMPP non è più disponibile ed è obsoleta in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="eb60c-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="eb60c-109">Se si desidera continuare con la funzionalità XMPP, è possibile farlo in un ambiente di coesistenza con una versione legacy (Skype for Business Server 2015 o Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="eb60c-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="eb60c-110">La funzionalità XMPP è installata in due parti: come proxy XMPP che viene eseguito nel server perimetrale legacy e il gateway XMPP in esecuzione nel front end server legacy.</span><span class="sxs-lookup"><span data-stu-id="eb60c-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="eb60c-111">Dal punto di vista della migrazione, gli utenti che desiderano usufruire della caratteristica XMPP devono rimanere nel server legacy e non devono essere spostati in un pool di Skype for Business Server 2019 ma continuano a usare il gateway XMPP legacy.</span><span class="sxs-lookup"><span data-stu-id="eb60c-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="eb60c-112">Ciò è possibile solo quando il partner federato XMPP è configurato in Skype for Business Server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eb60c-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="eb60c-113">Non è necessario eseguire la migrazione del server perimetrale legacy a Skype for Business Server 2019 se si desidera continuare con la funzionalità XMPP.</span><span class="sxs-lookup"><span data-stu-id="eb60c-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="eb60c-114">Tuttavia, è possibile avere la coesistenza del server perimetrale legacy (con proxy XMPP) e del server perimetrale di Skype for business 2019.</span><span class="sxs-lookup"><span data-stu-id="eb60c-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

