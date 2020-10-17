---
title: 'Lync Server 2013: definire un indirizzo IP del gateway SIP/CSTA'
description: 'Lync Server 2013: definire un indirizzo IP del gateway SIP/CSTA.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23286b2748df3af06f905a791bf0ee80c6f0a919
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560432"
---
# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a><span data-ttu-id="7f672-103">Definire un indirizzo IP del gateway SIP/CSTA in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f672-103">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f672-104">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="7f672-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="7f672-105">Se Lync Server si connetterà al gateway SIP/CSTA distribuito per il controllo delle chiamate remote tramite una connessione TCP (Transmission Control Protocol), sarà necessario definire l'indirizzo IP del gateway in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="7f672-105">If Lync Server will connect to the SIP/CSTA gateway that you deployed for remote call control by using a Transmission Control Protocol (TCP) connection, then you must define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="7f672-106">Questa operazione non è necessaria per i gateway che supportano le connessioni TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="7f672-106">This step is not necessary for gateways that support Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="7f672-107">Per tutti i gateway che supportano le connessioni TLS, è possibile ignorare questa procedura e continuare la distribuzione del controllo delle chiamate remote attenendosi alla procedura descritta in [Enable Lync users for Remote Call Control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="7f672-107">For any gateway that supports TLS connections, you can skip this procedure and continue deployment of remote call control by following the steps in [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a><span data-ttu-id="7f672-108">Per definire l'indirizzo IP di un gateway SIP/CSTA mediante Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="7f672-108">To define the SIP/CSTA gateway IP address by using Topology Builder</span></span>

1.  <span data-ttu-id="7f672-109">Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7f672-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="7f672-110">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="7f672-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="7f672-111">Scegliere l'opzione per scaricare una topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="7f672-111">Choose the option to download an existing topology.</span></span>

4.  <span data-ttu-id="7f672-112">Espandere il nodo **Server applicazioni attendibili**.</span><span class="sxs-lookup"><span data-stu-id="7f672-112">Expand the **Trusted application servers** node.</span></span>

5.  <span data-ttu-id="7f672-113">Fare clic con il pulsante destro del mouse sul pool di applicazioni attendibili creato, come descritto in [configurare una voce di applicazione attendibile per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), quindi fare clic su **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7f672-113">Right-click the trusted application pool that you created, as described in [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="7f672-114">Deselezionare la casella di controllo **Abilita la replica dei dati di configurazione nel pool**.</span><span class="sxs-lookup"><span data-stu-id="7f672-114">Clear the **Enable replication of configuration data to this pool** check box.</span></span>

7.  <span data-ttu-id="7f672-p102">Fare clic su **Limita utilizzo servizio a indirizzi IP selezionati**. L'impostazione predefinita è **Usa tutti gli indirizzi IP configurati**.</span><span class="sxs-lookup"><span data-stu-id="7f672-p102">Click **Limit service usage to selected IP addresses**. The default setting is **Use all configured IP addresses**.</span></span>

8.  <span data-ttu-id="7f672-117">Nella casella di testo **Indirizzo IP primario** immettere l'indirizzo IP del gateway SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="7f672-117">In the **Primary IP address** text box, enter the IP address of the SIP/CSTA gateway.</span></span>

9.  <span data-ttu-id="7f672-118">Per aggiornare la topologia nell'archivio di gestione centrale, fare clic su **Lync Server** nell'albero della console e quindi su **Pubblica** nel riquadro **Azioni**.</span><span class="sxs-lookup"><span data-stu-id="7f672-118">To update the topology in the Central Management store, in the console tree, click **Lync Server**, and then, from the **Actions** pane, click **Publish**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7f672-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f672-119">See Also</span></span>


[<span data-ttu-id="7f672-120">Configurare una route statica per il controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f672-120">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="7f672-121">Configurare una voce di applicazione attendibile per il controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f672-121">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

