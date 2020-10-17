---
title: Verificare il completamento della replica utente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e51ff7889b97a58298256cc1a1de3a5d4f901608
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518003"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="79ea5-102">Verificare il completamento della replica utente</span><span class="sxs-lookup"><span data-stu-id="79ea5-102">Verify user replication has completed</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79ea5-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="79ea5-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="79ea5-104">Quando si esegue il cmdlet **Move-CsLegacyUser** , è possibile che si verifichi un errore a causa di informazioni utente tra servizi di dominio Active Directory (ad DS) e i database di Lync Server 2013 che non sono sincronizzati perché la replica iniziale è incompleta.</span><span class="sxs-lookup"><span data-stu-id="79ea5-104">When running the **Move-CsLegacyUser** cmdlet, you may experience a failure due to user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases being out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="79ea5-105">Il tempo necessario per il corretto completamento della sincronizzazione iniziale del servizio Lync Server 2013 User Replicator dipende dal numero di controller di dominio ospitati nella foresta di Active Directory che ospita il pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79ea5-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="79ea5-106">Il processo di sincronizzazione iniziale di Lync Server 2013 User Replicator viene eseguito quando il server Lync Server 2013 front end è stato avviato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="79ea5-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="79ea5-107">Successivamente la sincronizzazione viene basata sull'intervallo di User Replicator.</span><span class="sxs-lookup"><span data-stu-id="79ea5-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="79ea5-108">Eseguire la procedura seguente per verificare che la replica degli utenti sia completata prima di eseguire il cmdlet **Move-CsLegacyUser**.</span><span class="sxs-lookup"><span data-stu-id="79ea5-108">Complete the following steps to verify user replication has completed before running the **Move-CsLegacyUser** cmdlet.</span></span>

<div>

## <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="79ea5-109">Per verificare che la replica degli utenti sia stata completata</span><span class="sxs-lookup"><span data-stu-id="79ea5-109">To verify that user replication has completed</span></span>

1.  <span data-ttu-id="79ea5-110">Dal front end server Lync Server 2013 fare clic sul pulsante **Start** e quindi su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="79ea5-110">From the Lync Server 2013 Front End server, click the **Start** menu, and then click **Run**.</span></span>

2.  <span data-ttu-id="79ea5-111">Digitare **eventvwr.exe** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="79ea5-111">Enter **eventvwr.exe** and then click **OK**.</span></span>

3.  <span data-ttu-id="79ea5-112">Nel Visualizzatore eventi fare clic su **Registri applicazioni e servizi** per espanderlo, quindi selezionare Lync Server</span><span class="sxs-lookup"><span data-stu-id="79ea5-112">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

4.  <span data-ttu-id="79ea5-113">Nel riquadro **Azioni** fare clic su **Filtro registro corrente**.</span><span class="sxs-lookup"><span data-stu-id="79ea5-113">In the **Actions** pane click **Filter Current Log**.</span></span>

5.  <span data-ttu-id="79ea5-114">Nell'elenco **Origini eventi** fare clic su **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="79ea5-114">From the **Event sources** list, click **LS User Replicator**.</span></span>

6.  <span data-ttu-id="79ea5-115">In **\<All Event IDs\>** immettere **30024** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="79ea5-115">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

7.  <span data-ttu-id="79ea5-116">Nella scheda **Generale** dell'elenco degli eventi filtrati cercare una voce in cui viene indicato che la replica utente è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="79ea5-116">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

