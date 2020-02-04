---
title: 'Lync Server 2013: Criteri vocali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice policies
ms:assetid: b7433c62-9d8c-48af-89a0-19f0d34806ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412891(v=OCS.15)
ms:contentKeyID: 48185223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3998bd6f879b20b1a22f46818a22f26bbb2cc29a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-policies-in-lync-server-2013"></a><span data-ttu-id="343b0-102">Criteri vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="343b0-102">Voice policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="343b0-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="343b0-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="343b0-104">I *criteri vocali* di Lync Server definiscono gli elementi seguenti per ogni utente, sito o organizzazione a cui è assegnato il criterio:</span><span class="sxs-lookup"><span data-stu-id="343b0-104">Lync Server *voice policies* define the following for each user, site, or organization that is assigned the policy:</span></span>

  - <span data-ttu-id="343b0-105">Un set di funzionalità di chiamata che possono essere abilitate o disabilitate per determinare la funzionalità VoIP aziendale disponibile per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="343b0-105">A set of calling features that can be enabled or disabled to determine the Enterprise Voice functionality available to users.</span></span>

  - <span data-ttu-id="343b0-106">Un set di record di utilizzo PSTN (Public Switched Telephone Network) che definiscono i tipi di chiamate autorizzate.</span><span class="sxs-lookup"><span data-stu-id="343b0-106">A set of public switched telephone network (PSTN) usage records that define what types of calls are authorized.</span></span>

<div>

## <a name="planning-for-voice-policies"></a><span data-ttu-id="343b0-107">Pianificazione per i criteri vocali</span><span class="sxs-lookup"><span data-stu-id="343b0-107">Planning for Voice Policies</span></span>

<span data-ttu-id="343b0-108">La procedura seguente consente di pianificare i criteri vocali necessari per la distribuzione di VoIP aziendale:</span><span class="sxs-lookup"><span data-stu-id="343b0-108">The following steps will help you plan the voice policies that you will need for your Enterprise Voice deployment:</span></span>

  - <span data-ttu-id="343b0-109">Determinare come configurare il criterio vocale globale (i criteri vocali predefiniti installati con il prodotto).</span><span class="sxs-lookup"><span data-stu-id="343b0-109">Determine how you will configure your global voice policy (the default voice policy that is installed with the product).</span></span> <span data-ttu-id="343b0-110">Questo criterio si applica a tutti gli utenti di VoIP aziendale a cui non è assegnato esplicitamente un criterio a livello di sito o per utente.</span><span class="sxs-lookup"><span data-stu-id="343b0-110">This policy will apply to all Enterprise Voice users who are not explicitly assigned a site-level or per-user policy.</span></span>

  - <span data-ttu-id="343b0-111">Identificare i criteri vocali a livello di sito che potrebbero essere necessari.</span><span class="sxs-lookup"><span data-stu-id="343b0-111">Identify any site-level voice policies that you might need.</span></span>

  - <span data-ttu-id="343b0-112">Identificare qualsiasi criterio vocale per utente che potrebbe essere necessario.</span><span class="sxs-lookup"><span data-stu-id="343b0-112">Identify any per-user voice policies that you might need.</span></span>

  - <span data-ttu-id="343b0-113">Decidere quali funzionalità di chiamata abilitare per ogni criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="343b0-113">Decide which call features to enable for each voice policy.</span></span>

  - <span data-ttu-id="343b0-114">Determinare i record di utilizzo PSTN da configurare per ogni criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="343b0-114">Determine what PSTN usage records to configure for each voice policy.</span></span>

<div>

## <a name="voice-policy-scope"></a><span data-ttu-id="343b0-115">Ambito dei criteri vocali</span><span class="sxs-lookup"><span data-stu-id="343b0-115">Voice Policy Scope</span></span>

<span data-ttu-id="343b0-116">L' *ambito dei criteri vocali* determina il livello gerarchico in cui è possibile applicare i criteri.</span><span class="sxs-lookup"><span data-stu-id="343b0-116">*Voice policy scope* determines the hierarchical level at which the policy can be applied.</span></span> <span data-ttu-id="343b0-117">In Lync Server è possibile configurare i criteri vocali con i livelli di ambito seguenti (elencati tra i più specifici per i più generali).</span><span class="sxs-lookup"><span data-stu-id="343b0-117">In Lync Server, you can configure voice policies with the following scope levels (listed from the most specific to the most general).</span></span>

  - <span data-ttu-id="343b0-118">I **criteri vocali dell'utente** possono essere assegnati a singoli utenti, gruppi o oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="343b0-118">**User voice policy** can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="343b0-119">Questo è il criterio di livello più basso.</span><span class="sxs-lookup"><span data-stu-id="343b0-119">This is the lowest level policy.</span></span> <span data-ttu-id="343b0-120">I criteri vocali dell'utente possono essere distribuiti per abilitare le funzionalità per determinati utenti o gruppi in un sito, ma non per altri nello stesso sito.</span><span class="sxs-lookup"><span data-stu-id="343b0-120">User voice policies can be deployed to enable features for certain users or groups at a site, but not for others in the same site.</span></span> <span data-ttu-id="343b0-121">Ad esempio, potresti voler disabilitare la chiamata a lunga distanza per alcuni dipendenti.</span><span class="sxs-lookup"><span data-stu-id="343b0-121">For example, you may want to disable long distance dialing for some employees.</span></span> <span data-ttu-id="343b0-122">Allo scopo di assegnare un criterio vocale, un oggetto contatto viene considerato come un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="343b0-122">For the purpose of assigning a voice policy, a contact object is treated as an individual user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="343b0-123">È consigliabile distribuire un criterio vocale utente per gli utenti di VoIP aziendale del sito succursale registrati con la distribuzione del sito centrale o gli utenti registrati in un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="343b0-123">We recommend that you deploy a user voice policy for branch site Enterprise Voice users who are registered with the central site deployment, or users who are registered on a Survivable Branch Appliance.</span></span>

    
    </div>

  - <span data-ttu-id="343b0-124">I **criteri vocali del sito** si applicano a un intero sito, eccetto per gli utenti, i gruppi o gli oggetti contatto assegnati a un criterio vocale per l'utente.</span><span class="sxs-lookup"><span data-stu-id="343b0-124">**Site voice policy** applies to an entire site, except for any users, groups, or contact objects that are assigned a user voice policy.</span></span> <span data-ttu-id="343b0-125">Per definire un criterio vocale del sito, è necessario specificare il sito a cui si applicano i criteri.</span><span class="sxs-lookup"><span data-stu-id="343b0-125">To define a site voice policy, you must specify the site to which the policy applies.</span></span> <span data-ttu-id="343b0-126">Se non viene assegnato un criterio vocale per l'utente, viene usato il criterio vocale del sito.</span><span class="sxs-lookup"><span data-stu-id="343b0-126">If a user voice policy is not assigned, the site voice policy is used.</span></span>

  - <span data-ttu-id="343b0-127">Il criterio vocale **globale** è il criterio vocale predefinito che viene installato con il prodotto.</span><span class="sxs-lookup"><span data-stu-id="343b0-127">**Global voice policy** is the default voice policy that is installed with the product.</span></span> <span data-ttu-id="343b0-128">È possibile modificare il criterio vocale globale per soddisfare le esigenze specifiche dell'organizzazione, ma non è possibile rinominarla o eliminarla.</span><span class="sxs-lookup"><span data-stu-id="343b0-128">You can edit the global voice policy to meet the specific needs of your organization, but you cannot rename or delete it.</span></span> <span data-ttu-id="343b0-129">Questo criterio vocale si applica a tutti gli utenti di VoIP aziendale, ai gruppi e agli oggetti contatto nella distribuzione, a meno che non si configuri e assegni un criterio vocale con un ambito più specifico.</span><span class="sxs-lookup"><span data-stu-id="343b0-129">This voice policy applies to all Enterprise Voice users, groups, and contact objects in your deployment unless you configure and assign a voice policy with more specific scope.</span></span> <span data-ttu-id="343b0-130">Se si vuole disabilitare completamente questo criterio, assicurarsi che tutti i siti e gli utenti dispongano di criteri personalizzati assegnati.</span><span class="sxs-lookup"><span data-stu-id="343b0-130">If you want to disable this policy entirely, be sure that all sites and users have custom policies assigned to them.</span></span>

</div>

<div>

## <a name="call-features"></a><span data-ttu-id="343b0-131">Caratteristiche delle chiamate</span><span class="sxs-lookup"><span data-stu-id="343b0-131">Call Features</span></span>

<span data-ttu-id="343b0-132">È possibile abilitare o disabilitare le funzionalità di chiamata seguenti per ogni criterio vocale:</span><span class="sxs-lookup"><span data-stu-id="343b0-132">You can enable or disable the following call features for each voice policy:</span></span>

  - <span data-ttu-id="343b0-133">L' **inoltro di chiamata** consente agli utenti di inoltrare le chiamate ad altri telefoni e dispositivi client.</span><span class="sxs-lookup"><span data-stu-id="343b0-133">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="343b0-134">Abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="343b0-134">Enabled by default.</span></span>

  - <span data-ttu-id="343b0-135">La **delega** consente agli utenti di specificare ad altri utenti di inviare e ricevere chiamate per proprio conto.</span><span class="sxs-lookup"><span data-stu-id="343b0-135">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="343b0-136">Abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="343b0-136">Enabled by default.</span></span>

  - <span data-ttu-id="343b0-137">Il **trasferimento** delle chiamate consente agli utenti di trasferire le chiamate ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="343b0-137">**Call transfer** enables users to transfer calls to other users.</span></span> <span data-ttu-id="343b0-138">Abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="343b0-138">Enabled by default.</span></span>

  - <span data-ttu-id="343b0-139">**Call Park** consente agli utenti di parcheggiare le chiamate e quindi prendere la chiamata da un altro telefono o client.</span><span class="sxs-lookup"><span data-stu-id="343b0-139">**Call park** enables users to park calls and then pick up the call from a different phone or client.</span></span> <span data-ttu-id="343b0-140">Disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="343b0-140">Disabled by default.</span></span>

  - <span data-ttu-id="343b0-141">La **chiamata simultanea** consente alle chiamate in arrivo di squillare su un altro telefono, ad esempio un cellulare o altri dispositivi endpoint.</span><span class="sxs-lookup"><span data-stu-id="343b0-141">**Simultaneous ringing** enables incoming calls to ring on an additional phone (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="343b0-142">Abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="343b0-142">Enabled by default.</span></span>

  - <span data-ttu-id="343b0-143">La **chiamata del team** consente agli utenti di un team definito di rispondere alle chiamate per gli altri membri del team.</span><span class="sxs-lookup"><span data-stu-id="343b0-143">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="343b0-144">Abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="343b0-144">Enabled by default.</span></span>

  - <span data-ttu-id="343b0-145">La **reinstradazione PSTN** consente alle chiamate effettuate dagli utenti a cui è assegnato questo criterio ad altri utenti aziendali di essere reinstradati nella rete PSTN (Public Switched Telephone Network) se la WAN è congestionata o non disponibile.</span><span class="sxs-lookup"><span data-stu-id="343b0-145">**PSTN reroute** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable.</span></span> <span data-ttu-id="343b0-146">Abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="343b0-146">Enabled by default.</span></span>

  - <span data-ttu-id="343b0-147">**L'override dei criteri di larghezza di banda** consente agli amministratori di ignorare le decisioni sui criteri di controllo ammissione chiamata per un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="343b0-147">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user.</span></span> <span data-ttu-id="343b0-148">Disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="343b0-148">Disabled by default.</span></span>

  - <span data-ttu-id="343b0-149">La **traccia di chiamata** non consentita consente agli utenti di segnalare chiamate illecite tramite il client Lync e quindi contrassegna tali chiamate nei record dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="343b0-149">**Malicious call tracing** enables users to report malicious calls by using the Lync client, and then flags such calls in the call detail records.</span></span> <span data-ttu-id="343b0-150">Disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="343b0-150">Disabled by default.</span></span>

  - <span data-ttu-id="343b0-151">La funzione di **escape della segreteria telefonica** impedisce che le chiamate vengano immediatamente indirizzate al sistema di segreteria telefonica dell'utente quando è configurato lo squillo simultaneo e che il telefono sia disattivato, fuori batteria o fuori portata e sia basato su un valore timer.</span><span class="sxs-lookup"><span data-stu-id="343b0-151">**Voicemail escape** prevents calls from being immediately routed to the user’s mobile phone voicemail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range, and is based on a timer value.</span></span> <span data-ttu-id="343b0-152">Questa impostazione Abilita e Disabilita il timer e imposta il valore del timer.</span><span class="sxs-lookup"><span data-stu-id="343b0-152">This setting enables and disables the timer and sets the value of the timer.</span></span> <span data-ttu-id="343b0-153">Può essere configurato solo tramite Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="343b0-153">It can be configured only by using the Lync Server Management Shell.</span></span> <span data-ttu-id="343b0-154">Disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="343b0-154">Disabled by default.</span></span>

  - <span data-ttu-id="343b0-155">L' **inoltro di chiamata e l'uso simultaneo di chiamate PSTN** consentono agli amministratori di specificare lo stesso utilizzo PSTN dei criteri vocali per l'inoltro di chiamata e la suoneria simultanea, limitano l'inoltro di chiamata e lo squillo simultaneo agli utenti interni di Lync o specificano un uso PSTN personalizzato diverso dall'uso PSTN del criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="343b0-155">**Call forwarding and simultaneous ringing PSTN usages** enables administrators to specify the same PSTN usage as the voice policy for call forwarding and simultaneous ringing, restrict call forwarding and simultaneous ringing to internal Lync users only, or specify a custom PSTN usage that is different from the voice policy’s PSTN usage.</span></span> <span data-ttu-id="343b0-156">L'impostazione predefinita consiste nell'usare lo stesso utilizzo PSTN del criterio vocale per l'inoltro di chiamata e lo squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="343b0-156">The default is to use the same PSTN usage as the voice policy for call forwarding and simultaneous ringing.</span></span>

</div>

<div>

## <a name="pstn-usage-records"></a><span data-ttu-id="343b0-157">Record utilizzo PSTN</span><span class="sxs-lookup"><span data-stu-id="343b0-157">PSTN Usage Records</span></span>

<span data-ttu-id="343b0-158">Ogni criterio vocale deve avere uno o più record di utilizzo PSTN associati.</span><span class="sxs-lookup"><span data-stu-id="343b0-158">Each voice policy should have one or more associated PSTN usage records.</span></span> <span data-ttu-id="343b0-159">Gli usi PSTN possono essere associati a un criterio vocale allo scopo di effettuare chiamate simultanee e inoltro di chiamata.</span><span class="sxs-lookup"><span data-stu-id="343b0-159">PSTN usages can be associated with a voice policy for the purpose of simultaneous ringing and call forwarding only.</span></span> <span data-ttu-id="343b0-160">Per informazioni dettagliate sulla pianificazione dei record di utilizzo PSTN, vedere [record sull'utilizzo PSTN in Lync Server 2013](lync-server-2013-pstn-usage-records.md).</span><span class="sxs-lookup"><span data-stu-id="343b0-160">For details about planning PSTN usage records, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="343b0-161">L'ordine di utilizzo PSTN è fondamentale perché in corrispondenza degli utenti alle route la funzionalità di routing in uscita confronta gli usi PSTN dall'alto verso il basso.</span><span class="sxs-lookup"><span data-stu-id="343b0-161">PSTN usage order is critical because in matching users to routes, the outbound routing functionality compares PSTN usages from top to bottom.</span></span> <span data-ttu-id="343b0-162">Se il primo utilizzo corrisponde alla route di chiamata, viene usata tale route.</span><span class="sxs-lookup"><span data-stu-id="343b0-162">If the first usage matches the call route, that route is used.</span></span> <span data-ttu-id="343b0-163">In caso contrario, la funzionalità di routing in uscita analizza il successivo utilizzo PSTN nell'elenco e continua fino a quando non viene trovata una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="343b0-163">If not, the outbound routing functionality looks at the next PSTN usage on the list and continues until a match is found.</span></span> <span data-ttu-id="343b0-164">In effetti, i successivi usi PSTN includono il backup se il primo nell'elenco non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="343b0-164">In effect, the subsequent PSTN usages provide backup if the first one on the list is unavailable.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

