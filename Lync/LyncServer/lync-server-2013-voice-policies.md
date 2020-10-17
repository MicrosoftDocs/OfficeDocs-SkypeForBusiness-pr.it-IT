---
title: 'Lync Server 2013: criteri vocali'
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
ms.openlocfilehash: 8ca6719ce8d1822f8d1d49ac08dfc6b6f54df7e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535533"
---
# <a name="voice-policies-in-lync-server-2013"></a><span data-ttu-id="fa5cd-102">Criteri vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa5cd-102">Voice policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa5cd-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="fa5cd-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="fa5cd-104">I *criteri vocali* di Lync Server definiscono quanto segue per ogni utente, sito o organizzazione a cui è assegnato il criterio:</span><span class="sxs-lookup"><span data-stu-id="fa5cd-104">Lync Server *voice policies* define the following for each user, site, or organization that is assigned the policy:</span></span>

  - <span data-ttu-id="fa5cd-105">Un set di funzionalità di chiamata che possono essere abilitate o disabilitate per determinare la funzionalità VoIP aziendale disponibile per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-105">A set of calling features that can be enabled or disabled to determine the Enterprise Voice functionality available to users.</span></span>

  - <span data-ttu-id="fa5cd-106">Un set di record di utilizzo PSTN (Public Switched Telephone Network) che definiscono i tipi di chiamate autorizzati.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-106">A set of public switched telephone network (PSTN) usage records that define what types of calls are authorized.</span></span>

<div>

## <a name="planning-for-voice-policies"></a><span data-ttu-id="fa5cd-107">Pianificazione dei criteri vocali</span><span class="sxs-lookup"><span data-stu-id="fa5cd-107">Planning for Voice Policies</span></span>

<span data-ttu-id="fa5cd-108">I passaggi seguenti consentiranno di pianificare i criteri vocali necessari per la distribuzione di VoIP aziendale:</span><span class="sxs-lookup"><span data-stu-id="fa5cd-108">The following steps will help you plan the voice policies that you will need for your Enterprise Voice deployment:</span></span>

  - <span data-ttu-id="fa5cd-109">Stabilire come verrà configurato il criterio vocale globale, ovvero il criterio vocale predefinito installato con il prodotto).</span><span class="sxs-lookup"><span data-stu-id="fa5cd-109">Determine how you will configure your global voice policy (the default voice policy that is installed with the product).</span></span> <span data-ttu-id="fa5cd-110">Questo criterio si applica a tutti gli utenti di VoIP aziendale che non sono assegnati in modo esplicito a un criterio a livello di sito o per utente.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-110">This policy will apply to all Enterprise Voice users who are not explicitly assigned a site-level or per-user policy.</span></span>

  - <span data-ttu-id="fa5cd-111">Identificare eventuali criteri vocali a livello di sito che potrebbero essere necessari.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-111">Identify any site-level voice policies that you might need.</span></span>

  - <span data-ttu-id="fa5cd-112">Identificare eventuali criteri vocali per utente che potrebbero essere necessari.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-112">Identify any per-user voice policies that you might need.</span></span>

  - <span data-ttu-id="fa5cd-113">Decidere quali funzionalità di chiamata abilitare per ogni criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-113">Decide which call features to enable for each voice policy.</span></span>

  - <span data-ttu-id="fa5cd-114">Stabilire quali record di utilizzo PSTN configurare per ogni criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-114">Determine what PSTN usage records to configure for each voice policy.</span></span>

<div>

## <a name="voice-policy-scope"></a><span data-ttu-id="fa5cd-115">Ambito dei criteri vocali</span><span class="sxs-lookup"><span data-stu-id="fa5cd-115">Voice Policy Scope</span></span>

<span data-ttu-id="fa5cd-116">L'*ambito dei criteri vocali* determina il livello gerarchico a cui è possibile applicare il criterio.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-116">*Voice policy scope* determines the hierarchical level at which the policy can be applied.</span></span> <span data-ttu-id="fa5cd-117">In Lync Server, è possibile configurare i criteri vocali con i seguenti livelli di ambito (elencati tra i più specifici per il più generale).</span><span class="sxs-lookup"><span data-stu-id="fa5cd-117">In Lync Server, you can configure voice policies with the following scope levels (listed from the most specific to the most general).</span></span>

  - <span data-ttu-id="fa5cd-p103">Il **criterio vocale utente** può essere assegnato a singoli utenti, gruppi o oggetti contatto. Questo è il criterio di livello più basso. È possibile distribuire criteri vocali utente per abilitare le funzionalità per determinati utenti o gruppi in un sito, ma non per altri nello stesso sito. Si potrebbe decidere ad esempio di disabilitare le chiamate interurbane per alcuni dipendenti. Ai fini dell'assegnazione di un criterio vocale, un oggetto contatto viene considerato un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-p103">**User voice policy** can be assigned to individual users, groups, or contact objects. This is the lowest level policy. User voice policies can be deployed to enable features for certain users or groups at a site, but not for others in the same site. For example, you may want to disable long distance dialing for some employees. For the purpose of assigning a voice policy, a contact object is treated as an individual user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fa5cd-123">Si consiglia di distribuire un criterio vocale utente per gli utenti di VoIP aziendale del sito di succursale che sono registrati con la distribuzione del sito centrale o gli utenti registrati in un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-123">We recommend that you deploy a user voice policy for branch site Enterprise Voice users who are registered with the central site deployment, or users who are registered on a Survivable Branch Appliance.</span></span>

    
    </div>

  - <span data-ttu-id="fa5cd-p104">Il **criterio vocale di sito** si applica a un intero sito, con l'eccezione degli utenti, gruppi o oggetti contatto a cui è stato assegnato un criterio vocale utente. Per definire un criterio vocale di sito, è necessario specificare il sito a cui si applica il criterio. Se non viene assegnato un criterio vocale utente, viene utilizzato il criterio vocale di sito.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-p104">**Site voice policy** applies to an entire site, except for any users, groups, or contact objects that are assigned a user voice policy. To define a site voice policy, you must specify the site to which the policy applies. If a user voice policy is not assigned, the site voice policy is used.</span></span>

  - <span data-ttu-id="fa5cd-127">**Global Voice Policy** è il criterio vocale predefinito installato con il prodotto.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-127">**Global voice policy** is the default voice policy that is installed with the product.</span></span> <span data-ttu-id="fa5cd-128">È possibile modificare il criterio vocale globale per soddisfare le specifiche esigenze dell'organizzazione, ma non è possibile rinominarlo o eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-128">You can edit the global voice policy to meet the specific needs of your organization, but you cannot rename or delete it.</span></span> <span data-ttu-id="fa5cd-129">Questo criterio vocale è valido per tutti gli utenti, i gruppi e gli oggetti contatto di VoIP aziendale nella distribuzione, a meno che non si configuri e assegni un criterio vocale con un ambito più specifico.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-129">This voice policy applies to all Enterprise Voice users, groups, and contact objects in your deployment unless you configure and assign a voice policy with more specific scope.</span></span> <span data-ttu-id="fa5cd-130">Se si desidera disabilitare completamente questo criterio, assicurarsi che tutti i siti e gli utenti dispongano di criteri personalizzati assegnati.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-130">If you want to disable this policy entirely, be sure that all sites and users have custom policies assigned to them.</span></span>

</div>

<div>

## <a name="call-features"></a><span data-ttu-id="fa5cd-131">Funzionalità di chiamata</span><span class="sxs-lookup"><span data-stu-id="fa5cd-131">Call Features</span></span>

<span data-ttu-id="fa5cd-132">È possibile abilitare o disabilitare le funzionalità di chiamata seguenti per ogni criterio vocale:</span><span class="sxs-lookup"><span data-stu-id="fa5cd-132">You can enable or disable the following call features for each voice policy:</span></span>

  - <span data-ttu-id="fa5cd-p106">L'**inoltro di chiamata** consente agli utenti di inoltrare chiamate ad altri telefoni e dispositivi client. Funzionalità abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-p106">**Call forwarding** enables users to forward calls to other phones and client devices. Enabled by default.</span></span>

  - <span data-ttu-id="fa5cd-p107">La **delega** consente agli utenti di specificare altri utenti per l'invio e la ricezione delle chiamate per loro conto. Funzionalità abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-p107">**Delegation** enables users to specify other users to send and receive calls on their behalf. Enabled by default.</span></span>

  - <span data-ttu-id="fa5cd-p108">Il **trasferimento di chiamata** consente agli utenti di trasferire chiamate ad altri utenti. Funzionalità abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>

  - <span data-ttu-id="fa5cd-p109">Il **parcheggio di chiamata** consente agli utenti di parcheggiare le chiamate e quindi di rispondere da un telefono o client diverso. Funzionalità disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-p109">**Call park** enables users to park calls and then pick up the call from a different phone or client. Disabled by default.</span></span>

  - <span data-ttu-id="fa5cd-p110">Lo **squillo simultaneo** consente lo squillo su un telefono aggiuntivo (ad esempio, un cellulare) o altri dispositivi endpoint per le chiamate in arrivo. Funzionalità abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-p110">**Simultaneous ringing** enables incoming calls to ring on an additional phone (for example, a mobile phone) or other endpoint devices. Enabled by default.</span></span>

  - <span data-ttu-id="fa5cd-p111">L'**intercettazione team** consente agli utenti in uno team specificato di rispondere alle chiamate per gli altri membri del team. Funzionalità abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>

  - <span data-ttu-id="fa5cd-p112">Il **reindirizzamento PSTN** consente di reindirizzare le chiamate effettuate dagli utenti assegnati a questo criterio ad altri utenti dell'organizzazione sulla rete PSTN, in caso di congestione o non disponibilità della rete WAN. Funzionalità abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-p112">**PSTN reroute** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>

  - <span data-ttu-id="fa5cd-p113">L'**override dei criteri di larghezza di banda** consente agli amministratori di ignorare le decisioni per i criteri di controllo di ammissione di chiamata per un particolare utente. Funzionalità disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-p113">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user. Disabled by default.</span></span>

  - <span data-ttu-id="fa5cd-149">L' **analisi chiamata** non consentita consente agli utenti di segnalare chiamate dannose tramite il client Lync e quindi di contrassegnare tali chiamate nei record dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-149">**Malicious call tracing** enables users to report malicious calls by using the Lync client, and then flags such calls in the call detail records.</span></span> <span data-ttu-id="fa5cd-150">Questa funzionalità è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-150">Disabled by default.</span></span>

  - <span data-ttu-id="fa5cd-151">L' **escape della segreteria telefonica** impedisce che le chiamate vengano immediatamente instradate al sistema di segreteria telefonica del cellulare dell'utente quando è configurato lo squillo simultaneo e il telefono è spento, fuori dalla batteria o fuori portata e si basa su un valore timer.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-151">**Voicemail escape** prevents calls from being immediately routed to the user’s mobile phone voicemail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range, and is based on a timer value.</span></span> <span data-ttu-id="fa5cd-152">Questa impostazione consente di abilitare e disabilitare il timer e di impostare il valore del timer.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-152">This setting enables and disables the timer and sets the value of the timer.</span></span> <span data-ttu-id="fa5cd-153">È possibile configurarlo solo utilizzando Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-153">It can be configured only by using the Lync Server Management Shell.</span></span> <span data-ttu-id="fa5cd-154">Questa funzionalità è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-154">Disabled by default.</span></span>

  - <span data-ttu-id="fa5cd-p116">La funzionalità **Usi PSTN inoltro di chiamata e squillo simultaneo dei telefoni** consente agli amministratori di specificare un utilizzo PSTN uguale al criterio vocale per l'inoltro di chiamata e lo squillo simultaneo, di limitare questo tipo di inoltro e di squillo ai soli utenti interni di Lync oppure di specificare un utilizzo PSTN personalizzato diverso dall'utilizzo PSTN del criterio vocale. Il comportamento predefinito prevede l'applicazione di un utilizzo PSTN uguale al criterio vocale per l'inoltro di chiamata e lo squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-p116">**Call forwarding and simultaneous ringing PSTN usages** enables administrators to specify the same PSTN usage as the voice policy for call forwarding and simultaneous ringing, restrict call forwarding and simultaneous ringing to internal Lync users only, or specify a custom PSTN usage that is different from the voice policy’s PSTN usage. The default is to use the same PSTN usage as the voice policy for call forwarding and simultaneous ringing.</span></span>

</div>

<div>

## <a name="pstn-usage-records"></a><span data-ttu-id="fa5cd-157">Record di utilizzo PSTN</span><span class="sxs-lookup"><span data-stu-id="fa5cd-157">PSTN Usage Records</span></span>

<span data-ttu-id="fa5cd-158">A ogni criterio vocale dovrebbero essere associati uno o più record di utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-158">Each voice policy should have one or more associated PSTN usage records.</span></span> <span data-ttu-id="fa5cd-159">Gli utilizzi PSTN possono essere associati a un criterio vocale solo ai fini dello squillo simultaneo e dell'inoltro di chiamata.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-159">PSTN usages can be associated with a voice policy for the purpose of simultaneous ringing and call forwarding only.</span></span> <span data-ttu-id="fa5cd-160">Per informazioni dettagliate sulla pianificazione dei record di utilizzo PSTN, vedere [PSTN Usage Records in Lync Server 2013](lync-server-2013-pstn-usage-records.md).</span><span class="sxs-lookup"><span data-stu-id="fa5cd-160">For details about planning PSTN usage records, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fa5cd-p118">L'ordine degli utilizzi PSTN è fondamentale perché, in fase di abbinamento degli utenti alle route, la funzionalità di routing in uscita confronta gli utilizzi PSTN in ordine, dall'alto verso il basso. Se il primo utilizzo corrisponde alla route della chiamata, viene utilizzata tale route. In caso contrario, la funzionalità di routing in uscita cerca l'utilizzo PSTN successivo nell'elenco e continua fino a trovare una corrispondenza. In effetti, gli utilizzi PSTN successivi rappresentano un backup nel caso il primo nell'elenco non sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="fa5cd-p118">PSTN usage order is critical because in matching users to routes, the outbound routing functionality compares PSTN usages from top to bottom. If the first usage matches the call route, that route is used. If not, the outbound routing functionality looks at the next PSTN usage on the list and continues until a match is found. In effect, the subsequent PSTN usages provide backup if the first one on the list is unavailable.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

