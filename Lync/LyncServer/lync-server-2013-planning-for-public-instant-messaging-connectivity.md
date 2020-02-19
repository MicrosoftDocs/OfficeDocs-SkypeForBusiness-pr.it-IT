---
title: 'Lync Server 2013: pianificazione della connettività per la messaggistica istantanea pubblica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06b650b277e10214be35414568f2c539f8dd21b3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="dc1b3-102">Pianificazione della connettività per la messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc1b3-102">Planning for public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc1b3-103">_**Ultimo argomento modificato:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="dc1b3-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="dc1b3-104">La connettività per la messaggistica istantanea pubblica è una classe di federazione ed è configurata per consentire agli utenti interni ed esterni di Lync Server 2013 di aggiungere contatti da uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="dc1b3-104">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="dc1b3-105">Contatti di Messenger</span><span class="sxs-lookup"><span data-stu-id="dc1b3-105">Messenger contacts</span></span>

  - <span data-ttu-id="dc1b3-106">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="dc1b3-106">Yahoo\!</span></span> <span data-ttu-id="dc1b3-107">contatti</span><span class="sxs-lookup"><span data-stu-id="dc1b3-107">contacts</span></span>

  - <span data-ttu-id="dc1b3-108">Contatti di AOL (America Online)</span><span class="sxs-lookup"><span data-stu-id="dc1b3-108">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="dc1b3-109">Al 1 ° settembre 2012, la licenza di sottoscrizione a Microsoft Lync Public IM Connectivity (PIC USL) non è più disponibile per l'acquisto dei contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="dc1b3-110">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="dc1b3-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="dc1b3-111">Messenger fino alla data di arresto del servizio.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-111">Messenger until the service shutdown date.</span></span> <span data-ttu-id="dc1b3-112">Una data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="dc1b3-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="dc1b3-113">sono stati annunciati.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-113">has been announced.</span></span> <span data-ttu-id="dc1b3-114">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="dc1b3-115">Il PIC USL è una licenza di sottoscrizione per utente, per mese, necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="dc1b3-115">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="dc1b3-116">Messaggero.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-116">Messenger.</span></span> <span data-ttu-id="dc1b3-117">La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale non verrà rinnovato.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="dc1b3-118">Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="dc1b3-119">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="dc1b3-120">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone attraverso la messaggistica istantanea e la voce.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="dc1b3-121">Per questa classe di federazione è necessario tenere conto delle considerazioni seguenti per la pianificazione:</span><span class="sxs-lookup"><span data-stu-id="dc1b3-121">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="dc1b3-122">Gli utenti di Windows Live Messenger possono avere comunicazioni audio/visive peer-to-peer con gli utenti di Lync Server 2013, oltre alla messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-122">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="dc1b3-123">I server perimetrali devono soddisfare requisiti specifici per le porte e i protocolli.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-123">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="dc1b3-124">Per informazioni dettagliate, vedere [Determine External a/V firewall and Port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc1b3-124">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="dc1b3-125">La messaggistica istantanea Yahoo non ha requisiti univoci, oltre a quelli utilizzati in genere nella pianificazione e nella distribuzione del server perimetrale tipico che fornisce la Federazione.</span><span class="sxs-lookup"><span data-stu-id="dc1b3-125">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="dc1b3-126">America Online richiede che il certificato del server perimetrale assegnato al servizio Access Edge disponga di un utilizzo chiave avanzato (EKU, client Enhanced Key Usage).</span><span class="sxs-lookup"><span data-stu-id="dc1b3-126">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dc1b3-127">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="dc1b3-127">In This Section</span></span>

  - [<span data-ttu-id="dc1b3-128">Riepilogo dei certificati-connettività per la messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc1b3-128">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [<span data-ttu-id="dc1b3-129">Riepilogo delle porte-connettività per la messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc1b3-129">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - <span data-ttu-id="dc1b3-130">[Riepilogo DNS-connettività per la messaggistica istantanea pubblica in Lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="dc1b3-130">[DNS summary - Public instant messaging connectivity in Lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

