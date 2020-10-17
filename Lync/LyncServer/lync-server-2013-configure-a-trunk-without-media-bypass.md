---
title: 'Lync Server 2013: configurare un trunk senza bypass multimediale'
description: 'Lync Server 2013: configurare un trunk senza bypass multimediale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 586ab4f283034c94bd7cb0179d73a963cad88347
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555962"
---
# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a><span data-ttu-id="4f598-103">Configurare un trunk senza bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f598-103">Configure a trunk without media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f598-104">_**Ultimo argomento modificato:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="4f598-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="4f598-105">Per configurare un trunk con il bypass multimediale disabilitato, attenersi alla procedura che segue.</span><span class="sxs-lookup"><span data-stu-id="4f598-105">If you want to configure a trunk with media bypass disabled, follow these steps.</span></span> <span data-ttu-id="4f598-106">Se si desidera configurare un trunk con bypass multimediale abilitato, vedere [Configure a Trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="4f598-106">If you want to configure a trunk with media bypass enabled, see [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

<span data-ttu-id="4f598-p102">Una configurazione trunk, come quella descritta di seguito, raggruppa un set di parametri che vengono applicati ai trunk assegnati a questa configurazione trunk. Per una determinata configurazione trunk è possibile specificare un ambito globale (corrispondente a tutti i trunk che non presentano una configurazione di sito o di pool più specifica) o un ambito di sito o di pool. La configurazione trunk a livello di pool viene usata per definire un singolo trunk come ambito di una determinata configurazione trunk.</span><span class="sxs-lookup"><span data-stu-id="4f598-p102">A trunk configuration, as described below, groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a><span data-ttu-id="4f598-110">Per configurare un trunk senza bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="4f598-110">To configure a trunk without media bypass</span></span>

1.  <span data-ttu-id="4f598-111">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4f598-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="4f598-112">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="4f598-112">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="4f598-113">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4f598-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4f598-114">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4f598-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4f598-115">Nella barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Configurazione trunk**.</span><span class="sxs-lookup"><span data-stu-id="4f598-115">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="4f598-116">Nella pagina **Configurazione trunk** utilizzare uno dei metodi seguenti per configurare un trunk:</span><span class="sxs-lookup"><span data-stu-id="4f598-116">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="4f598-117">Fare doppio clic su un trunk esistente, ad esempio il trunk **Globale**, per visualizzare la finestra di dialogo **Modifica configurazione trunk**.</span><span class="sxs-lookup"><span data-stu-id="4f598-117">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="4f598-118">Fare clic su **Nuovo** e quindi selezionare un ambito per la nuova configurazione trunk:</span><span class="sxs-lookup"><span data-stu-id="4f598-118">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="4f598-119">**Trunk del sito:** Scegliere il sito per la configurazione del trunk in **Seleziona un sito** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f598-119">**Site trunk:** Choose the site for this trunk configuration in **Select a Site** , and then click **OK**.</span></span> <span data-ttu-id="4f598-120">Si noti che se è già stata creata una configurazione trunk per un sito, tale sito non verrà visualizzato in **Seleziona un sito**.</span><span class="sxs-lookup"><span data-stu-id="4f598-120">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="4f598-121">La configurazione trunk verrà applicata a tutti i trunk presenti nel sito.</span><span class="sxs-lookup"><span data-stu-id="4f598-121">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="4f598-122">**Trunk del pool:** Scegliere il nome del trunk a cui si applica la configurazione del trunk in **Seleziona un servizio** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f598-122">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to in **Select a Service** and click **OK**.</span></span> <span data-ttu-id="4f598-123">Questo trunk può essere il trunk radice o qualsiasi trunk aggiuntivo definito in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="4f598-123">This trunk can be the root trunk, or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="4f598-124">Si noti che se è già stata creata una configurazione trunk per un trunk specifico, tale trunk non verrà visualizzato in **Seleziona un servizio**.</span><span class="sxs-lookup"><span data-stu-id="4f598-124">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4f598-125">Dopo aver selezionato l'ambito della configurazione trunk, non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="4f598-125">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="4f598-126">Il campo <STRONG>Nome</STRONG> è già compilato con il nome del sito o del servizio associato alla configurazione trunk e non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="4f598-126">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="4f598-127">Selezionare una delle opzioni di **Livello di supporto crittografia** seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f598-127">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="4f598-128">**Obbligatorio:** È necessario utilizzare la crittografia SRTP (Secure Real-Time Transport Protocol) per proteggere il traffico tra il Mediation Server e il gateway o il PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="4f598-128">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="4f598-129">**Facoltativo:** La crittografia SRTP verrà utilizzata se il provider di servizi o il produttore di apparecchiature lo supporta.</span><span class="sxs-lookup"><span data-stu-id="4f598-129">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="4f598-130">**Non supportato:** La crittografia SRTP non è supportata dal provider di servizi o dal produttore dell'attrezzatura e pertanto non verrà utilizzata.</span><span class="sxs-lookup"><span data-stu-id="4f598-130">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

6.  <span data-ttu-id="4f598-131">Verificare che la casella di controllo **Abilita bypass multimediale** sia deselezionata.</span><span class="sxs-lookup"><span data-stu-id="4f598-131">Be sure that the **Enable media bypass** check box is cleared.</span></span>

7.  <span data-ttu-id="4f598-p107">Selezionare la casella di controllo **Elaborazione multimediale centralizzata** se è presente un media termination point noto, ad esempio un gateway PSTN (Public Switched Telephone Network) in cui l'IP della terminazione multimediale e quello della terminazione dei segnali coincidono. Deselezionare questa casella di controllo se il trunk non dispone di un media termination point noto.</span><span class="sxs-lookup"><span data-stu-id="4f598-p107">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a public switched telephone network (PSTN) gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

8.  <span data-ttu-id="4f598-134">Se il peer trunk supporta la ricezione di richieste SIP REFER dal Mediation Server, selezionare la casella **di controllo Abilita l'invio di fare riferimento al gateway** .</span><span class="sxs-lookup"><span data-stu-id="4f598-134">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

9.  <span data-ttu-id="4f598-p108">(Facoltativo) Per abilitare il routing tra trunk, associare e configurare i record utilizzo PSTN a questa configurazione trunk. Gli utilizzi PSTN associati alla configurazione trunk verranno applicati per tutte le chiamate in arrivo tramite il trunk che non è originato da un endpoint Lync. Per gestire i record utilizzo PSTN associati a una configurazione trunk, usare uno di questi metodi:</span><span class="sxs-lookup"><span data-stu-id="4f598-p108">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration. The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint. To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="4f598-138">Per selezionare uno o più record da un elenco di tutti i record di utilizzo PSTN disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="4f598-138">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="4f598-139">Evidenziare i record da associare a questa configurazione trunk e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f598-139">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="4f598-140">Per rimuovere un record utilizzo PSTN da questa configurazione trunk, selezionare il record e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="4f598-140">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="4f598-141">Per definire un nuovo record utilizzo PSTN e associarlo a questa configurazione trunk, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f598-141">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="4f598-142">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4f598-142">Click **New**.</span></span>
        
        2.  <span data-ttu-id="4f598-143">Nel campo **Nome** specificare un nome descrittivo univoco per il record.</span><span class="sxs-lookup"><span data-stu-id="4f598-143">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="4f598-p110">Il nome del record di utilizzo PSTN deve essere univoco all'interno della distribuzione di VoIP aziendale. Dopo il salvataggio del record, il campo <STRONG>Nome</STRONG> non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="4f598-p110">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="4f598-146">Per associare e configurare le route per questo record utilizzo PSTN, usare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f598-146">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="4f598-147">Per selezionare una o più route dall'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="4f598-147">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="4f598-148">Evidenziare le route da associare a questo record utilizzo PSTN e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f598-148">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="4f598-149">Per rimuovere una route dal record utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="4f598-149">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="4f598-150">Per definire una nuova route e associarla a questo record utilizzo PSTN, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4f598-150">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="4f598-151">Per informazioni dettagliate, vedere [Create a Voice Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="4f598-151">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="4f598-152">Per modificare una route associata a questo record utilizzo PSTN, selezionare la route e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="4f598-152">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="4f598-153">Per ulteriori informazioni, vedere [Modify a Voice Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="4f598-153">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="4f598-154">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f598-154">Click **OK**.</span></span>
    
      - <span data-ttu-id="4f598-155">Per modificare un record utilizzo PSTN già associato a questa configurazione trunk, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f598-155">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="4f598-156">Selezionare il record utilizzo PSTN da modificare e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="4f598-156">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="4f598-157">Per associare e configurare le route per questo record utilizzo PSTN, usare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f598-157">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="4f598-158">Per selezionare una o più route dall'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="4f598-158">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="4f598-159">Evidenziare le route da associare a questo record utilizzo PSTN e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f598-159">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="4f598-160">Per rimuovere una route dal record utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="4f598-160">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="4f598-161">Per definire una nuova route e associarla a questo record utilizzo PSTN, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4f598-161">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="4f598-162">Per informazioni dettagliate, vedere [Create a Voice Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="4f598-162">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="4f598-163">Per modificare una route associata a questo record utilizzo PSTN, selezionare la route e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="4f598-163">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="4f598-164">Per ulteriori informazioni, vedere [Modify a Voice Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="4f598-164">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="4f598-165">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f598-165">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4f598-166">È importante associare i record di utilizzo PSTN in base al peer Mediation Server associato al trunk configurato.</span><span class="sxs-lookup"><span data-stu-id="4f598-166">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="4f598-167">Se il peer Mediation Server è un gateway PSTN o un session border controller (SBC), è consigliabile che la configurazione trunk non sia associata a un record di utilizzo PSTN che si incammini su una destinazione PSTN o su qualsiasi altro sistema downstream connesso tramite Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4f598-167">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

10. <span data-ttu-id="4f598-p118">Organizzare i record utilizzo PSTN in modo da ottenere prestazioni ottimali. Per modificare la posizione di un record nell'elenco, selezionare il record utilizzo PSTN e fare clic sulle frecce verso l'alto o verso il basso.</span><span class="sxs-lookup"><span data-stu-id="4f598-p118">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4f598-170">L'ordine in cui i record utilizzo PSTN sono elencati nella configurazione trunk è significativo.</span><span class="sxs-lookup"><span data-stu-id="4f598-170">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="4f598-171">Lync Server attraversa l'elenco dall'alto verso il basso.</span><span class="sxs-lookup"><span data-stu-id="4f598-171">Lync Server traverses the list from top to down.</span></span>

    
    </div>

11. <span data-ttu-id="4f598-172">Per abilitare il bypass multimediale per i client protetti da NAT o firewall, selezionare **Abilita latch RTP** e un SBC che supporti il latch.</span><span class="sxs-lookup"><span data-stu-id="4f598-172">**Enable RTP Latching** should be selected to enable bypass media for clients behind a NAT or firewall and an SBC that supports latching.</span></span>

12. <span data-ttu-id="4f598-173">**Abilitare la cronologia delle chiamate inoltrate** per consentire l'invio delle informazioni sulla cronologia delle chiamate al peer gateway del Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="4f598-173">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

13. <span data-ttu-id="4f598-174">Per abilitare l'inoltro delle informazioni sull'originatore delle chiamate PAI tra il lato Mediation Server e il lato gateway (e viceversa), è necessario selezionare **i dati P-Asserted-Identity** .</span><span class="sxs-lookup"><span data-stu-id="4f598-174">**Enable forward P-Asserted-Identity data** should be selected to enable PAI call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

14. <span data-ttu-id="4f598-175">Per abilitare il failover rapido, selezionare **Abilita timer di failover del routing in uscita**.</span><span class="sxs-lookup"><span data-stu-id="4f598-175">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="4f598-176">Il gateway associato a questo trunk può inviare una notifica entro 10 secondi dall'inizio dell'elaborazione di una chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="4f598-176">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="4f598-177">Se la notifica non viene ricevuta dal Mediation Server, il reinstradamento a un altro trunk si verificherà.</span><span class="sxs-lookup"><span data-stu-id="4f598-177">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="4f598-178">Nelle reti in cui la latenza potrebbe ritardare il tempo di risposta o il gateway impiega più di 10 secondi per rispondere, è consigliabile disabilitare il failover rapido.</span><span class="sxs-lookup"><span data-stu-id="4f598-178">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

15. <span data-ttu-id="4f598-179">(Facoltativo) Associare e configurare le **Regole di conversione per il numero del chiamante** per il trunk.</span><span class="sxs-lookup"><span data-stu-id="4f598-179">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="4f598-180">Tali regole sono applicabili al numero del chiamante per le chiamate in uscita.</span><span class="sxs-lookup"><span data-stu-id="4f598-180">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="4f598-181">Per scegliere una o più regole da un elenco di tutte le regole di conversione disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="4f598-181">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="4f598-182">In **Seleziona regole di conversione** fare clic sulle regole da associare al trunk e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f598-182">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="4f598-183">Per definire una nuova regola di conversione e associarla al trunk, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4f598-183">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="4f598-184">Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4f598-184">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="4f598-185">Per modificare una regola di conversione già associata al trunk, fare clic sul nome della regola e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="4f598-185">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="4f598-186">Per informazioni dettagliate, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4f598-186">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="4f598-187">Per copiare una regola di conversione esistente in modo da usarla come punto di partenza per definire una nuova regola, fare clic sul nome della regola, su **Copia** e quindi su **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="4f598-187">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="4f598-188">Per informazioni dettagliate, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="4f598-188">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="4f598-189">Per rimuovere una regola di conversione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="4f598-189">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="sicurezza" alt="security" /><span data-ttu-id="4f598-191">Nota sulla sicurezza:</span><span class="sxs-lookup"><span data-stu-id="4f598-191">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="4f598-192">Non associare regole di conversione a un trunk se nel peer trunk associato sono già configurate regole di conversione, poiché potrebbe verificarsi un conflitto tra le due regole.</span><span class="sxs-lookup"><span data-stu-id="4f598-192">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. <span data-ttu-id="4f598-p126">(Facoltativo) Associare e configurare le **Regole di conversione per il numero chiamato** per il trunk. Tali regole sono applicabili al numero chiamato in una chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="4f598-p126">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="4f598-195">Per scegliere una o più regole da un elenco di tutte le regole di conversione disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="4f598-195">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="4f598-196">In **Seleziona regole di conversione** fare clic sulle regole da associare al trunk e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f598-196">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="4f598-197">Per definire una nuova regola di conversione e associarla al trunk, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4f598-197">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="4f598-198">Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4f598-198">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="4f598-199">Per modificare una regola di conversione già associata al trunk, fare clic sul nome della regola e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="4f598-199">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="4f598-200">Per informazioni dettagliate, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4f598-200">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="4f598-201">Per copiare una regola di conversione esistente in modo da usarla come punto di partenza per definire una nuova regola, fare clic sul nome della regola, su **Copia** e quindi su **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="4f598-201">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="4f598-202">Per informazioni dettagliate, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="4f598-202">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="4f598-203">Per rimuovere una regola di conversione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="4f598-203">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="4f598-204">Non associare regole di conversione a un trunk se sono state configurate regole di conversione nel peer trunk associato, perché le due regole potrebbero essere in conflitto.</span><span class="sxs-lookup"><span data-stu-id="4f598-204">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="4f598-205">Verificare che le regole di conversione del trunk siano disposte nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="4f598-205">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="4f598-206">Per cambiare la posizione di una regola nell'elenco, evidenziare il nome della regola e quindi fare clic sulla freccia verso l'alto o verso il basso.</span><span class="sxs-lookup"><span data-stu-id="4f598-206">To change a rule’s position in the list, highlight the rule name, and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4f598-207">Lync Server attraversa l'elenco delle regole di conversione dall'alto verso il basso e utilizza la prima regola che corrisponde al numero composto.</span><span class="sxs-lookup"><span data-stu-id="4f598-207">Lync Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="4f598-208">Se si configura un trunk in modo che un numero che viene composto possa soddisfare più regole di conversione, verificare che le regole più restrittive siano elencate al di sopra di quelle meno restrittive.</span><span class="sxs-lookup"><span data-stu-id="4f598-208">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="4f598-209">Se ad esempio sono state incluse una regola di conversione per qualsiasi numero di 11 cifre e una regola di conversione solo per i numeri di 11 cifre che iniziano con +1425, verificare che la regola per i numeri di 11 cifre sia elencata <EM>al di sotto</EM> della regola più restrittiva.</span><span class="sxs-lookup"><span data-stu-id="4f598-209">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

18. <span data-ttu-id="4f598-210">Dopo aver terminato la configurazione del trunk, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f598-210">When you are finished configuring the trunk, click **OK**.</span></span>

19. <span data-ttu-id="4f598-211">Nella pagina **Configurazione trunk** fare clic su **Commit** e quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="4f598-211">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4f598-212">Ogni volta che si crea o si modifica una configurazione trunk, è necessario eseguire il comando <STRONG>Salva tutto</STRONG> per pubblicare la modifica apportata alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="4f598-212">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="4f598-213">Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="4f598-213">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4f598-214">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f598-214">See Also</span></span>


[<span data-ttu-id="4f598-215">Configurare un trunk con bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f598-215">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="4f598-216">Definizione delle regole di conversione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f598-216">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

