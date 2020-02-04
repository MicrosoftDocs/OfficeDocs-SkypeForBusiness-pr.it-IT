---
title: 'Lync Server 2013: Pubblicare la topologia aggiornata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4500d12c7b0a054ccce910f27c80f9aaa83eccaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a><span data-ttu-id="b9181-102">Pubblicare la topologia aggiornata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9181-102">Publish the updated topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9181-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b9181-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b9181-104">Dopo l'aggiornamento della topologia in Generatore di topologie, è necessario pubblicare la topologia in Central Management Store prima di poter configurare e usare il server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b9181-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Persistent Chat Server.</span></span> <span data-ttu-id="b9181-105">Le copie di sola lettura dei dati vengono replicate in tutti i server della topologia per garantire la sincronizzazione di tutti i server con la topologia e altre modifiche alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="b9181-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-an-updated-topology"></a><span data-ttu-id="b9181-106">Per pubblicare una topologia aggiornata</span><span class="sxs-lookup"><span data-stu-id="b9181-106">To publish an updated topology</span></span>

<span data-ttu-id="b9181-107">Prima di pubblicare la topologia, installare i database per il server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b9181-107">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="b9181-108">Usare generatore di topologie per installare i database selezionando **azione** e **Installa database**.</span><span class="sxs-lookup"><span data-stu-id="b9181-108">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>

1.  <span data-ttu-id="b9181-109">In un computer che esegue Lync Server 2013 o in cui sono installati gli strumenti di amministrazione di Lync Server, accedere usando un account che sia membro del gruppo **Domain Admins** e del gruppo **RTCUniversalServerAdmins** . e con autorizzazioni di controllo completo (ovvero, lettura, scrittura e modifica) nell'archivio di file da usare per il file Store del server di chat persistente (in modo che il generatore di topologia possa configurare gli elenchi di controllo di accesso discrezionale (DACL) necessari) o un account con diritti utente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="b9181-109">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>

2.  <span data-ttu-id="b9181-110">Avviare Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="b9181-110">Start Topology Builder.</span></span> <span data-ttu-id="b9181-111">Selezionare **Scarica la topologia dalla distribuzione esistente**o **Apri la topologia da un file locale** se è stata salvata localmente.</span><span class="sxs-lookup"><span data-stu-id="b9181-111">Select **Download Topology from existing deployment**, or **Open Topology from a local file** if you saved it locally.</span></span>

3.  <span data-ttu-id="b9181-112">Nell'albero della console fare clic con il pulsante destro del mouse su **Lync Server 2013**e quindi scegliere **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="b9181-112">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="b9181-113">Nella pagina **pubblica la topologia** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b9181-113">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="b9181-114">Nella pagina **completamento pubblicazione guidata** verificare che la topologia sia stata pubblicata correttamente e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="b9181-114">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b9181-115">Dopo aver pubblicato la topologia, è necessario configurare il supporto per il server di chat persistente prima di poter archiviare qualsiasi contenuto.</span><span class="sxs-lookup"><span data-stu-id="b9181-115">After publishing the topology, you must configure support for Persistent Chat Server before any content can be archived.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

