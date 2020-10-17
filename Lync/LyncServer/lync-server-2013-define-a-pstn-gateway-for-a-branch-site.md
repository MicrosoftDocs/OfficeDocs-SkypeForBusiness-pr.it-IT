---
title: 'Lync Server 2013: definire un gateway PSTN per un sito di succursale'
description: 'Lync Server 2013: definire un gateway PSTN per un sito di succursale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17fb1004366fef17f57d7e8b7d14696e1e3f0fbe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567772"
---
# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="9a4e1-103">Definire un gateway PSTN per un sito di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a4e1-103">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a4e1-104">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9a4e1-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="9a4e1-105">Eseguire questa procedura nel sito centrale, che contiene almeno un pool Front end o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9a4e1-105">Perform this procedure at the central site, which contains at least one Front End pool or Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9a4e1-106">Prima di eseguire la procedura, è necessario che vengano soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a4e1-106">Before you perform the procedure, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="9a4e1-107">&nbsp;Il software di comunicazione Lync Server 2013 deve essere configurato nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="9a4e1-107">Lync Server 2013&nbsp;communications software must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="9a4e1-108">Il Mediation Server deve essere distribuito nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="9a4e1-108">Mediation Server must be deployed at the central site.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a><span data-ttu-id="9a4e1-109">Per definire un gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="9a4e1-109">To define a PSTN gateway</span></span>

1.  <span data-ttu-id="9a4e1-110">Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server** e quindi **Generatore di topologie di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9a4e1-110">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="9a4e1-111">Nell'albero della console espandere il sito centrale, espandere **Siti di succursale** e quindi espandere il nome del sito derivato per il quale si desidera definire un gateway PSTN. Espandere quindi **Componenti condivisi**.</span><span class="sxs-lookup"><span data-stu-id="9a4e1-111">In the console tree, expand the central site, expand **Branch Office Sites**, expand name of the branch site that you want to define a public switched telephone network (PSTN) gateway for, and then expand **Shared Components**.</span></span>

3.  <span data-ttu-id="9a4e1-112">Fare clic con il pulsante destro del mouse su **Gateway PSTN** e quindi scegliere **Nuovo gateway IP/PSTN**.</span><span class="sxs-lookup"><span data-stu-id="9a4e1-112">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="9a4e1-113">Nella finestra di dialogo **Definisci nuovo gateway IP/PSTN** fare clic su **FQDN gateway o indirizzo IP** e quindi digitare il nome di dominio completo (FQDN) o l'indirizzo IP del gateway che si sta distribuendo nel sito derivato.</span><span class="sxs-lookup"><span data-stu-id="9a4e1-113">In the **Define New IP/PSTN Gateway** dialog box, click **Gateway FQDN or IP Address**, and then type the fully qualified domain name (FQDN) or IP address of the gateway that you are deploying at the branch site.</span></span>

5.  <span data-ttu-id="9a4e1-114">Fare clic su **Porta di attesa per gateway IP/PSTN** e quindi accettare i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="9a4e1-114">Click **Listening Port for IP/PSTN Gateway**, and then accept the default values.</span></span>

6.  <span data-ttu-id="9a4e1-115">Nell'elenco **Protocollo trasporto SIP** fare clic sul protocollo di trasporto utilizzato dal gateway e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9a4e1-115">In the **SIP Transport Protocol** list, click the transport protocol the gateway uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9a4e1-116">Per motivi di sicurezza, è consigliabile utilizzare un gateway PSTN che supporti TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="9a4e1-116">For security reasons, we strongly recommend that you use a PSTN gateway that supports Transport Layer Security (TLS).</span></span>

    
    </div>

<div>


> [!TIP]  
> <span data-ttu-id="9a4e1-117">Utilizzare il cmdlet <STRONG>Set-CsPstnGateway</STRONG> per modificare le proprietà di un gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="9a4e1-117">Use the cmdlet <STRONG>Set-CsPstnGateway</STRONG> to modify properties of a PSTN gateway.</span></span> <span data-ttu-id="9a4e1-118">Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>, nella Guida di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9a4e1-118">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>, in the Lync Server Management Shell Help.</span></span>



</div>

<span data-ttu-id="9a4e1-119">**Passaggio successivo** per la resilienza dei siti di succursale: [configurazione degli utenti per la resilienza dei siti di succursale in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="9a4e1-119">**Next step** for branch-site resiliency: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9a4e1-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a4e1-120">See Also</span></span>


[<span data-ttu-id="9a4e1-121">Opzioni di distribuzione di gateway PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a4e1-121">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

