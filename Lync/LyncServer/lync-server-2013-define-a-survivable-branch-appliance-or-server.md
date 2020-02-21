---
title: 'Lync Server 2013: define a Survivable Branch Appliance o server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 329fae20f239f10583b83b64d9b78fa953f6cdc3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="57eb4-102">Definire un Survivable Branch Appliance o un server di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57eb4-102">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57eb4-103">_**Ultimo argomento modificato:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="57eb4-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="57eb4-104">Eseguire questa procedura presso il sito centrale se la Survivable Branch Appliance o il Survivable Branch Server non è stato definito quando è stato aggiunto alla topologia.</span><span class="sxs-lookup"><span data-stu-id="57eb4-104">Perform this procedure at the central site if you did not define the Survivable Branch Appliance or Server when you added it to your topology.</span></span>

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="57eb4-105">Per definire un Survivable Branch Appliance o un Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="57eb4-105">To define a Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="57eb4-106">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**, quindi fare clic su **Generatore di topologie di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="57eb4-106">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="57eb4-107">Nell'albero della console espandere il sito centrale, espandere **siti di succursale**e quindi espandere il nome del sito di succursale in cui si intende distribuire il Survivable Branch Appliance o il Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="57eb4-107">In the console tree, expand the central site, expand **Branch sites**, and then expand the name of the branch site where you plan to deploy the Survivable Branch Appliance or Survivable Branch Server.</span></span>

3.  <span data-ttu-id="57eb4-108">Fare clic con il pulsante destro del mouse su **Survivable Branch Appliance**e quindi scegliere **Nuovo Survivable Branch Appliance**.</span><span class="sxs-lookup"><span data-stu-id="57eb4-108">Right-click **Survivable Branch Appliances**, and then click **New Survivable Branch Appliance**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="57eb4-109"><STRONG>Survivable Branch Appliances</STRONG> è il luogo in cui vengono definiti Survivable Branch Server e Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="57eb4-109"><STRONG>Survivable Branch Appliances</STRONG> is where you define Survivable Branch Servers and Survivable Branch Appliances.</span></span>

    
    </div>

4.  <span data-ttu-id="57eb4-110">Nella finestra di dialogo **Definisci Survivable Branch Appliance** fare clic su **FQDN**, digitare il nome di dominio completo (FQDN) del Survivable Branch Appliance o Survivable Branch Server che si desidera distribuire in questo sito di succursale e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="57eb4-110">In the **Define Survivable Branch Appliance** dialog box, click **FQDN**, type the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server you will deploy at this branch site, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="57eb4-111">Se si sta definendo un Survivable Branch Appliance, il nome immesso in <STRONG>FQDN</STRONG> deve corrispondere a quello dell'FQDN di Survivable Branch Appliance assegnato all'attributo <STRONG>servicePrincipalName</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="57eb4-111">If you are defining a Survivable Branch Appliance, the name you enter in <STRONG>FQDN</STRONG> must be the same as the Survivable Branch Appliance FQDN you assigned to the <STRONG>servicePrincipalName</STRONG> attribute.</span></span> <span data-ttu-id="57eb4-112">Per ulteriori informazioni, vedere <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">aggiungere un Survivable Branch Appliance a Active Directory in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="57eb4-112">For details, see <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</A>.</span></span>

    
    </div>

5.  <span data-ttu-id="57eb4-113">Fare clic su **pool Front End**, fare clic sul front end server (pool di servizi utente) nel sito centrale in cui si connetterà il Survivable Branch Appliance o il Survivable Branch Server e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="57eb4-113">Click **Front End pool**, click the Front End Server (User Services pool) at the central site that this Survivable Branch Appliance or Survivable Branch Server will connect to, and then click **Next**.</span></span>

6.  <span data-ttu-id="57eb4-114">Fare clic su **server perimetrale**, fare clic sul pool perimetrale che è possibile connettere a Survivable Branch Appliance o Survivable Branch Server per garantire la connettività PSTN agli utenti remoti del sito di succursale e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="57eb4-114">Click **Edge Server**, click the Edge pool that this Survivable Branch Appliance or Survivable Branch Server will connect to provide PSTN connectivity to remote users of the branch site, and then click **Next**.</span></span>

7.  <span data-ttu-id="57eb4-115">Fare clic su **FQDN gateway o indirizzo IP**e quindi digitare il nome di dominio completo o l'indirizzo IP del peer gateway a cui è associato il Survivable Branch Appliance o il Survivable Branch Server per il routing delle chiamate PSTN in ingresso o in uscita.</span><span class="sxs-lookup"><span data-stu-id="57eb4-115">Click **Gateway FQDN or IP Address**, and then type the FQDN or IP address of the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound or outbound PSTN calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="57eb4-116">Se si sta definendo un Survivable Branch Appliance, questo è il gateway a cui il Mediation Server all'interno del Survivable Branch Appliance si connetterà per la connettività PSTN.</span><span class="sxs-lookup"><span data-stu-id="57eb4-116">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span>

    
    </div>

8.  <span data-ttu-id="57eb4-117">Fare clic su **Porta di attesa per gateway IP/PSTN** e quindi accettare la porta predefinita.</span><span class="sxs-lookup"><span data-stu-id="57eb4-117">Click **Listening Port for IP/PSTN Gateway**, and then accept the default port.</span></span>

9.  <span data-ttu-id="57eb4-118">In **Protocollo trasporto SIP**fare clic sul protocollo di trasporto che verrà utilizzato dal Survivable Branch Appliance o Survivable Branch Server e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="57eb4-118">In **Sip Transport Protocol**, click the transport protocol the Survivable Branch Appliance or Survivable Branch Server will use, and then click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="57eb4-119">Per motivi di sicurezza, è consigliabile utilizzare Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="57eb4-119">For security reasons, we strongly recommend that you use Transport Layer Security (TLS).</span></span> <span data-ttu-id="57eb4-120">Se si sta definendo un Survivable Branch Appliance, consultare la documentazione del relativo fornitore per verificare che supporti il protocollo TLS.</span><span class="sxs-lookup"><span data-stu-id="57eb4-120">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>

    
    </div>

10. <span data-ttu-id="57eb4-121">Nell'albero della console fare clic con il pulsante destro del mouse sul nuovo Survivable Branch Appliance o Survivable Branch Server, scegliere **Topologia** e quindi fare clic su **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="57eb4-121">In the console tree, right-click the new Survivable Branch Appliance or Server, click **Topology**, and then click **Publish**.</span></span>

<span data-ttu-id="57eb4-122">**Passaggio successivo**: [distribuire un Survivable Branch Appliance or Server with Lync Server 2013-Branch site Task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span><span class="sxs-lookup"><span data-stu-id="57eb4-122">**Next step**: [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

