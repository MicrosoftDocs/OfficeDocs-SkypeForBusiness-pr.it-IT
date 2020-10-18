---
title: 'Lync Server 2013: installare il database del server Standard Edition'
description: 'Lync Server 2013: installare il database del server Standard Edition.'
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
ms.openlocfilehash: 0a20d2c01de94ad88960555db78c57c6b79d92f7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574082"
---
# <a name="install-standard-edition-server-database-for-lync-server-2013"></a><span data-ttu-id="f288b-103">Installare il database del server Standard Edition per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f288b-103">Install Standard Edition server database for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f288b-104">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f288b-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f288b-105">Configurazione di un server Standard Edition come unico server dell'infrastruttura che gli utenti di case differiscono da altre installazioni del server, in quanto è presente una selezione nella **distribuzione guidata** specificatamente per la configurazione del server iniziale.</span><span class="sxs-lookup"><span data-stu-id="f288b-105">Setting up a Standard Edition server as the only server in your infrastructure that homes users differs from other server installations in that there is a selection in the **Deployment Wizard** specifically for setting up the initial server.</span></span>

<div>

## <a name="to-install-a-standard-edition-server"></a><span data-ttu-id="f288b-106">Per installare un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f288b-106">To install a Standard Edition server</span></span>

1.  <span data-ttu-id="f288b-107">Accedere al server in cui si intende installare il server Standard Edition come amministratore locale o come equivalente di dominio.</span><span class="sxs-lookup"><span data-stu-id="f288b-107">Log on to the server where you are going to install Standard Edition server as a local administrator or a domain equivalent.</span></span>

2.  <span data-ttu-id="f288b-108">Se non è stato preparato Servizi di dominio Active Directory, eseguire prima queste procedure.</span><span class="sxs-lookup"><span data-stu-id="f288b-108">If you have not prepared Active Directory Domain Services, then first perform those procedures.</span></span> <span data-ttu-id="f288b-109">Per ulteriori informazioni, vedere [preparazione di servizi di dominio Active Directory per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="f288b-109">For details, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

3.  <span data-ttu-id="f288b-110">Nella distribuzione guidata di Lync Server, fare clic su **prepara primo server Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="f288b-110">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="f288b-111">Nella pagina **Prepara singolo Server Standard** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f288b-111">On the **Prepare single Standard Edition Server** page, click **Next**.</span></span>

5.  <span data-ttu-id="f288b-112">Nella pagina **esecuzione comandi** in corso viene installato SQL Server 2012 Express come archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="f288b-112">On the **Executing Commands** page, the SQL Server 2012 Express is installed as the Central Management store.</span></span> <span data-ttu-id="f288b-113">Vengono create le regole firewall necessarie.</span><span class="sxs-lookup"><span data-stu-id="f288b-113">Necessary firewall rules are created.</span></span> <span data-ttu-id="f288b-114">Al termine dell'installazione del database e dei prerequisiti software, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="f288b-114">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f288b-115">L'installazione iniziale può richiedere tempo senza che vengano visualizzati aggiornamenti visibili nella schermata riepilogativa di output dei comandi.</span><span class="sxs-lookup"><span data-stu-id="f288b-115">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="f288b-116">Ciò è dovuto all'installazione di SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="f288b-116">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="f288b-117">Se si desidera monitorare l'installazione del database, usare Gestione attività.</span><span class="sxs-lookup"><span data-stu-id="f288b-117">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

6.  <span data-ttu-id="f288b-118">Nella pagina distribuzione guidata di Lync Server, fare clic su **installa Generatore di topologie** se non sono stati precedentemente installati gli strumenti di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="f288b-118">On the Lync Server Deployment Wizard page, click **Install Topology Builder** if you have not previously installed the administrative tools.</span></span> <span data-ttu-id="f288b-119">Per informazioni dettagliate, vedere [Install Lync Server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f288b-119">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

7.  <span data-ttu-id="f288b-120">Verificare che accanto a "Prepara Active Directory", "Prepara primo Server Standard" e "Installa Generatore di topologie" siano visualizzati segni di spunta di colore verde.</span><span class="sxs-lookup"><span data-stu-id="f288b-120">Confirm that there are green check marks next to “Prepare Active Directory,” “Prepare first Standard Edition server,” and “Install Topology Builder.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

