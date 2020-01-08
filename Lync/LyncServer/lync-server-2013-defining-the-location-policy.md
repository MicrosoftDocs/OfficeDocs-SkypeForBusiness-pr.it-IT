---
title: 'Lync Server 2013: definizione dei criteri di posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26b0e9aca4b3e66202d6b3c4a47b90db4f207fda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a><span data-ttu-id="eb184-102">Definizione dei criteri di posizione per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb184-102">Defining the location policy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb184-103">_**Argomento Ultima modifica:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="eb184-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="eb184-104">Ogni criterio di posizione contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb184-104">Each location policy contains the following information:</span></span>

  - <span data-ttu-id="eb184-105">**Servizi di emergenza abilitati**</span><span class="sxs-lookup"><span data-stu-id="eb184-105">**Emergency Services Enabled**</span></span>  
    <span data-ttu-id="eb184-106">Quando questo valore è **Sì**, il client è abilitato per il E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="eb184-106">When this value is **Yes**, the client is enabled for E9-1-1.</span></span> <span data-ttu-id="eb184-107">Quando un client esegue la registrazione, tenta di acquisire una posizione dal servizio informazioni sulla posizione e includerà le informazioni sulla posizione come parte di una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="eb184-107">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>

<!-- end list -->

  - <span data-ttu-id="eb184-108">**Posizione richiesta**</span><span class="sxs-lookup"><span data-stu-id="eb184-108">**Location Required**</span></span>  
    <span data-ttu-id="eb184-109">Questa impostazione viene usata solo quando i **servizi di emergenza abilitati** sono impostati su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="eb184-109">This setting is used only when **Emergence Services Enabled** is set to **Yes**.</span></span>
    
    <span data-ttu-id="eb184-110">Puoi configurare l'impostazione della **posizione necessaria** per definire il comportamento del client.</span><span class="sxs-lookup"><span data-stu-id="eb184-110">You can configure the **Location Required** setting to define the client behavior.</span></span> <span data-ttu-id="eb184-111">Impostando il valore su **No** , l'utente non verrà richiesto per una posizione.</span><span class="sxs-lookup"><span data-stu-id="eb184-111">Setting the value to **No** means that the user will not be prompted for a location.</span></span> <span data-ttu-id="eb184-112">Impostando il valore su **Sì** , l'utente verrà richiesto per una posizione, ma può chiudere la richiesta.</span><span class="sxs-lookup"><span data-stu-id="eb184-112">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="eb184-113">Se si imposta il valore su **Disclaimer** , l'utente verrà richiesto di ricevere una posizione e verrà visualizzata anche una dichiarazione di non responsabilità se tenta di chiudere la richiesta.</span><span class="sxs-lookup"><span data-stu-id="eb184-113">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="eb184-114">In tutti i casi, l'utente può continuare a usare il client.</span><span class="sxs-lookup"><span data-stu-id="eb184-114">In all cases, the user can continue to use the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb184-115">Il testo della dichiarazione di non responsabilità non verrà visualizzato se un utente ha immesso manualmente una posizione prima di essere abilitato per il E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="eb184-115">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1.</span></span> <span data-ttu-id="eb184-116">Gli aggiornamenti al testo della dichiarazione di non responsabilità non verranno visualizzati dagli utenti che hanno già visualizzato la dichiarazione di non responsabilità.</span><span class="sxs-lookup"><span data-stu-id="eb184-116">Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="eb184-117">**Dichiarazione di non responsabilità avanzata del servizio di emergenza**</span><span class="sxs-lookup"><span data-stu-id="eb184-117">**Enhanced Emergency Service Disclaimer**</span></span>  
    <span data-ttu-id="eb184-118">Questa impostazione specifica la dichiarazione di non responsabilità che gli utenti vedono se eliminano la richiesta di una posizione.</span><span class="sxs-lookup"><span data-stu-id="eb184-118">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="eb184-119">In Lync Server 2013 è possibile usare i criteri di posizione per impostare dichiarazioni di non credito diverse per le diverse impostazioni locali o per diversi gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="eb184-119">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb184-120">Questa impostazione dei criteri di posizione è diversa da Lync Server 2010, in cui è stato usato il cmdlet <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> per impostare una dichiarazione di non responsabilità globale per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="eb184-120">This location policy setting differs from Lync Server 2010, where you used the <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet to set a global disclaimer for the entire organization.</span></span> <span data-ttu-id="eb184-121">Se esiste già una dichiarazione di non responsabilità globale, è necessario specificare la dichiarazione di non responsabilità nei criteri di posizione.</span><span class="sxs-lookup"><span data-stu-id="eb184-121">If a global disclaimer already exists, you need to specify that disclaimer in location policy.</span></span> <span data-ttu-id="eb184-122">In altre condizioni, Lync Server 2013 USA solo le dichiarazioni di non attestazione specificate nei criteri di posizione.</span><span class="sxs-lookup"><span data-stu-id="eb184-122">That is, Lync Server 2013 uses only disclaimers specified in location policy.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="eb184-123">**Stringa di chiamata di emergenza**</span><span class="sxs-lookup"><span data-stu-id="eb184-123">**Emergency Dial String**</span></span>  
    <span data-ttu-id="eb184-124">Questa stringa di chiamata (meno l'iniziale "+", ma anche qualsiasi normalizzazione eseguita dal dial plan dell'utente di Lync) indica che una chiamata è una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="eb184-124">This dial string (less the leading “+”, but including any normalization done by the Lync user’s Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="eb184-125">La **stringa** di chiamata di emergenza fa sì che il client includa le informazioni sulla posizione e sulla richiamata con la chiamata.</span><span class="sxs-lookup"><span data-stu-id="eb184-125">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb184-126">Se l'organizzazione non usa un prefisso di accesso alla linea esterna, non è necessario creare una regola di normalizzazione del dial plan corrispondente che aggiunga un "+" alla stringa 911 prima di inviare la chiamata al routing in uscita in un server di pool Lync; il valore "+" verrà anteposto automaticamente dal client Lync come risultato dei criteri di posizione.</span><span class="sxs-lookup"><span data-stu-id="eb184-126">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a “+” to the 911 string prior to sending the call to Outbound Routing on a Lync pool server; the “+” will be automatically prepended by the Lync client as a result of the location policy.</span></span> <span data-ttu-id="eb184-127">Tuttavia, se il sito usa un prefisso di accesso esterno, è necessario aggiungere una regola di normalizzazione ai criteri di dial plan applicabili che allineano il prefisso di accesso esterno e aggiunge "+".</span><span class="sxs-lookup"><span data-stu-id="eb184-127">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the “+”.</span></span> <span data-ttu-id="eb184-128">Ad esempio, se la tua posizione usa un prefisso di accesso esterno di 9 e un utente compone&nbsp;9 911 per effettuare una chiamata di emergenza, il client userà i criteri per il dial plan per normalizzare il valore in + 911 prima che il numero di telefono sia valutato dalle route nel profilo della posizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="eb184-128">For example, if your location uses an external access prefix of 9 and a user dials 9&nbsp;911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller’s location profile.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="eb184-129">**Maschere per stringhe di chiamate di emergenza**</span><span class="sxs-lookup"><span data-stu-id="eb184-129">**Emergency Dial String Masks**</span></span>  
    <span data-ttu-id="eb184-130">Elenco separato da punti e virgola delle stringhe di chiamata tradotte nella **stringa di chiamata di emergenza**specificata.</span><span class="sxs-lookup"><span data-stu-id="eb184-130">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="eb184-131">Ad esempio, potresti voler aggiungere 112, che è il numero di servizio di emergenza per la maggior parte dell'Europa.</span><span class="sxs-lookup"><span data-stu-id="eb184-131">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="eb184-132">Un utente di Lync che visita l'Europa potrebbe non sapere che 911 è il numero di emergenza degli Stati Uniti, ma può chiamare 112 e ottenere lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="eb184-132">A visiting Lync user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="eb184-133">Come per la stringa di chiamata di emergenza, non includere un "+" prima di ogni numero e se si usano i codici di accesso per le linee esterne, verificare che esistano regole di normalizzazione nei criteri di dial plan dell'utente per eliminare la cifra del codice di accesso.</span><span class="sxs-lookup"><span data-stu-id="eb184-133">As with the Emergency Dial String, do not include a “+” before each number, and if you use external line access codes, be sure there are normalization rules in the user’s Dial Plan policy to strip off the access code digit.</span></span>

<!-- end list -->

  - <span data-ttu-id="eb184-134">**Utilizzo PSTN**</span><span class="sxs-lookup"><span data-stu-id="eb184-134">**PSTN Usage**</span></span>  
    <span data-ttu-id="eb184-135">Nome dell'utilizzo PSTN che contiene i percorsi di routing che determinano il trunk SIP, il gateway PSTN o le chiamate di emergenza del gateway ELIN.</span><span class="sxs-lookup"><span data-stu-id="eb184-135">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb184-136">Un solo utilizzo può essere assegnato a un criterio di posizione.</span><span class="sxs-lookup"><span data-stu-id="eb184-136">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="eb184-137">Questo uso PSTN esegue l'override degli usi PSTN assegnati al criterio vocale dell'utente, ma si applica solo alle chiamate poste alla stringa di chiamata di emergenza o a una delle maschere di stringhe di chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="eb184-137">This PSTN Usage overrides the PSTN Usages assigned to the user’s voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="eb184-138">**URI di notifica**</span><span class="sxs-lookup"><span data-stu-id="eb184-138">**Notification URI**</span></span>  
    <span data-ttu-id="eb184-139">Specifica uno o più URI SIP del personale di sicurezza che riceve una notifica di messaggistica istantanea quando viene inserita una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="eb184-139">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed.</span></span> <span data-ttu-id="eb184-140">I gruppi di distribuzione sono supportati.</span><span class="sxs-lookup"><span data-stu-id="eb184-140">Distribution groups are supported.</span></span>

<!-- end list -->

  - <span data-ttu-id="eb184-141">**URI conferenza**</span><span class="sxs-lookup"><span data-stu-id="eb184-141">**Conference URI**</span></span>  
    <span data-ttu-id="eb184-142">Specifica un numero DID (Direct Interior Dialing) (in genere un numero di banco di sicurezza) che deve essere convogliato in conferenza quando viene inserita una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="eb184-142">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span>

<!-- end list -->

  - <span data-ttu-id="eb184-143">**Modalità conferenza**</span><span class="sxs-lookup"><span data-stu-id="eb184-143">**Conference Mode**</span></span>  
    <span data-ttu-id="eb184-144">Specifica se l'URI della conferenza verrà conferito alla chiamata di emergenza tramite una comunicazione unidirezionale o bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="eb184-144">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span>

<!-- end list -->

  - <span data-ttu-id="eb184-145">**Intervallo di aggiornamento della posizione**</span><span class="sxs-lookup"><span data-stu-id="eb184-145">**Location Refresh Interval**</span></span>  
    <span data-ttu-id="eb184-146">Specifica la quantità di tempo (in ore) tra le richieste client per un aggiornamento della posizione dal servizio informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="eb184-146">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="eb184-147">Il valore può essere impostato su qualsiasi valore compreso tra 1 e 12.</span><span class="sxs-lookup"><span data-stu-id="eb184-147">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="eb184-148">Il valore predefinito è 4.</span><span class="sxs-lookup"><span data-stu-id="eb184-148">The default value is 4.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

