---
title: 'Lync Server 2013: spostamento di utenti in VoIP aziendale'
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
ms.openlocfilehash: 3dfd2507f57265b53beea6f84d07760d35abe6e3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507053"
---
# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="431c4-102">Spostamento di utenti in VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="431c4-102">Moving users to Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="431c4-103">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="431c4-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="431c4-104">Se si sta spostando gli utenti da un'infrastruttura di telefonia PBX esistente a VoIP aziendale, il processo di distribuzione include alcuni passaggi che non fanno parte del processo di pianificazione già descritto in [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="431c4-104">If you are moving users from an existing PBX telephony infrastructure to Enterprise Voice, the deployment process includes some steps that are not part of the planning process already described in [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span></span> <span data-ttu-id="431c4-105">Per informazioni sulla migrazione di utenti da una distribuzione di VoIP aziendale precedente, vedere i documenti sulla migrazione inclusi con il supporto di installazione.</span><span class="sxs-lookup"><span data-stu-id="431c4-105">For information about migrating users from an earlier Enterprise Voice deployment, see the migration documents that were included with your installation media.</span></span>

<span data-ttu-id="431c4-106">Il processo di trasferimento degli utenti da un'infrastruttura di telefonia esistente a VoIP aziendale è costituito dai seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="431c4-106">The process of moving users from an existing telephony infrastructure to Enterprise Voice consists of the following steps:</span></span>

1.  <span data-ttu-id="431c4-107">Designazione dei numeri di telefono primari.</span><span class="sxs-lookup"><span data-stu-id="431c4-107">Designate primary phone numbers.</span></span>

2.  <span data-ttu-id="431c4-108">Abilitazione degli utenti per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="431c4-108">Enable users for Enterprise Voice.</span></span>

3.  <span data-ttu-id="431c4-109">Preparazione dei dial plan per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="431c4-109">Prepare dial plans for users.</span></span>

4.  <span data-ttu-id="431c4-110">Pianificazione dei criteri vocali per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="431c4-110">Plan user voice policies.</span></span>

5.  <span data-ttu-id="431c4-111">Pianificazione delle route delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="431c4-111">Plan call routes.</span></span>

6.  <span data-ttu-id="431c4-112">Configurazione del sistema PBX o del trunk SIP per il reinstradamento delle chiamate degli utenti abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="431c4-112">Configure PBX or SIP Trunk to reroute calls for users enabled for Enterprise Voice.</span></span>

7.  <span data-ttu-id="431c4-113">Spostare gli utenti nella messaggistica unificata di Exchange (scelta consigliata).</span><span class="sxs-lookup"><span data-stu-id="431c4-113">Move users to Exchange Unified Messaging (UM) (recommended).</span></span>

<span data-ttu-id="431c4-114">In questo argomento sono descritte le attività di pianificazione necessarie per ognuno di questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="431c4-114">This topic describes the planning that is necessary for each of these steps.</span></span>

<div>

## <a name="step-1-designate-primary-phone-numbers"></a><span data-ttu-id="431c4-p102">Passaggio 1. Designare i numeri di telefono primari</span><span class="sxs-lookup"><span data-stu-id="431c4-p102">Step 1. Designate primary phone numbers</span></span>

<span data-ttu-id="431c4-p103">VoIP aziendale integra funzionalità vocali con altre funzionalità multimediali di messaggistica. Ad esempio, quando il server riceve una chiamata in arrivo, esegue il mapping del numero all'URI SIP dell'utente e quindi inoltra la chiamata a tutti gli endpoint client associati a tale URI SIP. Per questo processo è necessario che ogni utente sia associato a un numero di telefono primario.</span><span class="sxs-lookup"><span data-stu-id="431c4-p103">Enterprise Voice integrates voice with other messaging media, such that when an incoming call arrives at the server, the server maps the number to the user’s SIP-URI and then forks the call to all the client endpoints associated with that SIP-URI. This process requires that each user be associated with a primary phone number.</span></span>

<span data-ttu-id="431c4-119">Un numero di telefono primario deve avere le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="431c4-119">A primary phone number must be:</span></span>

  - <span data-ttu-id="431c4-120">Deve essere globalmente univoco o, nel caso dei numeri di interno, univoco nell'azienda.</span><span class="sxs-lookup"><span data-stu-id="431c4-120">Globally unique or, in the case of internal extensions, unique in the enterprise.</span></span>

  - <span data-ttu-id="431c4-p104">Deve essere di proprietà dell'azienda e instradabile. Non deve essere un numero personale.</span><span class="sxs-lookup"><span data-stu-id="431c4-p104">Owned by and routable in the enterprise. Personal numbers should not be used.</span></span>

<span data-ttu-id="431c4-123">Per gli utenti dell'organizzazione possono essere presenti due o più numeri di telefono in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="431c4-123">Enterprise users can have two or more telephone numbers listed for them in Active Directory Domain Services.</span></span> <span data-ttu-id="431c4-124">Tutti i numeri di telefono associati a un determinato utente possono essere visualizzati o modificati nella finestra delle proprietà dello snap-in Utenti e computer di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="431c4-124">All the telephone numbers associated with a particular user can be viewed or changed on the property sheet for that user in the Active Directory Users and Computers snap-in.</span></span>

<span data-ttu-id="431c4-p106">La casella **Numero di telefono** nella scheda **Generale** della finestra di dialogo **Proprietà utente** deve contenere il numero di lavoro principale dell'utente. Questo numero viene in genere designato come numero di telefono primario.</span><span class="sxs-lookup"><span data-stu-id="431c4-p106">The **Telephone number** box on the **General** tab of the **User Properties** dialog box should contain the user’s main work number. This number will usually be designated as the user's Primary Phone Number.</span></span>

<span data-ttu-id="431c4-127">Alcuni utenti potrebbero avere requisiti particolari, ad esempio per un dirigente può essere necessario instradare tutte le chiamate in arrivo a un assistente amministrativo. Tali eccezioni devono essere limitate solo a casi di evidente necessità.</span><span class="sxs-lookup"><span data-stu-id="431c4-127">Some users may have special requirements (for example, an executive who wants all incoming calls routed through an administrative assistant), but such exceptions should be limited only to those where the need is clear and critical.</span></span>

<span data-ttu-id="431c4-128">Una volta scelto, il numero primario deve essere:</span><span class="sxs-lookup"><span data-stu-id="431c4-128">After a primary number is chosen, it must be:</span></span>

  - <span data-ttu-id="431c4-129">Normalizzato nel formato E.164, quando possibile.</span><span class="sxs-lookup"><span data-stu-id="431c4-129">Normalized to E.164 format, wherever possible.</span></span>

  - <span data-ttu-id="431c4-130">Copiato nell'attributo **msRTCSIP-line** di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="431c4-130">Copied to the Active Directory **msRTCSIP-line** attribute.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="431c4-131"><STRONG>Coesistenza con il controllo delle chiamate remote (RCC)</STRONG></span><span class="sxs-lookup"><span data-stu-id="431c4-131"><STRONG>Coexisting with remote call control (RCC)</STRONG></span></span><BR><span data-ttu-id="431c4-132">RCC è la possibilità di utilizzare Lync Server per monitorare e controllare un telefono PBX desktop.</span><span class="sxs-lookup"><span data-stu-id="431c4-132">RCC is the ability to use Lync Server to monitor and control a desktop PBX phone.</span></span> <span data-ttu-id="431c4-133">Il controllo viene instradato attraverso il server, che funge da gateway per il sistema PBX.</span><span class="sxs-lookup"><span data-stu-id="431c4-133">Control is routed through the server, which acts as a gateway to the PBX.</span></span> <span data-ttu-id="431c4-134">Anche se non è possibile configurare un utente per le chiamate remote e VoIP aziendale, l'impostazione URI linea designa il numero di telefono principale di un utente in entrambi i casi.</span><span class="sxs-lookup"><span data-stu-id="431c4-134">Although you cannot configure a user for both RCC and Enterprise Voice, the Line URI setting designates a user’s primary phone number in either case.</span></span><BR><span data-ttu-id="431c4-135">Se si desidera continuare a utilizzare l'infrastruttura PBX esistente per alcuni utenti selezionati, è possibile introdurre VoIP aziendale nell'organizzazione in modo graduale.</span><span class="sxs-lookup"><span data-stu-id="431c4-135">If you have an existing PBX infrastructure that you want selected users to continue using, you can introduce Enterprise Voice incrementally into your organization.</span></span> <span data-ttu-id="431c4-136">Per informazioni dettagliate su questo scenario di distribuzione, vedere <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP Deployment Options in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="431c4-136">For details about this deployment scenario, see <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP deployment options in Lync Server 2013</A> in the Planning documentation.</span></span><BR><span data-ttu-id="431c4-137">Nelle versioni precedenti, è possibile abilitare sia RCC che VoIP aziendale per un utente, ma solo se è stato configurato anche l'utente per il dual forking, una funzionalità in cui una chiamata in arrivo suonerà contemporaneamente il telefono PBX e Communicator di un utente.</span><span class="sxs-lookup"><span data-stu-id="431c4-137">In previous releases, you could enable both RCC and Enterprise Voice for a user, but only if you also configured the user for dual forking, a feature in which an incoming call will ring a user’s PBX phone and Communicator simultaneously.</span></span> <span data-ttu-id="431c4-138">In Lync Server 2010, il dual-forking non è supportato.</span><span class="sxs-lookup"><span data-stu-id="431c4-138">In Lync Server 2010, dual-forking is not supported.</span></span>

    
    </div>

<span data-ttu-id="431c4-139">Per popolare l'attributo **msRTCSIP-line** sono disponibili tre metodi:</span><span class="sxs-lookup"><span data-stu-id="431c4-139">There are three methods for populating the **msRTCSIP-line** attribute:</span></span>

  - <span data-ttu-id="431c4-140">Microsoft Identity Integration Server (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="431c4-140">Microsoft Identity Integration Server (recommended)</span></span>

  - <span data-ttu-id="431c4-141">La pagina **utenti** nel pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="431c4-141">The **Users** page in the Lync Server Control Panel</span></span>

<span data-ttu-id="431c4-142">Dove devono essere elaborati molti numeri di telefono, uno script personalizzato sviluppato dall'organizzazione è la scelta migliore.</span><span class="sxs-lookup"><span data-stu-id="431c4-142">Where many phone numbers must be processed, a script custom developed by your organization is the better choice.</span></span> <span data-ttu-id="431c4-143">A seconda della modalità con cui l'organizzazione rappresenta i numeri di telefono in Servizi di dominio Active Directory, può essere necessario utilizzare lo script per normalizzare i numeri di telefono primari in base al formato E.164 prima di copiarli nell'attributo **msRTCSIP-line**.</span><span class="sxs-lookup"><span data-stu-id="431c4-143">Depending on how your organization represents telephone numbers in Active Directory Domain Services, the script may have to normalize primary phone numbers to E.164 format before copying them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="431c4-144">Se l'organizzazione gestisce tutti i numeri di telefono in un unico formato in Servizi di dominio Active Directory e se tale formato è E.164, è necessario utilizzare lo script solo per scrivere ogni numero di telefono primario nell'attributo **msRTCSIP-line**.</span><span class="sxs-lookup"><span data-stu-id="431c4-144">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, and if that format is E.164, your script only needs to write each Primary Telephone Number to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="431c4-145">Se l'organizzazione gestisce tutti i numeri di telefono in un unico formato in Servizi di dominio Active Directory, ma tale formato non è E.164, è necessario utilizzare lo script per definire una regola di normalizzazione appropriata in modo da convertire i numeri di telefono primari dal formato esistente in E.164 prima di scriverli nell'attributo **msRTCSIP-line**.</span><span class="sxs-lookup"><span data-stu-id="431c4-145">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, but that format is not E.164, your script should define an appropriate normalization rule to convert Primary Telephone Numbers from their existing format to E.164 before writing them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="431c4-146">Se l'organizzazione non adotta un formato standard per i numeri di telefono in Servizi di dominio Active Directory, è necessario utilizzare lo script per definire le regole di normalizzazione appropriate per convertire i numeri di telefono primari dai diversi formati in un formato conforme a E.164 prima di scriverli nell'attributo **msRTCSIP-line**.</span><span class="sxs-lookup"><span data-stu-id="431c4-146">If your organization does not enforce a standard format for telephone numbers in Active Directory Domain Services, your script should define appropriate normalization rules to convert Primary Phone Numbers from their various formats to E.164 compliance before writing the Primary Telephone Numbers to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="431c4-147">Lo script dovrà inoltre aggiungere il prefisso **Tel:** ai numeri primari prima di scriverli nell'attributo**msRTCSIP-line**.</span><span class="sxs-lookup"><span data-stu-id="431c4-147">Your script will also have to insert the prefix **Tel:** before each primary number before writing it to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="431c4-148">Il formato previsto del numero specificato in questo attributo è il seguente:</span><span class="sxs-lookup"><span data-stu-id="431c4-148">The expected format of the number specified in this attribute is:</span></span>

  - <span data-ttu-id="431c4-149">Tel: + 14255550100; ext = 50100.</span><span class="sxs-lookup"><span data-stu-id="431c4-149">Tel:+14255550100;ext=50100.</span></span>

  - <span data-ttu-id="431c4-150">Tel:5550100 (per i numeri di interno univoci a livello aziendale)</span><span class="sxs-lookup"><span data-stu-id="431c4-150">Tel:5550100 (for unique enterprise wide extensions)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="431c4-151">La normalizzazione eseguita dal servizio Rubrica (ABS) non sostituisce né elimina in altro modo la necessità di normalizzare il numero di telefono primario di ogni utente in Servizi di dominio Active Directory. ABS infatti non dispone dell'accesso a Servizi di dominio Active Directory e pertanto non può copiare i numeri primari nell'attributo <STRONG>msRTCSIP-line</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="431c4-151">The normalization performed by the Address Book Service (ABS) does not replace or otherwise eliminate the need to normalize each user's primary phone number in Active Directory Domain Services because ABS does not have access to Active Directory Domain Services and therefore cannot copy primary numbers to the <STRONG>msRTCSIP-line</STRONG> attribute.</span></span>

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a><span data-ttu-id="431c4-p111">Passaggio 2. Abilitare gli utenti per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="431c4-p111">Step 2. Enable users for Enterprise Voice</span></span>

<span data-ttu-id="431c4-154">Oltre a identificare gli utenti da abilitare, per completare questo passaggio non sono necessarie attività di pianificazione particolari.</span><span class="sxs-lookup"><span data-stu-id="431c4-154">Other than identifying which users are to be enabled, no special planning is required to complete this step.</span></span>

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a><span data-ttu-id="431c4-p112">Passaggio 3. Preparare i dial plan per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="431c4-p112">Step 3. Prepare dial plans for users.</span></span>

<span data-ttu-id="431c4-p113">Senza un dial plan gli utenti abilitati per VoIP aziendale non sono in grado di effettuare chiamate a PSTN. Per dial plan si intende un set denominato di regole di normalizzazione che consente di convertire i numeri di telefono relativi a una località, a un utente o a un oggetto contatto specifico in un unico formato standard (E.164) ai fini dell'autorizzazione del telefono e del routing della chiamata. Le regole di normalizzazione definiscono la modalità di instradamento dei numeri di telefono espressi in diversi formati per ogni località, utente o oggetto contatto.</span><span class="sxs-lookup"><span data-stu-id="431c4-p113">Users who are enabled for Enterprise Voice will not be able to make calls to the PSTN without dial plans in place. A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing. Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span>

<span data-ttu-id="431c4-160">Per informazioni sulla preparazione dei dial plan, vedere [dial plan e regole di normalizzazione in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="431c4-160">For information about preparing dial plans, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span></span>

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a><span data-ttu-id="431c4-161">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="431c4-161">Step 4.</span></span> <span data-ttu-id="431c4-162">Pianificare i criteri vocali degli utenti</span><span class="sxs-lookup"><span data-stu-id="431c4-162">Plan user voice policies</span></span>

<span data-ttu-id="431c4-163">Le impostazioni utente relative alla classe di servizio in un sistema PBX legacy, ad esempio il diritto di effettuare chiamate interurbane o internazionali dai telefoni dell'azienda, devono essere configurate come criteri VoIP per gli utenti trasferiti in VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="431c4-163">User class-of-service settings on a legacy PBX, such as the right to make long-distance or international calls from company phones, must be reconfigured as VoIP policies for users moved to Enterprise Voice.</span></span> <span data-ttu-id="431c4-164">Per informazioni dettagliate sulla pianificazione e la creazione di criteri per VoIP aziendale, vedere [criteri vocali in Lync Server 2013](lync-server-2013-voice-policies.md).</span><span class="sxs-lookup"><span data-stu-id="431c4-164">For details about planning and creating policies for Enterprise Voice, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md).</span></span>

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a><span data-ttu-id="431c4-165">Passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="431c4-165">Step 5.</span></span> <span data-ttu-id="431c4-166">Pianificare le route delle chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="431c4-166">Plan outbound call routes</span></span>

<span data-ttu-id="431c4-167">Route di chiamata specificare in che modo Lync Server gestisce le chiamate in uscita effettuate dagli utenti di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="431c4-167">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="431c4-168">Quando un utente compone un numero, il server, se necessario, normalizza la stringa di composizione nel formato E.164 e tenta di associarla a un URI SIP.</span><span class="sxs-lookup"><span data-stu-id="431c4-168">When a user dials a number, the server, if necessary, normalizes the dial string to E.164 format and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="431c4-169">Se per il server non è possibile effettuare l'associazione, verrà applicata la logica di routing delle chiamate in uscita in base al numero.</span><span class="sxs-lookup"><span data-stu-id="431c4-169">If the server is unable to make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="431c4-170">Il passaggio finale della definizione della logica consiste nel creare una route di chiamate denominate separate per ogni insieme di numeri di telefono di destinazione elencati in ogni dial plan.</span><span class="sxs-lookup"><span data-stu-id="431c4-170">The final step in defining that logic is creating a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="431c4-171">Per informazioni dettagliate sulla pianificazione delle route di chiamata, vedere [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="431c4-171">For details about planning call routes, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a><span data-ttu-id="431c4-172">Passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="431c4-172">Step 6.</span></span> <span data-ttu-id="431c4-173">Configurare il sistema PBX o il trunk SIP per il reinstradamento delle chiamate degli utenti abilitati per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="431c4-173">Configure PBX or SIP Trunk to reroute calls for Enterprise Voice users</span></span>

<span data-ttu-id="431c4-174">Dopo il trasferimento, gli utenti precedentemente ospitati in un'infrastruttura PBX tradizionale o che usufruivano di una connessione trunk SIP Trunk a un provider di telefonia Internet (ITSP, Internet Telephony Service Provider) mantengono lo stesso numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="431c4-174">Users who formerly were hosted on a traditional PBX or on a SIP Trunk connection to an Internet Telephony Service Provider (ITSP) retain their phone numbers after the move.</span></span> <span data-ttu-id="431c4-175">L'unico requisito è che dopo lo spostamento, il PBX o il trunk SIP deve essere riconfigurato per instradare le chiamate in arrivo per gli utenti di VoIP aziendale al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="431c4-175">The only requirement is that after the move, the PBX or SIP Trunk must be reconfigured to route incoming calls for Enterprise Voice users to the Mediation Server.</span></span>

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a><span data-ttu-id="431c4-p120">Passaggio 7. Trasferire gli utenti al servizio Messaggistica unificata di Exchange (operazione consigliata).</span><span class="sxs-lookup"><span data-stu-id="431c4-p120">Step 7. Move users to Exchange Unified Messaging (recommended)</span></span>

<span data-ttu-id="431c4-178">Il passaggio degli utenti al servizio Messaggistica unificata di Exchange è costituito dalle seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="431c4-178">Moving users to Exchange Unified Messaging consists of the following tasks:</span></span>

  - <span data-ttu-id="431c4-179">Configurazione della messaggistica unificata di Exchange e di Lync Server per la collaborazione.</span><span class="sxs-lookup"><span data-stu-id="431c4-179">Configure Exchange Unified Messaging and Lync Server to work together.</span></span>

  - <span data-ttu-id="431c4-180">Abilitazione degli utenti per il risponditore automatico del servizio Messaggistica unificata di Exchange e per Outlook Voice Access.</span><span class="sxs-lookup"><span data-stu-id="431c4-180">Enable users for Exchange Unified Messaging call answering and Outlook Voice Access.</span></span> <span data-ttu-id="431c4-181">Questa attività viene eseguita nel server di Messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="431c4-181">This task is performed on the Exchange Unified Messaging server.</span></span> <span data-ttu-id="431c4-182">Per informazioni dettagliate, vedere la libreria TechNet di Exchange Server 2010 all'indirizzo [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372) .</span><span class="sxs-lookup"><span data-stu-id="431c4-182">For details, see the Exchange Server 2010 TechNet Library at [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

