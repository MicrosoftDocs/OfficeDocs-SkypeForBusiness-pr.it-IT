---
title: 'Lync Server 2013: installazione di SQL Server Reporting Services'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0448802e7de2c00b5c57730c5e95fb99b21b237e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a><span data-ttu-id="5ace8-102">Installazione di SQL Server Reporting Services in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ace8-102">Installing SQL Server Reporting Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ace8-103">_**Ultimo argomento modificato:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="5ace8-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="5ace8-104">Se si intende utilizzare i rapporti di monitoraggio di Microsoft Lync Server 2013 (vedere la sezione successiva di questa documentazione per ulteriori informazioni), è necessario prima installare SQL Server Reporting Services. È possibile installare Reporting Services nello stesso momento in cui si installa Microsoft SQL Server o in qualsiasi momento dopo l'installazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5ace8-104">If you intend to use Microsoft Lync Server 2013 Monitoring Reports (see the next section of this documentation for more information) you must first install SQL Server Reporting Services; Reporting Services can be installed at the same time you install Microsoft SQL Server or any time after SQL Server has been installed.</span></span> <span data-ttu-id="5ace8-105">Se SQL Server non è ancora stato installato, seguire le istruzioni fornite in precedenza in questa documentazione.</span><span class="sxs-lookup"><span data-stu-id="5ace8-105">If you have not installed SQL Server, then follow the instructions provided earlier in this documentation.</span></span> <span data-ttu-id="5ace8-106">Durante l'installazione di SQL Server assicurarsi di selezionare Reporting Services nella pagina Selezione funzionalità.</span><span class="sxs-lookup"><span data-stu-id="5ace8-106">When installing SQL Server, make sure that, on the Feature Selection page, you select Reporting Services.</span></span> <span data-ttu-id="5ace8-107">Verrà così installato SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="5ace8-107">That will install SQL Server Reporting Services.</span></span>

<span data-ttu-id="5ace8-108">Se SQL Server è già stato installato, ma SQL Server Reporting Services non è stato incluso nell'installazione, è possibile aggiungere questa funzionalità attenendosi alle istruzioni appropriate per SQL Server 2008 R2 o SQL Server 2012, a seconda della versione in uso.</span><span class="sxs-lookup"><span data-stu-id="5ace8-108">If you have already installed SQL Server but did not install SQL Server Reporting Services you can add that feature by following the appropriate set of instructions for SQL Server 2008 R2 or SQL Server 2012, as appropriate.</span></span>

<span data-ttu-id="5ace8-109">Per verificare che Reporting Services sia stato installato correttamente, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ace8-109">To verify that the reporting Services have been successfully installed, complete the following steps:</span></span>

1.  <span data-ttu-id="5ace8-110">Se si esegue Microsoft SQL Server 2008 R2, fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft SQL Server 2008 R2**, **Strumenti di configurazione** e quindi fare clic su **Gestione configurazione Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="5ace8-110">If you are running Microsoft SQL Server 2008 R2, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>
    
    <span data-ttu-id="5ace8-111">Se si esegue Microsoft SQL Server 2012, fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft SQL Server 2012**, **Strumenti di configurazione** e quindi fare clic su **Gestione configurazione Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="5ace8-111">If you are running Microsoft SQL Server 2012, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2012**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="5ace8-p102">Nella finestra di dialogo **Connessione configurazione Reporting Services** verificare che il nome del server sia visualizzato nella casella **Nome server** e che il nome dell'istanza di SQL Server in cui sono archiviati i dati di monitoraggio sia visualizzato nella casella **Istanza server di report**. Fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="5ace8-p102">In the **Reporting Services Configuration Connection** dialog box, verify that the name of your server appears in the **Server Name** box and that the name of the SQL Server instance that stores your monitoring data appears in the **Report Server Instance** box. Click **Connect**.</span></span>

<span data-ttu-id="5ace8-114">In Gestione configurazione Reporting Services il riquadro di stato del server di report deve mostrare che è stato installato SQL Server Reporting Service e che i servizi di Reporting sono in esecuzione: lo stato del server di report deve essere visualizzato come **avviato** e il pulsante **Start** deve essere disattivato e non disponibile.</span><span class="sxs-lookup"><span data-stu-id="5ace8-114">In the Reporting Service Configuration Manager, the Report Server Status pane should show that SQL Server Reporting Services has been installed and that the Reporting Services are currently running: the Report Server Status should be shown as **Started** and the **Start** button should be grayed-out and unavailable.</span></span> <span data-ttu-id="5ace8-115">Se Reporting Services risulta non in esecuzione, fare clic su**Avvia** per avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="5ace8-115">If the Reporting Service is not running, click **Start** in order to start the service.</span></span>

<span data-ttu-id="5ace8-116">Se accanto all'etichetta Nome database server di report non è elencato alcun database, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ace8-116">If no database is listed next to the Report Server Database Name label then do the following:</span></span>

1.  <span data-ttu-id="5ace8-117">In Gestione configurazione Reporting Services fare clic su **Database**.</span><span class="sxs-lookup"><span data-stu-id="5ace8-117">In the Reporting Services Configuration Manager click **Database**.</span></span>

2.  <span data-ttu-id="5ace8-118">Nel riquadro Database server di report fare clic su **Modifica database**.</span><span class="sxs-lookup"><span data-stu-id="5ace8-118">In the Report Server Database pane click **Change Database**.</span></span>

3.  <span data-ttu-id="5ace8-119">Nella Configurazione guidata database del server di report	selezionare **Crea un nuovo database del server di report** nel riquadro Azione e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5ace8-119">In the Report Server Database Configuration wizard, in the Action pane, select **Create a new report server database** and then click **Next**.</span></span>

4.  <span data-ttu-id="5ace8-p104">Nel riquadro Server di database della Configurazione guidata database del server di report verificare che le informazioni elencate nelle caselle **Nome server**, **Tipo di autenticazione** e **Nome utente** siano corrette. Fare clic su **Test connessione** per verificare che sia possibile attivare una connessione al server di database e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5ace8-p104">In the Report Server Database Configuration wizard, in the Database Server pane, verify that the information listed in the **Server Name**, **Authentication Type**, and **Username** boxes is correct. Click **Test Connection** to verify that a connection can be made to the database server and then click **Next**.</span></span>

5.  <span data-ttu-id="5ace8-122">Nel riquadro Database della Configurazione guidata database del server di report accettare i valori predefiniti per **Nome database**, **Lingua** e **Modalità server di report**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5ace8-122">In the Report Server Database Configuration wizard, in the Database pane, accept the default values for **Database Name**, **Language**, and **Report Server Mode** and then click **Next**.</span></span>

6.  <span data-ttu-id="5ace8-123">Nel riquadro Credenziali della Configurazione guidata database del server di report verificare che siano elencate le informazioni corrette nell'elenco a discesa **Tipo di autenticazione** e nelle caselle **Nome utente** e **Password**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5ace8-123">In the Report Server Database Configuration wizard, in the Credentials pane, verify that the correct information is listed in the **Authentication Type** dropdown list and the **User name** and **Password** boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="5ace8-124">Nel riquadro Riepilogo della Configurazione guidata database del server di report fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5ace8-124">In the Report Server Database Configuration wizard, in the Summary pane, click **Next**.</span></span>

8.  <span data-ttu-id="5ace8-125">Nel riquadro Continua e termina della Configurazione guidata database del server di report	 fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="5ace8-125">In the Report Server Database Configuration wizard, in the Progress and Finish pane, click **Finish**.</span></span>

<span data-ttu-id="5ace8-p105">Per verificare che siano stati configurati gli URL di Reporting Services, fare clic su **URL servizio Web**. Verranno visualizzati uno o più URL sotto il titolo **URL servizio Web ReportServer**. Fare clic su ognuno di questi URL per verificare che sia possibile raggiungere la home page per l'installazione locale di SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="5ace8-p105">To verify that the Reporting Service URLs have been configured, click **Web Service URL**. You should see one or more URLs listed under the heading **Report Server Web Service URLs**. Click each of these URLs to verify that you can reach the home page for the local installation of SQL Server Reporting Services.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

