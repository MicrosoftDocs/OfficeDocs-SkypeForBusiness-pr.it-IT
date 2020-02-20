---
title: "Lync Server 2013: configurazione dei client per l'utilizzo con il server Office Web Apps"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10ec5ddaca5a8409a18504cb73912d107c9a6455
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a><span data-ttu-id="de66d-102">Configurazione dei client di Lync Server 2013 per l'utilizzo con il server Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="de66d-102">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de66d-103">_**Ultimo argomento modificato:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="de66d-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="de66d-104">Se si desidera che gli utenti sperimentino le funzionalità complete del server Office Web App, è necessario aggiornare gli utenti a Microsoft Lync 2013; solo gli utenti di Lync 2013 saranno in grado di eseguire operazioni come scorrere le diapositive di PowerPoint indipendentemente dall'effettiva presentazione di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="de66d-104">If you want users to experience the full capabilities of Office Web App Server then you should upgrade those users to Microsoft Lync 2013; only users of Lync 2013 will be able to do such things as scroll through PowerPoint slides independent of the actual PowerPoint presentation.</span></span> <span data-ttu-id="de66d-105">Gli utenti possono, in qualsiasi momento, esaminare qualsiasi diapositiva della presentazione, senza interferire in alcun modo con la presentazione effettiva. Gli utenti che non utilizzano Lync 2013 saranno comunque in grado di partecipare a conferenze online e di visualizzare la presentazione di PowerPoint; Tuttavia, non potranno scorrere le diapositive in modo indipendente, né potranno visualizzare le transizioni di diapositive o visualizzare i video incorporati.</span><span class="sxs-lookup"><span data-stu-id="de66d-105">(That is, these users can look at any slide in the presentation at any time, without interfering in any way with the actual presentation.) Users who are not using Lync 2013 will still be able to join online conferences and view the PowerPoint presentation; however, they will not be able to independently scroll through the slides, nor will they be able to see slide transitions or view embedded videos.</span></span>

<span data-ttu-id="de66d-106">Si noti che queste funzionalità saranno sempre disponibili per gli utenti di Lync 2013; Questo è vero anche se il relatore di PowerPoint esegue Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="de66d-106">Note that these capabilities will always be available to users of Lync 2013; this is true even if the PowerPoint presenter is running Microsoft Lync 2010.</span></span> <span data-ttu-id="de66d-107">Se una presentazione di PowerPoint è ospitata da un utente che esegue Lync 2010, Lync Server 2013 coordinerà con il server Office Web Apps per assicurarsi che gli utenti di Lync 2013 visualizzino la versione del server Office Web Apps di tale presentazione.</span><span class="sxs-lookup"><span data-stu-id="de66d-107">If a PowerPoint presentation is being hosted by a user running Lync 2010, Lync Server 2013 will coordinate with Office Web Apps Server to make sure that Lync 2013 users will view the Office Web Apps Server version of that presentation.</span></span> <span data-ttu-id="de66d-108">Il server Office Web Apps non fornisce servizi di PowerPoint per gli utenti che eseguono client diversi da Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="de66d-108">Office Web Apps Server does not provide PowerPoint services for users running clients other than Lync 2013.</span></span> <span data-ttu-id="de66d-109">Gli utenti, invece, si connettono al servizio di conferenza server e visualizzano le presentazioni di PowerPoint nello stesso modo in Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="de66d-109">Instead, those users connect to the Conferencing server service and view PowerPoint presentations the same way they did in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="de66d-110">Questo significa anche che questi utenti avranno accesso solo alle funzionalità più limitate offerte da Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="de66d-110">This also means that these users will only have access to the more-limited capabilities offered by Lync Server 2010.</span></span>

<span data-ttu-id="de66d-111">Anche se non è necessaria alcuna configurazione client per il server Office Web Apps (oltre all'aggiornamento degli utenti a Lync 2013), è consigliabile eseguire l'aggiornamento a Internet Explorer 9.</span><span class="sxs-lookup"><span data-stu-id="de66d-111">Although no client configuration is required for Office Web Apps Server (other than upgrading users to Lync 2013), it is recommended that conference attendees be upgrade to Internet Explorer 9.</span></span> <span data-ttu-id="de66d-112">Anche se è possibile accedere a conferenze con Internet Explorer 8, esistono alcune limitazioni all'utilizzo di tale Web browser.</span><span class="sxs-lookup"><span data-stu-id="de66d-112">Although conferences can be accessed using Internet Explorer 8, there are some limitations to using that Web browser.</span></span> <span data-ttu-id="de66d-113">Ad esempio, gli utenti di Internet Explorer 8 non saranno in grado di ridimensionare la fase di PowerPoint in formato personalizzato. al contrario, saranno limitate all'utilizzo di una delle tre dimensioni predefinite dello stage.</span><span class="sxs-lookup"><span data-stu-id="de66d-113">For example, users of Internet Explorer 8 will not be able to resize the PowerPoint stage to a custom size; instead, they will be limited to using one of three predefined stage sizes.</span></span> <span data-ttu-id="de66d-114">Analogamente, gli utenti di Internet Explorer 8 non saranno in grado di riprodurre file multimediali.</span><span class="sxs-lookup"><span data-stu-id="de66d-114">Likewise, Internet Explorer 8 users will not be able to play media files.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

