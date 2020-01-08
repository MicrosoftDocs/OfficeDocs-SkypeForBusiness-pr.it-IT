---
title: 'Lync Server 2013: Requisiti di resilienza dei siti di succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ff969638f8c46abdd0ebcc8d11821a6a31b3c76
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a><span data-ttu-id="20e3f-102">Requisiti di resilienza dei siti di succursale per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20e3f-102">Branch-site resiliency requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20e3f-103">_**Argomento Ultima modifica:** 2014-02-25_</span><span class="sxs-lookup"><span data-stu-id="20e3f-103">_**Topic Last Modified:** 2014-02-25_</span></span>

<span data-ttu-id="20e3f-104">Questo argomento consente di preparare gli utenti per la sopravvivenza della filiale e della segreteria telefonica e specifica anche i requisiti hardware e software pertinenti.</span><span class="sxs-lookup"><span data-stu-id="20e3f-104">This topic will help you to prepare users for branch-site resiliency and voice mail survivability, and also specifies the relevant hardware and software requirements.</span></span>

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a><span data-ttu-id="20e3f-105">Preparazione degli utenti della filiale per la resilienza del sito filiale</span><span class="sxs-lookup"><span data-stu-id="20e3f-105">Preparing Branch Users for Branch-Site Resiliency</span></span>

<span data-ttu-id="20e3f-106">Preparare gli utenti per la resilienza del sito di succursale impostando il pool di registrar come Survivable Branch Appliance (SBA) o Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="20e3f-106">Prepare users for branch-site resiliency by setting their Registrar pool as the Survivable Branch Appliance (SBA) or Survivable Branch Server.</span></span>

<div>

## <a name="registrar-assignments-for-branch-users"></a><span data-ttu-id="20e3f-107">Assegnazioni del registrar per gli utenti della filiale</span><span class="sxs-lookup"><span data-stu-id="20e3f-107">Registrar Assignments for Branch Users</span></span>

<span data-ttu-id="20e3f-108">Indipendentemente dalla soluzione di resilienza del sito di succursale scelta, è necessario assegnare un registrar principale a ogni utente.</span><span class="sxs-lookup"><span data-stu-id="20e3f-108">Regardless of which branch-site resiliency solution you choose, you will need to assign a primary Registrar to each user.</span></span> <span data-ttu-id="20e3f-109">Gli utenti del sito succursale devono sempre registrarsi con il Registrar presso il sito della filiale, indipendentemente dal fatto che il registrar si trovi nella Survivable Branch Appliance, Survivable Branch Server o nel server autonomo Lync Server 2013 standard o Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="20e3f-109">Branch site users should always register with the Registrar at the branch site, regardless of whether that Registrar resides in the Survivable Branch Appliance, Survivable Branch Server, or stand-alone Lync Server 2013 Standard or Enterprise Edition server.</span></span> <span data-ttu-id="20e3f-110">È necessario un record di risorse del servizio DNS (Domain Name System) (SRV) in modo che un client possa individuare il pool di registrar.</span><span class="sxs-lookup"><span data-stu-id="20e3f-110">A domain name system (DNS) service (SRV) resource record is required so that a client can discover its Registrar pool.</span></span> <span data-ttu-id="20e3f-111">Se il Survivable Branch Appliance diventa non disponibile, questo è il modo in cui i client del sito Branch verranno automaticamente individuati nel registrar.</span><span class="sxs-lookup"><span data-stu-id="20e3f-111">If the Survivable Branch Appliance becomes unavailable, this is how branch site clients will automatically discover the backup Registrar.</span></span>

<span data-ttu-id="20e3f-112">Se un sito di succursale non ha un server DNS, esistono due modi alternativi per configurare l'individuazione di Survivable Branch Appliance o Survivable Branch Server:</span><span class="sxs-lookup"><span data-stu-id="20e3f-112">If a branch site does not have a DNS server, there are two alternative ways to configure discovery of the Survivable Branch Appliance or Survivable Branch Server:</span></span>

  - <span data-ttu-id="20e3f-113">Configurare l'opzione DHCP 120 nel server DHCP (Dynamic Host Configuration Protocol) del sito della filiale in modo che punti al nome di dominio completo (FQDN) del Survivable Branch Appliance o Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="20e3f-113">Configure DHCP option 120 on the branch site’s Dynamic Host Configuration Protocol (DHCP) server to point to the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="20e3f-114">Configurare Survivable Branch Appliance o Survivable Branch Server per rispondere alle query di 120 DHCP.</span><span class="sxs-lookup"><span data-stu-id="20e3f-114">Configure the Survivable Branch Appliance or Survivable Branch Server to respond to DHCP 120 queries.</span></span>

</div>

<div>

## <a name="voice-routing-for-branch-users"></a><span data-ttu-id="20e3f-115">Routing vocale per gli utenti di Branch</span><span class="sxs-lookup"><span data-stu-id="20e3f-115">Voice Routing for Branch Users</span></span>

<span data-ttu-id="20e3f-116">È consigliabile creare un criterio VoIP (Voice over Internet Protocol) separato per gli utenti in un sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="20e3f-116">We recommend that you create a separate user-level Voice over Internet Protocol (VoIP) policy for users in a branch site.</span></span> <span data-ttu-id="20e3f-117">Questo criterio deve includere una route primaria che usa il gateway Survivable Branch Appliance o Branch Server e una o più route di backup che usano un trunk con un gateway PSTN (Public Switched Telephone Network) nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="20e3f-117">This policy should include a primary route that uses the Survivable Branch Appliance or branch server gateway, and one or more backup routes that use a trunk with a public switched telephone network (PSTN) gateway at the central site.</span></span> <span data-ttu-id="20e3f-118">Se la route principale non è disponibile, viene usata invece la route di backup che usa uno o più gateway di sito centrale.</span><span class="sxs-lookup"><span data-stu-id="20e3f-118">If the primary route is unavailable, the backup route that uses one or more central site gateways is used instead.</span></span> <span data-ttu-id="20e3f-119">In questo modo, indipendentemente dalla posizione in cui un utente è registrato, nel registrar del sito succursale o nel pool di registrazione del backup presso il sito centrale, il criterio VoIP dell'utente è sempre attivo.</span><span class="sxs-lookup"><span data-stu-id="20e3f-119">This way, regardless of where a user is registered—on the branch site Registrar or the backup Registrar pool at the central site—the user’s VoIP policy is always in effect.</span></span> <span data-ttu-id="20e3f-120">Si tratta di una considerazione importante per gli scenari di failover.</span><span class="sxs-lookup"><span data-stu-id="20e3f-120">This is an important consideration for failover scenarios.</span></span> <span data-ttu-id="20e3f-121">Ad esempio, se è necessario rinominare il Survivable Branch Appliance o riconfigurare Survivable Branch Appliance per connettersi a un pool di registrar di backup presso il sito centrale, è necessario trasferire gli utenti del sito della filiale nel sito centrale per la durata.</span><span class="sxs-lookup"><span data-stu-id="20e3f-121">For example, if you need to rename the Survivable Branch Appliance or reconfigure the Survivable Branch Appliance to connect to a backup Registrar pool at the central site, then you must move branch site users to the central site for the duration.</span></span> <span data-ttu-id="20e3f-122">Per informazioni dettagliate sulla ridenominazione o la riconfigurazione di un Survivable Branch Appliance, vedere l' [Appendice B: gestione di un Survivable Branch Appliance in Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) nella documentazione relativa alla distribuzione. Se gli utenti non hanno criteri VoIP a livello di utente o piani di chiamata a livello di utente, quando gli utenti vengono spostati in un altro sito, i criteri VoIP a livello di sito e i piani di chiamata a livello di sito del sito centrale si applicano agli utenti per impostazione predefinita, anziché i criteri VoIP a livello di sito del sito di succursale e i dial plan.</span><span class="sxs-lookup"><span data-stu-id="20e3f-122">(For details about renaming or reconfiguring a Survivable Branch Appliance, see [Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) in the Deployment documentation.) If those users do not have user-level VoIP policies or user-level dial plans, when the users are moved to another site, the site-level VoIP policies and site-level dial plans of the central site apply to the users by default, instead of the branch site site-level VoIP policies and dial plans,.</span></span> <span data-ttu-id="20e3f-123">In questo scenario, a meno che i criteri VoIP a livello di sito e i piani di chiamata a livello di sito usati dal pool di registrazione di backup possano essere applicati anche agli utenti del sito succursale, le chiamate non riusciranno.</span><span class="sxs-lookup"><span data-stu-id="20e3f-123">In this scenario, unless the site-level VoIP policies and site-level dial plans used by the backup Registrar pool can also apply to the branch site users, their calls will fail.</span></span> <span data-ttu-id="20e3f-124">Ad esempio, se gli utenti di un sito di filiale che si trovano in Giappone vengono spostati in un sito centrale di Redmond, un dial plan con regole di normalizzazione che prevedono + 1425 a tutte le chiamate a 7 cifre è improbabile che si traducano in modo appropriato le chiamate per tali utenti.</span><span class="sxs-lookup"><span data-stu-id="20e3f-124">For example, if users from a branch site located in Japan are moved to a central site in Redmond, then a dial plan with normalization rules that prepend +1425 to all 7-digit calls is unlikely to appropriately translate calls for those users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="20e3f-125">Quando si crea una route di backup di una filiale, è consigliabile aggiungere due record di utilizzo PSTN al criterio utente della filiale e assegnare le route separate a ognuna di esse.</span><span class="sxs-lookup"><span data-stu-id="20e3f-125">When you create a branch office backup route, we recommend that you add two PSTN phone usage records to the branch office user policy and assign separate routes to each one.</span></span> <span data-ttu-id="20e3f-126">La route First o Primary indirizza le chiamate al gateway associato a Survivable Branch Appliance (SBA) o Branch Server; la route secondo o backup consentirebbe di indirizzare le chiamate al gateway nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="20e3f-126">The first, or primary, route would direct calls to the gateway associated with the Survivable Branch Appliance (SBA) or branch server; the second, or backup, route would direct calls to the gateway at the central site.</span></span> <span data-ttu-id="20e3f-127">In indirizzamento delle chiamate, l'SBA o il server di succursale tenterà tutte le route assegnate al primo record di utilizzo PSTN prima di tentare il secondo record di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="20e3f-127">In directing calls, the SBA or branch server will attempt all routes assigned to the first PSTN usage record before attempting the second usage record.</span></span>



</div>

<span data-ttu-id="20e3f-128">Per assicurarti che le chiamate in ingresso agli utenti del sito succursale raggiungano questi utenti quando il gateway di succursale o il componente Windows del sito Survivable Branch Appliance non è disponibile (il che accadrebbe, ad esempio, se il Survivable Branch Appliance o Branch il gateway non è più disponibile per la manutenzione), crea una route di failover nel gateway (o usa il provider di chiamate dirette in diretta) per reindirizzare le chiamate in arrivo al pool di registrazione del backup presso il sito centrale.</span><span class="sxs-lookup"><span data-stu-id="20e3f-128">To help ensure that inbound calls to branch site users will reach those users when the branch gateway or the Windows component of the Survivable Branch Appliance site is unavailable (which would happen, for example, if the Survivable Branch Appliance or branch gateway were down for maintenance), create a failover route on the gateway (or work with your Direct Inward Dialing (DID) provider) to redirect incoming calls to the backup Registrar pool at the central site.</span></span> <span data-ttu-id="20e3f-129">Da lì le chiamate verranno instradate sul collegamento WAN agli utenti di Branch.</span><span class="sxs-lookup"><span data-stu-id="20e3f-129">From there, the calls will be routed over the WAN link to branch users.</span></span> <span data-ttu-id="20e3f-130">Assicurarsi che la route traguardi i numeri in modo che siano conformi al gateway PSTN o ad altri formati di numeri di telefono accettati del peer trunk.</span><span class="sxs-lookup"><span data-stu-id="20e3f-130">Be sure that the route translates numbers to comply with the PSTN gateway or other trunk peer’s accepted phone number formats.</span></span> <span data-ttu-id="20e3f-131">Per informazioni dettagliate sulla creazione di una route di failover, vedere [configurazione di una route di failover in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span><span class="sxs-lookup"><span data-stu-id="20e3f-131">For details about creating a failover route, see [Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span></span> <span data-ttu-id="20e3f-132">Creare anche piani di chiamata a livello di servizio per il trunk associato al gateway nel sito della filiale per normalizzare le chiamate in arrivo.</span><span class="sxs-lookup"><span data-stu-id="20e3f-132">Also create service-level dial plans for the trunk associated with the gateway at the branch site to normalize incoming calls.</span></span> <span data-ttu-id="20e3f-133">Se si dispone di due appliance Survivable Branch in un sito di succursale, è possibile creare un dial plan a livello di sito per entrambi, a meno che non sia necessario un piano separato a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="20e3f-133">If you have two Survivable Branch Appliances at a branch site, you can create a site-level dial plan for both unless a separate service-level plan for each is necessary.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="20e3f-134">Per tenere conto del consumo di risorse del sito centrale da parte di tutti gli utenti del sito di succursale che si basano sul sito centrale per presenza, conferenza o failover, è consigliabile considerare ogni utente del sito filiale come se l'utente fosse registrato presso il sito centrale.</span><span class="sxs-lookup"><span data-stu-id="20e3f-134">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as if the user were registered with the central site.</span></span> <span data-ttu-id="20e3f-135">Attualmente non esistono limiti al numero di utenti del sito succursale, inclusi gli utenti registrati con un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="20e3f-135">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>



</div>

<span data-ttu-id="20e3f-136">Ti consigliamo anche di creare un dial plan a livello di utente e un criterio vocale e quindi assegnarlo agli utenti del sito succursale.</span><span class="sxs-lookup"><span data-stu-id="20e3f-136">We also recommend that you create a user-level dial plan and voice policy, and then assign it to branch site users.</span></span> <span data-ttu-id="20e3f-137">Per informazioni dettagliate, vedere [creare un dial plan in Lync server 2013](lync-server-2013-create-a-dial-plan.md) e [creare i criteri di routing VoIP per gli utenti di succursale in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="20e3f-137">For details, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) and [Create the VoIP routing policy for branch users in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) in the Deployment documentation.</span></span>

<div>

## <a name="routing-extension-numbers"></a><span data-ttu-id="20e3f-138">Numeri di interno di routing</span><span class="sxs-lookup"><span data-stu-id="20e3f-138">Routing Extension Numbers</span></span>

<span data-ttu-id="20e3f-139">Quando si preparano i dial plan e i criteri vocali per gli utenti del sito succursale, assicurarsi di includere regole di normalizzazione e regole di traduzione corrispondenti alle stringhe e al formato numerico usati nell'attributo msRTCSIP-line (o URI di linea), in modo che le chiamate di Lync 2013 siano abilitate tra Branch Gli utenti del sito e gli utenti del sito centrale verranno instradati correttamente, in particolare quando le chiamate devono essere reinstradate tramite la rete PSTN perché il collegamento WAN non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="20e3f-139">When preparing dial plans and voice policies for branch site users, be sure to include normalization rules and translation rules that match the strings and number format used in the msRTCSIP-line (or Line URI) attribute, so that Lync 2013 calls enabled between branch site users and central site users will be routed correctly—particularly when calls must be rerouted over the PSTN because the WAN link is unavailable.</span></span> <span data-ttu-id="20e3f-140">Ci sono inoltre considerazioni speciali per i numeri composti che includono numeri di interno, ma solo numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="20e3f-140">Additionally, there are special considerations for dialed numbers that include extension numbers, rather just phone numbers.</span></span>

<span data-ttu-id="20e3f-141">Regole di normalizzazione e traduzioni che corrispondono a URI di linea che contengono un numero di interno, sia in esclusiva che in aggiunta a un numero di telefono E. 164 completo, hanno requisiti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="20e3f-141">Normalization rules and translations rules that match Line URIs that contain an extension number, whether exclusively or in addition to a full E.164 phone number, have additional requirements.</span></span> <span data-ttu-id="20e3f-142">Questa sezione descrive diversi scenari di esempio per instradare le chiamate per gli URI di linea con un numero di interno.</span><span class="sxs-lookup"><span data-stu-id="20e3f-142">This section describes several example scenarios to route calls for Line URIs with an extension number.</span></span>

<span data-ttu-id="20e3f-143">Se l'organizzazione non ha numeri di telefono diretti per singoli utenti e l'URI di linea di ogni utente è configurato con *solo* un numero di interno, gli utenti interni possono chiamarsi a vicenda componendo solo un numero di interno.</span><span class="sxs-lookup"><span data-stu-id="20e3f-143">If your organization does not have Direct Inward Dial (DID) phone numbers configured for individual users and the Line URI of each user is configured with *only* an extension number, internal users can call one another by dialing only an extension number.</span></span> <span data-ttu-id="20e3f-144">Tuttavia, è necessario configurare le regole di normalizzazione che possono essere applicate alle chiamate da un utente di un sito di succursale a un utente del sito centrale, che corrispondono ai numeri di interno.</span><span class="sxs-lookup"><span data-stu-id="20e3f-144">However, you must configure normalization rules that can apply to calls from a branch site user to a central site user, that match the extension numbers.</span></span>

<span data-ttu-id="20e3f-145">In uno scenario in cui il collegamento WAN tra un sito di succursale e un sito centrale è disponibile, le chiamate dagli utenti del sito della filiale agli utenti del sito centrale non richiedono la regola di normalizzazione corrispondente per tradurre il numero perché la chiamata non viene instradata tramite la rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="20e3f-145">In a scenario where the WAN link between a branch site and a central site is available, calls from branch site users to central site users do not require the matching normalization rule to translate the number because the call is not routed over the PSTN.</span></span> <span data-ttu-id="20e3f-146">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="20e3f-146">For example:</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20e3f-147">Nome regola</span><span class="sxs-lookup"><span data-stu-id="20e3f-147">Rule name</span></span></th>
<th><span data-ttu-id="20e3f-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20e3f-148">Description</span></span></th>
<th><span data-ttu-id="20e3f-149">Schema numerico</span><span class="sxs-lookup"><span data-stu-id="20e3f-149">Number pattern</span></span></th>
<th><span data-ttu-id="20e3f-150">Conversione</span><span class="sxs-lookup"><span data-stu-id="20e3f-150">Translation</span></span></th>
<th><span data-ttu-id="20e3f-151">Esempio</span><span class="sxs-lookup"><span data-stu-id="20e3f-151">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20e3f-152">5digitExtensions</span><span class="sxs-lookup"><span data-stu-id="20e3f-152">5digitExtensions</span></span></p></td>
<td><p><span data-ttu-id="20e3f-153">Non traduce i numeri a 5 cifre</span><span class="sxs-lookup"><span data-stu-id="20e3f-153">Does not translate 5-digit numbers</span></span></p></td>
<td><p><span data-ttu-id="20e3f-154">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="20e3f-154">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="20e3f-155">$1</span><span class="sxs-lookup"><span data-stu-id="20e3f-155">$1</span></span></p></td>
<td><p><span data-ttu-id="20e3f-156">10001 non viene tradotto</span><span class="sxs-lookup"><span data-stu-id="20e3f-156">10001 is not translated</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="20e3f-157">È inoltre necessario includere i numeri di interno per scenari specifici, ad esempio quando il collegamento WAN tra un sito di succursale e un sito centrale non è disponibile e una chiamata da un sito di succursale deve essere instradata tramite la rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="20e3f-157">You must also accommodate extension numbers for specific scenarios, such as when the WAN link between a branch site and central site is unavailable and a call from a branch site must be routed over the PSTN.</span></span> <span data-ttu-id="20e3f-158">Durante un'interruzione WAN, se un utente del sito filiale chiama un utente del sito centrale solo tramite la chiamata dell'estensione dell'utente del sito centrale, è necessario disporre di una regola di traduzione in uscita che aggiunga il numero di telefono completo dell'utente del sito centrale.</span><span class="sxs-lookup"><span data-stu-id="20e3f-158">During a WAN outage, if a branch site user calls a central site user only by dialing the central site user’s extension, you must have an outbound translation rule that adds the central site user’s full phone number.</span></span> <span data-ttu-id="20e3f-159">Se l'URI di linea di un utente contiene il numero di telefono completo dell'organizzazione e il numero di interno univoco dell'utente invece di un numero di telefono completo univoco per l'utente, è necessario disporre di una regola di traduzione in uscita che aggiunga il numero di telefono completo dell'organizzazione. .</span><span class="sxs-lookup"><span data-stu-id="20e3f-159">If a user’s Line URI contains your organization’s full phone number and the user’s unique extension number instead of a full phone number that is unique to the user, then you must have an outbound translation rule that adds your organization’s full phone number instead.</span></span> <span data-ttu-id="20e3f-160">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="20e3f-160">For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20e3f-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20e3f-161">Description</span></span></th>
<th><span data-ttu-id="20e3f-162">Modello di corrispondenza</span><span class="sxs-lookup"><span data-stu-id="20e3f-162">Matching pattern</span></span></th>
<th><span data-ttu-id="20e3f-163">Conversione</span><span class="sxs-lookup"><span data-stu-id="20e3f-163">Translation</span></span></th>
<th><span data-ttu-id="20e3f-164">Esempio</span><span class="sxs-lookup"><span data-stu-id="20e3f-164">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20e3f-165">Converte i numeri a 5 cifre in un numero di telefono e un'estensione di un utente</span><span class="sxs-lookup"><span data-stu-id="20e3f-165">Translates 5-digit numbers to a user’s phone number and extension</span></span></p></td>
<td><p><span data-ttu-id="20e3f-166">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="20e3f-166">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="20e3f-167">+ 14255550123; ext = $1</span><span class="sxs-lookup"><span data-stu-id="20e3f-167">+14255550123;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="20e3f-168">10001 viene convertito in + 14255550123; ext = 10001</span><span class="sxs-lookup"><span data-stu-id="20e3f-168">10001 is translated to +14255550123;ext=10001</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20e3f-169">Converte i numeri a 5 cifre nel numero di telefono dell'organizzazione e nell'estensione di un utente</span><span class="sxs-lookup"><span data-stu-id="20e3f-169">Translates 5-digit numbers to your organization’s phone number and a user’s extension</span></span></p></td>
<td><p><span data-ttu-id="20e3f-170">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="20e3f-170">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="20e3f-171">+ 14255550100; ext = $1</span><span class="sxs-lookup"><span data-stu-id="20e3f-171">+14255550100;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="20e3f-172">10001 viene convertito in + 14255550100; ext = 10001</span><span class="sxs-lookup"><span data-stu-id="20e3f-172">10001 is translated to +14255550100;ext=10001</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="20e3f-173">In questo scenario, se il peer trunk che gestisce il reinstradamento alla rete PSTN non supporta i numeri di interno, la regola di traduzione in uscita deve anche rimuovere il numero di interno.</span><span class="sxs-lookup"><span data-stu-id="20e3f-173">In this scenario, if the trunk peer that handles rerouting to the PSTN does not support extension numbers, then the outbound translation rule must also remove the extension number.</span></span> <span data-ttu-id="20e3f-174">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="20e3f-174">For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20e3f-175">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20e3f-175">Description</span></span></th>
<th><span data-ttu-id="20e3f-176">Modello di corrispondenza</span><span class="sxs-lookup"><span data-stu-id="20e3f-176">Matching pattern</span></span></th>
<th><span data-ttu-id="20e3f-177">Conversione</span><span class="sxs-lookup"><span data-stu-id="20e3f-177">Translation</span></span></th>
<th><span data-ttu-id="20e3f-178">Esempio</span><span class="sxs-lookup"><span data-stu-id="20e3f-178">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20e3f-179">Rimuove l'estensione dai numeri di telefono con le estensioni</span><span class="sxs-lookup"><span data-stu-id="20e3f-179">Removes extension from phone numbers with extensions</span></span></p></td>
<td><p><span data-ttu-id="20e3f-180">^\+(\d *); EXT = (\d*) $</span><span class="sxs-lookup"><span data-stu-id="20e3f-180">^\+(\d *);ext=(\d*)$</span></span></p></td>
<td><p><span data-ttu-id="20e3f-181">+ $1</span><span class="sxs-lookup"><span data-stu-id="20e3f-181">+$1</span></span></p></td>
<td><p><span data-ttu-id="20e3f-182">+ 14255550123; ext = 10001 viene tradotto in + 14255550123</span><span class="sxs-lookup"><span data-stu-id="20e3f-182">+14255550123;ext=10001 is translated to +14255550123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="20e3f-183">Indipendentemente dal fatto che sia disponibile un collegamento WAN, se l'organizzazione non ha numeri DID configurati per singoli utenti e l'URI di linea per un utente contiene il numero di telefono dell'organizzazione e il numero di interno univoco dell'utente, è necessario configurare il URI della linea numero di telefono dell'organizzazione con un numero raggiungibile dal peer trunk o dal gateway PSTN del sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="20e3f-183">Whether or not a WAN link is available, if your organization does not have DID numbers configured for individual users and the Line URI for a user contains your organization’s phone number and the user’s unique extension number, then you must configure your organization’s phone number Line URI with a number that is reachable by the trunk peer or PSTN gateway at the branch site.</span></span> <span data-ttu-id="20e3f-184">Devi anche configurare l'URI della linea di numeri di telefono dell'organizzazione per includere la relativa estensione univoca per le chiamate da instradare al numero.</span><span class="sxs-lookup"><span data-stu-id="20e3f-184">You must also configure your organization’s phone number Line URI to include its own unique extension for calls to be routed to that number.</span></span>

<span data-ttu-id="20e3f-185">Per informazioni dettagliate sulle chiamate da un utente del sito centrale a un utente di un sito di succursale quando il collegamento WAN tra i siti non è disponibile, vedere "preparazione per la sopravvivenza della segreteria telefonica" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="20e3f-185">For details about calls from a central site user to a branch site user when the WAN link between the sites is unavailable, see "Preparing for Voice Mail Survivability" later in this topic.</span></span> <span data-ttu-id="20e3f-186">Per informazioni dettagliate sui dial plan e sulle regole di normalizzazione, incluse altre regole di esempio, vedere [dial plan e regole di normalizzazione in Lync server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) nella documentazione di pianificazione e [configurazione di dial plan in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="20e3f-186">For details about dial plans and normalization rules, including other sample rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation and [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) in the Deployment documentation.</span></span> <span data-ttu-id="20e3f-187">Per informazioni dettagliate sulle regole di traduzione in uscita, vedere [regole di traduzione in Lync server 2013](lync-server-2013-translation-rules.md) nella documentazione relativa alla pianificazione e [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="20e3f-187">For details about outbound translation rules, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md) in the Planning documentation and [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a><span data-ttu-id="20e3f-188">Preparazione per la sopravvivenza della segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="20e3f-188">Preparing for Voice Mail Survivability</span></span>

<span data-ttu-id="20e3f-189">La messaggistica unificata di Exchange viene in genere installata solo in un sito centrale e non nei siti di succursale.</span><span class="sxs-lookup"><span data-stu-id="20e3f-189">Exchange Unified Messaging (UM) is usually installed only at a central site and not at branch sites.</span></span> <span data-ttu-id="20e3f-190">Un chiamante dovrebbe essere in grado di uscire da un messaggio di segreteria telefonica, anche se il collegamento WAN tra sito di succursale e sito centrale non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="20e3f-190">A caller should be able to leave a voice mail message, even if the WAN link between branch site and central site is unavailable.</span></span> <span data-ttu-id="20e3f-191">Di conseguenza, la configurazione dell'URI di linea per il numero di telefono dell'operatore automatico di messaggistica unificata di Exchange che fornisce la segreteria telefonica per gli utenti del sito filiale richiede considerazioni particolari, oltre al criterio vocale, al dial plan e alle regole di normalizzazione applicabili alla segreteria telefonica. numero.</span><span class="sxs-lookup"><span data-stu-id="20e3f-191">As a result, configuring the Line URI for the Exchange UM Auto Attendant phone number that provides voice mail for branch site users requires special considerations, in addition to the voice policy, dial plan, and normalization rules applicable to that voice mail number.</span></span>

<span data-ttu-id="20e3f-192">Survivable Branch Appliances (SBAs) e Survivable Branch Servers garantiscono la sopravvivenza della segreteria telefonica per gli utenti di Branch durante un'interruzione WAN.</span><span class="sxs-lookup"><span data-stu-id="20e3f-192">Survivable Branch Appliances (SBAs) and Survivable Branch Servers provide voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="20e3f-193">In particolare, se si usa un Survivable Branch Appliance o Survivable Branch Server e la WAN non è disponibile, l'SBA o Survivable Branch Server reindirizza le chiamate senza risposta tramite la rete PSTN alla messaggistica unificata di Exchange nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="20e3f-193">Specifically, if you are using a Survivable Branch Appliance or Survivable Branch Server and the WAN becomes unavailable, the SBA or Survivable Branch Server reroutes unanswered calls over the PSTN to Exchange UM at the central site.</span></span> <span data-ttu-id="20e3f-194">Con un SBA o un Survivable Branch Server, gli utenti possono anche recuperare i messaggi della segreteria telefonica tramite la rete PSTN durante un'interruzione WAN.</span><span class="sxs-lookup"><span data-stu-id="20e3f-194">With a SBA or Survivable Branch Server, users can also retrieve voice mail messages through the PSTN during a WAN outage.</span></span> <span data-ttu-id="20e3f-195">Infine, durante un'interruzione WAN il Survivable Branch Appliance o Survivable Branch Server accoda le notifiche di mancata chiamata e quindi le carica nel server Messaggistica unificata di Exchange quando viene ripristinata la rete WAN.</span><span class="sxs-lookup"><span data-stu-id="20e3f-195">Finally, during a WAN outage the Survivable Branch Appliance or Survivable Branch Server queues missed-call notifications and then uploads them to the Exchange UM server when the WAN is restored.</span></span> <span data-ttu-id="20e3f-196">Per assicurarti che il reindirizzamento della segreteria telefonica sia resiliente, assicurati di aggiungere una voce per il nome di dominio completo del pool di siti centrali e una voce per il nome di dominio completo del server perimetrale nel file hosts nel Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="20e3f-196">To help ensure that voice mail rerouting is resilient, be sure that you add an entry for the central site pool’s FQDN and an entry for the Edge Server FQDN to the hosts file on the Survivable Branch Server.</span></span> <span data-ttu-id="20e3f-197">In caso contrario, la risoluzione DNS può uscire se non si dispone di un server DNS presso il sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="20e3f-197">Otherwise, DNS resolution can time out if you do not have a DNS server at the branch site.</span></span>

<span data-ttu-id="20e3f-198">Per gli utenti del sito succursale è consigliabile disporre delle configurazioni seguenti per la sopravvivenza della segreteria telefonica:</span><span class="sxs-lookup"><span data-stu-id="20e3f-198">We recommend the following configurations for voice mail survivability for branch site users:</span></span>

  - <span data-ttu-id="20e3f-199">Un amministratore di Microsoft Exchange deve configurare l'operatore automatico di messaggistica unificata di Exchange (AA) per accettare solo i messaggi.</span><span class="sxs-lookup"><span data-stu-id="20e3f-199">An Microsoft Exchange administrator should configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span> <span data-ttu-id="20e3f-200">Questa configurazione Disabilita tutte le altre funzionalità generiche, ad esempio il trasferimento a un utente o il trasferimento a un operatore, e limita l'AA ad accettare solo i messaggi.</span><span class="sxs-lookup"><span data-stu-id="20e3f-200">This configuration disables all other generic functionality, such as transfer to a user or transfer to an operator, and limits the AA to only accepting messages.</span></span> <span data-ttu-id="20e3f-201">In alternativa, l'amministratore di Exchange può usare un generico AA o un AA personalizzato per instradare la chiamata a un operatore.</span><span class="sxs-lookup"><span data-stu-id="20e3f-201">Alternatively, the Exchange administrator can use a generic AA or an AA customized to route the call to an operator.</span></span>

  - <span data-ttu-id="20e3f-202">L'amministratore di Lync Server deve assumere il numero di telefono AA e utilizzare tale numero come numero di **operatore automatico di messaggistica unificata di Exchange** nelle impostazioni di reinstradazione della segreteria telefonica per Survivable Branch Appliance o Branch Server.</span><span class="sxs-lookup"><span data-stu-id="20e3f-202">The Lync Server administrator should take the AA phone number and use that phone number as the **exchange um auto attendant** number in the voice mail rerouting settings for the Survivable Branch Appliance or branch server.</span></span>

  - <span data-ttu-id="20e3f-203">L'amministratore di Lync Server dovrebbe ottenere il numero di telefono per l'accesso abbonato alla messaggistica unificata di Exchange e usare tale numero come numero di **accesso del Sottoscrittore** nelle impostazioni di reindirizzamento della segreteria telefonica per Survivable Branch Appliance o Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="20e3f-203">The Lync Server administrator should get the Exchange UM subscriber access phone number and use that number as the **subscriber access** number in the voice mail rerouting settings for the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="20e3f-204">L'amministratore di Lync Server deve configurare la messaggistica unificata di Exchange in modo che solo un dial plan sia associato a tutti gli utenti della filiale che hanno bisogno di accedere alla segreteria telefonica durante un'interruzione WAN.</span><span class="sxs-lookup"><span data-stu-id="20e3f-204">The Lync Server administrator should configure Exchange UM so that only one dial plan is associated with all branch users who need access to voice mail during a WAN outage.</span></span>

  - <span data-ttu-id="20e3f-205">Quando il collegamento WAN non è disponibile, le chiamate agli utenti del sito succursale possono essere indirizzate alla segreteria telefonica di Exchange Unified Messaging (UM) dell'utente, ma solo se il criterio vocale applicato alla chiamata specifica un numero di telefono della segreteria telefonica univoco e non include un'estensione numero.</span><span class="sxs-lookup"><span data-stu-id="20e3f-205">When the WAN link is unavailable, calls to branch site users can be routed to the user’s Exchange Unified Messaging (UM) voice mailbox, but only if the voice policy applied to the call specifies a voice mail phone number that is unique and does not include an extension number.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a><span data-ttu-id="20e3f-206">Requisiti hardware e software per la resilienza del sito filiale</span><span class="sxs-lookup"><span data-stu-id="20e3f-206">Hardware and Software Requirements for Branch-Site Resiliency</span></span>

<span data-ttu-id="20e3f-207">I requisiti hardware e software variano a seconda della soluzione di resilienza.</span><span class="sxs-lookup"><span data-stu-id="20e3f-207">The hardware and software requirements vary, depending on your resiliency solution.</span></span>

<div>

## <a name="requirements-for-survivable-branch-appliances"></a><span data-ttu-id="20e3f-208">Requisiti per gli elettrodomestici Survivable Branch</span><span class="sxs-lookup"><span data-stu-id="20e3f-208">Requirements for Survivable Branch Appliances</span></span>

<span data-ttu-id="20e3f-209">Hardware e software obbligatori sono integrati nell'appliance Survivable Branch.</span><span class="sxs-lookup"><span data-stu-id="20e3f-209">Required hardware and software is built into the Survivable Branch Appliance.</span></span> <span data-ttu-id="20e3f-210">Tuttavia, è consigliabile anche che ogni sito della filiale distribuisca un server DHCP per ottenere gli indirizzi IP del client. in caso contrario, quando il lease DHCP scade, i client non avranno connettività IP.</span><span class="sxs-lookup"><span data-stu-id="20e3f-210">However, we also recommend that each branch site deploy a DHCP server to obtain client IP addresses; otherwise, when the DHCP lease expires, clients will not have IP connectivity.</span></span>

<span data-ttu-id="20e3f-211">Se i server DNS aziendali si trovano solo nei siti centrali, gli utenti del sito della succursale non potranno connettersi a questi ultimi durante un'interruzione WAN e quindi l'individuazione di Lync Server che usa il record DNS SRV (SRV) non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="20e3f-211">If the enterprise DNS servers are located only in central sites, branch site users will be unable to connect to them during a WAN outage, and therefore Lync Server discovery that uses DNS SRV (service (SRV) resource record) will fail.</span></span> <span data-ttu-id="20e3f-212">Per assicurare il reinstradamento rapido durante un'interruzione WAN, i record DNS devono essere memorizzati nella cache del sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="20e3f-212">To assure prompt rerouting during a WAN outage, DNS records must be cached at the branch site.</span></span> <span data-ttu-id="20e3f-213">Se il router della filiale lo supporta, attivare la memorizzazione nella cache DNS.</span><span class="sxs-lookup"><span data-stu-id="20e3f-213">If the branch router supports it, turn on DNS caching.</span></span> <span data-ttu-id="20e3f-214">In alternativa, è possibile distribuire un server DNS presso la filiale.</span><span class="sxs-lookup"><span data-stu-id="20e3f-214">Or, you can deploy a DNS server at the branch.</span></span> <span data-ttu-id="20e3f-215">Può trattarsi di un server autonomo o di una versione dell'appliance Survivable Branch che supporta le funzionalità DNS.</span><span class="sxs-lookup"><span data-stu-id="20e3f-215">This can be a stand-alone server or a version of the Survivable Branch Appliance that supports DNS capabilities.</span></span> <span data-ttu-id="20e3f-216">Per informazioni dettagliate, contattare il provider Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="20e3f-216">For details, contact your Survivable Branch Appliance provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="20e3f-217">Non è necessario disporre di un controller di dominio in un sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="20e3f-217">It is not necessary to have a domain controller at a branch site.</span></span> <span data-ttu-id="20e3f-218">Il Survivable Branch Appliance autentica i client usando un certificato speciale che invia il client in risposta alla richiesta di certificato del client quando viene eseguita la firma.</span><span class="sxs-lookup"><span data-stu-id="20e3f-218">The Survivable Branch Appliance authenticates clients by using a special certificate that it sends the client in response to the client’s certificate request when it signs in.</span></span>



</div>

<span data-ttu-id="20e3f-219">I client Lync possono individuare il server Lync usando l'opzione DHCP 120 (opzione registrar SIP).</span><span class="sxs-lookup"><span data-stu-id="20e3f-219">Lync clients can discover the Lync Server by using DHCP Option 120 (SIP Registrar Option).</span></span> <span data-ttu-id="20e3f-220">Questa operazione può essere configurata in uno dei due modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="20e3f-220">This can be configured in one of two ways:</span></span>

  - <span data-ttu-id="20e3f-221">Configurare il server DHCP presso il sito della filiale per rispondere alle query di 120 DHCP, che restituiscono il nome di dominio completo del registrar nel Survivable Branch Appliance o Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="20e3f-221">Configure the DHCP server at the branch site to reply to DHCP 120 queries, which return the FQDN of the Registrar on the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="20e3f-222">Attivare il protocollo DHCP di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="20e3f-222">Turn on Lync Server DHCP.</span></span> <span data-ttu-id="20e3f-223">Quando questo è attivato, il registrar di Lync Server risponde alle query di opzione 120 per DHCP.</span><span class="sxs-lookup"><span data-stu-id="20e3f-223">When this is turned on, the Lync Server Registrar responds to DHCP Option 120 queries.</span></span> <span data-ttu-id="20e3f-224">Tieni presente che il registrar non risponde a nessuna query DHCP diversa dalle opzioni DHCP 120.</span><span class="sxs-lookup"><span data-stu-id="20e3f-224">Note that the Registrar does not respond to any DHCP queries other than DHCP Options 120.</span></span>

<span data-ttu-id="20e3f-225">Inoltre, per i siti di succursale più grandi con più subnet, gli agenti di inoltro DHCP devono essere abilitati per inoltrare query DHCP Option 120 al server DHCP (configurazione 1) o al registrar (configurazione 2).</span><span class="sxs-lookup"><span data-stu-id="20e3f-225">Additionally, for larger branch sites that have multiple subnets, DHCP relay agents should be enabled to forward DHCP Option 120 queries to the DHCP Server (configuration 1) or to the Registrar (configuration 2).</span></span>

<span data-ttu-id="20e3f-226">Infine, gli utenti del sito succursale devono essere configurati per VoIP aziendale e provisioning con un endpoint di comunicazioni unificato appropriato.</span><span class="sxs-lookup"><span data-stu-id="20e3f-226">Finally, branch site users must be configured for Enterprise Voice and provisioned with an appropriate unified communications endpoint.</span></span>

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a><span data-ttu-id="20e3f-227">Requisiti per Survivable Branch Servers</span><span class="sxs-lookup"><span data-stu-id="20e3f-227">Requirements for Survivable Branch Servers</span></span>

<span data-ttu-id="20e3f-228">I requisiti per i Survivable Branch Server corrispondono ai requisiti per un server front-end.</span><span class="sxs-lookup"><span data-stu-id="20e3f-228">The requirements for Survivable Branch Servers are the same as the requirements for a Front End Server.</span></span> <span data-ttu-id="20e3f-229">Per informazioni dettagliate, vedere [piattaforme hardware server per Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="20e3f-229">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a><span data-ttu-id="20e3f-230">Requisiti per distribuzioni a livello di sito di Lync Server su vasta scala</span><span class="sxs-lookup"><span data-stu-id="20e3f-230">Requirements for Full-Scale Lync Server Branch-Site Deployments</span></span>

<span data-ttu-id="20e3f-231">Per informazioni dettagliate, vedere [determinazione dei requisiti di infrastruttura per Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="20e3f-231">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

