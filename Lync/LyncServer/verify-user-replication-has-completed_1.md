---
title: Verificare il completamento della replica utente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13f4fbd2e0d0236f9dc404ffa84ab2f0ce385e2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="1c4c4-102">Verificare il completamento della replica utente</span><span class="sxs-lookup"><span data-stu-id="1c4c4-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c4c4-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1c4c4-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1c4c4-104">Quando si utilizza il cmdlet **Move-CsLegacyUser** , potrebbe verificarsi un errore a causa di informazioni utente tra servizi di dominio Active Directory e i database di Lync Server 2013 non sincronizzati perché la replica iniziale è incompleta.</span><span class="sxs-lookup"><span data-stu-id="1c4c4-104">When running the **Move-CsLegacyUser** cmdlet, you may experience a failure due to user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases being out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="1c4c4-105">Il tempo necessario per il completamento della sincronizzazione iniziale di Lync Server 2013, dipende dal numero di controller di dominio ospitati nella foresta di Active Directory che ospita il pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1c4c4-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="1c4c4-106">Il processo di sincronizzazione iniziale di Lync Server 2013 User Replicator Service viene eseguito quando il server front-end di Lync Server 2013 viene avviato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="1c4c4-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="1c4c4-107">Successivamente, la sincronizzazione si basa sull'intervallo User Replicator.</span><span class="sxs-lookup"><span data-stu-id="1c4c4-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="1c4c4-108">Completare la procedura seguente per verificare che la replica degli utenti sia stata completata prima di eseguire il cmdlet **Move-CsLegacyUser** .</span><span class="sxs-lookup"><span data-stu-id="1c4c4-108">Complete the following steps to verify user replication has completed before running the **Move-CsLegacyUser** cmdlet.</span></span>

<div>

## <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="1c4c4-109">Per verificare che la replica dell'utente sia stata completata</span><span class="sxs-lookup"><span data-stu-id="1c4c4-109">To verify that user replication has completed</span></span>

1.  <span data-ttu-id="1c4c4-110">Dal server front-end di Lync Server 2013 fare clic sul menu **Start** e quindi su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="1c4c4-110">From the Lync Server 2013 Front End server, click the **Start** menu, and then click **Run**.</span></span>

2.  <span data-ttu-id="1c4c4-111">Immettere **eventvwr. exe** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c4c4-111">Enter **eventvwr.exe** and then click **OK**.</span></span>

3.  <span data-ttu-id="1c4c4-112">Nel Visualizzatore eventi fare clic su **registri applicazioni e servizi** per espanderlo e quindi selezionare Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1c4c4-112">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

4.  <span data-ttu-id="1c4c4-113">Nel riquadro **azioni** fare clic su **Filtra log corrente**.</span><span class="sxs-lookup"><span data-stu-id="1c4c4-113">In the **Actions** pane click **Filter Current Log**.</span></span>

5.  <span data-ttu-id="1c4c4-114">Nell'elenco **origini eventi** fare clic su **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="1c4c4-114">From the **Event sources** list, click **LS User Replicator**.</span></span>

6.  <span data-ttu-id="1c4c4-115">In \*\* \<tutti gli ID\> evento\*\* immettere **30024** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c4c4-115">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

7.  <span data-ttu-id="1c4c4-116">Nell'elenco eventi filtrati, nella scheda **generale** , cercare una voce che indica che la replica degli utenti è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="1c4c4-116">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

