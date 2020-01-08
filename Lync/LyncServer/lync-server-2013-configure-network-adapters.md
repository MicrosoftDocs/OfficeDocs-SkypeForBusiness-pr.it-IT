---
title: 'Lync Server 2013: Configurare le schede di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3469e9d5fa3f7aeb45bc8f35ff692d97d09b8481
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a><span data-ttu-id="71099-102">Configurare le schede di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71099-102">Configure network adapters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71099-103">_**Argomento Ultima modifica:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="71099-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="71099-104">È necessario assegnare uno o più indirizzi IP alla scheda di rete esterna e almeno un indirizzo IP alla scheda di rete interna.</span><span class="sxs-lookup"><span data-stu-id="71099-104">You must assign one or more IP addresses to the external network adapter and at least one IP address to the internal network adapter.</span></span>

<span data-ttu-id="71099-105">Nelle procedure seguenti il server che utilizza Forefront Threat Management Gateway (TMG) 2010 o Internet Information Server Request Routing richiede due schede di rete:</span><span class="sxs-lookup"><span data-stu-id="71099-105">In the following procedures, the server running either Forefront Threat Management Gateway (TMG) 2010 or Internet Information Server Application Request Routing has two network adapters:</span></span>

  - <span data-ttu-id="71099-106">Una scheda di rete pubblica o esterna, per i client che tentano di connettersi al sito Web, ovvero in genere tramite Internet.</span><span class="sxs-lookup"><span data-stu-id="71099-106">A public, or external, network adapter, for clients that attempt to connect to your website (that is, usually over the Internet).</span></span>

  - <span data-ttu-id="71099-107">Interfaccia di rete privata o interna per i server interni che esegue Lync Server che ospitano servizi Web.</span><span class="sxs-lookup"><span data-stu-id="71099-107">A private, or internal, network interface, for internal servers running Lync Server that are hosting Web Services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="71099-108">Analogamente agli Edge Server, è possibile impostare il gateway predefinito solo sulla scheda di rete esterna.</span><span class="sxs-lookup"><span data-stu-id="71099-108">Similar to the Edge Servers, you set the default gateway on the external network adapter only.</span></span> <span data-ttu-id="71099-109">Il gateway predefinito sarà l'indirizzo IP del router o del firewall di fronte esterno che indirizza il traffico a Internet.</span><span class="sxs-lookup"><span data-stu-id="71099-109">The default gateway will be the IP address of the router or external facing firewall that directs traffic to the Internet.</span></span> <span data-ttu-id="71099-110">Per il traffico destinato al proxy inverso alla scheda di rete interna, è necessario usare route statiche permanenti, ad esempio il comando instrada in Windows Server, per tutte le subnet che contengono server a cui fanno riferimento le regole di pubblicazione Web.</span><span class="sxs-lookup"><span data-stu-id="71099-110">For traffic that is destined from the reverse proxy to the internal facing network adaptor, you must use persistent static routes (such as the route command in Windows Server) for all subnets containing servers referenced by the web publishing rules.</span></span> <span data-ttu-id="71099-111">L'impostazione di una route persistente non fa sì che il computer diventi un router.</span><span class="sxs-lookup"><span data-stu-id="71099-111">Setting a persistent route does not cause the computer to become a router.</span></span> <span data-ttu-id="71099-112">Se l'inoltro IP non è abilitato, il computer agisce solo per indirizzare il traffico specifico destinato a un'altra rete all'interfaccia appropriata.</span><span class="sxs-lookup"><span data-stu-id="71099-112">If IP forwarding is not enabled, the computer is acting only to direct specific traffic destined for another network to the appropriate interface.</span></span> <span data-ttu-id="71099-113">Si tratta essenzialmente di impostare due gateway, uno come predefinito che punta alle reti esterne e uno per il traffico destinato all'interfaccia interna e a un router o a un'altra rete.</span><span class="sxs-lookup"><span data-stu-id="71099-113">This is essentially setting two gateways – one as the default pointing to the external networks, and one for traffic destined to the internal interface and on to a router or other network.</span></span><BR><span data-ttu-id="71099-114">Tuttavia, potrebbe non essere necessario creare route permanenti per tutte le subnet se i router della rete sono configurati per riepilogare le route.</span><span class="sxs-lookup"><span data-stu-id="71099-114">However, creating persistent routes for all subnets may not be necessary if your network’s routers are configured to summarize routes.</span></span> <span data-ttu-id="71099-115">Creare una route persistente per la rete in cui è definito il router e usare il router come gateway predefinito.</span><span class="sxs-lookup"><span data-stu-id="71099-115">Create a persistent route to the network where the router is defined and use the router as the default gateway.</span></span> <span data-ttu-id="71099-116">Se non si sa in che modo la rete è configurata e occorrono indicazioni su quali route permanenti devono essere create, consultare gli ingegneri di rete della società.</span><span class="sxs-lookup"><span data-stu-id="71099-116">If you are not sure how your network is configured and need guidance on what persistent routes need to be created, consult with your company’s Network Engineers.</span></span><BR><span data-ttu-id="71099-117">Il proxy inverso deve essere in grado di risolvere i record host DNS (A) per il Director interno o i nomi FQDN del pool hop successivo usati nelle regole di pubblicazione Web.</span><span class="sxs-lookup"><span data-stu-id="71099-117">The reverse proxy must be able to resolve the DNS host (A) records for the internal Director or Front End Server and next hop pool FQDNs used in the web publishing rules.</span></span> <span data-ttu-id="71099-118">Come per i server perimetrali, per motivi di sicurezza, è consigliabile non configurare un proxy inverso per l'uso di un server DNS nella rete interna.</span><span class="sxs-lookup"><span data-stu-id="71099-118">As with the Edge Servers, for security reasons, we recommend that you do not configure a reverse proxy to use a DNS server located in the internal network.</span></span> <span data-ttu-id="71099-119">Questo significa che è necessario disporre di server DNS nel perimetro oppure che occorrono voci di file HOSTs nel proxy inverso che risolve ognuno di questi FQDN nell'indirizzo IP interno dei server.</span><span class="sxs-lookup"><span data-stu-id="71099-119">This means you either need DNS servers in the perimeter, or you need HOSTS file entries on the reverse proxy that resolves each of these FQDNs to the internal IP address of the servers.</span></span>



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a><span data-ttu-id="71099-120">Per configurare le schede della scheda di rete nel computer proxy inverso</span><span class="sxs-lookup"><span data-stu-id="71099-120">To configure the network adapter cards on the reverse proxy computer</span></span>

1.  <span data-ttu-id="71099-121">Nel server Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2 in uso come proxy inverso, aprire **le impostazioni della scheda Modifica** facendo clic sul pulsante **Start**, scegliendo il **Pannello di controllo**, facendo clic su **Centro rete e condivisione**e quindi scegliendo **Cambia impostazioni adattatore**.</span><span class="sxs-lookup"><span data-stu-id="71099-121">On the Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 server running as the reverse proxy, open **Change Adapter Settings** by clicking **Start**, pointing to **Control Panel**, clicking **Network and Sharing Center**, and then clicking **Change Adapter Settings**.</span></span>

2.  <span data-ttu-id="71099-122">Fare clic con il pulsante destro del mouse sulla connessione di rete esterna che si vuole usare per l'interfaccia esterna e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="71099-122">Right-click the external network connection that you want to use for the external interface, and then click **Properties**.</span></span>

3.  <span data-ttu-id="71099-123">Nella pagina **Proprietà** fare clic sulla scheda **rete** , fare clic su **protocollo Internet versione 4 (TCP/IPv4)** nella finestra di dialogo **questa connessione usa l'elenco elementi seguenti** e quindi fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="71099-123">On the **Properties** page, click the **Networking** tab, click **Internet Protocol Version 4 (TCP/IPv4)** in the **This connection uses the following items** list, and then click **Properties**.</span></span>

4.  <span data-ttu-id="71099-124">Nella pagina delle **proprietà del protocollo Internet (TCP/IP)** configurare gli indirizzi IP appropriati per la subnet di rete a cui è collegata la scheda di rete.</span><span class="sxs-lookup"><span data-stu-id="71099-124">On the **Internet Protocol (TCP/IP) Properties** page, configure the IP addresses as appropriate for the network subnet to which the network adapter is attached.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="71099-125">Se il proxy inverso viene già usato da altre applicazioni che usano HTTPS/TCP/443, ad esempio, per la pubblicazione di Outlook Web Access, è necessario aggiungere un altro indirizzo IP in modo da poter pubblicare i servizi Web di Lync Server 2013 in HTTPS/TCP/443 senza interferire con le regole e i listener Web esistenti oppure sostituire il certificato esistente con uno che aggiunge i nuovi nomi FQDN esterni al nome alternativo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="71099-125">If the reverse proxy is already being used by other applications that use HTTPS/TCP/443, such as for publishing Outlook Web Access, you either need to add another IP address so that you can publish the Lync Server 2013 Web Services on HTTPS/TCP/443 without interfering with the existing rules and web listeners, or you need to replace the existing certificate with one that adds the new external FQDN names to the subject alternative name.</span></span>

    
    </div>

5.  <span data-ttu-id="71099-126">Fare clic su **OK**e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="71099-126">Click **OK**, and then click **OK**.</span></span>

6.  <span data-ttu-id="71099-127">In **connessioni di rete**fare clic con il pulsante destro del mouse sulla connessione di rete interna che si vuole usare per l'interfaccia interna e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="71099-127">In **Network Connections**, right-click the internal network connection that you want to use for the internal interface, and then click **Properties**.</span></span>

7.  <span data-ttu-id="71099-128">Ripetere i passaggi da 3 a 5 per configurare la connessione di rete interna.</span><span class="sxs-lookup"><span data-stu-id="71099-128">Repeat steps 3 through 5 to configure the internal network connection.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

