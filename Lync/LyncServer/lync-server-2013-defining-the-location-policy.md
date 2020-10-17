---
title: 'Lync Server 2013: definizione dei criteri percorso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bdb3b556f5b9a8d552a3c48e300b8c4b7b19f5f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504523"
---
# <a name="defining-the-location-policy-for-lync-server-2013"></a><span data-ttu-id="98665-102">Definizione dei criteri percorso per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98665-102">Defining the location policy for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98665-103">_**Ultimo argomento modificato:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="98665-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="98665-104">Ogni criterio percorso contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="98665-104">Each location policy contains the following information:</span></span>

  - <span data-ttu-id="98665-105">**Servizi di emergenza abilitati**</span><span class="sxs-lookup"><span data-stu-id="98665-105">**Emergency Services Enabled**</span></span>  
    <span data-ttu-id="98665-106">Quando questo valore è **Yes**, il client è abilitato per il servizio E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="98665-106">When this value is **Yes**, the client is enabled for E9-1-1.</span></span> <span data-ttu-id="98665-107">Quando un client si registra, tenta di acquisire una posizione dal servizio informazioni percorso e includerà le informazioni sul percorso come parte di una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="98665-107">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>

<!-- end list -->

  - <span data-ttu-id="98665-108">**Posizione obbligatoria**</span><span class="sxs-lookup"><span data-stu-id="98665-108">**Location Required**</span></span>  
    <span data-ttu-id="98665-109">Questa impostazione viene utilizzata solo quando i **servizi di emergenza abilitati**   sono impostati su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="98665-109">This setting is used only when **Emergence Services Enabled** is set to **Yes**.</span></span>
    
    <span data-ttu-id="98665-110">È possibile configurare l'impostazione del **percorso necessario** per definire il comportamento del client.</span><span class="sxs-lookup"><span data-stu-id="98665-110">You can configure the **Location Required** setting to define the client behavior.</span></span> <span data-ttu-id="98665-111">L'impostazione del valore su **No** significa che all'utente non verrà richiesto un percorso.</span><span class="sxs-lookup"><span data-stu-id="98665-111">Setting the value to **No** means that the user will not be prompted for a location.</span></span> <span data-ttu-id="98665-112">Se si imposta il valore su **Sì** , l'utente riceverà la richiesta di una posizione, ma può ignorare il prompt.</span><span class="sxs-lookup"><span data-stu-id="98665-112">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="98665-113">Se si imposta il valore come dichiarazione di non **responsabilità** , all'utente verrà richiesto un percorso e verrà visualizzata una dichiarazione di non responsabilità se si tenta di eliminare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="98665-113">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="98665-114">In tutti i casi, l'utente può continuare a utilizzare il client.</span><span class="sxs-lookup"><span data-stu-id="98665-114">In all cases, the user can continue to use the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98665-115">Il testo della dichiarazione di non responsabilità non verrà visualizzato se un utente ha immesso manualmente una posizione prima di essere abilitato per il servizio E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="98665-115">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1.</span></span> <span data-ttu-id="98665-116">Gli aggiornamenti del testo della dichiarazione di non responsabilità non verranno visualizzati dagli utenti che hanno già visualizzato la dichiarazione di non responsabilità.</span><span class="sxs-lookup"><span data-stu-id="98665-116">Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="98665-117">**Dichiarazione di non responsabilità avanzata del servizio di emergenza**</span><span class="sxs-lookup"><span data-stu-id="98665-117">**Enhanced Emergency Service Disclaimer**</span></span>  
    <span data-ttu-id="98665-118">Questa impostazione consente di specificare la dichiarazione di non responsabilità che gli utenti vedranno se ignorano la richiesta di un percorso.</span><span class="sxs-lookup"><span data-stu-id="98665-118">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="98665-119">In Lync Server 2013, è possibile utilizzare i criteri percorso per impostare diverse dichiarazioni di non responsabilità per le diverse impostazioni locali o gruppi di utenti diversi.</span><span class="sxs-lookup"><span data-stu-id="98665-119">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98665-120">Questa impostazione dei criteri percorso è diversa da Lync Server 2010, in cui è stato utilizzato il cmdlet <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> per impostare una dichiarazione di non responsabilità globale per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="98665-120">This location policy setting differs from Lync Server 2010, where you used the <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet to set a global disclaimer for the entire organization.</span></span> <span data-ttu-id="98665-121">Se esiste già una dichiarazione di non responsabilità globale, è necessario specificare la dichiarazione di non responsabilità nei criteri percorso.</span><span class="sxs-lookup"><span data-stu-id="98665-121">If a global disclaimer already exists, you need to specify that disclaimer in location policy.</span></span> <span data-ttu-id="98665-122">Vale a dire che Lync Server 2013 utilizza solo dichiarazioni di non responsabilità specificate nei criteri percorso.</span><span class="sxs-lookup"><span data-stu-id="98665-122">That is, Lync Server 2013 uses only disclaimers specified in location policy.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="98665-123">**Stringa di chiamata di emergenza**</span><span class="sxs-lookup"><span data-stu-id="98665-123">**Emergency Dial String**</span></span>  
    <span data-ttu-id="98665-124">Questa stringa di composizione (meno la principale "+", ma inclusa la normalizzazione fatta dal dial plan dell'utente di Lync) significa che una chiamata è una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="98665-124">This dial string (less the leading “+”, but including any normalization done by the Lync user’s Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="98665-125">La **stringa di composizione di emergenza** induce il client a includere le informazioni sul percorso e sulla richiamata tramite la chiamata.</span><span class="sxs-lookup"><span data-stu-id="98665-125">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98665-126">Se l'organizzazione non utilizza un prefisso di accesso alla linea esterna, non è necessario creare una regola di normalizzazione del dial plan corrispondente che aggiunga una "+" alla stringa 911 prima di inviare la chiamata al routing in uscita su un server del pool Lync. il "+" verrà anteposto automaticamente dal client Lync come risultato del criterio percorso.</span><span class="sxs-lookup"><span data-stu-id="98665-126">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a “+” to the 911 string prior to sending the call to Outbound Routing on a Lync pool server; the “+” will be automatically prepended by the Lync client as a result of the location policy.</span></span> <span data-ttu-id="98665-127">Tuttavia, se il sito utilizza un prefisso di accesso esterno, è necessario aggiungere una regola di normalizzazione al criterio del dial plan applicabile che rimuove il prefisso di accesso esterno e aggiunge "+".</span><span class="sxs-lookup"><span data-stu-id="98665-127">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the “+”.</span></span> <span data-ttu-id="98665-128">Ad esempio, se la posizione utilizza un prefisso di accesso esterno pari a 9 e un utente compone 9 &nbsp; 911 per effettuare una chiamata di emergenza, il client utilizzerà i criteri di dial plan per normalizzare questo valore su + 911 prima che il numero composto venga valutato dalle route nel profilo località del chiamante.</span><span class="sxs-lookup"><span data-stu-id="98665-128">For example, if your location uses an external access prefix of 9 and a user dials 9&nbsp;911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller’s location profile.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="98665-129">**Maschere di stringa di chiamata di emergenza**</span><span class="sxs-lookup"><span data-stu-id="98665-129">**Emergency Dial String Masks**</span></span>  
    <span data-ttu-id="98665-130">Elenco separato da punto e virgola di stringhe di composizione che vengono convertite nella **stringa di chiamata di emergenza**specificata.</span><span class="sxs-lookup"><span data-stu-id="98665-130">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="98665-131">Ad esempio, si consiglia di aggiungere 112, che è il numero di servizio di emergenza per la maggior parte dell'Europa.</span><span class="sxs-lookup"><span data-stu-id="98665-131">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="98665-132">Un utente di Lync in visita dall'Europa potrebbe non sapere che 911 è il numero di emergenza degli Stati Uniti, ma può comporre 112 e ottenere lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="98665-132">A visiting Lync user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="98665-133">Analogamente alla stringa di chiamata di emergenza, non includere un "+" prima di ogni numero e se si utilizzano codici di accesso alla linea esterna, accertarsi che siano presenti regole di normalizzazione nel criterio di dial plan dell'utente per eliminare la cifra del codice di accesso.</span><span class="sxs-lookup"><span data-stu-id="98665-133">As with the Emergency Dial String, do not include a “+” before each number, and if you use external line access codes, be sure there are normalization rules in the user’s Dial Plan policy to strip off the access code digit.</span></span>

<!-- end list -->

  - <span data-ttu-id="98665-134">**Utilizzo PSTN**</span><span class="sxs-lookup"><span data-stu-id="98665-134">**PSTN Usage**</span></span>  
    <span data-ttu-id="98665-135">Nome dell'utilizzo PSTN che contiene i percorsi di routing che determinano il trunk SIP, il gateway PSTN o le chiamate di emergenza del gateway ELIN.</span><span class="sxs-lookup"><span data-stu-id="98665-135">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98665-136">È possibile assegnare un solo utilizzo a un criterio percorso.</span><span class="sxs-lookup"><span data-stu-id="98665-136">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="98665-137">Questo utilizzo PSTN sostituisce gli utilizzi PSTN assegnati ai criteri vocali dell'utente, ma si applica solo alle chiamate effettuate alla stringa di chiamata di emergenza o a una delle maschere di chiamata di stringa di emergenza.</span><span class="sxs-lookup"><span data-stu-id="98665-137">This PSTN Usage overrides the PSTN Usages assigned to the user’s voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="98665-138">**URI di notifica**</span><span class="sxs-lookup"><span data-stu-id="98665-138">**Notification URI**</span></span>  
    <span data-ttu-id="98665-139">Specifica uno o più URI SIP del personale di sicurezza che ricevono una notifica di messaggistica istantanea quando viene effettuata una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="98665-139">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed.</span></span> <span data-ttu-id="98665-140">Sono supportati i gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="98665-140">Distribution groups are supported.</span></span>

<!-- end list -->

  - <span data-ttu-id="98665-141">**URI conferenza**</span><span class="sxs-lookup"><span data-stu-id="98665-141">**Conference URI**</span></span>  
    <span data-ttu-id="98665-142">Specifica un numero DID (Direct Inward Dialing) (in genere, un numero del desk di sicurezza) che dovrebbe essere utilizzato per la conferenza quando viene effettuata una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="98665-142">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span>

<!-- end list -->

  - <span data-ttu-id="98665-143">**Modalità conferenza**</span><span class="sxs-lookup"><span data-stu-id="98665-143">**Conference Mode**</span></span>  
    <span data-ttu-id="98665-144">Specifica se l'URI conferenza verrà configurata nella chiamata di emergenza utilizzando una comunicazione unidirezionale o bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="98665-144">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span>

<!-- end list -->

  - <span data-ttu-id="98665-145">**Intervallo di aggiornamento delle posizioni**</span><span class="sxs-lookup"><span data-stu-id="98665-145">**Location Refresh Interval**</span></span>  
    <span data-ttu-id="98665-146">Specifica la quantità di tempo (in ore) tra le richieste dei client per un aggiornamento del percorso dal servizio informazioni percorso.</span><span class="sxs-lookup"><span data-stu-id="98665-146">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="98665-147">Il valore può essere impostato su qualsiasi valore compreso tra 1 e 12.</span><span class="sxs-lookup"><span data-stu-id="98665-147">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="98665-148">Il valore predefinito è 4.</span><span class="sxs-lookup"><span data-stu-id="98665-148">The default value is 4.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

