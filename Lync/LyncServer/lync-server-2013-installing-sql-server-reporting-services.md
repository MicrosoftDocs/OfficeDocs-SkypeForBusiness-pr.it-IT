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
ms.openlocfilehash: 6342743486e3a3261e297d602ceb994d421dc13c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a><span data-ttu-id="5b5aa-102">Installazione di SQL Server Reporting Services in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b5aa-102">Installing SQL Server Reporting Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b5aa-103">_**Argomento Ultima modifica:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="5b5aa-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="5b5aa-104">Se si intende usare i report di monitoraggio di Microsoft Lync Server 2013 (vedere la sezione successiva di questa documentazione per altre informazioni), è necessario installare SQL Server Reporting Services. È possibile installare Reporting Services contemporaneamente all'installazione di Microsoft SQL Server o in qualsiasi momento dopo l'installazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-104">If you intend to use Microsoft Lync Server 2013 Monitoring Reports (see the next section of this documentation for more information) you must first install SQL Server Reporting Services; Reporting Services can be installed at the same time you install Microsoft SQL Server or any time after SQL Server has been installed.</span></span> <span data-ttu-id="5b5aa-105">Se SQL Server non è installato, seguire le istruzioni fornite in precedenza in questa documentazione.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-105">If you have not installed SQL Server, then follow the instructions provided earlier in this documentation.</span></span> <span data-ttu-id="5b5aa-106">Durante l'installazione di SQL Server, verificare che nella pagina Selezione funzionalità venga selezionato Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-106">When installing SQL Server, make sure that, on the Feature Selection page, you select Reporting Services.</span></span> <span data-ttu-id="5b5aa-107">Che installerà SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-107">That will install SQL Server Reporting Services.</span></span>

<span data-ttu-id="5b5aa-108">Se SQL Server è già stato installato, ma non è stato installato SQL Server Reporting Services, è possibile aggiungerlo seguendo il set di istruzioni appropriato per SQL Server 2008 R2 o SQL Server 2012, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-108">If you have already installed SQL Server but did not install SQL Server Reporting Services you can add that feature by following the appropriate set of instructions for SQL Server 2008 R2 or SQL Server 2012, as appropriate.</span></span>

<span data-ttu-id="5b5aa-109">Per verificare che Reporting Services sia stato installato correttamente, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="5b5aa-109">To verify that the reporting Services have been successfully installed, complete the following steps:</span></span>

1.  <span data-ttu-id="5b5aa-110">Se si esegue Microsoft SQL Server 2008 R2, fare clic sul **pulsante Start**, scegliere **tutti i programmi**, **Microsoft SQL Server 2008 R2**, **strumenti di configurazione**e quindi fare clic su **Gestione configurazione di Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-110">If you are running Microsoft SQL Server 2008 R2, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>
    
    <span data-ttu-id="5b5aa-111">Se si esegue Microsoft SQL Server 2012, fare clic sul **pulsante Start**, scegliere **tutti i programmi**, **Microsoft SQL Server 2012**, fare clic su **strumenti di configurazione**e quindi su **Gestione configurazione di Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-111">If you are running Microsoft SQL Server 2012, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2012**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="5b5aa-112">Nella finestra di dialogo **connessione configurazione Reporting Services** verificare che il nome del server sia visualizzato nella casella **nome server** e che il nome dell'istanza di SQL Server in cui sono archiviati i dati di monitoraggio sia visualizzato nella casella **istanza del server di report** .</span><span class="sxs-lookup"><span data-stu-id="5b5aa-112">In the **Reporting Services Configuration Connection** dialog box, verify that the name of your server appears in the **Server Name** box and that the name of the SQL Server instance that stores your monitoring data appears in the **Report Server Instance** box.</span></span> <span data-ttu-id="5b5aa-113">Fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-113">Click **Connect**.</span></span>

<span data-ttu-id="5b5aa-114">In Gestione configurazione di Reporting Service il riquadro Stato del server di report deve indicare che SQL Server Reporting Services è stato installato e che i servizi di Reporting sono attualmente in uso: lo stato del server di report deve essere visualizzato come **avviato** e il pulsante **Start** deve essere disattivato e non disponibile.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-114">In the Reporting Service Configuration Manager, the Report Server Status pane should show that SQL Server Reporting Services has been installed and that the Reporting Services are currently running: the Report Server Status should be shown as **Started** and the **Start** button should be grayed-out and unavailable.</span></span> <span data-ttu-id="5b5aa-115">Se il servizio Reporting non è in corso, fare clic su **Start** per avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-115">If the Reporting Service is not running, click **Start** in order to start the service.</span></span>

<span data-ttu-id="5b5aa-116">Se non è elencato alcun database accanto all'etichetta del nome del database del server di report, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b5aa-116">If no database is listed next to the Report Server Database Name label then do the following:</span></span>

1.  <span data-ttu-id="5b5aa-117">In Gestione configurazione di Reporting Services fare clic su **database**.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-117">In the Reporting Services Configuration Manager click **Database**.</span></span>

2.  <span data-ttu-id="5b5aa-118">Nel riquadro database server di report fare clic su **Cambia database**.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-118">In the Report Server Database pane click **Change Database**.</span></span>

3.  <span data-ttu-id="5b5aa-119">Nel riquadro azioni della configurazione guidata database server report selezionare **Crea un nuovo database del server di report** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-119">In the Report Server Database Configuration wizard, in the Action pane, select **Create a new report server database** and then click **Next**.</span></span>

4.  <span data-ttu-id="5b5aa-120">Nel riquadro Server database della configurazione guidata database server di report verificare che le informazioni elencate nelle caselle **nome server**, **tipo di autenticazione**e nome **utente** siano corrette.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-120">In the Report Server Database Configuration wizard, in the Database Server pane, verify that the information listed in the **Server Name**, **Authentication Type**, and **Username** boxes is correct.</span></span> <span data-ttu-id="5b5aa-121">Fare clic su **Test connessione** per verificare che sia possibile effettuare una connessione al server di database e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-121">Click **Test Connection** to verify that a connection can be made to the database server and then click **Next**.</span></span>

5.  <span data-ttu-id="5b5aa-122">Nel riquadro database della configurazione guidata database server report accettare i valori predefiniti per il **nome del database**, la **lingua**e la **modalità server di report** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-122">In the Report Server Database Configuration wizard, in the Database pane, accept the default values for **Database Name**, **Language**, and **Report Server Mode** and then click **Next**.</span></span>

6.  <span data-ttu-id="5b5aa-123">Nel riquadro credenziali della configurazione guidata database del server di report verificare che le informazioni corrette siano elencate nell'elenco a discesa **tipo di autenticazione** e nelle caselle **nome utente** e **password** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-123">In the Report Server Database Configuration wizard, in the Credentials pane, verify that the correct information is listed in the **Authentication Type** dropdown list and the **User name** and **Password** boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="5b5aa-124">Nel riquadro di riepilogo della configurazione guidata database server di report fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-124">In the Report Server Database Configuration wizard, in the Summary pane, click **Next**.</span></span>

8.  <span data-ttu-id="5b5aa-125">Nel riquadro Stato e fine della configurazione guidata database server di report fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-125">In the Report Server Database Configuration wizard, in the Progress and Finish pane, click **Finish**.</span></span>

<span data-ttu-id="5b5aa-126">Per verificare che gli URL del servizio di Reporting siano stati configurati, fare clic su **URL servizio Web**.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-126">To verify that the Reporting Service URLs have been configured, click **Web Service URL**.</span></span> <span data-ttu-id="5b5aa-127">Nella sezione **URL del servizio Web ReportServer del server report**verrà visualizzato uno o più URL.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-127">You should see one or more URLs listed under the heading **Report Server Web Service URLs**.</span></span> <span data-ttu-id="5b5aa-128">Fare clic su ognuno di questi URL per verificare che sia possibile accedere alla Home page per l'installazione locale di SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="5b5aa-128">Click each of these URLs to verify that you can reach the home page for the local installation of SQL Server Reporting Services.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

