---
title: 'Lync Server 2013: Spostamento di utenti in VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e92f0a7d71d42d8551a51028afec209e795941d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="2287d-102">Spostamento di utenti in VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2287d-102">Moving users to Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2287d-103">_**Argomento Ultima modifica:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="2287d-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="2287d-104">Se si stanno spostando gli utenti da un'infrastruttura di telefonia PBX esistente a VoIP aziendale, il processo di distribuzione include alcuni passaggi che non fanno parte del processo di pianificazione già descritto in [pianificazione di VoIP aziendale in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="2287d-104">If you are moving users from an existing PBX telephony infrastructure to Enterprise Voice, the deployment process includes some steps that are not part of the planning process already described in [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span></span> <span data-ttu-id="2287d-105">Per informazioni sulla migrazione degli utenti da una distribuzione di VoIP aziendale precedente, vedere i documenti di migrazione inclusi nel supporto di installazione.</span><span class="sxs-lookup"><span data-stu-id="2287d-105">For information about migrating users from an earlier Enterprise Voice deployment, see the migration documents that were included with your installation media.</span></span>

<span data-ttu-id="2287d-106">Il processo di spostamento degli utenti da un'infrastruttura di telefonia esistente a VoIP aziendale è costituito dai passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2287d-106">The process of moving users from an existing telephony infrastructure to Enterprise Voice consists of the following steps:</span></span>

1.  <span data-ttu-id="2287d-107">Designare i numeri di telefono primari.</span><span class="sxs-lookup"><span data-stu-id="2287d-107">Designate primary phone numbers.</span></span>

2.  <span data-ttu-id="2287d-108">Consentire agli utenti di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="2287d-108">Enable users for Enterprise Voice.</span></span>

3.  <span data-ttu-id="2287d-109">Preparare i dial plan per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="2287d-109">Prepare dial plans for users.</span></span>

4.  <span data-ttu-id="2287d-110">Pianificare i criteri vocali per l'utente.</span><span class="sxs-lookup"><span data-stu-id="2287d-110">Plan user voice policies.</span></span>

5.  <span data-ttu-id="2287d-111">Pianificare le route di chiamata.</span><span class="sxs-lookup"><span data-stu-id="2287d-111">Plan call routes.</span></span>

6.  <span data-ttu-id="2287d-112">Configurare PBX o trunk SIP per reindirizzare le chiamate per gli utenti abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="2287d-112">Configure PBX or SIP Trunk to reroute calls for users enabled for Enterprise Voice.</span></span>

7.  <span data-ttu-id="2287d-113">Consente di trasferire gli utenti alla messaggistica unificata di Exchange (scelta consigliata).</span><span class="sxs-lookup"><span data-stu-id="2287d-113">Move users to Exchange Unified Messaging (UM) (recommended).</span></span>

<span data-ttu-id="2287d-114">Questo argomento descrive la pianificazione necessaria per ognuno di questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="2287d-114">This topic describes the planning that is necessary for each of these steps.</span></span>

<div>

## <a name="step-1-designate-primary-phone-numbers"></a><span data-ttu-id="2287d-115">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="2287d-115">Step 1.</span></span> <span data-ttu-id="2287d-116">Designare i numeri di telefono primari</span><span class="sxs-lookup"><span data-stu-id="2287d-116">Designate primary phone numbers</span></span>

<span data-ttu-id="2287d-117">Enterprise Voice integra la voce con altri elementi multimediali di messaggistica, in modo che quando una chiamata in arrivo arriva al server, il server esegue il mapping del numero all'URI SIP dell'utente e quindi biforca la chiamata a tutti gli endpoint client associati all'URI SIP.</span><span class="sxs-lookup"><span data-stu-id="2287d-117">Enterprise Voice integrates voice with other messaging media, such that when an incoming call arrives at the server, the server maps the number to the user’s SIP-URI and then forks the call to all the client endpoints associated with that SIP-URI.</span></span> <span data-ttu-id="2287d-118">Questo processo richiede che ogni utente sia associato a un numero di telefono principale.</span><span class="sxs-lookup"><span data-stu-id="2287d-118">This process requires that each user be associated with a primary phone number.</span></span>

<span data-ttu-id="2287d-119">Un numero di telefono principale deve essere:</span><span class="sxs-lookup"><span data-stu-id="2287d-119">A primary phone number must be:</span></span>

  - <span data-ttu-id="2287d-120">Univoco globale o, nel caso di estensioni interne, univoco nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2287d-120">Globally unique or, in the case of internal extensions, unique in the enterprise.</span></span>

  - <span data-ttu-id="2287d-121">Di proprietà e instradabile nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2287d-121">Owned by and routable in the enterprise.</span></span> <span data-ttu-id="2287d-122">I numeri personali non devono essere usati.</span><span class="sxs-lookup"><span data-stu-id="2287d-122">Personal numbers should not be used.</span></span>

<span data-ttu-id="2287d-123">Gli utenti aziendali possono avere due o più numeri di telefono elencati in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2287d-123">Enterprise users can have two or more telephone numbers listed for them in Active Directory Domain Services.</span></span> <span data-ttu-id="2287d-124">Tutti i numeri di telefono associati a un determinato utente possono essere visualizzati o modificati nella finestra delle proprietà dell'utente nello snap-in utenti e computer di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2287d-124">All the telephone numbers associated with a particular user can be viewed or changed on the property sheet for that user in the Active Directory Users and Computers snap-in.</span></span>

<span data-ttu-id="2287d-125">La casella **numero di telefono** nella scheda **generale** della finestra di dialogo **proprietà utente** deve contenere il numero di lavoro principale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2287d-125">The **Telephone number** box on the **General** tab of the **User Properties** dialog box should contain the user’s main work number.</span></span> <span data-ttu-id="2287d-126">Questo numero viene in genere designato come numero di telefono principale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2287d-126">This number will usually be designated as the user's Primary Phone Number.</span></span>

<span data-ttu-id="2287d-127">Alcuni utenti possono avere esigenze particolari (ad esempio, un dirigente che vuole che tutte le chiamate in arrivo vengano instradate tramite un assistente amministrativo), ma queste eccezioni dovrebbero essere limitate solo a quelle in cui il bisogno è chiaro e critico.</span><span class="sxs-lookup"><span data-stu-id="2287d-127">Some users may have special requirements (for example, an executive who wants all incoming calls routed through an administrative assistant), but such exceptions should be limited only to those where the need is clear and critical.</span></span>

<span data-ttu-id="2287d-128">Dopo aver scelto un numero primario, deve essere:</span><span class="sxs-lookup"><span data-stu-id="2287d-128">After a primary number is chosen, it must be:</span></span>

  - <span data-ttu-id="2287d-129">Normalizzato in formato E. 164, ove possibile.</span><span class="sxs-lookup"><span data-stu-id="2287d-129">Normalized to E.164 format, wherever possible.</span></span>

  - <span data-ttu-id="2287d-130">Copiato nell'attributo **msRTCSIP-line** di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2287d-130">Copied to the Active Directory **msRTCSIP-line** attribute.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2287d-131"><STRONG>Coesistenza con il controllo delle chiamate remote (RCC)</STRONG></span><span class="sxs-lookup"><span data-stu-id="2287d-131"><STRONG>Coexisting with remote call control (RCC)</STRONG></span></span><BR><span data-ttu-id="2287d-132">RCC è la possibilità di usare Lync Server per monitorare e controllare un telefono PBX desktop.</span><span class="sxs-lookup"><span data-stu-id="2287d-132">RCC is the ability to use Lync Server to monitor and control a desktop PBX phone.</span></span> <span data-ttu-id="2287d-133">Il controllo viene instradato attraverso il server, che funge da gateway per il PBX.</span><span class="sxs-lookup"><span data-stu-id="2287d-133">Control is routed through the server, which acts as a gateway to the PBX.</span></span> <span data-ttu-id="2287d-134">Anche se non è possibile configurare un utente per le chiamate RCC e VoIP aziendale, l'impostazione URI linea designa il numero di telefono principale di un utente in entrambi i casi.</span><span class="sxs-lookup"><span data-stu-id="2287d-134">Although you cannot configure a user for both RCC and Enterprise Voice, the Line URI setting designates a user’s primary phone number in either case.</span></span><BR><span data-ttu-id="2287d-135">Se si vuole che gli utenti selezionati continuino a usare un'infrastruttura PBX esistente, è possibile introdurre l'opzione VoIP aziendale in modo incrementale nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2287d-135">If you have an existing PBX infrastructure that you want selected users to continue using, you can introduce Enterprise Voice incrementally into your organization.</span></span> <span data-ttu-id="2287d-136">Per informazioni dettagliate su questo scenario di distribuzione, vedere <A href="lync-server-2013-direct-sip-deployment-options.md">Opzioni di distribuzione SIP dirette in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2287d-136">For details about this deployment scenario, see <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP deployment options in Lync Server 2013</A> in the Planning documentation.</span></span><BR><span data-ttu-id="2287d-137">Nelle versioni precedenti è possibile abilitare sia RCC che VoIP aziendale per un utente, ma solo se è stato configurato anche l'utente per il forking duale, una caratteristica in cui una chiamata in arrivo suonerà contemporaneamente il telefono PBX e il Communicator di un utente.</span><span class="sxs-lookup"><span data-stu-id="2287d-137">In previous releases, you could enable both RCC and Enterprise Voice for a user, but only if you also configured the user for dual forking, a feature in which an incoming call will ring a user’s PBX phone and Communicator simultaneously.</span></span> <span data-ttu-id="2287d-138">In Lync Server 2010 la doppia forcella non è supportata.</span><span class="sxs-lookup"><span data-stu-id="2287d-138">In Lync Server 2010, dual-forking is not supported.</span></span>

    
    </div>

<span data-ttu-id="2287d-139">Esistono tre metodi per la compilazione dell'attributo **msRTCSIP-line** :</span><span class="sxs-lookup"><span data-stu-id="2287d-139">There are three methods for populating the **msRTCSIP-line** attribute:</span></span>

  - <span data-ttu-id="2287d-140">Microsoft Identity Integration Server (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="2287d-140">Microsoft Identity Integration Server (recommended)</span></span>

  - <span data-ttu-id="2287d-141">Pagina **utenti** nel pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="2287d-141">The **Users** page in the Lync Server Control Panel</span></span>

<span data-ttu-id="2287d-142">Dove devono essere elaborati molti numeri di telefono, uno script personalizzato sviluppato dall'organizzazione è la scelta migliore.</span><span class="sxs-lookup"><span data-stu-id="2287d-142">Where many phone numbers must be processed, a script custom developed by your organization is the better choice.</span></span> <span data-ttu-id="2287d-143">In base al modo in cui l'organizzazione rappresenta i numeri di telefono in servizi di dominio Active Directory, è possibile che lo script debba normalizzare i numeri di telefono primari in formato E. 164 prima di copiarli nell'attributo **msRTCSIP-line** .</span><span class="sxs-lookup"><span data-stu-id="2287d-143">Depending on how your organization represents telephone numbers in Active Directory Domain Services, the script may have to normalize primary phone numbers to E.164 format before copying them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="2287d-144">Se l'organizzazione mantiene tutti i numeri di telefono in servizi di dominio Active Directory in un unico formato e se tale formato è E. 164, lo script deve solo scrivere ogni numero di telefono principale nell'attributo **msRTCSIP-line** .</span><span class="sxs-lookup"><span data-stu-id="2287d-144">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, and if that format is E.164, your script only needs to write each Primary Telephone Number to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="2287d-145">Se l'organizzazione mantiene tutti i numeri di telefono in servizi di dominio Active Directory in un unico formato, ma tale formato non è E. 164, lo script deve definire una regola di normalizzazione appropriata per convertire i numeri di telefono primari dal formato esistente in E. 164 prima di scriverli nell'attributo **msRTCSIP-line** .</span><span class="sxs-lookup"><span data-stu-id="2287d-145">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, but that format is not E.164, your script should define an appropriate normalization rule to convert Primary Telephone Numbers from their existing format to E.164 before writing them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="2287d-146">Se l'organizzazione non applica un formato standard per i numeri di telefono in servizi di dominio Active Directory, lo script deve definire le regole di normalizzazione appropriate per convertire i numeri di telefono primari dai vari formati in conformità E. 164 prima di scrivere i numeri di telefono primari nell'attributo **msRTCSIP-line** .</span><span class="sxs-lookup"><span data-stu-id="2287d-146">If your organization does not enforce a standard format for telephone numbers in Active Directory Domain Services, your script should define appropriate normalization rules to convert Primary Phone Numbers from their various formats to E.164 compliance before writing the Primary Telephone Numbers to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="2287d-147">Lo script dovrà anche inserire il prefisso **Tel:** prima di ogni numero primario prima di scriverlo nell'attributo **msRTCSIP-line** .</span><span class="sxs-lookup"><span data-stu-id="2287d-147">Your script will also have to insert the prefix **Tel:** before each primary number before writing it to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="2287d-148">Il formato previsto del numero specificato in questo attributo è:</span><span class="sxs-lookup"><span data-stu-id="2287d-148">The expected format of the number specified in this attribute is:</span></span>

  - <span data-ttu-id="2287d-149">Tel: + 14255550100; ext = 50100.</span><span class="sxs-lookup"><span data-stu-id="2287d-149">Tel:+14255550100;ext=50100.</span></span>

  - <span data-ttu-id="2287d-150">Tel: 5550100 (per le estensioni esclusive di Enterprise Wide)</span><span class="sxs-lookup"><span data-stu-id="2287d-150">Tel:5550100 (for unique enterprise wide extensions)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2287d-151">La normalizzazione eseguita dal servizio Rubrica (ABS) non sostituisce o Elimina in altro modo la necessità di normalizzare il numero di telefono principale di ogni utente in servizi di dominio Active Directory, perché ABS non ha accesso a servizi di dominio Active Directory e quindi non può copiare i numeri primari nell'attributo <STRONG>msRTCSIP-line</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="2287d-151">The normalization performed by the Address Book Service (ABS) does not replace or otherwise eliminate the need to normalize each user's primary phone number in Active Directory Domain Services because ABS does not have access to Active Directory Domain Services and therefore cannot copy primary numbers to the <STRONG>msRTCSIP-line</STRONG> attribute.</span></span>

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a><span data-ttu-id="2287d-152">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="2287d-152">Step 2.</span></span> <span data-ttu-id="2287d-153">Abilitare gli utenti per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="2287d-153">Enable users for Enterprise Voice</span></span>

<span data-ttu-id="2287d-154">Oltre a identificare gli utenti che devono essere abilitati, non è necessaria alcuna pianificazione speciale per completare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="2287d-154">Other than identifying which users are to be enabled, no special planning is required to complete this step.</span></span>

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a><span data-ttu-id="2287d-155">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="2287d-155">Step 3.</span></span> <span data-ttu-id="2287d-156">Preparare i dial plan per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="2287d-156">Prepare dial plans for users.</span></span>

<span data-ttu-id="2287d-157">Gli utenti abilitati per VoIP aziendale non saranno in grado di effettuare chiamate alla rete PSTN senza dial plan in posizione.</span><span class="sxs-lookup"><span data-stu-id="2287d-157">Users who are enabled for Enterprise Voice will not be able to make calls to the PSTN without dial plans in place.</span></span> <span data-ttu-id="2287d-158">Un dial plan è un set denominato di regole di normalizzazione che converte i numeri di telefono per una posizione denominata, un singolo utente o un oggetto contatto in un unico formato standard (E. 164) per scopi di autorizzazione del telefono e routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="2287d-158">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="2287d-159">Le regole di normalizzazione definiscono il modo in cui i numeri di telefono espressi in diversi formati devono essere instradati per ogni posizione, utente o oggetto contatto specificato.</span><span class="sxs-lookup"><span data-stu-id="2287d-159">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span>

<span data-ttu-id="2287d-160">Per informazioni sulla preparazione di dial plan, vedere [dial plan e regole di normalizzazione in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="2287d-160">For information about preparing dial plans, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span></span>

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a><span data-ttu-id="2287d-161">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="2287d-161">Step 4.</span></span> <span data-ttu-id="2287d-162">Pianificare i criteri vocali degli utenti</span><span class="sxs-lookup"><span data-stu-id="2287d-162">Plan user voice policies</span></span>

<span data-ttu-id="2287d-163">Le impostazioni di classe del servizio utente in un PBX legacy, ad esempio il diritto di effettuare chiamate interurbane o internazionali da telefoni aziendali, devono essere riconfigurate come criteri VoIP per gli utenti spostati in Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2287d-163">User class-of-service settings on a legacy PBX, such as the right to make long-distance or international calls from company phones, must be reconfigured as VoIP policies for users moved to Enterprise Voice.</span></span> <span data-ttu-id="2287d-164">Per informazioni dettagliate sulla pianificazione e la creazione di criteri per VoIP aziendale, vedere [criteri vocali in Lync Server 2013](lync-server-2013-voice-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2287d-164">For details about planning and creating policies for Enterprise Voice, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md).</span></span>

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a><span data-ttu-id="2287d-165">Passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="2287d-165">Step 5.</span></span> <span data-ttu-id="2287d-166">Pianificare le route delle chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="2287d-166">Plan outbound call routes</span></span>

<span data-ttu-id="2287d-167">Le route di chiamata specificano il modo in cui Lync Server gestisce le chiamate in uscita poste dagli utenti VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="2287d-167">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="2287d-168">Quando un utente compone un numero, il server, se necessario, normalizza la stringa di chiamata in formato e. 164 e tenta di associarla a un URI SIP.</span><span class="sxs-lookup"><span data-stu-id="2287d-168">When a user dials a number, the server, if necessary, normalizes the dial string to E.164 format and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="2287d-169">Se il server non è in grado di eseguire la corrispondenza, applica la logica di routing delle chiamate in uscita in base al numero.</span><span class="sxs-lookup"><span data-stu-id="2287d-169">If the server is unable to make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="2287d-170">Il passaggio finale per definire la logica consiste nel creare una route di chiamata separata denominata per ogni set di numeri di telefono di destinazione elencati in ogni dial plan.</span><span class="sxs-lookup"><span data-stu-id="2287d-170">The final step in defining that logic is creating a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="2287d-171">Per informazioni dettagliate sulla pianificazione delle route di chiamata, vedere [route vocali in Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="2287d-171">For details about planning call routes, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a><span data-ttu-id="2287d-172">Passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="2287d-172">Step 6.</span></span> <span data-ttu-id="2287d-173">Configurare PBX o trunk SIP per reindirizzare le chiamate per gli utenti di VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="2287d-173">Configure PBX or SIP Trunk to reroute calls for Enterprise Voice users</span></span>

<span data-ttu-id="2287d-174">Gli utenti che in precedenza erano ospitati in un PBX tradizionale o in una connessione trunk SIP a un provider di servizi di telefonia Internet (ITSP) mantengono i numeri di telefono dopo lo stato di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="2287d-174">Users who formerly were hosted on a traditional PBX or on a SIP Trunk connection to an Internet Telephony Service Provider (ITSP) retain their phone numbers after the move.</span></span> <span data-ttu-id="2287d-175">L'unico requisito è che dopo lo stato di trasferimento il PBX o il trunk SIP debba essere riconfigurato per instradare le chiamate in arrivo per gli utenti di VoIP aziendale al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="2287d-175">The only requirement is that after the move, the PBX or SIP Trunk must be reconfigured to route incoming calls for Enterprise Voice users to the Mediation Server.</span></span>

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a><span data-ttu-id="2287d-176">Passaggio 7.</span><span class="sxs-lookup"><span data-stu-id="2287d-176">Step 7.</span></span> <span data-ttu-id="2287d-177">Trasferire gli utenti alla messaggistica unificata di Exchange (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="2287d-177">Move users to Exchange Unified Messaging (recommended)</span></span>

<span data-ttu-id="2287d-178">Lo spostamento degli utenti alla messaggistica unificata di Exchange è costituito dalle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="2287d-178">Moving users to Exchange Unified Messaging consists of the following tasks:</span></span>

  - <span data-ttu-id="2287d-179">Configurare la messaggistica unificata di Exchange e il server Lync per collaborare.</span><span class="sxs-lookup"><span data-stu-id="2287d-179">Configure Exchange Unified Messaging and Lync Server to work together.</span></span>

  - <span data-ttu-id="2287d-180">Consentire agli utenti di rispondere alle chiamate di messaggistica unificata di Exchange e Outlook Voice Access.</span><span class="sxs-lookup"><span data-stu-id="2287d-180">Enable users for Exchange Unified Messaging call answering and Outlook Voice Access.</span></span> <span data-ttu-id="2287d-181">Questa attività viene eseguita nel server Messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="2287d-181">This task is performed on the Exchange Unified Messaging server.</span></span> <span data-ttu-id="2287d-182">Per informazioni dettagliate, vedere la raccolta TechNet di [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372)Exchange Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2287d-182">For details, see the Exchange Server 2010 TechNet Library at [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

