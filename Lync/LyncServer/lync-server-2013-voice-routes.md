---
title: 'Lync Server 2013: Route vocali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e46b4074d41d2ac79dfe63bc99411a7aba72a88c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-routes-in-lync-server-2013"></a><span data-ttu-id="d9ef7-102">Route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9ef7-102">Voice routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9ef7-103">_**Argomento Ultima modifica:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="d9ef7-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="d9ef7-104">Le route di chiamata specificano il modo in cui Lync Server gestisce le chiamate in uscita poste dagli utenti VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-104">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="d9ef7-105">Quando un utente compone un numero, il server front-end normalizza la stringa di chiamata in formato E. 164, se necessario, e tenta di associarla a un URI SIP.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-105">When a user dials a number, the Front End Server normalizes the dial string to E.164 format, if necessary, and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="d9ef7-106">Se il server non riesce a eseguire la corrispondenza, applica la logica di routing delle chiamate in uscita in base al numero.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-106">If the server cannot make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="d9ef7-107">Il passaggio finale per definire la logica consiste nel creare una route di chiamata separata denominata per ogni set di numeri di telefono di destinazione elencati in ogni dial plan.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-107">The final step in defining that logic is to create a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="d9ef7-108">Prima di definire le route di chiamata in uscita, è necessario eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="d9ef7-108">Before you define outbound call routes, you should complete the following steps:</span></span>

  - <span data-ttu-id="d9ef7-109">Distribuire uno o più trunk.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-109">Deploy one or more trunks.</span></span>

  - <span data-ttu-id="d9ef7-110">Creare piani di chiamata in base alle esigenze per siti, singoli e oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-110">Create dial plans as needed for sites, individuals, and Contact objects.</span></span>

  - <span data-ttu-id="d9ef7-111">Creare record di utilizzo PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="d9ef7-111">Create public switched telephone network (PSTN) usage records.</span></span>

<span data-ttu-id="d9ef7-112">Per abilitare il routing delle chiamate in uscita, è inoltre necessario creare e assegnare uno o più criteri vocali.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-112">Additionally, to enable outbound call routing, you must create and assign one or more voice policies.</span></span> <span data-ttu-id="d9ef7-113">Questa operazione può essere eseguita prima o dopo la definizione delle route di chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-113">You can do this either before or after you define outbound call routes.</span></span>

<span data-ttu-id="d9ef7-114">Per ogni route devi specificare:</span><span class="sxs-lookup"><span data-stu-id="d9ef7-114">For each route, you must specify:</span></span>

  - <span data-ttu-id="d9ef7-115">Nome con cui la route può essere facilmente identificata.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-115">A name by which the route can be easily identified.</span></span>

  - <span data-ttu-id="d9ef7-116">Descrizione facoltativa nei casi in cui il nome da solo potrebbe non essere sufficiente per descrivere la route.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-116">An optional description in cases where the name alone may not be sufficient to describe the route.</span></span>

  - <span data-ttu-id="d9ef7-117">Modello di corrispondenza delle espressioni regolari che identifica i numeri di telefono di destinazione a cui viene applicata la route, insieme alle eccezioni a cui non deve essere applicato il modello corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-117">The regular expression matching pattern that identifies the destination phone numbers to which the route is applied, along with exceptions to which the matching pattern is not to be applied.</span></span>

  - <span data-ttu-id="d9ef7-118">Uno o più trunk che si desidera assegnare alla route.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-118">One or more trunks that you want to assign to the route.</span></span>

  - <span data-ttu-id="d9ef7-119">I record di utilizzo PSTN che gli utenti devono avere per chiamare i numeri corrispondenti all'espressione regolare numero di telefono di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-119">The PSTN usage records that users must have in order to call numbers matching the destination phone number regular expression.</span></span>

<span data-ttu-id="d9ef7-120">Puoi specificare le route di chiamata nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-120">You can specify call routes in the Lync Server Control Panel.</span></span> <span data-ttu-id="d9ef7-121">Queste route di chiamata popolano la tabella di routing del server, che Lync Server usa per instradare le chiamate destinate alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-121">These call routes populate the server routing table, which Lync Server uses to route calls that are destined for the PSTN.</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="d9ef7-122">Supporto di M:N trunk</span><span class="sxs-lookup"><span data-stu-id="d9ef7-122">M:N Trunk Support</span></span>

<span data-ttu-id="d9ef7-123">Lync Server offre flessibilità per il modo in cui le chiamate vengono instradate alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-123">Lync Server provides flexibility in how calls are routed to the PSTN.</span></span> <span data-ttu-id="d9ef7-124">Una route vocale specifica un set di trunk alla rete PSTN che può essere usato per una determinata chiamata vocale.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-124">A voice route specifies a set of trunks to the PSTN that can be used for a particular voice call.</span></span> <span data-ttu-id="d9ef7-125">Un trunk associa un Mediation Server e un numero di porta con un gateway PSTN e un numero di porta in ascolto.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-125">A trunk associates a Mediation Server and a port number with a PSTN gateway and listening port number.</span></span> <span data-ttu-id="d9ef7-126">Questa associazione logica consente a un Mediation Server di essere associato a più gateway e di avere più connessioni allo stesso gateway.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-126">This logical association enables a Mediation Server to be associated with multiple gateways and have multiple connections to the same gateway.</span></span> <span data-ttu-id="d9ef7-127">Quando si definisce una route di chiamata, è necessario specificare i trunk associati alla route, ma non si specificano i server di mediazione associati alla route.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-127">When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with the route.</span></span> <span data-ttu-id="d9ef7-128">Per creare Trunks definendo le relazioni tra Mediation Server e gateway PSTN, IP-PBX e Session Border Controller (SBCs), usare il generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-128">To create trunks by defining the relationships between Mediation Servers and PSTN gateways, IP-PBXs, and Session Border Controllers (SBCs), use the Topology Builder.</span></span>

</div>

<div>

## <a name="least-cost-routing"></a><span data-ttu-id="d9ef7-129">Routing con costi minimi</span><span class="sxs-lookup"><span data-stu-id="d9ef7-129">Least-Cost Routing</span></span>

<span data-ttu-id="d9ef7-130">La possibilità di specificare i trunk a cui vengono instradati i vari numeri consente di determinare quali Route incorrono i costi più bassi e di implementarle di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-130">The ability to specify the trunks to which various numbers are routed enables you to determine which routes incur the lowest costs and implement them accordingly.</span></span> <span data-ttu-id="d9ef7-131">La regola generale nella selezione di Trunks consiste nel scegliere il trunk con il gateway più vicino alla posizione del numero di destinazione per ridurre al minimo le spese interurbane.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-131">The general rule in selecting trunks is to choose the trunk with the closest gateway to the location of the destination number in order to minimize long-distance charges.</span></span> <span data-ttu-id="d9ef7-132">Ad esempio, se ci si trova a New York e si chiama un numero a Roma, è necessario portare la chiamata tramite la rete IP verso il trunk con il gateway nell'ufficio di Roma, in modo da incorrere in una tariffa solo per una chiamata locale.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-132">For example, if you are in New York and calling a number in Rome, you would carry the call over the IP network to the trunk with the gateway in your Rome office, thereby incurring a charge only for a local call.</span></span>

<span data-ttu-id="d9ef7-133">Per un esempio di come potrebbe essere usato il routing con costi minimi, tenere presente quanto segue: Fabrikam decide di consentire agli utenti tedeschi di chiamare i numeri statunitensi usando il trunk degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-133">For an example of how least-cost routing might be used, consider the following: Fabrikam decides to enable German users to dial U.S. numbers by using the U.S. trunk.</span></span> <span data-ttu-id="d9ef7-134">Fabrikam vuole anche configurare il sistema in modo che tutte le chiamate dagli utenti di Lync Server statunitensi alla Germania e i paesi/aree geografiche adiacenti interrompano il trunk con il gateway in Germania.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-134">Fabrikam also wants to configure the system so that all calls from U.S. Lync Server users to Germany and adjacent countries/regions terminate on the trunk with the gateway in Germany.</span></span> <span data-ttu-id="d9ef7-135">Questo routing consente di risparmiare denaro, perché una chiamata da Germania a Austria, ad esempio, è meno costosa di una chiamata dagli Stati Uniti in Austria.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-135">This routing will save money, because a call from Germany to Austria, for example, is less expensive than a call from the U.S. to Austria.</span></span>

</div>

<div>

## <a name="translating-outbound-dial-strings"></a><span data-ttu-id="d9ef7-136">Traduzione di stringhe di chiamata in uscita</span><span class="sxs-lookup"><span data-stu-id="d9ef7-136">Translating Outbound Dial Strings</span></span>

<span data-ttu-id="d9ef7-137">Lync Server 2013, come i suoi predecessori immediati, richiede che tutte le stringhe di chiamata vengano normalizzate in formato E. 164 allo scopo di eseguire la ricerca di numeri inversa (RNL).</span><span class="sxs-lookup"><span data-stu-id="d9ef7-137">Lync Server 2013, like its immediate predecessors, requires all dial strings to be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="d9ef7-138">Per i trunk con gateway o PBX (Private Branch Exchange) che richiedono numeri tradotti in formati di chiamata locali, Lync Server 2013 consente di creare una o più regole che aiutano a manipolare il numero chiamato (ad esempio, l'URI della richiesta) prima di instradarlo al tronco.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-138">For trunks with gateways or private branch exchanges (PBXs) that require numbers translated in local dialing formats, Lync Server 2013 enables you to create one or more rules that assist in manipulating the called number (i.e. Request URI) prior to routing it to the trunk.</span></span> <span data-ttu-id="d9ef7-139">Ad esempio, è possibile scrivere una regola per rimuovere + 44 dalla testa di una stringa di chiamata e sostituirla con 0144.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-139">For example, you could write a rule to remove +44 from the head of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="d9ef7-140">Con Lync Server 2013 è possibile creare una o più regole che aiutano a manipolare il numero chiamante prima di instradarlo al trunk.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-140">With Lync Server 2013, it is possible to create one or more rules that assist in manipulating the calling number prior to routing it to the trunk.</span></span>

<span data-ttu-id="d9ef7-141">Nella pianificazione dei trunk che associano gateway: coppie di porte con Mediation Server: coppie di porte, può essere utile raggruppare trunk con requisiti di chiamata locali simili e quindi ridurre il numero di regole di traduzione necessarie e il tempo necessario per scriverle.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-141">In planning your trunks that associate gateways:port pairs with Mediation Server:port pairs, it may be useful to group trunks with similar local dialing requirements, and therefore reduce the number of required translation rules and the time it takes to write them.</span></span>

</div>

<div>

## <a name="configuring-caller-id"></a><span data-ttu-id="d9ef7-142">Configurazione dell'ID chiamante</span><span class="sxs-lookup"><span data-stu-id="d9ef7-142">Configuring Caller ID</span></span>

<span data-ttu-id="d9ef7-143">Lync Server offre un modo per modificare l'ID chiamante per le chiamate in uscita.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-143">Lync Server provides a way to manipulate the caller ID for outbound calls.</span></span> <span data-ttu-id="d9ef7-144">Ad esempio, se un'organizzazione vuole mascherare le estensioni della chiamata diretta dei dipendenti e sostituirle con il numero generico aziendale o dipartimentale, un amministratore può eseguire questa operazione usando il pannello di controllo di Lync Server per eliminare l'ID chiamante e sostituirlo con un ID chiamante alternativo specificato.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-144">For example, if an organization wants to mask employees’ direct-dial extensions and replace them with the generic corporate or departmental number, an administrator can do that by using Lync Server Control Panel to suppress the caller ID and replace it with a specified alternative caller ID.</span></span> <span data-ttu-id="d9ef7-145">Per pianificare la logica di routing, valutare quali utenti, gruppi, siti è consigliabile usare, magari per tutti i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-145">In planning your routing logic, consider which individuals, groups, sites you’ll want this option for—perhaps, even, for all employees.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d9ef7-146">Per le chiamate che vengono reinstradate tramite la rete PSTN, l'ID chiamante generico verrà presentato al posto dell'ID chiamante originale.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-146">For calls that are rerouted over the PSTN, the generic caller ID will be presented instead of the original caller ID.</span></span> <span data-ttu-id="d9ef7-147">In questo modo, la chiamata al bypass non disturba o le impostazioni di privacy che il chiamato può configurare.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-147">This can cause the call to bypass Do Not Disturb or privacy settings that the callee may have configured.</span></span>



</div>

</div>

<div>

## <a name="additional-routing-logic"></a><span data-ttu-id="d9ef7-148">Logica di routing aggiuntiva</span><span class="sxs-lookup"><span data-stu-id="d9ef7-148">Additional Routing Logic</span></span>

<span data-ttu-id="d9ef7-149">Per creare route di chiamata in uscita, è necessario tenere presenti i fattori seguenti che possono influire sulla logica di routing:</span><span class="sxs-lookup"><span data-stu-id="d9ef7-149">In creating outbound call routes, you should be aware of the following factors that can affect routing logic:</span></span>

  - <span data-ttu-id="d9ef7-150">Quando viene stabilita una chiamata su un contorno federato, viene usata la parte Domain dell'URI per instradare la chiamata all'organizzazione responsabile dell'applicazione della logica di routing in uscita.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-150">Where a call is established over a federated boundary, the domain portion of the URI is used to route the call over to the enterprise that is responsible for applying the outbound routing logic.</span></span>

  - <span data-ttu-id="d9ef7-151">Se la parte relativa al dominio dell'URI della richiesta non contiene un dominio supportato per l'organizzazione, il componente di routing in uscita nel server non elabora la chiamata.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-151">If the domain portion of the request URI does not contain a supported domain for the enterprise, the outbound routing component on the server does not process the call.</span></span>

  - <span data-ttu-id="d9ef7-152">Se un utente non è abilitato per VoIP aziendale, il server applica altre logiche di routing, a seconda delle esigenze.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-152">If a user is not enabled for Enterprise Voice, the server applies other routing logic, as appropriate.</span></span>

  - <span data-ttu-id="d9ef7-153">Se una chiamata viene indirizzata a un gateway completamente occupato (tutte le linee di trunk sono occupate), il gateway respinge la chiamata e la logica di routing in uscita reindirizza la chiamata alla route di costo inferiore successiva.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-153">If a call is routed to a gateway that is fully occupied (all trunk lines are busy), the gateway rejects the call and the outbound routing logic redirects the call to the next-least-cost route.</span></span> <span data-ttu-id="d9ef7-154">Prestare questa considerazione, poiché un gateway dimensionato per un piccolo ufficio oltremare (ad esempio Zurigo) può effettivamente trasportare una quantità significativa di traffico non locale per le chiamate internazionali in Svizzera.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-154">Give this careful consideration, because a gateway sized for a small office overseas (for example, Zurich) may actually carry a significant amount of nonlocal traffic for international calls to Switzerland.</span></span> <span data-ttu-id="d9ef7-155">Se il gateway non è dimensionato correttamente per il traffico aggiuntivo, le chiamate in Svizzera possono essere instradate tramite un gateway in Germania, con conseguente pagamento di pedaggio più ampio.</span><span class="sxs-lookup"><span data-stu-id="d9ef7-155">If the gateway is not correctly sized for this additional traffic, calls to Switzerland may be routed by way of a gateway in Germany, resulting in larger toll charges.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

