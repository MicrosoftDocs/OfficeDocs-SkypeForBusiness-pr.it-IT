---
title: Verificare che la replica degli utenti sia stata completata
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc736894acccabb587d5f4afd2fa47edff1b5e25
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="e7f24-102">Verificare che la replica degli utenti sia stata completata</span><span class="sxs-lookup"><span data-stu-id="e7f24-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7f24-103">_**Ultimo argomento modificato:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="e7f24-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="e7f24-104">Quando si esegue il cmdlet **Move-CsUser** , è possibile che si verifichi un errore perché le informazioni degli utenti tra servizi di dominio Active Directory e i database di Lync Server 2013 non sono sincronizzate perché la replica iniziale è incompleta.</span><span class="sxs-lookup"><span data-stu-id="e7f24-104">When running the **Move-CsUser** cmdlet, you may experience a failure because user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="e7f24-105">Il tempo necessario per il corretto completamento della sincronizzazione iniziale del servizio Lync Server 2013 User Replicator dipende dal numero di controller di dominio ospitati nella foresta di Active Directory che ospita il pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e7f24-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="e7f24-106">Il processo di sincronizzazione iniziale di Lync Server 2013 User Replicator viene eseguito quando il server Lync Server 2013 front end è stato avviato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="e7f24-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="e7f24-107">Successivamente la sincronizzazione viene basata sull'intervallo di User Replicator.</span><span class="sxs-lookup"><span data-stu-id="e7f24-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="e7f24-108">Eseguire la procedura seguente per verificare che la replica degli utenti sia completata prima di eseguire il cmdlet **Move-CsUser**.</span><span class="sxs-lookup"><span data-stu-id="e7f24-108">Complete the following steps to verify user replication has completed before running the **Move-CsUser** cmdlet.</span></span>

<div>

## <a name="to-verify-user-replication-has-completed"></a><span data-ttu-id="e7f24-109">Per verificare che la replica degli utenti sia stata completata</span><span class="sxs-lookup"><span data-stu-id="e7f24-109">To verify user replication has completed</span></span>

1.  <span data-ttu-id="e7f24-110">Accedere al computer in cui è installato il Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e7f24-110">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="e7f24-111">Fare clic su **Start** e scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="e7f24-111">Click the **Start** menu, and then click **Run**.</span></span>

3.  <span data-ttu-id="e7f24-112">Digitare **eventvwr.exe** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7f24-112">Enter **eventvwr.exe** and then click **OK**.</span></span>

4.  <span data-ttu-id="e7f24-113">Nel Visualizzatore eventi fare clic su **Registri applicazioni e servizi** per espanderlo, quindi selezionare Lync Server</span><span class="sxs-lookup"><span data-stu-id="e7f24-113">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

5.  <span data-ttu-id="e7f24-114">Nel riquadro **Azioni** fare clic su **Filtro registro corrente**.</span><span class="sxs-lookup"><span data-stu-id="e7f24-114">In the **Actions** pane click **Filter Current Log**.</span></span>

6.  <span data-ttu-id="e7f24-115">Nell'elenco **Origini eventi** fare clic su **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="e7f24-115">From the **Event sources** list, click **LS User Replicator**.</span></span>

7.  <span data-ttu-id="e7f24-116">In \*\* \<tutti gli ID\> evento\*\* immettere **30024** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7f24-116">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

8.  <span data-ttu-id="e7f24-117">Nella scheda **Generale** dell'elenco degli eventi filtrati cercare una voce in cui viene indicato che la replica utente è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="e7f24-117">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

