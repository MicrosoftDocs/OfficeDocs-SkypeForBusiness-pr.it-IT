---
title: 'Lync Server 2013: Definire un Survivable Branch Appliance o un Survivable Branch Server'
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
ms.openlocfilehash: df5577ff0211afd005feb8fea4788598a03d536e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="eb16f-102">Definire un Survivable Branch Appliance o un Survivable Branch Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb16f-102">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb16f-103">_**Argomento Ultima modifica:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="eb16f-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="eb16f-104">Eseguire questa procedura nel sito centrale se non è stata definita l'appliance o il server della filiale Survivable quando è stato aggiunto alla topologia.</span><span class="sxs-lookup"><span data-stu-id="eb16f-104">Perform this procedure at the central site if you did not define the Survivable Branch Appliance or Server when you added it to your topology.</span></span>

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="eb16f-105">Per definire un Survivable Branch Appliance o Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="eb16f-105">To define a Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="eb16f-106">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="eb16f-106">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="eb16f-107">Nell'albero della console espandere il sito centrale, espandere **siti di succursale**e quindi espandere il nome del sito della filiale in cui si prevede di distribuire il Survivable Branch Appliance o Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="eb16f-107">In the console tree, expand the central site, expand **Branch sites**, and then expand the name of the branch site where you plan to deploy the Survivable Branch Appliance or Survivable Branch Server.</span></span>

3.  <span data-ttu-id="eb16f-108">Fare clic con il pulsante destro del mouse su **Survivable Branch Appliances**e quindi scegliere **Nuovo Survivable Branch Appliance**.</span><span class="sxs-lookup"><span data-stu-id="eb16f-108">Right-click **Survivable Branch Appliances**, and then click **New Survivable Branch Appliance**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="eb16f-109"><STRONG>Survivable Branch Appliances</STRONG> è la posizione in cui puoi definire Survivable Branch Servers e Survivable Branch Appliances.</span><span class="sxs-lookup"><span data-stu-id="eb16f-109"><STRONG>Survivable Branch Appliances</STRONG> is where you define Survivable Branch Servers and Survivable Branch Appliances.</span></span>

    
    </div>

4.  <span data-ttu-id="eb16f-110">Nella finestra di dialogo **Definisci Survivable Branch Appliance** fare clic su **FQDN**, digitare il nome di dominio completo (FQDN) del Survivable Branch Appliance o Survivable Branch Server che verrà distribuito in questo sito della filiale e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="eb16f-110">In the **Define Survivable Branch Appliance** dialog box, click **FQDN**, type the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server you will deploy at this branch site, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="eb16f-111">Se si definisce un Survivable Branch Appliance, il nome immesso in <STRONG>FQDN</STRONG> deve essere uguale a quello dell'FQDN di Survivable Branch Appliance assegnato all'attributo <STRONG>servicePrincipalName</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="eb16f-111">If you are defining a Survivable Branch Appliance, the name you enter in <STRONG>FQDN</STRONG> must be the same as the Survivable Branch Appliance FQDN you assigned to the <STRONG>servicePrincipalName</STRONG> attribute.</span></span> <span data-ttu-id="eb16f-112">Per informazioni dettagliate, vedere <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">aggiungere un Survivable Branch Appliance a Active Directory in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="eb16f-112">For details, see <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</A>.</span></span>

    
    </div>

5.  <span data-ttu-id="eb16f-113">Fare clic su **pool Front End**, fare clic sul server front-end (pool di servizi utente) nel sito centrale a cui si connette questo Survivable Branch Appliance o Survivable Branch Server e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="eb16f-113">Click **Front End pool**, click the Front End Server (User Services pool) at the central site that this Survivable Branch Appliance or Survivable Branch Server will connect to, and then click **Next**.</span></span>

6.  <span data-ttu-id="eb16f-114">Fare clic su **Edge Server**, fare clic sul pool di bordi in cui questo Survivable Branch Appliance o Survivable Branch Server si connetterà per consentire la connettività PSTN agli utenti remoti del sito della filiale e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="eb16f-114">Click **Edge Server**, click the Edge pool that this Survivable Branch Appliance or Survivable Branch Server will connect to provide PSTN connectivity to remote users of the branch site, and then click **Next**.</span></span>

7.  <span data-ttu-id="eb16f-115">Fare clic su **FQDN gateway o indirizzo IP**e quindi digitare il nome di dominio completo o l'indirizzo IP del peer del gateway a cui è associato il Survivable Branch Appliance o Survivable Branch Server per il routing delle chiamate PSTN in ingresso o in uscita.</span><span class="sxs-lookup"><span data-stu-id="eb16f-115">Click **Gateway FQDN or IP Address**, and then type the FQDN or IP address of the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound or outbound PSTN calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="eb16f-116">Se si definisce un Survivable Branch Appliance, si tratta del gateway a cui il Mediation Server all'interno del Survivable Branch Appliance si connetterà per la connettività PSTN.</span><span class="sxs-lookup"><span data-stu-id="eb16f-116">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span>

    
    </div>

8.  <span data-ttu-id="eb16f-117">Fare clic su **porta di ascolto per gateway IP/PSTN**e quindi accettare la porta predefinita.</span><span class="sxs-lookup"><span data-stu-id="eb16f-117">Click **Listening Port for IP/PSTN Gateway**, and then accept the default port.</span></span>

9.  <span data-ttu-id="eb16f-118">In **protocollo di trasporto SIP**fare clic sul protocollo di trasporto che verrà usato da Survivable Branch Appliance o Survivable Branch Server e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="eb16f-118">In **Sip Transport Protocol**, click the transport protocol the Survivable Branch Appliance or Survivable Branch Server will use, and then click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb16f-119">Per motivi di sicurezza, ti consigliamo vivamente di usare Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="eb16f-119">For security reasons, we strongly recommend that you use Transport Layer Security (TLS).</span></span> <span data-ttu-id="eb16f-120">Se si definisce un Survivable Branch Appliance, vedere la documentazione del fornitore di Survivable Branch Appliance per verificare che il Survivable Branch Appliance supporti il protocollo TLS.</span><span class="sxs-lookup"><span data-stu-id="eb16f-120">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>

    
    </div>

10. <span data-ttu-id="eb16f-121">Nell'albero della console fare clic con il pulsante destro del mouse sul nuovo dispositivo o server Survivable Branch, scegliere **topologia**e quindi fare clic su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="eb16f-121">In the console tree, right-click the new Survivable Branch Appliance or Server, click **Topology**, and then click **Publish**.</span></span>

<span data-ttu-id="eb16f-122">**Passaggio successivo**: [distribuire un Survivable Branch Appliance o un server con Lync Server 2013-attività del sito succursale](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span><span class="sxs-lookup"><span data-stu-id="eb16f-122">**Next step**: [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

