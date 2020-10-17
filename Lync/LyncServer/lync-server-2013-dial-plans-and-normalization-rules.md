---
title: 'Lync Server 2013: dial plan e regole di normalizzazione'
description: 'Lync Server 2013: dial plan e regole di normalizzazione.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0341d0c5267a2272ff45bd93408b2bd14f0ceeaa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559742"
---
# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="183d9-103">Dial plan e regole di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="183d9-103">Dial plans and normalization rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="183d9-104">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="183d9-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="183d9-105">Per dial plan si intende un set denominato di regole di normalizzazione che consente di convertire i numeri di telefono relativi a una località, a un utente o a un oggetto contatto specifico in un unico formato standard (E.164) ai fini dell'autorizzazione del telefono e del routing della chiamata.</span><span class="sxs-lookup"><span data-stu-id="183d9-105">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span>

<span data-ttu-id="183d9-106">Le regole di normalizzazione definiscono il modo in cui i numeri di telefono espressi nei vari formati devono essere instradati per ogni posizione, utente o oggetto contatto specificato.</span><span class="sxs-lookup"><span data-stu-id="183d9-106">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span> <span data-ttu-id="183d9-107">La stessa stringa di composizione può essere interpretata e convertita in modo diverso, a seconda della posizione da cui viene composto e della persona o dell'oggetto contatto che effettua la chiamata.</span><span class="sxs-lookup"><span data-stu-id="183d9-107">The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object making the call.</span></span>

<div>

## <a name="dial-plan-scope"></a><span data-ttu-id="183d9-108">Ambito del dial plan</span><span class="sxs-lookup"><span data-stu-id="183d9-108">Dial Plan Scope</span></span>

<span data-ttu-id="183d9-109">L'*ambito* di un dial plan determina il livello gerarchico a cui è possibile applicare il dial plan.</span><span class="sxs-lookup"><span data-stu-id="183d9-109">A dial plan’s *scope* determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="183d9-110">In Lync Server, a un utente può essere assegnato un dial plan specifico per utente.</span><span class="sxs-lookup"><span data-stu-id="183d9-110">In Lync Server, a user can be assigned a specific per-user dial plan.</span></span> <span data-ttu-id="183d9-111">Se non viene assegnato un dial plan utente, viene applicato il dial plan del pool di registrazione.</span><span class="sxs-lookup"><span data-stu-id="183d9-111">If a user dial plan is not assigned, the Registrar pool dial plan is applied.</span></span> <span data-ttu-id="183d9-112">Se non è presente alcun dial plan del pool di registrazione, viene applicato il dial plan del sito.</span><span class="sxs-lookup"><span data-stu-id="183d9-112">If there is no Registrar pool dial plan, the site dial plan is applied.</span></span> <span data-ttu-id="183d9-113">Infine, se non è presente alcun altro dial plan applicabile all'utente, viene applicato il dial plan globale.</span><span class="sxs-lookup"><span data-stu-id="183d9-113">Finally, if there is no other dial plan applicable to the user, the global dial plan is applied.</span></span>

<span data-ttu-id="183d9-114">I client ottengono i livelli di ambito del dial plan tramite le impostazioni di provisioning in-band fornite quando gli utenti accedono a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="183d9-114">Clients obtain dial plan scope levels through in-band provisioning settings that are provided when users log on to Lync Server.</span></span> <span data-ttu-id="183d9-115">In qualità di amministratore, è possibile gestire e assegnare i livelli di ambito del piano di chiamata utilizzando il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="183d9-115">As the administrator, you can manage and assign dial plan scope levels by using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="183d9-116">Il dial plan del gateway PSTN (Public Switched Telephone Network) a livello di servizio viene applicato alle chiamate in arrivo da un determinato gateway.</span><span class="sxs-lookup"><span data-stu-id="183d9-116">The service level public switched telephone network (PSTN) gateway dial plan is applied to the incoming calls from a particular gateway.</span></span>



</div>

<span data-ttu-id="183d9-117">I livelli di ambito del dial plan sono definiti come segue:</span><span class="sxs-lookup"><span data-stu-id="183d9-117">Dial plan scope levels are defined as follows:</span></span>

  - <span data-ttu-id="183d9-118">**Dial plan utente:** Può essere assegnato a singoli utenti, gruppi o oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="183d9-118">**User dial plan:** Can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="183d9-119">Le applicazioni vocali possono cercare un dial plan per utente quando si riceve una chiamata con il contesto telefonico impostato su User-default.</span><span class="sxs-lookup"><span data-stu-id="183d9-119">Voice applications can look up a per-user dial plan when a call is received with the phone-context set to user-default.</span></span> <span data-ttu-id="183d9-120">Ai fini dell'assegnazione di un dial plan, un oggetto contatto viene trattato come un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="183d9-120">For the purpose of assigning a dial plan, a contact object is treated as an individual user.</span></span>

  - <span data-ttu-id="183d9-121">**Dial plan del pool:** Può essere creato a livello di servizio per qualsiasi gateway PSTN o registrar nella topologia.</span><span class="sxs-lookup"><span data-stu-id="183d9-121">**Pool dial plan:** Can be created at the service level for any PSTN gateway or Registrar in your topology.</span></span> <span data-ttu-id="183d9-122">Per definire un dial plan pool, è necessario specificare un particolare servizio (gateway PSTN o pool di registrazione) a cui applicare il dial plan.</span><span class="sxs-lookup"><span data-stu-id="183d9-122">To define a pool dial plan, you must specify the particular service (PSTN gateway or Registrar pool) to which the dial plan applies.</span></span>

  - <span data-ttu-id="183d9-123">**Dial plan del sito:** Può essere creato per un intero sito, ad eccezione degli utenti, dei gruppi o degli oggetti contatto a cui è assegnato un dial plan di pool o un dial plan utente.</span><span class="sxs-lookup"><span data-stu-id="183d9-123">**Site dial plan:** Can be created for an entire site, except for any users, groups, or contact objects that are assigned a pool dial plan or user dial plan.</span></span> <span data-ttu-id="183d9-124">Per definire un dial plan sito, è necessario specificare il sito a cui applicare il dial plan.</span><span class="sxs-lookup"><span data-stu-id="183d9-124">To define a site dial plan, you must specify the site to which the dial plan applies.</span></span>

  - <span data-ttu-id="183d9-125">**Dial plan globale:** Il dial plan predefinito installato con il prodotto.</span><span class="sxs-lookup"><span data-stu-id="183d9-125">**Global dial plan:** The default dial plan installed with the product.</span></span> <span data-ttu-id="183d9-126">È possibile modificare il dial plan globale, ma non eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="183d9-126">You can edit the global dial plan, but you cannot delete it.</span></span> <span data-ttu-id="183d9-127">Questo dial plan si applica a tutti gli utenti, i gruppi e gli oggetti contatto di VoIP aziendale nella distribuzione, a meno che non si configuri e assegni un dial plan con un ambito più specifico.</span><span class="sxs-lookup"><span data-stu-id="183d9-127">This dial plan applies to all Enterprise Voice users, groups, and contact objects in your deployment, unless you configure and assign a dial plan with a more specific scope.</span></span>

</div>

<div>

## <a name="planning-for-dial-plans"></a><span data-ttu-id="183d9-128">Pianificazione di dial plan</span><span class="sxs-lookup"><span data-stu-id="183d9-128">Planning for Dial Plans</span></span>

<span data-ttu-id="183d9-129">Per pianificare un dial plan, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="183d9-129">To plan a dial plan, follow these steps:</span></span>

  - <span data-ttu-id="183d9-130">Elencare tutte le impostazioni locali in cui l'organizzazione ha un ufficio.</span><span class="sxs-lookup"><span data-stu-id="183d9-130">List all the locales in which your organization has an office.</span></span>
    
    <span data-ttu-id="183d9-131">L'elenco deve essere aggiornato e completo.</span><span class="sxs-lookup"><span data-stu-id="183d9-131">The list must be up-to-date and complete.</span></span> <span data-ttu-id="183d9-132">Dovrà essere rivisto con l'evolversi della società.</span><span class="sxs-lookup"><span data-stu-id="183d9-132">It will need to be revised as company organization evolves.</span></span> <span data-ttu-id="183d9-133">In un'azienda di grandi dimensioni multinazionali con numerose filiali di piccole dimensioni, può essere un'attività che richiede molto tempo.</span><span class="sxs-lookup"><span data-stu-id="183d9-133">In a large, multinational company with numerous small branch offices, this can be a time-consuming task.</span></span>

  - <span data-ttu-id="183d9-134">Identificare i modelli di numeri validi per ogni sito.</span><span class="sxs-lookup"><span data-stu-id="183d9-134">Identify valid number patterns for each site.</span></span>
    
    <span data-ttu-id="183d9-p109">La parte della pianificazione dei dial plan che richiede più tempo è l'identificazione dei formati di numeri validi per ogni sito. In alcuni casi, può essere possibile copiare negli altri dial plan le regole di normalizzazione scritte per un dial plan, in particolare se i siti corrispondenti si trovano nello stesso paese, nella stessa area geografica o anche nello stesso continente. In altri casi, possono essere sufficienti piccole modifiche dei numeri in un dial plan per utilizzarli in altri dial plan.</span><span class="sxs-lookup"><span data-stu-id="183d9-p109">The most time-consuming part of planning your dial plans is identifying the valid number patterns for each site. In some cases, you may be able to copy normalization rules that you have written for one dial plan to other dial plans, especially if the corresponding sites are within the same country/region or even continent. In other cases, small changes to numbers in one dial plan may be enough to use them in other dial plans.</span></span>

  - <span data-ttu-id="183d9-138">Sviluppare uno schema a livello di organizzazione per la denominazione dei dial plan.</span><span class="sxs-lookup"><span data-stu-id="183d9-138">Develop an organization-wide scheme for naming dial plans.</span></span>
    
    <span data-ttu-id="183d9-139">L'adozione di uno schema di denominazione standard assicura la coerenza all'interno dell'organizzazione e agevola la manutenzione e gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="183d9-139">Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>

  - <span data-ttu-id="183d9-140">Decidere se sono necessari più dial plan per una singola posizione.</span><span class="sxs-lookup"><span data-stu-id="183d9-140">Decide whether multiple dial plans are required for a single location.</span></span>
    
    <span data-ttu-id="183d9-141">Se l'organizzazione gestisce un singolo dial plan su più posizioni, potrebbe essere comunque necessario creare un dial plan separato per gli utenti di VoIP aziendale che eseguono la migrazione da un sistema PBX (Private Branch Exchange) e che devono mantenere le proprie estensioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="183d9-141">If your organization maintains a single dial plan across multiple locations, you may still need to create a separate dial plan for Enterprise Voice users who are migrating from a private branch exchange (PBX) and who need to have their existing extensions retained.</span></span>

  - <span data-ttu-id="183d9-142">Decidere se i dial plan per utente sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="183d9-142">Decide whether per-user dial plans are required.</span></span> <span data-ttu-id="183d9-143">Ad esempio, se si dispone di utenti in un sito di succursale registrato con il sito centrale o se si dispone di utenti registrati in un Survivable Branch Appliance, è possibile prendere in considerazione scenari di composizione speciali per tali utenti utilizzando i dial plan per utente e le regole di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="183d9-143">For example, if you have users at a branch site who are registered with the central site or if you have users who are registered on a Survivable Branch Appliance, you can consider special dialing scenarios for such users using per-user dial plans and normalization rules.</span></span> <span data-ttu-id="183d9-144">Per informazioni dettagliate, vedere [requisiti di resilienza dei siti di succursale per Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="183d9-144">For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span></span>

  - <span data-ttu-id="183d9-145">Determinare l'ambito del dial plan (come descritto in precedenza in questo argomento).</span><span class="sxs-lookup"><span data-stu-id="183d9-145">Determine dial plan scope (as previously described in this topic).</span></span>

<span data-ttu-id="183d9-146">Per creare un dial plan, è necessario specificare i valori nei campi seguenti, in base alle esigenze, utilizzando il pannello di controllo di Lync Server o Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="183d9-146">To create a dial plan, you specify values in the following fields, as required, by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="name-and-simple-name"></a><span data-ttu-id="183d9-147">Nome e nome semplice</span><span class="sxs-lookup"><span data-stu-id="183d9-147">Name and Simple Name</span></span>

<span data-ttu-id="183d9-148">Per i dial plan utente, è necessario specificare un nome descrittivo che identifichi gli utenti, i gruppi o gli oggetti contatto a cui verrà assegnato il piano di chiamata.</span><span class="sxs-lookup"><span data-stu-id="183d9-148">For user dial plans, you should specify a descriptive name that identifies the users, groups, or contact objects to which the dial plan will be assigned.</span></span> <span data-ttu-id="183d9-149">Per i dial plan sito, il campo Nome è precompilato con il nome del sito e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="183d9-149">For site dial plans, the Name field is prepopulated with the site name and cannot be changed.</span></span> <span data-ttu-id="183d9-150">Per i dial plan del pool, il campo nome viene prepopolato con il gateway PSTN o con il nome di dominio completo (FQDN) del pool Front end e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="183d9-150">For pool dial plans, the Name field is prepopulated with the PSTN gateway or Front End pool fully qualified domain name (FQDN) and cannot be changed.</span></span>

<span data-ttu-id="183d9-151">Il *Nome semplice* del dial plan è precompilato con una stringa derivata dal nome del dial plan.</span><span class="sxs-lookup"><span data-stu-id="183d9-151">The dial plan *Simple Name* is prepopulated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="183d9-152">Il campo nome semplice è modificabile, che consente di creare una convenzione di denominazione più descrittiva per i dial plan.</span><span class="sxs-lookup"><span data-stu-id="183d9-152">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="183d9-153">Il valore *Nome semplice* non può essere vuoto e deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="183d9-153">The *Simple Name* value cannot be empty and must be unique.</span></span> <span data-ttu-id="183d9-154">Una procedura consigliata consiste nello sviluppare una convenzione di denominazione per l'intera organizzazione e quindi utilizzare questa convenzione in modo coerente in tutti i siti e gli utenti.</span><span class="sxs-lookup"><span data-stu-id="183d9-154">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

</div>

<div>

## <a name="description"></a><span data-ttu-id="183d9-155">Descrizione</span><span class="sxs-lookup"><span data-stu-id="183d9-155">Description</span></span>

<span data-ttu-id="183d9-p113">Si consiglia di digitare il nome comune e riconoscibile della località geografica a cui si applica il dial plan corrispondente. Se ad esempio il nome del dial plan è Londra.Contoso.com, la descrizione consigliabile è Londra.</span><span class="sxs-lookup"><span data-stu-id="183d9-p113">We recommend that you type the common, recognizable name of the geographic location to which the corresponding dial plan applies. For example, if the dial plan name is London.Contoso.com, the recommended description would be London.</span></span>

</div>

<div>

## <a name="dial-in-conferencing-region"></a><span data-ttu-id="183d9-158">Area conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="183d9-158">Dial-in Conferencing Region</span></span>

<span data-ttu-id="183d9-159">Se si distribuisce la funzionalità di conferenza telefonica con accesso esterno, è necessario specificare un'area della conferenza telefonica con accesso esterno per associare i numeri di accesso relativi a un dial plan.</span><span class="sxs-lookup"><span data-stu-id="183d9-159">If you are deploying dial-in conferencing, you will need to specify a dial-in conferencing region to associate dial-in conferencing access numbers with a dial plan.</span></span>

</div>

<div>

## <a name="external-access-prefix"></a><span data-ttu-id="183d9-160">Prefisso accesso esterno</span><span class="sxs-lookup"><span data-stu-id="183d9-160">External Access Prefix</span></span>

<span data-ttu-id="183d9-161">È possibile specificare un prefisso di accesso esterno composto da un massimo di quattro caratteri ( \# \* e 0-9) se gli utenti devono comporre una o più cifre iniziali aggiuntive (ad esempio, 9) per ottenere una linea esterna.</span><span class="sxs-lookup"><span data-stu-id="183d9-161">You can specify an external access prefix of up to four characters (\#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="183d9-162">Se si specifica un prefisso di accesso esterno, non è necessario creare una regola di normalizzazione aggiuntiva per regolare il prefisso.</span><span class="sxs-lookup"><span data-stu-id="183d9-162">If you specify an external access prefix, you do not need to create an additional normalization rule to accommodate the prefix.</span></span>



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a><span data-ttu-id="183d9-163">Regole di normalizzazione</span><span class="sxs-lookup"><span data-stu-id="183d9-163">Normalization Rules</span></span>

<span data-ttu-id="183d9-164">Le regole di normalizzazione definiscono la modalità di routing di numeri di telefono espressi in formati diversi per la località specifica.</span><span class="sxs-lookup"><span data-stu-id="183d9-164">Normalization rules define how phone numbers expressed in various formats are to be routed for the named location.</span></span> <span data-ttu-id="183d9-165">La stessa stringa di numeri può essere interpretata e convertita in modo diverso, a seconda delle impostazioni locali da cui viene composto.</span><span class="sxs-lookup"><span data-stu-id="183d9-165">The same number string may be interpreted and translated differently, depending on the locale from which it is dialed.</span></span> <span data-ttu-id="183d9-166">Sono necessarie per il routing delle chiamate, perché gli utenti possono utilizzare vari formati quando immettono i numeri di telefono nei rispettivi elenchi contatti.</span><span class="sxs-lookup"><span data-stu-id="183d9-166">Normalization rules are necessary for call routing because users can, and do, use various formats when entering phone numbers in their Contacts lists.</span></span>

<span data-ttu-id="183d9-167">La normalizzazione dei numeri di telefono forniti dall'utente fornisce un formato coerente che facilita le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="183d9-167">Normalizing user-supplied phone numbers provides a consistent format that facilitates the following tasks:</span></span>

  - <span data-ttu-id="183d9-168">Associare un numero composto al SIP-URI del destinatario previsto.</span><span class="sxs-lookup"><span data-stu-id="183d9-168">Match a dialed number to the intended recipient’s SIP-URI.</span></span>

  - <span data-ttu-id="183d9-169">Applicare le regole di autorizzazione di composizione alla parte chiamante.</span><span class="sxs-lookup"><span data-stu-id="183d9-169">Apply dialing authorization rules to the calling party.</span></span>

<span data-ttu-id="183d9-170">Di seguito sono riportati alcuni campi numerici che può essere necessario includere nelle regole di normalizzazione:</span><span class="sxs-lookup"><span data-stu-id="183d9-170">The following number fields are among those that your normalization rules may need to account for:</span></span>

  - <span data-ttu-id="183d9-171">Dial plan</span><span class="sxs-lookup"><span data-stu-id="183d9-171">Dial plan</span></span>

  - <span data-ttu-id="183d9-172">Codice paese</span><span class="sxs-lookup"><span data-stu-id="183d9-172">Country code</span></span>

  - <span data-ttu-id="183d9-173">Indicativo di località</span><span class="sxs-lookup"><span data-stu-id="183d9-173">Area code</span></span>

  - <span data-ttu-id="183d9-174">Lunghezza numero di interno</span><span class="sxs-lookup"><span data-stu-id="183d9-174">Length of extension</span></span>

  - <span data-ttu-id="183d9-175">Prefisso sito</span><span class="sxs-lookup"><span data-stu-id="183d9-175">Site prefix</span></span>

<div>

## <a name="creating-normalization-rules"></a><span data-ttu-id="183d9-176">Creazione di regole di normalizzazione</span><span class="sxs-lookup"><span data-stu-id="183d9-176">Creating Normalization Rules</span></span>

<span data-ttu-id="183d9-177">Le regole di normalizzazione utilizzano le espressioni regolari di .NET Framework per specificare formati di corrispondenza numerica che il server utilizza per convertire le stringhe di composizione nel formato E.164 allo scopo di eseguire la ricerca inversa dei numeri.</span><span class="sxs-lookup"><span data-stu-id="183d9-177">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup.</span></span> <span data-ttu-id="183d9-178">Per creare le regole di normalizzazione nel pannello di controllo di Lync Server, immettere manualmente le espressioni oppure immettendo le cifre iniziali e la lunghezza delle stringhe di composizione e consentendo al pannello di controllo di Lync Server di generare automaticamente l'espressione regolare corrispondente.</span><span class="sxs-lookup"><span data-stu-id="183d9-178">You create normalization rules in the Lync Server Control Panel either by entering the expressions manually, or by entering the starting digits and the length of the dial strings to be matched and letting the Lync Server Control Panel generate the corresponding regular expression for you.</span></span> <span data-ttu-id="183d9-179">In ogni caso, al termine è possibile immettere un numero di test per verificare che la regola di normalizzazione funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="183d9-179">Either way, when you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="183d9-180">Per informazioni dettagliate sull'utilizzo di espressioni regolari di .NET Framework, vedere la sezione relativa alle espressioni regolari di .NET Framework all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .</span><span class="sxs-lookup"><span data-stu-id="183d9-180">For details about using .NET Framework regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a><span data-ttu-id="183d9-181">Regole di normalizzazione di esempio</span><span class="sxs-lookup"><span data-stu-id="183d9-181">Sample Normalization Rules</span></span>

<span data-ttu-id="183d9-p116">Nella tabella seguente sono illustrati alcuni esempi di regole di normalizzazione scritte come espressioni regolari di .NET Framework. Si tratta di esempi puramente indicativi che non devono essere intesi come riferimenti obbligatori per la creazione di regole di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="183d9-p116">The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a><span data-ttu-id="183d9-184">Tabella 1. Regole di normalizzazione tramite espressioni regolari di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="183d9-184">Table 1.Normalization Rules Using .NET Framework Regular Expressions</span></span>

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
<th><span data-ttu-id="183d9-185">Nome regola</span><span class="sxs-lookup"><span data-stu-id="183d9-185">Rule name</span></span></th>
<th><span data-ttu-id="183d9-186">Descrizione</span><span class="sxs-lookup"><span data-stu-id="183d9-186">Description</span></span></th>
<th><span data-ttu-id="183d9-187">Formato numero</span><span class="sxs-lookup"><span data-stu-id="183d9-187">Number pattern</span></span></th>
<th><span data-ttu-id="183d9-188">Translation</span><span class="sxs-lookup"><span data-stu-id="183d9-188">Translation</span></span></th>
<th><span data-ttu-id="183d9-189">Esempio</span><span class="sxs-lookup"><span data-stu-id="183d9-189">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="183d9-190">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="183d9-190">4digitExtension</span></span></p></td>
<td><p><span data-ttu-id="183d9-191">Converte i numeri di interno a 4 cifre</span><span class="sxs-lookup"><span data-stu-id="183d9-191">Translates 4-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="183d9-192">^ (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="183d9-192">^(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="183d9-193">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="183d9-193">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="183d9-194">0100 viene convertito in +14255550100</span><span class="sxs-lookup"><span data-stu-id="183d9-194">0100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="183d9-195">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="183d9-195">5digitExtension</span></span></p></td>
<td><p><span data-ttu-id="183d9-196">Converte i numeri di interno a 5 cifre</span><span class="sxs-lookup"><span data-stu-id="183d9-196">Translates 5-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="183d9-197">^ 5 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="183d9-197">^5(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="183d9-198">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="183d9-198">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="183d9-199">50100 viene convertito in +14255550100</span><span class="sxs-lookup"><span data-stu-id="183d9-199">50100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="183d9-200">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="183d9-200">7digitcallingRedmond</span></span></p></td>
<td><p><span data-ttu-id="183d9-201">Converte i numeri a 7 cifre in numeri locali di Redmond</span><span class="sxs-lookup"><span data-stu-id="183d9-201">Translates 7-digit numbers to Redmond local numbers</span></span></p></td>
<td><p><span data-ttu-id="183d9-202">^ (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="183d9-202">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="183d9-203">+ 1425 $1</span><span class="sxs-lookup"><span data-stu-id="183d9-203">+1425$1</span></span></p></td>
<td><p><span data-ttu-id="183d9-204">5550100 viene convertito in +14255550100</span><span class="sxs-lookup"><span data-stu-id="183d9-204">5550100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="183d9-205">7digitcallingDallas</span><span class="sxs-lookup"><span data-stu-id="183d9-205">7digitcallingDallas</span></span></p></td>
<td><p><span data-ttu-id="183d9-206">Converte i numeri a 7 cifre in numeri locali di Dallas</span><span class="sxs-lookup"><span data-stu-id="183d9-206">Translates 7-digit numbers to Dallas local numbers</span></span></p></td>
<td><p><span data-ttu-id="183d9-207">^ (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="183d9-207">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="183d9-208">+ 1972 $1</span><span class="sxs-lookup"><span data-stu-id="183d9-208">+1972$1</span></span></p></td>
<td><p><span data-ttu-id="183d9-209">5550100 viene convertito in +19725550100</span><span class="sxs-lookup"><span data-stu-id="183d9-209">5550100 is translated to +19725550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="183d9-210">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="183d9-210">10digitcallingUS</span></span></p></td>
<td><p><span data-ttu-id="183d9-211">Converte i numeri a 10 cifre in numeri degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="183d9-211">Translates 10-digit numbers in the United States</span></span></p></td>
<td><p><span data-ttu-id="183d9-212">^ (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="183d9-212">^(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="183d9-213">+ 1 $1</span><span class="sxs-lookup"><span data-stu-id="183d9-213">+1$1</span></span></p></td>
<td><p><span data-ttu-id="183d9-214">2065550100 viene convertito in +12065550100</span><span class="sxs-lookup"><span data-stu-id="183d9-214">2065550100 is translated to +12065550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="183d9-215">LDCallingUS</span><span class="sxs-lookup"><span data-stu-id="183d9-215">LDCallingUS</span></span></p></td>
<td><p><span data-ttu-id="183d9-216">Converte i numeri con prefissi interurbani in numeri degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="183d9-216">Translates numbers with long distance prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="183d9-217">^ 1 (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="183d9-217">^1(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="183d9-218">+ $1</span><span class="sxs-lookup"><span data-stu-id="183d9-218">+$1</span></span></p></td>
<td><p><span data-ttu-id="183d9-219">12145550100 viene convertito in +2145550100</span><span class="sxs-lookup"><span data-stu-id="183d9-219">12145550100 is translated to +2145550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="183d9-220">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="183d9-220">IntlCallingUS</span></span></p></td>
<td><p><span data-ttu-id="183d9-221">Converte i numeri con prefissi internazionali in numeri degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="183d9-221">Translates numbers with international prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="183d9-222">^ 011 (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="183d9-222">^011(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="183d9-223">+ $1</span><span class="sxs-lookup"><span data-stu-id="183d9-223">+$1</span></span></p></td>
<td><p><span data-ttu-id="183d9-224">01191445550100 viene convertito in +91445550100</span><span class="sxs-lookup"><span data-stu-id="183d9-224">01191445550100 is translated to +91445550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="183d9-225">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="183d9-225">RedmondOperator</span></span></p></td>
<td><p><span data-ttu-id="183d9-226">Converte il numero 0 nel numero dell'operatore di Redmond</span><span class="sxs-lookup"><span data-stu-id="183d9-226">Translates 0 to Redmond Operator</span></span></p></td>
<td><p><span data-ttu-id="183d9-227">^ $0</span><span class="sxs-lookup"><span data-stu-id="183d9-227">^0$</span></span></p></td>
<td><p><span data-ttu-id="183d9-228">+ 14255550100</span><span class="sxs-lookup"><span data-stu-id="183d9-228">+14255550100</span></span></p></td>
<td><p><span data-ttu-id="183d9-229">0 viene convertito in +14255550100</span><span class="sxs-lookup"><span data-stu-id="183d9-229">0 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="183d9-230">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="183d9-230">RedmondSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="183d9-231">Converte i numeri con prefisso on-net (6) e il codice sito di Redmond (222)</span><span class="sxs-lookup"><span data-stu-id="183d9-231">Translates numbers with on-net prefix (6) and Redmond site code (222)</span></span></p></td>
<td><p><span data-ttu-id="183d9-232">^ 6222 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="183d9-232">^6222(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="183d9-233">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="183d9-233">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="183d9-234">62220100 viene convertito in +14255550100</span><span class="sxs-lookup"><span data-stu-id="183d9-234">62220100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="183d9-235">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="183d9-235">NYSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="183d9-236">Converte i numeri con prefisso on-net (6) e il codice sito di NY (333)</span><span class="sxs-lookup"><span data-stu-id="183d9-236">Translates numbers with on-net prefix (6) and NY site code (333)</span></span></p></td>
<td><p><span data-ttu-id="183d9-237">^ 6333 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="183d9-237">^6333(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="183d9-238">+ 1202555 $1</span><span class="sxs-lookup"><span data-stu-id="183d9-238">+1202555$1</span></span></p></td>
<td><p><span data-ttu-id="183d9-239">63330100 viene convertito in +12025550100</span><span class="sxs-lookup"><span data-stu-id="183d9-239">63330100 is translated to +12025550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="183d9-240">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="183d9-240">DallasSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="183d9-241">Converte i numeri con prefisso on-net (6) e il codice sito di Dallas (444)</span><span class="sxs-lookup"><span data-stu-id="183d9-241">Translates numbers with on-net prefix (6) and Dallas site code (444)</span></span></p></td>
<td><p><span data-ttu-id="183d9-242">^ 6444 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="183d9-242">^6444(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="183d9-243">+ 1972555 $1</span><span class="sxs-lookup"><span data-stu-id="183d9-243">+1972555$1</span></span></p></td>
<td><p><span data-ttu-id="183d9-244">64440100 viene convertito in +19725550100</span><span class="sxs-lookup"><span data-stu-id="183d9-244">64440100 is translated to +19725550100</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="183d9-245">Nella tabella seguente viene illustrato un esempio di dial plan per Redmond, Washington, Stati Uniti, in base alle regole di normalizzazione riportate nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="183d9-245">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a><span data-ttu-id="183d9-p117">Tabella 2. Dial plan di Redmond basato sulle regole di normalizzazione riportate nella tabella 1</span><span class="sxs-lookup"><span data-stu-id="183d9-p117">Table 2. Redmond Dial Plan Based on Normalization Rules Shown in Table 1</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="183d9-248">Redmond. FQDNforesta</span><span class="sxs-lookup"><span data-stu-id="183d9-248">Redmond.forestFQDN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="183d9-249">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="183d9-249">5digitExtension</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="183d9-250">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="183d9-250">7digitcallingRedmond</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="183d9-251">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="183d9-251">10digitcallingUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="183d9-252">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="183d9-252">IntlCallingUS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="183d9-253">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="183d9-253">RedmondSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="183d9-254">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="183d9-254">NYSitePrefix</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="183d9-255">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="183d9-255">DallasSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="183d9-256">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="183d9-256">RedmondOperator</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="183d9-p118">I nomi delle regole di normalizzazione illustrate nella tabella precedente non includono spazi, ma si tratta di una scelta. Il primo nome della tabella, ad esempio, potrebbe essere "5 digit extension" o "5-digit Extension" ed essere comunque valido.</span><span class="sxs-lookup"><span data-stu-id="183d9-p118">The normalization rules names shown in the preceding table do not include spaces, but this is a matter of choice. The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

