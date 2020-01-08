---
title: 'Lync Server 2013: Pianificazione per la disponibilità elevata e il ripristino di emergenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 092e59813f76690233a950cd8ce914df47146d37
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="f9092-102">Pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9092-102">Planning for high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9092-103">_**Argomento Ultima modifica:** 2013-10-31_</span><span class="sxs-lookup"><span data-stu-id="f9092-103">_**Topic Last Modified:** 2013-10-31_</span></span>

<span data-ttu-id="f9092-104">Come in Lync Server 2010, il principale schema di disponibilità elevata per la maggior parte dei ruoli del server in Lync Server 2013 è basato sulla ridondanza del server tramite pooling.</span><span class="sxs-lookup"><span data-stu-id="f9092-104">As in Lync Server 2010, the main high availability scheme for most server roles in Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="f9092-105">Se un server che esegue un determinato ruolo del server non riesce, gli altri server nel pool che esegue lo stesso ruolo accettano il carico del server.</span><span class="sxs-lookup"><span data-stu-id="f9092-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="f9092-106">Questo vale per i server front-end, Edge Server, Mediation Server e direttori.</span><span class="sxs-lookup"><span data-stu-id="f9092-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="f9092-107">Lync Server 2013 aggiunge nuove misure per il ripristino di emergenza per i pool Front-End introducendo dispersement geografiche dei server in due centri dati per consentire la prosecuzione del servizio in caso di abbandono di un intero pool o sito.</span><span class="sxs-lookup"><span data-stu-id="f9092-107">Lync Server 2013 adds new disaster recovery measures for Front End pools by introducing geographical dispersement of your servers into two data centers to provide continuation of service should one entire pool or site go down.</span></span>

<span data-ttu-id="f9092-108">Lync Server 2013 migliora inoltre l'elevata disponibilità di back end server, supportando il mirroring sincrono di SQL per i database di back-end.</span><span class="sxs-lookup"><span data-stu-id="f9092-108">Lync Server 2013 also enhances Back End Server high availability, by supporting synchronous SQL mirroring for your Back End databases.</span></span>

<span data-ttu-id="f9092-109">In questa sezione vengono illustrate le principali caratteristiche di elevata disponibilità e ripristino di emergenza e vengono inoltre illustrati i passaggi che è possibile eseguire per l'elevata disponibilità e il ripristino di emergenza anche per gli altri ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="f9092-109">This section explains these major high availability and disaster recovery features, and also covers what steps you can take for high availability and disaster recovery for your other server roles as well.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f9092-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="f9092-110">In This Section</span></span>

  - [<span data-ttu-id="f9092-111">Ripristino di emergenza del pool Front End in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9092-111">Front End pool disaster recovery in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [<span data-ttu-id="f9092-112">Ripristino di emergenza dei server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9092-112">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)

  - [<span data-ttu-id="f9092-113">Pianificazione della resilienza di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9092-113">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="f9092-114">Funzionalità di gestione delle chiamate per il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9092-114">Call management features for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [<span data-ttu-id="f9092-115">Configurazione del server Chat persistente per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9092-115">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="f9092-116">Resilienza di siti metropolitani di Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f9092-116">Lync Server 2010 metropolitan site resiliency</span></span>](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

