---
title: 'Lync Server 2013: pubblicazione della topologia aggiornata per aggiungere database di archiviazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f5d6e409682aaafd6e48966fa47797b870f90b0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a><span data-ttu-id="cdd0e-102">Pubblicazione della topologia aggiornata per l'aggiunta dei database di archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdd0e-102">Publishing the updated topology to add Archiving databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdd0e-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="cdd0e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="cdd0e-104">Dopo aver aggiornato la topologia in Generatore di topologie, è necessario pubblicare la topologia nell'archivio di gestione centrale prima di poter configurare e utilizzare l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="cdd0e-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Archiving.</span></span> <span data-ttu-id="cdd0e-105">In tutti i server della topologia vengono replicate copie di sola lettura dei dati in modo che siano sincronizzati con la topologia e altre modifiche della configurazione.</span><span class="sxs-lookup"><span data-stu-id="cdd0e-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-your-updated-topology"></a><span data-ttu-id="cdd0e-106">Per pubblicare una topologia aggiornata</span><span class="sxs-lookup"><span data-stu-id="cdd0e-106">To publish your updated topology</span></span>

1.  <span data-ttu-id="cdd0e-107">In un computer in cui è in esecuzione Lync Server 2013 o in cui sono installati gli strumenti di amministrazione di Lync Server, eseguire l'accesso utilizzando un account membro del gruppo utenti locali (o un account con diritti utente equivalenti).</span><span class="sxs-lookup"><span data-stu-id="cdd0e-107">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cdd0e-108">È possibile definire una topologia utilizzando un account membro del gruppo Users locale, ma per pubblicare una topologia, necessaria per aggiungere un server alla topologia. è necessario utilizzare un account che sia membro del gruppo <STRONG>Domain Admins</STRONG> e del gruppo <STRONG>RTCUniversalServerAdmins</STRONG> e che disponga di autorizzazioni di controllo completo (ovvero lettura, scrittura e modifica) sulla condivisione file utilizzata per l'archivio file di Lync Server 2013 (ovvero, in modo che generatore di topologie possa configurare l'elenco di controllo di accesso discrezionale necessario (DACL) o un account con diritti equivalenti.</span><span class="sxs-lookup"><span data-stu-id="cdd0e-108">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="cdd0e-109">Aprire la topologia creata nella sezione precedente utilizzando Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="cdd0e-109">Open the topology you created in the previous section using Topology Builder.</span></span>

3.  <span data-ttu-id="cdd0e-110">Nell'albero della console fare clic con il pulsante destro del mouse su **Lync Server 2013**e quindi scegliere **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="cdd0e-110">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="cdd0e-111">Nella pagina **Pubblicare la topologia** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cdd0e-111">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="cdd0e-112">Nella pagina **Crea altri database** verificare che il database sia selezionato e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cdd0e-112">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cdd0e-113">Se non si dispone delle autorizzazioni appropriate per la creazione di database, è possibile annullare la selezione del database e un utente con le autorizzazioni appropriate può creare il database.</span><span class="sxs-lookup"><span data-stu-id="cdd0e-113">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="cdd0e-114">Per informazioni dettagliate sulle autorizzazioni e i diritti di amministratore necessari, vedere <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in Lync server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cdd0e-114">For details about the required administrator rights and permissions, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="cdd0e-115">Solo i database su server SQL Server dedicati possono essere installati tramite Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="cdd0e-115">Only databases on dedicated SQL Server servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="cdd0e-116">I database nei server SQL Server collocati con altri componenti server devono essere installati eseguendo l'installazione locale in tale computer.</span><span class="sxs-lookup"><span data-stu-id="cdd0e-116">Databases on SQL Server servers that are collocated with other server components must be installed by running local setup on that computer.</span></span>

    
    </div>

6.  <span data-ttu-id="cdd0e-117">Nella pagina **Pubblicazione guidata completata** verificare che la topologia sia stata pubblicata correttamente e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="cdd0e-117">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cdd0e-118">Dopo aver pubblicato la topologia, è necessario configurare le opzioni e i criteri per l'archiviazione, prima che sia possibile archiviare qualsiasi contenuto.</span><span class="sxs-lookup"><span data-stu-id="cdd0e-118">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="cdd0e-119">Per informazioni dettagliate, vedere <A href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for archiving in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cdd0e-119">For details, see <A href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

