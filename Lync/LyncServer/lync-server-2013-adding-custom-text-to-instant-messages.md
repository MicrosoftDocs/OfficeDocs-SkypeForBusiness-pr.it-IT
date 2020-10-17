---
title: 'Lync Server 2013: aggiunta di testo personalizzato ai messaggi istantanei'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding custom text to instant messages
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398847(v=OCS.15)
ms:contentKeyID: 48185458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 466eac15cf75728578e7d517d15ddb222d1c4b70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521363"
---
# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a><span data-ttu-id="e078f-102">Aggiunta di testo personalizzato ai messaggi istantanei in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e078f-102">Adding custom text to instant messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e078f-103">_**Ultimo argomento modificato:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="e078f-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="e078f-104">Aggiungere una dichiarazione di non responsabilità o un avviso all'inizio di ogni conversazione di messaggistica istantanea di Lync 2013 utilizzando i cmdlet **New-CsClientPolicy** o **Set-CsClientPolicy** di Lync Server Management Shell con il parametro IMWarning.</span><span class="sxs-lookup"><span data-stu-id="e078f-104">Add a disclaimer or warning to the beginning of every Lync 2013 instant messaging (IM) conversation by using the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the IMWarning parameter.</span></span>

<span data-ttu-id="e078f-105">Il comando nell'esempio seguente aggiunge un promemoria di sicurezza nella parte superiore della finestra di conversazione ogni volta che viene avviata una nuova conversazione di messaggistica istantanea:</span><span class="sxs-lookup"><span data-stu-id="e078f-105">The command in the following example adds a security reminder at the top of the Conversation window whenever a new IM conversation begins:</span></span>

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

<span data-ttu-id="e078f-106">Utilizzare **Grant-CSClientPolicy** per assegnare il nuovo criterio agli utenti.</span><span class="sxs-lookup"><span data-stu-id="e078f-106">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="e078f-107">Per informazioni dettagliate, vedere **New-CsClientPolicy** e **Grant-CsClientPolicy** nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e078f-107">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

