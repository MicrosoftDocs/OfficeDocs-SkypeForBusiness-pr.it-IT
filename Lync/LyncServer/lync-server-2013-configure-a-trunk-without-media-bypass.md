---
title: 'Lync Server 2013: configurare un trunk senza bypass multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e6508fe88a585c22b9936e787be2ee99b8f9b7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a><span data-ttu-id="208cd-102">Configurare un trunk senza bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="208cd-102">Configure a trunk without media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="208cd-103">_**Argomento Ultima modifica:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="208cd-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="208cd-104">Se si vuole configurare un trunk con il bypass multimediale disabilitato, eseguire le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="208cd-104">If you want to configure a trunk with media bypass disabled, follow these steps.</span></span> <span data-ttu-id="208cd-105">Se si vuole configurare un trunk con il bypass multimediale abilitato, vedere [configurare un trunk con il bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="208cd-105">If you want to configure a trunk with media bypass enabled, see [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

<span data-ttu-id="208cd-106">Una configurazione trunk, come descritto di seguito, raggruppa un set di parametri applicati ai trunk assegnati alla configurazione del trunk.</span><span class="sxs-lookup"><span data-stu-id="208cd-106">A trunk configuration, as described below, groups a set of parameters that are applied to trunks assigned this trunk configuration.</span></span> <span data-ttu-id="208cd-107">Una particolare configurazione trunk può essere portata a livello globale (per tutti i trunk che non dispongono di una configurazione di sito o di pool più specifica) o di un sito o di un pool.</span><span class="sxs-lookup"><span data-stu-id="208cd-107">A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool.</span></span> <span data-ttu-id="208cd-108">La configurazione del trunk a livello di pool viene usata per l'ambito di una configurazione trunk specifica in un singolo trunk.</span><span class="sxs-lookup"><span data-stu-id="208cd-108">The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a><span data-ttu-id="208cd-109">Per configurare un trunk senza bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="208cd-109">To configure a trunk without media bypass</span></span>

1.  <span data-ttu-id="208cd-110">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="208cd-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="208cd-111">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="208cd-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="208cd-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="208cd-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="208cd-113">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="208cd-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="208cd-114">Sulla barra di spostamento sinistra fare clic su **routing vocale**e quindi su **configurazione trunk**.</span><span class="sxs-lookup"><span data-stu-id="208cd-114">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="208cd-115">Nella pagina **trunk Configuration** usare uno dei metodi seguenti per configurare un trunk:</span><span class="sxs-lookup"><span data-stu-id="208cd-115">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="208cd-116">Fare doppio clic su un trunk esistente, ad esempio il trunk **globale** , per visualizzare la finestra di dialogo **modifica configurazione trunk** .</span><span class="sxs-lookup"><span data-stu-id="208cd-116">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="208cd-117">Fare clic su **nuovo**e quindi selezionare un ambito per la nuova configurazione trunk:</span><span class="sxs-lookup"><span data-stu-id="208cd-117">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="208cd-118">**Trunk sito:** Scegliere il sito per questa configurazione trunk in **selezionare un sito** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="208cd-118">**Site trunk:** Choose the site for this trunk configuration in **Select a Site** , and then click **OK**.</span></span> <span data-ttu-id="208cd-119">Tieni presente che se è già stata creata una configurazione trunk per un sito, il sito non viene visualizzato in **Seleziona un sito**.</span><span class="sxs-lookup"><span data-stu-id="208cd-119">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="208cd-120">Questa configurazione trunk verrà applicata a tutti i trunk nel sito.</span><span class="sxs-lookup"><span data-stu-id="208cd-120">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="208cd-121">**Trunk pool:** Scegliere il nome del trunk a cui si applica la configurazione del trunk in **selezionare un servizio** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="208cd-121">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to in **Select a Service** and click **OK**.</span></span> <span data-ttu-id="208cd-122">Questo trunk può essere il trunk radice o altri trunk definiti in Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="208cd-122">This trunk can be the root trunk, or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="208cd-123">Tieni presente che se è già stata creata una configurazione trunk per un trunk specifico, il trunk non viene visualizzato in **Seleziona un servizio**.</span><span class="sxs-lookup"><span data-stu-id="208cd-123">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="208cd-124">Dopo aver selezionato l'ambito della configurazione trunk, non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="208cd-124">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="208cd-125">Il campo <STRONG>nome</STRONG> viene prepopolato con il nome del sito o del servizio associato alla configurazione del trunk e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="208cd-125">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="208cd-126">Selezionare una delle opzioni seguenti per il **livello di supporto della crittografia** :</span><span class="sxs-lookup"><span data-stu-id="208cd-126">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="208cd-127">**Obbligatorio:** Per proteggere il traffico tra il Mediation Server e il gateway o il PBX (Private Branch Exchange), è necessario usare la crittografia SRTP (Secure Real Time Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="208cd-127">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="208cd-128">**Facoltativo:** La crittografia SRTP verrà usata se il provider di servizi o il produttore di attrezzature lo supporta.</span><span class="sxs-lookup"><span data-stu-id="208cd-128">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="208cd-129">**Non supportato:** La crittografia SRTP non è supportata dal provider di servizi o dal produttore di attrezzature e quindi non verrà usata.</span><span class="sxs-lookup"><span data-stu-id="208cd-129">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

6.  <span data-ttu-id="208cd-130">Assicurarsi che la casella di controllo **Abilita esclusione multimediale** sia deselezionata.</span><span class="sxs-lookup"><span data-stu-id="208cd-130">Be sure that the **Enable media bypass** check box is cleared.</span></span>

7.  <span data-ttu-id="208cd-131">Selezionare la casella di controllo **elaborazione multimediale centralizzata** se è presente un punto di interruzione del contenuto multimediale noto, ad esempio un gateway PSTN (Public Switched Telephone Network) in cui la terminazione multimediale ha lo stesso IP della terminazione di segnalazione.</span><span class="sxs-lookup"><span data-stu-id="208cd-131">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a public switched telephone network (PSTN) gateway where the media termination has the same IP as the signaling termination).</span></span> <span data-ttu-id="208cd-132">Deselezionare questa casella di controllo se il trunk non ha un punto di interruzione multimediale noto.</span><span class="sxs-lookup"><span data-stu-id="208cd-132">Clear this check box if the trunk does not have a well-known media termination point.</span></span>

8.  <span data-ttu-id="208cd-133">Se il peer trunk supporta la ricezione delle richieste SIP REFER dal Mediation Server, selezionare la casella **di controllo Consenti invio di riferimento al gateway** .</span><span class="sxs-lookup"><span data-stu-id="208cd-133">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

9.  <span data-ttu-id="208cd-134">Opzionale Per abilitare il routing tra trunk, associa e configura i record di utilizzo PSTN alla configurazione del trunk.</span><span class="sxs-lookup"><span data-stu-id="208cd-134">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="208cd-135">Gli usi PSTN associati alla configurazione del trunk verranno applicati per tutte le chiamate in arrivo tramite il trunk non proveniente da un endpoint Lync.</span><span class="sxs-lookup"><span data-stu-id="208cd-135">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint.</span></span> <span data-ttu-id="208cd-136">Per gestire i record di utilizzo PSTN associati a una configurazione trunk, usare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="208cd-136">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="208cd-137">Per selezionare uno o più record da un elenco di tutti i record di utilizzo PSTN disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="208cd-137">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="208cd-138">Evidenziare i record che si desidera associare alla configurazione del trunk e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="208cd-138">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="208cd-139">Per rimuovere un record di utilizzo PSTN dalla configurazione del trunk, selezionare il record e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="208cd-139">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="208cd-140">Per definire un nuovo record di utilizzo PSTN e associarlo alla configurazione del trunk, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="208cd-140">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="208cd-141">Fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="208cd-141">Click **New**.</span></span>
        
        2.  <span data-ttu-id="208cd-142">Nel campo **nome** specificare un nome descrittivo per il record univoco.</span><span class="sxs-lookup"><span data-stu-id="208cd-142">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="208cd-143">Il nome del record utilizzo PSTN deve essere univoco all'interno della distribuzione VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="208cd-143">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="208cd-144">Dopo il salvataggio del record, il campo <STRONG>nome</STRONG> non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="208cd-144">After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="208cd-145">Usare uno dei metodi seguenti per associare e configurare le route per il record di utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="208cd-145">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="208cd-146">Per selezionare una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="208cd-146">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="208cd-147">Evidenziare le route da associare al record di utilizzo PSTN e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="208cd-147">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="208cd-148">Per rimuovere una route dal record utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="208cd-148">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="208cd-149">Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="208cd-149">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="208cd-150">Per informazioni dettagliate, vedere [creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="208cd-150">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="208cd-151">Per modificare una route associata a questo record di utilizzo PSTN, selezionare la route e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="208cd-151">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="208cd-152">Per informazioni dettagliate, vedere [modificare una route vocale in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="208cd-152">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="208cd-153">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="208cd-153">Click **OK**.</span></span>
    
      - <span data-ttu-id="208cd-154">Per modificare un record di utilizzo PSTN già associato alla configurazione del trunk, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="208cd-154">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="208cd-155">Selezionare il record di utilizzo PSTN che si vuole modificare e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="208cd-155">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="208cd-156">Usare uno dei metodi seguenti per associare e configurare le route per il record di utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="208cd-156">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="208cd-157">Per selezionare una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="208cd-157">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="208cd-158">Evidenziare le route da associare al record di utilizzo PSTN e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="208cd-158">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="208cd-159">Per rimuovere una route dal record utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="208cd-159">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="208cd-160">Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="208cd-160">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="208cd-161">Per informazioni dettagliate, vedere [creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="208cd-161">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="208cd-162">Per modificare una route associata a questo record di utilizzo PSTN, selezionare la route e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="208cd-162">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="208cd-163">Per informazioni dettagliate, vedere [modificare una route vocale in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="208cd-163">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="208cd-164">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="208cd-164">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="208cd-165">È importante associare i record di utilizzo PSTN in base al peer di Mediation Server associato al trunk configurato.</span><span class="sxs-lookup"><span data-stu-id="208cd-165">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="208cd-166">Se il peer di Mediation Server è un gateway PSTN o un SBC (Session Border Controller), è consigliabile che la configurazione trunk non sia associata a un record di utilizzo PSTN che si indirizza a una destinazione PSTN o a qualsiasi altro sistema downstream connesso tramite Lync Server.</span><span class="sxs-lookup"><span data-stu-id="208cd-166">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

10. <span data-ttu-id="208cd-167">Disporre i record di utilizzo PSTN per ottenere prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="208cd-167">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="208cd-168">Per modificare la posizione di un record nell'elenco, selezionare il record utilizzo PSTN e fare clic sulle frecce in su o in giù.</span><span class="sxs-lookup"><span data-stu-id="208cd-168">To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="208cd-169">L'ordine in cui sono elencati i record di utilizzo PSTN nella configurazione trunk è significativo.</span><span class="sxs-lookup"><span data-stu-id="208cd-169">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="208cd-170">Lync Server attraversa l'elenco dall'alto verso il basso.</span><span class="sxs-lookup"><span data-stu-id="208cd-170">Lync Server traverses the list from top to down.</span></span>

    
    </div>

11. <span data-ttu-id="208cd-171">**Abilitare il latching RTP** deve essere selezionato per consentire l'esclusione di elementi multimediali per i client dietro un NAT o un firewall e un SBC che supporta il blocco.</span><span class="sxs-lookup"><span data-stu-id="208cd-171">**Enable RTP Latching** should be selected to enable bypass media for clients behind a NAT or firewall and an SBC that supports latching.</span></span>

12. <span data-ttu-id="208cd-172">**Abilitare la cronologia delle chiamate in avanti** deve essere selezionata per consentire l'invio di informazioni sulla cronologia delle chiamate al peer del gateway del Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="208cd-172">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

13. <span data-ttu-id="208cd-173">**Abilita inoltro P-asserzione-i dati di identità** devono essere selezionati per consentire l'inoltro delle informazioni sull'originatore delle chiamate di Pai tra il lato Mediation Server e il lato gateway (e viceversa), quando presenti.</span><span class="sxs-lookup"><span data-stu-id="208cd-173">**Enable forward P-Asserted-Identity data** should be selected to enable PAI call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

14. <span data-ttu-id="208cd-174">**Abilitare il timer di failover del routing in uscita** deve essere selezionato per consentire il failover veloce.</span><span class="sxs-lookup"><span data-stu-id="208cd-174">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="208cd-175">Il gateway associato a questo trunk può dare notifica entro 10 secondi che sta elaborando una chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="208cd-175">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="208cd-176">La reinstradazione a un altro trunk si verificherà se la notifica non viene ricevuta dal Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="208cd-176">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="208cd-177">Nelle reti in cui la latenza può ritardare il tempo di risposta o il gateway richiede più di 10 secondi per rispondere, il failover veloce deve essere disabilitato.</span><span class="sxs-lookup"><span data-stu-id="208cd-177">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

15. <span data-ttu-id="208cd-178">Opzionale Associa e configura le **regole di traduzione del numero chiamante** per il trunk.</span><span class="sxs-lookup"><span data-stu-id="208cd-178">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="208cd-179">Queste regole di traduzione si applicano al numero chiamante per le chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="208cd-179">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="208cd-180">Per scegliere una o più regole da un elenco di tutte le regole di traduzione disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="208cd-180">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="208cd-181">In **Seleziona regole di traduzione**fare clic sulle regole da associare al trunk e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="208cd-181">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="208cd-182">Per definire una nuova regola di traduzione e associarla al trunk, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="208cd-182">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="208cd-183">Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="208cd-183">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="208cd-184">Per modificare una regola di traduzione già associata al trunk, fare clic sul nome della regola e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="208cd-184">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="208cd-185">Per informazioni dettagliate, vedere [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="208cd-185">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="208cd-186">Per copiare una regola di traduzione esistente da usare come punto di partenza per la definizione di una nuova regola, fare clic sul nome della regola e scegliere **copia**e quindi fare clic su **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="208cd-186">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="208cd-187">Per informazioni dettagliate, vedere [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="208cd-187">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="208cd-188">Per rimuovere una regola di traduzione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="208cd-188">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="sicurezza" alt="security" /><span data-ttu-id="208cd-190">Nota sulla sicurezza:</span><span class="sxs-lookup"><span data-stu-id="208cd-190">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="208cd-191">Non associare regole di traduzione a un trunk se sono state configurate regole di traduzione nel peer trunk associato, perché le due regole potrebbero essere in conflitto.</span><span class="sxs-lookup"><span data-stu-id="208cd-191">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. <span data-ttu-id="208cd-192">Opzionale Associare e configurare **le regole di traduzione dei numeri** per il trunk.</span><span class="sxs-lookup"><span data-stu-id="208cd-192">(Optional) Associate and configure **called number translation rules** for the trunk.</span></span> <span data-ttu-id="208cd-193">Le regole di traduzione si applicano al numero chiamato in una chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="208cd-193">The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="208cd-194">Per scegliere una o più regole da un elenco di tutte le regole di traduzione disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="208cd-194">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="208cd-195">In **Seleziona regole di traduzione**fare clic sulle regole da associare al trunk e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="208cd-195">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="208cd-196">Per definire una nuova regola di traduzione e associarla al trunk, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="208cd-196">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="208cd-197">Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="208cd-197">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="208cd-198">Per modificare una regola di traduzione già associata al trunk, fare clic sul nome della regola e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="208cd-198">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="208cd-199">Per informazioni dettagliate, vedere [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="208cd-199">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="208cd-200">Per copiare una regola di traduzione esistente da usare come punto di partenza per la definizione di una nuova regola, fare clic sul nome della regola e scegliere **copia**e quindi fare clic su **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="208cd-200">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="208cd-201">Per informazioni dettagliate, vedere [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="208cd-201">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="208cd-202">Per rimuovere una regola di traduzione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="208cd-202">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="208cd-203">Non associare regole di traduzione a un trunk se sono state configurate regole di traduzione nel peer trunk associato, perché le due regole potrebbero essere in conflitto.</span><span class="sxs-lookup"><span data-stu-id="208cd-203">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="208cd-204">Verificare che le regole di traduzione del trunk siano disposte nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="208cd-204">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="208cd-205">Per modificare la posizione di una regola nell'elenco, evidenziare il nome della regola e quindi fare clic sulla freccia verso l'alto o verso il basso.</span><span class="sxs-lookup"><span data-stu-id="208cd-205">To change a rule’s position in the list, highlight the rule name, and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="208cd-206">Lync Server attraversa l'elenco delle regole di traduzione dall'alto verso il basso e usa la prima regola che corrisponde al numero selezionato.</span><span class="sxs-lookup"><span data-stu-id="208cd-206">Lync Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="208cd-207">Se si configura un trunk in modo che un numero composto possa corrispondere a più regole di traduzione, assicurarsi che le regole più restrittive siano ordinate al di sopra delle regole meno restrittive.</span><span class="sxs-lookup"><span data-stu-id="208cd-207">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="208cd-208">Se ad esempio è stata inclusa una regola di traduzione che corrisponde a qualsiasi numero di 11 cifre e a una regola di traduzione che corrisponde a solo numeri a 11 cifre che iniziano con + 1425, assicurarsi che la regola che corrisponde a qualsiasi numero di 11 cifre sia ordinata <EM>sotto</EM> la regola più restrittiva.</span><span class="sxs-lookup"><span data-stu-id="208cd-208">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

18. <span data-ttu-id="208cd-209">Al termine della configurazione del trunk, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="208cd-209">When you are finished configuring the trunk, click **OK**.</span></span>

19. <span data-ttu-id="208cd-210">Nella pagina **trunk Configuration** fare clic su **commit**e quindi su **Commit all**.</span><span class="sxs-lookup"><span data-stu-id="208cd-210">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="208cd-211">Ogni volta che si crea o si modifica una configurazione trunk, è necessario eseguire il comando <STRONG>commit tutti</STRONG> per pubblicare la modifica della configurazione.</span><span class="sxs-lookup"><span data-stu-id="208cd-211">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="208cd-212">Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A> nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="208cd-212">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="208cd-213">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="208cd-213">See Also</span></span>


[<span data-ttu-id="208cd-214">Configurare un trunk con il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="208cd-214">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="208cd-215">Definizione delle regole di conversione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="208cd-215">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

