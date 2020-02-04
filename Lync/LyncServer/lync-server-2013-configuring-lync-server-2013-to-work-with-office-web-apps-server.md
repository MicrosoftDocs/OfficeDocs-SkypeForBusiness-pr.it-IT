---
title: Configurazione di Lync Server 2013 per l'utilizzo con Office Web Apps Server
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
ms.openlocfilehash: f3516822064d0fd42b44edb7af73b321644c36c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a><span data-ttu-id="c0a2a-102">Configurazione di Lync Server 2013 per l'utilizzo con Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="c0a2a-102">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0a2a-103">_**Argomento Ultima modifica:** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="c0a2a-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="c0a2a-104">Prima di poter configurare Lync Server 2013 per l'uso di Office Web Apps Server, è necessario che Office Web Apps Server venga distribuito e configurato.</span><span class="sxs-lookup"><span data-stu-id="c0a2a-104">Before you can configure Lync Server 2013 to use Office Web Apps Server, Office Web Apps Server must be deployed and configured.</span></span> <span data-ttu-id="c0a2a-105">Vedere la **Guida ai documenti per la distribuzione di Office Web Apps Server e Office** Web Apps per informazioni dettagliate su come installare e configurare un singolo server di Office Web Apps o per informazioni su come installare e configurare una farm di Office Web Apps Server per una disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="c0a2a-105">See the document **Guide to Deploying Office Web Apps Server and Office Web Apps** for detail information on how to install and configure a single Office Web Apps Server, or for information on how to install and configure an Office Web Apps Server Farm for high availability.</span></span>

<span data-ttu-id="c0a2a-106">Dopo l'installazione di Office Web Apps Server e la Web farm correttamente configurata, è necessario configurare Lync Server per comunicare con il nuovo server. a questo scopo, Aggiungi l'URL di individuazione del server Office Web Apps alla topologia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c0a2a-106">After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Lync Server to communicate with the new server; this is done by adding the Office Web Apps Server discovery URL to your Lync Server topology.</span></span> <span data-ttu-id="c0a2a-107">Per aggiungere Office Web Apps Server alla topologia, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="c0a2a-107">To add Office Web Apps Server to your topology, complete the following steps:</span></span>

1.  <span data-ttu-id="c0a2a-108">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c0a2a-108">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="c0a2a-109">Nella finestra di dialogo **Generatore di topologia** selezionare **Scarica topologia da distribuzione esistente** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0a2a-109">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="c0a2a-110">Nella finestra di dialogo **Salva topologia come** Digitare un nome per il documento della topologia, ad esempio **PreWebAppsServerTopology**, nella casella **nome file** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c0a2a-110">In the **Save Topology As** dialog box, type a name for your topology document (for example, **PreWebAppsServerTopology**) in the **File name** box and then click **Save**.</span></span> <span data-ttu-id="c0a2a-111">Questa topologia può essere recuperata e ripubblicata in seguito se si verificano problemi con la nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="c0a2a-111">This topology can later be retrieved and republished if you encounter problems with your new topology.</span></span>

4.  <span data-ttu-id="c0a2a-112">In Generatore di topologie espandere **Lync Server 2013**, espandere il nome del sito, espandere i **pool di front-end di Enterprise Edition**, fare clic con il pulsante destro del mouse sul nome di uno dei pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c0a2a-112">In Topology Builder, expand **Lync Server 2013**, expand the name of your site, expand **Enterprise Edition Front End pools**, right-click the name of one of your pools, and then click **Edit Properties**.</span></span>

5.  <span data-ttu-id="c0a2a-113">Nella scheda **generale** della finestra di dialogo **modifica proprietà** individuare il titolo **associato a Office Web Apps Server** e quindi fare clic su **nuovo** (o selezionare un server di Office Web Apps esistente nell'elenco a discesa).</span><span class="sxs-lookup"><span data-stu-id="c0a2a-113">In the **Edit Properties** dialog box, on the **General** tab, find the heading **Associate Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

6.  <span data-ttu-id="c0a2a-114">Nella finestra di dialogo **Definisci nuovo server Office Web Apps** Digitare il nome di dominio completo (FQDN) del computer Office Web Apps Server nella casella **FQDN server di Office Web Apps** . Quando si esegue questa operazione, l'URL di individuazione del server di Office Web Apps deve essere automaticamente immesso nella casella **URL individuazione server di Office Web Apps** .</span><span class="sxs-lookup"><span data-stu-id="c0a2a-114">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="c0a2a-115">Se il server Office Web Apps è installato in locale e nella stessa area di rete di Lync Server 2013, l'opzione **Office Web Apps Server è distribuita in una rete esterna, ovvero perimetro/Internet,** non deve essere selezionata.</span><span class="sxs-lookup"><span data-stu-id="c0a2a-115">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="c0a2a-116">Se il server Office Web Apps è distribuito all'esterno del firewall interno, selezionare l'opzione **Office Web Apps Server è distribuito in una rete esterna (ovvero perimetro/Internet)**.</span><span class="sxs-lookup"><span data-stu-id="c0a2a-116">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>

7.  <span data-ttu-id="c0a2a-117">Nella finestra di dialogo **Definisci nuovo server Office Web Apps** fare clic su **OK**e quindi su **OK** nella finestra di dialogo **modifica proprietà** .</span><span class="sxs-lookup"><span data-stu-id="c0a2a-117">In the **Define New Office Web Apps Server** dialog box, click **OK**, and then click **OK** in the **Edit Properties** dialog box.</span></span> <span data-ttu-id="c0a2a-118">L'URL di individuazione di Office Web Apps verrà quindi elencato come una delle associazioni del pool.</span><span class="sxs-lookup"><span data-stu-id="c0a2a-118">The Office Web Apps discovery URL will then be listed as one of the pool's Associations.</span></span>

<span data-ttu-id="c0a2a-119">Sarà necessario ripetere questa procedura per ogni pool che deve essere associato al server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="c0a2a-119">You will have to repeat this process for each pool that needs to be associated with your Office Web Apps Server.</span></span>

<span data-ttu-id="c0a2a-120">Dopo aver aggiunto l'URL di individuazione alla topologia, è necessario pubblicare la topologia aggiornata.</span><span class="sxs-lookup"><span data-stu-id="c0a2a-120">After you have added the discovery URL to the topology you must then publish this updated topology.</span></span> <span data-ttu-id="c0a2a-121">Per eseguire questa operazione in Generatore di topologie:</span><span class="sxs-lookup"><span data-stu-id="c0a2a-121">To do that in Topology Builder:</span></span>

1.  <span data-ttu-id="c0a2a-122">Fare clic su **azione** e quindi su **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="c0a2a-122">Click **Action** and then click **Publish Topology**.</span></span>

2.  <span data-ttu-id="c0a2a-123">Nella pagina **Pubblica topologia** della procedura guidata Pubblica topologia fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c0a2a-123">In the Publish Topology wizard, on the **Publish the Topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="c0a2a-124">Nella pagina **completamento pubblicazione guidata** fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="c0a2a-124">On the **Publishing wizard complete** page, click **Finish**.</span></span>

4.  <span data-ttu-id="c0a2a-125">Chiudi generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="c0a2a-125">Close Topology Builder.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

