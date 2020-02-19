---
title: 'Lync Server 2013: configurare un trunk con bypass multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk with media bypass
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48184959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fa619262aee2b1342dce6f211eec7ff31aabe62
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a><span data-ttu-id="0a01d-102">Configurare un trunk con bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a01d-102">Configure a trunk with media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a01d-103">_**Ultimo argomento modificato:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="0a01d-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="0a01d-104">Seguire questa procedura per configurare un trunk con bypass multimediale abilitato.</span><span class="sxs-lookup"><span data-stu-id="0a01d-104">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="0a01d-105">Per configurare un trunk con bypass multimediale disabilitato, vedere [Configure a Trunk Without Media Bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="0a01d-105">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span></span> <span data-ttu-id="0a01d-106">La funzionalità bypass multimediale è utile se si desidera ridurre il numero dei Mediation Server distribuiti.</span><span class="sxs-lookup"><span data-stu-id="0a01d-106">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="0a01d-107">Un pool Mediation Server viene in genere distribuito in un sito centrale e controlla i gateway nei siti di succursale.</span><span class="sxs-lookup"><span data-stu-id="0a01d-107">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="0a01d-108">Abilitando il bypass multimediale, gli elementi multimediali per chiamate PSTN da client dei siti di succursale possono attraversare direttamente i gateway di tali siti.</span><span class="sxs-lookup"><span data-stu-id="0a01d-108">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="0a01d-109">Lync Server 2013 le route delle chiamate in uscita e i criteri VoIP aziendale devono essere adeguatamente configurati in modo che le chiamate PSTN dai client in un sito di succursale vengano instradate al gateway appropriato.</span><span class="sxs-lookup"><span data-stu-id="0a01d-109">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="0a01d-110">Si consiglia di abilitare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="0a01d-110">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="0a01d-111">Tuttavia, prima di abilitare il bypass multimediale su un trunk SIP, verificare che il provider trunk SIP qualificato supporti il bypass multimediale ed è in grado di soddisfare i requisiti per l'attivazione corretta dello scenario.</span><span class="sxs-lookup"><span data-stu-id="0a01d-111">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="0a01d-112">In particolare, il provider deve disporre degli indirizzi IP dei server nella rete interna dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0a01d-112">Specifically, the provider must have the IP addresses of servers in your organization’s internal network.</span></span> <span data-ttu-id="0a01d-113">Se il provider non è in grado di supportare questo scenario, non sarà possibile utilizzare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="0a01d-113">If the provider cannot support this scenario, media bypass will not succeed.</span></span> <span data-ttu-id="0a01d-114">Per informazioni dettagliate, vedere [Planning for Media Bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="0a01d-114">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0a01d-115">Il bypass multimediale non interagisce con tutti i gateway PSTN (Public Switched Telephone Network), IP-PBX e Session Border Controller (SBC).</span><span class="sxs-lookup"><span data-stu-id="0a01d-115">Media bypass will not interoperate with every public switched telephone network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="0a01d-116">Microsoft ha testato una serie di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con i sistemi IP-PBX Cisco.</span><span class="sxs-lookup"><span data-stu-id="0a01d-116">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="0a01d-117">Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span><span class="sxs-lookup"><span data-stu-id="0a01d-117">Media bypass is supported only with products and versions that are listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="0a01d-118">Una configurazione trunk come descritto di seguito raggruppa un insieme di parametri applicati ai trunk assegnati alla configurazione del trunk.</span><span class="sxs-lookup"><span data-stu-id="0a01d-118">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration.</span></span> <span data-ttu-id="0a01d-119">Per una determinata configurazione trunk è possibile specificare un ambito globale (corrispondente a tutti i trunk che non presentano una configurazione di sito o di pool più specifica) o un ambito di sito o di pool.</span><span class="sxs-lookup"><span data-stu-id="0a01d-119">A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool.</span></span> <span data-ttu-id="0a01d-120">La configurazione trunk a livello di pool viene usata per definire un singolo trunk come ambito di una determinata configurazione trunk.</span><span class="sxs-lookup"><span data-stu-id="0a01d-120">The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="0a01d-121">Per configurare un trunk con bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="0a01d-121">To configure a trunk with media bypass</span></span>

1.  <span data-ttu-id="0a01d-122">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0a01d-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="0a01d-123">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="0a01d-123">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="0a01d-124">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0a01d-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0a01d-125">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0a01d-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0a01d-126">Nella barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Configurazione trunk**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-126">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="0a01d-127">Nella pagina **Configurazione trunk** utilizzare uno dei metodi seguenti per configurare un trunk:</span><span class="sxs-lookup"><span data-stu-id="0a01d-127">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="0a01d-128">Fare doppio clic su un trunk esistente, ad esempio il trunk **Globale**, per visualizzare la finestra di dialogo **Modifica configurazione trunk**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-128">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="0a01d-129">Fare clic su **Nuovo** e quindi selezionare un ambito per la nuova configurazione trunk:</span><span class="sxs-lookup"><span data-stu-id="0a01d-129">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="0a01d-130">**Trunk del sito:** Scegliere il sito per la configurazione del trunk da **Seleziona un sito**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-130">**Site trunk:** Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="0a01d-131">Si noti che se è già stata creata una configurazione trunk per un sito, tale sito non verrà visualizzato in **Seleziona un sito**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-131">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="0a01d-132">La configurazione trunk verrà applicata a tutti i trunk presenti nel sito.</span><span class="sxs-lookup"><span data-stu-id="0a01d-132">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="0a01d-133">**Trunk del pool:** Scegliere il nome del trunk a cui si applica la configurazione del trunk.</span><span class="sxs-lookup"><span data-stu-id="0a01d-133">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="0a01d-134">Questo trunk può essere il trunk radice o qualsiasi trunk aggiuntivo definito in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="0a01d-134">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="0a01d-135">Da **Seleziona un servizio**, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-135">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="0a01d-136">Si noti che se è già stata creata una configurazione trunk per un trunk specifico, tale trunk non verrà visualizzato in **Seleziona un servizio**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-136">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0a01d-137">Dopo aver selezionato l'ambito della configurazione trunk, non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="0a01d-137">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="0a01d-138">Il campo <STRONG>Nome</STRONG> è già compilato con il nome del sito o del servizio associato alla configurazione trunk e non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="0a01d-138">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="0a01d-139">Specificare un valore nelle **finestre di dialogo massime iniziali supportate**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-139">Specify a value in **Maximum early dialogs supported**.</span></span> <span data-ttu-id="0a01d-140">Questo è il numero massimo di risposte a forcella che un gateway PSTN (Public Switched Telephone Network), un IP-PBX o un session border controller (SBC) di ITSP può ricevere a un invito inviato al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="0a01d-140">This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server.</span></span> <span data-ttu-id="0a01d-141">Il valore predefinito è 20.</span><span class="sxs-lookup"><span data-stu-id="0a01d-141">The default value is 20.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0a01d-142">Prima di modificare questo valore, consultare il provider di servizi o il produttore delle apparecchiature per informazioni più dettagliate sulle capacità del sistema in uso.</span><span class="sxs-lookup"><span data-stu-id="0a01d-142">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

    
    </div>

6.  <span data-ttu-id="0a01d-143">Selezionare una delle opzioni di **Livello di supporto crittografia** seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a01d-143">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="0a01d-144">**Obbligatorio:** È necessario utilizzare la crittografia SRTP (Secure Real-Time Transport Protocol) per proteggere il traffico tra il Mediation Server e il gateway o il PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="0a01d-144">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="0a01d-145">**Facoltativo:** La crittografia SRTP verrà utilizzata se il provider di servizi o il produttore di apparecchiature lo supporta.</span><span class="sxs-lookup"><span data-stu-id="0a01d-145">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="0a01d-146">**Non supportato:** La crittografia SRTP non è supportata dal provider di servizi o dal produttore dell'attrezzatura e pertanto non verrà utilizzata.</span><span class="sxs-lookup"><span data-stu-id="0a01d-146">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

7.  <span data-ttu-id="0a01d-147">Selezionare la casella di controllo **Abilita bypass multimediale** se si desidera che gli elementi multimediali ignorino il Mediation Server per l'elaborazione da parte del trunk peer.</span><span class="sxs-lookup"><span data-stu-id="0a01d-147">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0a01d-148">Per un corretto funzionamento del bypass multimediale, è necessario che il gateway PSTN, il sistema IP-PBX o il Session Border Controller supporti determinate funzionalità.</span><span class="sxs-lookup"><span data-stu-id="0a01d-148">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="0a01d-149">Per informazioni dettagliate, vedere <A href="lync-server-2013-planning-for-media-bypass.md">Planning for Media Bypass in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="0a01d-149">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="0a01d-p111">Selezionare la casella di controllo **Elaborazione multimediale centralizzata** se esiste un punto di terminazione multimediale noto, ad esempio un gateway PSTN in cui la terminazione multimediale ha lo stesso IP della terminazione di segnalazione. Deselezionare la casella di controllo se il trunk non dispone di un punto di terminazione multimediale noto.</span><span class="sxs-lookup"><span data-stu-id="0a01d-p111">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

9.  <span data-ttu-id="0a01d-152">Se il peer trunk supporta la ricezione di richieste SIP REFER dal Mediation Server, selezionare la casella **di controllo Abilita l'invio di fare riferimento al gateway** .</span><span class="sxs-lookup"><span data-stu-id="0a01d-152">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0a01d-153">Se si disabilita questa opzione mentre è selezionata l'opzione <STRONG>Abilita bypass multimediale</STRONG> saranno necessarie ulteriori impostazioni.</span><span class="sxs-lookup"><span data-stu-id="0a01d-153">If you disable this option while the <STRONG>Enable media bypass</STRONG> option is selected, additional settings are required.</span></span> <span data-ttu-id="0a01d-154">Se il trunk peer non supporta la ricezione di richieste SIP REFER dal Mediation Server ed è abilitato il bypass multimediale, sarà inoltre necessario eseguire il cmdlet <STRONG>Set-CsTrunkConfiguration</STRONG> per disabilitare RTCP per le chiamate attive e in attesa in modo da supportare le condizioni appropriate per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="0a01d-154">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="0a01d-155">Per informazioni dettagliate, vedere la documentazione di <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> .</span><span class="sxs-lookup"><span data-stu-id="0a01d-155">For details, see the <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> documentation.</span></span><BR><span data-ttu-id="0a01d-156">In alternativa, è possibile selezionare <STRONG>Abilita fare riferimento utilizzando un controllo delle chiamate di terze parti</STRONG> se si desidera che le chiamate trasferite vengano ignorate tramite il supporto e il gateway non supporta le richieste SIP REFER.</span><span class="sxs-lookup"><span data-stu-id="0a01d-156">Alternatively, you can select <STRONG>Enable refer using third-party-call control</STRONG> if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

    
    </div>

10. <span data-ttu-id="0a01d-p113">(Facoltativo) Per abilitare il routing tra trunk, associare e configurare i record utilizzo PSTN a questa configurazione trunk. Gli utilizzi PSTN associati alla configurazione trunk verranno applicati per tutte le chiamate in arrivo tramite il trunk che non è originato da un endpoint Lync. Per gestire i record utilizzo PSTN associati a una configurazione trunk, usare uno di questi metodi:</span><span class="sxs-lookup"><span data-stu-id="0a01d-p113">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration. The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint. To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="0a01d-160">Per selezionare uno o più record da un elenco di tutti i record di utilizzo PSTN disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-160">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="0a01d-161">Evidenziare i record da associare a questa configurazione trunk e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-161">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="0a01d-162">Per rimuovere un record utilizzo PSTN da questa configurazione trunk, selezionare il record e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-162">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="0a01d-163">Per definire un nuovo record utilizzo PSTN e associarlo a questa configurazione trunk, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a01d-163">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="0a01d-164">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-164">Click **New**.</span></span>
        
        2.  <span data-ttu-id="0a01d-165">Nel campo **Nome** specificare un nome descrittivo univoco per il record.</span><span class="sxs-lookup"><span data-stu-id="0a01d-165">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="0a01d-p115">Il nome del record di utilizzo PSTN deve essere univoco all'interno della distribuzione di VoIP aziendale. Dopo il salvataggio del record, il campo <STRONG>Nome</STRONG> non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="0a01d-p115">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="0a01d-168">Per associare e configurare le route per questo record utilizzo PSTN, usare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a01d-168">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="0a01d-169">Per selezionare una o più route dall'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-169">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="0a01d-170">Evidenziare le route da associare a questo record utilizzo PSTN e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-170">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="0a01d-171">Per rimuovere una route dal record utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-171">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="0a01d-172">Per definire una nuova route e associarla a questo record utilizzo PSTN, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-172">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="0a01d-173">Per informazioni dettagliate, vedere [Create a Voice Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="0a01d-173">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="0a01d-174">Per modificare una route associata a questo record utilizzo PSTN, selezionare la route e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-174">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="0a01d-175">Per ulteriori informazioni, vedere [Modify a Voice Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="0a01d-175">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="0a01d-176">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-176">Click **OK**.</span></span>
    
      - <span data-ttu-id="0a01d-177">Per modificare un record utilizzo PSTN già associato a questa configurazione trunk, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a01d-177">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="0a01d-178">Selezionare il record utilizzo PSTN da modificare e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-178">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="0a01d-179">Per associare e configurare le route per questo record utilizzo PSTN, usare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a01d-179">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="0a01d-180">Per selezionare una o più route dall'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-180">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="0a01d-181">Evidenziare le route da associare a questo record utilizzo PSTN e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-181">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="0a01d-182">Per rimuovere una route dal record utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-182">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="0a01d-183">Per definire una nuova route e associarla a questo record utilizzo PSTN, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-183">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="0a01d-184">Per informazioni dettagliate, vedere [Create a Voice Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="0a01d-184">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="0a01d-185">Per modificare una route associata a questo record utilizzo PSTN, selezionare la route e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-185">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="0a01d-186">Per ulteriori informazioni, vedere [Modify a Voice Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="0a01d-186">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="0a01d-187">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-187">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0a01d-188">È importante associare i record di utilizzo PSTN in base al peer Mediation Server associato al trunk configurato.</span><span class="sxs-lookup"><span data-stu-id="0a01d-188">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="0a01d-189">Se il peer Mediation Server è un gateway PSTN o un session border controller (SBC), è consigliabile che la configurazione trunk non sia associata a un record di utilizzo PSTN che si incammini su una destinazione PSTN o su qualsiasi altro sistema downstream connesso tramite Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0a01d-189">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

11. <span data-ttu-id="0a01d-p123">Organizzare i record utilizzo PSTN in modo da ottenere prestazioni ottimali. Per modificare la posizione di un record nell'elenco, selezionare il record utilizzo PSTN e fare clic sulle frecce verso l'alto o verso il basso.</span><span class="sxs-lookup"><span data-stu-id="0a01d-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0a01d-192">L'ordine in cui i record utilizzo PSTN sono elencati nella configurazione trunk è significativo.</span><span class="sxs-lookup"><span data-stu-id="0a01d-192">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="0a01d-193">Lync Server attraversa l'elenco dall'alto verso il basso.</span><span class="sxs-lookup"><span data-stu-id="0a01d-193">Lync Server traverses the list from top to down.</span></span>

    
    </div>

12. <span data-ttu-id="0a01d-194">**Abilitare il latching RTP** deve essere selezionato per abilitare il bypass multimediale per i client dietro una NAT (Network Address Translation) o un firewall e un SBC che supporta l'aggancio.</span><span class="sxs-lookup"><span data-stu-id="0a01d-194">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

13. <span data-ttu-id="0a01d-195">**Abilitare la cronologia delle chiamate inoltrate** per consentire l'invio delle informazioni sulla cronologia delle chiamate al peer gateway del Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="0a01d-195">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

14. <span data-ttu-id="0a01d-196">**Abilitare l'inoltro dei dati di identità p-Asserted-Identity** per abilitare l'inoltro delle informazioni sull'originatore delle chiamate di p-Asserted-Identity (PAI) tra il lato Mediation Server e il lato gateway (e viceversa), se presente.</span><span class="sxs-lookup"><span data-stu-id="0a01d-196">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

15. <span data-ttu-id="0a01d-197">Per abilitare il failover rapido, selezionare **Abilita timer di failover del routing in uscita**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-197">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="0a01d-198">Il gateway associato a questo trunk può inviare una notifica entro 10 secondi dall'inizio dell'elaborazione di una chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="0a01d-198">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="0a01d-199">Se la notifica non viene ricevuta dal Mediation Server, il reinstradamento a un altro trunk si verificherà.</span><span class="sxs-lookup"><span data-stu-id="0a01d-199">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="0a01d-200">Nelle reti in cui la latenza potrebbe ritardare il tempo di risposta o il gateway impiega più di 10 secondi per rispondere, è consigliabile disabilitare il failover rapido.</span><span class="sxs-lookup"><span data-stu-id="0a01d-200">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

16. <span data-ttu-id="0a01d-201">(Facoltativo) Associare e configurare le **Regole di conversione per il numero del chiamante** per il trunk.</span><span class="sxs-lookup"><span data-stu-id="0a01d-201">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="0a01d-202">Tali regole sono applicabili al numero del chiamante per le chiamate in uscita.</span><span class="sxs-lookup"><span data-stu-id="0a01d-202">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="0a01d-203">Per scegliere una o più regole da un elenco di tutte le regole di conversione disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-203">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="0a01d-204">In **Seleziona regole di conversione** fare clic sulle regole da associare al trunk e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-204">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="0a01d-205">Per definire una nuova regola di conversione e associarla al trunk, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-205">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="0a01d-206">Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0a01d-206">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="0a01d-207">Per modificare una regola di conversione già associata al trunk, fare clic sul nome della regola e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-207">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="0a01d-208">Per informazioni dettagliate, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0a01d-208">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="0a01d-209">Per copiare una regola di conversione esistente in modo da usarla come punto di partenza per definire una nuova regola, fare clic sul nome della regola, su **Copia** e quindi su **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-209">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="0a01d-210">Per informazioni dettagliate, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="0a01d-210">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="0a01d-211">Per rimuovere una regola di conversione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-211">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="0a01d-212">Non associare regole di conversione a un trunk se nel peer trunk associato sono già configurate regole di conversione, poiché potrebbe verificarsi un conflitto tra le due regole.</span><span class="sxs-lookup"><span data-stu-id="0a01d-212">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="0a01d-p131">(Facoltativo) Associare e configurare le **Regole di conversione per il numero chiamato** per il trunk. Tali regole sono applicabili al numero chiamato in una chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="0a01d-p131">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="0a01d-215">Per scegliere una o più regole da un elenco di tutte le regole di conversione disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-215">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="0a01d-216">In **Seleziona regole di conversione** fare clic sulle regole da associare al trunk e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-216">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="0a01d-217">Per definire una nuova regola di conversione e associarla al trunk, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-217">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="0a01d-218">Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0a01d-218">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="0a01d-219">Per modificare una regola di conversione già associata al trunk, fare clic sul nome della regola e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-219">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="0a01d-220">Per informazioni dettagliate, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0a01d-220">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="0a01d-221">Per copiare una regola di conversione esistente in modo da usarla come punto di partenza per definire una nuova regola, fare clic sul nome della regola, su **Copia** e quindi su **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-221">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="0a01d-222">Per informazioni dettagliate, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="0a01d-222">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="0a01d-223">Per rimuovere una regola di conversione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-223">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="0a01d-224">Non associare regole di conversione a un trunk se sono state configurate regole di conversione nel peer trunk associato, perché le due regole potrebbero essere in conflitto.</span><span class="sxs-lookup"><span data-stu-id="0a01d-224">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

18. <span data-ttu-id="0a01d-225">Verificare che le regole di conversione del trunk siano disposte nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="0a01d-225">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="0a01d-226">Per modificare la posizione di una regola nell'elenco, evidenziare il nome della regola e fare clic sulla freccia su o giù.</span><span class="sxs-lookup"><span data-stu-id="0a01d-226">To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0a01d-227">Lync Server 2013 attraversa l'elenco delle regole di conversione dall'alto verso il basso e utilizza la prima regola che corrisponde al numero composto.</span><span class="sxs-lookup"><span data-stu-id="0a01d-227">Lync Server 2013 traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="0a01d-228">Se si configura un trunk in modo che un numero che viene composto possa soddisfare più regole di conversione, verificare che le regole più restrittive siano elencate al di sopra di quelle meno restrittive.</span><span class="sxs-lookup"><span data-stu-id="0a01d-228">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="0a01d-229">Se ad esempio sono state incluse una regola di conversione per qualsiasi numero di 11 cifre e una regola di conversione solo per i numeri di 11 cifre che iniziano con +1425, verificare che la regola per i numeri di 11 cifre sia elencata <EM>al di sotto</EM> della regola più restrittiva.</span><span class="sxs-lookup"><span data-stu-id="0a01d-229">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

19. <span data-ttu-id="0a01d-230">Dopo aver terminato la configurazione del trunk, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-230">When you are finished configuring the trunk, click **OK**.</span></span>

20. <span data-ttu-id="0a01d-231">Nella pagina **Configurazione trunk** fare clic su **Commit** e quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="0a01d-231">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0a01d-232">Ogni volta che si crea o si modifica una configurazione trunk, è necessario eseguire il comando <STRONG>Salva tutto</STRONG> per pubblicare la modifica apportata alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="0a01d-232">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="0a01d-233">Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="0a01d-233">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

<span data-ttu-id="0a01d-234">Dopo aver configurato il trunk, continuare a configurare il bypass multimediale scegliendo tra le opzioni di bypass multimediale globale, come descritto in [Global Media Bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0a01d-234">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Global media bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0a01d-235">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a01d-235">See Also</span></span>


[<span data-ttu-id="0a01d-236">Configurare un trunk senza bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a01d-236">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[<span data-ttu-id="0a01d-237">Configurare il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a01d-237">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="0a01d-238">Opzioni di bypass multimediale globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a01d-238">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="0a01d-239">Definizione delle regole di conversione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a01d-239">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

