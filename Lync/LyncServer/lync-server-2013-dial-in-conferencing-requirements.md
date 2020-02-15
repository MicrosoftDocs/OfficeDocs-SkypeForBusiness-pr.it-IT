---
title: Requisiti per le conferenze telefoniche con accesso esterno di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b80ab9db6b565530db211db8aa47e2e00cbd9cf2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="5d388-102">Requisiti per le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d388-102">Dial-in conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d388-103">_**Ultimo argomento modificato:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="5d388-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="5d388-104">Prima di avviare il processo di distribuzione di Lync Server 2013, è necessario pianificare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d388-104">Before you start the Lync Server 2013 deployment process you need to plan for the following:</span></span>

  - <span data-ttu-id="5d388-105">La configurazione da utilizzare per la connessione alla rete PSTN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="5d388-105">The configuration to use for connecting to the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="5d388-106">La strategia per l'assegnazione delle aree di conferenza telefonica con accesso esterno ai numeri di chiamata in ingresso</span><span class="sxs-lookup"><span data-stu-id="5d388-106">Your strategy for assigning dial-in conferencing regions to dial-in access numbers</span></span>

  - <span data-ttu-id="5d388-107">La strategia per la creazione di directory conferenze</span><span class="sxs-lookup"><span data-stu-id="5d388-107">Your strategy for creating conference directories</span></span>

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a><span data-ttu-id="5d388-108">Pianificazione della connettività PSTN con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="5d388-108">Planning for Dial-in PSTN Connectivity</span></span>

<span data-ttu-id="5d388-109">Le conferenze telefoniche con accesso esterno richiedono almeno un Mediation Server e almeno un gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="5d388-109">Dial-in conferencing requires at least one Mediation Server and at least one PSTN gateway.</span></span>

<span data-ttu-id="5d388-110">È possibile distribuire un Mediation Server in un sito centrale o in un sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="5d388-110">You can deploy a Mediation Server in a central site or in a branch site.</span></span> <span data-ttu-id="5d388-111">In un sito centrale è possibile collocare un Mediation Server in un pool Front end o in un server Standard Edition oppure è possibile distribuirlo in un server autonomo o in un pool.</span><span class="sxs-lookup"><span data-stu-id="5d388-111">In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool.</span></span> <span data-ttu-id="5d388-112">In un sito di succursale è possibile distribuire un Mediation Server in un server autonomo o come componente del Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="5d388-112">In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>

<span data-ttu-id="5d388-113">È possibile distribuire un gateway PSTN in un sito centrale o in un sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="5d388-113">You can deploy a PSTN gateway in a central site or in a branch site.</span></span> <span data-ttu-id="5d388-114">In un sito di succursale, il gateway PSTN può essere autonomo o come componente del Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="5d388-114">In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5d388-115">Le conferenze telefoniche con accesso esterno non utilizzano il bypass multimediale perché A/V Conferencing Server non supporta il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="5d388-115">Dial-in conferencing does not use media bypass because A/V Conferencing Server do not support media bypass.</span></span>



</div>

<span data-ttu-id="5d388-116">Per informazioni dettagliate sulla pianificazione della configurazione per il Mediation Server e i gateway PSTN per le conferenze telefoniche con accesso esterno, vedere [componenti e topologie per Mediation Server in Lync server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="5d388-116">For details about planning your configuration for Mediation Server and PSTN gateways for dial-in conferencing, see [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a><span data-ttu-id="5d388-117">Pianificazione delle aree di conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="5d388-117">Planning for Dial-in Conferencing Regions</span></span>

<span data-ttu-id="5d388-118">Durante la configurazione della chiamata in ingresso, è possibile creare numeri di accesso esterno e dial plan.</span><span class="sxs-lookup"><span data-stu-id="5d388-118">During dial-in configuration, you create dial plans and dial-in conferencing access numbers.</span></span> <span data-ttu-id="5d388-119">I dial plan sono insiemi di regole di normalizzazione che specificano il numero e il modello di cifre di un numero di telefono e traducono il numero di telefono nel formato E. 164 standard per il routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="5d388-119">Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number and translate the phone number into the standard E.164 format for call routing.</span></span> <span data-ttu-id="5d388-120">Le conferenze telefoniche con accesso esterno sono i numeri che i partecipanti chiamano per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="5d388-120">Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>

<span data-ttu-id="5d388-121">Ogni numero di accesso per le conferenze telefoniche in ingresso deve essere associato ad almeno un dial plan.</span><span class="sxs-lookup"><span data-stu-id="5d388-121">Every dial-in conferencing access number must be associated with at least one dial plan.</span></span> <span data-ttu-id="5d388-122">Le aree di conferenza telefonica con accesso esterno associano un numero di telefono per le conferenze telefoniche con dial plan.</span><span class="sxs-lookup"><span data-stu-id="5d388-122">Dial-in conferencing regions associate a dial-in conferencing access number with its dial plans.</span></span> <span data-ttu-id="5d388-123">Quando si configura un dial plan, è necessario specificare l'area di conferenza telefonica con accesso esterno che si applica al dial plan.</span><span class="sxs-lookup"><span data-stu-id="5d388-123">When you set up a dial plan, you specify the dial-in conferencing region that applies to the dial plan.</span></span> <span data-ttu-id="5d388-124">Quando si crea il numero di accesso esterno, si selezionano le aree geografiche che associano il numero di accesso ai dial plan corretti.</span><span class="sxs-lookup"><span data-stu-id="5d388-124">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="5d388-125">Quando si crea un dial plan, è necessario specificare l'ambito del dial plan: ambito utente, ambito del pool o ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="5d388-125">When you create a dial plan, you specify the scope of the dial plan: user scope, pool scope, or site scope.</span></span> <span data-ttu-id="5d388-126">A ogni utente viene assegnato il dial plan dall'ambito più stretto applicato all'utente.</span><span class="sxs-lookup"><span data-stu-id="5d388-126">Every user is assigned the dial plan from the narrowest scope that applies to the user.</span></span> <span data-ttu-id="5d388-127">Ad esempio, a un utente viene assegnato un dial plan a livello di utente, se si applica.</span><span class="sxs-lookup"><span data-stu-id="5d388-127">For example, a user is assigned a user-level dial plan, if one applies.</span></span> <span data-ttu-id="5d388-128">Se non si applica un dial plan a livello di utente, all'utente viene assegnato un dial plan a livello di pool.</span><span class="sxs-lookup"><span data-stu-id="5d388-128">If a user-level dial plan does not apply, the user is assigned a pool-level dial plan.</span></span> <span data-ttu-id="5d388-129">Se non si applica un dial plan a livello di pool, all'utente viene assegnato un dial plan a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="5d388-129">If a pool-level dial plan does not apply, the user is assigned a site-level dial plan.</span></span> <span data-ttu-id="5d388-130">Se non si applica un dial plan a livello di sito, all'utente viene assegnato il dial plan globale.</span><span class="sxs-lookup"><span data-stu-id="5d388-130">If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span>

<span data-ttu-id="5d388-131">Prima di configurare i dial plan, è importante pianificare la modalità di denominazione e l'utilizzo delle aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="5d388-131">Before you configure the dial plans, is it important to plan how you want to name and use regions.</span></span> <span data-ttu-id="5d388-132">Le considerazioni seguenti sono valide per le aree di conferenza telefonica con accesso esterno:</span><span class="sxs-lookup"><span data-stu-id="5d388-132">The following considerations apply to dial-in conferencing regions:</span></span>

  - <span data-ttu-id="5d388-133">Una regione è in genere un'area geografica associata a un ufficio o a un gruppo di uffici.</span><span class="sxs-lookup"><span data-stu-id="5d388-133">A region is typically a geographical area that is associated with an office or group of offices.</span></span>

  - <span data-ttu-id="5d388-134">Le lingue sono associate ai numeri di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="5d388-134">Languages are associated with dial-in access numbers.</span></span> <span data-ttu-id="5d388-135">Se si supportano aree geografiche con più lingue, è necessario decidere in che modo si desidera definire le aree per il supporto di più lingue.</span><span class="sxs-lookup"><span data-stu-id="5d388-135">If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages.</span></span> <span data-ttu-id="5d388-136">Ad esempio, è possibile definire più aree in base a una combinazione di geografia e lingua oppure definire una singola area geografica in base alla geografia e disporre di un numero di accesso esterno diverso per ogni lingua.</span><span class="sxs-lookup"><span data-stu-id="5d388-136">For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>

  - <span data-ttu-id="5d388-137">Quando un utente pianifica una riunione, per impostazione predefinita la riunione utilizza l'area specificata dal dial plan dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5d388-137">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>

  - <span data-ttu-id="5d388-138">Per impostazione predefinita, tutti i numeri di accesso esterno per l'area sono inclusi nell'invito alla riunione.</span><span class="sxs-lookup"><span data-stu-id="5d388-138">By default, the all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>

  - <span data-ttu-id="5d388-139">È importante assegnare un nome alle aree geografiche in modo che siano chiaramente riconoscibili.</span><span class="sxs-lookup"><span data-stu-id="5d388-139">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="5d388-140">L'utente può utilizzare i nomi delle aree geografiche per modificare l'area di una riunione in modo che i numeri di accesso diversi siano inclusi nell'invito.</span><span class="sxs-lookup"><span data-stu-id="5d388-140">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="5d388-141">Quando gli utenti utilizzano Outlook per pianificare una riunione, l'utente utilizza il componente aggiuntivo per riunioni online per Lync 2013 per modificare l'area geografica.</span><span class="sxs-lookup"><span data-stu-id="5d388-141">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Lync 2013 to change the region).</span></span>

  - <span data-ttu-id="5d388-142">Le aree geografiche devono essere progettate in modo che qualsiasi invitato che desidera comporre una conferenza possa visualizzare un numero di accesso locale nell'invito alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="5d388-142">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>

  - <span data-ttu-id="5d388-143">È possibile configurare l'ordine in cui i numeri di accesso all'interno di un'area vengono visualizzati nella pagina Impostazioni conferenza telefonica con chiamata in ingresso (e, di conseguenza, nell'ordine in cui vengono visualizzati nell'invito alla conferenza) utilizzando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5d388-143">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="5d388-144">Qualsiasi utente da qualsiasi percorso può chiamare qualsiasi numero di accesso esterno per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="5d388-144">Any user from any location can call any dial-in access number to join a conference.</span></span>

</div>

<div>

## <a name="planning-for-conference-directories"></a><span data-ttu-id="5d388-145">Pianificazione delle directory conferenze</span><span class="sxs-lookup"><span data-stu-id="5d388-145">Planning for Conference Directories</span></span>

<span data-ttu-id="5d388-146">Le directory conferenze mantengono un mapping tra l'ID riunione alfanumerico utilizzato da un partecipante per partecipare a una conferenza quando si utilizza Lync 2013 e l'ID conferenza solo numerico utilizzato da un partecipante di conferenze telefoniche con accesso esterno per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="5d388-146">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="5d388-147">Il formato dell'ID conferenza è il seguente:</span><span class="sxs-lookup"><span data-stu-id="5d388-147">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="5d388-148">La creazione di più directory conferenze garantirà che gli ID conferenza rimarranno invariati fino a quando non verrà creata una quantità significativa di conferenze.</span><span class="sxs-lookup"><span data-stu-id="5d388-148">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="5d388-149">In un'organizzazione che dispone di un numero tipico di conferenze per utente, si consiglia di creare una directory conferenze per ogni 999 utenti nel pool.</span><span class="sxs-lookup"><span data-stu-id="5d388-149">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="5d388-150">Utilizzo di questa guida di riferimento gli ID conferenza possono generalmente essere mantenuti piccoli.</span><span class="sxs-lookup"><span data-stu-id="5d388-150">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="5d388-151">Tuttavia, una volta che il numero di directory conferenze (tra i pool) è superiore a 9, il numero dell'ID conferenza aumenterà per supportare altre conferenze.</span><span class="sxs-lookup"><span data-stu-id="5d388-151">However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5d388-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d388-152">See Also</span></span>


[<span data-ttu-id="5d388-153">Componente Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d388-153">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  
[<span data-ttu-id="5d388-154">Dial plan e regole di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d388-154">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

