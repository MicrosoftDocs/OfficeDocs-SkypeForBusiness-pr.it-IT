---
title: 'Lync Server 2013: Panoramica dei servizi di emergenza'
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
ms.openlocfilehash: 48b261ed0b173c85ccd076be14d65aa456558830
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="8d840-102">Panoramica dei servizi di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d840-102">Overview of E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d840-103">_**Argomento Ultima modifica:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="8d840-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="8d840-104">Microsoft Lync Server 2013 supporta le chiamate avanzate 9-1-1 (E9-1-1) dai client Lync e dai dispositivi Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="8d840-104">Microsoft Lync Server 2013 supports Enhanced 9-1-1 (E9-1-1) calling from Lync clients and Lync Phone Edition devices.</span></span> <span data-ttu-id="8d840-105">Quando si configura Lync Server per E9-1-1, le chiamate di emergenza effettuate da Lync 2013 o Lync Phone Edition includono le informazioni sulla posizione di risposta alle emergenze dal database del servizio informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="8d840-105">When you configure Lync Server for E9-1-1, emergency calls placed from Lync 2013 or Lync Phone Edition include Emergency Response Location (ERL) information from the Location Information service database.</span></span> <span data-ttu-id="8d840-106">Posizioni ERL è costituito da indirizzi civici (ovvero Street) e altre informazioni utili per identificare una posizione più precisa negli edifici di Office e in altre strutture multitenant.</span><span class="sxs-lookup"><span data-stu-id="8d840-106">ERLs consist of civic (that is, street) addresses and other information that helps to identify a more precise location in office buildings and other multitenant facilities.</span></span> <span data-ttu-id="8d840-107">Quando un utente effettua una chiamata di emergenza, Lync Server instrada l'audio della chiamata, insieme alla posizione e alle informazioni di callback, tramite un Mediation Server a un provider di servizi E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="8d840-107">When a user makes an emergency call, Lync Server routes the call audio, along with the location and callback information, through a Mediation Server to an E9-1-1 service provider.</span></span> <span data-ttu-id="8d840-108">Il provider di servizi E9-1-1 USA l'indirizzo civico del chiamante per instradare la chiamata al punto di PSAP (Public Safety Answering Point) che serve la posizione del chiamante e invia lungo una chiave di query del servizio di emergenza (ESQK) che PSAP USA per cercare gli Elfi del chiamante.</span><span class="sxs-lookup"><span data-stu-id="8d840-108">The E9-1-1 service provider uses the civic address of the caller to route the call to the Public Safety Answering Point (PSAP) that serves the caller's location, and sends along an Emergency Service Query Key (ESQK) that the PSAP uses to look up the caller's ERL.</span></span>

<span data-ttu-id="8d840-109">Lync Server supporta due metodi per il routing delle chiamate di emergenza a un provider di servizi E9-1-1:</span><span class="sxs-lookup"><span data-stu-id="8d840-109">Lync Server supports two methods for routing emergency calls to an E9-1-1 service provider:</span></span>

  - <span data-ttu-id="8d840-110">Connessione trunk SIP (Session Initiation Protocol) a un provider di servizi E9-1-1 qualificato</span><span class="sxs-lookup"><span data-stu-id="8d840-110">A Session Initiation Protocol (SIP) trunk connection to a qualified E9-1-1 service provider</span></span>

  - <span data-ttu-id="8d840-111">Un gateway ELIN (Emergency Location Identification Number) a un provider di servizi E9-1-1 Basato su PSTN (Public Switched Telephone)</span><span class="sxs-lookup"><span data-stu-id="8d840-111">An Emergency Location Identification Number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider</span></span>

<span data-ttu-id="8d840-112">Quando si usa un provider di servizi E9-1-1 trunk SIP, è possibile aggiungere posizioni ERL al database del servizio informazioni sulla posizione e quindi convalidare le posizioni in base a una guida all'indirizzo Master Street (stradario) gestita dal provider di servizi E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="8d840-112">When you use a SIP trunk E9-1-1 service provider, you add ERLs to the Location Information service database, and then validate the locations against a Master Street Address Guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span> <span data-ttu-id="8d840-113">Se un provider di servizi E9-1-1 riceve una chiamata che non ha informazioni sulla posizione o ha una posizione che non è stata convalidata rispetto a stradario, il provider di servizi E9-1-1 instrada la chiamata a un centro di risposta alle chiamate di emergenza nazionale/regionale (ECRC), con personale specializzato che ottiene verbalmente la posizione del chiamante, se possibile, e instrada manualmente la chiamata al PSAP appropriato.</span><span class="sxs-lookup"><span data-stu-id="8d840-113">If an E9-1-1 service provider receives a call that doesn’t have location information or has a location that has not been validated against the MSAG, the E9-1-1 service provider routes the call to a national/regional Emergency Call Response Center (ECRC), which is staffed with specially trained personnel who verbally obtain the caller’s location, if possible, and manually route the call to the appropriate PSAP.</span></span> <span data-ttu-id="8d840-114">Alcuni provider di servizi E9-1-1 del trunk SIP forniscono anche ai clienti un numero di chiamate PSTN Direct inwarding (DID) per il ECRC, che fornisce un mezzo alternativo per il routing delle telefonate di 9-1-1, se il trunk SIP non riesce per qualsiasi motivo.</span><span class="sxs-lookup"><span data-stu-id="8d840-114">(Some SIP trunk E9-1-1 service providers also provide customers with a PSTN direct inward dialing (DID) number to the ECRC, which provides an alternate means of routing 9-1-1 calls, if the SIP trunk fails for any reason.)</span></span>

<span data-ttu-id="8d840-115">A differenza del TDM (Time Division Multiplexing) e dei telefoni PBX (Private Branch Exchange) basati su IP, che hanno posizioni fisse, un endpoint Lync può essere molto mobile.</span><span class="sxs-lookup"><span data-stu-id="8d840-115">Unlike time division multiplexing (TDM) and IP-based private branch exchange (PBX) phones, which have fixed locations, a Lync endpoint can be very mobile.</span></span> <span data-ttu-id="8d840-116">Quando si distribuisce la funzionalità E9-1-1, Lync Server garantisce che non importa dove si trova un chiamante, la chiamata di emergenza può essere instradata al PSAP che serve la posizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="8d840-116">When you deploy the E9-1-1 feature, Lync Server helps to ensure that no matter where a caller is located, the emergency call can be routed to the PSAP that serves the caller’s location.</span></span> <span data-ttu-id="8d840-117">Ad esempio, se l'ufficio principale di un utente si trova a Redmond, Washington, ma l'utente inserisce una chiamata di emergenza da un computer in una filiale di Wichita, Kansas, il trunk SIP o il provider di servizi E9-1-1 Basato su PSTN instradano la chiamata a PSAP in Wichita , non al PSAP di Redmond.</span><span class="sxs-lookup"><span data-stu-id="8d840-117">For example, if a user’s main office is located in Redmond, Washington, but the user places an emergency call from a computer in a branch office in Wichita, Kansas, the SIP trunk or PSTN-based E9-1-1 service provider will route the call to the PSAP in Wichita, not to the PSAP in Redmond.</span></span>

<span data-ttu-id="8d840-118">Quando si usa un gateway ELIN, si aggiunge anche posizioni ERL al database del servizio informazioni sulla posizione, ma si include anche un numero ELIN per ogni posizione.</span><span class="sxs-lookup"><span data-stu-id="8d840-118">When you use an ELIN gateway, you also add ERLs to the Location Information service database, but you include also an ELIN number for each location.</span></span> <span data-ttu-id="8d840-119">Il numero ELIN diventa il numero delle chiamate di emergenza durante la chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="8d840-119">The ELIN number becomes the emergency calling number during the emergency call.</span></span> <span data-ttu-id="8d840-120">Devi quindi verificare che il gestore PSTN carichi i dati ELIN nel database ALI (Automatic Location Identification).</span><span class="sxs-lookup"><span data-stu-id="8d840-120">You must then make sure that your PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8d840-121">I dispositivi analogici connessi a Lync non possono ricevere informazioni sulla posizione dal servizio informazioni sulla posizione o trasmettere il percorso al provider di servizi E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="8d840-121">Lync-connected analog devices cannot receive location information from the Location Information service or transmit location to the E9-1-1 service provider.</span></span> <span data-ttu-id="8d840-122">Se si usa l'opzione del provider di servizi E9-1-1 SIP trunk ed è necessario supportare E9-1-1 da telefoni analogici, sono disponibili due opzioni:</span><span class="sxs-lookup"><span data-stu-id="8d840-122">If you use the SIP trunk E9-1-1 service provider option and need to support E9-1-1 from analog phones, you have two options:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="8d840-123"><STRONG></STRONG>&nbsp;Opzione&nbsp;tradizionale&nbsp;PS-Ali se si dispone di gateway PSTN locali in ogni sito in cui sono distribuiti telefoni analogici e ogni telefono analogico ha un servizio, è possibile eseguire il provisioning della posizione del dispositivo analogico direttamente con un provider di servizi di switch privato/identificazione automatica della posizione (PS-Ali).</span><span class="sxs-lookup"><span data-stu-id="8d840-123"><STRONG>Traditional PS-ALI option</STRONG>&nbsp;&nbsp;&nbsp;If you have local PSTN gateways at each site where analog phones are deployed and each analog phone has a DID, you can provision the analog device’s location directly with a Private Switch/Automatic Location Identification (PS-ALI) service provider.</span></span> <span data-ttu-id="8d840-124">In questo caso, devi configurare i criteri vocali di Lync appositamente predisposti e assegnarli agli oggetti contatto del dispositivo analogico in modo che le chiamate E9-1-1 da questi telefoni vengano indirizzate direttamente attraverso il gateway locale al provider PSTN che assiste il sito (invece di instradare il chiamata a un trunk SIP del provider di servizi E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="8d840-124">In this case, you configure specially-crafted Lync voice policies and assign them to the analog device contact objects so that E9-1-1 calls from those phones route directly through the local gateway to the PSTN provider that services the site (instead of routing the call to an E9-1-1 service provider SIP trunk).</span></span> <span data-ttu-id="8d840-125">Quando viene inserita una chiamata di emergenza, un database di un provider PS-ALI associato al trunk PSTN esegue il mapping dell'DID di ogni telefono analogico in una posizione fisica e fornisce questa posizione al PSAP.</span><span class="sxs-lookup"><span data-stu-id="8d840-125">When an emergency call is placed, a database at a PS-ALI provider that is associated with the PSTN trunk maps the DID of each analog phone to a physical location and provides this location to the PSAP.</span></span> <span data-ttu-id="8d840-126">Questi record devono essere aggiornati con il provider di servizi PS-ALI ogni volta che i telefoni vengono spostati in posizioni ERL diversi.</span><span class="sxs-lookup"><span data-stu-id="8d840-126">These records must be updated with the PS-ALI service provider every time phones are moved to different ERLs.</span></span></P>
> <LI>
> <P><span data-ttu-id="8d840-127"><STRONG></STRONG>&nbsp;Opzione&nbsp;provider&nbsp;di servizi E9-1-1 è possibile registrare il telefono analogico DIDs e il relativo posizioni ERL con il provider di servizi E9-1-1, se supportato dal provider di servizi E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="8d840-127"><STRONG>E9-1-1 service provider option</STRONG>&nbsp;&nbsp;&nbsp;You can register the analog phone DIDs and their corresponding ERLs with the E9-1-1 service provider, if this is supported by the E9-1-1 service provider.</span></span> <span data-ttu-id="8d840-128">Se il provider riceve una chiamata da Lync Server che non include dati di PIDF-LO, il provider può verificare se esiste una corrispondenza di database nel numero DID della parte chiamante.</span><span class="sxs-lookup"><span data-stu-id="8d840-128">If the provider receives a call from Lync Server that doesn’t include PIDF-LO data, the provider can see if there is a database match on the calling party’s DID number.</span></span> <span data-ttu-id="8d840-129">Usando gli elfi recuperati dal relativo database, il provider può instradare automaticamente la chiamata di emergenza al PSAP corretto e PSAP riceverà l'DID del dispositivo analogico e un record ESQK che consente al dispatcher di cercare la posizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="8d840-129">By using the ERL retrieved from its database, the provider can automatically route the emergency call to the correct PSAP, and the PSAP will receive the DID of the analog device and an ESQK record that allows the dispatcher to lookup the caller’s location.</span></span></P></LI></UL><span data-ttu-id="8d840-130">Se si usa l'opzione gateway ELIN ed è necessario supportare E9-1-1 da telefoni analogici, è possibile eseguire il provisioning della posizione del dispositivo analogico direttamente con il provider di servizi PS-ALI, come descritto nella prima opzione precedente.</span><span class="sxs-lookup"><span data-stu-id="8d840-130">If you use the ELIN gateway option and need to support E9-1-1 from analog phones, you can provision the analog device's location directly with the PS-ALI service provider, as described in the first option above.</span></span>



</div>

<span data-ttu-id="8d840-131">Dal punto di vista di Lync Server, il processo E9-1-1 può essere separato in due fasi:</span><span class="sxs-lookup"><span data-stu-id="8d840-131">From a Lync Server perspective, the E9-1-1 process can be separated into two stages:</span></span>

  - <span data-ttu-id="8d840-132">Fase 1: acquisizione di una posizione</span><span class="sxs-lookup"><span data-stu-id="8d840-132">Stage 1: Acquiring a location</span></span>

  - <span data-ttu-id="8d840-133">Fase 2: routing della chiamata di emergenza a un provider di servizi E9-1-1</span><span class="sxs-lookup"><span data-stu-id="8d840-133">Stage 2: Routing the emergency call to an E9-1-1 service provider</span></span>

<span data-ttu-id="8d840-134">Questa sezione descrive il funzionamento di queste fasi.</span><span class="sxs-lookup"><span data-stu-id="8d840-134">This section describes how these stages work.</span></span>

<span data-ttu-id="8d840-135">Se si prevede di configurare l'infrastruttura per rilevare automaticamente la posizione del client, è prima di tutto necessario decidere quali elementi di rete verranno usati per eseguire il mapping dei chiamanti alle posizioni.</span><span class="sxs-lookup"><span data-stu-id="8d840-135">If you plan to configure your infrastructure to automatically detect client location, first you need to decide which network elements you will use to map callers to locations.</span></span> <span data-ttu-id="8d840-136">Per informazioni dettagliate sulle possibili opzioni, vedere [definizione degli elementi di rete usati per determinare la posizione in Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span><span class="sxs-lookup"><span data-stu-id="8d840-136">For details about the possible options, see [Defining the network elements used to determine location in Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8d840-137">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="8d840-137">In This Section</span></span>

  - [<span data-ttu-id="8d840-138">Acquisizione di una posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d840-138">Acquiring a location in Lync Server 2013</span></span>](lync-server-2013-acquiring-a-location.md)

  - [<span data-ttu-id="8d840-139">Routing delle chiamate di emergenza tramite un trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d840-139">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [<span data-ttu-id="8d840-140">Routing delle chiamate di emergenza tramite un gateway ELIN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d840-140">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

