---
title: 'Lync Server 2013: Definizione dei requisiti per Front End Server, messaggistica istantanea e presenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af371d116948d348b49c552dfe53290c1dae1900
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="7bd0b-102">Definizione dei requisiti per Front End Server, messaggistica istantanea e presenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bd0b-102">Defining your requirements for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bd0b-103">_**Argomento Ultima modifica:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="7bd0b-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="7bd0b-104">L'attività principale di pianificazione per la messaggistica istantanea e la presenza è garantire che i server front-end siano sufficienti per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-104">The main task of planning for instant messaging (IM) and presence is ensuring that you have enough Front End Servers for your users.</span></span>

<div>

## <a name="enabling-communication-with-external-users"></a><span data-ttu-id="7bd0b-105">Abilitazione delle comunicazioni con utenti esterni</span><span class="sxs-lookup"><span data-stu-id="7bd0b-105">Enabling Communication with External Users</span></span>

<span data-ttu-id="7bd0b-106">È possibile aumentare notevolmente i vantaggi offerti dall'investimento in Lync Server, consentendo agli utenti di comunicare con utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-106">You can greatly increase the benefits of your investment in Lync Server by enabling your users to communicate with external users.</span></span> <span data-ttu-id="7bd0b-107">Gli utenti esterni possono includere:</span><span class="sxs-lookup"><span data-stu-id="7bd0b-107">External users can include:</span></span>

  - <span data-ttu-id="7bd0b-108">**Utenti remoti**   gli utenti dell'organizzazione, quando lavorano all'esterno dei firewall e usano i loro laptop o altri dispositivi Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-108">**Remote users**   Your organization’s own users, when they are working outside your firewalls and are using their laptops or other Lync Server devices.</span></span>

  - <span data-ttu-id="7bd0b-109">**Gli utenti federati**   degli utenti di aziende con cui si lavora che eseguono anche Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-109">**Federated users**   Users from companies you work with who also run Lync Server.</span></span> <span data-ttu-id="7bd0b-110">Per consentire agli utenti di contattare facilmente questi utenti, è possibile creare relazioni federate con queste società.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-110">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span>

  - <span data-ttu-id="7bd0b-111">**Utenti pubblici**   utenti di servizi di messaggistica istantanea pubblica, ad esempio i servizi di messaggistica istantanea forniti da Windows Live Network of\!Internet Services, Yahoo e AOL, e gli utenti di provider e server che usano il protocollo XMPP (Extensible Messaging and Presence Protocol), ad esempio Google Talk.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-111">**Public users**   Users of public IM services, such as IM services provided by the Windows Live network of Internet services, Yahoo\!, and AOL, and users of providers and servers that use Extensible Messaging and Presence Protocol (XMPP), such as Google Talk.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7bd0b-112">Tieni presente che potrebbe essere necessaria una licenza separata per la connettività di messaggistica istantanea pubblica con Windows Live, AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="7bd0b-112">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo!</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="7bd0b-113">A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL") non è più disponibile per l'acquisto di contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-113">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="7bd0b-114">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="7bd0b-114">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="7bd0b-115">Messenger fino alla data di chiusura del servizio.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-115">Messenger until the service shut down date.</span></span> <span data-ttu-id="7bd0b-116">Data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="7bd0b-116">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="7bd0b-117">è stato annunciato.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-117">has been announced.</span></span> <span data-ttu-id="7bd0b-118">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-118">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="7bd0b-119">Il PIC USL è una licenza per abbonamento mensile per ogni utente necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="7bd0b-119">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="7bd0b-120">Messenger.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-120">Messenger.</span></span> <span data-ttu-id="7bd0b-121">La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto di Yahoo!, l'accordo sottostante per il quale sta per finire.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-121">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="7bd0b-122">Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-122">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="7bd0b-123">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-123">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="7bd0b-124">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e voce.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-124">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="7bd0b-125">Per abilitare uno o tutti questi scenari, è necessario distribuire un server perimetrale per facilitare le comunicazioni sicure tra la distribuzione di Lync Server e gli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-125">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Lync Server deployment and external users.</span></span> <span data-ttu-id="7bd0b-126">Gli utenti e gli utenti remoti dell'organizzazione presso le organizzazioni federate potranno vedere la presenza e comunicare tramite messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-126">Your organization’s remote users and users at federated organizations will be able to see each other’s presence and communicate using IM.</span></span> <span data-ttu-id="7bd0b-127">Per informazioni dettagliate sull'abilitazione delle comunicazioni con utenti esterni, vedere [pianificazione per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-127">For details about enabling communication with external users, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-im-content"></a><span data-ttu-id="7bd0b-128">Archiviazione del contenuto di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="7bd0b-128">Archiving IM Content</span></span>

<span data-ttu-id="7bd0b-129">Lync Server offre funzionalità che possono essere usate se l'organizzazione deve seguire le regole di conformità.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-129">Lync Server provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="7bd0b-130">È possibile usare l'archiviazione per archiviare il contenuto dei messaggi di messaggistica istantanea per tutti gli utenti dell'organizzazione o solo per determinati utenti specificati.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-130">You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify.</span></span> <span data-ttu-id="7bd0b-131">Per informazioni dettagliate, vedere [pianificazione dell'archiviazione in Lync Server 2013](lync-server-2013-planning-for-archiving.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-131">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="7bd0b-132">Se è stato distribuito anche Microsoft Exchange Server 2013, è possibile integrare l'archiviazione dei dati di Exchange con l'archiviazione dei dati di Lync Server e usare un singolo strumento per eseguire ricerche in entrambi i tipi di dati archiviati.</span><span class="sxs-lookup"><span data-stu-id="7bd0b-132">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Lync Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="7bd0b-133">Per altre informazioni, vedere [configurazione di Microsoft Lync server 2013 per usare l'archiviazione di Microsoft Exchange server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="7bd0b-133">For more information, see [Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

