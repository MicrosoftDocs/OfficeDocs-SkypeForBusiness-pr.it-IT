---
title: 'Lync Server 2013: installare il database del server Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 877a9b8519c6c0e8b0c3e4a92d190f5a55d8861e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a><span data-ttu-id="c26db-102">Installare il database del server Standard Edition per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c26db-102">Install Standard Edition server database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c26db-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c26db-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c26db-104">Configurazione di un server Standard Edition come unico server dell'infrastruttura che gli utenti di case differiscono da altre installazioni del server, in quanto è presente una selezione nella **distribuzione guidata** specificatamente per la configurazione del server iniziale.</span><span class="sxs-lookup"><span data-stu-id="c26db-104">Setting up a Standard Edition server as the only server in your infrastructure that homes users differs from other server installations in that there is a selection in the **Deployment Wizard** specifically for setting up the initial server.</span></span>

<div>

## <a name="to-install-a-standard-edition-server"></a><span data-ttu-id="c26db-105">Per installare un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="c26db-105">To install a Standard Edition server</span></span>

1.  <span data-ttu-id="c26db-106">Accedere al server in cui si intende installare il server Standard Edition come amministratore locale o come equivalente di dominio.</span><span class="sxs-lookup"><span data-stu-id="c26db-106">Log on to the server where you are going to install Standard Edition server as a local administrator or a domain equivalent.</span></span>

2.  <span data-ttu-id="c26db-107">Se non è stato preparato Servizi di dominio Active Directory, eseguire prima queste procedure.</span><span class="sxs-lookup"><span data-stu-id="c26db-107">If you have not prepared Active Directory Domain Services, then first perform those procedures.</span></span> <span data-ttu-id="c26db-108">Per ulteriori informazioni, vedere [preparazione di servizi di dominio Active Directory per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="c26db-108">For details, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

3.  <span data-ttu-id="c26db-109">Nella distribuzione guidata di Lync Server, fare clic su **prepara primo server Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="c26db-109">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="c26db-110">Nella pagina **Prepara singolo Server Standard** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c26db-110">On the **Prepare single Standard Edition Server** page, click **Next**.</span></span>

5.  <span data-ttu-id="c26db-111">Nella pagina **esecuzione comandi** in corso viene installato SQL Server 2012 Express come archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="c26db-111">On the **Executing Commands** page, the SQL Server 2012 Express is installed as the Central Management store.</span></span> <span data-ttu-id="c26db-112">Vengono create le regole firewall necessarie.</span><span class="sxs-lookup"><span data-stu-id="c26db-112">Necessary firewall rules are created.</span></span> <span data-ttu-id="c26db-113">Al termine dell'installazione del database e dei prerequisiti software, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="c26db-113">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c26db-114">L'installazione iniziale può richiedere tempo senza che vengano visualizzati aggiornamenti visibili nella schermata riepilogativa di output dei comandi.</span><span class="sxs-lookup"><span data-stu-id="c26db-114">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="c26db-115">Ciò è dovuto all'installazione di SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="c26db-115">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="c26db-116">Se si desidera monitorare l'installazione del database, usare Gestione attività.</span><span class="sxs-lookup"><span data-stu-id="c26db-116">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

6.  <span data-ttu-id="c26db-117">Nella pagina distribuzione guidata di Lync Server, fare clic su **installa Generatore di topologie** se non sono stati precedentemente installati gli strumenti di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="c26db-117">On the Lync Server Deployment Wizard page, click **Install Topology Builder** if you have not previously installed the administrative tools.</span></span> <span data-ttu-id="c26db-118">Per informazioni dettagliate, vedere [Install Lync Server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c26db-118">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

7.  <span data-ttu-id="c26db-119">Verificare che accanto a "Prepara Active Directory", "Prepara primo Server Standard" e "Installa Generatore di topologie" siano visualizzati segni di spunta di colore verde.</span><span class="sxs-lookup"><span data-stu-id="c26db-119">Confirm that there are green check marks next to “Prepare Active Directory,” “Prepare first Standard Edition server,” and “Install Topology Builder.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

