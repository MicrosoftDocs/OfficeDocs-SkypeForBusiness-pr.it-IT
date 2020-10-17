---
title: 'Lync Server 2013: pianificazione per la disponibilità elevata e il ripristino di emergenza'
description: 'Lync Server 2013: pianificazione della disponibilità elevata e del ripristino di emergenza.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bb5f430201c48738421c4fbe72151ca58173898
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571842"
---
# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="550f0-103">Pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="550f0-103">Planning for high availability and disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="550f0-104">_**Ultimo argomento modificato:** 2013-10-31_</span><span class="sxs-lookup"><span data-stu-id="550f0-104">_**Topic Last Modified:** 2013-10-31_</span></span>

<span data-ttu-id="550f0-105">Come in Lync Server 2010, il principale schema di disponibilità elevata per la maggior parte dei ruoli del server in Lync Server 2013 si basa sulla ridondanza del server tramite pool.</span><span class="sxs-lookup"><span data-stu-id="550f0-105">As in Lync Server 2010, the main high availability scheme for most server roles in Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="550f0-106">In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore.</span><span class="sxs-lookup"><span data-stu-id="550f0-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="550f0-107">Ciò vale per Front End Server, server perimetrali, Mediation Server e Director.</span><span class="sxs-lookup"><span data-stu-id="550f0-107">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="550f0-108">Lync Server 2013 aggiunge nuove misure per il ripristino di emergenza per i pool Front End introducendo dispersione geografiche dei server in due data center per fornire la continuazione del servizio se un intero pool o sito si sposta verso il basso.</span><span class="sxs-lookup"><span data-stu-id="550f0-108">Lync Server 2013 adds new disaster recovery measures for Front End pools by introducing geographical dispersement of your servers into two data centers to provide continuation of service should one entire pool or site go down.</span></span>

<span data-ttu-id="550f0-109">Lync Server 2013 consente inoltre di migliorare la disponibilità elevata del server back-end, grazie al supporto del mirroring SQL sincrono per i database back-end.</span><span class="sxs-lookup"><span data-stu-id="550f0-109">Lync Server 2013 also enhances Back End Server high availability, by supporting synchronous SQL mirroring for your Back End databases.</span></span>

<span data-ttu-id="550f0-110">In questa sezione vengono illustrate le principali funzionalità per disponibilità elevata e ripristino di emergenza e descritti i passaggi da effettuare per assicurare disponibilità elevata e ripristino di emergenza per gli altri ruoli server.</span><span class="sxs-lookup"><span data-stu-id="550f0-110">This section explains these major high availability and disaster recovery features, and also covers what steps you can take for high availability and disaster recovery for your other server roles as well.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="550f0-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="550f0-111">In This Section</span></span>

  - [<span data-ttu-id="550f0-112">Ripristino di emergenza del pool Front end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="550f0-112">Front End pool disaster recovery in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [<span data-ttu-id="550f0-113">Ripristino di emergenza del server perimetrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="550f0-113">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)

  - [<span data-ttu-id="550f0-114">Pianificazione della resilienza di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="550f0-114">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="550f0-115">Funzionalità di gestione delle chiamate per il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="550f0-115">Call management features for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [<span data-ttu-id="550f0-116">Configurazione del server Chat persistente per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="550f0-116">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="550f0-117">Resilienza del sito metropolitano di Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="550f0-117">Lync Server 2010 metropolitan site resiliency</span></span>](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

