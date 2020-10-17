---
title: 'Lync Server 2013: creare un criterio vocale e configurare i record di utilizzo PSTN'
description: 'Lync Server 2013: creare un criterio vocale e configurare i record di utilizzo PSTN.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice policy and configure PSTN usage records
ms:assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399027(v=OCS.15)
ms:contentKeyID: 48185693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55833572b5ca79019d5037406ae530ef5591b6fe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562452"
---
# <a name="create-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="2baa6-103">Creare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2baa6-103">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2baa6-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2baa6-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2baa6-105">Se si desidera creare un nuovo criterio vocale, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="2baa6-105">Follow these steps if you want to create a new voice policy.</span></span> <span data-ttu-id="2baa6-106">Se si desidera modificare un criterio vocale, vedere [modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) per la procedura.</span><span class="sxs-lookup"><span data-stu-id="2baa6-106">If you want to edit a voice policy, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2baa6-107">Ogni criterio vocale deve disporre di almeno un record di utilizzo PSTN (Public Switched Telephone Network) associato.</span><span class="sxs-lookup"><span data-stu-id="2baa6-107">Each voice policy must have at least one associated public switched telephone network (PSTN) usage record.</span></span> <span data-ttu-id="2baa6-108">Per visualizzare un elenco di tutti i record di utilizzo PSTN disponibili nella distribuzione di VoIP aziendale e visualizzarne le proprietà, vedere <A href="lync-server-2013-view-pstn-usage-records.md">visualizzare i record di utilizzo PSTN in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2baa6-108">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-voice-policy"></a><span data-ttu-id="2baa6-109">Per creare un criterio vocale</span><span class="sxs-lookup"><span data-stu-id="2baa6-109">To create a voice policy</span></span>

1.  <span data-ttu-id="2baa6-110">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2baa6-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="2baa6-111">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="2baa6-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="2baa6-112">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2baa6-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2baa6-113">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2baa6-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2baa6-114">Sulla barra di spostamento sinistra fare clic su **routing vocale** e quindi su **criteri vocali**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-114">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="2baa6-115">Nella pagina **criteri vocali** fare clic su **nuovo** e quindi selezionare un ambito per il nuovo criterio:</span><span class="sxs-lookup"><span data-stu-id="2baa6-115">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>
    
      - <span data-ttu-id="2baa6-116">I **criteri del sito** si applicano a un intero sito, ad eccezione degli utenti o dei gruppi assegnati a un criterio utente.</span><span class="sxs-lookup"><span data-stu-id="2baa6-116">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy.</span></span> <span data-ttu-id="2baa6-117">Se si seleziona sito per un ambito di criteri, scegliere il sito nella finestra di dialogo **Seleziona un sito** .</span><span class="sxs-lookup"><span data-stu-id="2baa6-117">If you select Site for a policy scope, choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="2baa6-118">Se per un sito è già stato creato un criterio vocale, il sito non viene visualizzato nella finestra di dialogo **Seleziona un sito** .</span><span class="sxs-lookup"><span data-stu-id="2baa6-118">If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="2baa6-119">I **criteri utente** possono essere applicati a utenti o gruppi specificati.</span><span class="sxs-lookup"><span data-stu-id="2baa6-119">**User policy** can be applied to specified users or groups.</span></span>

5.  <span data-ttu-id="2baa6-120">Se l'ambito dei criteri vocali è utente, immettere un nome descrittivo per il criterio nel campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="2baa6-120">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2baa6-121">Se l'ambito del criterio vocale è sito, il campo <STRONG>nome</STRONG> nei <STRONG>nuovi criteri vocali</STRONG> viene prepopolato con il nome del sito e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="2baa6-121">If the voice policy scope is Site, the <STRONG>Name</STRONG> field in <STRONG>New Voice Policy</STRONG> is prepopulated with the site name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="2baa6-122">Optional Immettere ulteriori informazioni descrittive per il criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="2baa6-122">(Optional) Enter additional descriptive information for the voice policy.</span></span>

7.  <span data-ttu-id="2baa6-123">Selezionare o deselezionare le caselle di controllo seguenti per abilitare o disabilitare ognuna delle **funzionalità di chiamata** per i criteri vocali:</span><span class="sxs-lookup"><span data-stu-id="2baa6-123">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>
    
      - <span data-ttu-id="2baa6-124">La **funzione di escape della segreteria telefonica** fa in modo che le chiamate non vengano immediatamente instradate al sistema di segreteria telefonica del dispositivo mobile dell'utente quando è attivo lo squillo simultaneo, e il telefono è spento, scarico o fuori copertura di rete.</span><span class="sxs-lookup"><span data-stu-id="2baa6-124">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2baa6-125">Questa funzionalità può essere configurata solo tramite Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="2baa6-125">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="2baa6-126">L'**inoltro di chiamata** consente agli utenti di inoltrare chiamate ad altri telefoni e dispositivi client.</span><span class="sxs-lookup"><span data-stu-id="2baa6-126">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="2baa6-127">Lync Server 2013 offre un'ampia gamma di opzioni di configurazione per l'inoltro di chiamata.</span><span class="sxs-lookup"><span data-stu-id="2baa6-127">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="2baa6-128">Ad esempio, se l'organizzazione desidera evitare che le chiamate in entrata vengano inoltrate esternamente a PSTN, l'amministratore può applicare un criterio vocale specifico per la distribuzione di questa limitazione.</span><span class="sxs-lookup"><span data-stu-id="2baa6-128">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="2baa6-129">La funzionalità è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2baa6-129">Enabled by default.</span></span>
    
      - <span data-ttu-id="2baa6-130">La **delega** consente agli utenti di specificare altri utenti per l'invio e la ricezione delle chiamate per loro conto.</span><span class="sxs-lookup"><span data-stu-id="2baa6-130">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="2baa6-131">In Lync Server 2013, un delegato può configurare lo squillo simultaneo che consente alle chiamate in arrivo al proprio manager di suonare tutti gli obiettivi di squillo simultanei del delegato.</span><span class="sxs-lookup"><span data-stu-id="2baa6-131">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="2baa6-132">In questo modo, al delegato viene offerta una maggiore flessibilità quando si trova a dover rispondere a chiamate destinate al proprio manager.</span><span class="sxs-lookup"><span data-stu-id="2baa6-132">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="2baa6-133">La funzionalità è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2baa6-133">Enabled by default.</span></span>
    
      - <span data-ttu-id="2baa6-134">Il **trasferimento di chiamata** consente agli utenti di trasferire chiamate ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="2baa6-134">**Call transfer** enables users to transfer calls to other users.</span></span> <span data-ttu-id="2baa6-135">Funzionalità abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2baa6-135">Enabled by default.</span></span>
    
      - <span data-ttu-id="2baa6-136">**Parcheggio di chiamata** consente agli utenti di parcheggiare le chiamate in attesa e quindi di prendere la chiamata da un altro telefono o client.</span><span class="sxs-lookup"><span data-stu-id="2baa6-136">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client.</span></span> <span data-ttu-id="2baa6-137">Questa opzione è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2baa6-137">Disabled by default.</span></span>
    
      - <span data-ttu-id="2baa6-138">**Squillo simultaneo** consente lo squillo in telefoni aggiuntivi, ad esempio un telefono cellulare, o in altri dispositivi endpoint per le chiamate in arrivo.</span><span class="sxs-lookup"><span data-stu-id="2baa6-138">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="2baa6-139">Lync Server 2013 offre una vasta gamma di opzioni di configurazione per lo squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="2baa6-139">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="2baa6-140">Funzionalità abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2baa6-140">Enabled by default.</span></span>
    
      - <span data-ttu-id="2baa6-p111">**Intercettazione team**: consente agli utenti di un team definito di rispondere alle chiamate per altri membri del team. Questa opzione è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2baa6-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>
    
      - <span data-ttu-id="2baa6-p112">**Abilita reindirizzamento PSTN**: consente il rendirizzamento di chiamate effettuate da utenti assegnati ai criteri ad altri utenti aziendali nella rete PSTN in caso di congestione o non disponibilità della rete WAN. Questa opzione è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2baa6-p112">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>
    
      - <span data-ttu-id="2baa6-145">L'**override dei criteri di larghezza di banda** consente agli amministratori di ignorare le decisioni per i criteri di controllo di ammissione di chiamata per un particolare utente.</span><span class="sxs-lookup"><span data-stu-id="2baa6-145">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user.</span></span> <span data-ttu-id="2baa6-146">Funzionalità disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2baa6-146">Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2baa6-147">Verrà eseguito l'override dei criteri solo per le chiamate in arrivo all'utente e non per le chiamate in uscita effettuate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2baa6-147">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user.</span></span> <span data-ttu-id="2baa6-148">Dopo che la sessione viene stabilita, l'utilizzo della larghezza di banda viene registrato accuratamente.</span><span class="sxs-lookup"><span data-stu-id="2baa6-148">After the session is established, the bandwidth consumption will be accurately recorded.</span></span> <span data-ttu-id="2baa6-149">Questa impostazione deve essere utilizzata con parsimonia e deve essere riservata alle decisioni appropriate per il controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="2baa6-149">This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

        
        </div>
    
      - <span data-ttu-id="2baa6-150">L' **analisi chiamata** non consentita consente agli utenti di segnalare chiamate non consentite (ad esempio minacce di bomba) utilizzando l'interfaccia utente del client, che a sua scelta contrassegna le chiamate nei record dettagli chiamata (CDRs).</span><span class="sxs-lookup"><span data-stu-id="2baa6-150">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) by using the client UI, which in turn flags the calls in the call detail records (CDRs).</span></span> <span data-ttu-id="2baa6-151">Questa opzione è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2baa6-151">Disabled by default.</span></span>

8.  <span data-ttu-id="2baa6-152">Per associare e configurare record di utilizzo PSTN per i criteri vocali, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2baa6-152">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="2baa6-p116">Per scegliere uno o più record da un elenco di record di utilizzo PSTN disponibile nella distribuzione di VoIP aziendale, fare clic su **Seleziona**. Evidenziare i record da associare al criterio vocale e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="2baa6-155">Per rimuovere un record di utilizzo PSTN dal criterio vocale, evidenziarlo e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-155">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="2baa6-156">Per definire un nuovo record di utilizzo PSTN e associarlo ai criteri vocali, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2baa6-156">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="2baa6-157">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-157">Click **New**.</span></span>
        
        2.  <span data-ttu-id="2baa6-158">Nel campo **Nome** immettere un nome descrittivo univoco per il record.</span><span class="sxs-lookup"><span data-stu-id="2baa6-158">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="2baa6-159">Ad esempio, potrebbe essere necessario creare un record di utilizzo PSTN denominato **Redmond** per i dipendenti a tempo pieno situati a Redmond e un altro denominato **RedmondTemps** per i dipendenti temporanei.</span><span class="sxs-lookup"><span data-stu-id="2baa6-159">For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="2baa6-p118">Il nome del record di utilizzo PSTN deve essere univoco all'interno della distribuzione di VoIP aziendale. Dopo il salvataggio del record, il campo <STRONG>Nome</STRONG> non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="2baa6-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="2baa6-162">Utilizzare uno dei metodi seguenti per associare e configurare route per il record di utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="2baa6-162">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="2baa6-163">Per scegliere una o più route nell'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**, evidenziare le route che si desidera associare al record di utilizzo PSTN e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-163">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="2baa6-164">Per rimuovere una route dal record di utilizzo PSTN, evidenziare la route e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-164">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="2baa6-165">Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-165">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="2baa6-166">Per informazioni dettagliate, vedere [Create a Voice Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="2baa6-166">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="2baa6-167">Per modificare una route già associata al record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-167">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="2baa6-168">Per ulteriori informazioni, vedere [Modify a Voice Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="2baa6-168">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="2baa6-169">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-169">Click **OK**.</span></span>
    
      - <span data-ttu-id="2baa6-170">Per modificare un record di utilizzo PSTN già associato al criterio vocale, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2baa6-170">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="2baa6-171">Evidenziare il record di utilizzo PSTN che si desidera modificare e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-171">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>
        
        2.  <span data-ttu-id="2baa6-172">Utilizzare uno dei metodi seguenti per associare e configurare route per il record di utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="2baa6-172">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="2baa6-173">Per scegliere una o più route nell'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**, evidenziare le route che si desidera associare al record di utilizzo PSTN e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-173">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="2baa6-174">Per rimuovere una route dal record di utilizzo PSTN, evidenziare la route e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-174">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="2baa6-175">Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-175">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="2baa6-176">Per informazioni dettagliate, vedere [Create a Voice Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="2baa6-176">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="2baa6-177">Per modificare una route già associata a questo record di utilizzo PSTN, evidenziare la route e leccare **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-177">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span> <span data-ttu-id="2baa6-178">Per ulteriori informazioni, vedere [Modify a Voice Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="2baa6-178">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="2baa6-179">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-179">Click **OK**.</span></span>

9.  <span data-ttu-id="2baa6-p123">Disporre i record di utilizzo PSTN per garantire prestazioni ottimali. Per modificare la posizione di un record nell'elenco, evidenziare il nome del record e fare clic sulla freccia in su o in giù.</span><span class="sxs-lookup"><span data-stu-id="2baa6-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2baa6-182">L'ordine in cui i record di utilizzo PSTN sono elencati nei criteri vocali è significativo.</span><span class="sxs-lookup"><span data-stu-id="2baa6-182">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="2baa6-183">Lync Server attraversa l'elenco dall'alto verso il basso.</span><span class="sxs-lookup"><span data-stu-id="2baa6-183">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="2baa6-184">È consigliabile organizzare l'elenco in base a frequenza di utilizzo, ad esempio: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="2baa6-184">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

10. <span data-ttu-id="2baa6-185">Per associare e configurare record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo in questo criterio vocale, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2baa6-185">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="2baa6-186">Per utilizzare gli stessi record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo di questo criterio vocale, selezionare l'opzione **Route tramite gli usi PSTN di chiamata** dal  menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="2baa6-186">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="2baa6-187">Per consentire l'inoltro di chiamata e lo squillo simultaneo solo agli utenti interni di Lync, selezionare la **Route di opzione per gli utenti interni di Lync solo** dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="2baa6-187">To allow call forwarding and simultaneous ringing to internal Lync users only, select the option **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="2baa6-188">Le chiamate non verranno inoltrare ai numeri PSTN esterni.</span><span class="sxs-lookup"><span data-stu-id="2baa6-188">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="2baa6-189">Per specificare diversi record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo rispetto a quelli utilizzati per questo criterio vocale, selezionare la route delle opzioni **utilizzando gli utilizzi PSTN personalizzati** dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="2baa6-189">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu.</span></span> <span data-ttu-id="2baa6-190">Questa opzione consente di visualizzare un controllo per selezionare i record di utilizzo PSTN esistenti o creare nuovi record di utilizzo PSTN in modo specifico per l'inoltro di chiamata e lo squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="2baa6-190">This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="2baa6-p127">Per scegliere uno o più record in un elenco dei record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo, fare clic su **Seleziona**. Evidenziare i record che si desidera associare ai criteri vocali dell'inoltro di chiamata e squillo simultaneo e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="2baa6-193">Per rimuovere un record di utilizzo PSTN dal criterio vocale dell'inoltro di chiamata e squillo simultaneo, evidenziarlo e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-193">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="2baa6-194">Per definire un nuovo record di utilizzo PSTN e associarlo al criterio vocale dell'inoltro di chiamata e squillo simultaneo, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2baa6-194">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="2baa6-195">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-195">Click **New**.</span></span>
            
            2.  <span data-ttu-id="2baa6-196">Nel campo **Nome** immettere un nome descrittivo univoco per il record.</span><span class="sxs-lookup"><span data-stu-id="2baa6-196">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="2baa6-p128">Il nome del record di utilizzo PSTN deve essere univoco all'interno della distribuzione di VoIP aziendale. Dopo il salvataggio del record, il campo <STRONG>Nome</STRONG> non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="2baa6-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="2baa6-199">Utilizzare uno dei metodi seguenti per associare e configurare route per il record di utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="2baa6-199">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="2baa6-200">Per scegliere una o più route nell'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**, evidenziare le route che si desidera associare al record di utilizzo PSTN e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-200">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="2baa6-201">Per rimuovere una route dal record di utilizzo PSTN, evidenziarla e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-201">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="2baa6-202">Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-202">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="2baa6-203">Per informazioni dettagliate, vedere [Create a Voice Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="2baa6-203">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="2baa6-204">Per modificare una route già associata al record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-204">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="2baa6-205">Per ulteriori informazioni, vedere [Modify a Voice Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="2baa6-205">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="2baa6-206">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-206">Click **OK**.</span></span>
        
          - <span data-ttu-id="2baa6-207">Per modificare un record di utilizzo PSTN già associato al criterio vocale, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2baa6-207">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="2baa6-208">Evidenziare il record di utilizzo PSTN che si desidera modificare e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-208">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="2baa6-209">Utilizzare uno dei metodi seguenti per associare e configurare route per il record di utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="2baa6-209">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="2baa6-210">Per scegliere una o più route da un elenco di tutte le route disponibili nella distribuzione di VoIP aziendale, fare clic su **Seleziona**. Evidenziare le route da associare al record di utilizzo PSTN e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-210">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="2baa6-211">Per rimuovere una route dal record di utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-211">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="2baa6-212">Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-212">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="2baa6-213">Per informazioni dettagliate, vedere [Create a Voice Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="2baa6-213">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="2baa6-214">Per modificare una route già associata al record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-214">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="2baa6-215">Per ulteriori informazioni, vedere [Modify a Voice Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="2baa6-215">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="2baa6-216">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-216">Click **OK**.</span></span>

11. <span data-ttu-id="2baa6-p133">(Facoltativo) Immettere un numero per testare il criteri vocale e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Numero convertito da testare**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2baa6-219">È possibile salvare i criteri locali che non hanno ancora superato il test e quindi riconfigurarli in seguito.</span><span class="sxs-lookup"><span data-stu-id="2baa6-219">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="2baa6-220">Per ulteriori informazioni, vedere <A href="lync-server-2013-test-voice-routing.md">test Voice routing in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2baa6-220">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="2baa6-221">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-221">Click **OK**.</span></span>

13. <span data-ttu-id="2baa6-222">Nella pagina **Criteri vocali** fare clic su **Commit** e quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="2baa6-222">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2baa6-223">Ogni volta che si crea o si modifica un criterio vocale, è necessario eseguire il comando <STRONG>Commit all</STRONG> per pubblicare la modifica della configurazione.</span><span class="sxs-lookup"><span data-stu-id="2baa6-223">Any time you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="2baa6-224">Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="2baa6-224">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

14. <span data-ttu-id="2baa6-225">(Facoltativo) La funzione di escape della segreteria telefonica rileva quando una chiamata viene risposta automaticamente dalla segreteria telefonica del dispositivo mobile dell'utente, e la disconnette dalla segreteria.</span><span class="sxs-lookup"><span data-stu-id="2baa6-225">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="2baa6-226">In questo modo, la chiamata continua a squillare sugli altri endpoint dell'utente, consentendo a quest'ultimo di rispondere.</span><span class="sxs-lookup"><span data-stu-id="2baa6-226">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="2baa6-227">Per informazioni dettagliate su come configurare un criterio di segreteria telefonica, vedere [Configuring Voice mail Escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span><span class="sxs-lookup"><span data-stu-id="2baa6-227">For details on how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2baa6-228">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2baa6-228">See Also</span></span>


[<span data-ttu-id="2baa6-229">Modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2baa6-229">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="2baa6-230">Visualizzare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2baa6-230">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="2baa6-231">Creare una route vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2baa6-231">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="2baa6-232">Modificare una route vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2baa6-232">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="2baa6-233">Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2baa6-233">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="2baa6-234">Configurazione della funzionalità di escape della segreteria telefonica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2baa6-234">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="2baa6-235">Testare il routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2baa6-235">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

