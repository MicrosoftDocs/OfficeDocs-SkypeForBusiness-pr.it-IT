---
title: 'Lync Server 2013: Elenco di controllo di distribuzione per i trunk SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef670fc4ae9e8a9acba3277a00fc0daf6ff766b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764492"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="af233-102">Elenco di controllo di distribuzione per i trunk SIP per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af233-102">SIP trunk deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af233-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="af233-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="af233-104">Prima di poter distribuire un trunk SIP, il provider di servizi deve scambiare alcune informazioni di base sui rispettivi endpoint del trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="af233-104">Before you can deploy a SIP trunk, you and your service provider must exchange some basic connection information about your respective SIP trunk endpoints.</span></span>

<span data-ttu-id="af233-105">Ottenere le informazioni seguenti per ogni gateway di ITSP a cui ci si connette:</span><span class="sxs-lookup"><span data-stu-id="af233-105">Get the following information for each ITSP gateway that you will connect to:</span></span>

  - <span data-ttu-id="af233-106">Indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="af233-106">IP address</span></span>

  - <span data-ttu-id="af233-107">Nome di dominio completo (FQDN)</span><span class="sxs-lookup"><span data-stu-id="af233-107">Fully qualified domain name (FQDN)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="af233-108">Il provider di servizi può richiedere di connettersi a più di un gateway ITSP.</span><span class="sxs-lookup"><span data-stu-id="af233-108">The service provider may ask you to connect to more than one ITSP gateway.</span></span> <span data-ttu-id="af233-109">In questo caso, è necessario configurare una connessione tra ogni gateway ITSP e ogni Mediation Server nel pool.</span><span class="sxs-lookup"><span data-stu-id="af233-109">In that case, you must configure a connection between each ITSP gateway and each Mediation Server in your pool.</span></span>



</div>

<span data-ttu-id="af233-110">Le informazioni fornite al provider di servizi variano a seconda del tipo di connessione trunk SIP:</span><span class="sxs-lookup"><span data-stu-id="af233-110">The information you give to your service provider depends on your SIP trunk connection type:</span></span>

  - <span data-ttu-id="af233-111">Per le connessioni MPLS (Multiprotocol Label Switching) o private network, assegna al ITSP l'indirizzo IP instradabile pubblicamente del router nella rete perimetrale (nota anche come DMZ, zona demilitarizzata e subnet schermata).</span><span class="sxs-lookup"><span data-stu-id="af233-111">For Multiprotocol Label Switching (MPLS) or private network connections, give the ITSP the publicly routable IP Address of the router in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="af233-112">Verificare che il gateway o Session Border Controller (SBC) in ITSP possa raggiungere questo indirizzo.</span><span class="sxs-lookup"><span data-stu-id="af233-112">Verify that the gateway or Session Border Controller (SBC) at the ITSP can reach this address.</span></span> <span data-ttu-id="af233-113">Assegna anche a ITSP il nome di dominio completo di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="af233-113">Also give the ITSP the FQDN of your Mediation Server.</span></span>

  - <span data-ttu-id="af233-114">Per le connessioni VPN (Virtual Private Network), assegnare all'ITSP l'indirizzo IP del server VPN.</span><span class="sxs-lookup"><span data-stu-id="af233-114">For virtual private network (VPN) connections, give the ITSP the IP address of your VPN server.</span></span>

<div>

## <a name="certificate-considerations"></a><span data-ttu-id="af233-115">Considerazioni sui certificati</span><span class="sxs-lookup"><span data-stu-id="af233-115">Certificate Considerations</span></span>

<span data-ttu-id="af233-116">Per determinare se è necessario un certificato per il trunking SIP, verificare con il proprio ITSP informazioni sul supporto del protocollo:</span><span class="sxs-lookup"><span data-stu-id="af233-116">To determine whether you need a certificate for SIP trunking, check with your ITSP about protocol support:</span></span>

1.  <span data-ttu-id="af233-117">Se il ITSP supporta solo TCP (Transmission Control Protocol), non è necessario un certificato.</span><span class="sxs-lookup"><span data-stu-id="af233-117">If your ITSP supports Transmission Control Protocol (TCP) only, you do not need a certificate.</span></span>

2.  <span data-ttu-id="af233-118">Se il ITSP supporta Transport Layer Security (TLS), ITSP deve specificare un certificato.</span><span class="sxs-lookup"><span data-stu-id="af233-118">If your ITSP supports Transport Layer Security (TLS), the ITSP must provide you with a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="af233-119">SIP funziona in combinazione con RTP (Real-Time Transport Protocol) o SRTP (Secure Real-Time Transport Protocol), i protocolli che gestiscono i dati vocali effettivi nelle chiamate VoIP (Voice over Internet Protocol).</span><span class="sxs-lookup"><span data-stu-id="af233-119">SIP works in conjunction with real-time transport protocol (RTP) or secure real-time transport protocol (SRTP), the protocols that manage the actual voice data in Voice over Internet Protocol (VoIP) calls.</span></span>



</div>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="af233-120">Processo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="af233-120">Deployment Process</span></span>

<span data-ttu-id="af233-121">Per implementare il lato Lync Server della connessione trunk SIP, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="af233-121">To implement the Lync Server side of the SIP trunk connection, follow these steps:</span></span>

1.  <span data-ttu-id="af233-122">Usando il generatore di topologia di Lync Server, creare e configurare la topologia del dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="af233-122">Using the Lync Server Topology Builder, create and configure the SIP domain topology.</span></span> <span data-ttu-id="af233-123">Per informazioni dettagliate, vedere [definire e configurare una topologia in Generatore di topologia per Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="af233-123">For details, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="af233-124">Usando il pannello di controllo di Lync Server, configurare il routing vocale per il nuovo dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="af233-124">Using the Lync Server Control Panel, configure voice routing for the new SIP domain.</span></span> <span data-ttu-id="af233-125">Per informazioni dettagliate, vedere [configurazione di Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="af233-125">For details, see [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="af233-126">Testare la connettività usando il cmdlet **Test-CsPstnOutboundCall** .</span><span class="sxs-lookup"><span data-stu-id="af233-126">Test connectivity by using the **Test-CsPstnOutboundCall** cmdlet.</span></span> <span data-ttu-id="af233-127">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell o la Guida di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="af233-127">For details, see the Lync Server Management Shell documentation or Help for Lync Server Management Shell.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

