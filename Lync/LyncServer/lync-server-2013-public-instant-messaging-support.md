---
title: 'Lync Server 2013: Supporto per la messaggistica istantanea pubblica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public instant messaging support
ms:assetid: 1f45163b-52c6-4a78-b9c8-dfe3abe4e5eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204732(v=OCS.15)
ms:contentKeyID: 48183582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3e3207d1a7a12f4db379e4d58615cffdfb45036
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="public-instant-messaging-support-in-lync-server-2013"></a><span data-ttu-id="fe001-102">Supporto per la messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe001-102">Public instant messaging support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe001-103">_**Argomento Ultima modifica:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="fe001-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="fe001-104">Lync Server 2013 supporta l'uso dei provider di connettività di messaggistica istantanea pubblici con licenza, nonché l'uso del protocollo XMPP (eXtensible Messaging and Presence Protocol) per implementare un tipo speciale di federazione che consente a un server Lync di accedere alla configurazione XMPP partner di dominio tramite il client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="fe001-104">Lync Server 2013 supports the use of licensed public instant messaging (IM) connectivity providers, as well as the use of eXtensible Messaging and Presence Protocol (XMPP) to implement a special type of federation that enables a Lync Server to access configured XMPP domain partners by using the Lync 2013 client.</span></span>

<div>

## <a name="public-im-connectivity-provider-support"></a><span data-ttu-id="fe001-105">Supporto del provider di connettività di messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="fe001-105">Public IM Connectivity Provider Support</span></span>

<span data-ttu-id="fe001-106">I partner di connettività di messaggistica istantanea pubblica attualmente supportati sono:</span><span class="sxs-lookup"><span data-stu-id="fe001-106">The currently supported public instant messaging connectivity partners are:</span></span>

  - <span data-ttu-id="fe001-107">America Online</span><span class="sxs-lookup"><span data-stu-id="fe001-107">America Online</span></span>

  - <span data-ttu-id="fe001-108">Windows Live</span><span class="sxs-lookup"><span data-stu-id="fe001-108">Windows Live</span></span>

  - <span data-ttu-id="fe001-109">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="fe001-109">Yahoo\!</span></span>

<span data-ttu-id="fe001-110">Per le comunicazioni con gli utenti di Windows Live, Lync Server 2013 supporta la messaggistica istantanea e le chiamate audio e video peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="fe001-110">For communications with Windows Live users, Lync Server 2013 supports peer-to-peer IM and audio and video calls.</span></span> <span data-ttu-id="fe001-111">Per le comunicazioni con AOL e\!Yahoo, Lync Server 2013 supporta la messaggistica istantanea peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="fe001-111">For communications with AOL and Yahoo\!, Lync Server 2013 supports peer-to-peer IM.</span></span> <span data-ttu-id="fe001-112">Potrebbe essere necessaria una licenza separata.</span><span class="sxs-lookup"><span data-stu-id="fe001-112">A separate license may be required.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="fe001-113">A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL") non è più disponibile per l'acquisto di contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="fe001-113">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="fe001-114">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="fe001-114">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="fe001-115">Messenger fino alla data di chiusura del servizio.</span><span class="sxs-lookup"><span data-stu-id="fe001-115">Messenger until the service shut down date.</span></span> <span data-ttu-id="fe001-116">Data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="fe001-116">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="fe001-117">è stato annunciato.</span><span class="sxs-lookup"><span data-stu-id="fe001-117">has been announced.</span></span> <span data-ttu-id="fe001-118">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fe001-118">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="fe001-119">Il PIC USL è una licenza per abbonamento mensile per ogni utente necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="fe001-119">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="fe001-120">Messenger.</span><span class="sxs-lookup"><span data-stu-id="fe001-120">Messenger.</span></span> <span data-ttu-id="fe001-121">La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto di Yahoo!, l'accordo sottostante per il quale sta per finire.</span><span class="sxs-lookup"><span data-stu-id="fe001-121">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="fe001-122">Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="fe001-122">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="fe001-123">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="fe001-123">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="fe001-124">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e voce.</span><span class="sxs-lookup"><span data-stu-id="fe001-124">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="xmpp-federation-support"></a><span data-ttu-id="fe001-125">Supporto federativo XMPP</span><span class="sxs-lookup"><span data-stu-id="fe001-125">XMPP Federation Support</span></span>

<span data-ttu-id="fe001-126">La Federazione XMPP supporta le comunicazioni degli utenti di Lync con gli utenti di domini XMPP configurati che usano un provider pubblico, ad esempio GTalk.</span><span class="sxs-lookup"><span data-stu-id="fe001-126">XMPP federation supports Lync users communication with configured XMPP domain users who use a public provider, such as GTalk.</span></span> <span data-ttu-id="fe001-127">Le comunicazioni con questi utenti possono includere le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe001-127">Communications with these users can include the following:</span></span>

  - <span data-ttu-id="fe001-128">Messaggistica istantanea e presenza peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="fe001-128">Peer-to-peer IM and presence</span></span>

  - <span data-ttu-id="fe001-129">Creazione di contatti federati XMPP nel client Lync</span><span class="sxs-lookup"><span data-stu-id="fe001-129">Creation of XMPP federated contacts in the Lync client</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

