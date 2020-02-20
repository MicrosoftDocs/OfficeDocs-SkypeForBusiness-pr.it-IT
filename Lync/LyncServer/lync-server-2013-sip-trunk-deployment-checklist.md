---
title: 'Lync Server 2013: elenco di controllo di distribuzione trunk SIP'
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
ms.openlocfilehash: a2d584b507f677632b28deb1cae28ebfa4cc7bfa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="48424-102">Elenco di controllo per la distribuzione del trunk SIP per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48424-102">SIP trunk deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48424-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="48424-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="48424-104">Prima di distribuire un trunk SIP, è necessario scambiare con il provider del servizio alcune informazioni di connessione di base sui rispettivi endpoint di trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="48424-104">Before you can deploy a SIP trunk, you and your service provider must exchange some basic connection information about your respective SIP trunk endpoints.</span></span>

<span data-ttu-id="48424-105">Ottenere le informazioni seguenti per ogni gateway ITSP (Internet Telephony Service Provider, provider di servizi di telefonia Internet) al quale si eseguirà la connessione:</span><span class="sxs-lookup"><span data-stu-id="48424-105">Get the following information for each ITSP gateway that you will connect to:</span></span>

  - <span data-ttu-id="48424-106">Indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="48424-106">IP address</span></span>

  - <span data-ttu-id="48424-107">Nome di dominio completo (FQDN)</span><span class="sxs-lookup"><span data-stu-id="48424-107">Fully qualified domain name (FQDN)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="48424-108">Il provider di servizi potrebbe chiedere di eseguire la connessione a più gateway ITSP.</span><span class="sxs-lookup"><span data-stu-id="48424-108">The service provider may ask you to connect to more than one ITSP gateway.</span></span> <span data-ttu-id="48424-109">In tal caso, è necessario configurare una connessione tra ogni gateway di ITSP e ogni Mediation Server nel pool.</span><span class="sxs-lookup"><span data-stu-id="48424-109">In that case, you must configure a connection between each ITSP gateway and each Mediation Server in your pool.</span></span>



</div>

<span data-ttu-id="48424-110">Le informazioni fornite al provider di servizi variano in base al tipo di connessione trunk SIP:</span><span class="sxs-lookup"><span data-stu-id="48424-110">The information you give to your service provider depends on your SIP trunk connection type:</span></span>

  - <span data-ttu-id="48424-111">Per le connessioni MPLS (Multiprotocol Label Switching) o a reti private, fornire all'ITSP l'indirizzo IP instradabile pubblicamente del router nella rete perimetrale, denominata anche DMZ o subnet schermata.</span><span class="sxs-lookup"><span data-stu-id="48424-111">For Multiprotocol Label Switching (MPLS) or private network connections, give the ITSP the publicly routable IP Address of the router in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="48424-112">Verificare che il gateway o il Session Border Controller dell'ITSP sia in grado di raggiungere tale indirizzo.</span><span class="sxs-lookup"><span data-stu-id="48424-112">Verify that the gateway or Session Border Controller (SBC) at the ITSP can reach this address.</span></span> <span data-ttu-id="48424-113">Assegnare anche all'ITSP il nome di dominio completo del Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="48424-113">Also give the ITSP the FQDN of your Mediation Server.</span></span>

  - <span data-ttu-id="48424-114">Per le connessioni VPN, fornire all'ITSP l'indirizzo IP del server VPN.</span><span class="sxs-lookup"><span data-stu-id="48424-114">For virtual private network (VPN) connections, give the ITSP the IP address of your VPN server.</span></span>

<div>

## <a name="certificate-considerations"></a><span data-ttu-id="48424-115">Considerazioni sui certificati</span><span class="sxs-lookup"><span data-stu-id="48424-115">Certificate Considerations</span></span>

<span data-ttu-id="48424-116">Per determinare se è necessario un certificato per il trunking SIP, verificare i protocolli supportati con l'ITSP:</span><span class="sxs-lookup"><span data-stu-id="48424-116">To determine whether you need a certificate for SIP trunking, check with your ITSP about protocol support:</span></span>

1.  <span data-ttu-id="48424-117">Se l'ITSP supporta solo TCP, non è necessario un certificato.</span><span class="sxs-lookup"><span data-stu-id="48424-117">If your ITSP supports Transmission Control Protocol (TCP) only, you do not need a certificate.</span></span>

2.  <span data-ttu-id="48424-118">Se supporta TLS, l'ITSP dovrà fornire un certificato.</span><span class="sxs-lookup"><span data-stu-id="48424-118">If your ITSP supports Transport Layer Security (TLS), the ITSP must provide you with a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="48424-119">Il protocollo SIP funziona in combinazione con RTP o SRTP, i protocolli che gestiscono gli effettivi dati vocali nelle chiamate VoIP.</span><span class="sxs-lookup"><span data-stu-id="48424-119">SIP works in conjunction with real-time transport protocol (RTP) or secure real-time transport protocol (SRTP), the protocols that manage the actual voice data in Voice over Internet Protocol (VoIP) calls.</span></span>



</div>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="48424-120">Processo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="48424-120">Deployment Process</span></span>

<span data-ttu-id="48424-121">Per implementare il margine Lync Server della connessione trunk SIP, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="48424-121">To implement the Lync Server side of the SIP trunk connection, follow these steps:</span></span>

1.  <span data-ttu-id="48424-122">Se si utilizza il generatore di topologie di Lync Server, creare e configurare la topologia di dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="48424-122">Using the Lync Server Topology Builder, create and configure the SIP domain topology.</span></span> <span data-ttu-id="48424-123">Per informazioni dettagliate, vedere [definire e configurare una topologia in Generatore di topologie per Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="48424-123">For details, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="48424-124">Se si utilizza il pannello di controllo di Lync Server, configurare il routing vocale per il nuovo dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="48424-124">Using the Lync Server Control Panel, configure voice routing for the new SIP domain.</span></span> <span data-ttu-id="48424-125">Per informazioni dettagliate, vedere [Configuring Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="48424-125">For details, see [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="48424-126">Testare la connettività utilizzando il cmdlet  **Test-CsPstnOutboundCall**.</span><span class="sxs-lookup"><span data-stu-id="48424-126">Test connectivity by using the **Test-CsPstnOutboundCall** cmdlet.</span></span> <span data-ttu-id="48424-127">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell o la guida per Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="48424-127">For details, see the Lync Server Management Shell documentation or Help for Lync Server Management Shell.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

