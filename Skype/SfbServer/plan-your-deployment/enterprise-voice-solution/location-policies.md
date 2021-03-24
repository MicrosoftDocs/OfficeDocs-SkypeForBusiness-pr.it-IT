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
description: Leggere questo argomento per informazioni su come pianificare i criteri percorso per una distribuzione avanzata di servizi di emergenza (E9-1-1) in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 3d9c574d18351594d9773f02770e960c993ae401
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101452"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="27395-103">Pianificare i criteri percorso per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="27395-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="27395-104">Leggere questo argomento per informazioni su come pianificare i criteri percorso per una distribuzione avanzata di servizi di emergenza (E9-1-1) in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="27395-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="27395-105">Skype for Business Server ora supporta la configurazione di più numeri di emergenza per un client.</span><span class="sxs-lookup"><span data-stu-id="27395-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="27395-106">Se si desidera configurare più numeri di emergenza, è necessario seguire le informazioni in Pianificare più numeri di emergenza [in Skype for Business Server](multiple-emergency-numbers.md) e Configurare più numeri di emergenza in Skype for [Business.](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="27395-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="27395-107">È possibile creare criteri percorso utilizzando il Pannello di controllo di Skype for Business o il cmdlet [New-CsLocationPolicy.](/powershell/module/skype/new-cslocationpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="27395-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="27395-108">Per ulteriori informazioni, vedere [Creare criteri percorso in Skype for Business Server.](../../deploy/deploy-enterprise-voice/create-location-policies.md)</span><span class="sxs-lookup"><span data-stu-id="27395-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="27395-109">Ogni criterio percorso contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="27395-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="27395-110">**Abilita Enhanced 9-1-1**</span><span class="sxs-lookup"><span data-stu-id="27395-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="27395-111">Quando questo valore è abilitato, il client è abilitato per i servizi di emergenza avanzato (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="27395-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="27395-112">Quando un client esegue la registrazione, tenta di acquisire una posizione dal servizio informazioni sulla posizione e include le informazioni sulla posizione come parte di una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="27395-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="27395-113">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="27395-113">**Location**</span></span>
  
<span data-ttu-id="27395-114">Questa impostazione viene utilizzata solo quando **è abilitato l'opzione Abilita Enhanced 9-1-1.**</span><span class="sxs-lookup"><span data-stu-id="27395-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="27395-115">È possibile configurare **l'impostazione Percorso** per definire il comportamento del client come segue:</span><span class="sxs-lookup"><span data-stu-id="27395-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="27395-116">Se si imposta il **valore su No,** all'utente non verrà richiesto di specificare una posizione.</span><span class="sxs-lookup"><span data-stu-id="27395-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="27395-117">Se si imposta il **valore su Sì,** all'utente verrà richiesto di specificare una posizione, ma potrà ignorare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="27395-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="27395-118">Se si  imposta il valore su Dichiarazione di non responsabilità, all'utente verrà richiesto di specificare una posizione e verrà inoltre visualizzata una dichiarazione di non responsabilità se tenta di ignorare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="27395-118">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="27395-119">In tutti i casi, l'utente può continuare a usare il client.</span><span class="sxs-lookup"><span data-stu-id="27395-119">In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="27395-120">Il testo della dichiarazione di non responsabilità non verrà visualizzato se un utente ha immesso manualmente una posizione prima di essere abilitato per E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="27395-120">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1.</span></span> <span data-ttu-id="27395-121">Gli aggiornamenti al testo della dichiarazione di non responsabilità non verranno visualizzati dagli utenti che hanno già visualizzato la dichiarazione di non responsabilità.</span><span class="sxs-lookup"><span data-stu-id="27395-121">Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="27395-122">**Dichiarazione di non responsabilità per il servizio di emergenza avanzato**</span><span class="sxs-lookup"><span data-stu-id="27395-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="27395-123">Questa impostazione consente di specificare la dichiarazione di non responsabilità che gli utenti visualizzano se ignorano la richiesta di una posizione.</span><span class="sxs-lookup"><span data-stu-id="27395-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="27395-124">In Skype for Business Server puoi usare i criteri percorso per impostare dichiarazioni di non responsabilità diverse per impostazioni locali o set di utenti diversi.</span><span class="sxs-lookup"><span data-stu-id="27395-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="27395-125">**Stringa di composizione di emergenza (numero di composizione E9-1-1)**</span><span class="sxs-lookup"><span data-stu-id="27395-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="27395-126">Questa stringa di composizione (meno il "+" iniziale, ma inclusa qualsiasi normalizzazione eseguita dal dial plan dell'utente) indica che una chiamata è una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="27395-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="27395-127">La **stringa di composizione di** emergenza fa in modo che il client includa informazioni sulla posizione e sulla richiamata con la chiamata.</span><span class="sxs-lookup"><span data-stu-id="27395-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="27395-128">Se l'organizzazione non utilizza un prefisso di accesso alla linea esterna, non è necessario creare una regola di normalizzazione dial plan corrispondente che aggiunge un "+" alla stringa 911 prima di inviare la chiamata al routing in uscita su un server che esegue Skype for Business Server. il "+" verrà anteposto automaticamente dal client Skype for Business come risultato dei criteri percorso.</span><span class="sxs-lookup"><span data-stu-id="27395-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="27395-129">Tuttavia, se il sito utilizza un prefisso di accesso esterno, è necessario aggiungere una regola di normalizzazione al criterio dial plan applicabile che rimuove il prefisso di accesso esterno e aggiunge "+".</span><span class="sxs-lookup"><span data-stu-id="27395-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="27395-130">Ad esempio, se la posizione utilizza un prefisso di accesso esterno 9 e un utente compone il 9 911 per effettuare una chiamata di emergenza, il client utilizzerà il relativo criterio dial plan per normalizzare il valore su +911 prima che il numero composto venga valutato dalle route nel profilo di posizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="27395-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="27395-131">**Maschere stringa di composizione di emergenza (maschera di composizione E9-1-1)**</span><span class="sxs-lookup"><span data-stu-id="27395-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="27395-132">Elenco di stringhe di composizione separate da punto e virgola che viene convertito nella stringa di composizione di emergenza **specificata.**</span><span class="sxs-lookup"><span data-stu-id="27395-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="27395-133">Ad esempio, è possibile aggiungere 112, che è il numero del servizio di emergenza per la maggior parte dell'Europa.</span><span class="sxs-lookup"><span data-stu-id="27395-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="27395-134">Un utente di Skype for Business in visita dall'Europa potrebbe non sapere che 911 è il numero di emergenza statunitense, ma può comporre il 112 e ottenere lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="27395-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="27395-135">Come per la stringa di composizione di emergenza, non includere un "+" prima di ogni numero e se si utilizzano codici di accesso alla linea esterna, assicurarsi che nel criterio dial plan dell'utente siano presenti regole di normalizzazione per rimuovere la cifra del codice di accesso.</span><span class="sxs-lookup"><span data-stu-id="27395-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="27395-136">**Utilizzo PSTN**</span><span class="sxs-lookup"><span data-stu-id="27395-136">**PSTN usage**</span></span>
  
<span data-ttu-id="27395-137">Nome dell'utilizzo PSTN che contiene i percorsi di routing che determinano a quale trunk SIP, gateway PSTN o gateway ELIN verranno effettuate le chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="27395-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="27395-138">A un criterio percorso può essere assegnato un solo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="27395-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="27395-139">Questo utilizzo PSTN sostituisce gli utilizzi PSTN assegnati ai criteri vocali dell'utente, ma si applica solo alle chiamate effettuate alla stringa di composizione di emergenza o a una delle maschere stringa di composizione di emergenza.</span><span class="sxs-lookup"><span data-stu-id="27395-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="27395-140">**URI notifica**</span><span class="sxs-lookup"><span data-stu-id="27395-140">**Notification URI**</span></span>
  
<span data-ttu-id="27395-141">Specifica uno o più URI SIP del personale di sicurezza che riceve una notifica di messaggistica istantanea quando viene inviata una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="27395-141">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed.</span></span> <span data-ttu-id="27395-142">I gruppi di distribuzione sono supportati.</span><span class="sxs-lookup"><span data-stu-id="27395-142">Distribution groups are supported.</span></span>
  
 <span data-ttu-id="27395-143">**URI conferenza**</span><span class="sxs-lookup"><span data-stu-id="27395-143">**Conference URI**</span></span>
  
<span data-ttu-id="27395-144">Specifica un numero DID (Direct InWard Dialing) (in genere un numero del desk di sicurezza) a cui effettuare una conferenza quando viene effettuato un intervento di emergenza.</span><span class="sxs-lookup"><span data-stu-id="27395-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="27395-145">**Modalità conferenza**</span><span class="sxs-lookup"><span data-stu-id="27395-145">**Conference Mode**</span></span>
  
<span data-ttu-id="27395-146">Specifica se l'URI conferenza verrà chiamato in conferenza tramite una comunicazione unidirezionale o bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="27395-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="27395-147">**Intervallo di aggiornamento della posizione**</span><span class="sxs-lookup"><span data-stu-id="27395-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="27395-148">Specifica l'intervallo di tempo, in ore, tra le richieste del client per un aggiornamento della posizione dal servizio informazioni percorso.</span><span class="sxs-lookup"><span data-stu-id="27395-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="27395-149">Il valore può essere impostato su qualsiasi valore compreso tra 1 e 12.</span><span class="sxs-lookup"><span data-stu-id="27395-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="27395-150">Il valore predefinito è 4.</span><span class="sxs-lookup"><span data-stu-id="27395-150">The default value is 4.</span></span>
