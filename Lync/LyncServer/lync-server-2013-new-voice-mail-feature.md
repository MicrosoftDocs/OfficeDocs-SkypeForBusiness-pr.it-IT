---
title: 'Lync Server 2013: Nuova funzionalità di segreteria telefonica'
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
ms.openlocfilehash: 27dbea942488181eb69695f78713c9e126c32aab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-voice-mail-feature-in-lync-server-2013"></a><span data-ttu-id="15b00-102">Nuova funzionalità di segreteria telefonica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15b00-102">New voice mail feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15b00-103">_**Argomento Ultima modifica:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="15b00-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="15b00-104">Lync Server 2013 introduce l'escape per la segreteria telefonica, un miglioramento per la gestione della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="15b00-104">Lync Server 2013 introduces Voice mail Escape, an enhancement for managing voice mail.</span></span> <span data-ttu-id="15b00-105">Questa nuova funzionalità può rilevare quando una chiamata è stata instradata alla segreteria telefonica e impedire che la chiamata venga immediatamente instradata alla segreteria telefonica dell'utente senza dare all'utente la possibilità di rispondere alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="15b00-105">This new feature can detect when a call has been routed to voice mail, and prevent the call from being immediately routed to the user’s mobile phone voice mail without giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="15b00-106">Questo scenario si verifica quando l'utente abilita la chiamata simultanea al cellulare e il telefono cellulare è disattivato, non è più a portata di batteria o fuori campo.</span><span class="sxs-lookup"><span data-stu-id="15b00-106">This scenario occurs when the user enables simultaneous ringing to their mobile phone, and their mobile phone is turned off, out of battery, or out of range.</span></span> <span data-ttu-id="15b00-107">La funzionalità di escape della segreteria telefonica rileva che la chiamata è stata immediatamente risolta dalla segreteria telefonica dell'utente e disconnette la chiamata alla segreteria telefonica per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="15b00-107">Voicemail Escape detects that the call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="15b00-108">La chiamata continua a squillare sugli altri endpoint dell'utente dando all'utente la possibilità di rispondere alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="15b00-108">The call continues to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="15b00-109">Se l'utente non risponde alla chiamata, la chiamata viene instradata alla segreteria telefonica aziendale.</span><span class="sxs-lookup"><span data-stu-id="15b00-109">If the user does not answer the call, then the call is routed to the corporate voice mail.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="15b00-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15b00-110">See Also</span></span>


[<span data-ttu-id="15b00-111">Configurazione della posta in uscita della segreteria telefonica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15b00-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="15b00-112">Nuove funzionalità di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15b00-112">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

