---
title: 'Lync Server 2013: pubblicare la topologia aggiornata'
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
ms.openlocfilehash: 5a0a690d38d6f7d348cdaf12503b08027bc4c0f4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a><span data-ttu-id="4f73d-102">Pubblicare la topologia aggiornata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f73d-102">Publish the updated topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f73d-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4f73d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4f73d-104">Dopo aver aggiornato la topologia in Generatore di topologie, è necessario pubblicare la topologia nell'archivio di gestione centrale prima di poter configurare e utilizzare il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4f73d-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Persistent Chat Server.</span></span> <span data-ttu-id="4f73d-105">In tutti i server della topologia vengono replicate copie di sola lettura dei dati in modo che tutti i server siano sincronizzati con la topologia e altre modifiche della configurazione.</span><span class="sxs-lookup"><span data-stu-id="4f73d-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-an-updated-topology"></a><span data-ttu-id="4f73d-106">Per pubblicare una topologia aggiornata</span><span class="sxs-lookup"><span data-stu-id="4f73d-106">To publish an updated topology</span></span>

<span data-ttu-id="4f73d-107">Prima di pubblicare la topologia, installare i database per il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4f73d-107">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="4f73d-108">Utilizzare Generatore di topologie per installare i database selezionando **azione** e **Installa database**.</span><span class="sxs-lookup"><span data-stu-id="4f73d-108">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>

1.  <span data-ttu-id="4f73d-109">In un computer in cui è in esecuzione Lync Server 2013 o in cui sono installati gli strumenti di amministrazione di Lync Server, accedere utilizzando un account membro del gruppo **Domain Admins** e del gruppo **RTCUniversalServerAdmins** . e con autorizzazioni di controllo completo, ovvero lettura, scrittura e modifica, nell'archivio file da utilizzare per l'archivio file del server Chat persistente, in modo che il generatore di topologie possa configurare gli elenchi di controllo di accesso discrezionale necessari o un account con diritti utente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="4f73d-109">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>

2.  <span data-ttu-id="4f73d-110">Avviare Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="4f73d-110">Start Topology Builder.</span></span> <span data-ttu-id="4f73d-111">Selezionare **Scarica topologia dalla distribuzione esistente** o **Apri topologia da un file locale**, se la topologia è stata salvata in locale.</span><span class="sxs-lookup"><span data-stu-id="4f73d-111">Select **Download Topology from existing deployment**, or **Open Topology from a local file** if you saved it locally.</span></span>

3.  <span data-ttu-id="4f73d-112">Nell'albero della console fare clic con il pulsante destro del mouse su **Lync Server 2013**e quindi scegliere **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="4f73d-112">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="4f73d-113">Nella pagina **Pubblicare la topologia** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4f73d-113">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="4f73d-114">Nella pagina **Pubblicazione guidata completata** verificare che la topologia sia stata pubblicata correttamente e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="4f73d-114">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4f73d-115">Dopo aver pubblicato la topologia, è necessario configurare il supporto per il server Chat persistente prima che sia possibile archiviare qualsiasi contenuto.</span><span class="sxs-lookup"><span data-stu-id="4f73d-115">After publishing the topology, you must configure support for Persistent Chat Server before any content can be archived.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

