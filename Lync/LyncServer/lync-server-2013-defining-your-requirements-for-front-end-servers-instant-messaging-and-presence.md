---
title: 'Lync Server 2013: definizione dei requisiti per Front End Server, messaggistica istantanea e presenza'
description: 'Lync Server 2013: definizione dei requisiti per Front End Server, messaggistica istantanea e presenza.'
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
ms.openlocfilehash: 923132b32d5aef80191b19a7b85c3f17276e5946
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545372"
---
# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="2c429-103">Definizione dei requisiti per Front End Server, messaggistica istantanea e presenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c429-103">Defining your requirements for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c429-104">_**Ultimo argomento modificato:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="2c429-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="2c429-105">L'attività principale di pianificazione per la messaggistica istantanea e la presenza è garantire che i Front End Server siano sufficienti per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="2c429-105">The main task of planning for instant messaging (IM) and presence is ensuring that you have enough Front End Servers for your users.</span></span>

<div>

## <a name="enabling-communication-with-external-users"></a><span data-ttu-id="2c429-106">Abilitazione delle comunicazioni con gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="2c429-106">Enabling Communication with External Users</span></span>

<span data-ttu-id="2c429-107">È possibile aumentare notevolmente i vantaggi derivanti dall'investimento in Lync Server, consentendo agli utenti di comunicare con utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="2c429-107">You can greatly increase the benefits of your investment in Lync Server by enabling your users to communicate with external users.</span></span> <span data-ttu-id="2c429-108">Gli utenti esterni possono essere:</span><span class="sxs-lookup"><span data-stu-id="2c429-108">External users can include:</span></span>

  - <span data-ttu-id="2c429-109">**Utenti**     remoti Gli utenti dell'organizzazione, quando lavorano all'esterno dei firewall e utilizzano i laptop o altri dispositivi di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2c429-109">**Remote users**   Your organization’s own users, when they are working outside your firewalls and are using their laptops or other Lync Server devices.</span></span>

  - <span data-ttu-id="2c429-110">**Utenti federati**     Utenti provenienti da società con cui si lavora, che eseguono anche Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2c429-110">**Federated users**   Users from companies you work with who also run Lync Server.</span></span> <span data-ttu-id="2c429-111">Per consentire agli utenti di mettersi facilmente in contatto con questi utenti, si creano relazioni federate con le relative società.</span><span class="sxs-lookup"><span data-stu-id="2c429-111">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span>

  - <span data-ttu-id="2c429-112">**Utenti pubblici**     Gli utenti di servizi di messaggistica istantanea pubblica, ad esempio i servizi di messaggistica istantanea forniti dalla rete Windows Live di servizi Internet, Yahoo \! e AOL, e gli utenti di provider e server che utilizzano il protocollo XMPP (Extensible Messaging and Presence Protocol), ad esempio Google Talk.</span><span class="sxs-lookup"><span data-stu-id="2c429-112">**Public users**   Users of public IM services, such as IM services provided by the Windows Live network of Internet services, Yahoo\!, and AOL, and users of providers and servers that use Extensible Messaging and Presence Protocol (XMPP), such as Google Talk.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2c429-113">Si noti che potrebbe essere necessaria una licenza separata per la connettività per messaggistica istantanea pubblica con Windows Live, AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="2c429-113">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo!</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="2c429-114">Al 1 ° settembre 2012, la licenza di sottoscrizione di Microsoft Lync Public IM Connectivity ("PIC USL") non è più disponibile per l'acquisto dei contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="2c429-114">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="2c429-115">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="2c429-115">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="2c429-116">Messenger fino alla data di arresto del servizio.</span><span class="sxs-lookup"><span data-stu-id="2c429-116">Messenger until the service shut down date.</span></span> <span data-ttu-id="2c429-117">Una data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="2c429-117">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="2c429-118">sono stati annunciati.</span><span class="sxs-lookup"><span data-stu-id="2c429-118">has been announced.</span></span> <span data-ttu-id="2c429-119">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2c429-119">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="2c429-120">Il PIC USL è una licenza per ogni utente per ogni mese che è necessaria per Lync Server o Office Communications Server per la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="2c429-120">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="2c429-121">Messaggero.</span><span class="sxs-lookup"><span data-stu-id="2c429-121">Messenger.</span></span> <span data-ttu-id="2c429-122">La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale si sta liquidando.</span><span class="sxs-lookup"><span data-stu-id="2c429-122">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="2c429-123">Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="2c429-123">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="2c429-124">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="2c429-124">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="2c429-125">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</span><span class="sxs-lookup"><span data-stu-id="2c429-125">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="2c429-126">Per abilitare uno o tutti questi scenari, è necessario distribuire un server perimetrale per consentire le comunicazioni protette tra la distribuzione di Lync Server e gli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="2c429-126">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Lync Server deployment and external users.</span></span> <span data-ttu-id="2c429-127">Gli utenti remoti e le organizzazioni remote dell'organizzazione saranno in grado di visualizzare gli altri utenti e comunicare tramite messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="2c429-127">Your organization’s remote users and users at federated organizations will be able to see each other’s presence and communicate using IM.</span></span> <span data-ttu-id="2c429-128">Per informazioni dettagliate sull'abilitazione della comunicazione con gli utenti esterni, vedere [Planning for External User Access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2c429-128">For details about enabling communication with external users, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-im-content"></a><span data-ttu-id="2c429-129">Contenuto di messaggistica istantanea di archiviazione</span><span class="sxs-lookup"><span data-stu-id="2c429-129">Archiving IM Content</span></span>

<span data-ttu-id="2c429-130">Lync Server fornisce caratteristiche che è possibile utilizzare se l'organizzazione deve rispettare le normative di conformità.</span><span class="sxs-lookup"><span data-stu-id="2c429-130">Lync Server provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="2c429-131">È possibile utilizzare l'archiviazione per archiviare il contenuto dei messaggi di messaggistica istantanea per tutti gli utenti dell'organizzazione o solo per alcuni utenti specificati.</span><span class="sxs-lookup"><span data-stu-id="2c429-131">You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify.</span></span> <span data-ttu-id="2c429-132">Per informazioni dettagliate, vedere [Planning for archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2c429-132">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="2c429-133">Se si dispone anche di Microsoft Exchange Server 2013 distribuito, è possibile integrare l'archiviazione dei dati di Exchange con l'archiviazione dei dati di Lync Server e utilizzare un singolo strumento per eseguire la ricerca di entrambi i tipi di dati archiviati.</span><span class="sxs-lookup"><span data-stu-id="2c429-133">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Lync Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="2c429-134">Per ulteriori informazioni, vedere [configurazione di Microsoft Lync server 2013 per l'utilizzo dell'archiviazione di Microsoft Exchange server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="2c429-134">For more information, see [Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

