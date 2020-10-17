---
title: 'Lync Server 2013: pianificazione per le conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bf1bf0ce10281bf4d31fc8fdb1be9251b72caf6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507023"
---
# <a name="planning-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="0bc22-102">Pianificazione per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bc22-102">Planning for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bc22-103">_**Ultimo argomento modificato:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="0bc22-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="0bc22-104">Lync Server 2013 offre una vasta gamma di funzionalità di conferenza:</span><span class="sxs-lookup"><span data-stu-id="0bc22-104">Lync Server 2013 offers a rich set of conferencing capabilities:</span></span>

  - <span data-ttu-id="0bc22-105">Web Conferencing, che include collaborazione su documenti, condivisione di applicazioni e condivisione del desktop.</span><span class="sxs-lookup"><span data-stu-id="0bc22-105">Web conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span> <span data-ttu-id="0bc22-106">Lync Server 2013 utilizza Office Web Apps e il server Office Web Apps per gestire la condivisione e il rendering delle presentazioni di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="0bc22-106">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="0bc22-107">Per informazioni dettagliate sull'installazione e sulla configurazione del server Office Web Apps, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="0bc22-107">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="0bc22-108">A/V Conferencing, che consente agli utenti di partecipare a conferenze audio o video in tempo reale senza dover utilizzare servizi esterni, come il servizio Microsoft Live Meeting o un ponte audio di terze parti</span><span class="sxs-lookup"><span data-stu-id="0bc22-108">Audio/video (A/V) conferencing, which enables users to have real-time audio or video conferences without the need for external services such as the Microsoft Live Meeting service or a third-party audio bridge.</span></span>

  - <span data-ttu-id="0bc22-109">Conferenza telefonica con accesso esterno, che consente agli utenti di partecipare alla parte audio di una conferenza di Lync Server 2013 utilizzando un telefono PSTN senza dover utilizzare un provider di servizi di audioconferenza di terze parti.</span><span class="sxs-lookup"><span data-stu-id="0bc22-109">Dial-in conferencing, which allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring a third-party audio conferencing provider.</span></span>

  - <span data-ttu-id="0bc22-110">IM Conferencing, per conferenza in cui più di due utenti comunicano in una singola sessione di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="0bc22-110">Instant messaging (IM) conferencing, in which more than two parties communicate in a single IM session.</span></span> <span data-ttu-id="0bc22-111">Per informazioni dettagliate sulle conferenze di messaggistica istantanea, vedere [pianificazione di front end server, messaggistica istantanea e presenza in Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="0bc22-111">For details about IM conferencing, see [Planning for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="0bc22-112">Lync Server 2013 supporta sia le conferenze pianificate sia le conferenze estemporanee.</span><span class="sxs-lookup"><span data-stu-id="0bc22-112">Lync Server 2013 supports both scheduled conferences and impromptu conferences.</span></span>

<span data-ttu-id="0bc22-113">Quando si distribuisce Lync Server 2013, Front End Server, è possibile scegliere se distribuire anche le funzionalità di conferenza Web, A/V Conferencing e di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="0bc22-113">When you deploy Lync Server 2013, Front End Server, you can choose whether to also deploy the web conferencing, A/V conferencing, and dial-in conferencing capabilities.</span></span> <span data-ttu-id="0bc22-114">Le funzionalità di conferenza di messaggistica istantanea vengono sempre distribuite automaticamente insieme alle funzionalità di conversazione di messaggistica istantanea nei server front end di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0bc22-114">IM conferencing capabilities are always automatically deployed along with IM conversation capabilities on Lync Server 2013 Front End Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0bc22-115">Se la distribuzione include riunioni organizzate utilizzando client Office Communicator 2007 R2 (inclusa la console di Live Meeting o il componente aggiuntivo per conferenze per Microsoft Office Outlook), le riunioni avranno le limitazioni seguenti dopo la migrazione a Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="0bc22-115">If your deployment includes meetings organized using Office Communicator 2007 R2 clients (including the Live Meeting console or Conferencing Add-in for Microsoft Office Outlook), the meetings will have the following limitations after they are migrated to Lync Server 2013:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="0bc22-116">Gli utenti della riunione non saranno in grado di utilizzare le funzionalità di collaborazione dati, tra cui la collaborazione dei documenti, la condivisione di applicazioni e la condivisione del desktop.</span><span class="sxs-lookup"><span data-stu-id="0bc22-116">Users in the meeting will not be able to use data collaboration features, including document collaboration, application sharing, and desktop sharing.</span></span></P>
> <LI>
> <P><span data-ttu-id="0bc22-117">Possono verificarsi problemi di stabilità poiché i client di Office Communicator 2007 R2 non sono supportati con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0bc22-117">Stability issues may arise since Office Communicator 2007 R2 clients are not supported with Lync Server 2013.</span></span></P></LI></UL><span data-ttu-id="0bc22-118">Per evitare questi problemi, ripianificare le riunioni organizzate utilizzando client di Office Communicator 2007 R2 con Outlook 2010 o Outlook 2013 utilizzando il componente aggiuntivo per riunioni online per Lync 2010 o il componente aggiuntivo per riunioni online per Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="0bc22-118">To avoid these issues, reschedule any meeting organized using Office Communicator 2007 R2 clients with Outlook 2010 or Outlook 2013 using either the Online Meeting Add-in for Lync 2010 or Online Meeting Add-in for Lync 2013.</span></span>



</div>

<span data-ttu-id="0bc22-119">Nelle sezioni che seguono vengono illustrati gli elementi necessari alla distribuzione dei vari tipi di funzionalità per conferenze, compresi il processo di pianificazione, i componenti, i requisiti hardware e software e il processo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0bc22-119">The following sections describe what is required to deploy the various types of conferencing capabilities, including the planning process, components, hardware and software requirements, and the deployment process.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0bc22-120">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="0bc22-120">In This Section</span></span>

  - [<span data-ttu-id="0bc22-121">Panoramica delle conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bc22-121">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)

  - [<span data-ttu-id="0bc22-122">Definizione dei requisiti per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bc22-122">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [<span data-ttu-id="0bc22-123">Componenti e topologie per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bc22-123">Components and topologies for conferencing in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [<span data-ttu-id="0bc22-124">Requisiti tecnici per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bc22-124">Technical requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-conferencing.md)

  - [<span data-ttu-id="0bc22-125">Elenco di controllo di distribuzione per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bc22-125">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [<span data-ttu-id="0bc22-126">Supporto per riunioni di grandi dimensioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bc22-126">Support for large meetings in Lync Server 2013</span></span>](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

