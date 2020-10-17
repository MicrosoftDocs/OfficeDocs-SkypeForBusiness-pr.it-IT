---
title: "Lync Server 2013: pianificazione dell'integrazione della messaggistica unificata di Exchange"
description: "Lync Server 2013: pianificazione dell'integrazione della messaggistica unificata di Exchange."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Exchange Unified Messaging integration
ms:assetid: e7c63a71-2d99-4aa9-b649-36c1a431bdf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399031(v=OCS.15)
ms:contentKeyID: 48185880
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31296444d21a86a7837da3e29fc2152f3ca96ccc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571882"
---
# <a name="planning-for-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="a69ab-103">Pianificazione dell'integrazione della messaggistica unificata di Exchange in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a69ab-103">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a69ab-104">_**Ultimo argomento modificato:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="a69ab-104">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="a69ab-105">Lync Server 2013 supporta l'integrazione con la messaggistica unificata di Exchange per la combinazione di messaggi vocali e messaggi di posta elettronica in un'unica infrastruttura di messaggistica.</span><span class="sxs-lookup"><span data-stu-id="a69ab-105">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="a69ab-106">In Microsoft Exchange Server 2007 Service Pack 1 (SP1) e Microsoft Exchange Server 2010, la messaggistica unificata di Exchange è uno dei diversi ruoli del server Exchange che è possibile installare e configurare.</span><span class="sxs-lookup"><span data-stu-id="a69ab-106">In Microsoft Exchange Server 2007 Service Pack 1 (SP1) and Microsoft Exchange Server 2010, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span>

<span data-ttu-id="a69ab-107">In Microsoft Exchange Server 2013, la messaggistica unificata di Exchange viene eseguita come servizio su un server cassette postali di Exchange.</span><span class="sxs-lookup"><span data-stu-id="a69ab-107">In Microsoft Exchange Server 2013, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="a69ab-108">Per le distribuzioni di VoIP aziendale di Lync Server 2013, la messaggistica unificata combina la messaggistica vocale e la messaggistica di posta elettronica in un unico archivio disponibile da un telefono (Outlook Voice Access) o da un computer.</span><span class="sxs-lookup"><span data-stu-id="a69ab-108">For Lync Server 2013 Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that is available from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="a69ab-109">La messaggistica unificata e Lync Server 2013 interagiscono per fornire servizi di ricezione chiamata, Outlook Voice Access e operatore automatico agli utenti di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="a69ab-109">Unified Messaging and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="a69ab-110">Per ulteriori informazioni sulle modifiche apportate all'architettura in Microsoft Exchange Server 2013, vedere la sezione relativa alle modifiche all'architettura vocale nella documentazione di Microsoft Exchange Server 2013 all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730) .</span><span class="sxs-lookup"><span data-stu-id="a69ab-110">For more information about the architecture changes in Microsoft Exchange Server 2013, see “Voice Architecture Changes” in the Microsoft Exchange Server 2013 documentation at [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730).</span></span>

<span data-ttu-id="a69ab-111">Affinché queste funzionalità siano supportate in una distribuzione di messaggistica unificata di Exchange locale, è necessario eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a69ab-111">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>

  - <span data-ttu-id="a69ab-112">Microsoft Exchange Server 2007 Service Pack 1 (SP1) o Service Pack più recente</span><span class="sxs-lookup"><span data-stu-id="a69ab-112">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack</span></span>

  - <span data-ttu-id="a69ab-113">Microsoft Exchange Server 2010 o Service Pack più recente</span><span class="sxs-lookup"><span data-stu-id="a69ab-113">Microsoft Exchange Server 2010 or latest service pack</span></span>

  - <span data-ttu-id="a69ab-114">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="a69ab-114">Microsoft Exchange Server 2013</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a69ab-115">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="a69ab-115">In This Section</span></span>

  - [<span data-ttu-id="a69ab-116">Funzionalità della messaggistica unificata integrata e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a69ab-116">Features of integrated Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-features-of-integrated-unified-messaging.md)

  - [<span data-ttu-id="a69ab-117">Componenti e topologie per la messaggistica unificata locale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a69ab-117">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="a69ab-118">Linee guida per l'integrazione della messaggistica unificata locale e di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a69ab-118">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

  - [<span data-ttu-id="a69ab-119">Processo di distribuzione per l'integrazione della messaggistica unificata locale e di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a69ab-119">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

