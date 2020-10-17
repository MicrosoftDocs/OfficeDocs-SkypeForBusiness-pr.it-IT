---
title: 'Lync Server 2013: requisiti di resilienza dei siti di succursale'
description: 'Lync Server 2013: requisiti di resilienza dei siti di succursale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef05917fb53d1333895236e849cb54596cc41947
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555082"
---
# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a><span data-ttu-id="4d285-103">Requisiti di resilienza dei siti di succursale per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d285-103">Branch-site resiliency requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d285-104">_**Ultimo argomento modificato:** 2014-02-25_</span><span class="sxs-lookup"><span data-stu-id="4d285-104">_**Topic Last Modified:** 2014-02-25_</span></span>

<span data-ttu-id="4d285-105">In questo argomento vengono fornite informazioni utili per preparare gli utenti per la resilienza dei siti di succursale e per il funzionamento continuato (survivability) della segreteria telefonica e vengono specificati i requisiti hardware e software pertinenti.</span><span class="sxs-lookup"><span data-stu-id="4d285-105">This topic will help you to prepare users for branch-site resiliency and voice mail survivability, and also specifies the relevant hardware and software requirements.</span></span>

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a><span data-ttu-id="4d285-106">Preparazione degli utenti di succursale per la resilienza del sito di succursale</span><span class="sxs-lookup"><span data-stu-id="4d285-106">Preparing Branch Users for Branch-Site Resiliency</span></span>

<span data-ttu-id="4d285-107">Preparare gli utenti per la resilienza dei siti di succursale impostando il pool di registrazione come Survivable Branch Appliance (SBA) o Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="4d285-107">Prepare users for branch-site resiliency by setting their Registrar pool as the Survivable Branch Appliance (SBA) or Survivable Branch Server.</span></span>

<div>

## <a name="registrar-assignments-for-branch-users"></a><span data-ttu-id="4d285-108">Assegnazioni di registrazione per utenti di succursale</span><span class="sxs-lookup"><span data-stu-id="4d285-108">Registrar Assignments for Branch Users</span></span>

<span data-ttu-id="4d285-109">Indipendentemente dalla soluzione di resilienza del sito di succursale scelta, è necessario assegnare un Registrar primario a ciascun utente.</span><span class="sxs-lookup"><span data-stu-id="4d285-109">Regardless of which branch-site resiliency solution you choose, you will need to assign a primary Registrar to each user.</span></span> <span data-ttu-id="4d285-110">Gli utenti del sito di succursale devono sempre registrarsi con il registrar nel sito di succursale, indipendentemente dal fatto che il registrar risieda nel Survivable Branch Appliance, nel Survivable Branch Server o nel server autonomo Lync Server 2013 standard o Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="4d285-110">Branch site users should always register with the Registrar at the branch site, regardless of whether that Registrar resides in the Survivable Branch Appliance, Survivable Branch Server, or stand-alone Lync Server 2013 Standard or Enterprise Edition server.</span></span> <span data-ttu-id="4d285-111">È necessario un record di risorse del servizio DNS (Domain Name System) (SRV) in modo che un client possa individuare il pool di registrazione.</span><span class="sxs-lookup"><span data-stu-id="4d285-111">A domain name system (DNS) service (SRV) resource record is required so that a client can discover its Registrar pool.</span></span> <span data-ttu-id="4d285-112">Se il Survivable Branch Appliance non è disponibile, questo è il modo in cui i client dei siti di succursale scopriranno automaticamente la registrazione di backup.</span><span class="sxs-lookup"><span data-stu-id="4d285-112">If the Survivable Branch Appliance becomes unavailable, this is how branch site clients will automatically discover the backup Registrar.</span></span>

<span data-ttu-id="4d285-113">Se un sito di succursale non dispone di un server DNS, esistono due modi alternativi per configurare l'individuazione del Survivable Branch Appliance o Survivable Branch Server:</span><span class="sxs-lookup"><span data-stu-id="4d285-113">If a branch site does not have a DNS server, there are two alternative ways to configure discovery of the Survivable Branch Appliance or Survivable Branch Server:</span></span>

  - <span data-ttu-id="4d285-114">Configurare l'opzione DHCP 120 nel server DHCP (Dynamic Host Configuration Protocol) del sito di succursale in modo che punti al nome di dominio completo (FQDN) del Survivable Branch Appliance o Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="4d285-114">Configure DHCP option 120 on the branch site’s Dynamic Host Configuration Protocol (DHCP) server to point to the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="4d285-115">Configurare il Survivable Branch Appliance o il Survivable Branch Server per rispondere alle query DHCP 120.</span><span class="sxs-lookup"><span data-stu-id="4d285-115">Configure the Survivable Branch Appliance or Survivable Branch Server to respond to DHCP 120 queries.</span></span>

</div>

<div>

## <a name="voice-routing-for-branch-users"></a><span data-ttu-id="4d285-116">Routing vocale per gli utenti di succursale</span><span class="sxs-lookup"><span data-stu-id="4d285-116">Voice Routing for Branch Users</span></span>

<span data-ttu-id="4d285-117">Per gli utenti di un sito di succursale è consigliabile creare criteri VoIP (Voice over Internet Protocol) a livello di utente separati.</span><span class="sxs-lookup"><span data-stu-id="4d285-117">We recommend that you create a separate user-level Voice over Internet Protocol (VoIP) policy for users in a branch site.</span></span> <span data-ttu-id="4d285-118">Questo criterio deve includere una route principale che utilizza il Survivable Branch Appliance o il gateway del server di succursale e una o più route di backup che utilizzano un trunk con un gateway PSTN (Public Switched Telephone Network) nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="4d285-118">This policy should include a primary route that uses the Survivable Branch Appliance or branch server gateway, and one or more backup routes that use a trunk with a public switched telephone network (PSTN) gateway at the central site.</span></span> <span data-ttu-id="4d285-119">Se la route principale non è disponibile, viene sostituita dalla route di backup, che può utilizzare uno o più gateway del sito centrale.</span><span class="sxs-lookup"><span data-stu-id="4d285-119">If the primary route is unavailable, the backup route that uses one or more central site gateways is used instead.</span></span> <span data-ttu-id="4d285-120">In questo modo, non è rilevante se l'utente è registrato presso la funzione di registrazione del sito di succursale o presso il pool di registrazione di backup nel sito centrale: i criteri VoIP dell'utente saranno sempre attivi.</span><span class="sxs-lookup"><span data-stu-id="4d285-120">This way, regardless of where a user is registered—on the branch site Registrar or the backup Registrar pool at the central site—the user’s VoIP policy is always in effect.</span></span> <span data-ttu-id="4d285-121">Questa considerazione è particolarmente importante per gli scenari di failover.</span><span class="sxs-lookup"><span data-stu-id="4d285-121">This is an important consideration for failover scenarios.</span></span> <span data-ttu-id="4d285-122">Ad esempio, se è necessario rinominare il Survivable Branch Appliance o riconfigurare il Survivable Branch Appliance per connettersi a un pool di registrazione di backup nel sito centrale, è necessario spostare gli utenti dei siti di succursale nel sito centrale per tutta la durata.</span><span class="sxs-lookup"><span data-stu-id="4d285-122">For example, if you need to rename the Survivable Branch Appliance or reconfigure the Survivable Branch Appliance to connect to a backup Registrar pool at the central site, then you must move branch site users to the central site for the duration.</span></span> <span data-ttu-id="4d285-123">Per informazioni dettagliate sulla ridenominazione o la riconfigurazione di un Survivable Branch Appliance, vedere l' [Appendice B: Managing a Survivable Branch Appliance in Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) nella documentazione relativa alla distribuzione. Se gli utenti non dispongono di criteri VoIP a livello di utente o di dial plan a livello di utente, quando gli utenti vengono spostati in un altro sito, i criteri VoIP a livello di sito e i dial plan a livello di sito del sito centrale si applicano agli utenti per impostazione predefinita, anziché i criteri VoIP a livello di sito di succursale e i dial plan.</span><span class="sxs-lookup"><span data-stu-id="4d285-123">(For details about renaming or reconfiguring a Survivable Branch Appliance, see [Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) in the Deployment documentation.) If those users do not have user-level VoIP policies or user-level dial plans, when the users are moved to another site, the site-level VoIP policies and site-level dial plans of the central site apply to the users by default, instead of the branch site site-level VoIP policies and dial plans,.</span></span> <span data-ttu-id="4d285-124">In questo scenario le chiamate degli utenti del sito di succursale avranno esito positivo se a tali utenti non è possibile applicare i criteri VoIP e i dial plan a livello di sito utilizzati dal pool di registrazione di backup.</span><span class="sxs-lookup"><span data-stu-id="4d285-124">In this scenario, unless the site-level VoIP policies and site-level dial plans used by the backup Registrar pool can also apply to the branch site users, their calls will fail.</span></span> <span data-ttu-id="4d285-125">Se ad esempio gli utenti di un sito di succursale situato in Giappone vengono spostati in un sito centrale situato a Redmond, è improbabile che un dial plan con regole di normalizzazione che antepongono il prefisso +1425 a tutte le chiamate a numeri di sette cifre sia in grado di convertire correttamente le chiamate di tali utenti.</span><span class="sxs-lookup"><span data-stu-id="4d285-125">For example, if users from a branch site located in Japan are moved to a central site in Redmond, then a dial plan with normalization rules that prepend +1425 to all 7-digit calls is unlikely to appropriately translate calls for those users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4d285-126">Quando si crea una route di backup per una succursale, è consigliabile aggiungere ai criteri utente della succursale due record di utilizzo telefono PSTN e assegnare route distinte a ognuno.</span><span class="sxs-lookup"><span data-stu-id="4d285-126">When you create a branch office backup route, we recommend that you add two PSTN phone usage records to the branch office user policy and assign separate routes to each one.</span></span> <span data-ttu-id="4d285-127">La prima route o Primary indirizza le chiamate al gateway associato a Survivable Branch Appliance (SBA) o a Branch Server; la seconda route o backup consentirebbe di indirizzare le chiamate al gateway nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="4d285-127">The first, or primary, route would direct calls to the gateway associated with the Survivable Branch Appliance (SBA) or branch server; the second, or backup, route would direct calls to the gateway at the central site.</span></span> <span data-ttu-id="4d285-128">Per l'indirizzamento delle chiamate, l'SBA o il server di succursale dovrà tentare tutte le route assegnate al primo record di utilizzo PSTN prima di tentare quelle del secondo record di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="4d285-128">In directing calls, the SBA or branch server will attempt all routes assigned to the first PSTN usage record before attempting the second usage record.</span></span>



</div>

<span data-ttu-id="4d285-129">Per garantire che le chiamate in ingresso agli utenti dei siti di succursale raggiungano tali utenti quando il gateway di succursale o il componente Windows del sito Survivable Branch Appliance non è disponibile (cosa che accadrebbe, ad esempio, se il Survivable Branch Appliance o il gateway di succursale è stato premuto per la manutenzione), creare una route di failover sul gateway (o collaborare con il provider di composizione Direct inverso) per reindirizzare le chiamate in arrivo al pool di registrazione di backup nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="4d285-129">To help ensure that inbound calls to branch site users will reach those users when the branch gateway or the Windows component of the Survivable Branch Appliance site is unavailable (which would happen, for example, if the Survivable Branch Appliance or branch gateway were down for maintenance), create a failover route on the gateway (or work with your Direct Inward Dialing (DID) provider) to redirect incoming calls to the backup Registrar pool at the central site.</span></span> <span data-ttu-id="4d285-130">Dal pool di registrazione di backup del sito centrale le chiamate verranno instradate agli utenti di succursale attraverso il collegamento WAN.</span><span class="sxs-lookup"><span data-stu-id="4d285-130">From there, the calls will be routed over the WAN link to branch users.</span></span> <span data-ttu-id="4d285-131">Verificare che la route sia in grado di convertire i numeri nei formati di numero di telefono consentiti per il gateway PSTN o un altro trunk peer.</span><span class="sxs-lookup"><span data-stu-id="4d285-131">Be sure that the route translates numbers to comply with the PSTN gateway or other trunk peer’s accepted phone number formats.</span></span> <span data-ttu-id="4d285-132">Per informazioni dettagliate sulla creazione di una route di failover, vedere [configurazione di una route di failover in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span><span class="sxs-lookup"><span data-stu-id="4d285-132">For details about creating a failover route, see [Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span></span> <span data-ttu-id="4d285-133">Per consentire la normalizzazione delle chiamate in arrivo da parte del trunk associato al gateway del sito di succursale, è inoltre necessario creare dial plan a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="4d285-133">Also create service-level dial plans for the trunk associated with the gateway at the branch site to normalize incoming calls.</span></span> <span data-ttu-id="4d285-134">Se in un sito di succursale sono disponibili due Survivable Branch Appliance, è possibile creare un dial plan a livello di sito per entrambi, a meno che non sia necessario un piano di servizio separato per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="4d285-134">If you have two Survivable Branch Appliances at a branch site, you can create a site-level dial plan for both unless a separate service-level plan for each is necessary.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4d285-135">Per tenere conto del consumo delle risorse del sito centrale da parte degli utenti dei siti di succursale che si appoggiano al sito centrale per le funzionalità di presenza, conferenza o failover, è consigliabile considerare ogni utente del sito di succursale come se fosse registrato presso il sito centrale.</span><span class="sxs-lookup"><span data-stu-id="4d285-135">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as if the user were registered with the central site.</span></span> <span data-ttu-id="4d285-136">Al momento non sono presenti limiti al numero di utenti di siti di succursale, compresi gli utenti registrati con un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="4d285-136">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>



</div>

<span data-ttu-id="4d285-137">È inoltre consigliabile creare criteri vocali e di dial plan a livello di utente e quindi assegnarli agli utenti del sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="4d285-137">We also recommend that you create a user-level dial plan and voice policy, and then assign it to branch site users.</span></span> <span data-ttu-id="4d285-138">Per ulteriori informazioni, vedere [creare un dial plan in Lync server 2013](lync-server-2013-create-a-dial-plan.md) e [creare i criteri di routing VoIP per gli utenti di succursale in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4d285-138">For details, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) and [Create the VoIP routing policy for branch users in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) in the Deployment documentation.</span></span>

<div>

## <a name="routing-extension-numbers"></a><span data-ttu-id="4d285-139">Routing di numeri di interno</span><span class="sxs-lookup"><span data-stu-id="4d285-139">Routing Extension Numbers</span></span>

<span data-ttu-id="4d285-140">Quando si preparano i dial plan e i criteri vocali per gli utenti dei siti di succursale assicurarsi di includere regole di normalizzazione e regole di conversione che corrispondono alle stringhe e al formato numerico utilizzati nell'attributo msRTCSIP-line (o URI di linea), in modo che le chiamate di Lync 2013 abilitate tra gli utenti dei siti di succursale e gli utenti del sito centrale vengano instradate correttamente, in particolare quando le chiamate devono essere reinstradate sulla rete PSTN perché il collegamento WAN non</span><span class="sxs-lookup"><span data-stu-id="4d285-140">When preparing dial plans and voice policies for branch site users, be sure to include normalization rules and translation rules that match the strings and number format used in the msRTCSIP-line (or Line URI) attribute, so that Lync 2013 calls enabled between branch site users and central site users will be routed correctly—particularly when calls must be rerouted over the PSTN because the WAN link is unavailable.</span></span> <span data-ttu-id="4d285-141">Per i numeri composti contenenti numeri di interno, sono inoltre necessarie considerazioni specifiche rispetto ai numeri di telefono semplici.</span><span class="sxs-lookup"><span data-stu-id="4d285-141">Additionally, there are special considerations for dialed numbers that include extension numbers, rather just phone numbers.</span></span>

<span data-ttu-id="4d285-p108">Per le regole di normalizzazione e le regole di conversione corrispondenti a URI di linea contenenti un numero di interno, da solo o insieme a un numero di telefono E. 164 completo, esistono requisiti aggiuntivi. In questa sezione sono descritti alcuni scenari di esempio con l'indirizzamento di chiamate per URI di linea contenenti un numero di interno.</span><span class="sxs-lookup"><span data-stu-id="4d285-p108">Normalization rules and translations rules that match Line URIs that contain an extension number, whether exclusively or in addition to a full E.164 phone number, have additional requirements. This section describes several example scenarios to route calls for Line URIs with an extension number.</span></span>

<span data-ttu-id="4d285-p109">Se nell'organizzazione non sono configurati numeri di telefono DID (Direct Inward Dial) per utenti singoli e l'URI di linea di ogni utente è configurato con un *solo* numero di interno, gli utenti interni possono chiamarsi componendo solo il numero di interno desiderato. È tuttavia necessario configurare regole di normalizzazione applicabili alle chiamate da un utente di un sito di succursale a un utente del sito centrale corrispondenti ai numeri di interno.</span><span class="sxs-lookup"><span data-stu-id="4d285-p109">If your organization does not have Direct Inward Dial (DID) phone numbers configured for individual users and the Line URI of each user is configured with *only* an extension number, internal users can call one another by dialing only an extension number. However, you must configure normalization rules that can apply to calls from a branch site user to a central site user, that match the extension numbers.</span></span>

<span data-ttu-id="4d285-p110">In uno scenario in cui sia disponibile un collegamento WAN tra il sito di succursale e il sito centrale, per le chiamate tra utenti del sito di succursale e utenti del sito centrale non è necessaria la regola di normalizzazione per la conversione del numero, poiché la chiamata non viene indirizzata attraverso PSTN. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4d285-p110">In a scenario where the WAN link between a branch site and a central site is available, calls from branch site users to central site users do not require the matching normalization rule to translate the number because the call is not routed over the PSTN. For example:</span></span>


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
<th><span data-ttu-id="4d285-148">Nome regola</span><span class="sxs-lookup"><span data-stu-id="4d285-148">Rule name</span></span></th>
<th><span data-ttu-id="4d285-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d285-149">Description</span></span></th>
<th><span data-ttu-id="4d285-150">Formato numero</span><span class="sxs-lookup"><span data-stu-id="4d285-150">Number pattern</span></span></th>
<th><span data-ttu-id="4d285-151">Translation</span><span class="sxs-lookup"><span data-stu-id="4d285-151">Translation</span></span></th>
<th><span data-ttu-id="4d285-152">Esempio</span><span class="sxs-lookup"><span data-stu-id="4d285-152">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d285-153">5digitExtensions</span><span class="sxs-lookup"><span data-stu-id="4d285-153">5digitExtensions</span></span></p></td>
<td><p><span data-ttu-id="4d285-154">Non converte i numeri a cinque cifre</span><span class="sxs-lookup"><span data-stu-id="4d285-154">Does not translate 5-digit numbers</span></span></p></td>
<td><p><span data-ttu-id="4d285-155">^ (\d {5} ) $</span><span class="sxs-lookup"><span data-stu-id="4d285-155">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="4d285-156">$1</span><span class="sxs-lookup"><span data-stu-id="4d285-156">$1</span></span></p></td>
<td><p><span data-ttu-id="4d285-157">10001 non viene convertito</span><span class="sxs-lookup"><span data-stu-id="4d285-157">10001 is not translated</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4d285-p111">È inoltre necessario prevedere numeri di interno per scenari specifici in cui, ad esempio, il collegamento WAN tra un sito di succursale e il sito centrale non sia disponibile e sia necessario instradare tramite PSTN le chiamate provenienti dal sito di succursale. Se durante un'interruzione del funzionamento del collegamento WAN un utente di un sito di succursale chiama un utente del sito centrale componendo solo l'interno di quest'ultimo, è necessaria una regola di conversione in uscita che aggiunga il numero di telefono completo dell'utente del sito centrale. Se l'URI di linea di un utente contiene il numero di telefono completo dell'organizzazione e il numero di interno univoco dell'utente anziché il numero di telefono completo univoco dell'utente, è necessaria un regola di conversione in uscita che aggiunga il numero di telefono completo dell'organizzazione. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4d285-p111">You must also accommodate extension numbers for specific scenarios, such as when the WAN link between a branch site and central site is unavailable and a call from a branch site must be routed over the PSTN. During a WAN outage, if a branch site user calls a central site user only by dialing the central site user’s extension, you must have an outbound translation rule that adds the central site user’s full phone number. If a user’s Line URI contains your organization’s full phone number and the user’s unique extension number instead of a full phone number that is unique to the user, then you must have an outbound translation rule that adds your organization’s full phone number instead. For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d285-162">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d285-162">Description</span></span></th>
<th><span data-ttu-id="4d285-163">Formato corrispondente</span><span class="sxs-lookup"><span data-stu-id="4d285-163">Matching pattern</span></span></th>
<th><span data-ttu-id="4d285-164">Translation</span><span class="sxs-lookup"><span data-stu-id="4d285-164">Translation</span></span></th>
<th><span data-ttu-id="4d285-165">Esempio</span><span class="sxs-lookup"><span data-stu-id="4d285-165">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d285-166">Converte i numeri a cinque cifre in numero di telefono e interno dell'utente corrispondente</span><span class="sxs-lookup"><span data-stu-id="4d285-166">Translates 5-digit numbers to a user’s phone number and extension</span></span></p></td>
<td><p><span data-ttu-id="4d285-167">^ (\d {5} ) $</span><span class="sxs-lookup"><span data-stu-id="4d285-167">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="4d285-168">+ 14255550123; ext = $1</span><span class="sxs-lookup"><span data-stu-id="4d285-168">+14255550123;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="4d285-169">10001 viene convertito in +14255550123;ext=10001</span><span class="sxs-lookup"><span data-stu-id="4d285-169">10001 is translated to +14255550123;ext=10001</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d285-170">Converte i numeri a cinque cifre in numero di telefono dell'organizzazione e interno dell'utente corrispondente</span><span class="sxs-lookup"><span data-stu-id="4d285-170">Translates 5-digit numbers to your organization’s phone number and a user’s extension</span></span></p></td>
<td><p><span data-ttu-id="4d285-171">^ (\d {5} ) $</span><span class="sxs-lookup"><span data-stu-id="4d285-171">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="4d285-172">+ 14255550100; ext = $1</span><span class="sxs-lookup"><span data-stu-id="4d285-172">+14255550100;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="4d285-173">10001 viene convertito in +14255550100;ext=10001</span><span class="sxs-lookup"><span data-stu-id="4d285-173">10001 is translated to +14255550100;ext=10001</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4d285-p112">In questo scenario, se i numeri di interno non sono supportati dal trunk peer che gestisce il reindirizzamento a PSTN, la regola di conversione in uscita deve inoltre prevedere la rimozione del numero di interno. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4d285-p112">In this scenario, if the trunk peer that handles rerouting to the PSTN does not support extension numbers, then the outbound translation rule must also remove the extension number. For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d285-176">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d285-176">Description</span></span></th>
<th><span data-ttu-id="4d285-177">Formato corrispondente</span><span class="sxs-lookup"><span data-stu-id="4d285-177">Matching pattern</span></span></th>
<th><span data-ttu-id="4d285-178">Translation</span><span class="sxs-lookup"><span data-stu-id="4d285-178">Translation</span></span></th>
<th><span data-ttu-id="4d285-179">Esempio</span><span class="sxs-lookup"><span data-stu-id="4d285-179">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d285-180">Rimuove l'interno dai numeri di telefono con interno</span><span class="sxs-lookup"><span data-stu-id="4d285-180">Removes extension from phone numbers with extensions</span></span></p></td>
<td><p><span data-ttu-id="4d285-181">^\+(\d *); EXT = (\d*) $</span><span class="sxs-lookup"><span data-stu-id="4d285-181">^\+(\d *);ext=(\d*)$</span></span></p></td>
<td><p><span data-ttu-id="4d285-182">+ $1</span><span class="sxs-lookup"><span data-stu-id="4d285-182">+$1</span></span></p></td>
<td><p><span data-ttu-id="4d285-183">+14255550123;ext=10001 viene convertito in +14255550123</span><span class="sxs-lookup"><span data-stu-id="4d285-183">+14255550123;ext=10001 is translated to +14255550123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4d285-p113">Indipendentemente dalla disponibilità di un collegamento WAN, se per l'organizzazione non sono configurati numeri DID per i singoli utenti e l'URI di linea di ogni utente contiene il numero di telefono dell'organizzazione e il numero di interno univoco dell'utente, è necessario configurare l'URI di linea del numero di telefono dell'organizzazione con un numero raggiungibile da parte del trunk peer o del gateway PSTN presso il sito di succursale. È inoltre necessario configurare l'URI di linea del numero di telefono dell'organizzazione in modo che includa l'interno univoco per le chiamate da indirizzare a tale numero.</span><span class="sxs-lookup"><span data-stu-id="4d285-p113">Whether or not a WAN link is available, if your organization does not have DID numbers configured for individual users and the Line URI for a user contains your organization’s phone number and the user’s unique extension number, then you must configure your organization’s phone number Line URI with a number that is reachable by the trunk peer or PSTN gateway at the branch site. You must also configure your organization’s phone number Line URI to include its own unique extension for calls to be routed to that number.</span></span>

<span data-ttu-id="4d285-186">Per informazioni dettagliate sulle chiamate da un utente del sito centrale a un utente di un sito di succursale in caso di indisponibilità del collegamento WAN tra i siti, vedere "Preparazione per il funzionamento continuato (survivability) della segreteria telefonica" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4d285-186">For details about calls from a central site user to a branch site user when the WAN link between the sites is unavailable, see "Preparing for Voice Mail Survivability" later in this topic.</span></span> <span data-ttu-id="4d285-187">Per informazioni dettagliate sui dial plan e le regole di normalizzazione, incluse le altre regole di esempio, vedere [dial plans and normalizzation Rules in Lync server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) nella documentazione relativa alla pianificazione e [configurazione dei dial plan in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4d285-187">For details about dial plans and normalization rules, including other sample rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation and [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) in the Deployment documentation.</span></span> <span data-ttu-id="4d285-188">Per informazioni dettagliate sulle regole di conversione in uscita, vedere [Translation Rules in Lync server 2013](lync-server-2013-translation-rules.md) nella documentazione relativa alla pianificazione e [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4d285-188">For details about outbound translation rules, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md) in the Planning documentation and [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a><span data-ttu-id="4d285-189">Preparazione per il funzionamento continuato (survivability) della segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="4d285-189">Preparing for Voice Mail Survivability</span></span>

<span data-ttu-id="4d285-190">La messaggistica unificata di Exchange è in genere installata solo in un sito centrale e non nei siti di succursale.</span><span class="sxs-lookup"><span data-stu-id="4d285-190">Exchange Unified Messaging (UM) is usually installed only at a central site and not at branch sites.</span></span> <span data-ttu-id="4d285-191">Il chiamante deve poter lasciare un messaggio nella segreteria telefonica anche quando il collegamento WAN tra il sito di succursale e il sito centrale non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="4d285-191">A caller should be able to leave a voice mail message, even if the WAN link between branch site and central site is unavailable.</span></span> <span data-ttu-id="4d285-192">Di conseguenza, la configurazione dell'URI di linea per il numero di telefono dell'operatore automatico di messaggistica unificata di Exchange che fornisce la segreteria telefonica per gli utenti dei siti di succursale richiede considerazioni speciali, oltre al criterio vocale, al dial plan e alle regole di normalizzazione applicabili a quel numero di segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="4d285-192">As a result, configuring the Line URI for the Exchange UM Auto Attendant phone number that provides voice mail for branch site users requires special considerations, in addition to the voice policy, dial plan, and normalization rules applicable to that voice mail number.</span></span>

<span data-ttu-id="4d285-193">Survivable Branch Appliances (SBA) e Survivable Branch Server offrono la sopravvivenza dei messaggi vocali per gli utenti di succursali durante un'interruzione della rete WAN.</span><span class="sxs-lookup"><span data-stu-id="4d285-193">Survivable Branch Appliances (SBAs) and Survivable Branch Servers provide voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="4d285-194">In particolare, se si utilizza un Survivable Branch Appliance o Survivable Branch Server e la rete WAN non è disponibile, l'ASB o il Survivable Branch Server reindirizza le chiamate senza risposta sulla rete PSTN alla messaggistica unificata di Exchange nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="4d285-194">Specifically, if you are using a Survivable Branch Appliance or Survivable Branch Server and the WAN becomes unavailable, the SBA or Survivable Branch Server reroutes unanswered calls over the PSTN to Exchange UM at the central site.</span></span> <span data-ttu-id="4d285-195">Con una SBA o un Survivable Branch Server, gli utenti possono anche recuperare i messaggi vocali tramite la rete PSTN durante un'interruzione della rete WAN.</span><span class="sxs-lookup"><span data-stu-id="4d285-195">With a SBA or Survivable Branch Server, users can also retrieve voice mail messages through the PSTN during a WAN outage.</span></span> <span data-ttu-id="4d285-196">Infine, durante un'interruzione della rete WAN, Survivable Branch Appliance o Survivable Branch Server accoda le notifiche di chiamata senza risposta e quindi le carica nel server Messaggistica unificata di Exchange quando viene ripristinata la rete WAN.</span><span class="sxs-lookup"><span data-stu-id="4d285-196">Finally, during a WAN outage the Survivable Branch Appliance or Survivable Branch Server queues missed-call notifications and then uploads them to the Exchange UM server when the WAN is restored.</span></span> <span data-ttu-id="4d285-197">Per garantire che il reindirizzamento della segreteria telefonica sia resiliente, è necessario aggiungere una voce per il nome di dominio completo del pool di siti centrali e una voce per il nome di dominio completo del server perimetrale nel file hosts nel Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="4d285-197">To help ensure that voice mail rerouting is resilient, be sure that you add an entry for the central site pool’s FQDN and an entry for the Edge Server FQDN to the hosts file on the Survivable Branch Server.</span></span> <span data-ttu-id="4d285-198">In caso contrario, se il sito di succursale non dispone di un server DNS, può verificarsi il timeout della risoluzione DNS.</span><span class="sxs-lookup"><span data-stu-id="4d285-198">Otherwise, DNS resolution can time out if you do not have a DNS server at the branch site.</span></span>

<span data-ttu-id="4d285-199">Per configurare il funzionamento continuato (survivability) della segreteria telefonica per gli utenti dei siti di succursale, sono consigliate le configurazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d285-199">We recommend the following configurations for voice mail survivability for branch site users:</span></span>

  - <span data-ttu-id="4d285-200">Un amministratore di Microsoft Exchange deve configurare l'operatore automatico di messaggistica unificata di Exchange (AA) per accettare solo i messaggi.</span><span class="sxs-lookup"><span data-stu-id="4d285-200">An Microsoft Exchange administrator should configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span> <span data-ttu-id="4d285-201">Con questa configurazione viene disabilitata ogni altra funzionalità generica, ad esempio il trasferimento a un utente o al centralino.</span><span class="sxs-lookup"><span data-stu-id="4d285-201">This configuration disables all other generic functionality, such as transfer to a user or transfer to an operator, and limits the AA to only accepting messages.</span></span> <span data-ttu-id="4d285-202">In alternativa, l'amministratore di Exchange può indirizzare le chiamate al centralino utilizzando Operatore automatico, generico o personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4d285-202">Alternatively, the Exchange administrator can use a generic AA or an AA customized to route the call to an operator.</span></span>

  - <span data-ttu-id="4d285-203">L'amministratore di Lync Server deve assumere il numero di telefono AA e utilizzarlo come numero dell' **operatore automatico di messaggistica unificata di Exchange** nelle impostazioni di reinstradamento della segreteria telefonica per il Survivable Branch Appliance o il Branch Server.</span><span class="sxs-lookup"><span data-stu-id="4d285-203">The Lync Server administrator should take the AA phone number and use that phone number as the **exchange um auto attendant** number in the voice mail rerouting settings for the Survivable Branch Appliance or branch server.</span></span>

  - <span data-ttu-id="4d285-204">L'amministratore di Lync Server dovrebbe ottenere il numero di telefono di accesso sottoscrittore Messaggistica unificata di Exchange e utilizzare tale numero come numero di **accesso del Sottoscrittore** nelle impostazioni di reinstradamento della segreteria telefonica per Survivable Branch Appliance o Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="4d285-204">The Lync Server administrator should get the Exchange UM subscriber access phone number and use that number as the **subscriber access** number in the voice mail rerouting settings for the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="4d285-205">L'amministratore di Lync Server deve configurare la messaggistica unificata di Exchange in modo che un solo dial plan sia associato a tutti gli utenti di succursale che devono accedere alla segreteria telefonica durante un'interruzione della rete WAN.</span><span class="sxs-lookup"><span data-stu-id="4d285-205">The Lync Server administrator should configure Exchange UM so that only one dial plan is associated with all branch users who need access to voice mail during a WAN outage.</span></span>

  - <span data-ttu-id="4d285-206">In caso di indisponibilità del collegamento WAN, le chiamate agli utenti dei siti di succursale possono essere instradate alla casella vocale di messaggistica unificata di Exchange degli utenti, ma solo se i criteri vocali applicati alle chiamate specificano un numero di telefono della segreteria telefonica univoco e senza numero di interno.</span><span class="sxs-lookup"><span data-stu-id="4d285-206">When the WAN link is unavailable, calls to branch site users can be routed to the user’s Exchange Unified Messaging (UM) voice mailbox, but only if the voice policy applied to the call specifies a voice mail phone number that is unique and does not include an extension number.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a><span data-ttu-id="4d285-207">Requisiti hardware e software per la resilienza dei siti di succursale</span><span class="sxs-lookup"><span data-stu-id="4d285-207">Hardware and Software Requirements for Branch-Site Resiliency</span></span>

<span data-ttu-id="4d285-208">I requisiti hardware e software variano a seconda della soluzione di resilienza in uso.</span><span class="sxs-lookup"><span data-stu-id="4d285-208">The hardware and software requirements vary, depending on your resiliency solution.</span></span>

<div>

## <a name="requirements-for-survivable-branch-appliances"></a><span data-ttu-id="4d285-209">Requisiti per Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="4d285-209">Requirements for Survivable Branch Appliances</span></span>

<span data-ttu-id="4d285-210">L'hardware e il software necessari sono incorporati nel Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="4d285-210">Required hardware and software is built into the Survivable Branch Appliance.</span></span> <span data-ttu-id="4d285-211">Tuttavia, è consigliabile anche che ogni sito di succursale distribuisca un server DHCP per ottenere gli indirizzi IP del client; in caso contrario, quando il lease DHCP scade, i client non avranno connettività IP.</span><span class="sxs-lookup"><span data-stu-id="4d285-211">However, we also recommend that each branch site deploy a DHCP server to obtain client IP addresses; otherwise, when the DHCP lease expires, clients will not have IP connectivity.</span></span>

<span data-ttu-id="4d285-212">Se i server DNS dell'organizzazione si trovano solo in siti centrali, gli utenti dei siti di succursale non saranno in grado di connettersi a essi durante un'interruzione della rete WAN e pertanto l'individuazione di Lync Server che utilizza il record di risorse DNS SRV (SRV) avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="4d285-212">If the enterprise DNS servers are located only in central sites, branch site users will be unable to connect to them during a WAN outage, and therefore Lync Server discovery that uses DNS SRV (service (SRV) resource record) will fail.</span></span> <span data-ttu-id="4d285-213">Per garantire il reindirizzamento rapido durante un'interruzione della rete WAN, i record DNS devono essere memorizzati nella cache nel sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="4d285-213">To assure prompt rerouting during a WAN outage, DNS records must be cached at the branch site.</span></span> <span data-ttu-id="4d285-214">Se il router di succursale lo supporta, abilitare la memorizzazione nella cache DNS.</span><span class="sxs-lookup"><span data-stu-id="4d285-214">If the branch router supports it, turn on DNS caching.</span></span> <span data-ttu-id="4d285-215">In alternativa, è possibile distribuire un server DNS nel branch.</span><span class="sxs-lookup"><span data-stu-id="4d285-215">Or, you can deploy a DNS server at the branch.</span></span> <span data-ttu-id="4d285-216">Può trattarsi di un server autonomo o di una versione del Survivable Branch Appliance che supporta le funzionalità DNS.</span><span class="sxs-lookup"><span data-stu-id="4d285-216">This can be a stand-alone server or a version of the Survivable Branch Appliance that supports DNS capabilities.</span></span> <span data-ttu-id="4d285-217">Per informazioni dettagliate, contattare il proprio provider di Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="4d285-217">For details, contact your Survivable Branch Appliance provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4d285-218">Presso un sito di succursale non è necessario un controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="4d285-218">It is not necessary to have a domain controller at a branch site.</span></span> <span data-ttu-id="4d285-219">Survivable Branch Appliance consente di autenticare i client utilizzando un certificato speciale che invia il client in risposta alla richiesta di certificato del client quando viene eseguita la firma.</span><span class="sxs-lookup"><span data-stu-id="4d285-219">The Survivable Branch Appliance authenticates clients by using a special certificate that it sends the client in response to the client’s certificate request when it signs in.</span></span>



</div>

<span data-ttu-id="4d285-220">I client Lync possono individuare Lync Server tramite l'opzione DHCP 120 (opzione di registrazione SIP).</span><span class="sxs-lookup"><span data-stu-id="4d285-220">Lync clients can discover the Lync Server by using DHCP Option 120 (SIP Registrar Option).</span></span> <span data-ttu-id="4d285-221">È possibile configurare tale opzione in uno dei due modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d285-221">This can be configured in one of two ways:</span></span>

  - <span data-ttu-id="4d285-222">Configurare il server DHCP nel sito di succursale per rispondere alle query DHCP 120, che restituiscono il nome di dominio completo del servizio di registrazione nel Survivable Branch Appliance o Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="4d285-222">Configure the DHCP server at the branch site to reply to DHCP 120 queries, which return the FQDN of the Registrar on the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="4d285-223">Abilitare il protocollo DHCP di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4d285-223">Turn on Lync Server DHCP.</span></span> <span data-ttu-id="4d285-224">Quando questa opzione è attivata, il servizio di registrazione di Lync Server risponde a query DHCP Option 120.</span><span class="sxs-lookup"><span data-stu-id="4d285-224">When this is turned on, the Lync Server Registrar responds to DHCP Option 120 queries.</span></span> <span data-ttu-id="4d285-225">Si noti che la funzione di registrazione risponde solo alle query DHCP con l'opzione 120.</span><span class="sxs-lookup"><span data-stu-id="4d285-225">Note that the Registrar does not respond to any DHCP queries other than DHCP Options 120.</span></span>

<span data-ttu-id="4d285-226">Nei siti di succursale di grandi dimensioni dotati di più subnet, per inoltrare query DHCP 120 al server DHCP (configurazione 1) o alla funzione di registrazione (configurazione 2), è inoltre necessario abilitare gli agenti di inoltro DHCP.</span><span class="sxs-lookup"><span data-stu-id="4d285-226">Additionally, for larger branch sites that have multiple subnets, DHCP relay agents should be enabled to forward DHCP Option 120 queries to the DHCP Server (configuration 1) or to the Registrar (configuration 2).</span></span>

<span data-ttu-id="4d285-227">Infine, gli utenti dei siti di succursale devono essere configurati per VoIP aziendale e provisionati con un endpoint di comunicazioni unificate appropriato.</span><span class="sxs-lookup"><span data-stu-id="4d285-227">Finally, branch site users must be configured for Enterprise Voice and provisioned with an appropriate unified communications endpoint.</span></span>

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a><span data-ttu-id="4d285-228">Requisiti per Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="4d285-228">Requirements for Survivable Branch Servers</span></span>

<span data-ttu-id="4d285-229">I requisiti per i Survivable Branch Server sono gli stessi dei requisiti per un front end server.</span><span class="sxs-lookup"><span data-stu-id="4d285-229">The requirements for Survivable Branch Servers are the same as the requirements for a Front End Server.</span></span> <span data-ttu-id="4d285-230">Per informazioni dettagliate, vedere [server hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="4d285-230">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a><span data-ttu-id="4d285-231">Requisiti per distribuzioni di siti di succursale Lync Server in scala intera</span><span class="sxs-lookup"><span data-stu-id="4d285-231">Requirements for Full-Scale Lync Server Branch-Site Deployments</span></span>

<span data-ttu-id="4d285-232">Per informazioni dettagliate, vedere [Determining Your Infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="4d285-232">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

