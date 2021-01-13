---
title: Pianificare i criteri percorso per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Leggere questo argomento per informazioni su come pianificare i criteri percorso per una distribuzione di servizi di emergenza avanzata (E9-1-1) in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 1e89c2f0ea9d5115b29e9bc6d77b3863bb11888c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825536"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="cf491-103">Pianificare i criteri percorso per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="cf491-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="cf491-104">Leggere questo argomento per informazioni su come pianificare i criteri percorso per una distribuzione di servizi di emergenza avanzata (E9-1-1) in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="cf491-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cf491-105">Skype for Business Server ora supporta la configurazione di più numeri di emergenza per un client.</span><span class="sxs-lookup"><span data-stu-id="cf491-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="cf491-106">Se si desidera configurare più numeri di emergenza, è necessario seguire le informazioni in [pianificare numeri di emergenza multipli in Skype for Business Server](multiple-emergency-numbers.md) e [configurare più numeri di emergenza in Skype for business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="cf491-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="cf491-107">È possibile creare criteri percorso utilizzando il pannello di controllo di Skype for business o utilizzando il cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="cf491-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="cf491-108">Per ulteriori informazioni, vedere [create location Policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cf491-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="cf491-109">Ogni criterio percorso contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf491-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="cf491-110">**Abilitare Enhanced 9-1-1**</span><span class="sxs-lookup"><span data-stu-id="cf491-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="cf491-111">Quando questo valore è abilitato, il client è abilitato per i servizi di emergenza avanzati (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="cf491-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="cf491-112">Quando un client si registra, tenta di acquisire una posizione dal servizio informazioni percorso e includerà le informazioni sul percorso come parte di una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="cf491-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="cf491-113">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="cf491-113">**Location**</span></span>
  
<span data-ttu-id="cf491-114">Questa impostazione viene utilizzata solo quando è abilitata l'opzione **attiva Enhanced 9-1-1** .</span><span class="sxs-lookup"><span data-stu-id="cf491-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="cf491-115">È possibile configurare l'impostazione **percorso** per definire il comportamento del client come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cf491-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="cf491-116">L'impostazione del valore su **No** significa che all'utente non verrà richiesto un percorso.</span><span class="sxs-lookup"><span data-stu-id="cf491-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="cf491-117">Se si imposta il valore su **Sì** , l'utente riceverà la richiesta di una posizione, ma può ignorare il prompt.</span><span class="sxs-lookup"><span data-stu-id="cf491-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="cf491-118">Se si imposta il valore come dichiarazione di non **responsabilità** , all'utente verrà richiesto un percorso e verrà visualizzata una dichiarazione di non responsabilità se si tenta di eliminare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="cf491-118">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="cf491-119">In tutti i casi, l'utente può continuare a utilizzare il client.</span><span class="sxs-lookup"><span data-stu-id="cf491-119">In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cf491-120">Il testo della dichiarazione di non responsabilità non verrà visualizzato se un utente ha immesso manualmente una posizione prima di essere abilitato per il servizio E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="cf491-120">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1.</span></span> <span data-ttu-id="cf491-121">Gli aggiornamenti del testo della dichiarazione di non responsabilità non verranno visualizzati dagli utenti che hanno già visualizzato la dichiarazione di non responsabilità.</span><span class="sxs-lookup"><span data-stu-id="cf491-121">Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="cf491-122">**Dichiarazione di non responsabilità avanzata del servizio di emergenza**</span><span class="sxs-lookup"><span data-stu-id="cf491-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="cf491-123">Questa impostazione consente di specificare la dichiarazione di non responsabilità che gli utenti vedranno se ignorano la richiesta di un percorso.</span><span class="sxs-lookup"><span data-stu-id="cf491-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="cf491-124">In Skype for Business Server, è possibile utilizzare i criteri percorso per impostare diverse dichiarazioni di non responsabilità per le diverse impostazioni locali o gruppi di utenti diversi.</span><span class="sxs-lookup"><span data-stu-id="cf491-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="cf491-125">**Stringa di chiamata di emergenza (numero di chiamata E9-1-1)**</span><span class="sxs-lookup"><span data-stu-id="cf491-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="cf491-126">Questa stringa di composizione (meno la principale "+", ma inclusa la normalizzazione fatta dal dial plan dell'utente) significa che una chiamata è una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="cf491-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="cf491-127">La **stringa di composizione di emergenza** induce il client a includere le informazioni sul percorso e sulla richiamata tramite la chiamata.</span><span class="sxs-lookup"><span data-stu-id="cf491-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cf491-128">Se l'organizzazione non utilizza un prefisso di accesso alla linea esterna, non è necessario creare una regola di normalizzazione del dial plan corrispondente che aggiunga una "+" alla stringa 911 prima di inviare la chiamata al routing in uscita su un server su cui è in esecuzione Skype for Business Server. il "+" verrà anteposto automaticamente dal client Skype for business a causa del criterio percorso.</span><span class="sxs-lookup"><span data-stu-id="cf491-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="cf491-129">Tuttavia, se il sito utilizza un prefisso di accesso esterno, è necessario aggiungere una regola di normalizzazione al criterio del dial plan applicabile che rimuove il prefisso di accesso esterno e aggiunge "+".</span><span class="sxs-lookup"><span data-stu-id="cf491-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="cf491-130">Ad esempio, se la posizione utilizza un prefisso di accesso esterno pari a 9 e un utente compone 9 911 per effettuare una chiamata di emergenza, il client utilizzerà i criteri di dial plan per normalizzare questo valore su + 911 prima che il numero composto venga valutato dalle route nel profilo località del chiamante.</span><span class="sxs-lookup"><span data-stu-id="cf491-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="cf491-131">**Maschere della stringa di chiamata di emergenza (maschera di chiamata E9-1-1)**</span><span class="sxs-lookup"><span data-stu-id="cf491-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="cf491-132">Elenco separato da punto e virgola di stringhe di composizione che vengono convertite nella **stringa di chiamata di emergenza** specificata.</span><span class="sxs-lookup"><span data-stu-id="cf491-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="cf491-133">Ad esempio, si consiglia di aggiungere 112, che è il numero di servizio di emergenza per la maggior parte dell'Europa.</span><span class="sxs-lookup"><span data-stu-id="cf491-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="cf491-134">Un utente che visita Skype for business dall'Europa potrebbe non sapere che 911 è il numero di emergenza degli Stati Uniti, ma può comporre 112 e ottenere lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="cf491-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="cf491-135">Analogamente alla stringa di chiamata di emergenza, non includere un "+" prima di ogni numero e se si utilizzano codici di accesso alla linea esterna, accertarsi che siano presenti regole di normalizzazione nel criterio di dial plan dell'utente per eliminare la cifra del codice di accesso.</span><span class="sxs-lookup"><span data-stu-id="cf491-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="cf491-136">**Utilizzo PSTN**</span><span class="sxs-lookup"><span data-stu-id="cf491-136">**PSTN usage**</span></span>
  
<span data-ttu-id="cf491-137">Nome dell'utilizzo PSTN che contiene i percorsi di routing che determinano il trunk SIP, il gateway PSTN o le chiamate di emergenza del gateway ELIN.</span><span class="sxs-lookup"><span data-stu-id="cf491-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cf491-138">È possibile assegnare un solo utilizzo a un criterio percorso.</span><span class="sxs-lookup"><span data-stu-id="cf491-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="cf491-139">Questo utilizzo PSTN sostituisce gli utilizzi PSTN assegnati ai criteri vocali dell'utente, ma si applica solo alle chiamate effettuate alla stringa di chiamata di emergenza o a una delle maschere di chiamata di stringa di emergenza.</span><span class="sxs-lookup"><span data-stu-id="cf491-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="cf491-140">**URI di notifica**</span><span class="sxs-lookup"><span data-stu-id="cf491-140">**Notification URI**</span></span>
  
<span data-ttu-id="cf491-141">Specifica uno o più URI SIP del personale di sicurezza che ricevono una notifica di messaggistica istantanea quando viene effettuata una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="cf491-141">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed.</span></span> <span data-ttu-id="cf491-142">Sono supportati i gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cf491-142">Distribution groups are supported.</span></span>
  
 <span data-ttu-id="cf491-143">**URI conferenza**</span><span class="sxs-lookup"><span data-stu-id="cf491-143">**Conference URI**</span></span>
  
<span data-ttu-id="cf491-144">Specifica un numero DID (Direct Inward Dialing) (in genere, un numero del desk di sicurezza) che dovrebbe essere utilizzato per la conferenza quando viene effettuata una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="cf491-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="cf491-145">**Modalità conferenza**</span><span class="sxs-lookup"><span data-stu-id="cf491-145">**Conference Mode**</span></span>
  
<span data-ttu-id="cf491-146">Specifica se l'URI conferenza verrà configurata nella chiamata di emergenza utilizzando una comunicazione unidirezionale o bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="cf491-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="cf491-147">**Intervallo di aggiornamento delle posizioni**</span><span class="sxs-lookup"><span data-stu-id="cf491-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="cf491-148">Specifica la quantità di tempo (in ore) tra le richieste dei client per un aggiornamento del percorso dal servizio informazioni percorso.</span><span class="sxs-lookup"><span data-stu-id="cf491-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="cf491-149">Il valore può essere impostato su qualsiasi valore compreso tra 1 e 12.</span><span class="sxs-lookup"><span data-stu-id="cf491-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="cf491-150">Il valore predefinito è 4.</span><span class="sxs-lookup"><span data-stu-id="cf491-150">The default value is 4.</span></span>
  

