---
title: 'Lync Server 2013: Pianificazione dei servizi di conferenza'
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
ms.openlocfilehash: 53b7813a197dd7cc3116540c605d7efbdb22a04b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="03711-102">Pianificazione dei servizi di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03711-102">Planning for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03711-103">_**Argomento Ultima modifica:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="03711-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="03711-104">Lync Server 2013 offre una vasta gamma di funzionalità di conferenza:</span><span class="sxs-lookup"><span data-stu-id="03711-104">Lync Server 2013 offers a rich set of conferencing capabilities:</span></span>

  - <span data-ttu-id="03711-105">Web Conferencing, che include la collaborazione tra documenti, condivisione applicazioni e condivisione desktop.</span><span class="sxs-lookup"><span data-stu-id="03711-105">Web conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span> <span data-ttu-id="03711-106">Lync Server 2013 usa Office Web Apps e il server Office Web Apps per gestire la condivisione e il rendering delle presentazioni di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="03711-106">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="03711-107">Per informazioni dettagliate sull'installazione e la configurazione del server Office Web Apps, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="03711-107">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="03711-108">Servizi di conferenza audio/video (A/V), che consente agli utenti di avere conferenze audio o video in tempo reale senza la necessità di un servizio esterno, ad esempio Microsoft Live Meeting Service o un bridge audio di terze parti.</span><span class="sxs-lookup"><span data-stu-id="03711-108">Audio/video (A/V) conferencing, which enables users to have real-time audio or video conferences without the need for external services such as the Microsoft Live Meeting service or a third-party audio bridge.</span></span>

  - <span data-ttu-id="03711-109">Servizi di conferenza telefonica con accesso esterno, che consente agli utenti di partecipare alla parte audio di una conferenza di Lync Server 2013 utilizzando un telefono PSTN (Public Switched Telephone Network) senza richiedere un provider di audioconferenza di terze parti.</span><span class="sxs-lookup"><span data-stu-id="03711-109">Dial-in conferencing, which allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring a third-party audio conferencing provider.</span></span>

  - <span data-ttu-id="03711-110">Servizi di conferenza di messaggistica istantanea, in cui più di due parti comunicano in una singola sessione di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="03711-110">Instant messaging (IM) conferencing, in which more than two parties communicate in a single IM session.</span></span> <span data-ttu-id="03711-111">Per informazioni dettagliate sui servizi di conferenza di messaggistica istantanea, vedere [pianificazione dei server front-end, della messaggistica immediata e della presenza in Lync server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="03711-111">For details about IM conferencing, see [Planning for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="03711-112">Lync Server 2013 supporta sia le conferenze pianificate che le conferenze estemporanee.</span><span class="sxs-lookup"><span data-stu-id="03711-112">Lync Server 2013 supports both scheduled conferences and impromptu conferences.</span></span>

<span data-ttu-id="03711-113">Quando si distribuisce Lync Server 2013, Front End Server, è possibile scegliere se distribuire anche le funzionalità di conferenza Web, conferenze A/V e servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="03711-113">When you deploy Lync Server 2013, Front End Server, you can choose whether to also deploy the web conferencing, A/V conferencing, and dial-in conferencing capabilities.</span></span> <span data-ttu-id="03711-114">Le funzionalità di conferenza di messaggistica istantanea vengono sempre distribuite automaticamente insieme alle funzionalità di conversazione di messaggistica istantanea nei server front end di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03711-114">IM conferencing capabilities are always automatically deployed along with IM conversation capabilities on Lync Server 2013 Front End Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="03711-115">Se la distribuzione include riunioni organizzate con client di Office Communicator 2007 R2 (inclusa la console Live Meeting o il componente aggiuntivo conferenza per Microsoft Office Outlook), le riunioni avranno le seguenti limitazioni dopo la migrazione a Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="03711-115">If your deployment includes meetings organized using Office Communicator 2007 R2 clients (including the Live Meeting console or Conferencing Add-in for Microsoft Office Outlook), the meetings will have the following limitations after they are migrated to Lync Server 2013:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="03711-116">Gli utenti della riunione non saranno in grado di usare le caratteristiche di collaborazione dei dati, tra cui la collaborazione tra documenti, la condivisione delle applicazioni e la condivisione del desktop.</span><span class="sxs-lookup"><span data-stu-id="03711-116">Users in the meeting will not be able to use data collaboration features, including document collaboration, application sharing, and desktop sharing.</span></span></P>
> <LI>
> <P><span data-ttu-id="03711-117">I problemi di stabilità possono verificarsi perché i client di Office Communicator 2007 R2 non sono supportati con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03711-117">Stability issues may arise since Office Communicator 2007 R2 clients are not supported with Lync Server 2013.</span></span></P></LI></UL><span data-ttu-id="03711-118">Per evitare questi problemi, ripianificare le riunioni organizzate con i client Office Communicator 2007 R2 con Outlook 2010 o Outlook 2013 usando il componente aggiuntivo riunione online per Lync 2010 o il componente aggiuntivo riunione online per Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="03711-118">To avoid these issues, reschedule any meeting organized using Office Communicator 2007 R2 clients with Outlook 2010 or Outlook 2013 using either the Online Meeting Add-in for Lync 2010 or Online Meeting Add-in for Lync 2013.</span></span>



</div>

<span data-ttu-id="03711-119">Le sezioni seguenti descrivono le informazioni necessarie per distribuire i vari tipi di funzionalità di conferenza, inclusi il processo di pianificazione, i componenti, i requisiti hardware e software e il processo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="03711-119">The following sections describe what is required to deploy the various types of conferencing capabilities, including the planning process, components, hardware and software requirements, and the deployment process.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="03711-120">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="03711-120">In This Section</span></span>

  - [<span data-ttu-id="03711-121">Panoramica delle conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03711-121">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)

  - [<span data-ttu-id="03711-122">Definizione dei requisiti per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03711-122">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [<span data-ttu-id="03711-123">Componenti e topologie per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03711-123">Components and topologies for conferencing in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [<span data-ttu-id="03711-124">Requisiti tecnici per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03711-124">Technical requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-conferencing.md)

  - [<span data-ttu-id="03711-125">Elenco di controllo di distribuzione per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03711-125">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [<span data-ttu-id="03711-126">Supporto per le riunioni di grandi dimensioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03711-126">Support for large meetings in Lync Server 2013</span></span>](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

