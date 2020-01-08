---
title: 'Lync Server 2013: modificare un criterio vocale e configurare i record di utilizzo PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify a voice policy and configure PSTN usage records
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398511(v=OCS.15)
ms:contentKeyID: 48184419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb7c4cdc47c0624b3d94d0dc52c527310f803d83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="29c4e-102">Modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29c4e-102">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29c4e-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="29c4e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="29c4e-104">Seguire questa procedura se si vuole modificare un criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="29c4e-104">Follow these steps if you want to modify a voice policy.</span></span> <span data-ttu-id="29c4e-105">Se si vuole creare un nuovo criterio vocale, vedere [creare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) per la procedura.</span><span class="sxs-lookup"><span data-stu-id="29c4e-105">If you want to create a new voice policy, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="29c4e-106">Se un utente viene assegnato a un criterio vocale non ha un record di utilizzo PSTN (Public Switched Telephone Network) associato, l'utente non può inserire le chiamate in uscita.</span><span class="sxs-lookup"><span data-stu-id="29c4e-106">If a user is assigned to a voice policy has no associated public switched telephone network (PSTN) usage records, the user cannot place outbound calls.</span></span> <span data-ttu-id="29c4e-107">Per un elenco di tutti i record di utilizzo PSTN disponibili nella distribuzione vocale aziendale e per visualizzarne le proprietà, vedere <A href="lync-server-2013-view-pstn-usage-records.md">visualizzare i record di utilizzo PSTN in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="29c4e-107">For a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-modify-a-voice-policy"></a><span data-ttu-id="29c4e-108">Per modificare un criterio vocale</span><span class="sxs-lookup"><span data-stu-id="29c4e-108">To modify a voice policy</span></span>

1.  <span data-ttu-id="29c4e-109">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="29c4e-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="29c4e-110">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="29c4e-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="29c4e-111">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29c4e-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="29c4e-112">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="29c4e-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="29c4e-113">Sulla barra di spostamento sinistra fare clic su **routing vocale**e quindi su **criteri vocali**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-113">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="29c4e-114">Nella pagina **criteri vocali** fare doppio clic su un nome di criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="29c4e-114">On the **Voice Policy** page, double-click a voice policy name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="29c4e-115">L'ambito e il nome sono stati impostati quando è stato creato il criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="29c4e-115">The scope and name were set when the voice policy was created.</span></span> <span data-ttu-id="29c4e-116">Non possono essere modificate.</span><span class="sxs-lookup"><span data-stu-id="29c4e-116">They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="29c4e-117">Opzionale In **modifica criterio vocale**immettere altre informazioni descrittive per il criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="29c4e-117">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

6.  <span data-ttu-id="29c4e-118">Selezionare o deselezionare le caselle di controllo seguenti per abilitare o disabilitare ognuna delle **funzionalità di chiamata**:</span><span class="sxs-lookup"><span data-stu-id="29c4e-118">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>
    
      - <span data-ttu-id="29c4e-119">La funzionalità **escape** per la segreteria telefonica impedisce che le chiamate vengano immediatamente indirizzate al sistema di segreteria telefonica dell'utente quando è configurato lo squillo simultaneo e che il telefono sia disattivato, fuori batteria o fuori portata.</span><span class="sxs-lookup"><span data-stu-id="29c4e-119">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="29c4e-120">Questa caratteristica può essere configurata solo tramite Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="29c4e-120">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="29c4e-121">L' **inoltro di chiamata** consente agli utenti di inoltrare le chiamate ad altri telefoni e dispositivi client.</span><span class="sxs-lookup"><span data-stu-id="29c4e-121">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="29c4e-122">Lync Server 2013 offre una gamma molto più ampia di opzioni di configurazione per l'inoltro di chiamata.</span><span class="sxs-lookup"><span data-stu-id="29c4e-122">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="29c4e-123">Ad esempio, se un'organizzazione non vuole consentire la trasmissione esterna delle chiamate in arrivo alla rete PSTN, un amministratore può applicare un criterio vocale speciale per distribuire questa restrizione.</span><span class="sxs-lookup"><span data-stu-id="29c4e-123">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="29c4e-124">Abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="29c4e-124">Enabled by default.</span></span>
    
      - <span data-ttu-id="29c4e-125">La **delega** consente agli utenti di specificare ad altri utenti di inviare e ricevere chiamate per proprio conto.</span><span class="sxs-lookup"><span data-stu-id="29c4e-125">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="29c4e-126">In Lync Server 2013, un delegato può configurare lo squillo simultaneo che consente alle chiamate in arrivo al suo manager di chiamare tutte le destinazioni di chiamata simultanee del delegato.</span><span class="sxs-lookup"><span data-stu-id="29c4e-126">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="29c4e-127">In questo modo il delegato offre maggiore flessibilità per rispondere alle chiamate indirizzate al responsabile.</span><span class="sxs-lookup"><span data-stu-id="29c4e-127">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="29c4e-128">Abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="29c4e-128">Enabled by default.</span></span>
    
      - <span data-ttu-id="29c4e-129">Il **trasferimento** delle chiamate consente agli utenti di trasferire le chiamate ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="29c4e-129">**Call transfer** enables users to transfer calls to other users.</span></span> <span data-ttu-id="29c4e-130">Abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="29c4e-130">Enabled by default.</span></span>
    
      - <span data-ttu-id="29c4e-131">**Call Park** consente agli utenti di parcheggiare le chiamate in attesa e quindi di ritirare la chiamata da un altro telefono o client.</span><span class="sxs-lookup"><span data-stu-id="29c4e-131">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client.</span></span> <span data-ttu-id="29c4e-132">Disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="29c4e-132">Disabled by default.</span></span>
    
      - <span data-ttu-id="29c4e-133">La **chiamata simultanea** consente alle chiamate in arrivo di squillare su altri telefoni (ad esempio, un cellulare) o altri dispositivi endpoint.</span><span class="sxs-lookup"><span data-stu-id="29c4e-133">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="29c4e-134">Lync Server 2013 offre una gamma molto più ampia di opzioni di configurazione per la chiamata simultanea.</span><span class="sxs-lookup"><span data-stu-id="29c4e-134">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="29c4e-135">Abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="29c4e-135">Enabled by default.</span></span>
    
      - <span data-ttu-id="29c4e-136">La **chiamata del team** consente agli utenti di un team definito di rispondere alle chiamate per gli altri membri del team.</span><span class="sxs-lookup"><span data-stu-id="29c4e-136">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="29c4e-137">Abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="29c4e-137">Enabled by default.</span></span>
    
      - <span data-ttu-id="29c4e-138">La **reinstradazione PSTN** consente alle chiamate effettuate dagli utenti a cui è assegnato questo criterio ad altri utenti aziendali di essere reinstradati nella rete PSTN (Public Switched Telephone Network) se la WAN è congestionata o non disponibile.</span><span class="sxs-lookup"><span data-stu-id="29c4e-138">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable.</span></span> <span data-ttu-id="29c4e-139">Abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="29c4e-139">Enabled by default.</span></span>
    
      - <span data-ttu-id="29c4e-140">**L'override dei criteri di larghezza di banda** consente agli amministratori di ignorare le decisioni sui criteri di controllo dell'ammissione delle chiamate per un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="29c4e-140">**Bandwidth policy override** enables administrators to override call admission control (CAC) policy decisions for a particular user.</span></span> <span data-ttu-id="29c4e-141">Disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="29c4e-141">Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="29c4e-142">Il criterio verrà ignorato solo per le chiamate in arrivo all'utente e non per le chiamate in uscita poste dall'utente.</span><span class="sxs-lookup"><span data-stu-id="29c4e-142">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user.</span></span> <span data-ttu-id="29c4e-143">Una volta stabilita la sessione, il consumo di larghezza di banda verrà accuratamente registrato.</span><span class="sxs-lookup"><span data-stu-id="29c4e-143">After the session is established, the bandwidth consumption will be accurately recorded.</span></span> <span data-ttu-id="29c4e-144">Questa impostazione deve essere usata con parsimonia.</span><span class="sxs-lookup"><span data-stu-id="29c4e-144">This setting should be used sparingly.</span></span>

        
        </div>
    
      - <span data-ttu-id="29c4e-145">La **traccia di chiamata** non consentita consente agli utenti di segnalare chiamate illecite (ad esempio minacce bomba) usando l'interfaccia utente del client, che a sua volta contrassegna le chiamate nei record dettagli chiamata (CDRs).</span><span class="sxs-lookup"><span data-stu-id="29c4e-145">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) using the client UI, which in turn flags the calls in the call detail records (CDRs).</span></span> <span data-ttu-id="29c4e-146">Disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="29c4e-146">Disabled by default.</span></span>

7.  <span data-ttu-id="29c4e-147">Per associare e configurare i record di utilizzo PSTN per questo criterio vocale, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="29c4e-147">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="29c4e-148">Per scegliere uno o più record da un elenco di tutti i record di utilizzo PSTN disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-148">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="29c4e-149">Evidenziare i record che si desidera associare a questo criterio vocale e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-149">Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="29c4e-150">Per rimuovere un record di utilizzo PSTN da questo criterio vocale, evidenziare il record e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-150">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="29c4e-151">Per definire un nuovo record di utilizzo PSTN e associarlo a questo criterio vocale, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="29c4e-151">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="29c4e-152">Fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-152">Click **New**.</span></span>
        
        2.  <span data-ttu-id="29c4e-153">Nel campo **nome** immettere un nome descrittivo univoco per il record.</span><span class="sxs-lookup"><span data-stu-id="29c4e-153">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="29c4e-154">Ad esempio, potresti voler creare un record di utilizzo PSTN denominato **Redmond** per i dipendenti a tempo pieno che si trovano a Redmond e un altro record denominato **RedmondTemps** per i dipendenti temporanei.</span><span class="sxs-lookup"><span data-stu-id="29c4e-154">For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another record named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="29c4e-155">Il nome del record utilizzo PSTN deve essere univoco all'interno della distribuzione VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="29c4e-155">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="29c4e-156">Dopo il salvataggio del record, il campo <STRONG>nome</STRONG> non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="29c4e-156">After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="29c4e-157">Usare uno dei metodi seguenti per associare e configurare le route per questo record di utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="29c4e-157">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="29c4e-158">Per scegliere una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**, evidenziare le route da associare al record di utilizzo PSTN e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-158">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="29c4e-159">Per rimuovere una route dal record utilizzo PSTN, evidenziare la route e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-159">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="29c4e-160">Per definire una nuova route e associarla a questo record di utilizzo PSTN, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-160">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="29c4e-161">Per informazioni dettagliate, vedere [creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="29c4e-161">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="29c4e-162">Per modificare una route già associata a questo record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-162">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="29c4e-163">Per informazioni dettagliate, vedere [modificare una route vocale in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="29c4e-163">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="29c4e-164">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-164">Click **OK**.</span></span>
    
      - <span data-ttu-id="29c4e-165">Per modificare un record di utilizzo PSTN già associato a questo criterio vocale, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="29c4e-165">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="29c4e-166">Evidenziare il record di utilizzo PSTN che si vuole modificare e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-166">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="29c4e-167">Usare uno dei metodi seguenti per associare e configurare le route per questo record di utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="29c4e-167">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="29c4e-168">Per scegliere una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**, evidenziare le route da associare al record di utilizzo PSTN e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-168">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="29c4e-169">Per rimuovere una route da questo record di utilizzo PSTN, evidenziare la route e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-169">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="29c4e-170">Per definire una nuova route e associarla a questo record di utilizzo PSTN, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-170">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="29c4e-171">Per informazioni dettagliate, vedere [creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="29c4e-171">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="29c4e-172">Per modificare una route già associata a questo record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-172">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="29c4e-173">Per informazioni dettagliate, vedere [modificare una route vocale in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="29c4e-173">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="29c4e-174">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-174">Click **OK**.</span></span>

8.  <span data-ttu-id="29c4e-175">Disporre i record di utilizzo PSTN per ottenere prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="29c4e-175">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="29c4e-176">Per modificare la posizione di un record nell'elenco, evidenziare il nome del record e fare clic sulla freccia verso l'alto o verso il basso.</span><span class="sxs-lookup"><span data-stu-id="29c4e-176">To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="29c4e-177">L'ordine in cui i record di utilizzo PSTN sono elencati nel criterio vocale è significativo.</span><span class="sxs-lookup"><span data-stu-id="29c4e-177">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="29c4e-178">Lync Server attraversa l'elenco dall'alto verso il basso.</span><span class="sxs-lookup"><span data-stu-id="29c4e-178">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="29c4e-179">Ti consigliamo di organizzare l'elenco in base alla frequenza di utilizzo, ad esempio: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="29c4e-179">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

9.  <span data-ttu-id="29c4e-180">Per associare e configurare i record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo in questo criterio vocale, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="29c4e-180">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="29c4e-181">Per usare gli stessi record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo come criterio vocale, selezionare la route di opzione **usando gli utilizzi PSTN chiamata** dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="29c4e-181">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="29c4e-182">Per consentire l'inoltro di chiamata e lo squillo simultaneo solo agli utenti interni di Lync, selezionare instrada solo agli **utenti interni di Lync** dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="29c4e-182">To allow call forwarding and simultaneous ringing to internal Lync users only, select **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="29c4e-183">Le chiamate non verranno inoltrate ai numeri PSTN esterni.</span><span class="sxs-lookup"><span data-stu-id="29c4e-183">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="29c4e-184">Per specificare diversi record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo rispetto a quelli usati per questo criterio vocale, selezionare la route di opzione **usando gli usi PSTN personalizzati** dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="29c4e-184">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu.</span></span> <span data-ttu-id="29c4e-185">Questa opzione consente di visualizzare un controllo per selezionare i record di utilizzo PSTN esistenti o per creare nuovi record di utilizzo PSTN, in particolare per l'inoltro di chiamata e lo squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="29c4e-185">This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="29c4e-186">Per scegliere uno o più record da un elenco di record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-186">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**.</span></span> <span data-ttu-id="29c4e-187">Evidenziare i record che si desidera associare ai criteri di inoltro di chiamata e squillo simultaneo e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-187">Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="29c4e-188">Per rimuovere un record di utilizzo PSTN da questo inoltro di chiamata e dal criterio di squillo simultaneo, evidenziare il record e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-188">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="29c4e-189">Per definire un nuovo record di utilizzo PSTN e associarlo ai criteri di inoltro di chiamata e squillo simultaneo, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="29c4e-189">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="29c4e-190">Fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-190">Click **New**.</span></span>
            
            2.  <span data-ttu-id="29c4e-191">Nel campo **nome** immettere un nome descrittivo univoco per il record.</span><span class="sxs-lookup"><span data-stu-id="29c4e-191">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="29c4e-192">Il nome del record utilizzo PSTN deve essere univoco all'interno della distribuzione VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="29c4e-192">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="29c4e-193">Dopo il salvataggio del record, il campo <STRONG>nome</STRONG> non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="29c4e-193">After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="29c4e-194">Usare uno dei metodi seguenti per associare e configurare le route per questo record di utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="29c4e-194">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="29c4e-195">Per scegliere una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**, evidenziare le route da associare al record di utilizzo PSTN e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-195">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="29c4e-196">Per rimuovere una route dal record utilizzo PSTN, evidenziare la route e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-196">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="29c4e-197">Per definire una nuova route e associarla a questo record di utilizzo PSTN, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-197">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="29c4e-198">Per informazioni dettagliate, vedere [creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="29c4e-198">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="29c4e-199">Per modificare una route già associata a questo record di utilizzo PSTN, evidenziare la route e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-199">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="29c4e-200">Per informazioni dettagliate, vedere [modificare una route vocale in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="29c4e-200">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="29c4e-201">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-201">Click **OK**.</span></span>
        
          - <span data-ttu-id="29c4e-202">Per modificare un record di utilizzo PSTN già associato a questo criterio vocale, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="29c4e-202">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="29c4e-203">Evidenziare il record di utilizzo PSTN che si vuole modificare e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-203">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="29c4e-204">Usare uno dei metodi seguenti per associare e configurare le route per questo record di utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="29c4e-204">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="29c4e-205">Per scegliere una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**, evidenziare le route da associare al record di utilizzo PSTN e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-205">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="29c4e-206">Per rimuovere una route da questo record di utilizzo PSTN, evidenziare la route e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-206">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="29c4e-207">Per definire una nuova route e associarla a questo record di utilizzo PSTN, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-207">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="29c4e-208">Per informazioni dettagliate, vedere [creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="29c4e-208">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="29c4e-209">Per modificare una route già associata a questo record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-209">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="29c4e-210">Per informazioni dettagliate, vedere [modificare una route vocale in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="29c4e-210">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="29c4e-211">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-211">Click **OK**.</span></span>

10. <span data-ttu-id="29c4e-212">Opzionale Immettere un numero per testare il criterio vocale e fare clic su **Vai**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-212">(Optional) Enter a number to test the voice policy and click **Go**.</span></span> <span data-ttu-id="29c4e-213">I risultati del test vengono visualizzati in **numero tradotto per il test**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-213">The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="29c4e-214">È possibile salvare un criterio vocale che non supera ancora il test e quindi riconfigurarlo in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="29c4e-214">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="29c4e-215">Per informazioni dettagliate, vedere <A href="lync-server-2013-test-voice-routing.md">eseguire il test del routing vocale in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="29c4e-215">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="29c4e-216">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-216">Click **OK**.</span></span>

12. <span data-ttu-id="29c4e-217">Nella pagina **criteri vocali** fare clic su **commit**e quindi su **Commit all**.</span><span class="sxs-lookup"><span data-stu-id="29c4e-217">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="29c4e-218">Ogni volta che si crea o si modifica un criterio vocale, è necessario eseguire il comando <STRONG>commit tutti</STRONG> per pubblicare la modifica della configurazione.</span><span class="sxs-lookup"><span data-stu-id="29c4e-218">Whenever you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="29c4e-219">Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A> nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="29c4e-219">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

13. <span data-ttu-id="29c4e-220">Opzionale La funzionalità di escape della segreteria telefonica rileva che una chiamata è stata immediatamente risolta dalla segreteria telefonica dell'utente e disconnette la chiamata alla segreteria telefonica per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="29c4e-220">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="29c4e-221">In questo modo la chiamata continuerà a squillare sugli altri endpoint dell'utente dando all'utente la possibilità di rispondere alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="29c4e-221">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="29c4e-222">Per informazioni dettagliate su come configurare un criterio per la segreteria telefonica, vedere [configurazione della modalità di escape della segreteria telefonica in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span><span class="sxs-lookup"><span data-stu-id="29c4e-222">For details about how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="29c4e-223">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29c4e-223">See Also</span></span>


[<span data-ttu-id="29c4e-224">Creare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29c4e-224">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="29c4e-225">Visualizzare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29c4e-225">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="29c4e-226">Creare una route vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29c4e-226">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="29c4e-227">Modificare una route vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29c4e-227">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="29c4e-228">Pubblicare le modifiche in sospeso nella configurazione di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29c4e-228">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="29c4e-229">Configurazione della posta in uscita della segreteria telefonica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29c4e-229">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="29c4e-230">Testare il routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29c4e-230">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

