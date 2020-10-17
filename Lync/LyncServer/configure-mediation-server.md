---
title: Configurare Mediation Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72b5742d264efb8c84518511d40195a109594e2a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503373"
---
# <a name="configure-mediation-server"></a><span data-ttu-id="dfec6-102">Configurare Mediation Server</span><span class="sxs-lookup"><span data-stu-id="dfec6-102">Configure Mediation Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfec6-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="dfec6-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="dfec6-104">In questa procedura vengono illustrati i passaggi per configurare il pool di Lync Server 2013 per l'utilizzo di Lync Server 2013 Mediation Server, anziché del Mediation Server di Office Communications Server 2007 R2 legacy.</span><span class="sxs-lookup"><span data-stu-id="dfec6-104">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="dfec6-p101">Per pubblicare, abilitare o disabilitare correttamente una topologia quando si aggiunge o si rimuove un ruolo del server, è necessario accedere come utente membro dei gruppi RTCUniversalServerAdmins e Domain Admins. È inoltre possibile delegare i diritti di amministratore e le autorizzazioni appropriate per l'aggiunta di ruoli del server. Per informazioni dettagliate, vedere Delegare autorizzazioni di installazione nella documentazione relativa alla distribuzione del server Standard Edition o Enterprise Edition. Per apportare altre modifiche relative alla configurazione è sufficiente appartenere al gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="dfec6-p101">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups. It is also possible to delegate the proper administrator rights and permissions for adding server roles. For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation. For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dfec6-109">Per informazioni più aggiornate sulla ricerca di gateway PSTN, IP-PBX e servizi di trunking SIP qualificati che interagiscono con Lync Server 2013, vedere "Microsoft Unified Communications Open Interoperability Program" all'indirizzo <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A> .</span><span class="sxs-lookup"><span data-stu-id="dfec6-109">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="dfec6-110">Per configurare Mediation Server mediante il Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="dfec6-110">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="dfec6-111">Aprire una topologia esistente dal Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="dfec6-111">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="dfec6-112">Nel riquadro sinistro spostarsi su **Gateway PSTN**.</span><span class="sxs-lookup"><span data-stu-id="dfec6-112">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="dfec6-113">Fare clic con il pulsante destro del mouse su **Gateway PSTN** e quindi scegliere **Nuovo gateway IP/PSTN**.</span><span class="sxs-lookup"><span data-stu-id="dfec6-113">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="dfec6-114">Inserire le informazioni seguenti nella pagina **Definisci nuovo gateway IP/PSTN**:</span><span class="sxs-lookup"><span data-stu-id="dfec6-114">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="dfec6-p102">Immettere il nome di dominio completo (FQDN) o l'indirizzo IP del gateway. Il nome di dominio completo (FQDN) del gateway è richiesto se il gateway utilizza il protocollo TLS.</span><span class="sxs-lookup"><span data-stu-id="dfec6-p102">Enter the gateway FQDN or IP address. The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="dfec6-117">Accettare il valore predefinito di **Porta di attesa per gateway IP/PSTN** o immettere la nuova porta di attesa, se è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="dfec6-117">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="dfec6-118">Impostare il **Protocollo trasporto SIP**.</span><span class="sxs-lookup"><span data-stu-id="dfec6-118">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="dfec6-119">Nel riquadro sinistro spostarsi su **Pool Enterprise Edition Front End** o **Server Standard**.</span><span class="sxs-lookup"><span data-stu-id="dfec6-119">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="dfec6-120">Fare clic con il pulsante destro del mouse sul pool e quindi scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="dfec6-120">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="dfec6-121">In **Mediation Server** impostare le **Porte di attesa**.</span><span class="sxs-lookup"><span data-stu-id="dfec6-121">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="dfec6-122">Quindi, associare il gateway PSTN creato selezionandolo e facendo clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="dfec6-122">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="dfec6-123">In **Generatore di topologie** selezionare il nodo di primo livello **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="dfec6-123">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="dfec6-124">Nel menu **Azioni** selezionare **Pubblica topologia** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="dfec6-124">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="dfec6-125">Al termine della **Pubblicazione guidata**, fare clic su **Fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="dfec6-125">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dfec6-126">È importante completare l'argomento successivo, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">modificare le route vocali per utilizzare il nuovo Lync server 2013 Mediation Server</A> per assicurarsi che le route vocali puntino al Mediation Server corretto.</span><span class="sxs-lookup"><span data-stu-id="dfec6-126">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

