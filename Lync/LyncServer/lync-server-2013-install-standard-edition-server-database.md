---
title: 'Lync Server 2013: Installare il database del server Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cad6f67dbf1bfff1ee16dbd7455b02d904aac0d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a><span data-ttu-id="848d4-102">Installare il database del server Standard Edition per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="848d4-102">Install Standard Edition server database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="848d4-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="848d4-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="848d4-104">Configurazione di un server Standard Edition come unico server nell'infrastruttura in cui gli utenti di case si differenziano da altre installazioni del server, in quanto esiste una selezione nella **distribuzione guidata** in modo specifico per la configurazione del server iniziale.</span><span class="sxs-lookup"><span data-stu-id="848d4-104">Setting up a Standard Edition server as the only server in your infrastructure that homes users differs from other server installations in that there is a selection in the **Deployment Wizard** specifically for setting up the initial server.</span></span>

<div>

## <a name="to-install-a-standard-edition-server"></a><span data-ttu-id="848d4-105">Per installare un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="848d4-105">To install a Standard Edition server</span></span>

1.  <span data-ttu-id="848d4-106">Accedere al server in cui si vuole installare il server Standard Edition come amministratore locale o come equivalente di dominio.</span><span class="sxs-lookup"><span data-stu-id="848d4-106">Log on to the server where you are going to install Standard Edition server as a local administrator or a domain equivalent.</span></span>

2.  <span data-ttu-id="848d4-107">Se non sono stati preparati servizi di dominio Active Directory, eseguire prima di tutto queste procedure.</span><span class="sxs-lookup"><span data-stu-id="848d4-107">If you have not prepared Active Directory Domain Services, then first perform those procedures.</span></span> <span data-ttu-id="848d4-108">Per informazioni dettagliate, vedere [preparazione di servizi di dominio Active Directory per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="848d4-108">For details, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

3.  <span data-ttu-id="848d4-109">Nella distribuzione guidata di Lync Server fare clic su **prepara primo server Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="848d4-109">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="848d4-110">Nella pagina **prepara Single Standard Edition server** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="848d4-110">On the **Prepare single Standard Edition Server** page, click **Next**.</span></span>

5.  <span data-ttu-id="848d4-111">Nella pagina **esecuzione dei comandi** , SQL Server 2012 Express viene installato come Central Management store.</span><span class="sxs-lookup"><span data-stu-id="848d4-111">On the **Executing Commands** page, the SQL Server 2012 Express is installed as the Central Management store.</span></span> <span data-ttu-id="848d4-112">Vengono create le regole firewall necessarie.</span><span class="sxs-lookup"><span data-stu-id="848d4-112">Necessary firewall rules are created.</span></span> <span data-ttu-id="848d4-113">Dopo aver completato l'installazione del database e del software prerequisito, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="848d4-113">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="848d4-114">L'installazione iniziale può richiedere del tempo senza aggiornamenti visibili alla schermata di riepilogo dell'output del comando.</span><span class="sxs-lookup"><span data-stu-id="848d4-114">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="848d4-115">Ciò è dovuto all'installazione di SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="848d4-115">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="848d4-116">Se è necessario monitorare l'installazione del database, usare Gestione attività per monitorare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="848d4-116">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

6.  <span data-ttu-id="848d4-117">Nella pagina distribuzione guidata di Lync Server fare clic su **installa Generatore di topologie** se non sono stati installati in precedenza gli strumenti di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="848d4-117">On the Lync Server Deployment Wizard page, click **Install Topology Builder** if you have not previously installed the administrative tools.</span></span> <span data-ttu-id="848d4-118">Per informazioni dettagliate, vedere [installare gli strumenti di amministrazione di Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="848d4-118">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

7.  <span data-ttu-id="848d4-119">Verificare che siano presenti segni di spunta verdi accanto a "prepara Active Directory", "prepara First Standard Edition Server" e "Install topologia Builder".</span><span class="sxs-lookup"><span data-stu-id="848d4-119">Confirm that there are green check marks next to “Prepare Active Directory,” “Prepare first Standard Edition server,” and “Install Topology Builder.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

