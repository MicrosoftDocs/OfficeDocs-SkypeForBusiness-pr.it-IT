---
title: Verificare il completamento della replica utente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e96d3231fbbfe9ce9062e948e6b60de6521720e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="c2837-102">Verificare il completamento della replica utente</span><span class="sxs-lookup"><span data-stu-id="c2837-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2837-103">_**Argomento Ultima modifica:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="c2837-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="c2837-104">Quando si esegue il cmdlet **Move-CsUser** , è possibile che si verifichi un errore perché le informazioni degli utenti tra servizi di dominio Active Directory e i database di Lync Server 2013 non sono sincronizzate perché la replica iniziale è incompleta.</span><span class="sxs-lookup"><span data-stu-id="c2837-104">When running the **Move-CsUser** cmdlet, you may experience a failure because user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="c2837-105">Il tempo necessario per il completamento della sincronizzazione iniziale di Lync Server 2013, dipende dal numero di controller di dominio ospitati nella foresta di Active Directory che ospita il pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c2837-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="c2837-106">Il processo di sincronizzazione iniziale di Lync Server 2013 User Replicator Service viene eseguito quando il server front-end di Lync Server 2013 viene avviato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="c2837-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="c2837-107">Successivamente, la sincronizzazione si basa sull'intervallo User Replicator.</span><span class="sxs-lookup"><span data-stu-id="c2837-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="c2837-108">Completare la procedura seguente per verificare che la replica degli utenti sia stata completata prima di eseguire il cmdlet **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="c2837-108">Complete the following steps to verify user replication has completed before running the **Move-CsUser** cmdlet.</span></span>

<div>

## <a name="to-verify-user-replication-has-completed"></a><span data-ttu-id="c2837-109">Per verificare che la replica degli utenti sia stata completata</span><span class="sxs-lookup"><span data-stu-id="c2837-109">To verify user replication has completed</span></span>

1.  <span data-ttu-id="c2837-110">Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c2837-110">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="c2837-111">Fare clic sul menu **Start** e quindi su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c2837-111">Click the **Start** menu, and then click **Run**.</span></span>

3.  <span data-ttu-id="c2837-112">Immettere **eventvwr. exe** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2837-112">Enter **eventvwr.exe** and then click **OK**.</span></span>

4.  <span data-ttu-id="c2837-113">Nel Visualizzatore eventi fare clic su **registri applicazioni e servizi** per espanderlo e quindi selezionare Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c2837-113">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

5.  <span data-ttu-id="c2837-114">Nel riquadro **azioni** fare clic su **Filtra log corrente**.</span><span class="sxs-lookup"><span data-stu-id="c2837-114">In the **Actions** pane click **Filter Current Log**.</span></span>

6.  <span data-ttu-id="c2837-115">Nell'elenco **origini eventi** fare clic su **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="c2837-115">From the **Event sources** list, click **LS User Replicator**.</span></span>

7.  <span data-ttu-id="c2837-116">In \*\* \<tutti gli ID\> evento\*\* immettere **30024** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2837-116">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

8.  <span data-ttu-id="c2837-117">Nell'elenco eventi filtrati, nella scheda **generale** , cercare una voce che indica che la replica degli utenti è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="c2837-117">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

