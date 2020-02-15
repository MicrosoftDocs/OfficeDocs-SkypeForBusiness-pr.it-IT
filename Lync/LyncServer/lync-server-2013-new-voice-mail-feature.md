---
title: 'Lync Server 2013: nuova funzionalità di segreteria telefonica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New voice mail feature
ms:assetid: 84d13238-67ef-42cc-801a-2d8147ba3b7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688117(v=OCS.15)
ms:contentKeyID: 49733715
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b7951b0dd9a6841d66c1782322f6c44a4e16d99
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-voice-mail-feature-in-lync-server-2013"></a><span data-ttu-id="fff6b-102">Nuova funzionalità di segreteria telefonica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fff6b-102">New voice mail feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fff6b-103">_**Ultimo argomento modificato:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="fff6b-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="fff6b-104">Lync Server 2013 introduce Voice mail Escape, un miglioramento per la gestione dei messaggi vocali.</span><span class="sxs-lookup"><span data-stu-id="fff6b-104">Lync Server 2013 introduces Voice mail Escape, an enhancement for managing voice mail.</span></span> <span data-ttu-id="fff6b-105">La nuova funzione rileva quando una chiamata viene instradata alla segreteria telefonica, e evita che arrivi direttamente alla segreteria telefonica senza che l'utente abbia la possibilità di rispondere.</span><span class="sxs-lookup"><span data-stu-id="fff6b-105">This new feature can detect when a call has been routed to voice mail, and prevent the call from being immediately routed to the user’s mobile phone voice mail without giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="fff6b-106">Una situazione simile si ha quando l'utente abilita lo squillo simultaneo sul proprio cellulare, che a sua volta è spento, scarico o fuori copertura.</span><span class="sxs-lookup"><span data-stu-id="fff6b-106">This scenario occurs when the user enables simultaneous ringing to their mobile phone, and their mobile phone is turned off, out of battery, or out of range.</span></span> <span data-ttu-id="fff6b-107">La funzione di escape della segreteria telefonica rileva quando una chiamata viene risposta automaticamente dalla segreteria telefonica del dispositivo mobile dell'utente, e la disconnette dalla segreteria.</span><span class="sxs-lookup"><span data-stu-id="fff6b-107">Voicemail Escape detects that the call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="fff6b-108">In questo modo, la chiamata continua a squillare sugli altri endpoint dell'utente, consentendo a quest'ultimo di rispondere.</span><span class="sxs-lookup"><span data-stu-id="fff6b-108">The call continues to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="fff6b-109">Se l'utente non risponde, la chiamata è instradata alla segreteria telefonica aziendale.</span><span class="sxs-lookup"><span data-stu-id="fff6b-109">If the user does not answer the call, then the call is routed to the corporate voice mail.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="fff6b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fff6b-110">See Also</span></span>


[<span data-ttu-id="fff6b-111">Configurazione della funzionalità di escape della segreteria telefonica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fff6b-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="fff6b-112">Nuove funzionalità di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fff6b-112">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

