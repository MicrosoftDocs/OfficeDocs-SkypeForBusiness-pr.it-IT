---
title: "Lync Server 2013: configurazione dei client per l'uso con Office Web Apps Server"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 263f53b61aa609c4385af2a9646bf84da2dea3cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a><span data-ttu-id="c5855-102">Configurazione dei client di Lync Server 2013 per l'uso con Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="c5855-102">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5855-103">_**Argomento Ultima modifica:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="c5855-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="c5855-104">Se si vuole che gli utenti sperimentino le funzionalità complete di Office Web App Server, è consigliabile aggiornare gli utenti a Microsoft Lync 2013; solo gli utenti di Lync 2013 potranno eseguire operazioni come scorrere le diapositive di PowerPoint indipendentemente dall'effettiva presentazione di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="c5855-104">If you want users to experience the full capabilities of Office Web App Server then you should upgrade those users to Microsoft Lync 2013; only users of Lync 2013 will be able to do such things as scroll through PowerPoint slides independent of the actual PowerPoint presentation.</span></span> <span data-ttu-id="c5855-105">In altri casi, questi utenti possono osservare qualsiasi diapositiva della presentazione in qualsiasi momento, senza interferire in alcun modo con la presentazione effettiva. Gli utenti che non usano Lync 2013 saranno comunque in grado di partecipare a conferenze online e visualizzare la presentazione di PowerPoint. Tuttavia, non saranno in grado di scorrere le diapositive in modo indipendente, né potranno vedere le transizioni delle diapositive o visualizzare i video incorporati.</span><span class="sxs-lookup"><span data-stu-id="c5855-105">(That is, these users can look at any slide in the presentation at any time, without interfering in any way with the actual presentation.) Users who are not using Lync 2013 will still be able to join online conferences and view the PowerPoint presentation; however, they will not be able to independently scroll through the slides, nor will they be able to see slide transitions or view embedded videos.</span></span>

<span data-ttu-id="c5855-106">Tieni presente che queste funzionalità saranno sempre disponibili per gli utenti di Lync 2013; Questo vale anche se il relatore di PowerPoint è in uso in Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="c5855-106">Note that these capabilities will always be available to users of Lync 2013; this is true even if the PowerPoint presenter is running Microsoft Lync 2010.</span></span> <span data-ttu-id="c5855-107">Se una presentazione di PowerPoint viene ospitata da un utente che sta eseguendo Lync 2010, Lync Server 2013 verrà coordinato con Office Web Apps Server per assicurarsi che gli utenti di Lync 2013 visualizzino la versione del server Office Web Apps della presentazione.</span><span class="sxs-lookup"><span data-stu-id="c5855-107">If a PowerPoint presentation is being hosted by a user running Lync 2010, Lync Server 2013 will coordinate with Office Web Apps Server to make sure that Lync 2013 users will view the Office Web Apps Server version of that presentation.</span></span> <span data-ttu-id="c5855-108">Office Web Apps Server non offre servizi di PowerPoint per gli utenti che utilizzano client diversi da Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c5855-108">Office Web Apps Server does not provide PowerPoint services for users running clients other than Lync 2013.</span></span> <span data-ttu-id="c5855-109">Gli utenti possono invece connettersi al servizio servizi di conferenza e visualizzare le presentazioni di PowerPoint nello stesso modo in Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c5855-109">Instead, those users connect to the Conferencing server service and view PowerPoint presentations the same way they did in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="c5855-110">Ciò significa anche che questi utenti avranno accesso solo alle funzionalità più limitate offerte da Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c5855-110">This also means that these users will only have access to the more-limited capabilities offered by Lync Server 2010.</span></span>

<span data-ttu-id="c5855-111">Anche se non è richiesta alcuna configurazione client per Office Web Apps Server (ad eccezione dell'aggiornamento degli utenti a Lync 2013), è consigliabile aggiornare i partecipanti alla conferenza a Internet Explorer 9.</span><span class="sxs-lookup"><span data-stu-id="c5855-111">Although no client configuration is required for Office Web Apps Server (other than upgrading users to Lync 2013), it is recommended that conference attendees be upgrade to Internet Explorer 9.</span></span> <span data-ttu-id="c5855-112">Anche se è possibile accedere alle conferenze con Internet Explorer 8, esistono alcune limitazioni all'uso di tale Web browser.</span><span class="sxs-lookup"><span data-stu-id="c5855-112">Although conferences can be accessed using Internet Explorer 8, there are some limitations to using that Web browser.</span></span> <span data-ttu-id="c5855-113">Ad esempio, gli utenti di Internet Explorer 8 non saranno in grado di ridimensionare la fase di PowerPoint in dimensioni personalizzate. al contrario, si limiterà a usare una delle tre dimensioni predefinite della fase.</span><span class="sxs-lookup"><span data-stu-id="c5855-113">For example, users of Internet Explorer 8 will not be able to resize the PowerPoint stage to a custom size; instead, they will be limited to using one of three predefined stage sizes.</span></span> <span data-ttu-id="c5855-114">Allo stesso modo, gli utenti di Internet Explorer 8 non saranno in grado di riprodurre file multimediali.</span><span class="sxs-lookup"><span data-stu-id="c5855-114">Likewise, Internet Explorer 8 users will not be able to play media files.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

