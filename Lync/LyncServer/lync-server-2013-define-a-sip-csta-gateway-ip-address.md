---
title: "Lync Server 2013: Definire l'indirizzo IP di un gateway SIP/CSTA"
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
ms.openlocfilehash: c50958f2c7c44045e25ff4ac9619f3ad73a5f302
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728516"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a><span data-ttu-id="2a16e-102">Definire l'indirizzo IP di un gateway SIP/CSTA in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a16e-102">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a16e-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="2a16e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2a16e-104">Se Lync Server si connette al gateway SIP/CSTA distribuito per il controllo delle chiamate remote tramite una connessione TCP (Transmission Control Protocol), è necessario definire l'indirizzo IP del gateway in Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="2a16e-104">If Lync Server will connect to the SIP/CSTA gateway that you deployed for remote call control by using a Transmission Control Protocol (TCP) connection, then you must define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="2a16e-105">Questo passaggio non è necessario per i gateway che supportano connessioni TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="2a16e-105">This step is not necessary for gateways that support Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="2a16e-106">Per qualsiasi gateway che supporta connessioni TLS, è possibile ignorare questa procedura e continuare la distribuzione del controllo delle chiamate remote seguendo la procedura descritta in [abilitare gli utenti di Lync per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="2a16e-106">For any gateway that supports TLS connections, you can skip this procedure and continue deployment of remote call control by following the steps in [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a><span data-ttu-id="2a16e-107">Per definire l'indirizzo IP del gateway SIP/CSTA tramite Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="2a16e-107">To define the SIP/CSTA gateway IP address by using Topology Builder</span></span>

1.  <span data-ttu-id="2a16e-108">Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2a16e-108">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="2a16e-109">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2a16e-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="2a16e-110">Scegliere l'opzione per scaricare una topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="2a16e-110">Choose the option to download an existing topology.</span></span>

4.  <span data-ttu-id="2a16e-111">Espandere il nodo **Trusted Application Servers** .</span><span class="sxs-lookup"><span data-stu-id="2a16e-111">Expand the **Trusted application servers** node.</span></span>

5.  <span data-ttu-id="2a16e-112">Fare clic con il pulsante destro del mouse sul pool di applicazioni attendibile creato, come descritto in [configurare una voce di applicazione attendibile per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)e quindi fare clic su **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="2a16e-112">Right-click the trusted application pool that you created, as described in [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="2a16e-113">Deselezionare la casella di controllo **Abilita replica dei dati di configurazione nel pool** .</span><span class="sxs-lookup"><span data-stu-id="2a16e-113">Clear the **Enable replication of configuration data to this pool** check box.</span></span>

7.  <span data-ttu-id="2a16e-114">Fare clic su **limita l'utilizzo del servizio agli indirizzi IP selezionati**.</span><span class="sxs-lookup"><span data-stu-id="2a16e-114">Click **Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="2a16e-115">L'impostazione predefinita è **usare tutti gli indirizzi IP configurati**.</span><span class="sxs-lookup"><span data-stu-id="2a16e-115">The default setting is **Use all configured IP addresses**.</span></span>

8.  <span data-ttu-id="2a16e-116">Nella casella di testo **indirizzo IP principale** immettere l'indirizzo IP del gateway SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="2a16e-116">In the **Primary IP address** text box, enter the IP address of the SIP/CSTA gateway.</span></span>

9.  <span data-ttu-id="2a16e-117">Per aggiornare la topologia in Central Management store, nell'albero della console fare clic su **Lync Server**e quindi, nel riquadro **azioni** , fare clic su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="2a16e-117">To update the topology in the Central Management store, in the console tree, click **Lync Server**, and then, from the **Actions** pane, click **Publish**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2a16e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a16e-118">See Also</span></span>


[<span data-ttu-id="2a16e-119">Configurare una route statica per il controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a16e-119">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="2a16e-120">Configurare una voce applicazione attendibile per il controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a16e-120">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

