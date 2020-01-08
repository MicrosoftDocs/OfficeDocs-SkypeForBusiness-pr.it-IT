---
title: 'Lync Server 2013: configurare un trunk con il bypass multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a trunk with media bypass
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48184959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41f5f254dfd3ad63d3f6390f16837c777bd02a91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a><span data-ttu-id="22b0b-102">Configurare un trunk con il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22b0b-102">Configure a trunk with media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22b0b-103">_**Argomento Ultima modifica:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="22b0b-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="22b0b-104">Seguire questa procedura per configurare un trunk con il bypass multimediale abilitato.</span><span class="sxs-lookup"><span data-stu-id="22b0b-104">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="22b0b-105">Per configurare un trunk con il bypass multimediale disabilitato, vedere [configurare un trunk senza bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="22b0b-105">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span></span> <span data-ttu-id="22b0b-106">Il bypass multimediale è utile quando si vuole ridurre al minimo il numero di server di mediazione distribuiti.</span><span class="sxs-lookup"><span data-stu-id="22b0b-106">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="22b0b-107">In genere, un pool di Mediation Server verrà distribuito in un sito centrale e controllerà i gateway nei siti di succursale.</span><span class="sxs-lookup"><span data-stu-id="22b0b-107">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="22b0b-108">L'abilitazione del bypass multimediale consente alle chiamate PSTN (Public Switched Telephone Network) dei client in siti di succursale di scorrere direttamente attraverso i gateway in questi siti.</span><span class="sxs-lookup"><span data-stu-id="22b0b-108">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="22b0b-109">Le route delle chiamate in uscita di Lync Server 2013 e i criteri VoIP aziendale devono essere configurati correttamente in modo che le chiamate PSTN da client in un sito di succursale vengano indirizzate al gateway appropriato.</span><span class="sxs-lookup"><span data-stu-id="22b0b-109">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="22b0b-110">Ti consigliamo vivamente di abilitare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="22b0b-110">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="22b0b-111">Tuttavia, prima di abilitare il bypass multimediale in un trunk SIP, verificare che il provider trunk SIP completo supporti il bypass multimediale ed è in grado di soddisfare i requisiti per l'abilitazione dello scenario.</span><span class="sxs-lookup"><span data-stu-id="22b0b-111">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="22b0b-112">In particolare, il provider deve avere gli indirizzi IP dei server nella rete interna dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="22b0b-112">Specifically, the provider must have the IP addresses of servers in your organization’s internal network.</span></span> <span data-ttu-id="22b0b-113">Se il provider non supporta questo scenario, il bypass multimediale non avrà esito positivo.</span><span class="sxs-lookup"><span data-stu-id="22b0b-113">If the provider cannot support this scenario, media bypass will not succeed.</span></span> <span data-ttu-id="22b0b-114">Per informazioni dettagliate, vedere [pianificazione di un bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="22b0b-114">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="22b0b-115">Il bypass multimediale non si interagisce con tutti i gateway PSTN (Public Switched Telephone Network), IP-PBX e Session Border Controller (SBC).</span><span class="sxs-lookup"><span data-stu-id="22b0b-115">Media bypass will not interoperate with every public switched telephone network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="22b0b-116">Microsoft ha testato un set di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con Cisco IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="22b0b-116">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="22b0b-117">Il bypass multimediale è supportato solo con prodotti e versioni elencati nel programma Unified Communications Open Interoperability-Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span><span class="sxs-lookup"><span data-stu-id="22b0b-117">Media bypass is supported only with products and versions that are listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="22b0b-118">Una configurazione trunk come descritto di seguito raggruppa un set di parametri applicati ai trunk assegnati a questa configurazione trunk.</span><span class="sxs-lookup"><span data-stu-id="22b0b-118">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration.</span></span> <span data-ttu-id="22b0b-119">Una particolare configurazione trunk può essere portata a livello globale (per tutti i trunk che non dispongono di una configurazione di sito o di pool più specifica) o di un sito o di un pool.</span><span class="sxs-lookup"><span data-stu-id="22b0b-119">A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool.</span></span> <span data-ttu-id="22b0b-120">La configurazione del trunk a livello di pool viene usata per l'ambito di una configurazione trunk specifica in un singolo trunk.</span><span class="sxs-lookup"><span data-stu-id="22b0b-120">The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="22b0b-121">Per configurare un trunk con il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="22b0b-121">To configure a trunk with media bypass</span></span>

1.  <span data-ttu-id="22b0b-122">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="22b0b-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="22b0b-123">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="22b0b-123">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="22b0b-124">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22b0b-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="22b0b-125">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="22b0b-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="22b0b-126">Sulla barra di spostamento sinistra fare clic su **routing vocale**e quindi su **configurazione trunk**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-126">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="22b0b-127">Nella pagina **trunk Configuration** usare uno dei metodi seguenti per configurare un trunk:</span><span class="sxs-lookup"><span data-stu-id="22b0b-127">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="22b0b-128">Fare doppio clic su un trunk esistente, ad esempio il trunk **globale** , per visualizzare la finestra di dialogo **modifica configurazione trunk** .</span><span class="sxs-lookup"><span data-stu-id="22b0b-128">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="22b0b-129">Fare clic su **nuovo**e quindi selezionare un ambito per la nuova configurazione trunk:</span><span class="sxs-lookup"><span data-stu-id="22b0b-129">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="22b0b-130">**Trunk sito:** Scegliere il sito per la configurazione del trunk da **Seleziona un sito**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-130">**Site trunk:** Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="22b0b-131">Tieni presente che se è già stata creata una configurazione trunk per un sito, il sito non viene visualizzato in **Seleziona un sito**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-131">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="22b0b-132">Questa configurazione trunk verrà applicata a tutti i trunk nel sito.</span><span class="sxs-lookup"><span data-stu-id="22b0b-132">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="22b0b-133">**Trunk pool:** Scegliere il nome del trunk a cui si applica la configurazione del trunk.</span><span class="sxs-lookup"><span data-stu-id="22b0b-133">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="22b0b-134">Questo trunk può essere il trunk radice o eventuali trunk aggiuntivi definiti in Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="22b0b-134">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="22b0b-135">In **Seleziona un servizio**fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-135">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="22b0b-136">Tieni presente che se è già stata creata una configurazione trunk per un trunk specifico, il trunk non viene visualizzato in **Seleziona un servizio**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-136">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22b0b-137">Dopo aver selezionato l'ambito della configurazione trunk, non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="22b0b-137">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="22b0b-138">Il campo <STRONG>nome</STRONG> viene prepopolato con il nome del sito o del servizio associato alla configurazione del trunk e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="22b0b-138">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="22b0b-139">Specificare un valore nelle **finestre di dialogo iniziali massime supportate**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-139">Specify a value in **Maximum early dialogs supported**.</span></span> <span data-ttu-id="22b0b-140">Questo è il numero massimo di risposte a forcella un gateway PSTN (IP-PBX) o ITSP session border controller (SBC) pubblico può ricevere un invito inviato al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="22b0b-140">This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server.</span></span> <span data-ttu-id="22b0b-141">Il valore predefinito è 20.</span><span class="sxs-lookup"><span data-stu-id="22b0b-141">The default value is 20.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22b0b-142">Prima di modificare questo valore, consultare il provider di servizi o il produttore di attrezzature per informazioni dettagliate sulle funzionalità del sistema.</span><span class="sxs-lookup"><span data-stu-id="22b0b-142">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

    
    </div>

6.  <span data-ttu-id="22b0b-143">Selezionare una delle opzioni seguenti per il **livello di supporto della crittografia** :</span><span class="sxs-lookup"><span data-stu-id="22b0b-143">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="22b0b-144">**Obbligatorio:** Per proteggere il traffico tra il Mediation Server e il gateway o il PBX (Private Branch Exchange), è necessario usare la crittografia SRTP (Secure Real Time Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="22b0b-144">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="22b0b-145">**Facoltativo:** La crittografia SRTP verrà usata se il provider di servizi o il produttore di attrezzature lo supporta.</span><span class="sxs-lookup"><span data-stu-id="22b0b-145">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="22b0b-146">**Non supportato:** La crittografia SRTP non è supportata dal provider di servizi o dal produttore di attrezzature e quindi non verrà usata.</span><span class="sxs-lookup"><span data-stu-id="22b0b-146">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

7.  <span data-ttu-id="22b0b-147">Selezionare la casella di controllo **Abilita esclusione multimediale** se si vuole che il supporto venga ignorato dal server Mediation per l'elaborazione da parte del peer trunk.</span><span class="sxs-lookup"><span data-stu-id="22b0b-147">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="22b0b-148">Per il corretto funzionamento del bypass multimediale, il gateway PSTN, IP-PBX o ITSP session border controller deve supportare alcune funzionalità.</span><span class="sxs-lookup"><span data-stu-id="22b0b-148">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="22b0b-149">Per informazioni dettagliate, vedere <A href="lync-server-2013-planning-for-media-bypass.md">pianificazione di un bypass multimediale in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="22b0b-149">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="22b0b-150">Selezionare la casella di controllo **elaborazione multimediale centralizzata** se è presente un punto di interruzione del contenuto multimediale noto, ad esempio un gateway PSTN in cui la terminazione multimediale ha lo stesso IP della terminazione di segnalazione.</span><span class="sxs-lookup"><span data-stu-id="22b0b-150">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination).</span></span> <span data-ttu-id="22b0b-151">Deselezionare questa casella di controllo se il trunk non ha un punto di interruzione multimediale noto.</span><span class="sxs-lookup"><span data-stu-id="22b0b-151">Clear this check box if the trunk does not have a well-known media termination point.</span></span>

9.  <span data-ttu-id="22b0b-152">Se il peer trunk supporta la ricezione delle richieste SIP REFER dal Mediation Server, selezionare la casella **di controllo Consenti invio di riferimento al gateway** .</span><span class="sxs-lookup"><span data-stu-id="22b0b-152">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22b0b-153">Se si disattiva questa opzione mentre è selezionata l'opzione <STRONG>Abilita bypass multimediale</STRONG> , sono necessarie altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="22b0b-153">If you disable this option while the <STRONG>Enable media bypass</STRONG> option is selected, additional settings are required.</span></span> <span data-ttu-id="22b0b-154">Se il peer trunk non supporta la ricezione delle richieste SIP REFER dal Mediation Server e il bypass multimediale è abilitato, è necessario eseguire anche il cmdlet <STRONG>Set-CsTrunkConfiguration</STRONG> per disabilitare RTCP per le chiamate attive e detenute, al fine di supportare le condizioni appropriate per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="22b0b-154">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="22b0b-155">Per informazioni dettagliate, vedere la documentazione di <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> .</span><span class="sxs-lookup"><span data-stu-id="22b0b-155">For details, see the <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> documentation.</span></span><BR><span data-ttu-id="22b0b-156">In alternativa, è possibile selezionare <STRONG>Abilita riferimento tramite il controllo delle chiamate di terze parti</STRONG> se si vuole che le chiamate trasferite vengano ignorate da elementi multimediali e il gateway non supporta le richieste di riferimento SIP.</span><span class="sxs-lookup"><span data-stu-id="22b0b-156">Alternatively, you can select <STRONG>Enable refer using third-party-call control</STRONG> if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

    
    </div>

10. <span data-ttu-id="22b0b-157">Opzionale Per abilitare il routing tra trunk, associa e configura i record di utilizzo PSTN alla configurazione del trunk.</span><span class="sxs-lookup"><span data-stu-id="22b0b-157">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="22b0b-158">Gli usi PSTN associati alla configurazione del trunk verranno applicati per tutte le chiamate in arrivo tramite il trunk non proveniente da un endpoint Lync.</span><span class="sxs-lookup"><span data-stu-id="22b0b-158">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint.</span></span> <span data-ttu-id="22b0b-159">Per gestire i record di utilizzo PSTN associati a una configurazione trunk, usare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="22b0b-159">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="22b0b-160">Per selezionare uno o più record da un elenco di tutti i record di utilizzo PSTN disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-160">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="22b0b-161">Evidenziare i record che si desidera associare alla configurazione del trunk e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-161">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="22b0b-162">Per rimuovere un record di utilizzo PSTN dalla configurazione del trunk, selezionare il record e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-162">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="22b0b-163">Per definire un nuovo record di utilizzo PSTN e associarlo alla configurazione del trunk, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="22b0b-163">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="22b0b-164">Fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-164">Click **New**.</span></span>
        
        2.  <span data-ttu-id="22b0b-165">Nel campo **nome** specificare un nome descrittivo per il record univoco.</span><span class="sxs-lookup"><span data-stu-id="22b0b-165">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="22b0b-166">Il nome del record utilizzo PSTN deve essere univoco all'interno della distribuzione VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="22b0b-166">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="22b0b-167">Dopo il salvataggio del record, il campo <STRONG>nome</STRONG> non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="22b0b-167">After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="22b0b-168">Usare uno dei metodi seguenti per associare e configurare le route per il record di utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="22b0b-168">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="22b0b-169">Per selezionare una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-169">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="22b0b-170">Evidenziare le route da associare al record di utilizzo PSTN e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-170">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="22b0b-171">Per rimuovere una route dal record utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-171">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="22b0b-172">Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-172">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="22b0b-173">Per informazioni dettagliate, vedere [creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="22b0b-173">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="22b0b-174">Per modificare una route associata a questo record di utilizzo PSTN, selezionare la route e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-174">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="22b0b-175">Per informazioni dettagliate, vedere [modificare una route vocale in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="22b0b-175">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="22b0b-176">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-176">Click **OK**.</span></span>
    
      - <span data-ttu-id="22b0b-177">Per modificare un record di utilizzo PSTN già associato alla configurazione del trunk, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="22b0b-177">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="22b0b-178">Selezionare il record di utilizzo PSTN che si vuole modificare e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-178">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="22b0b-179">Usare uno dei metodi seguenti per associare e configurare le route per il record di utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="22b0b-179">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="22b0b-180">Per selezionare una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-180">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="22b0b-181">Evidenziare le route da associare al record di utilizzo PSTN e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-181">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="22b0b-182">Per rimuovere una route dal record utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-182">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="22b0b-183">Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-183">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="22b0b-184">Per informazioni dettagliate, vedere [creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="22b0b-184">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="22b0b-185">Per modificare una route associata a questo record di utilizzo PSTN, selezionare la route e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-185">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="22b0b-186">Per informazioni dettagliate, vedere [modificare una route vocale in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="22b0b-186">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="22b0b-187">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-187">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="22b0b-188">È importante associare i record di utilizzo PSTN in base al peer di Mediation Server associato al trunk configurato.</span><span class="sxs-lookup"><span data-stu-id="22b0b-188">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="22b0b-189">Se il peer di Mediation Server è un gateway PSTN o un SBC (Session Border Controller), è consigliabile che la configurazione trunk non sia associata a un record di utilizzo PSTN che si indirizza a una destinazione PSTN o a qualsiasi altro sistema downstream connesso tramite Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22b0b-189">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

11. <span data-ttu-id="22b0b-190">Disporre i record di utilizzo PSTN per ottenere prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="22b0b-190">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="22b0b-191">Per modificare la posizione di un record nell'elenco, selezionare il record utilizzo PSTN e fare clic sulle frecce in su o in giù.</span><span class="sxs-lookup"><span data-stu-id="22b0b-191">To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="22b0b-192">L'ordine in cui sono elencati i record di utilizzo PSTN nella configurazione trunk è significativo.</span><span class="sxs-lookup"><span data-stu-id="22b0b-192">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="22b0b-193">Lync Server attraversa l'elenco dall'alto verso il basso.</span><span class="sxs-lookup"><span data-stu-id="22b0b-193">Lync Server traverses the list from top to down.</span></span>

    
    </div>

12. <span data-ttu-id="22b0b-194">**Abilitare il latching RTP** deve essere selezionato per consentire l'esclusione di elementi multimediali per i client dietro un NAT (Network Address Translation) o un firewall e un SBC che supporta il blocco.</span><span class="sxs-lookup"><span data-stu-id="22b0b-194">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

13. <span data-ttu-id="22b0b-195">**Abilitare la cronologia delle chiamate in avanti** deve essere selezionata per consentire l'invio di informazioni sulla cronologia delle chiamate al peer del gateway del Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="22b0b-195">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

14. <span data-ttu-id="22b0b-196">**Abilita inoltro p-asserzione-i dati di identità** devono essere selezionati per consentire l'inoltro delle informazioni sull'origine delle chiamate p-Asserted-Identity (PAI) tra il lato Mediation Server e il lato gateway (e viceversa), quando presenti.</span><span class="sxs-lookup"><span data-stu-id="22b0b-196">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

15. <span data-ttu-id="22b0b-197">**Abilitare il timer di failover del routing in uscita** deve essere selezionato per consentire il failover veloce.</span><span class="sxs-lookup"><span data-stu-id="22b0b-197">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="22b0b-198">Il gateway associato a questo trunk può dare notifica entro 10 secondi che sta elaborando una chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="22b0b-198">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="22b0b-199">La reinstradazione a un altro trunk si verificherà se la notifica non viene ricevuta dal Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="22b0b-199">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="22b0b-200">Nelle reti in cui la latenza può ritardare il tempo di risposta o il gateway richiede più di 10 secondi per rispondere, il failover veloce deve essere disabilitato.</span><span class="sxs-lookup"><span data-stu-id="22b0b-200">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

16. <span data-ttu-id="22b0b-201">Opzionale Associa e configura le **regole di traduzione del numero chiamante** per il trunk.</span><span class="sxs-lookup"><span data-stu-id="22b0b-201">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="22b0b-202">Queste regole di traduzione si applicano al numero chiamante per le chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="22b0b-202">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="22b0b-203">Per scegliere una o più regole da un elenco di tutte le regole di traduzione disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-203">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="22b0b-204">In **Seleziona regole di traduzione**fare clic sulle regole da associare al trunk e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-204">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="22b0b-205">Per definire una nuova regola di traduzione e associarla al trunk, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-205">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="22b0b-206">Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="22b0b-206">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="22b0b-207">Per modificare una regola di traduzione già associata al trunk, fare clic sul nome della regola e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-207">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="22b0b-208">Per informazioni dettagliate, vedere [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="22b0b-208">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="22b0b-209">Per copiare una regola di traduzione esistente da usare come punto di partenza per la definizione di una nuova regola, fare clic sul nome della regola e scegliere **copia**e quindi fare clic su **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-209">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="22b0b-210">Per informazioni dettagliate, vedere [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="22b0b-210">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="22b0b-211">Per rimuovere una regola di traduzione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-211">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="22b0b-212">Non associare regole di traduzione a un trunk se sono state configurate regole di traduzione nel peer trunk associato, perché le due regole potrebbero essere in conflitto.</span><span class="sxs-lookup"><span data-stu-id="22b0b-212">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="22b0b-213">Opzionale Associare e configurare **le regole di traduzione dei numeri** per il trunk.</span><span class="sxs-lookup"><span data-stu-id="22b0b-213">(Optional) Associate and configure **called number translation rules** for the trunk.</span></span> <span data-ttu-id="22b0b-214">Le regole di traduzione si applicano al numero chiamato in una chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="22b0b-214">The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="22b0b-215">Per scegliere una o più regole da un elenco di tutte le regole di traduzione disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-215">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="22b0b-216">In **Seleziona regole di traduzione**fare clic sulle regole da associare al trunk e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-216">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="22b0b-217">Per definire una nuova regola di traduzione e associarla al trunk, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-217">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="22b0b-218">Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="22b0b-218">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="22b0b-219">Per modificare una regola di traduzione già associata al trunk, fare clic sul nome della regola e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-219">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="22b0b-220">Per informazioni dettagliate, vedere [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="22b0b-220">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="22b0b-221">Per copiare una regola di traduzione esistente da usare come punto di partenza per la definizione di una nuova regola, fare clic sul nome della regola e scegliere **copia**e quindi fare clic su **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-221">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="22b0b-222">Per informazioni dettagliate, vedere [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="22b0b-222">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="22b0b-223">Per rimuovere una regola di traduzione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-223">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="22b0b-224">Non associare regole di traduzione a un trunk se sono state configurate regole di traduzione nel peer trunk associato, perché le due regole potrebbero essere in conflitto.</span><span class="sxs-lookup"><span data-stu-id="22b0b-224">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

18. <span data-ttu-id="22b0b-225">Verificare che le regole di traduzione del trunk siano disposte nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="22b0b-225">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="22b0b-226">Per modificare la posizione di una regola nell'elenco, evidenziare il nome della regola e quindi fare clic sulla freccia in su o in giù.</span><span class="sxs-lookup"><span data-stu-id="22b0b-226">To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="22b0b-227">Lync Server 2013 attraversa l'elenco delle regole di traduzione dall'alto verso il basso e usa la prima regola che corrisponde al numero selezionato.</span><span class="sxs-lookup"><span data-stu-id="22b0b-227">Lync Server 2013 traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="22b0b-228">Se si configura un trunk in modo che un numero composto possa corrispondere a più regole di traduzione, assicurarsi che le regole più restrittive siano ordinate al di sopra delle regole meno restrittive.</span><span class="sxs-lookup"><span data-stu-id="22b0b-228">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="22b0b-229">Se ad esempio è stata inclusa una regola di traduzione che corrisponde a qualsiasi numero di 11 cifre e a una regola di traduzione che corrisponde a solo numeri a 11 cifre che iniziano con + 1425, assicurarsi che la regola che corrisponde a qualsiasi numero di 11 cifre sia ordinata <EM>sotto</EM> la regola più restrittiva.</span><span class="sxs-lookup"><span data-stu-id="22b0b-229">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

19. <span data-ttu-id="22b0b-230">Al termine della configurazione del trunk, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-230">When you are finished configuring the trunk, click **OK**.</span></span>

20. <span data-ttu-id="22b0b-231">Nella pagina **trunk Configuration** fare clic su **commit**e quindi su **Commit all**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-231">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22b0b-232">Ogni volta che si crea o si modifica una configurazione trunk, è necessario eseguire il comando <STRONG>commit tutti</STRONG> per pubblicare la modifica della configurazione.</span><span class="sxs-lookup"><span data-stu-id="22b0b-232">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="22b0b-233">Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A> nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="22b0b-233">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

<span data-ttu-id="22b0b-234">Dopo aver configurato il trunk, continuare a configurare il bypass multimediale scegliendo tra le opzioni di bypass multimediale globale, come descritto in [Opzioni di bypass multimediale globale in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="22b0b-234">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Global media bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="22b0b-235">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22b0b-235">See Also</span></span>


[<span data-ttu-id="22b0b-236">Configurare un trunk senza bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22b0b-236">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[<span data-ttu-id="22b0b-237">Configurare il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22b0b-237">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="22b0b-238">Opzioni di bypass multimediale globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22b0b-238">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="22b0b-239">Definizione delle regole di conversione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22b0b-239">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

