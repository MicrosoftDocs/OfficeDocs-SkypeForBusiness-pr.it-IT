---
title: 'Lync Server 2013: route vocali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 350b64c15b0819813b8287bb9b40272845f3a285
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-routes-in-lync-server-2013"></a><span data-ttu-id="49052-102">Route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49052-102">Voice routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49052-103">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="49052-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="49052-104">Route di chiamata specificare in che modo Lync Server gestisce le chiamate in uscita effettuate dagli utenti di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="49052-104">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="49052-105">Quando un utente compone un numero, il front end Server normalizza la stringa di composizione nel formato E. 164, se necessario, e tenta di corrispondere a un URI SIP.</span><span class="sxs-lookup"><span data-stu-id="49052-105">When a user dials a number, the Front End Server normalizes the dial string to E.164 format, if necessary, and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="49052-106">Se il server non riesce a effettuare l'associazione, applica la logica di routing delle chiamate in uscita in base al numero.</span><span class="sxs-lookup"><span data-stu-id="49052-106">If the server cannot make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="49052-107">Il passaggio finale della definizione della logica consiste nel creare una route di chiamata denominata separata per ogni insieme di numeri di telefono di destinazione elencati in ogni dial plan.</span><span class="sxs-lookup"><span data-stu-id="49052-107">The final step in defining that logic is to create a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="49052-108">Prima di definire le route delle chiamate in uscita, è necessario completare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="49052-108">Before you define outbound call routes, you should complete the following steps:</span></span>

  - <span data-ttu-id="49052-109">Distribuire uno o più trunk.</span><span class="sxs-lookup"><span data-stu-id="49052-109">Deploy one or more trunks.</span></span>

  - <span data-ttu-id="49052-110">Creare dial plan in base alle necessità per siti, individui e oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="49052-110">Create dial plans as needed for sites, individuals, and Contact objects.</span></span>

  - <span data-ttu-id="49052-111">Creare record di utilizzo PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="49052-111">Create public switched telephone network (PSTN) usage records.</span></span>

<span data-ttu-id="49052-p102">Per abilitare il routing delle chiamate in uscita, è inoltre necessario creare e assegnare uno o più criteri vocali. È possibile eseguire questa attività prima o dopo avere definito le route delle chiamate in uscita.</span><span class="sxs-lookup"><span data-stu-id="49052-p102">Additionally, to enable outbound call routing, you must create and assign one or more voice policies. You can do this either before or after you define outbound call routes.</span></span>

<span data-ttu-id="49052-114">Per ogni route, è necessario specificare:</span><span class="sxs-lookup"><span data-stu-id="49052-114">For each route, you must specify:</span></span>

  - <span data-ttu-id="49052-115">Un nome in base al quale la route possa essere facilmente identificata.</span><span class="sxs-lookup"><span data-stu-id="49052-115">A name by which the route can be easily identified.</span></span>

  - <span data-ttu-id="49052-116">Una descrizione facoltativa per i casi in cui il nome da solo potrebbe non essere sufficiente per descrivere la route.</span><span class="sxs-lookup"><span data-stu-id="49052-116">An optional description in cases where the name alone may not be sufficient to describe the route.</span></span>

  - <span data-ttu-id="49052-117">Il formato di corrispondenza dell'espressione regolare per l'identificazione dei numeri di telefono di destinazione a cui è applicata la route e le eccezioni a cui il formato di corrispondenza non deve essere applicato.</span><span class="sxs-lookup"><span data-stu-id="49052-117">The regular expression matching pattern that identifies the destination phone numbers to which the route is applied, along with exceptions to which the matching pattern is not to be applied.</span></span>

  - <span data-ttu-id="49052-118">Uno o più trunk che si desidera assegnare alla route.</span><span class="sxs-lookup"><span data-stu-id="49052-118">One or more trunks that you want to assign to the route.</span></span>

  - <span data-ttu-id="49052-119">I record di utilizzo PSTN di cui gli utenti devono disporre per chiamare i numeri corrispondenti all'espressione regolare dei numeri di telefono di destinazione.</span><span class="sxs-lookup"><span data-stu-id="49052-119">The PSTN usage records that users must have in order to call numbers matching the destination phone number regular expression.</span></span>

<span data-ttu-id="49052-120">È possibile specificare le route di chiamata nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="49052-120">You can specify call routes in the Lync Server Control Panel.</span></span> <span data-ttu-id="49052-121">Queste route di chiamata popolano la tabella di routing del server, che Lync Server utilizza per instradare le chiamate destinate alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="49052-121">These call routes populate the server routing table, which Lync Server uses to route calls that are destined for the PSTN.</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="49052-122">Supporto dei trunk M:N</span><span class="sxs-lookup"><span data-stu-id="49052-122">M:N Trunk Support</span></span>

<span data-ttu-id="49052-123">Lync Server fornisce flessibilità per il modo in cui le chiamate vengono instradate alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="49052-123">Lync Server provides flexibility in how calls are routed to the PSTN.</span></span> <span data-ttu-id="49052-124">Una route vocale specifica un insieme di trunk alla rete PSTN che possono essere utilizzati per una determinata chiamata vocale.</span><span class="sxs-lookup"><span data-stu-id="49052-124">A voice route specifies a set of trunks to the PSTN that can be used for a particular voice call.</span></span> <span data-ttu-id="49052-125">Un trunk associa un Mediation Server e un numero di porta con un gateway PSTN e un numero di porta di attesa.</span><span class="sxs-lookup"><span data-stu-id="49052-125">A trunk associates a Mediation Server and a port number with a PSTN gateway and listening port number.</span></span> <span data-ttu-id="49052-126">Questa associazione logica consente a un Mediation Server di essere associato a più gateway e di disporre di più connessioni allo stesso gateway.</span><span class="sxs-lookup"><span data-stu-id="49052-126">This logical association enables a Mediation Server to be associated with multiple gateways and have multiple connections to the same gateway.</span></span> <span data-ttu-id="49052-127">Quando si definisce una route di chiamata, è necessario specificare i trunk associati a tale route, ma non si specifica quali Mediation Server sono associati alla route.</span><span class="sxs-lookup"><span data-stu-id="49052-127">When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with the route.</span></span> <span data-ttu-id="49052-128">Per creare trunk definendo le relazioni tra Mediation Server e gateway PSTN, IP-PBX e Session Border Controller (SBCs), utilizzare il generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="49052-128">To create trunks by defining the relationships between Mediation Servers and PSTN gateways, IP-PBXs, and Session Border Controllers (SBCs), use the Topology Builder.</span></span>

</div>

<div>

## <a name="least-cost-routing"></a><span data-ttu-id="49052-129">Least Cost Routing</span><span class="sxs-lookup"><span data-stu-id="49052-129">Least-Cost Routing</span></span>

<span data-ttu-id="49052-p105">La possibilità di specificare i trunk verso cui vengono instradati diversi numeri consente di determinare quali route comportano i costi minori e di implementarle di conseguenza. In generale, per ridurre i costi delle chiamate interurbane, è consigliabile scegliere il trunk con il gateway più vicino alla località del numero di destinazione. Se ad esempio ci si trova a New York e si sta chiamando un numero a Roma, è possibile trasmettere la chiamata tramite la rete IP al trunk con il gateway nell'ufficio di Roma, sostenendo in questo modo solo i costi di una chiamata locale.</span><span class="sxs-lookup"><span data-stu-id="49052-p105">The ability to specify the trunks to which various numbers are routed enables you to determine which routes incur the lowest costs and implement them accordingly. The general rule in selecting trunks is to choose the trunk with the closest gateway to the location of the destination number in order to minimize long-distance charges. For example, if you are in New York and calling a number in Rome, you would carry the call over the IP network to the trunk with the gateway in your Rome office, thereby incurring a charge only for a local call.</span></span>

<span data-ttu-id="49052-133">Per un esempio del modo in cui è possibile utilizzare il routing a costi minimi, prendere in considerazione quanto segue: Fabrikam decide di abilitare gli utenti tedeschi a comporre numeri statunitensi usando il trunk degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="49052-133">For an example of how least-cost routing might be used, consider the following: Fabrikam decides to enable German users to dial U.S. numbers by using the U.S. trunk.</span></span> <span data-ttu-id="49052-134">Anche Fabrikam desidera configurare il sistema in modo che tutte le chiamate provenienti da utenti di Lync Server statunitensi verso la Germania e i paesi/aree adiacenti terminano nel trunk con il gateway in Germania.</span><span class="sxs-lookup"><span data-stu-id="49052-134">Fabrikam also wants to configure the system so that all calls from U.S. Lync Server users to Germany and adjacent countries/regions terminate on the trunk with the gateway in Germany.</span></span> <span data-ttu-id="49052-135">Questo routing consente di risparmiare denaro, perché una chiamata dalla Germania all'Austria, ad esempio, è meno costosa di una chiamata dagli Stati Uniti all'Austria.</span><span class="sxs-lookup"><span data-stu-id="49052-135">This routing will save money, because a call from Germany to Austria, for example, is less expensive than a call from the U.S. to Austria.</span></span>

</div>

<div>

## <a name="translating-outbound-dial-strings"></a><span data-ttu-id="49052-136">Conversione delle stringhe di composizione in uscita</span><span class="sxs-lookup"><span data-stu-id="49052-136">Translating Outbound Dial Strings</span></span>

<span data-ttu-id="49052-137">Lync Server 2013, come i suoi predecessori immediati, richiede che tutte le stringhe di composizione vengano normalizzate nel formato E. 164 allo scopo di eseguire la ricerca di numeri inversi (inversa).</span><span class="sxs-lookup"><span data-stu-id="49052-137">Lync Server 2013, like its immediate predecessors, requires all dial strings to be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="49052-138">Per i trunk con gateway o PBX (Private Branch Exchange) che richiedono numeri tradotti nei formati di composizione locali, Lync Server 2013 consente di creare una o più regole che consentono di modificare il numero chiamato (ovvero l'URI della richiesta) prima di instradarlo al trunk.</span><span class="sxs-lookup"><span data-stu-id="49052-138">For trunks with gateways or private branch exchanges (PBXs) that require numbers translated in local dialing formats, Lync Server 2013 enables you to create one or more rules that assist in manipulating the called number (i.e. Request URI) prior to routing it to the trunk.</span></span> <span data-ttu-id="49052-139">È ad esempio possibile scrivere una regola per rimuovere il prefisso +44 all'inizio di una stringa di composizione e sostituirlo con 0144.</span><span class="sxs-lookup"><span data-stu-id="49052-139">For example, you could write a rule to remove +44 from the head of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="49052-140">Con Lync Server 2013, è possibile creare una o più regole che agevolano la manipolazione del numero di chiamata prima di instradarlo al trunk.</span><span class="sxs-lookup"><span data-stu-id="49052-140">With Lync Server 2013, it is possible to create one or more rules that assist in manipulating the calling number prior to routing it to the trunk.</span></span>

<span data-ttu-id="49052-141">Nella pianificazione dei trunk che associano i gateway: coppie di porte con Mediation Server: coppie di porte, può essere utile raggruppare trunk con requisiti di composizione locali simili e quindi ridurre il numero di regole di conversione necessarie e il tempo necessario per scriverle.</span><span class="sxs-lookup"><span data-stu-id="49052-141">In planning your trunks that associate gateways:port pairs with Mediation Server:port pairs, it may be useful to group trunks with similar local dialing requirements, and therefore reduce the number of required translation rules and the time it takes to write them.</span></span>

</div>

<div>

## <a name="configuring-caller-id"></a><span data-ttu-id="49052-142">Configurazione dell'ID chiamante</span><span class="sxs-lookup"><span data-stu-id="49052-142">Configuring Caller ID</span></span>

<span data-ttu-id="49052-143">Lync Server consente di modificare l'ID chiamante per le chiamate in uscita.</span><span class="sxs-lookup"><span data-stu-id="49052-143">Lync Server provides a way to manipulate the caller ID for outbound calls.</span></span> <span data-ttu-id="49052-144">Ad esempio, se un'organizzazione desidera mascherare le estensioni di composizione diretta dei dipendenti e sostituirle con il numero di reparto o aziendale generico, un amministratore può eseguire tale operazione utilizzando il pannello di controllo di Lync Server per sopprimere l'ID chiamante e sostituirlo con un ID chiamante alternativo specificato.</span><span class="sxs-lookup"><span data-stu-id="49052-144">For example, if an organization wants to mask employees’ direct-dial extensions and replace them with the generic corporate or departmental number, an administrator can do that by using Lync Server Control Panel to suppress the caller ID and replace it with a specified alternative caller ID.</span></span> <span data-ttu-id="49052-145">Nella pianificazione della logica di routing considerare per quali singoli, gruppi o siti si desidera tale opzione oppure se deve essere applicata addirittura per tutti i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="49052-145">In planning your routing logic, consider which individuals, groups, sites you’ll want this option for—perhaps, even, for all employees.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="49052-p109">Per le chiamate reinoltrate tramite PSTN, verrà visualizzato l'ID chiamante generico anziché quello originario. La chiamata potrebbe quindi ignorare eventuali impostazioni Non disturbare o di privacy configurate dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="49052-p109">For calls that are rerouted over the PSTN, the generic caller ID will be presented instead of the original caller ID. This can cause the call to bypass Do Not Disturb or privacy settings that the callee may have configured.</span></span>



</div>

</div>

<div>

## <a name="additional-routing-logic"></a><span data-ttu-id="49052-148">Logica di routing aggiuntiva</span><span class="sxs-lookup"><span data-stu-id="49052-148">Additional Routing Logic</span></span>

<span data-ttu-id="49052-149">Durante la creazione delle route delle chiamate in uscita, tenere presente i fattori seguenti che influiscono sulla logica di routing:</span><span class="sxs-lookup"><span data-stu-id="49052-149">In creating outbound call routes, you should be aware of the following factors that can affect routing logic:</span></span>

  - <span data-ttu-id="49052-150">Nelle situazioni in cui viene effettuata una chiamata attraverso un confine federato, la parte dell'URI relativa al dominio viene utilizzata per instradare la chiamata all'azienda responsabile dell'applicazione della logica di routing in uscita.</span><span class="sxs-lookup"><span data-stu-id="49052-150">Where a call is established over a federated boundary, the domain portion of the URI is used to route the call over to the enterprise that is responsible for applying the outbound routing logic.</span></span>

  - <span data-ttu-id="49052-151">Se la parte dell'URI della richiesta relativa al dominio non contiene un dominio supportato per l'azienda, il componente di routing in uscita nel server non elabora la chiamata.</span><span class="sxs-lookup"><span data-stu-id="49052-151">If the domain portion of the request URI does not contain a supported domain for the enterprise, the outbound routing component on the server does not process the call.</span></span>

  - <span data-ttu-id="49052-152">Se un utente non è abilitato per VoIP aziendale, il server applica un'altra logica di routing, a seconda dei casi.</span><span class="sxs-lookup"><span data-stu-id="49052-152">If a user is not enabled for Enterprise Voice, the server applies other routing logic, as appropriate.</span></span>

  - <span data-ttu-id="49052-p110">Se una chiamata viene instradata a un gateway completamente occupato (tutte le linee di trunk sono occupate), il gateway rifiuta la chiamata e la logica di routing in uscita la reindirizza alla successiva route Least Cost Routing. È necessario valutare con attenzione questo aspetto perché un gateway adatto nelle dimensioni a una piccola sede all'estero, ad esempio Zurigo, potrebbe in realtà trasportare una quantità significativa di traffico non locale per le chiamate internazionali dirette in Svizzera. Se il gateway non presenta dimensioni adeguate a questo traffico aggiuntivo, le chiamate dirette in Svizzera potrebbero essere instradate mediante un gateway in Germania, con conseguenti tariffe più alte.</span><span class="sxs-lookup"><span data-stu-id="49052-p110">If a call is routed to a gateway that is fully occupied (all trunk lines are busy), the gateway rejects the call and the outbound routing logic redirects the call to the next-least-cost route. Give this careful consideration, because a gateway sized for a small office overseas (for example, Zurich) may actually carry a significant amount of nonlocal traffic for international calls to Switzerland. If the gateway is not correctly sized for this additional traffic, calls to Switzerland may be routed by way of a gateway in Germany, resulting in larger toll charges.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

