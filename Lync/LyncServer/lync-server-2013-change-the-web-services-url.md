---
title: "Lync Server 2013: modificare l'URL dei servizi Web"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 934e448f48413df2938deab8a0d08389cfad37bd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a><span data-ttu-id="8dc9d-102">Modificare l'URL dei servizi Web in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dc9d-102">Change the Web Services URL in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dc9d-103">_**Argomento Ultima modifica:** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="8dc9d-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="8dc9d-104">Quando si configurano i pool Front-end e i server Standard Edition, è possibile configurare un nome di dominio completo (FQDN) di una Web farm esterna e le porte associate.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-104">When you set up your Front End pools and Standard Edition servers, you have the option to configure an external Web farm fully qualified domain name (FQDN) and associated ports.</span></span> <span data-ttu-id="8dc9d-105">Se non è stato configurato questo URL quando è stata eseguita la distribuzione guidata di Lync Server, è necessario configurare manualmente queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-105">If you did not configure this URL when you ran the Lync Server Deployment Wizard, you need to manually configure these settings.</span></span> <span data-ttu-id="8dc9d-106">In genere, un amministratore non deve modificare queste impostazioni, perché queste sono le porte consigliate e predefinite.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-106">An administrator typically does not need to modify these settings, as these are the recommended and default ports.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8dc9d-107">La schermata seguente è stata scattata durante la configurazione di un server Standard Edition, quindi l'opzione Sostituisci FQDN è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-107">The following screen shot was taken while configuring a Standard Edition server, so the Override FQDN option is disabled.</span></span> <span data-ttu-id="8dc9d-108">Questa opzione è abilitata quando si configura un server Enterprise Edition in un pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-108">That option is enabled when configuring an Enterprise Edition server in a Front End pool.</span></span>



</div>

<span data-ttu-id="8dc9d-109">![Modificare le impostazioni dei pool per i servizi Web](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Modificare le impostazioni dei pool per i servizi Web")</span><span class="sxs-lookup"><span data-stu-id="8dc9d-109">![Edit Web Services Pool Settings](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Edit Web Services Pool Settings")</span></span>

<div>

## <a name="to-configure-web-services"></a><span data-ttu-id="8dc9d-110">Per configurare i servizi Web</span><span class="sxs-lookup"><span data-stu-id="8dc9d-110">To configure web services</span></span>

1.  <span data-ttu-id="8dc9d-111">Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="8dc9d-112">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-112">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="8dc9d-113">In Generatore di topologia, nell'albero della console, in **server front-end Standard Edition**, **pool di front end Enterprise Edition**e **pool di directory**, selezionare il nome del pool.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-113">In Topology Builder, in the console tree under **Standard Edition Front End Servers**, **Enterprise Edition Front End pools**, and **Directory pools**, select the pool name.</span></span> <span data-ttu-id="8dc9d-114">Fare clic con il pulsante destro del mouse sul nome, scegliere **modifica proprietà**e quindi fare clic su **servizi Web**.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-114">Right-click the name, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="8dc9d-115">Aggiungere o modificare il **nome di dominio completo dei servizi Web esterni**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-115">Add or edit the **External Web Services FQDN**, and then click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="8dc9d-116">Se si hanno più di un pool Front end o un server front-end, l'FQDN dei servizi Web esterni deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-116">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="8dc9d-117">Se ad esempio si definisce il nome di dominio completo dei servizi Web esterni di un front end server come <STRONG>pool01.contoso.com</STRONG>, non è possibile usare <STRONG>pool01.contoso.com</STRONG> per un altro pool Front-end o front end server.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-117">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="8dc9d-118">Se si sta distribuendo anche Directors, l'FQDN dei servizi Web esterni definiti per qualsiasi pool di Director o Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front-end o front end server.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-118">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="8dc9d-119">Verificare che le porte in attesa e pubblicate siano configurate correttamente per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-119">Verify the listening and published ports are configured correctly for your environment.</span></span>

6.  <span data-ttu-id="8dc9d-120">Ripetere questi passaggi per tutti i server Standard Edition, i pool Front-end e i pool di Director nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-120">Repeat these steps for all Standard Edition servers, Front End Pools, and Director pools in your environment.</span></span>

7.  <span data-ttu-id="8dc9d-121">Nell'albero della console fare clic su **Lync Server 2013**e quindi, nel riquadro **azioni** , fare clic su **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-121">In the console tree, click **Lync Server 2013**, and then, in the **Actions** pane, click **Publish Topology**.</span></span>

<span data-ttu-id="8dc9d-122">Quando si configurano le porte di ascolto e di pubblicazione, è necessario tenere presenti alcuni requisiti:</span><span class="sxs-lookup"><span data-stu-id="8dc9d-122">There are a few requirements you should be aware of when configuring the Listening and Publishing ports:</span></span>

  - <span data-ttu-id="8dc9d-123">Le porte in attesa visualizzate sono le porte configurate per Internet Information Server (IIS) in ogni server front-end.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-123">The listening ports shown are the ports that are configured for Internet Information Server (IIS) on each Front End Server.</span></span>

  - <span data-ttu-id="8dc9d-124">Le porte di ascolto interne ed esterne devono essere diverse per IIS.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-124">The internal and external listening ports must be different for IIS.</span></span> <span data-ttu-id="8dc9d-125">Per le porte di ascolto esterne, si tratta in genere dello stesso perché uno rappresenta il bilanciamento del carico hardware per il traffico Web interno e uno rappresenta il server proxy inverso per il traffico Web esterno.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-125">For the external listening ports, these are typically the same because one represents the hardware load balancer for internal web traffic and one represents the reverse proxy server for external web traffic.</span></span>

  - <span data-ttu-id="8dc9d-126">È possibile ignorare i servizi Web interni in un pool di front-end, un Director o un pool di Director e definire il proprio nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-126">You can override the Internal web services on a Front End pool, Director or a Director pool and define your own FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="8dc9d-127">Se si decide di ignorare i servizi Web interni con un nome di dominio completo definito autonomamente, ogni nome di dominio completo deve essere univoco da qualsiasi altro pool di front-end, direttore o pool di Director.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-127">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

  - <span data-ttu-id="8dc9d-128">Le porte pubblicate devono essere configurate nel proxy inverso o nel bilanciamento del carico hardware come porte di ascolto.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-128">The published ports must be configured on the reverse proxy or hardware load balancer as listening ports.</span></span>

  - <span data-ttu-id="8dc9d-129">Per un pool Front-End (non illustrato nell'esempio), il nome di dominio completo del pool SIP interno deve essere diverso dall'FQDN dei servizi Web interni, perché il traffico Web passa attraverso il servizio di bilanciamento del carico hardware e il traffico del pool SIP interno passa attraverso il servizio di bilanciamento del carico DNS .</span><span class="sxs-lookup"><span data-stu-id="8dc9d-129">For an Front End pool (not shown in the example), the internal SIP pool FQDN must be different from the internal web services FQDN, because web traffic comes through the hardware load balancer and the internal SIP pool traffic travels comes through the DNS load balancer.</span></span> <span data-ttu-id="8dc9d-130">Questo requisito deve essere soddisfatto.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-130">This requirement must be met.</span></span>

  - <span data-ttu-id="8dc9d-131">Una distribuzione di Lync Server Standard Edition non richiede o consente l'override di un FQDN dei servizi Web interni perché questo server non può essere caricato in modo equilibrato.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-131">A Lync Server Standard Edition deployment does not need or allow an internal web services FQDN to be overridden because this server cannot be load balanced.</span></span>

  - <span data-ttu-id="8dc9d-132">Se si dispone di un dispositivo di bilanciamento del carico hardware nell'ambiente usato sia per il traffico SIP interno che per quello Web, il generatore di topologie non può distinguere.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-132">If you have a hardware load balancer in your environment that you use for both internal SIP and web traffic, the Topology Builder cannot make the distinction.</span></span>
    
    <span data-ttu-id="8dc9d-133">Gli FQDN dei servizi Web devono essere facilmente differenziati l'uno dall'altro; Questo consente di garantire che i client punti di reindirizzamento degli URL verso il server appropriato.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-133">Web service FQDNs should be easily-differentiated from one another; that helps to ensure that URL redirection points clients towards the appropriate server.</span></span> <span data-ttu-id="8dc9d-134">Se ad esempio sono presenti due nomi di dominio completi, è possibile considerare la denominazione di un meeting.contoso.com e l'altro conferencing.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-134">For example, if you have two FQDNs you might consider naming one meeting.contoso.com and the other conferencing.contoso.com.</span></span> <span data-ttu-id="8dc9d-135">Se si hanno nomi di dominio completi, ad esempio meet1.contoso.com e meet2.contoso.com, è possibile che si possano eseguire potenziali problemi di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-135">You could potentially run into redirection issues if you have FQDNs with more similar names, such as meet1.contoso.com and meet2.contoso.com.</span></span>

<span data-ttu-id="8dc9d-136">I servizi Web esterni funzionano in combinazione con un proxy inverso nella rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-136">The external web services works in conjunction with a reverse proxy in the perimeter network.</span></span> <span data-ttu-id="8dc9d-137">Offre ai client l'accesso esterno tramite questi servizi Web.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-137">It provides clients external access to by using these web services.</span></span> <span data-ttu-id="8dc9d-138">I nomi di dominio completi configurati in questo articolo vengono inviati ai client durante l'accesso e vengono usati per ripristinare una connessione HTTPS al proxy inverso quando si connette in remoto.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-138">The FQDNs configured here are sent to clients when they log on, and are used to make an HTTPS connection back to the reverse proxy when connecting remotely.</span></span> <span data-ttu-id="8dc9d-139">Il server proxy inverso inoltra il nome di dominio completo del servizio Web esterno a un bilanciamento del carico hardware interno o direttamente al pool.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-139">The reverse-proxy server forwards the external web service FQDN to an internal hardware load balancer, or directly to the pool.</span></span> <span data-ttu-id="8dc9d-140">Il proxy inverso deve essere in grado di risolvere il nome di dominio completo dei servizi Web esterni con l'indirizzo IP del server Web interno.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-140">The reverse proxy must be able to resolve the external web services FQDN to the IP address of the internal Web server.</span></span> <span data-ttu-id="8dc9d-141">I servizi Web esterni FDQN devono essere risolvibili in Internet pubblico.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-141">The external web services FDQN must be resolvable in the public Internet.</span></span>

<span data-ttu-id="8dc9d-142">Se il server interno è un server Standard Edition, il nome di dominio completo interno è il nome di dominio completo del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-142">If your internal server is a Standard Edition server, the internal FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="8dc9d-143">Se il server interno è un pool Front-End, il nome completo è un IP virtuale (VIP) di bilanciamento del carico hardware che bilancia il carico dei server della Web farm interna.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-143">If your internal server is a Front End pool, the FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="8dc9d-144">Un bilanciamento del carico hardware è obbligatorio in un pool Front-end con più server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-144">A hardware load balancer is required in a Front End pool with more than one Enterprise Edition server.</span></span> <span data-ttu-id="8dc9d-145">Un tipo di bilanciamento del carico non è necessario per un server Standard Edition o un server front-end singolo Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="8dc9d-145">A load balancer is not required for a Standard Edition server or a single Enterprise Edition Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

