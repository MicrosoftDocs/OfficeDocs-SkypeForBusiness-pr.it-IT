---
title: Requisiti per i servizi di conferenza telefonica con accesso esterno di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2f4878e81a28b5d51726cb1f3e2dc5c7c5aa0fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="1256e-102">Requisiti per i servizi di conferenza telefonica con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1256e-102">Dial-in conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1256e-103">_**Argomento Ultima modifica:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="1256e-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="1256e-104">Prima di avviare il processo di distribuzione di Lync Server 2013 è necessario pianificare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1256e-104">Before you start the Lync Server 2013 deployment process you need to plan for the following:</span></span>

  - <span data-ttu-id="1256e-105">La configurazione da usare per la connessione alla rete PSTN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="1256e-105">The configuration to use for connecting to the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="1256e-106">Strategia per l'assegnazione di aree per i servizi di conferenza telefonica con accesso esterno ai numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="1256e-106">Your strategy for assigning dial-in conferencing regions to dial-in access numbers</span></span>

  - <span data-ttu-id="1256e-107">Strategia per la creazione di directory conferenza</span><span class="sxs-lookup"><span data-stu-id="1256e-107">Your strategy for creating conference directories</span></span>

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a><span data-ttu-id="1256e-108">Pianificazione della connettività PSTN con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="1256e-108">Planning for Dial-in PSTN Connectivity</span></span>

<span data-ttu-id="1256e-109">I servizi di conferenza telefonica con accesso esterno richiedono almeno un Mediation Server e almeno un gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="1256e-109">Dial-in conferencing requires at least one Mediation Server and at least one PSTN gateway.</span></span>

<span data-ttu-id="1256e-110">È possibile distribuire un Mediation Server in un sito centrale o in un sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="1256e-110">You can deploy a Mediation Server in a central site or in a branch site.</span></span> <span data-ttu-id="1256e-111">In un sito centrale è possibile collocare un Mediation Server in un pool Front-end o in un server Standard Edition oppure distribuirlo in un server o un pool autonomo.</span><span class="sxs-lookup"><span data-stu-id="1256e-111">In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool.</span></span> <span data-ttu-id="1256e-112">In un sito di succursale è possibile distribuire un Mediation Server in un server autonomo o come componente di Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="1256e-112">In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>

<span data-ttu-id="1256e-113">È possibile distribuire un gateway PSTN in un sito centrale o in un sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="1256e-113">You can deploy a PSTN gateway in a central site or in a branch site.</span></span> <span data-ttu-id="1256e-114">In un sito di succursale il gateway PSTN può essere autonomo o un componente dell'appliance Survivable Branch.</span><span class="sxs-lookup"><span data-stu-id="1256e-114">In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1256e-115">I servizi di conferenza telefonica con accesso esterno non usano il bypass multimediale perché un/V Conferencing Server non supporta il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="1256e-115">Dial-in conferencing does not use media bypass because A/V Conferencing Server do not support media bypass.</span></span>



</div>

<span data-ttu-id="1256e-116">Per informazioni dettagliate sulla pianificazione della configurazione per Mediation Server e gateway PSTN per i servizi di conferenza telefonica con accesso esterno, vedere [componenti e topologie per Mediation Server in Lync server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="1256e-116">For details about planning your configuration for Mediation Server and PSTN gateways for dial-in conferencing, see [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a><span data-ttu-id="1256e-117">Pianificazione per le aree di conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="1256e-117">Planning for Dial-in Conferencing Regions</span></span>

<span data-ttu-id="1256e-118">Durante la configurazione della chiamata in ingresso, è possibile creare piani di chiamata e numeri di accesso per i servizi di conferenza telefonica</span><span class="sxs-lookup"><span data-stu-id="1256e-118">During dial-in configuration, you create dial plans and dial-in conferencing access numbers.</span></span> <span data-ttu-id="1256e-119">I dial plan sono insiemi di regole di normalizzazione che specificano il numero e il modello di cifre in un numero di telefono e traducono il numero di telefono nel formato standard E. 164 per il routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="1256e-119">Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number and translate the phone number into the standard E.164 format for call routing.</span></span> <span data-ttu-id="1256e-120">I numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso sono i numeri che partecipano a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="1256e-120">Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>

<span data-ttu-id="1256e-121">Tutte le conferenze telefoniche con accesso esterno devono essere associate ad almeno un dial plan.</span><span class="sxs-lookup"><span data-stu-id="1256e-121">Every dial-in conferencing access number must be associated with at least one dial plan.</span></span> <span data-ttu-id="1256e-122">Le aree dei servizi di conferenza telefonica con accesso esterno associano un numero di telefono per i servizi di conferenza telefonica con dial plan.</span><span class="sxs-lookup"><span data-stu-id="1256e-122">Dial-in conferencing regions associate a dial-in conferencing access number with its dial plans.</span></span> <span data-ttu-id="1256e-123">Quando si configura un dial plan, si specifica l'area dei servizi di conferenza telefonica con accesso esterno che si applica al dial plan.</span><span class="sxs-lookup"><span data-stu-id="1256e-123">When you set up a dial plan, you specify the dial-in conferencing region that applies to the dial plan.</span></span> <span data-ttu-id="1256e-124">Quando si crea il numero di accesso per la chiamata in ingresso, si selezionano le aree geografiche che associano il numero di accesso con i dial plan appropriati.</span><span class="sxs-lookup"><span data-stu-id="1256e-124">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="1256e-125">Quando si crea un dial plan, si specifica l'ambito del dial plan: ambito utente, ambito del pool o ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="1256e-125">When you create a dial plan, you specify the scope of the dial plan: user scope, pool scope, or site scope.</span></span> <span data-ttu-id="1256e-126">A ogni utente viene assegnato il dial plan dall'ambito più ristretto che si applica all'utente.</span><span class="sxs-lookup"><span data-stu-id="1256e-126">Every user is assigned the dial plan from the narrowest scope that applies to the user.</span></span> <span data-ttu-id="1256e-127">Ad esempio, a un utente viene assegnato un dial plan a livello di utente, se si applica.</span><span class="sxs-lookup"><span data-stu-id="1256e-127">For example, a user is assigned a user-level dial plan, if one applies.</span></span> <span data-ttu-id="1256e-128">Se non si applica un dial plan a livello di utente, all'utente viene assegnato un dial plan a livello di pool.</span><span class="sxs-lookup"><span data-stu-id="1256e-128">If a user-level dial plan does not apply, the user is assigned a pool-level dial plan.</span></span> <span data-ttu-id="1256e-129">Se non si applica un dial plan a livello di pool, all'utente viene assegnato un dial plan a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="1256e-129">If a pool-level dial plan does not apply, the user is assigned a site-level dial plan.</span></span> <span data-ttu-id="1256e-130">Se non si applica un dial plan a livello di sito, all'utente viene assegnato il dial plan globale.</span><span class="sxs-lookup"><span data-stu-id="1256e-130">If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span>

<span data-ttu-id="1256e-131">Prima di configurare i dial plan, è importante pianificare il nome e l'uso delle aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="1256e-131">Before you configure the dial plans, is it important to plan how you want to name and use regions.</span></span> <span data-ttu-id="1256e-132">Le considerazioni seguenti si applicano alle aree dei servizi di conferenza telefonica con accesso esterno:</span><span class="sxs-lookup"><span data-stu-id="1256e-132">The following considerations apply to dial-in conferencing regions:</span></span>

  - <span data-ttu-id="1256e-133">In genere un'area geografica è associata a un ufficio o a un gruppo di uffici.</span><span class="sxs-lookup"><span data-stu-id="1256e-133">A region is typically a geographical area that is associated with an office or group of offices.</span></span>

  - <span data-ttu-id="1256e-134">Le lingue sono associate ai numeri di accesso per la chiamata in ingresso.</span><span class="sxs-lookup"><span data-stu-id="1256e-134">Languages are associated with dial-in access numbers.</span></span> <span data-ttu-id="1256e-135">Se si supportano aree geografiche con più lingue, è necessario decidere come definire le aree per il supporto di più lingue.</span><span class="sxs-lookup"><span data-stu-id="1256e-135">If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages.</span></span> <span data-ttu-id="1256e-136">Ad esempio, è possibile definire più aree in base a una combinazione di geografia e lingua oppure definire una singola area geografica in base alla geografia e avere un numero di accesso esterno diverso per ogni lingua.</span><span class="sxs-lookup"><span data-stu-id="1256e-136">For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>

  - <span data-ttu-id="1256e-137">Quando un utente pianifica una riunione, per impostazione predefinita la riunione usa l'area specificata dal dial plan dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1256e-137">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>

  - <span data-ttu-id="1256e-138">Per impostazione predefinita, tutti i numeri di accesso per le connessioni in ingresso per l'area geografica sono inclusi nell'invito alla riunione.</span><span class="sxs-lookup"><span data-stu-id="1256e-138">By default, the all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>

  - <span data-ttu-id="1256e-139">È importante assegnare un nome alle aree geografiche in modo che siano chiaramente riconoscibili.</span><span class="sxs-lookup"><span data-stu-id="1256e-139">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="1256e-140">L'utente può usare i nomi delle aree geografiche per modificare l'area geografica di una riunione in modo da includere nell'invito diversi numeri di accesso.</span><span class="sxs-lookup"><span data-stu-id="1256e-140">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="1256e-141">Quando gli utenti usano Outlook per pianificare una riunione, l'utente usa il componente aggiuntivo riunione online per Lync 2013 per modificare l'area geografica.</span><span class="sxs-lookup"><span data-stu-id="1256e-141">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Lync 2013 to change the region).</span></span>

  - <span data-ttu-id="1256e-142">Le aree geografiche devono essere progettate in modo che tutti gli invitati che desiderano connettersi a una conferenza possano visualizzare un numero di accesso locale nell'invito alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="1256e-142">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>

  - <span data-ttu-id="1256e-143">È possibile configurare l'ordine in cui i numeri di accesso all'interno di un'area vengono visualizzati nella pagina delle impostazioni di conferenza telefonica con accesso esterno (e, di conseguenza, nell'ordine in cui vengono visualizzati nell'invito alla conferenza) usando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1256e-143">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="1256e-144">Qualsiasi utente da qualsiasi luogo può chiamare un numero di accesso esterno per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="1256e-144">Any user from any location can call any dial-in access number to join a conference.</span></span>

</div>

<div>

## <a name="planning-for-conference-directories"></a><span data-ttu-id="1256e-145">Pianificazione per le directory conferenza</span><span class="sxs-lookup"><span data-stu-id="1256e-145">Planning for Conference Directories</span></span>

<span data-ttu-id="1256e-146">Le directory conferenza mantengono un mapping tra l'ID riunione alfanumerico usato da un partecipante per partecipare a una conferenza quando si usa Lync 2013 e l'ID conferenza solo numerico usato da un partecipante di conferenza telefonica con accesso esterno per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="1256e-146">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="1256e-147">Il formato dell'ID conferenza è il seguente:</span><span class="sxs-lookup"><span data-stu-id="1256e-147">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="1256e-148">La creazione di più directory conferenza garantirà che gli ID conferenza rimarranno invariati finché non verrà creata una quantità significativa di conferenze.</span><span class="sxs-lookup"><span data-stu-id="1256e-148">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="1256e-149">In un'organizzazione con un numero tipico di conferenze per ogni utente, è consigliabile creare una directory conferenza per ogni utenti di 999 nel pool.</span><span class="sxs-lookup"><span data-stu-id="1256e-149">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="1256e-150">Uso di questa guida di riferimento gli ID conferenza possono in genere essere mantenuti piccoli.</span><span class="sxs-lookup"><span data-stu-id="1256e-150">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="1256e-151">Tuttavia, una volta che il numero di directory conferenza (tra i pool) supera 9, il numero dell'ID conferenza crescerà per supportare altre conferenze.</span><span class="sxs-lookup"><span data-stu-id="1256e-151">However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1256e-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1256e-152">See Also</span></span>


[<span data-ttu-id="1256e-153">Componente Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1256e-153">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  
[<span data-ttu-id="1256e-154">Dial plan e regole di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1256e-154">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

