---
title: 'Lync Server 2013: Panoramica del servizio E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67a1f0a5e36b4905cab14fd0aa320d7c8f5c606c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="c3dc2-102">Panoramica del servizio E9-1-1 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3dc2-102">Overview of E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3dc2-103">_**Ultimo argomento modificato:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="c3dc2-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="c3dc2-104">Microsoft Lync Server 2013 supporta la chiamata avanzata 9-1-1 (E9-1-1) dai client Lync e dai dispositivi Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-104">Microsoft Lync Server 2013 supports Enhanced 9-1-1 (E9-1-1) calling from Lync clients and Lync Phone Edition devices.</span></span> <span data-ttu-id="c3dc2-105">Quando si configura Lync Server per il servizio E9-1-1, le chiamate di emergenza effettuate da Lync 2013 o Lync Phone Edition includono le informazioni di Emergency Response Location (elfi) dal database dei servizi di informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-105">When you configure Lync Server for E9-1-1, emergency calls placed from Lync 2013 or Lync Phone Edition include Emergency Response Location (ERL) information from the Location Information service database.</span></span> <span data-ttu-id="c3dc2-106">Le informazioni ERL includono gli indirizzi civici (ovvero la via) e altri dati che consentono di individuare la posizione con maggiore precisione in edifici di uffici e altre strutture con più occupanti.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-106">ERLs consist of civic (that is, street) addresses and other information that helps to identify a more precise location in office buildings and other multitenant facilities.</span></span> <span data-ttu-id="c3dc2-107">Quando un utente effettua una chiamata di emergenza, Lync Server instrada l'audio della chiamata, insieme al percorso e alle informazioni di callback, tramite un Mediation Server a un provider di servizi E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-107">When a user makes an emergency call, Lync Server routes the call audio, along with the location and callback information, through a Mediation Server to an E9-1-1 service provider.</span></span> <span data-ttu-id="c3dc2-108">Tale provider utilizza l'indirizzo civico del chiamante per instradare la chiamata al centro di raccolta delle chiamate di emergenza (PSAP) responsabile per l'area in cui si trova il chiamante, quindi invia la chiave di query del servizio di emergenza (ESQK, Emergency Service Query Key) che verrà utilizzata dal centro PSAP per cercare le informazioni ERL del chiamante.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-108">The E9-1-1 service provider uses the civic address of the caller to route the call to the Public Safety Answering Point (PSAP) that serves the caller's location, and sends along an Emergency Service Query Key (ESQK) that the PSAP uses to look up the caller's ERL.</span></span>

<span data-ttu-id="c3dc2-109">Lync Server supporta due metodi per il routing delle chiamate di emergenza a un provider di servizi E9-1-1:</span><span class="sxs-lookup"><span data-stu-id="c3dc2-109">Lync Server supports two methods for routing emergency calls to an E9-1-1 service provider:</span></span>

  - <span data-ttu-id="c3dc2-110">Una connessione trunk SIP (Session Initiation Protocol) a un provider di servizi E9-1-1 qualificato</span><span class="sxs-lookup"><span data-stu-id="c3dc2-110">A Session Initiation Protocol (SIP) trunk connection to a qualified E9-1-1 service provider</span></span>

  - <span data-ttu-id="c3dc2-111">Un gateway ELIN (Emergency Location Identification Number) a un provider di servizi E9-1-1 basato su PSTN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="c3dc2-111">An Emergency Location Identification Number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider</span></span>

<span data-ttu-id="c3dc2-112">Quando si utilizza un provider di servizi E9-1-1 trunk SIP, è possibile aggiungere posizioni ERL al database del servizio informazioni percorso e quindi convalidare le posizioni in base a una guida (allo stradario generale) gestita dal provider di servizi E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-112">When you use a SIP trunk E9-1-1 service provider, you add ERLs to the Location Information service database, and then validate the locations against a Master Street Address Guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span> <span data-ttu-id="c3dc2-113">Se un provider di servizi E9-1-1 riceve una chiamata senza informazioni sulla posizione o con una posizione che non può essere verificata nello stradario, il provider instrada la chiamata a un centro di risposta alle chiamate di emergenza (ECRC) nazionale/regionale con personale formato appositamente che tenta di ottenere la posizione del chiamante verbalmente, se possibile, e instrada manualmente la chiamata al centro PSAP appropriato.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-113">If an E9-1-1 service provider receives a call that doesn’t have location information or has a location that has not been validated against the MSAG, the E9-1-1 service provider routes the call to a national/regional Emergency Call Response Center (ECRC), which is staffed with specially trained personnel who verbally obtain the caller’s location, if possible, and manually route the call to the appropriate PSAP.</span></span> <span data-ttu-id="c3dc2-114">Alcuni provider di servizi E9-1-1 su trunk SIP inoltre forniscono ai clienti un numero DID (Direct Inward Dialing) PSTN per il centro ECRC, offrendo un mezzo alternativo per il routing delle chiamate 9-1-1 in caso di malfunzionamento del trunk SIP per un motivo qualsiasi.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-114">(Some SIP trunk E9-1-1 service providers also provide customers with a PSTN direct inward dialing (DID) number to the ECRC, which provides an alternate means of routing 9-1-1 calls, if the SIP trunk fails for any reason.)</span></span>

<span data-ttu-id="c3dc2-115">A differenza del TDM (Time Division Multiplexing) e dei telefoni PBX (Private Branch Exchange) basati su IP, che dispongono di posizioni fisse, un endpoint Lync può essere molto mobile.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-115">Unlike time division multiplexing (TDM) and IP-based private branch exchange (PBX) phones, which have fixed locations, a Lync endpoint can be very mobile.</span></span> <span data-ttu-id="c3dc2-116">Quando si distribuisce la funzionalità E9-1-1, Lync Server consente di garantire che non vi siano informazioni sul luogo in cui si trova il chiamante, la chiamata di emergenza può essere instradata al PSAP che serve la posizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-116">When you deploy the E9-1-1 feature, Lync Server helps to ensure that no matter where a caller is located, the emergency call can be routed to the PSAP that serves the caller’s location.</span></span> <span data-ttu-id="c3dc2-117">Se l'ufficio principale dell'utente si trova a Milano, ma l'utente effettua una chiamata di emergenza da un computer in una succursale a Roma, il provider di servizi E9-1-1 su PSTN o su trunk SIP instraderà la chiamata al centro PSAP di Roma e non a quello di Milano.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-117">For example, if a user’s main office is located in Redmond, Washington, but the user places an emergency call from a computer in a branch office in Wichita, Kansas, the SIP trunk or PSTN-based E9-1-1 service provider will route the call to the PSAP in Wichita, not to the PSAP in Redmond.</span></span>

<span data-ttu-id="c3dc2-118">Quando si utilizza un gateway ELIN, è inoltre possibile aggiungere posizioni ERL al database del servizio informazioni percorso, ma è anche necessario includere un numero ELIN per ogni percorso.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-118">When you use an ELIN gateway, you also add ERLs to the Location Information service database, but you include also an ELIN number for each location.</span></span> <span data-ttu-id="c3dc2-119">Il numero ELIN diventa il numero chiamante durante la chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-119">The ELIN number becomes the emergency calling number during the emergency call.</span></span> <span data-ttu-id="c3dc2-120">È quindi necessario verificare che la portante PSTN carichi i numeri ELIN nel database ALI (Automatic Location Identification).</span><span class="sxs-lookup"><span data-stu-id="c3dc2-120">You must then make sure that your PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c3dc2-121">I dispositivi analogici connessi a Lync non sono in grado di ricevere informazioni sul percorso dal servizio informazioni percorso o di trasmissione al provider di servizi E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-121">Lync-connected analog devices cannot receive location information from the Location Information service or transmit location to the E9-1-1 service provider.</span></span> <span data-ttu-id="c3dc2-122">Se si utilizzata l'opzione del provider di servizi E9-1-1 su trunk SIP ed è necessario supportare i servizi E9-1-1 da telefoni analogici, sono disponibili due opzioni:</span><span class="sxs-lookup"><span data-stu-id="c3dc2-122">If you use the SIP trunk E9-1-1 service provider option and need to support E9-1-1 from analog phones, you have two options:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="c3dc2-123"><STRONG></STRONG>&nbsp;Opzione&nbsp;tradizionale&nbsp;PS-Ali se si dispone di gateway PSTN locali in ogni sito in cui vengono distribuiti telefoni analogici e che ogni telefono analogico ha un did, è possibile eseguire il provisioning della posizione del dispositivo analogico direttamente con un provider di servizi switch privato/rilevamento automatico località (PS-Ali).</span><span class="sxs-lookup"><span data-stu-id="c3dc2-123"><STRONG>Traditional PS-ALI option</STRONG>&nbsp;&nbsp;&nbsp;If you have local PSTN gateways at each site where analog phones are deployed and each analog phone has a DID, you can provision the analog device’s location directly with a Private Switch/Automatic Location Identification (PS-ALI) service provider.</span></span> <span data-ttu-id="c3dc2-124">In questo caso, è necessario configurare criteri vocali di Lync appositi e assegnarli agli oggetti contatto dei dispositivi analogici, in modo che le chiamate E9-1-1 da tali telefoni vengano instradate direttamente tramite il gateway locale al provider PSTN che fornisce i servizi al sito, anziché instradare la chiamata al trunk SIP di un provider di servizi E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-124">In this case, you configure specially-crafted Lync voice policies and assign them to the analog device contact objects so that E9-1-1 calls from those phones route directly through the local gateway to the PSTN provider that services the site (instead of routing the call to an E9-1-1 service provider SIP trunk).</span></span> <span data-ttu-id="c3dc2-125">Quando viene effettuata una chiamata di emergenza, un database presso un provider PS-ALI associato al trunk PSTN mappa il DID di ogni telefono analogico a una posizione fisica, quindi fornisce tale posizione al centro PSAP.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-125">When an emergency call is placed, a database at a PS-ALI provider that is associated with the PSTN trunk maps the DID of each analog phone to a physical location and provides this location to the PSAP.</span></span> <span data-ttu-id="c3dc2-126">Questi record devono essere aggiornati presso il provider di servizi PS-ALI ogni volta che i telefoni vengono spostati in posizioni ERL diverse.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-126">These records must be updated with the PS-ALI service provider every time phones are moved to different ERLs.</span></span></P>
> <LI>
> <P><span data-ttu-id="c3dc2-127"><STRONG></STRONG>&nbsp;Opzione&nbsp;del&nbsp;provider di servizi E9-1-1 è possibile registrare le DIDs del telefono analogico e le corrispondenti posizioni ERL con il provider di servizi E9-1-1, se questo è supportato dal provider di servizi E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-127"><STRONG>E9-1-1 service provider option</STRONG>&nbsp;&nbsp;&nbsp;You can register the analog phone DIDs and their corresponding ERLs with the E9-1-1 service provider, if this is supported by the E9-1-1 service provider.</span></span> <span data-ttu-id="c3dc2-128">Se il provider riceve una chiamata da Lync Server che non include dati di PIDF-LO, il provider può vedere se esiste una corrispondenza di database sul numero DID della parte chiamante.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-128">If the provider receives a call from Lync Server that doesn’t include PIDF-LO data, the provider can see if there is a database match on the calling party’s DID number.</span></span> <span data-ttu-id="c3dc2-129">In base alle informazioni ERL recuperate dal database, il provider può instradare automaticamente la chiamata di emergenza al centro PSAP corretto, che riceverà il DID del dispositivo analogico e un record ESQK che consente al dispatcher di cercare la posizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-129">By using the ERL retrieved from its database, the provider can automatically route the emergency call to the correct PSAP, and the PSAP will receive the DID of the analog device and an ESQK record that allows the dispatcher to lookup the caller’s location.</span></span></P></LI></UL><span data-ttu-id="c3dc2-p108">Se si utilizza l'opzione del gateway ELIN ed è necessario supportare i servizi E9-1-1 da telefoni analogici, è possibile eseguire il provisioning della posizione del dispositivo analogico direttamente con il provider di servizi PS-ALI, come descritto in precedenza nella prima opzione.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-p108">If you use the ELIN gateway option and need to support E9-1-1 from analog phones, you can provision the analog device's location directly with the PS-ALI service provider, as described in the first option above.    </span></span></div>

<span data-ttu-id="c3dc2-131">Dal punto di vista di Lync Server, il processo di E9-1-1 può essere suddiviso in due fasi:</span><span class="sxs-lookup"><span data-stu-id="c3dc2-131">From a Lync Server perspective, the E9-1-1 process can be separated into two stages:</span></span>

  - <span data-ttu-id="c3dc2-132">Fase 1: acquisizione di una posizione</span><span class="sxs-lookup"><span data-stu-id="c3dc2-132">Stage 1: Acquiring a location</span></span>

  - <span data-ttu-id="c3dc2-133">Fase 2: instradamento della chiamata di emergenza a un provider di servizi E9-1-1</span><span class="sxs-lookup"><span data-stu-id="c3dc2-133">Stage 2: Routing the emergency call to an E9-1-1 service provider</span></span>

<span data-ttu-id="c3dc2-134">In questa sezione viene descritto il funzionamento di queste due fasi.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-134">This section describes how these stages work.</span></span>

<span data-ttu-id="c3dc2-135">Se si prevede di configurare l'infrastruttura per il rilevamento automatico della posizione dei client, è innanzitutto necessario decidere quali elementi di rete verranno utilizzati per il mapping tra chiamanti e posizioni.</span><span class="sxs-lookup"><span data-stu-id="c3dc2-135">If you plan to configure your infrastructure to automatically detect client location, first you need to decide which network elements you will use to map callers to locations.</span></span> <span data-ttu-id="c3dc2-136">Per informazioni dettagliate sulle possibili opzioni, vedere [definizione degli elementi di rete utilizzati per determinare la posizione in Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span><span class="sxs-lookup"><span data-stu-id="c3dc2-136">For details about the possible options, see [Defining the network elements used to determine location in Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c3dc2-137">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="c3dc2-137">In This Section</span></span>

  - [<span data-ttu-id="c3dc2-138">Acquisizione di una posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3dc2-138">Acquiring a location in Lync Server 2013</span></span>](lync-server-2013-acquiring-a-location.md)

  - [<span data-ttu-id="c3dc2-139">Routing delle chiamate al servizio E9-1-1 tramite un trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3dc2-139">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [<span data-ttu-id="c3dc2-140">Routing delle chiamate al servizio E9-1-1 tramite un gateway ELIN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3dc2-140">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

