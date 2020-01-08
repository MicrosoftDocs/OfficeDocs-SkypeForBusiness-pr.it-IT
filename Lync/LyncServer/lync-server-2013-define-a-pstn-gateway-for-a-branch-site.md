---
title: 'Lync Server 2013: Definire un gateway PSTN per un sito di succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c253f82001fef4dd52e19dccb11e7ac77bb12417
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="ff56d-102">Definire un gateway PSTN per un sito di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff56d-102">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff56d-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ff56d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ff56d-104">Eseguire questa procedura nel sito centrale, che contiene almeno un pool Front-end o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ff56d-104">Perform this procedure at the central site, which contains at least one Front End pool or Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ff56d-105">Prima di eseguire la procedura, è necessario che siano presenti le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ff56d-105">Before you perform the procedure, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="ff56d-106">Il software di&nbsp;comunicazione di Lync Server 2013 deve essere configurato nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="ff56d-106">Lync Server 2013&nbsp;communications software must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="ff56d-107">Mediation Server deve essere distribuito nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="ff56d-107">Mediation Server must be deployed at the central site.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a><span data-ttu-id="ff56d-108">Per definire un gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="ff56d-108">To define a PSTN gateway</span></span>

1.  <span data-ttu-id="ff56d-109">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Microsoft Lync Server**e quindi su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ff56d-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="ff56d-110">Nell'albero della console espandere il sito centrale, espandere **siti di filiale**, espandere il nome del sito della filiale per la definizione di un gateway PSTN (Public Switched Telephone Network), quindi espandere i **componenti condivisi**.</span><span class="sxs-lookup"><span data-stu-id="ff56d-110">In the console tree, expand the central site, expand **Branch Office Sites**, expand name of the branch site that you want to define a public switched telephone network (PSTN) gateway for, and then expand **Shared Components**.</span></span>

3.  <span data-ttu-id="ff56d-111">Fare clic con il pulsante destro del mouse su **gateway PSTN**e quindi scegliere **nuovo gateway IP/PSTN**.</span><span class="sxs-lookup"><span data-stu-id="ff56d-111">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="ff56d-112">Nella finestra di dialogo **Definisci nuovo gateway IP/PSTN** fare clic su **FQDN gateway o indirizzo IP**e quindi digitare il nome di dominio completo (FQDN) o l'indirizzo IP del gateway che si sta distribuendo nel sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="ff56d-112">In the **Define New IP/PSTN Gateway** dialog box, click **Gateway FQDN or IP Address**, and then type the fully qualified domain name (FQDN) or IP address of the gateway that you are deploying at the branch site.</span></span>

5.  <span data-ttu-id="ff56d-113">Fare clic su **porta di ascolto per gateway IP/PSTN**e quindi accettare i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="ff56d-113">Click **Listening Port for IP/PSTN Gateway**, and then accept the default values.</span></span>

6.  <span data-ttu-id="ff56d-114">Nell'elenco **protocollo di trasporto SIP** fare clic sul protocollo di trasporto usato dal gateway e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff56d-114">In the **SIP Transport Protocol** list, click the transport protocol the gateway uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff56d-115">Per motivi di sicurezza, ti consigliamo vivamente di usare un gateway PSTN che supporta TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="ff56d-115">For security reasons, we strongly recommend that you use a PSTN gateway that supports Transport Layer Security (TLS).</span></span>

    
    </div>

<div>


> [!TIP]  
> <span data-ttu-id="ff56d-116">Utilizzare il cmdlet <STRONG>Set-CsPstnGateway</STRONG> per modificare le proprietà di un gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="ff56d-116">Use the cmdlet <STRONG>Set-CsPstnGateway</STRONG> to modify properties of a PSTN gateway.</span></span> <span data-ttu-id="ff56d-117">Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>, nella Guida di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ff56d-117">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>, in the Lync Server Management Shell Help.</span></span>



</div>

<span data-ttu-id="ff56d-118">**Passaggio successivo** per la resilienza del sito di succursale: [configurazione degli utenti per la resilienza del sito di succursale in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="ff56d-118">**Next step** for branch-site resiliency: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ff56d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff56d-119">See Also</span></span>


[<span data-ttu-id="ff56d-120">Opzioni di distribuzione di gateway PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff56d-120">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

