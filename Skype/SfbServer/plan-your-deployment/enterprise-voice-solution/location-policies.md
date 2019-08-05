---
title: Pianificare i criteri di posizione per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Leggere questo argomento per informazioni su come pianificare i criteri di posizione per una distribuzione di servizi di emergenza avanzata (E9-1-1) in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 8f21a5a0f54fbeaca4c46ed51bf4dafe4c2a3dcb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187649"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="aa0dd-103">Pianificare i criteri di posizione per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="aa0dd-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="aa0dd-104">Leggere questo argomento per informazioni su come pianificare i criteri di posizione per una distribuzione di servizi di emergenza avanzata (E9-1-1) in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="aa0dd-105">Skype for Business Server ora supporta la configurazione di più numeri di emergenza per un client.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="aa0dd-106">Se si vogliono configurare più numeri di emergenza, è necessario seguire le informazioni in [piano per i numeri di emergenza multipli in Skype for Business Server](multiple-emergency-numbers.md) e [configurare più numeri di emergenza in Skype for business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="aa0dd-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="aa0dd-107">È possibile creare criteri di posizione usando il pannello di controllo di Skype for business o usando il cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="aa0dd-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="aa0dd-108">Per altre informazioni, vedere [creare criteri di posizione in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="aa0dd-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="aa0dd-109">Ogni criterio di posizione contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa0dd-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="aa0dd-110">**Abilitare 9-1-1 avanzato**</span><span class="sxs-lookup"><span data-stu-id="aa0dd-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="aa0dd-111">Quando questo valore è abilitato, il client è abilitato per i servizi di emergenza avanzati (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="aa0dd-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="aa0dd-112">Quando un client esegue la registrazione, tenta di acquisire una posizione dal servizio informazioni sulla posizione e includerà le informazioni sulla posizione come parte di una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="aa0dd-113">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="aa0dd-113">**Location**</span></span>
  
<span data-ttu-id="aa0dd-114">Questa impostazione viene usata solo quando è abilitato **Enable Enhanced 9-1-1** .</span><span class="sxs-lookup"><span data-stu-id="aa0dd-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="aa0dd-115">Puoi configurare l'impostazione della **posizione** per definire il comportamento del client nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="aa0dd-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="aa0dd-116">Impostando il valore su **No** , l'utente non verrà richiesto per una posizione.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="aa0dd-117">Impostando il valore su **Sì** , l'utente verrà richiesto per una posizione, ma può chiudere la richiesta.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="aa0dd-118">Se si imposta il valore su **Disclaimer** , l'utente verrà richiesto di ricevere una posizione e verrà visualizzata anche una dichiarazione di non responsabilità se tenta di chiudere la richiesta.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-118">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="aa0dd-119">In tutti i casi, l'utente può continuare a usare il client.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-119">In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="aa0dd-120">Il testo della dichiarazione di non responsabilità non verrà visualizzato se un utente ha immesso manualmente una posizione prima di essere abilitato per il E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-120">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1.</span></span> <span data-ttu-id="aa0dd-121">Gli aggiornamenti al testo della dichiarazione di non responsabilità non verranno visualizzati dagli utenti che hanno già visualizzato la dichiarazione di non responsabilità.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-121">Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="aa0dd-122">**Dichiarazione di non responsabilità avanzata del servizio di emergenza**</span><span class="sxs-lookup"><span data-stu-id="aa0dd-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="aa0dd-123">Questa impostazione specifica la dichiarazione di non responsabilità che gli utenti vedono se eliminano la richiesta di una posizione.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="aa0dd-124">In Skype for Business Server è possibile usare i criteri di posizione per impostare dichiarazioni di non credito diverse per le diverse impostazioni locali o per diversi gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="aa0dd-125">**Stringa di chiamata di emergenza (numero di telefono E9-1-1)**</span><span class="sxs-lookup"><span data-stu-id="aa0dd-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="aa0dd-126">Questa stringa di chiamata (meno l'iniziale "+", ma anche qualsiasi normalizzazione eseguita dal dial plan dell'utente) indica che una chiamata è una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="aa0dd-127">La **stringa** di chiamata di emergenza fa sì che il client includa le informazioni sulla posizione e sulla richiamata con la chiamata.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aa0dd-128">Se l'organizzazione non usa un prefisso di accesso alla linea esterna, non è necessario creare una regola di normalizzazione del dial plan corrispondente che aggiunga un "+" alla stringa 911 prima di inviare la chiamata al routing in uscita in un server che esegue Skype for Business Server; il "+" verrà anteposto automaticamente dal client Skype for business come risultato dei criteri di posizione.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="aa0dd-129">Tuttavia, se il sito usa un prefisso di accesso esterno, è necessario aggiungere una regola di normalizzazione ai criteri di dial plan applicabili che allineano il prefisso di accesso esterno e aggiunge "+".</span><span class="sxs-lookup"><span data-stu-id="aa0dd-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="aa0dd-130">Ad esempio, se la tua posizione usa un prefisso di accesso esterno di 9 e un utente compone 9 911 per effettuare una chiamata di emergenza, il client userà i criteri per il dial plan per normalizzare questa operazione su + 911 prima che il numero composto venga valutato dalle route nel profilo della posizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="aa0dd-131">**Maschere di stringhe di chiamate di emergenza (E9-1-1 Dial mask)**</span><span class="sxs-lookup"><span data-stu-id="aa0dd-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="aa0dd-132">Elenco separato da punti e virgola delle stringhe di chiamata tradotte nella **stringa di chiamata di emergenza**specificata.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="aa0dd-133">Ad esempio, potresti voler aggiungere 112, che è il numero di servizio di emergenza per la maggior parte dell'Europa.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="aa0dd-134">Un utente di Skype for business che visita l'Europa potrebbe non sapere che 911 è il numero di emergenza degli Stati Uniti, ma può chiamare 112 e ottenere lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="aa0dd-135">Come per la stringa di chiamata di emergenza, non includere un "+" prima di ogni numero e se si usano i codici di accesso per le linee esterne, verificare che esistano regole di normalizzazione nei criteri di dial plan dell'utente per eliminare la cifra del codice di accesso.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="aa0dd-136">**Utilizzo PSTN**</span><span class="sxs-lookup"><span data-stu-id="aa0dd-136">**PSTN usage**</span></span>
  
<span data-ttu-id="aa0dd-137">Nome dell'utilizzo PSTN che contiene i percorsi di routing che determinano il trunk SIP, il gateway PSTN o le chiamate di emergenza del gateway ELIN.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aa0dd-138">Un solo utilizzo può essere assegnato a un criterio di posizione.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="aa0dd-139">Questo uso PSTN esegue l'override degli usi PSTN assegnati al criterio vocale dell'utente, ma si applica solo alle chiamate poste alla stringa di chiamata di emergenza o a una delle maschere di stringhe di chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="aa0dd-140">**URI di notifica**</span><span class="sxs-lookup"><span data-stu-id="aa0dd-140">**Notification URI**</span></span>
  
<span data-ttu-id="aa0dd-141">Specifica uno o più URI SIP del personale di sicurezza che riceve una notifica di messaggistica istantanea quando viene inserita una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-141">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed.</span></span> <span data-ttu-id="aa0dd-142">I gruppi di distribuzione sono supportati.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-142">Distribution groups are supported.</span></span>
  
 <span data-ttu-id="aa0dd-143">**URI conferenza**</span><span class="sxs-lookup"><span data-stu-id="aa0dd-143">**Conference URI**</span></span>
  
<span data-ttu-id="aa0dd-144">Specifica un numero DID (Direct Interior Dialing) (in genere un numero di banco di sicurezza) che deve essere convogliato in conferenza quando viene inserita una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="aa0dd-145">**Modalità conferenza**</span><span class="sxs-lookup"><span data-stu-id="aa0dd-145">**Conference Mode**</span></span>
  
<span data-ttu-id="aa0dd-146">Specifica se l'URI della conferenza verrà conferito alla chiamata di emergenza tramite una comunicazione unidirezionale o bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="aa0dd-147">**Intervallo di aggiornamento della posizione**</span><span class="sxs-lookup"><span data-stu-id="aa0dd-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="aa0dd-148">Specifica la quantità di tempo (in ore) tra le richieste client per un aggiornamento della posizione dal servizio informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="aa0dd-149">Il valore può essere impostato su qualsiasi valore compreso tra 1 e 12.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="aa0dd-150">Il valore predefinito è 4.</span><span class="sxs-lookup"><span data-stu-id="aa0dd-150">The default value is 4.</span></span>
  

