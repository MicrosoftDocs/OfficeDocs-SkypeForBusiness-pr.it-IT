---
title: 'Lync Server 2013: modificare un criterio vocale e configurare i record di utilizzo PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice policy and configure PSTN usage records
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398511(v=OCS.15)
ms:contentKeyID: 48184419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c11ae10476d286fd24f82b96ba9191b0e758e276
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="f1597-102">Modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1597-102">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1597-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f1597-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f1597-104">Eseguire la procedura seguente se si desidera modificare criteri vocali.</span><span class="sxs-lookup"><span data-stu-id="f1597-104">Follow these steps if you want to modify a voice policy.</span></span> <span data-ttu-id="f1597-105">Se si desidera creare un nuovo criterio vocale, vedere [creare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) per la procedura.</span><span class="sxs-lookup"><span data-stu-id="f1597-105">If you want to create a new voice policy, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f1597-106">Se a un utente assegnato a criteri vocali non sono associati record di utilizzo PSTN, l'utente non può effettuare chiamate in uscita.</span><span class="sxs-lookup"><span data-stu-id="f1597-106">If a user is assigned to a voice policy has no associated public switched telephone network (PSTN) usage records, the user cannot place outbound calls.</span></span> <span data-ttu-id="f1597-107">Per un elenco di tutti i record di utilizzo PSTN disponibili nella distribuzione di VoIP aziendale e per visualizzare le relative proprietà, vedere <A href="lync-server-2013-view-pstn-usage-records.md">visualizzare i record di utilizzo PSTN in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f1597-107">For a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-modify-a-voice-policy"></a><span data-ttu-id="f1597-108">Per modificare criteri vocali</span><span class="sxs-lookup"><span data-stu-id="f1597-108">To modify a voice policy</span></span>

1.  <span data-ttu-id="f1597-109">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f1597-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="f1597-110">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f1597-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f1597-111">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1597-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f1597-112">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f1597-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f1597-113">Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Criteri vocali**.</span><span class="sxs-lookup"><span data-stu-id="f1597-113">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="f1597-114">Nella pagina **Criteri vocali** fare doppio clic sui nomi dei criteri vocali.</span><span class="sxs-lookup"><span data-stu-id="f1597-114">On the **Voice Policy** page, double-click a voice policy name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f1597-p105">L'ambito e il nome sono stati impostati durante la creazione dei criteri vocali e non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="f1597-p105">The scope and name were set when the voice policy was created. They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="f1597-117">Facoltativo: in **Modifica criterio vocale** immettere informazioni descrittive aggiuntive per i criteri vocali.</span><span class="sxs-lookup"><span data-stu-id="f1597-117">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

6.  <span data-ttu-id="f1597-118">Selezionare o deselezionare le caselle di controllo seguenti per abilitare o disabilitare ogni opzione presente in **Funzionalità di chiamata**:</span><span class="sxs-lookup"><span data-stu-id="f1597-118">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>
    
      - <span data-ttu-id="f1597-119">La **funzione di escape della segreteria telefonica** fa in modo che le chiamate non vengano immediatamente instradate al sistema di segreteria telefonica del dispositivo mobile dell'utente quando è attivo lo squillo simultaneo, e il telefono è spento, scarico o fuori copertura di rete.</span><span class="sxs-lookup"><span data-stu-id="f1597-119">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f1597-120">Questa funzionalità può essere configurata solo tramite Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f1597-120">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="f1597-121">L'**inoltro di chiamata** consente agli utenti di inoltrare chiamate ad altri telefoni e dispositivi client.</span><span class="sxs-lookup"><span data-stu-id="f1597-121">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="f1597-122">Lync Server 2013 offre un'ampia gamma di opzioni di configurazione per l'inoltro di chiamata.</span><span class="sxs-lookup"><span data-stu-id="f1597-122">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="f1597-123">Ad esempio, se l'organizzazione desidera evitare che le chiamate in entrata vengano inoltrate esternamente a PSTN, l'amministratore può applicare un criterio vocale specifico per la distribuzione di questa limitazione.</span><span class="sxs-lookup"><span data-stu-id="f1597-123">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="f1597-124">Funzionalità abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f1597-124">Enabled by default.</span></span>
    
      - <span data-ttu-id="f1597-125">La **delega** consente agli utenti di specificare altri utenti per l'invio e la ricezione delle chiamate per loro conto.</span><span class="sxs-lookup"><span data-stu-id="f1597-125">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="f1597-126">In Lync Server 2013, un delegato può configurare lo squillo simultaneo che consente alle chiamate in arrivo al proprio manager di suonare tutti gli obiettivi di squillo simultanei del delegato.</span><span class="sxs-lookup"><span data-stu-id="f1597-126">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="f1597-127">In questo modo, al delegato viene offerta una maggiore flessibilità quando si trova a dover rispondere a chiamate destinate al proprio manager.</span><span class="sxs-lookup"><span data-stu-id="f1597-127">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="f1597-128">La funzionalità è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f1597-128">Enabled by default.</span></span>
    
      - <span data-ttu-id="f1597-p108">**Trasferimento chiamata**: consente agli utenti di trasferire chiamate ad altri utenti. Questa opzione è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f1597-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>
    
      - <span data-ttu-id="f1597-p109">**Parcheggio di chiamata**: consente agli utenti di eseguire il parcheggio di chiamate in attesa e quindi di rispondere alla chiamata da un telefono o un client diverso. Questa opzione è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f1597-p109">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client. Disabled by default.</span></span>
    
      - <span data-ttu-id="f1597-133">**Squillo simultaneo** consente lo squillo in telefoni aggiuntivi, ad esempio un telefono cellulare, o in altri dispositivi endpoint per le chiamate in arrivo.</span><span class="sxs-lookup"><span data-stu-id="f1597-133">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="f1597-134">Lync Server 2013 offre una vasta gamma di opzioni di configurazione per lo squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="f1597-134">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="f1597-135">Funzionalità abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f1597-135">Enabled by default.</span></span>
    
      - <span data-ttu-id="f1597-p111">**Intercettazione team**: consente agli utenti di un team definito di rispondere alle chiamate per altri membri del team. Questa opzione è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f1597-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>
    
      - <span data-ttu-id="f1597-p112">**Abilita reindirizzamento PSTN**: consente il rendirizzamento di chiamate effettuate da utenti assegnati ai criteri ad altri utenti aziendali nella rete PSTN in caso di congestione o non disponibilità della rete WAN. Questa opzione è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f1597-p112">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>
    
      - <span data-ttu-id="f1597-p113">**Abilita override criteri larghezza di banda**: consente agli amministratori di eseguire l'override delle decisioni relative ai criteri di controllo di ammissione di chiamata per un utente specifico. Questa opzione è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f1597-p113">**Bandwidth policy override** enables administrators to override call admission control (CAC) policy decisions for a particular user. Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f1597-p114">Verrà eseguito l'override dei criteri solo per le chiamate in arrivo all'utente e non per le chiamate in uscita effettuate dall'utente. Dopo che la sessione viene stabilita, l'utilizzo della larghezza di banda viene registrato accuratamente. Questa impostazione deve essere utilizzata con cautela.</span><span class="sxs-lookup"><span data-stu-id="f1597-p114">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly.</span></span>

        
        </div>
    
      - <span data-ttu-id="f1597-p115">**Abilita traccia chiamate moleste**: consente agli utenti di segnalare chiamate moleste, ad esempio minacce di attentato, utilizzando l'interfaccia utente client, tramite cui le chiamate vengono contrassegnate nella registrazione dettagli chiamata (CDR). Questa opzione è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f1597-p115">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) using the client UI, which in turn flags the calls in the call detail records (CDRs). Disabled by default.</span></span>

7.  <span data-ttu-id="f1597-147">Per associare e configurare record di utilizzo PSTN per i criteri vocali, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1597-147">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="f1597-p116">Per scegliere uno o più record da un elenco di record di utilizzo PSTN disponibile nella distribuzione di VoIP aziendale, fare clic su **Seleziona**. Evidenziare i record da associare al criterio vocale e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f1597-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="f1597-150">Per rimuovere un record di utilizzo PSTN dal criterio vocale, evidenziarlo e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="f1597-150">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="f1597-151">Per definire un nuovo record di utilizzo PSTN e associarlo ai criteri vocali, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1597-151">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="f1597-152">Fare clic su **Nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="f1597-152">Click **New**.</span></span>
        
        2.  <span data-ttu-id="f1597-p117">Nel campo **Nome** immettere un nome descrittivo univoco per il record. È possibile, ad esempio, creare un record di utilizzo PSTN denominato **Redmond** per dipendenti a tempo pieno che si trovano a Redmond e un altro record denominato **RedmondTemp** per i dipendenti temporanei.</span><span class="sxs-lookup"><span data-stu-id="f1597-p117">In the **Name** field, enter a unique descriptive name for the record. For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another record named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="f1597-p118">Il nome del record di utilizzo PSTN deve essere univoco all'interno della distribuzione VoIP aziendale. Dopo avere salvato il record, il campo <STRONG>Nome</STRONG> non può più essere modificato.</span><span class="sxs-lookup"><span data-stu-id="f1597-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="f1597-157">Utilizzare uno dei metodi seguenti per associare e configurare route per il record di utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="f1597-157">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="f1597-158">Per scegliere una o più route nell'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**, evidenziare le route che si desidera associare al record di utilizzo PSTN e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f1597-158">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="f1597-159">Per rimuovere una route dal record di utilizzo PSTN, evidenziarla e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="f1597-159">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="f1597-160">Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f1597-160">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="f1597-161">Per informazioni dettagliate, vedere [Create a Voice Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f1597-161">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="f1597-162">Per modificare una route già associata al record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f1597-162">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="f1597-163">Per ulteriori informazioni, vedere [Modify a Voice Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f1597-163">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="f1597-164">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f1597-164">Click **OK**.</span></span>
    
      - <span data-ttu-id="f1597-165">Per modificare un record di utilizzo PSTN già associato al criterio vocale, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1597-165">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="f1597-166">Evidenziare il record di utilizzo PSTN da modificare e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f1597-166">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="f1597-167">Utilizzare uno dei metodi seguenti per associare e configurare route per il record di utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="f1597-167">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="f1597-168">Per scegliere una o più route da un elenco di tutte le route disponibili nella distribuzione di VoIP aziendale, fare clic su **Seleziona**. Evidenziare le route da associare al record di utilizzo PSTN e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f1597-168">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="f1597-169">Per rimuovere una route dal record di utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="f1597-169">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="f1597-170">Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f1597-170">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="f1597-171">Per informazioni dettagliate, vedere [Create a Voice Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f1597-171">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="f1597-172">Per modificare una route già associata al record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f1597-172">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="f1597-173">Per ulteriori informazioni, vedere [Modify a Voice Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f1597-173">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="f1597-174">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f1597-174">Click **OK**.</span></span>

8.  <span data-ttu-id="f1597-p123">Disporre i record di utilizzo PSTN per garantire prestazioni ottimali. Per modificare la posizione di un record nell'elenco, evidenziare il nome del record e fare clic sulla freccia in su o in giù.</span><span class="sxs-lookup"><span data-stu-id="f1597-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f1597-177">L'ordine in cui i record di utilizzo PSTN sono elencati nei criteri vocali è significativo.</span><span class="sxs-lookup"><span data-stu-id="f1597-177">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="f1597-178">Lync Server attraversa l'elenco dall'alto verso il basso.</span><span class="sxs-lookup"><span data-stu-id="f1597-178">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="f1597-179">È consigliabile organizzare l'elenco in base a frequenza di utilizzo, ad esempio: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="f1597-179">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

9.  <span data-ttu-id="f1597-180">Per associare e configurare record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo in questo criterio vocale, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1597-180">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="f1597-181">Per utilizzare gli stessi record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo di questo criterio vocale, selezionare l'opzione **Route tramite gli usi PSTN di chiamata** dal  menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="f1597-181">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="f1597-182">Per consentire l'inoltro di chiamata e lo squillo simultaneo solo agli utenti interni di Lync, selezionare **instrada solo gli utenti interni di Lync** dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="f1597-182">To allow call forwarding and simultaneous ringing to internal Lync users only, select **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="f1597-183">Le chiamate non verranno inoltrare ai numeri PSTN esterni.</span><span class="sxs-lookup"><span data-stu-id="f1597-183">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="f1597-p126">Per specificare record di utilizzo PSTN differenti per l'inoltro di chiamata e lo squillo simultaneo rispetto a quelli usati per questo criterio vocale, selezionare l'opzione **Route tramite gli usi PSTN di chiamata** dal  menu a discesa. Questa opzione visualizza un controllo che consente di selezionare i record di utilizzo PSTN esistenti, o di crearne di nuovi, specifici per l'inoltro di chiamata e lo squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="f1597-p126">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="f1597-p127">Per scegliere uno o più record in un elenco dei record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo, fare clic su **Seleziona**. Evidenziare i record che si desidera associare ai criteri vocali dell'inoltro di chiamata e squillo simultaneo e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f1597-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="f1597-188">Per rimuovere un record di utilizzo PSTN dal criterio vocale dell'inoltro di chiamata e squillo simultaneo, evidenziarlo e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="f1597-188">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="f1597-189">Per definire un nuovo record di utilizzo PSTN e associarlo al criterio vocale dell'inoltro di chiamata e squillo simultaneo, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1597-189">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="f1597-190">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f1597-190">Click **New**.</span></span>
            
            2.  <span data-ttu-id="f1597-191">Nel campo **Nome** immettere un nome descrittivo univoco per il record.</span><span class="sxs-lookup"><span data-stu-id="f1597-191">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="f1597-p128">Il nome del record di utilizzo PSTN deve essere univoco all'interno della distribuzione di VoIP aziendale. Dopo il salvataggio del record, il campo <STRONG>Nome</STRONG> non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="f1597-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="f1597-194">Utilizzare uno dei metodi seguenti per associare e configurare route per il record di utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="f1597-194">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="f1597-195">Per scegliere una o più route nell'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**, evidenziare le route che si desidera associare al record di utilizzo PSTN e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f1597-195">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="f1597-196">Per rimuovere una route dal record di utilizzo PSTN, evidenziarla e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="f1597-196">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="f1597-197">Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f1597-197">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="f1597-198">Per informazioni dettagliate, vedere [Create a Voice Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f1597-198">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="f1597-199">Per modificare una route già associata al record di utilizzo PSTN, evidenziarla e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f1597-199">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="f1597-200">Per ulteriori informazioni, vedere [Modify a Voice Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f1597-200">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="f1597-201">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f1597-201">Click **OK**.</span></span>
        
          - <span data-ttu-id="f1597-202">Per modificare un record di utilizzo PSTN già associato al criterio vocale, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1597-202">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="f1597-203">Evidenziare il record di utilizzo PSTN da modificare e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f1597-203">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="f1597-204">Utilizzare uno dei metodi seguenti per associare e configurare route per il record di utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="f1597-204">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="f1597-205">Per scegliere una o più route nell'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**, evidenziare le route che si desidera associare al record di utilizzo PSTN e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f1597-205">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="f1597-206">Per rimuovere una route dal record di utilizzo PSTN, evidenziare la route e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="f1597-206">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="f1597-207">Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f1597-207">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="f1597-208">Per informazioni dettagliate, vedere [Create a Voice Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f1597-208">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="f1597-209">Per modificare una route già associata al record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f1597-209">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="f1597-210">Per ulteriori informazioni, vedere [Modify a Voice Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f1597-210">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="f1597-211">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f1597-211">Click **OK**.</span></span>

10. <span data-ttu-id="f1597-p133">(Facoltativo) Immettere un numero per testare il criteri vocale e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Numero convertito da testare**.</span><span class="sxs-lookup"><span data-stu-id="f1597-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f1597-214">È possibile salvare i criteri locali che non hanno ancora superato il test e quindi riconfigurarli in seguito.</span><span class="sxs-lookup"><span data-stu-id="f1597-214">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="f1597-215">Per ulteriori informazioni, vedere <A href="lync-server-2013-test-voice-routing.md">test Voice routing in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f1597-215">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="f1597-216">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f1597-216">Click **OK**.</span></span>

12. <span data-ttu-id="f1597-217">Nella pagina **Criteri vocali** fare clic su **Commit** e quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="f1597-217">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f1597-218">Quando si creano o modificano criteri vocali, è necessario eseguire il comando <STRONG>Salva tutto</STRONG> per pubblicare la modifica di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f1597-218">Whenever you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="f1597-219">Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="f1597-219">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

13. <span data-ttu-id="f1597-220">(Facoltativo) La funzione di escape della segreteria telefonica rileva quando una chiamata viene risposta automaticamente dalla segreteria telefonica del dispositivo mobile dell'utente, e la disconnette dalla segreteria.</span><span class="sxs-lookup"><span data-stu-id="f1597-220">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="f1597-221">In questo modo, la chiamata continua a squillare sugli altri endpoint dell'utente, consentendo a quest'ultimo di rispondere.</span><span class="sxs-lookup"><span data-stu-id="f1597-221">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="f1597-222">Per informazioni dettagliate su come configurare un criterio di segreteria telefonica, vedere [Configuring Voice mail Escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span><span class="sxs-lookup"><span data-stu-id="f1597-222">For details about how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f1597-223">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1597-223">See Also</span></span>


[<span data-ttu-id="f1597-224">Creare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1597-224">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="f1597-225">Visualizzare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1597-225">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="f1597-226">Creare una route vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1597-226">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="f1597-227">Modificare una route vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1597-227">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="f1597-228">Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1597-228">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="f1597-229">Configurazione della funzionalità di escape della segreteria telefonica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1597-229">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="f1597-230">Testare il routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1597-230">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

