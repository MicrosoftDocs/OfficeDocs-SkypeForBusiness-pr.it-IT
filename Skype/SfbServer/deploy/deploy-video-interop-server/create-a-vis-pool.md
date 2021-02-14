---
title: Creare un pool VIS in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Riepilogo: creare un pool di Video Interop Server in Skype for Business Server utilizzando Generatore di topologie.'
ms.openlocfilehash: 7c6f45b232151d99cbce169826c8110cf4a8d494
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802056"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a><span data-ttu-id="bc6a8-103">Creare un pool VIS in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bc6a8-103">Create a VIS pool in Skype for Business Server</span></span>
 
<span data-ttu-id="bc6a8-104">**Riepilogo:** Creare un pool di Video Interop Server in Skype for Business Server usando Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="bc6a8-105">Creare un pool VIS o VIS tramite Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="bc6a8-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="bc6a8-106">Aprire Generatore di topologie nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="bc6a8-107">Nel riquadro sinistro di Generatore di topologie fare clic con il pulsante destro del mouse su **Pool di Video Interop Server** e scegliere Nuovo pool di Video Interop **Server.**</span><span class="sxs-lookup"><span data-stu-id="bc6a8-107">From the left pane of Topology Builder, right click on **Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="bc6a8-108">Verrà aperta la procedura **guidata Crea un nuovo pool di Video Interop Server.**</span><span class="sxs-lookup"><span data-stu-id="bc6a8-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="bc6a8-109">Specificare l'FQDN del pool per il nuovo Video Interop Server e selezionare Il pool ha un **solo server** o questo **pool** ha più server in base alle proprie esigenze, quindi premere **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="bc6a8-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="bc6a8-110">Se si desidera distribuire un pool Video Interop Server per garantire la disponibilità elevata, selezionare **Questo pool dispone di più server.**</span><span class="sxs-lookup"><span data-stu-id="bc6a8-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="bc6a8-111">Tieni presente questa opzione che:</span><span class="sxs-lookup"><span data-stu-id="bc6a8-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="bc6a8-112">È necessario distribuire il bilanciamento del carico DNS per supportare i pool di Video Interop Server.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="bc6a8-113">Nella pagina successiva, per l'elemento Definire i computer nel **pool,** immettere **l'FQDN** computer di ogni server del pool nel campo di testo e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="bc6a8-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="bc6a8-114">Ripetere questo passaggio per aggiungere un altro Video Interop Server al pool.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="bc6a8-115">Dopo aver definito tutti i computer nel pool, premere **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="bc6a8-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
     <span data-ttu-id="bc6a8-116">Se si desidera distribuire un solo Video Interop Server nel pool perché non è necessaria la disponibilità elevata, selezionare Il pool dispone di un **solo server** e premere **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="bc6a8-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="bc6a8-117">Selezionare il pool/FE hop successivo nell'elenco a discesa e premere **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="bc6a8-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="bc6a8-118">Selezionare un pool di server perimetrali da associare al VIS e premere **Fine.**</span><span class="sxs-lookup"><span data-stu-id="bc6a8-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="bc6a8-119">Impostare una porta TCP o TLS.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="bc6a8-120">Selezionare il video Interop Server appena aggiunto nel riquadro sinistro di Generatore di topologie, fare clic con il pulsante destro del mouse su di esso e scegliere **Modifica proprietà.**</span><span class="sxs-lookup"><span data-stu-id="bc6a8-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="bc6a8-121">Abilitare o aggiornare la porta TCP o TLS in base ai requisiti e scegliere **OK.**</span><span class="sxs-lookup"><span data-stu-id="bc6a8-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="bc6a8-122">Anche se per impostazione predefinita VIENE aggiunto TLS, solo TCP è stato completamente testato con Cisco Unified Communications Manager (CallManager o CUCM).</span><span class="sxs-lookup"><span data-stu-id="bc6a8-122">Although by default TLS is added, only TCP has been fully tested with Cisco Unified Communications Manager (CallManager, or CUCM).</span></span>
    
6. <span data-ttu-id="bc6a8-123">Aggiungere un gateway video.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-123">Add a video gateway.</span></span> <span data-ttu-id="bc6a8-124">A tale scopo, espandere Componenti condivisi, fare clic con il pulsante destro del mouse su **Gateway video** e selezionare Nuovo **gateway video.**</span><span class="sxs-lookup"><span data-stu-id="bc6a8-124">To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="bc6a8-125">Fornire l'FQDN o l'indirizzo IP del gateway video.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-125">Provide the video gateway FQDN or IP address.</span></span> <span data-ttu-id="bc6a8-126">Il gateway video potrebbe essere in un sottodominio o in un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-126">The video gateway could be in a subdomain or a different domain.</span></span> <span data-ttu-id="bc6a8-127">Il modello CUCM utilizzato dai VTC del sistema funge da gateway video.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-127">The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="bc6a8-128">Selezionare IPv4 o IPv6 in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-128">Select either IPv4 or IPv6 as appropriate.</span></span> <span data-ttu-id="bc6a8-129">È possibile utilizzare tutti gli indirizzi IP configurati o limitare l'utilizzo del servizio agli indirizzi IP selezionati.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-129">You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="bc6a8-130">Selezionare la porta di attesa del gateway video.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="bc6a8-131">Selezionare il protocollo di trasporto (TCP o TLS) e associarlo a un Video Interop Server configurato per un trunk SIP video.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="bc6a8-132">Il protocollo di trasporto per il gateway video deve corrispondere al protocollo di trasporto configurato per il VIS.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="bc6a8-133">Al termine del passaggio precedente viene aggiunto un trunk VIDEO SIP corrispondente.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="bc6a8-134">Fare clic con il pulsante destro del mouse sul trunk video SIP e selezionare il trunk appena aggiunto.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="bc6a8-135">Il nome del trunk SIP video, il server di interoperabilità video associato, il protocollo di trasporto SIP e la porta possono essere tutti modificati.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="bc6a8-136">Un Video Interop Server supporta trunk 1:N.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="bc6a8-137">Di conseguenza, è possibile aggiungere più trunk, associati a un singolo Video Interop Server, in cui ogni trunk termina in un gateway video diverso.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="bc6a8-138">Il limite è che un determinato gateway video dispone di un solo trunk che può essere definito per la distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="bc6a8-139">Pubblicare il documento della topologia come descritto in Creare e pubblicare una nuova topologia [in Skype for Business Server 2015.](../../deploy/install/create-and-publish-new-topology.md)</span><span class="sxs-lookup"><span data-stu-id="bc6a8-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bc6a8-140">Per migliorare la resilienza, è possibile configurare un secondo pool Video Interop Server o VIS oppure un pool Front End di backup.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="bc6a8-141">Per [ulteriori informazioni, vedere Meccanismi](../../plan-your-deployment/video-interop-server.md#resiliency) di resilienza.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="bc6a8-142">Tutte le attività eseguite utilizzando Generatore di topologie dovrebbero ora essere completate.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-142">All tasks performed using Topology Builder should now be complete.</span></span> <span data-ttu-id="bc6a8-143">Procedere con l'installazione del software nel nuovo server o server VIS.</span><span class="sxs-lookup"><span data-stu-id="bc6a8-143">Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="bc6a8-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc6a8-144">See also</span></span>

[<span data-ttu-id="bc6a8-145">Distribuire il ruolo del server VIS in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bc6a8-145">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="bc6a8-146">Pianificare Video Interop Server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bc6a8-146">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="bc6a8-147">Creare e pubblicare una nuova topologia in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bc6a8-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)
