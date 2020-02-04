---
title: "Lync Server 2013: Installare l'archivio di configurazione locale"
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
ms.openlocfilehash: e4af6d4b6dfe203f69a6b104b6ade636d2658178
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a><span data-ttu-id="b1578-102">Installare l'archivio di configurazione locale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1578-102">Install the Local Configuration store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1578-103">_**Argomento Ultima modifica:** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="b1578-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="b1578-104">Prima di eseguire questa procedura, verificare di aver effettuato l'accesso al server con un account utente di dominio che sia un amministratore locale e un membro del gruppo RTCUniversalReadOnlyAdmin.</span><span class="sxs-lookup"><span data-stu-id="b1578-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmin group.</span></span>

<span data-ttu-id="b1578-105">Per poter eseguire qualsiasi operazione con la distribuzione guidata di Lync Server, è necessario che l'archivio di configurazione locale sia presente in un server.</span><span class="sxs-lookup"><span data-stu-id="b1578-105">To be able to do anything with the Lync Server Deployment Wizard, we need the Local Configuration store to exist on a server.</span></span> <span data-ttu-id="b1578-106">L'archivio di configurazione locale è una copia di sola lettura di Central Management store, che viene creata dopo l'installazione locale di SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="b1578-106">The Local Configuration store is a read-only copy of the Central Management store, which gets created after the local installation of SQL Server Express.</span></span> <span data-ttu-id="b1578-107">L'archivio di gestione centralizzato viene aggiunto al database di SQL Server esistente installato nel server Standard Edition o nel database basato su SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="b1578-107">The Central Management store itself is added to the existing SQL Server database installed on the Standard Edition server or SQL Server Express-based database.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b1578-108">Se non è ancora stata eseguita la configurazione di Lync Server 2013 su questo server, verrà richiesto di eseguire un'unità e un percorso in cui installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b1578-108">If you haven’t run Lync Server 2013 setup on this server before, you’ll be prompted for a drive and path to install Lync Server 2013 to.</span></span> <span data-ttu-id="b1578-109">In questo modo è possibile eseguire l'installazione in un'unità diversa dall'unità di sistema, se l'organizzazione lo richiede o se si hanno problemi di spazio.</span><span class="sxs-lookup"><span data-stu-id="b1578-109">This will let you install to a drive other than the system drive, if your organization requires it, or if you have space concerns.</span></span> <span data-ttu-id="b1578-110">È possibile modificare semplicemente il percorso di installazione per i file di Lync Server nella finestra di dialogo Imposta in una nuova unità disponibile.</span><span class="sxs-lookup"><span data-stu-id="b1578-110">You can just change the installation location path for the Lync Server files in the Setup dialog box to a new, available drive.</span></span> <span data-ttu-id="b1578-111">Se si installano i file di configurazione in questo percorso, incluso OCSCore. msi, verranno distribuiti anche il resto dei file di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b1578-111">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will deploy there as well.</span></span>



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a><span data-ttu-id="b1578-112">Per installare l'archivio di configurazione locale</span><span class="sxs-lookup"><span data-stu-id="b1578-112">To install the Local Configuration store</span></span>

1.  <span data-ttu-id="b1578-113">Dal supporto di installazione passare \\a Setup\\amd64\\Setup. exe e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1578-113">From your installation media, browse to \\setup\\amd64\\Setup.exe, and then click **OK**.</span></span>

2.  <span data-ttu-id="b1578-114">Se viene chiesto di installare Microsoft Visual C++ 2012 ridistribuibile, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="b1578-114">If you’re prompted to install the Microsoft Visual C++ 2012 Redistributable, click **Yes**.</span></span>

3.  <span data-ttu-id="b1578-115">Nella pagina **percorso di installazione di Lync Server 2013** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1578-115">On the **Lync Server 2013 Installation Location** page, click **OK**.</span></span>

4.  <span data-ttu-id="b1578-116">Nella pagina **contratto di licenza con l'utente finale** verificare le condizioni di licenza, è necessario selezionare **Accetto i termini del contratto di licenza**e quindi fare clic su **OK** per poter continuare.</span><span class="sxs-lookup"><span data-stu-id="b1578-116">On the **End User License Agreement** page, review the license terms, you’ll need to select **I accept the terms in the license agreement**, and then click **OK** to be able to continue.</span></span>

5.  <span data-ttu-id="b1578-117">Nella pagina distribuzione guidata fare clic su **Installa o aggiorna Lync Server System**.</span><span class="sxs-lookup"><span data-stu-id="b1578-117">On the Deployment Wizard page, click **Install or Update Lync Server System**.</span></span>

6.  <span data-ttu-id="b1578-118">Nella pagina **Lync Server 2013** , accanto a **Step1: install Local Configuration Store**, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="b1578-118">On the **Lync Server 2013** page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

7.  <span data-ttu-id="b1578-119">Nella pagina **Installa configurazione locale Store** verificare che sia selezionata l'opzione **Recupera direttamente dall'archivio di gestione centrale** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b1578-119">On the **Install Local Configuration Store** page, make sure that the **Retrieve directly from the Central Management store** option is selected, and then click **Next**.</span></span>

8.  <span data-ttu-id="b1578-120">Dopo aver completato l'installazione di configurazione del server locale, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="b1578-120">When the local server configuration installation is complete, you should click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

