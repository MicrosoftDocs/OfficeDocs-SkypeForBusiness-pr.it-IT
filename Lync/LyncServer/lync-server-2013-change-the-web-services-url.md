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
ms.openlocfilehash: 94424edc38cf1cc0eacac2638a4ed30a18f06779
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a><span data-ttu-id="b5b4a-102">Modificare l'URL dei servizi Web in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5b4a-102">Change the Web Services URL in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5b4a-103">_**Ultimo argomento modificato:** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="b5b4a-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="b5b4a-104">Quando si impostano i pool Front End e i Server Standard, si ha la possibilità di configurare il nome di dominio completo (FQDN) di una Web farm esterna e le porte associate.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-104">When you set up your Front End pools and Standard Edition servers, you have the option to configure an external Web farm fully qualified domain name (FQDN) and associated ports.</span></span> <span data-ttu-id="b5b4a-105">Se non è stato configurato questo URL quando è stata eseguita la distribuzione guidata di Lync Server, è necessario configurare manualmente tali impostazioni.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-105">If you did not configure this URL when you ran the Lync Server Deployment Wizard, you need to manually configure these settings.</span></span> <span data-ttu-id="b5b4a-106">Un amministratore in genere non ha necessità di modificare tali impostazioni, dal momento che si tratta delle porte consigliate e predefinite.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-106">An administrator typically does not need to modify these settings, as these are the recommended and default ports.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b5b4a-107">La schermata seguente è stata scattata durante la configurazione di un server Standard Edition, quindi l'opzione Sostituisci FQDN è disattivata.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-107">The following screen shot was taken while configuring a Standard Edition server, so the Override FQDN option is disabled.</span></span> <span data-ttu-id="b5b4a-108">Questa opzione è abilitata durante la configurazione di un server Enterprise Edition in un pool Front end.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-108">That option is enabled when configuring an Enterprise Edition server in a Front End pool.</span></span>



</div>

<span data-ttu-id="b5b4a-109">![Modificare le impostazioni del pool di servizi Web](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Modificare le impostazioni del pool di servizi Web")</span><span class="sxs-lookup"><span data-stu-id="b5b4a-109">![Edit Web Services Pool Settings](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Edit Web Services Pool Settings")</span></span>

<div>

## <a name="to-configure-web-services"></a><span data-ttu-id="b5b4a-110">Per configurare i servizi Web</span><span class="sxs-lookup"><span data-stu-id="b5b4a-110">To configure web services</span></span>

1.  <span data-ttu-id="b5b4a-111">Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="b5b4a-112">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-112">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="b5b4a-113">In Generatore di topologie, nell'albero della console in **Standard Edition Front End Server**, **pool Enterprise Edition front end**e **pool di directory**selezionare il nome del pool.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-113">In Topology Builder, in the console tree under **Standard Edition Front End Servers**, **Enterprise Edition Front End pools**, and **Directory pools**, select the pool name.</span></span> <span data-ttu-id="b5b4a-114">Fare clic con il pulsante destro del mouse sul nome, scegliere **Modifica proprietà** e quindi fare clic su **Servizi Web**.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-114">Right-click the name, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="b5b4a-115">Aggiungere o modificare l'FQDN di **Servizi Web esterni** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-115">Add or edit the **External Web Services FQDN**, and then click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="b5b4a-116">Se si dispone di più di un pool Front end o front end server, l'FQDN dei servizi Web esterni deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-116">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="b5b4a-117">Ad esempio, se si definisce l'FQDN dei servizi Web esterni di un front end server come <STRONG>pool01.contoso.com</STRONG>, non è possibile utilizzare <STRONG>pool01.contoso.com</STRONG> per un altro pool Front end o front end server.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-117">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="b5b4a-118">Se si sta distribuendo anche Director, l'FQDN dei servizi Web esterni definiti per qualsiasi server Director o di server Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front end o front-end.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-118">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="b5b4a-119">Verificare che le porte di attesa e pubblicate siano configurate correttamente per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-119">Verify the listening and published ports are configured correctly for your environment.</span></span>

6.  <span data-ttu-id="b5b4a-120">Ripetere questi passaggi per tutti i server Standard Edition, i pool Front End e i pool di server Director nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-120">Repeat these steps for all Standard Edition servers, Front End Pools, and Director pools in your environment.</span></span>

7.  <span data-ttu-id="b5b4a-121">Nell'albero della console fare clic su **Lync Server 2013** e quindi fare clic su **Pubblica topologia** nel riquadro **Azioni**.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-121">In the console tree, click **Lync Server 2013**, and then, in the **Actions** pane, click **Publish Topology**.</span></span>

<span data-ttu-id="b5b4a-122">Per la configurazione delle porte di attesa e pubblicate è necessario tenere conto di alcuni requisiti:</span><span class="sxs-lookup"><span data-stu-id="b5b4a-122">There are a few requirements you should be aware of when configuring the Listening and Publishing ports:</span></span>

  - <span data-ttu-id="b5b4a-123">Le porte di attesa visualizzate sono quelle configurate per Internet Information Server (IIS) in ogni Front End Server.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-123">The listening ports shown are the ports that are configured for Internet Information Server (IIS) on each Front End Server.</span></span>

  - <span data-ttu-id="b5b4a-p105">Le porte di attesa interne ed esterne devono essere diverse per IIS. Per le porte di attesa esterne, queste sono in genere le stesse perché una rappresenta il dispositivo di bilanciamento del carico hardware per il traffico Web interno e una rappresenta il server proxy inverso per il traffico Web esterno.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-p105">The internal and external listening ports must be different for IIS. For the external listening ports, these are typically the same because one represents the hardware load balancer for internal web traffic and one represents the reverse proxy server for external web traffic.</span></span>

  - <span data-ttu-id="b5b4a-126">È possibile sostituire i servizi Web interni in un pool Front End, in un server Director o in un pool di Director e definire il nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-126">You can override the Internal web services on a Front End pool, Director or a Director pool and define your own FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="b5b4a-127">Se si decide di sostituire i servizi Web interni con un FQDN autodefinito, ogni FQDN deve essere univoco da qualsiasi altro pool Front End, Director o pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-127">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

  - <span data-ttu-id="b5b4a-128">Le porte pubblicate devono essere configurate nel proxy inverso o nel dispositivo di bilanciamento del carico hardware come porte di attesa.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-128">The published ports must be configured on the reverse proxy or hardware load balancer as listening ports.</span></span>

  - <span data-ttu-id="b5b4a-p106">Per un pool Front End (non mostrato nell'esempio, l'FQDN del pool SIP interno deve essere diverso dall'FQDN dei Servizi Web interni, perché il traffico Web arriva attraverso il dispositivo di bilanciamento del carico hardware e il traffico del pool SIP interno passa attraverso il servizio di bilanciamento del carico DNS. Questo requisito deve essere soddisfatto.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-p106">For an Front End pool (not shown in the example), the internal SIP pool FQDN must be different from the internal web services FQDN, because web traffic comes through the hardware load balancer and the internal SIP pool traffic travels comes through the DNS load balancer. This requirement must be met.</span></span>

  - <span data-ttu-id="b5b4a-131">Una distribuzione di Lync Server Standard Edition non richiede o consente l'override di un FQDN dei servizi Web interni perché questo server non è in grado di bilanciare il carico.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-131">A Lync Server Standard Edition deployment does not need or allow an internal web services FQDN to be overridden because this server cannot be load balanced.</span></span>

  - <span data-ttu-id="b5b4a-132">Se nel proprio ambiente si dispone di un dispositivo di bilanciamento del carico hardware utilizzato sia per il traffico SIP interno che per quello Web, il generatore di topologie non è in grado di effettuare la distinzione.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-132">If you have a hardware load balancer in your environment that you use for both internal SIP and web traffic, the Topology Builder cannot make the distinction.</span></span>
    
    <span data-ttu-id="b5b4a-133">Gli FQDN dei servizi Web devono essere facilmente differenziati l'uno dall'altro; Questo aiuta a garantire che i client punti di reindirizzamento URL verso il server appropriato.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-133">Web service FQDNs should be easily-differentiated from one another; that helps to ensure that URL redirection points clients towards the appropriate server.</span></span> <span data-ttu-id="b5b4a-134">Ad esempio, se si dispone di due FQDN, è possibile prendere in considerazione la denominazione di un meeting.contoso.com e l'altro conferencing.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-134">For example, if you have two FQDNs you might consider naming one meeting.contoso.com and the other conferencing.contoso.com.</span></span> <span data-ttu-id="b5b4a-135">È possibile che si verifichino problemi di reindirizzamento se sono presenti FQDN con nomi simili, ad esempio meet1.contoso.com e meet2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-135">You could potentially run into redirection issues if you have FQDNs with more similar names, such as meet1.contoso.com and meet2.contoso.com.</span></span>

<span data-ttu-id="b5b4a-136">I servizi Web esterni operano in combinazione con un proxy inverso nella rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-136">The external web services works in conjunction with a reverse proxy in the perimeter network.</span></span> <span data-ttu-id="b5b4a-137">Consente ai client di accedere all'esterno utilizzando questi servizi Web.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-137">It provides clients external access to by using these web services.</span></span> <span data-ttu-id="b5b4a-138">Gli FQDN configurati in questo articolo vengono inviati ai client quando eseguono l'accesso e vengono utilizzati per riportare una connessione HTTPS al proxy inverso quando si effettua la connessione in remoto.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-138">The FQDNs configured here are sent to clients when they log on, and are used to make an HTTPS connection back to the reverse proxy when connecting remotely.</span></span> <span data-ttu-id="b5b4a-139">Il server proxy inverso inoltra il nome di dominio completo del servizio Web esterno a un dispositivo di bilanciamento del carico hardware interno o direttamente al pool.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-139">The reverse-proxy server forwards the external web service FQDN to an internal hardware load balancer, or directly to the pool.</span></span> <span data-ttu-id="b5b4a-140">Il proxy inverso deve essere in grado di risolvere il nome di dominio completo dei servizi Web esterni nell'indirizzo IP del server Web interno.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-140">The reverse proxy must be able to resolve the external web services FQDN to the IP address of the internal Web server.</span></span> <span data-ttu-id="b5b4a-141">L'nome dei servizi Web esterni deve essere risolvibile nella rete Internet pubblica.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-141">The external web services FDQN must be resolvable in the public Internet.</span></span>

<span data-ttu-id="b5b4a-142">Se il server interno è un server Standard Edition, il nome di dominio completo interno è il nome di dominio completo del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-142">If your internal server is a Standard Edition server, the internal FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="b5b4a-143">Se il server interno è un pool Front End, l'FQDN è un IP virtuale (VIP) dello strumento di bilanciamento del carico hardware che gestisce il bilanciamento del carico dei server della Web farm interna.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-143">If your internal server is a Front End pool, the FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="b5b4a-144">È necessario un dispositivo di bilanciamento del carico hardware in un pool Front End con più di un server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-144">A hardware load balancer is required in a Front End pool with more than one Enterprise Edition server.</span></span> <span data-ttu-id="b5b4a-145">Non è invece necessario per un server Standard Edition o un singolo Enterprise Edition Front End Server.</span><span class="sxs-lookup"><span data-stu-id="b5b4a-145">A load balancer is not required for a Standard Edition server or a single Enterprise Edition Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

