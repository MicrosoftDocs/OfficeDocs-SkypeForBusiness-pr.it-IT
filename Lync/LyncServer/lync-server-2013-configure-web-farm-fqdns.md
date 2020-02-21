---
title: 'Lync Server 2013: configurare i nomi di dominio completi della Web farm'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46cca998a35a7519675cd787f5887f2a65d491c4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a><span data-ttu-id="e6753-102">Configurare i nomi di dominio completi della Web farm per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6753-102">Configure web farm FQDNs for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6753-103">_**Ultimo argomento modificato:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="e6753-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="e6753-104">Quando è stata definita la configurazione del server Standard Edition, del pool Front End, del Director o del pool di Director in Generatore di topologie, è necessario configurare un nome di dominio completo (FQDN) dei servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="e6753-104">When you defined the configuration of the Standard Edition server, Front End pool, Director or Director pool in Topology Builder, you configure an external web services fully qualified domain name (FQDN).</span></span> <span data-ttu-id="e6753-105">Durante il processo di accesso di un client ospitato nel server Standard Edition o nel pool Front End, i nomi FQDN dei servizi Web configurati vengono inviati tramite il provisioning di tipo in-band.</span><span class="sxs-lookup"><span data-stu-id="e6753-105">During the log on process of a client homed in the Standard Edition server or Front End pool, the configured web services FQDNs are sent by way of in-band provisioning.</span></span> <span data-ttu-id="e6753-106">Se è necessario aggiungere o modificare l'URL dei servizi Web esterni, è possibile utilizzare Generatore di topologie per configurare o riconfigurare la configurazione dei servizi Web utilizzando la procedura descritta in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e6753-106">If you need to add or change the external web services URL, you use Topology Builder to configure or reconfigure the web services configuration using the procedure in this topic.</span></span>

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a><span data-ttu-id="e6753-107">Per configurare l'FQDN di un pool esterno per i servizi Web</span><span class="sxs-lookup"><span data-stu-id="e6753-107">To configure an external pool FQDN for web services</span></span>

1.  <span data-ttu-id="e6753-108">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="e6753-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="e6753-109">In Generatore di topologie fare clic con il pulsante destro del mouse sul nome del pool da modificare, quindi fare clic su **modifica proprietà**nell'albero della console in **Standard Edition Front**-end, **Enterprise Edition front end**e **Director**.</span><span class="sxs-lookup"><span data-stu-id="e6753-109">In Topology Builder, in the console tree under **Standard Edition Front Ends**, **Enterprise Edition Front Ends**, and **Directors**, right-click the pool name that you need to edit, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="e6753-110">Nella sezione **Servizi Web** aggiungere o modificare l'FQDN per i servizi\*\*\*\* Web esterni.</span><span class="sxs-lookup"><span data-stu-id="e6753-110">In the **Web services** section, add or edit the **External web services FQDN**.</span></span>

4.  <span data-ttu-id="e6753-p102">Controllare e modificare i valori di **Porte di attesa** sia per HTTP che per HTTPS. I valori predefiniti saranno i seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6753-p102">Review and adjust the **Listening ports** for both HTTP and HTTPS. The defaults will be:</span></span>
    
      - <span data-ttu-id="e6753-113">**Porte di attesa:** HTTP 8080, HTTPS 4443</span><span class="sxs-lookup"><span data-stu-id="e6753-113">**Listening ports:** HTTP 8080, HTTPS 4443</span></span>
    
      - <span data-ttu-id="e6753-114">**Porte pubblicate:** HTTP 80, HTTPS 443</span><span class="sxs-lookup"><span data-stu-id="e6753-114">**Published ports:** HTTP 80, HTTPS 443</span></span>
    
    <span data-ttu-id="e6753-115">Dove per **Porte di attesa** si intendono le porte che verranno configurate per i servizi Web esterni per ricevere le richieste dal proxy inverso e per **Porte pubblicate** si intendono le porte pubblicate esternamente dal proxy inverso e comunicate ai client durante il provisioning di tipo in-band.</span><span class="sxs-lookup"><span data-stu-id="e6753-115">Where the **Listening ports** is the port that the external web services will be configured to receive requests from the reverse proxy, and the **Published ports** is the ports that are published externally by the reverse proxy and is communicated to clients during in-band provisioning.</span></span>

5.  <span data-ttu-id="e6753-116">Dopo aver aggiunto e aggiornato le configurazioni, fare clic su **OK** per continuare.</span><span class="sxs-lookup"><span data-stu-id="e6753-116">When you have completed your additions and updates, click **OK** to continue.</span></span>

6.  <span data-ttu-id="e6753-117">Fare clic con il pulsante destro del mouse su **Lync Server 2013**e quindi scegliere **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="e6753-117">Right-click **Lync Server 2013**, and then click **Publish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e6753-118">Al termine della pubblicazione, è possibile che venga visualizzato un collegamento in cui viene indicato che devono essere eseguiti passaggi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e6753-118">After publishing successfully completes, a link may be presented that informs you that there are additional steps that need to be taken.</span></span> <span data-ttu-id="e6753-119">Se si fa clic sul collegamento, verrà aperto un elenco dei server coinvolti dalle modifiche apportate in Generatore di topologie che richiederanno di rieseguire la distribuzione guidata di Lync Server in ogni server elencato per aggiornare la configurazione dei componenti aggiunti, rimossi o modificati.</span><span class="sxs-lookup"><span data-stu-id="e6753-119">The link, if clicked, opens a list of servers affected by the changes made in Topology Builder that will require you to re-run the Lync Server Deployment Wizard on each listed server to update the configuration for added, removed, or changed components.</span></span>

    
    </div>

7.  <span data-ttu-id="e6753-120">Ripetere questi passaggi per ogni server Standard Edition, il pool Front End, il Director o il pool di Director nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e6753-120">Repeat these steps for each Standard Edition server, Front End pool, Director or Director pool in the organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

