---
title: Configurazione di Lync Server 2013 per l'utilizzo con il server Office Web Apps
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92409327c28716f804ecc915e0ff4e298e1e42b4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a><span data-ttu-id="7946e-102">Configurazione di Lync Server 2013 per l'utilizzo con il server Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="7946e-102">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7946e-103">_**Ultimo argomento modificato:** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="7946e-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="7946e-104">Prima di poter configurare Lync Server 2013 per l'utilizzo del server Office Web Apps, è necessario distribuire e configurare il server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="7946e-104">Before you can configure Lync Server 2013 to use Office Web Apps Server, Office Web Apps Server must be deployed and configured.</span></span> <span data-ttu-id="7946e-105">Vedere la guida alla distribuzione del server Office Web Apps e di Office Web Apps\*\*\*\* per informazioni dettagliate su come installare e configurare un singolo server Office Web Apps o per informazioni su come installare e configurare una server farm Office Web Apps per la disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="7946e-105">See the document **Guide to Deploying Office Web Apps Server and Office Web Apps** for detail information on how to install and configure a single Office Web Apps Server, or for information on how to install and configure an Office Web Apps Server Farm for high availability.</span></span>

<span data-ttu-id="7946e-106">Dopo l'installazione del server Office Web Apps e la Web farm correttamente configurata, è necessario configurare Lync Server per la comunicazione con il nuovo server. a tale scopo, è possibile aggiungere l'URL di individuazione del server Office Web Apps alla topologia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7946e-106">After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Lync Server to communicate with the new server; this is done by adding the Office Web Apps Server discovery URL to your Lync Server topology.</span></span> <span data-ttu-id="7946e-107">Per aggiungere il server Office Web Apps alla topologia, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7946e-107">To add Office Web Apps Server to your topology, complete the following steps:</span></span>

1.  <span data-ttu-id="7946e-108">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**, quindi fare clic su **Generatore di topologie di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7946e-108">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="7946e-109">Nella finestra di dialogo **Generatore di topologie** selezionare **Scarica topologia dalla distribuzione esistente** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7946e-109">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="7946e-p103">Nella casella **Salva topologia con nome** digitare un nome per il documento della topologia (ad esempio **TopologiaPreServerWebApps**) nella casella **Nome file** e quindi fare clic su **Salva**. Questa topologia potrà essere recuperata e ripubblicata in seguito se si verificano problemi con la nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="7946e-p103">In the **Save Topology As** dialog box, type a name for your topology document (for example, **PreWebAppsServerTopology**) in the **File name** box and then click **Save**. This topology can later be retrieved and republished if you encounter problems with your new topology.</span></span>

4.  <span data-ttu-id="7946e-112">In Generatore di topologie espandere **Lync Server 2013**, espandere il nome del sito, espandere **pool Enterprise Edition front end**, fare clic con il pulsante destro del mouse sul nome di uno dei pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7946e-112">In Topology Builder, expand **Lync Server 2013**, expand the name of your site, expand **Enterprise Edition Front End pools**, right-click the name of one of your pools, and then click **Edit Properties**.</span></span>

5.  <span data-ttu-id="7946e-113">Nella scheda **Generale** della finestra di dialogo **Modifica proprietà** individuare il titolo **Associa il pool a un server Office Web Apps** e quindi fare clic su **Nuovo** oppure selezionare un server Office Web Apps esistente nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="7946e-113">In the **Edit Properties** dialog box, on the **General** tab, find the heading **Associate Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

6.  <span data-ttu-id="7946e-114">Nella finestra di dialogo **Definire un nuovo server Office Web Apps** digitare il nome di dominio completo (FQDN) del computer del server Office Web Apps nella casella **FQDN server Office Web Apps**. L'URL di individuazione del server Office Web Apps dovrebbe comparire così automaticamente nella casella **URL di individuazione server Office Web Apps**.</span><span class="sxs-lookup"><span data-stu-id="7946e-114">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="7946e-115">Se il server Office Web Apps è installato in locale e nella stessa area di rete di Lync Server 2013, il **Server Office Web Apps Option è distribuito in una rete esterna (ovvero perimetro/Internet)** non deve essere selezionata.</span><span class="sxs-lookup"><span data-stu-id="7946e-115">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="7946e-116">Se il server Office Web Apps è distribuito all'esterno del firewall interno, allora selezionare l'opzione **Il server Office Web Apps è distribuito in una rete esterna (perimetro/Internet)**.</span><span class="sxs-lookup"><span data-stu-id="7946e-116">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>

7.  <span data-ttu-id="7946e-p104">Nella finestra di dialogo **Definire un nuovo server Office Web Apps** fare clic su **OK** e quindi fare clic su **OK** nella finestra di dialogo **Modifica proprietà**. L'URL di individuazione di Office Web Apps verrà elencato come una delle associazioni del pool.</span><span class="sxs-lookup"><span data-stu-id="7946e-p104">In the **Define New Office Web Apps Server** dialog box, click **OK**, and then click **OK** in the **Edit Properties** dialog box. The Office Web Apps discovery URL will then be listed as one of the pool's Associations.</span></span>

<span data-ttu-id="7946e-119">Sarà necessario ripetere questa procedura per ogni pool che deve essere associato al server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="7946e-119">You will have to repeat this process for each pool that needs to be associated with your Office Web Apps Server.</span></span>

<span data-ttu-id="7946e-p105">Dopo aver aggiunto l'URL di individuazione alla topologia, è necessario pubblicare la topologia aggiornata, operazione da eseguire in Generatore di topologie:</span><span class="sxs-lookup"><span data-stu-id="7946e-p105">After you have added the discovery URL to the topology you must then publish this updated topology. To do that in Topology Builder:</span></span>

1.  <span data-ttu-id="7946e-122">Fare clic su **Azione** e quindi su **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="7946e-122">Click **Action** and then click **Publish Topology**.</span></span>

2.  <span data-ttu-id="7946e-123">Nella pagina **Pubblicare la topologia** della procedura guidata Pubblica topologia fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7946e-123">In the Publish Topology wizard, on the **Publish the Topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="7946e-124">Nella pagina **Pubblicazione guidata completata** fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="7946e-124">On the **Publishing wizard complete** page, click **Finish**.</span></span>

4.  <span data-ttu-id="7946e-125">Chiudere Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="7946e-125">Close Topology Builder.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

