---
title: "Lync Server 2013: installazione dell'archivio di configurazione locale"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 478f45ff682b399f911b41d11a16c802181d14ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a><span data-ttu-id="2f152-102">Installare l'archivio di configurazione locale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f152-102">Install the Local Configuration store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f152-103">_**Ultimo argomento modificato:** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="2f152-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="2f152-104">Prima di eseguire la procedura seguente, verificare di aver eseguito l'accesso al server con un account utente di dominio che sia un amministratore locale e un membro del gruppo RTCUniversalReadOnlyAdmin.</span><span class="sxs-lookup"><span data-stu-id="2f152-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmin group.</span></span>

<span data-ttu-id="2f152-105">Per poter eseguire qualsiasi operazione con la distribuzione guidata di Lync Server, è necessario che l'archivio di configurazione locale esista su un server.</span><span class="sxs-lookup"><span data-stu-id="2f152-105">To be able to do anything with the Lync Server Deployment Wizard, we need the Local Configuration store to exist on a server.</span></span> <span data-ttu-id="2f152-106">L'archivio di configurazione locale è una copia di sola lettura dell'archivio di gestione centrale, che viene creato dopo l'installazione locale di SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="2f152-106">The Local Configuration store is a read-only copy of the Central Management store, which gets created after the local installation of SQL Server Express.</span></span> <span data-ttu-id="2f152-107">L'archivio di gestione centrale viene aggiunto al database di SQL Server esistente installato nel server Standard Edition o nel database basato su SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="2f152-107">The Central Management store itself is added to the existing SQL Server database installed on the Standard Edition server or SQL Server Express-based database.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2f152-108">Se non è stato eseguito il programma di installazione di Lync Server 2013 su questo server, verrà richiesto di eseguire un'unità e un percorso in cui installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2f152-108">If you haven’t run Lync Server 2013 setup on this server before, you’ll be prompted for a drive and path to install Lync Server 2013 to.</span></span> <span data-ttu-id="2f152-109">In questo modo è possibile eseguire l'installazione in un'unità diversa dall'unità di sistema, se l'organizzazione lo richiede o se si dispone di problemi di spazio.</span><span class="sxs-lookup"><span data-stu-id="2f152-109">This will let you install to a drive other than the system drive, if your organization requires it, or if you have space concerns.</span></span> <span data-ttu-id="2f152-110">È possibile modificare il percorso di installazione dei file di Lync Server nella finestra di dialogo Imposta su una nuova unità disponibile.</span><span class="sxs-lookup"><span data-stu-id="2f152-110">You can just change the installation location path for the Lync Server files in the Setup dialog box to a new, available drive.</span></span> <span data-ttu-id="2f152-111">Se si installano i file di installazione in questo percorso, incluso OCSCore. msi, verranno distribuiti anche gli altri file di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2f152-111">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will deploy there as well.</span></span>



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a><span data-ttu-id="2f152-112">Per installare l'archivio di configurazione locale</span><span class="sxs-lookup"><span data-stu-id="2f152-112">To install the Local Configuration store</span></span>

1.  <span data-ttu-id="2f152-113">Dal supporto di installazione, passare a \\installazione\\amd64\\Setup. exe e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f152-113">From your installation media, browse to \\setup\\amd64\\Setup.exe, and then click **OK**.</span></span>

2.  <span data-ttu-id="2f152-114">Se viene richiesto di installare Microsoft Visual C++ 2012 Redistributable, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="2f152-114">If you’re prompted to install the Microsoft Visual C++ 2012 Redistributable, click **Yes**.</span></span>

3.  <span data-ttu-id="2f152-115">Nella pagina **percorso di installazione di Lync Server 2013** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f152-115">On the **Lync Server 2013 Installation Location** page, click **OK**.</span></span>

4.  <span data-ttu-id="2f152-116">Nella pagina **contratto di licenza con l'utente finale** , esaminare le condizioni di licenza, è necessario selezionare **Accetto i termini del contratto di licenza**e quindi fare clic su **OK** per continuare.</span><span class="sxs-lookup"><span data-stu-id="2f152-116">On the **End User License Agreement** page, review the license terms, you’ll need to select **I accept the terms in the license agreement**, and then click **OK** to be able to continue.</span></span>

5.  <span data-ttu-id="2f152-117">Nella pagina Distribuzione guidata fare clic su **Installa o aggiorna il sistema Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2f152-117">On the Deployment Wizard page, click **Install or Update Lync Server System**.</span></span>

6.  <span data-ttu-id="2f152-118">Nella pagina **Lync Server 2013** , accanto a **passaggio 1: installazione dell'archivio di configurazione locale**, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="2f152-118">On the **Lync Server 2013** page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

7.  <span data-ttu-id="2f152-119">Nella pagina **installazione dell'archivio di configurazione locale** verificare che l'opzione **Recupera direttamente dall'archivio di gestione centrale** sia selezionata e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2f152-119">On the **Install Local Configuration Store** page, make sure that the **Retrieve directly from the Central Management store** option is selected, and then click **Next**.</span></span>

8.  <span data-ttu-id="2f152-120">Al termine dell'installazione di configurazione del server locale, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="2f152-120">When the local server configuration installation is complete, you should click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

