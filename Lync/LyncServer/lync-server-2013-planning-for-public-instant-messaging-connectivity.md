---
title: 'Lync Server 2013: pianificazione della connettività di messaggistica istantanea pubblica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4432484fbd6056d51a38090a18dbe106851d7c0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="946c2-102">Pianificazione della connettività di messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="946c2-102">Planning for public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="946c2-103">_**Argomento Ultima modifica:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="946c2-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="946c2-104">La connettività di messaggistica istantanea pubblica è una classe di federazione ed è configurata per consentire agli utenti interni ed esterni di Lync Server 2013 di aggiungere contatti da una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="946c2-104">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="946c2-105">Contatti di Messenger</span><span class="sxs-lookup"><span data-stu-id="946c2-105">Messenger contacts</span></span>

  - <span data-ttu-id="946c2-106">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="946c2-106">Yahoo\!</span></span> <span data-ttu-id="946c2-107">contatti</span><span class="sxs-lookup"><span data-stu-id="946c2-107">contacts</span></span>

  - <span data-ttu-id="946c2-108">Contatti di America Online (AOL)</span><span class="sxs-lookup"><span data-stu-id="946c2-108">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="946c2-109">A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User (PIC USL) non è più disponibile per l'acquisto di contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="946c2-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="946c2-110">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="946c2-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="946c2-111">Messenger fino alla data di chiusura del servizio.</span><span class="sxs-lookup"><span data-stu-id="946c2-111">Messenger until the service shutdown date.</span></span> <span data-ttu-id="946c2-112">Data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="946c2-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="946c2-113">è stato annunciato.</span><span class="sxs-lookup"><span data-stu-id="946c2-113">has been announced.</span></span> <span data-ttu-id="946c2-114">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="946c2-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="946c2-115">Il PIC USL è una licenza per abbonamento per utente, per mese necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="946c2-115">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="946c2-116">Messenger.</span><span class="sxs-lookup"><span data-stu-id="946c2-116">Messenger.</span></span> <span data-ttu-id="946c2-117">La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto da Yahoo!, l'accordo sottostante per il quale non verrà rinnovato.</span><span class="sxs-lookup"><span data-stu-id="946c2-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="946c2-118">Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="946c2-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="946c2-119">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="946c2-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="946c2-120">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone tramite messaggistica istantanea e voce.</span><span class="sxs-lookup"><span data-stu-id="946c2-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="946c2-121">Questa classe di federazione richiede le seguenti considerazioni sulla pianificazione:</span><span class="sxs-lookup"><span data-stu-id="946c2-121">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="946c2-122">Gli utenti di Windows Live Messenger possono avere comunicazioni audio/visive peer-to-peer con gli utenti di Lync Server 2013, oltre alla messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="946c2-122">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="946c2-123">Gli Edge Server devono soddisfare requisiti specifici per la porta e il protocollo.</span><span class="sxs-lookup"><span data-stu-id="946c2-123">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="946c2-124">Per informazioni dettagliate, vedere [determinare i requisiti del firewall e della porta a/V esterni per Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="946c2-124">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="946c2-125">La messaggistica istantanea di Yahoo non ha requisiti univoci, ad eccezione di quelli usati in genere nella pianificazione e distribuzione del server perimetrale tipico che fornisce la Federazione.</span><span class="sxs-lookup"><span data-stu-id="946c2-125">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="946c2-126">America Online richiede che il certificato Edge Server assegnato al servizio Access Edge disponga di un utilizzo di chiave avanzata client (EKU).</span><span class="sxs-lookup"><span data-stu-id="946c2-126">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="946c2-127">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="946c2-127">In This Section</span></span>

  - [<span data-ttu-id="946c2-128">Riepilogo del certificato-connettività di messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="946c2-128">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [<span data-ttu-id="946c2-129">Riepilogo della porta-connettività di messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="946c2-129">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - <span data-ttu-id="946c2-130">[Riepilogo DNS-connettività di messaggistica istantanea pubblica in Lync Server 2013](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="946c2-130">[DNS summary - Public instant messaging connectivity in Lync Server 2013](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

