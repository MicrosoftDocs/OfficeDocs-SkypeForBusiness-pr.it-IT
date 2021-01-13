---
title: Componenti e topologie per il controllo di ammissione di chiamata in Skype for business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: Pianificazione del controllo di ammissione di chiamata (CAC) se si dispone di una rete MPLS, un trunk SIP o un gateway PSTN o un PBX di terze parti. Si applica a Skype for Business Server VoIP aziendale.
ms.openlocfilehash: e40525121020259a40f10d90cd79d70aaa749ac3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825846"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a><span data-ttu-id="7c08d-104">Componenti e topologie per il controllo di ammissione di chiamata in Skype for business</span><span class="sxs-lookup"><span data-stu-id="7c08d-104">Components and topologies for call admission control in Skype for Business</span></span>

<span data-ttu-id="7c08d-105">Pianificazione del controllo di ammissione di chiamata (CAC) se si dispone di una rete MPLS, un trunk SIP o un gateway PSTN o un PBX di terze parti.</span><span class="sxs-lookup"><span data-stu-id="7c08d-105">Planning for call admission control (CAC) if you have an MPLS network, a SIP trunk, or a third-party PSTN gateway or PBX.</span></span> <span data-ttu-id="7c08d-106">Si applica a Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="7c08d-106">Applies to Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="7c08d-107">Negli argomenti di questa sezione vengono fornite informazioni sulle considerazioni speciali di cui tenere conto per la distribuzione del servizio Controllo di ammissione di chiamata con diversi tipi di topologie di rete.</span><span class="sxs-lookup"><span data-stu-id="7c08d-107">The topics in this section provide information about special considerations for deploying call admission control (CAC) with various types of network topologies.</span></span>

## <a name="call-admission-control-on-an-mpls-network"></a><span data-ttu-id="7c08d-108">Controllo di ammissione di chiamata su una rete MPLS</span><span class="sxs-lookup"><span data-stu-id="7c08d-108">Call admission control on an MPLS network</span></span>

<span data-ttu-id="7c08d-p103">In una rete MPLS (Multiprotocol Label Switching) tutti i siti sono connessi tramite full mesh, ovvero tutti i siti sono connessi direttamente alla dorsale MPLS del provider di servizi Internet e a ogni sito viene assegnata una larghezza di banda da utilizzare nel cloud MPLS attraverso un collegamento WAN. Non è presente alcun hub di rete o sito centrale per controllare il routing IP. Nella figura seguente viene illustrata una rete semplice basata sulla tecnologia MPLS.</span><span class="sxs-lookup"><span data-stu-id="7c08d-p103">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="7c08d-113">**Rete MPLS di esempio**</span><span class="sxs-lookup"><span data-stu-id="7c08d-113">**Example MPLS network**</span></span>

![CAC con MPLS](../../media/CAC_MPLS_1.jpg)

<span data-ttu-id="7c08d-p104">Per distribuire il controllo di ammissione di chiamata in una rete MPLS, è necessario creare un'area di rete che rappresenti il cloud MPLS e un sito di rete che rappresenti ogni sito satellite MPLS. Nella figura seguente viene illustrato come è consigliabile configurare l'area di rete e i siti di rete per rappresentare la rete MPLS di esempio della figura precedente. I limiti di larghezza di banda totali e quelli di sessione sono quindi basati sulla capacità del collegamento WAN che va da ogni sito di rete all'area di rete che rappresenta il cloud MPLS.</span><span class="sxs-lookup"><span data-stu-id="7c08d-p104">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="7c08d-118">**Area di rete e siti di rete per una rete MPLS**</span><span class="sxs-lookup"><span data-stu-id="7c08d-118">**Network region and network sites for an MPLS network**</span></span>

![Controllo di ammissione di chiamata (CAC) con diagramma MPLS](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a><span data-ttu-id="7c08d-120">Controllo di ammissione di chiamata in un trunk SIP</span><span class="sxs-lookup"><span data-stu-id="7c08d-120">Call admission control on a SIP trunk</span></span>

<span data-ttu-id="7c08d-p105">Per distribuire il servizio Controllo di ammissione di chiamata in un trunk SIP, creare un sito di rete per rappresentare il provider di servizi di telefonia Internet (ITSP). Per applicare i valori dei criteri di larghezza di banda nel trunk SIP, creare criteri tra siti tra il sito di rete dell'organizzazione e il sito di rete creato per rappresentare l'ITSP.</span><span class="sxs-lookup"><span data-stu-id="7c08d-p105">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="7c08d-123">Nella figura seguente è illustrato un esempio di distribuzione del servizio Controllo di ammissione di chiamata in un trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="7c08d-123">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="7c08d-124">**Configurazione del servizio Controllo di ammissione di chiamata in un trunk SIP**</span><span class="sxs-lookup"><span data-stu-id="7c08d-124">**CAC configuration on a SIP trunk**</span></span>

![Diagramma del trunking SIP del controllo di ammissione di chiamata](../../media/CAC_SIP_trunk_1.jpg)

<span data-ttu-id="7c08d-126">Per configurare il servizio Controllo di ammissione di chiamata in un trunk SIP, è necessario eseguire le operazioni seguenti durante la distribuzione del servizio:</span><span class="sxs-lookup"><span data-stu-id="7c08d-126">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1. <span data-ttu-id="7c08d-127">Creare un sito di rete per rappresentare l'ITSP.</span><span class="sxs-lookup"><span data-stu-id="7c08d-127">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="7c08d-128">Associare il sito di rete a un'area di rete appropriata e allocare una larghezza di banda pari a zero per audio e video per il sito di rete.</span><span class="sxs-lookup"><span data-stu-id="7c08d-128">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="7c08d-129">Per informazioni dettagliate, vedere [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7c08d-129">For details, see [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) in the Deployment documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7c08d-130">Per l'ITSP, questa configurazione del sito di rete non è funzionale.</span><span class="sxs-lookup"><span data-stu-id="7c08d-130">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="7c08d-131">I valori dei criteri di larghezza di banda vengono effettivamente applicati nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="7c08d-131">Bandwidth policy values are actually applied in step 2.</span></span>

2. <span data-ttu-id="7c08d-132">Creare un collegamento tra siti per il trunk SIP utilizzando i valori dei parametri rilevanti per il sito creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="7c08d-132">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="7c08d-133">Utilizzare, ad esempio, il nome del sito di rete dell'organizzazione come valore del parametro NetworkSiteID1 e il sito di rete dell'ITSP come valore del parametro NetworkSiteID2.</span><span class="sxs-lookup"><span data-stu-id="7c08d-133">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="7c08d-134">Per informazioni dettagliate, vedere [creare criteri intersito di rete in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) nella documentazione relativa alla distribuzione e [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7c08d-134">For details, see [Create network intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in the Deployment documentation, and [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span></span>

3. <span data-ttu-id="7c08d-135">Ottenere l'indirizzo IP del punto di terminazione multimediale della sessione (SCB, Session Border Controller) dall'ITSP.</span><span class="sxs-lookup"><span data-stu-id="7c08d-135">Get the IP address of the Session Border Controller's (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="7c08d-136">Aggiungere tale indirizzo IP con una subnet mask di 32 al sito di rete che rappresenta l'ITSP.</span><span class="sxs-lookup"><span data-stu-id="7c08d-136">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="7c08d-137">Per informazioni dettagliate, vedere [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="7c08d-137">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="7c08d-138">Controllo di ammissione di chiamata con un PBX o un gateway PSTN di terze parti</span><span class="sxs-lookup"><span data-stu-id="7c08d-138">Call admission control with a third-party PSTN gateway or PBX</span></span>

<span data-ttu-id="7c08d-139">In questo argomento vengono descritti alcuni esempi del modo in cui il controllo di ammissione di chiamata può essere distribuito sul collegamento tra l'interfaccia gateway del Mediation Server e un gateway PSTN (Public Switched Telephone Network) di terze parti o un sistema PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="7c08d-139">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server's gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="7c08d-140">Caso 1: CAC tra il Mediation Server e un gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="7c08d-140">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="7c08d-141">È possibile distribuire il servizio di controllo di ammissione sul collegamento WAN dall'interfaccia del gateway del Mediation Server a un gateway PSTN o PBX di terze parti.</span><span class="sxs-lookup"><span data-stu-id="7c08d-141">CAC can be deployed on the WAN link from the Mediation Server's gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="7c08d-142">**Caso 1: CAC tra il Mediation Server e un gateway PSTN**</span><span class="sxs-lookup"><span data-stu-id="7c08d-142">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

![Caso 1: CAC tra il gateway PSTN di Mediation Server](../../media/CAC_gateways_1.jpg)

<span data-ttu-id="7c08d-144">In questo esempio viene applicato il servizio di controllo di ammissione tra il Mediation Server e un gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="7c08d-144">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="7c08d-145">Se un utente del client Skype for business nel sito di rete 1 inserisce una chiamata PSTN tramite il gateway PSTN nel sito di rete 2, il file multimediale scorre attraverso il collegamento WAN.</span><span class="sxs-lookup"><span data-stu-id="7c08d-145">If a Skype for Business client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="7c08d-146">Pertanto, vengono eseguiti due controlli CAC per ogni sessione PSTN:</span><span class="sxs-lookup"><span data-stu-id="7c08d-146">Therefore, two CAC checks are performed for each PSTN session:</span></span>

- <span data-ttu-id="7c08d-147">Tra l'applicazione client Skype for business e il Mediation Server</span><span class="sxs-lookup"><span data-stu-id="7c08d-147">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="7c08d-148">Tra il Mediation Server e il gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="7c08d-148">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="7c08d-149">Questo metodo funziona sia per le chiamate PSTN in arrivo a un client nel sito di rete 1 che per le chiamate PSTN in uscita provenienti da un'applicazione client nel sito di rete 1.</span><span class="sxs-lookup"><span data-stu-id="7c08d-149">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="7c08d-150">Verificare che la subnet IP a cui appartiene il gateway PSTN sia configurata e associata a sito di rete 2.</span><span class="sxs-lookup"><span data-stu-id="7c08d-150">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="7c08d-151">Verificare che la subnet IP alla quale appartengono entrambe le interfacce del Mediation Server sia configurata e associata al sito di rete 1.</span><span class="sxs-lookup"><span data-stu-id="7c08d-151">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="7c08d-152">Per informazioni dettagliate, vedere [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="7c08d-152">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="7c08d-153">Caso 2: CAC tra il Mediation Server e un PBX di terze parti con il punto di terminazione multimediale</span><span class="sxs-lookup"><span data-stu-id="7c08d-153">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="7c08d-154">Questa configurazione è simile al caso 1.</span><span class="sxs-lookup"><span data-stu-id="7c08d-154">This configuration is similar to Case 1.</span></span> <span data-ttu-id="7c08d-155">In entrambi i casi, il Mediation Server sa quale dispositivo termina i file multimediali all'estremità opposta del collegamento WAN e l'indirizzo IP del gateway PSTN o del PBX con il punto di terminazione multimediale è configurato sul Mediation Server come hop successivo.</span><span class="sxs-lookup"><span data-stu-id="7c08d-155">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="7c08d-156">**Caso 2: CAC tra il Mediation Server e un PBX di terze parti con MTP**</span><span class="sxs-lookup"><span data-stu-id="7c08d-156">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

![Caso 2: CAC tra Mediation Server PBX con MTP](../../media/CAC_gateways_2.jpg)

<span data-ttu-id="7c08d-158">In questo esempio viene applicato il servizio di controllo di ammissione tra il Mediation Server e il sistema PBX/MTP.</span><span class="sxs-lookup"><span data-stu-id="7c08d-158">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="7c08d-159">Se un utente del client Skype for business nel sito di rete 1 inserisce una chiamata PSTN tramite il sistema PBX/MTP che si trova nel sito di rete 2, il file multimediale scorre attraverso il collegamento WAN.</span><span class="sxs-lookup"><span data-stu-id="7c08d-159">If a Skype for Business client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="7c08d-160">Pertanto, per ogni sessione PSTN vengono eseguiti due controlli CAC:</span><span class="sxs-lookup"><span data-stu-id="7c08d-160">Therefore, for each PSTN session two CAC checks are performed:</span></span>

- <span data-ttu-id="7c08d-161">Tra l'applicazione client Skype for business e il Mediation Server</span><span class="sxs-lookup"><span data-stu-id="7c08d-161">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="7c08d-162">Tra il Mediation Server e il sistema PBX/MTP</span><span class="sxs-lookup"><span data-stu-id="7c08d-162">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="7c08d-163">Questo metodo funziona sia per le chiamate PSTN in arrivo a un client nel sito di rete 1 che per le chiamate PSTN in uscita provenienti da un client nel sito di rete 1.</span><span class="sxs-lookup"><span data-stu-id="7c08d-163">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="7c08d-164">Verificare che la subnet IP a cui appartiene il MTP sia configurata e associata al sito di rete 2.</span><span class="sxs-lookup"><span data-stu-id="7c08d-164">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="7c08d-165">Verificare che la subnet IP alla quale appartengono entrambe le interfacce del Mediation Server sia configurata e associata al sito di rete 1.</span><span class="sxs-lookup"><span data-stu-id="7c08d-165">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="7c08d-166">Per informazioni dettagliate, vedere [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="7c08d-166">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="7c08d-167">Caso 3: CAC tra il Mediation Server e un PBX di terze parti senza un punto di terminazione multimediale</span><span class="sxs-lookup"><span data-stu-id="7c08d-167">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="7c08d-168">Il caso 3 è leggermente diverso rispetto ai primi due casi.</span><span class="sxs-lookup"><span data-stu-id="7c08d-168">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="7c08d-169">Se non è presente alcun MTP sul PBX di terze parti, per una richiesta di sessione in uscita al sistema PBX di terze parti, il Mediation Server non sa dove i contenuti multimediali verranno terminati nel limite del PBX.</span><span class="sxs-lookup"><span data-stu-id="7c08d-169">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="7c08d-170">In questo caso, il contenuto multimediale scorre direttamente tra il Mediation Server e il dispositivo endpoint di terze parti.</span><span class="sxs-lookup"><span data-stu-id="7c08d-170">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="7c08d-171">**Caso 3: CAC tra il Mediation Server e un PBX di terze parti senza MTP**</span><span class="sxs-lookup"><span data-stu-id="7c08d-171">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

![Caso 3: CAC tra Mediation Server PBX no MTP](../../media/CAC_gateways_3.jpg)

<span data-ttu-id="7c08d-173">In questo esempio, se un utente del client Skype for business nel sito di rete 1 inserisce una chiamata a un utente tramite il sistema PBX, Mediation Server è in grado di eseguire controlli CAC solo sul lato proxy (tra l'applicazione client Skype for business e il Mediation Server).</span><span class="sxs-lookup"><span data-stu-id="7c08d-173">In this example, if a Skype for Business client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Skype for Business client application and Mediation Server).</span></span> <span data-ttu-id="7c08d-174">Poiché il Mediation Server non dispone di informazioni sul dispositivo endpoint durante la richiesta della sessione, non è possibile eseguire controlli CAC sul collegamento WAN (tra il Mediation Server e l'endpoint di terze parti) prima dello stabilimento di chiamata.</span><span class="sxs-lookup"><span data-stu-id="7c08d-174">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="7c08d-175">Dopo che la sessione è stata stabilita, tuttavia, Mediation Server facilita la contabilità per la larghezza di banda utilizzata nel trunk.</span><span class="sxs-lookup"><span data-stu-id="7c08d-175">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="7c08d-176">Per le chiamate che hanno origine dall'endpoint di terze parti, le informazioni sul dispositivo endpoint sono disponibili al momento della richiesta di sessione e il controllo CAC può essere eseguito su entrambi i lati del Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="7c08d-176">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

> [!NOTE]
> <span data-ttu-id="7c08d-177">Verificare che la subnet IP a cui appartengono i dispositivi endpoint sia configurata e associata a sito di rete 2.</span><span class="sxs-lookup"><span data-stu-id="7c08d-177">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="7c08d-178">Verificare che la subnet IP alla quale appartengono entrambe le interfacce del Mediation Server sia configurata e associata al sito di rete 1.</span><span class="sxs-lookup"><span data-stu-id="7c08d-178">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="7c08d-179">Per informazioni dettagliate, vedere [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="7c08d-179">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>


