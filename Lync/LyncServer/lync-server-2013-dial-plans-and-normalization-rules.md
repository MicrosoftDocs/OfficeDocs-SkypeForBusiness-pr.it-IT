---
title: 'Lync Server 2013: dial plan e regole di normalizzazione'
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
ms.openlocfilehash: d4f1cc8221281502487a8f58e1562674432ea29d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="1babe-102">Dial plan e regole di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1babe-102">Dial plans and normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1babe-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="1babe-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="1babe-104">Un dial plan è un set denominato di regole di normalizzazione che converte i numeri di telefono per una posizione denominata, un singolo utente o un oggetto contatto in un unico formato standard (E. 164) per scopi di autorizzazione del telefono e routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="1babe-104">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span>

<span data-ttu-id="1babe-105">Le regole di normalizzazione definiscono il modo in cui i numeri di telefono espressi in diversi formati devono essere instradati per ogni posizione, utente o oggetto contatto specificato.</span><span class="sxs-lookup"><span data-stu-id="1babe-105">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span> <span data-ttu-id="1babe-106">La stessa stringa di chiamata può essere interpretata e tradotta in modo diverso, a seconda della posizione in cui viene chiamata e della persona o dell'oggetto contatto che effettua la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1babe-106">The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object making the call.</span></span>

<div>

## <a name="dial-plan-scope"></a><span data-ttu-id="1babe-107">Ambito di dial plan</span><span class="sxs-lookup"><span data-stu-id="1babe-107">Dial Plan Scope</span></span>

<span data-ttu-id="1babe-108">L' *ambito* di un dial plan determina il livello gerarchico in cui è possibile applicare il dial plan.</span><span class="sxs-lookup"><span data-stu-id="1babe-108">A dial plan’s *scope* determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="1babe-109">In Lync Server a un utente può essere assegnato un dial plan specifico per utente.</span><span class="sxs-lookup"><span data-stu-id="1babe-109">In Lync Server, a user can be assigned a specific per-user dial plan.</span></span> <span data-ttu-id="1babe-110">Se non è stato assegnato un piano di chiamata, viene applicato il piano di chiamata del pool di registrar.</span><span class="sxs-lookup"><span data-stu-id="1babe-110">If a user dial plan is not assigned, the Registrar pool dial plan is applied.</span></span> <span data-ttu-id="1babe-111">Se non è presente un piano di chiamata per pool di registrar, viene applicato il dial plan del sito.</span><span class="sxs-lookup"><span data-stu-id="1babe-111">If there is no Registrar pool dial plan, the site dial plan is applied.</span></span> <span data-ttu-id="1babe-112">Infine, se non è disponibile un altro dial plan per l'utente, viene applicato il dial plan globale.</span><span class="sxs-lookup"><span data-stu-id="1babe-112">Finally, if there is no other dial plan applicable to the user, the global dial plan is applied.</span></span>

<span data-ttu-id="1babe-113">I client ottengono i livelli di ambito dei dial plan tramite le impostazioni di provisioning in banda fornite quando gli utenti accedono a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1babe-113">Clients obtain dial plan scope levels through in-band provisioning settings that are provided when users log on to Lync Server.</span></span> <span data-ttu-id="1babe-114">L'amministratore può gestire e assegnare livelli di ambito di dial plan tramite il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1babe-114">As the administrator, you can manage and assign dial plan scope levels by using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1babe-115">Il dial plan di gateway PSTN (Public Switched Telephone Network) a livello di servizio viene applicato alle chiamate in arrivo da un determinato gateway.</span><span class="sxs-lookup"><span data-stu-id="1babe-115">The service level public switched telephone network (PSTN) gateway dial plan is applied to the incoming calls from a particular gateway.</span></span>



</div>

<span data-ttu-id="1babe-116">I livelli di ambito dei dial plan sono definiti come segue:</span><span class="sxs-lookup"><span data-stu-id="1babe-116">Dial plan scope levels are defined as follows:</span></span>

  - <span data-ttu-id="1babe-117">**Dial plan utente:** Possono essere assegnati a singoli utenti, gruppi o oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="1babe-117">**User dial plan:** Can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="1babe-118">Le applicazioni vocali possono cercare un dial plan per utente quando viene ricevuta una chiamata con il set di impostazioni del telefono-impostazione predefinita per l'utente.</span><span class="sxs-lookup"><span data-stu-id="1babe-118">Voice applications can look up a per-user dial plan when a call is received with the phone-context set to user-default.</span></span> <span data-ttu-id="1babe-119">Ai fini dell'assegnazione di un dial plan, un oggetto contatto viene considerato come singolo utente.</span><span class="sxs-lookup"><span data-stu-id="1babe-119">For the purpose of assigning a dial plan, a contact object is treated as an individual user.</span></span>

  - <span data-ttu-id="1babe-120">**Dial plan per pool:** Può essere creato a livello di servizio per qualsiasi gateway o registrar PSTN nella topologia.</span><span class="sxs-lookup"><span data-stu-id="1babe-120">**Pool dial plan:** Can be created at the service level for any PSTN gateway or Registrar in your topology.</span></span> <span data-ttu-id="1babe-121">Per definire un dial plan per pool, è necessario specificare il servizio specifico (gateway PSTN o pool di registrar) a cui si applica il dial plan.</span><span class="sxs-lookup"><span data-stu-id="1babe-121">To define a pool dial plan, you must specify the particular service (PSTN gateway or Registrar pool) to which the dial plan applies.</span></span>

  - <span data-ttu-id="1babe-122">**Dial plan di sito:** Può essere creato per un intero sito, fatta eccezione per gli utenti, i gruppi o gli oggetti contatto assegnati a un dial plan per pool o a un dial plan utente.</span><span class="sxs-lookup"><span data-stu-id="1babe-122">**Site dial plan:** Can be created for an entire site, except for any users, groups, or contact objects that are assigned a pool dial plan or user dial plan.</span></span> <span data-ttu-id="1babe-123">Per definire un dial plan di sito, è necessario specificare il sito a cui si applica il dial plan.</span><span class="sxs-lookup"><span data-stu-id="1babe-123">To define a site dial plan, you must specify the site to which the dial plan applies.</span></span>

  - <span data-ttu-id="1babe-124">**Dial plan globale:** Il dial plan predefinito installato con il prodotto.</span><span class="sxs-lookup"><span data-stu-id="1babe-124">**Global dial plan:** The default dial plan installed with the product.</span></span> <span data-ttu-id="1babe-125">È possibile modificare il dial plan globale, ma non è possibile eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="1babe-125">You can edit the global dial plan, but you cannot delete it.</span></span> <span data-ttu-id="1babe-126">Questo dial plan si applica a tutti gli utenti di VoIP aziendale, ai gruppi e agli oggetti contatto nella distribuzione, a meno che non si configuri e assegni un dial plan con un ambito più specifico.</span><span class="sxs-lookup"><span data-stu-id="1babe-126">This dial plan applies to all Enterprise Voice users, groups, and contact objects in your deployment, unless you configure and assign a dial plan with a more specific scope.</span></span>

</div>

<div>

## <a name="planning-for-dial-plans"></a><span data-ttu-id="1babe-127">Pianificazione per i dial plan</span><span class="sxs-lookup"><span data-stu-id="1babe-127">Planning for Dial Plans</span></span>

<span data-ttu-id="1babe-128">Per pianificare un dial plan, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1babe-128">To plan a dial plan, follow these steps:</span></span>

  - <span data-ttu-id="1babe-129">Elencare tutte le impostazioni locali in cui l'organizzazione ha un ufficio.</span><span class="sxs-lookup"><span data-stu-id="1babe-129">List all the locales in which your organization has an office.</span></span>
    
    <span data-ttu-id="1babe-130">L'elenco deve essere aggiornato e completo.</span><span class="sxs-lookup"><span data-stu-id="1babe-130">The list must be up-to-date and complete.</span></span> <span data-ttu-id="1babe-131">Sarà necessario rivedere l'evoluzione dell'organizzazione aziendale.</span><span class="sxs-lookup"><span data-stu-id="1babe-131">It will need to be revised as company organization evolves.</span></span> <span data-ttu-id="1babe-132">In un'azienda di grandi dimensioni multinazionali con numerose piccole filiali, può essere un'attività che richiede tempo.</span><span class="sxs-lookup"><span data-stu-id="1babe-132">In a large, multinational company with numerous small branch offices, this can be a time-consuming task.</span></span>

  - <span data-ttu-id="1babe-133">Identificare i modelli di numero validi per ogni sito.</span><span class="sxs-lookup"><span data-stu-id="1babe-133">Identify valid number patterns for each site.</span></span>
    
    <span data-ttu-id="1babe-134">La parte più lunga della pianificazione dei dial plan sta identificando i modelli di numero validi per ogni sito.</span><span class="sxs-lookup"><span data-stu-id="1babe-134">The most time-consuming part of planning your dial plans is identifying the valid number patterns for each site.</span></span> <span data-ttu-id="1babe-135">In alcuni casi, è possibile copiare le regole di normalizzazione scritte per un dial plan ad altri piani di chiamata, in particolare se i siti corrispondenti si trovano all'interno dello stesso paese/area geografica o addirittura in un continente.</span><span class="sxs-lookup"><span data-stu-id="1babe-135">In some cases, you may be able to copy normalization rules that you have written for one dial plan to other dial plans, especially if the corresponding sites are within the same country/region or even continent.</span></span> <span data-ttu-id="1babe-136">In altri casi, le piccole modifiche ai numeri in un dial plan possono essere sufficienti per usarle in altri piani di chiamata.</span><span class="sxs-lookup"><span data-stu-id="1babe-136">In other cases, small changes to numbers in one dial plan may be enough to use them in other dial plans.</span></span>

  - <span data-ttu-id="1babe-137">Sviluppare uno schema a livello di organizzazione per la denominazione dei dial plan.</span><span class="sxs-lookup"><span data-stu-id="1babe-137">Develop an organization-wide scheme for naming dial plans.</span></span>
    
    <span data-ttu-id="1babe-138">L'adozione di uno schema di denominazione standard assicura la coerenza in tutta l'organizzazione e rende più semplici la manutenzione e gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="1babe-138">Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>

  - <span data-ttu-id="1babe-139">Decidere se è necessario disporre di più piani di chiamata per una singola posizione.</span><span class="sxs-lookup"><span data-stu-id="1babe-139">Decide whether multiple dial plans are required for a single location.</span></span>
    
    <span data-ttu-id="1babe-140">Se l'organizzazione mantiene un singolo dial plan in più posizioni, potrebbe essere comunque necessario creare un dial plan separato per gli utenti di VoIP aziendale che eseguono la migrazione da un PBX (Private Branch Exchange) e che devono mantenere le proprie estensioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="1babe-140">If your organization maintains a single dial plan across multiple locations, you may still need to create a separate dial plan for Enterprise Voice users who are migrating from a private branch exchange (PBX) and who need to have their existing extensions retained.</span></span>

  - <span data-ttu-id="1babe-141">Decidere se i piani di chiamata per utente sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="1babe-141">Decide whether per-user dial plans are required.</span></span> <span data-ttu-id="1babe-142">Se ad esempio sono presenti utenti in un sito di succursale registrati con il sito centrale o se si hanno utenti registrati in un Survivable Branch Appliance, è possibile prendere in considerazione scenari di Dialing speciali per tali utenti che usano i piani di chiamata per utente e le regole di normalizzazione .</span><span class="sxs-lookup"><span data-stu-id="1babe-142">For example, if you have users at a branch site who are registered with the central site or if you have users who are registered on a Survivable Branch Appliance, you can consider special dialing scenarios for such users using per-user dial plans and normalization rules.</span></span> <span data-ttu-id="1babe-143">Per informazioni dettagliate, vedere [requisiti di resilienza dei siti secondari per Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1babe-143">For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span></span>

  - <span data-ttu-id="1babe-144">Determinare l'ambito di dial plan (come descritto in precedenza in questo argomento).</span><span class="sxs-lookup"><span data-stu-id="1babe-144">Determine dial plan scope (as previously described in this topic).</span></span>

<span data-ttu-id="1babe-145">Per creare un dial plan, specificare i valori nei campi seguenti, in base alle esigenze, usando il pannello di controllo di Lync Server o Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1babe-145">To create a dial plan, you specify values in the following fields, as required, by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="name-and-simple-name"></a><span data-ttu-id="1babe-146">Nome e nome semplice</span><span class="sxs-lookup"><span data-stu-id="1babe-146">Name and Simple Name</span></span>

<span data-ttu-id="1babe-147">Per i piani di chiamata utente, devi specificare un nome descrittivo che identifichi gli utenti, i gruppi o gli oggetti contatto a cui verrà assegnato il dial plan.</span><span class="sxs-lookup"><span data-stu-id="1babe-147">For user dial plans, you should specify a descriptive name that identifies the users, groups, or contact objects to which the dial plan will be assigned.</span></span> <span data-ttu-id="1babe-148">Per i piani di chiamata del sito, il campo nome viene precompilato con il nome del sito e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="1babe-148">For site dial plans, the Name field is prepopulated with the site name and cannot be changed.</span></span> <span data-ttu-id="1babe-149">Per i piani di chiamata in pool, il campo nome viene prepopolato con il gateway PSTN o con il nome di dominio completo (FQDN) del pool Front end e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="1babe-149">For pool dial plans, the Name field is prepopulated with the PSTN gateway or Front End pool fully qualified domain name (FQDN) and cannot be changed.</span></span>

<span data-ttu-id="1babe-150">Il *nome semplice* dial plan viene precompilato con una stringa derivata dal nome del dial plan.</span><span class="sxs-lookup"><span data-stu-id="1babe-150">The dial plan *Simple Name* is prepopulated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="1babe-151">Il campo Nome semplice è modificabile, per creare una convenzione di denominazione più descrittiva per i piani di chiamata.</span><span class="sxs-lookup"><span data-stu-id="1babe-151">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="1babe-152">Il valore *nome semplice* non può essere vuoto e deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="1babe-152">The *Simple Name* value cannot be empty and must be unique.</span></span> <span data-ttu-id="1babe-153">L'approccio ideale è sviluppare una convenzione di denominazione per l'intera organizzazione e quindi utilizzare questa convenzione in modo coerente in tutte le sedi e per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1babe-153">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

</div>

<div>

## <a name="description"></a><span data-ttu-id="1babe-154">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1babe-154">Description</span></span>

<span data-ttu-id="1babe-155">È consigliabile digitare il nome comune e riconoscibile della posizione geografica in cui si applica il piano di chiamata corrispondente.</span><span class="sxs-lookup"><span data-stu-id="1babe-155">We recommend that you type the common, recognizable name of the geographic location to which the corresponding dial plan applies.</span></span> <span data-ttu-id="1babe-156">Ad esempio, se il nome del dial plan è London.Contoso.com, la descrizione consigliata sarà Londra.</span><span class="sxs-lookup"><span data-stu-id="1babe-156">For example, if the dial plan name is London.Contoso.com, the recommended description would be London.</span></span>

</div>

<div>

## <a name="dial-in-conferencing-region"></a><span data-ttu-id="1babe-157">Area servizi di conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="1babe-157">Dial-in Conferencing Region</span></span>

<span data-ttu-id="1babe-158">Se si distribuiscono i servizi di conferenza telefonica con accesso esterno, è necessario specificare un'area per i servizi di conferenza telefonica con chiamata in ingresso per associare i numeri per i servizi di conferenza telefonica con dial plan.</span><span class="sxs-lookup"><span data-stu-id="1babe-158">If you are deploying dial-in conferencing, you will need to specify a dial-in conferencing region to associate dial-in conferencing access numbers with a dial plan.</span></span>

</div>

<div>

## <a name="external-access-prefix"></a><span data-ttu-id="1babe-159">Prefisso di accesso esterno</span><span class="sxs-lookup"><span data-stu-id="1babe-159">External Access Prefix</span></span>

<span data-ttu-id="1babe-160">Se gli utenti devono chiamare una o più cifre iniziali aggiuntive (ad\#esempio \*9) per ottenere una linea esterna, è possibile specificare un prefisso di accesso esterno composto da un massimo di quattro caratteri (e 0-9).</span><span class="sxs-lookup"><span data-stu-id="1babe-160">You can specify an external access prefix of up to four characters (\#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1babe-161">Se si specifica un prefisso di accesso esterno, non è necessario creare una regola di normalizzazione aggiuntiva per includere il prefisso.</span><span class="sxs-lookup"><span data-stu-id="1babe-161">If you specify an external access prefix, you do not need to create an additional normalization rule to accommodate the prefix.</span></span>



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a><span data-ttu-id="1babe-162">Regole di normalizzazione</span><span class="sxs-lookup"><span data-stu-id="1babe-162">Normalization Rules</span></span>

<span data-ttu-id="1babe-163">Le regole di normalizzazione definiscono il modo in cui i numeri di telefono espressi in diversi formati devono essere instradati per la posizione denominata.</span><span class="sxs-lookup"><span data-stu-id="1babe-163">Normalization rules define how phone numbers expressed in various formats are to be routed for the named location.</span></span> <span data-ttu-id="1babe-164">La stessa stringa numerica può essere interpretata e tradotta in modo diverso, a seconda della posizione da cui viene composta.</span><span class="sxs-lookup"><span data-stu-id="1babe-164">The same number string may be interpreted and translated differently, depending on the locale from which it is dialed.</span></span> <span data-ttu-id="1babe-165">Le regole di normalizzazione sono necessarie per il routing delle chiamate perché gli utenti possono usare vari formati per l'immissione di numeri di telefono nei rispettivi elenchi di contatti.</span><span class="sxs-lookup"><span data-stu-id="1babe-165">Normalization rules are necessary for call routing because users can, and do, use various formats when entering phone numbers in their Contacts lists.</span></span>

<span data-ttu-id="1babe-166">La normalizzazione dei numeri di telefono forniti dall'utente fornisce un formato coerente che facilita le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="1babe-166">Normalizing user-supplied phone numbers provides a consistent format that facilitates the following tasks:</span></span>

  - <span data-ttu-id="1babe-167">Corrisponde a un numero composto al SIP-URI del destinatario previsto.</span><span class="sxs-lookup"><span data-stu-id="1babe-167">Match a dialed number to the intended recipient’s SIP-URI.</span></span>

  - <span data-ttu-id="1babe-168">Applicare le regole di autorizzazione di chiamata alla parte chiamante.</span><span class="sxs-lookup"><span data-stu-id="1babe-168">Apply dialing authorization rules to the calling party.</span></span>

<span data-ttu-id="1babe-169">I campi numero seguenti sono tra quelli che potrebbero essere necessari per le regole di normalizzazione:</span><span class="sxs-lookup"><span data-stu-id="1babe-169">The following number fields are among those that your normalization rules may need to account for:</span></span>

  - <span data-ttu-id="1babe-170">Dial plan</span><span class="sxs-lookup"><span data-stu-id="1babe-170">Dial plan</span></span>

  - <span data-ttu-id="1babe-171">Codice paese</span><span class="sxs-lookup"><span data-stu-id="1babe-171">Country code</span></span>

  - <span data-ttu-id="1babe-172">Prefisso</span><span class="sxs-lookup"><span data-stu-id="1babe-172">Area code</span></span>

  - <span data-ttu-id="1babe-173">Lunghezza dell'estensione</span><span class="sxs-lookup"><span data-stu-id="1babe-173">Length of extension</span></span>

  - <span data-ttu-id="1babe-174">Prefisso del sito</span><span class="sxs-lookup"><span data-stu-id="1babe-174">Site prefix</span></span>

<div>

## <a name="creating-normalization-rules"></a><span data-ttu-id="1babe-175">Creazione di regole di normalizzazione</span><span class="sxs-lookup"><span data-stu-id="1babe-175">Creating Normalization Rules</span></span>

<span data-ttu-id="1babe-176">Le regole di normalizzazione usano le espressioni regolari .NET Framework per specificare modelli numerici di abbinamento che il server utilizza per tradurre le stringhe di composizione in formato E.164 allo scopo di eseguire la ricerca inversa.</span><span class="sxs-lookup"><span data-stu-id="1babe-176">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup.</span></span> <span data-ttu-id="1babe-177">È possibile creare regole di normalizzazione nel pannello di controllo di Lync Server immettendo le espressioni manualmente oppure immettendo le cifre iniziali e la lunghezza delle stringhe di chiamata da corrispondere e lasciando che il pannello di controllo di Lync Server generi il corrispondente espressione regolare per l'utente.</span><span class="sxs-lookup"><span data-stu-id="1babe-177">You create normalization rules in the Lync Server Control Panel either by entering the expressions manually, or by entering the starting digits and the length of the dial strings to be matched and letting the Lync Server Control Panel generate the corresponding regular expression for you.</span></span> <span data-ttu-id="1babe-178">In entrambi i casi, al termine, è possibile immettere un numero di test per verificare che la regola di normalizzazione funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="1babe-178">Either way, when you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="1babe-179">Per informazioni dettagliate sull'uso delle espressioni regolari di .NET Framework, vedere "espressioni regolari di [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).NET Framework".</span><span class="sxs-lookup"><span data-stu-id="1babe-179">For details about using .NET Framework regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a><span data-ttu-id="1babe-180">Esempio di regole di normalizzazione</span><span class="sxs-lookup"><span data-stu-id="1babe-180">Sample Normalization Rules</span></span>

<span data-ttu-id="1babe-p116">La tabella seguente mostra esempi di regole di normalizzazione scritte sotto forma di espressioni regolari .NET Framework. Si tratta solo di esempi, non di regole fisse di riferimento per la creazione di regole di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="1babe-p116">The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a><span data-ttu-id="1babe-183">Tabella 1. regole di normalizzazione con le espressioni regolari di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1babe-183">Table 1.Normalization Rules Using .NET Framework Regular Expressions</span></span>

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
<th><span data-ttu-id="1babe-184">Nome regola</span><span class="sxs-lookup"><span data-stu-id="1babe-184">Rule name</span></span></th>
<th><span data-ttu-id="1babe-185">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1babe-185">Description</span></span></th>
<th><span data-ttu-id="1babe-186">Schema numerico</span><span class="sxs-lookup"><span data-stu-id="1babe-186">Number pattern</span></span></th>
<th><span data-ttu-id="1babe-187">Conversione</span><span class="sxs-lookup"><span data-stu-id="1babe-187">Translation</span></span></th>
<th><span data-ttu-id="1babe-188">Esempio</span><span class="sxs-lookup"><span data-stu-id="1babe-188">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1babe-189">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="1babe-189">4digitExtension</span></span></p></td>
<td><p><span data-ttu-id="1babe-190">Converte le estensioni a 4 cifre</span><span class="sxs-lookup"><span data-stu-id="1babe-190">Translates 4-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="1babe-191">^ (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="1babe-191">^(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="1babe-192">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="1babe-192">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="1babe-193">0100 viene convertito in +14255550100</span><span class="sxs-lookup"><span data-stu-id="1babe-193">0100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1babe-194">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="1babe-194">5digitExtension</span></span></p></td>
<td><p><span data-ttu-id="1babe-195">Converte le estensioni a 5 cifre</span><span class="sxs-lookup"><span data-stu-id="1babe-195">Translates 5-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="1babe-196">^ 5 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="1babe-196">^5(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="1babe-197">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="1babe-197">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="1babe-198">50100 viene convertito in +14255550100</span><span class="sxs-lookup"><span data-stu-id="1babe-198">50100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1babe-199">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="1babe-199">7digitcallingRedmond</span></span></p></td>
<td><p><span data-ttu-id="1babe-200">Converte i numeri a 7 cifre in numeri locali di Redmond</span><span class="sxs-lookup"><span data-stu-id="1babe-200">Translates 7-digit numbers to Redmond local numbers</span></span></p></td>
<td><p><span data-ttu-id="1babe-201">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="1babe-201">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="1babe-202">+1425$1</span><span class="sxs-lookup"><span data-stu-id="1babe-202">+1425$1</span></span></p></td>
<td><p><span data-ttu-id="1babe-203">5550100 viene convertito in +14255550100</span><span class="sxs-lookup"><span data-stu-id="1babe-203">5550100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1babe-204">7digitcallingDallas</span><span class="sxs-lookup"><span data-stu-id="1babe-204">7digitcallingDallas</span></span></p></td>
<td><p><span data-ttu-id="1babe-205">Converte i numeri a 7 cifre in numeri locali di Dallas</span><span class="sxs-lookup"><span data-stu-id="1babe-205">Translates 7-digit numbers to Dallas local numbers</span></span></p></td>
<td><p><span data-ttu-id="1babe-206">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="1babe-206">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="1babe-207">+ 1972 $1</span><span class="sxs-lookup"><span data-stu-id="1babe-207">+1972$1</span></span></p></td>
<td><p><span data-ttu-id="1babe-208">5550100 viene convertito in + 19725550100</span><span class="sxs-lookup"><span data-stu-id="1babe-208">5550100 is translated to +19725550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1babe-209">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="1babe-209">10digitcallingUS</span></span></p></td>
<td><p><span data-ttu-id="1babe-210">Converte i numeri a 10 cifre negli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="1babe-210">Translates 10-digit numbers in the United States</span></span></p></td>
<td><p><span data-ttu-id="1babe-211">^ (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="1babe-211">^(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="1babe-212">+ 1 $1</span><span class="sxs-lookup"><span data-stu-id="1babe-212">+1$1</span></span></p></td>
<td><p><span data-ttu-id="1babe-213">2065550100 viene convertito in + 12065550100</span><span class="sxs-lookup"><span data-stu-id="1babe-213">2065550100 is translated to +12065550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1babe-214">LDCallingUS</span><span class="sxs-lookup"><span data-stu-id="1babe-214">LDCallingUS</span></span></p></td>
<td><p><span data-ttu-id="1babe-215">Converte i numeri con i prefissi a lunga distanza negli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="1babe-215">Translates numbers with long distance prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="1babe-216">^ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="1babe-216">^1(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="1babe-217">+ $1</span><span class="sxs-lookup"><span data-stu-id="1babe-217">+$1</span></span></p></td>
<td><p><span data-ttu-id="1babe-218">12145550100 viene convertito in + 2145550100</span><span class="sxs-lookup"><span data-stu-id="1babe-218">12145550100 is translated to +2145550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1babe-219">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="1babe-219">IntlCallingUS</span></span></p></td>
<td><p><span data-ttu-id="1babe-220">Converte i numeri con i prefissi internazionali negli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="1babe-220">Translates numbers with international prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="1babe-221">^ 011 (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="1babe-221">^011(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="1babe-222">+ $1</span><span class="sxs-lookup"><span data-stu-id="1babe-222">+$1</span></span></p></td>
<td><p><span data-ttu-id="1babe-223">01191445550100 viene convertito in + 91445550100</span><span class="sxs-lookup"><span data-stu-id="1babe-223">01191445550100 is translated to +91445550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1babe-224">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="1babe-224">RedmondOperator</span></span></p></td>
<td><p><span data-ttu-id="1babe-225">Converte 0 in operatore Redmond</span><span class="sxs-lookup"><span data-stu-id="1babe-225">Translates 0 to Redmond Operator</span></span></p></td>
<td><p><span data-ttu-id="1babe-226">^0$</span><span class="sxs-lookup"><span data-stu-id="1babe-226">^0$</span></span></p></td>
<td><p><span data-ttu-id="1babe-227">+14255550100</span><span class="sxs-lookup"><span data-stu-id="1babe-227">+14255550100</span></span></p></td>
<td><p><span data-ttu-id="1babe-228">0 viene convertito in +14255550100</span><span class="sxs-lookup"><span data-stu-id="1babe-228">0 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1babe-229">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="1babe-229">RedmondSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="1babe-230">Converte i numeri con il prefisso on-net (6) e il codice del sito Redmond (222)</span><span class="sxs-lookup"><span data-stu-id="1babe-230">Translates numbers with on-net prefix (6) and Redmond site code (222)</span></span></p></td>
<td><p><span data-ttu-id="1babe-231">^ 6222 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="1babe-231">^6222(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="1babe-232">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="1babe-232">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="1babe-233">62220100 viene convertito in +14255550100</span><span class="sxs-lookup"><span data-stu-id="1babe-233">62220100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1babe-234">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="1babe-234">NYSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="1babe-235">Converte i numeri con il prefisso on-net (6) e il codice del sito NY (333)</span><span class="sxs-lookup"><span data-stu-id="1babe-235">Translates numbers with on-net prefix (6) and NY site code (333)</span></span></p></td>
<td><p><span data-ttu-id="1babe-236">^ 6333 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="1babe-236">^6333(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="1babe-237">+ 1202555 $1</span><span class="sxs-lookup"><span data-stu-id="1babe-237">+1202555$1</span></span></p></td>
<td><p><span data-ttu-id="1babe-238">63330100 viene convertito in + 12025550100</span><span class="sxs-lookup"><span data-stu-id="1babe-238">63330100 is translated to +12025550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1babe-239">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="1babe-239">DallasSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="1babe-240">Converte i numeri con il prefisso on-net (6) e il codice del sito di Dallas (444)</span><span class="sxs-lookup"><span data-stu-id="1babe-240">Translates numbers with on-net prefix (6) and Dallas site code (444)</span></span></p></td>
<td><p><span data-ttu-id="1babe-241">^ 6444 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="1babe-241">^6444(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="1babe-242">+ 1972555 $1</span><span class="sxs-lookup"><span data-stu-id="1babe-242">+1972555$1</span></span></p></td>
<td><p><span data-ttu-id="1babe-243">64440100 viene convertito in + 19725550100</span><span class="sxs-lookup"><span data-stu-id="1babe-243">64440100 is translated to +19725550100</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1babe-244">La tabella seguente illustra un piano di chiamata di esempio per Redmond, Washington, Stati Uniti, in base alle regole di normalizzazione indicate nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="1babe-244">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a><span data-ttu-id="1babe-245">Tabella 2.</span><span class="sxs-lookup"><span data-stu-id="1babe-245">Table 2.</span></span> <span data-ttu-id="1babe-246">Dial plan Redmond basato sulle regole di normalizzazione visualizzate nella tabella 1</span><span class="sxs-lookup"><span data-stu-id="1babe-246">Redmond Dial Plan Based on Normalization Rules Shown in Table 1</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1babe-247">Redmond. FQDNforesta</span><span class="sxs-lookup"><span data-stu-id="1babe-247">Redmond.forestFQDN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1babe-248">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="1babe-248">5digitExtension</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1babe-249">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="1babe-249">7digitcallingRedmond</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1babe-250">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="1babe-250">10digitcallingUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1babe-251">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="1babe-251">IntlCallingUS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1babe-252">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="1babe-252">RedmondSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1babe-253">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="1babe-253">NYSitePrefix</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1babe-254">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="1babe-254">DallasSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1babe-255">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="1babe-255">RedmondOperator</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="1babe-p118">I nomi delle regole di normalizzazione mostrati nella tabella precedente non includono spazi, ma questa è solo una scelta. Il primo nome nella tabella, ad esempio, avrebbe potuto essere "5 digit extension" o "5-digit Extension" e sarebbe stato comunque valido.</span><span class="sxs-lookup"><span data-stu-id="1babe-p118">The normalization rules names shown in the preceding table do not include spaces, but this is a matter of choice. The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

