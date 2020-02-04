---
title: 'Lync Server 2013: uso di Microsoft SQL Server 2008 R2 come database di Operations Manager di System Center'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27516e7ca6c3fb70a01b7c1d245054d515ae351b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a><span data-ttu-id="27c82-102">Uso di Microsoft SQL Server 2008 R2 come database di Operations Manager di System Center per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27c82-102">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27c82-103">_**Argomento Ultima modifica:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="27c82-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="27c82-104">Per usare SQL Server 2008 R2 come database back-end, completare la procedura descritta in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="27c82-104">To use SQL Server 2008 R2 as your back-end database, complete the steps detailed in this topic.</span></span>

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a><span data-ttu-id="27c82-105">Configurazione di SQL Server 2008 R2 e SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="27c82-105">Configuring SQL Server 2008 R2 and SQL Server Reporting Services</span></span>

<span data-ttu-id="27c82-106">Prima di iniziare l'installazione di System Center Operations Manager, è necessario apportare due modifiche a SQL Server 2008 R2 e alla configurazione di SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="27c82-106">Before you begin installing System Center Operations Manager you must make two changes to your SQL Server 2008 R2 and your SQL Server Reporting Services configuration.</span></span> <span data-ttu-id="27c82-107">Queste modifiche sono necessarie solo se si usa SQL Server 2008 R2 come database di Operations Manager. Eseguire innanzitutto le operazioni seguenti nel computer che ospita il database di Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="27c82-107">(These changes are required only if you are using SQL Server 2008 R2 as your Operations Manager database.) First, do the following on the computer that will host your Operations Manager database:</span></span>

1.  <span data-ttu-id="27c82-108">Fare clic sul pulsante **Start** e quindi su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="27c82-108">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="27c82-109">Nella finestra di dialogo **Esegui** Digitare **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50. ARCHINST\\Reporting Services\\ReportServer** e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="27c82-109">In the **Run** dialog box, type **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer** and then press ENTER.</span></span>

3.  <span data-ttu-id="27c82-110">Nella cartella **ReportServer** aprire il file **RSReportServer. config** nel blocco note o in qualsiasi altro editor di testo.</span><span class="sxs-lookup"><span data-stu-id="27c82-110">In the **ReportServer** folder, open the file **rsreportserver.config** in Notepad or any other text editor.</span></span>

4.  <span data-ttu-id="27c82-111">Accanto all'inizio del file verrà visualizzata una serie di nodi "Aggiungi chiave".</span><span class="sxs-lookup"><span data-stu-id="27c82-111">Near the beginning of the file you will see a series of "Add Key" nodes.</span></span> <span data-ttu-id="27c82-112">Trovare la voce che inizia \*\* \<Add Key = "SecureConnectionLevel"\*\* e impostare il valore su **0**:</span><span class="sxs-lookup"><span data-stu-id="27c82-112">Find the entry that begins **\<Add Key="SecureConnectionLevel"** and set the value to **0**:</span></span>
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  <span data-ttu-id="27c82-113">Salvare il file **RSReportServer. config** e quindi chiudere l'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="27c82-113">Save the file **rsreportserver.config** and then close your text editor.</span></span>

<span data-ttu-id="27c82-114">Dopo l'aggiornamento del file di configurazione del server di report, è necessario assegnare il certificato corretto a SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="27c82-114">After updating the Report Server configuration file you must then assign the correct certificate to SQL Server Reporting Services.</span></span> <span data-ttu-id="27c82-115">per farlo:</span><span class="sxs-lookup"><span data-stu-id="27c82-115">To do that:</span></span>

1.  <span data-ttu-id="27c82-116">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft SQL Server 2008 R2**, fare clic su **strumenti di configurazione**e quindi su **Gestione configurazione di Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="27c82-116">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="27c82-117">Nella finestra di dialogo **connessione configurazione Reporting Services** verificare che il nome del server sia visualizzato nella casella **nome server** .</span><span class="sxs-lookup"><span data-stu-id="27c82-117">In the **Reporting Services Configuration Connection** dialog box, make sure that the name of your server appears in the **Server Name** box.</span></span> <span data-ttu-id="27c82-118">Selezionare l'istanza di SQL Server che ospiterà il database di Operations Manager, ad esempio **ARCHINST**, nell'elenco a discesa **istanza del server di report** e quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-118">Select the SQL Server instance that will host your Operations Manager database (for example, **ARCHINST**) from the **Report Server Instance** drop-down list and then click **Connect**.</span></span>

3.  <span data-ttu-id="27c82-119">In Gestione configurazione di Reporting Services fare clic su **URL servizio Web**.</span><span class="sxs-lookup"><span data-stu-id="27c82-119">In Reporting Services Configuration Manager, click **Web Service URL**.</span></span>

4.  <span data-ttu-id="27c82-120">Nella pagina **URL servizio Web** selezionare il certificato da usare per Reporting Services dall'elenco a discesa **certificati SSL** e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="27c82-120">On the **Web Service URL** page, select the certificate to be used for your Reporting Services from the **SSL Certificate** dropdown list and then click **Apply**.</span></span> <span data-ttu-id="27c82-121">Dopo alcuni secondi verrà visualizzata una coppia di URL elencati in **URL servizio Web**ReportServer.</span><span class="sxs-lookup"><span data-stu-id="27c82-121">After a few seconds, you will see a pair of URLs listed under **Report Server Web Service URLs**.</span></span>

5.  <span data-ttu-id="27c82-122">Fare clic su entrambi gli URL per verificare che sia possibile accedere a SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="27c82-122">Click both of the URLs to verify that you can access SQL Server Reporting Services.</span></span>

6.  <span data-ttu-id="27c82-123">Chiudere Gestione configurazione di Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="27c82-123">Close Reporting Services Configuration Manager.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="27c82-124">Creazione di un database di System Center Operations Manager da usare con SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="27c82-124">Creating a System Center Operations Manager database for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="27c82-125">Se si vuole configurare System Center Operations Manager per l'uso di un database di SQL Server 2008 R2, sarà necessario "manualmente" creare il database di Operations Manager nel computer in cui è installato SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="27c82-125">If you want to configure System Center Operations Manager to use a SQL Server 2008 R2 database, you will need to "manually" create the Operations Manager database on the computer running SQL Server 2008 R2.</span></span> <span data-ttu-id="27c82-126">Di nuovo, questi passaggi non sono necessari se si usa SQL Server 2005 o SQL Server 2008 come database back-end.</span><span class="sxs-lookup"><span data-stu-id="27c82-126">(Again, these steps are not required if you are using SQL Server 2005 or SQL Server 2008 as your back-end database.)</span></span>

<span data-ttu-id="27c82-127">Per creare manualmente un database di Operations Manager, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="27c82-127">To manually create an Operations Manager database do the following:</span></span>

1.  <span data-ttu-id="27c82-128">Nel supporto di configurazione di System Center Operations Manager 2007 R2, nella cartella\\SupportTools amd64, fare doppio clic su **DBCreateWizard. exe**.</span><span class="sxs-lookup"><span data-stu-id="27c82-128">On the System Center Operations Manager 2007 R2 setup media, in the SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="27c82-129">Nella schermata **Introduzione alla configurazione** guidata database della configurazione guidata database fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-129">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="27c82-130">Nella pagina **informazioni database** uscire da tutte le impostazioni e quindi fare clic su **Avanti**</span><span class="sxs-lookup"><span data-stu-id="27c82-130">On the **Database Information** page leave all the settings as-is and then click **Next**</span></span>

4.  <span data-ttu-id="27c82-131">Nella pagina **Configurazione gruppo di gestione** Digitare un nome per il gruppo di gestione, ad esempio **il monitoraggio di Lync Server**, nella casella **nome gruppo** di gestione e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-131">On the **Management Group Configuration** page type a name for your Management Group (for example, **Lync Server Monitoring**) in the **Management Group name** box and then click **Next**.</span></span>

5.  <span data-ttu-id="27c82-132">Nella pagina **report di errore di Operations Manager** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-132">On the **Operations Manager Error Reports** page click **Next**.</span></span>

6.  <span data-ttu-id="27c82-133">Nella pagina di **Riepilogo** fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="27c82-133">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="27c82-134">Creazione di un data warehouse di System Center Operations Manager da usare con SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="27c82-134">Creating a System Center Operations Manager data warehouse for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="27c82-135">Microsoft Lync Server 2013 viene fornito con tre nuovi report di Operations Manager di System Center:</span><span class="sxs-lookup"><span data-stu-id="27c82-135">Microsoft Lync Server 2013 ships with three new System Center Operations Manager reports:</span></span>

  - <span data-ttu-id="27c82-136">**Report disponibilità scenario finale**   questo report descrive in dettaglio la disponibilità/uptime dei servizi principali di Lync Server, ad esempio registrazione o presenza.</span><span class="sxs-lookup"><span data-stu-id="27c82-136">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="27c82-137">**Report capacità con**   le informazioni sui contatori delle prestazioni, questo report Mostra le tendenze per i componenti di sistema, ad esempio la disponibilità della memoria e l'uso del processore</span><span class="sxs-lookup"><span data-stu-id="27c82-137">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="27c82-138">**Report componente questo**   report elenca i generatori di avvisi principali raggruppati in base al componente Lync Server.</span><span class="sxs-lookup"><span data-stu-id="27c82-138">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="27c82-139">Per usare questi nuovi report, è necessario installare un data warehouse di System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="27c82-139">In order to use these new reports you must install a System Center Operations Manager data warehouse.</span></span> <span data-ttu-id="27c82-140">Un data warehouse consente l'archiviazione a lungo termine dei dati delle operazioni. Per usare un data warehouse con SQL Server 2008 R2, è necessario eseguire la procedura seguente nel computer che ospita il database di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="27c82-140">(A data warehouse provides for long-term storage of operations data.) To use a data warehouse with SQL Server 2008 R2 you must carry out the following steps on the computer that hosts your SQL Server database:</span></span>

1.  <span data-ttu-id="27c82-141">Nel supporto di configurazione di System Center Operations Manager, nella cartella\\Setup\\SupportTools amd64, fare doppio clic su **DBCreateWizard. exe**.</span><span class="sxs-lookup"><span data-stu-id="27c82-141">On the System Center Operations Manager setup media, in the Setup\\SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="27c82-142">Nella schermata **Introduzione alla configurazione** guidata database della configurazione guidata database fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-142">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="27c82-143">Nella pagina **informazioni database** selezionare **database warehouse dei dati di Operations Manager** dall'elenco a discesa **tipo di database** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-143">On the **Database Information** page, select **Operations Manager Data Warehouse Database** from the **Database Type** dropdown list and then click **Next**.</span></span>

4.  <span data-ttu-id="27c82-144">Nella pagina di **Riepilogo** fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="27c82-144">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a><span data-ttu-id="27c82-145">Installazione della console di System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="27c82-145">Installing the System Center Operations Manager console</span></span>

<span data-ttu-id="27c82-146">La console di Operations Manager è lo strumento principale usato per gestire System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="27c82-146">The Operations Manager console is the primary tool used to manage System Center Operations Manager.</span></span> <span data-ttu-id="27c82-147">Prima di installare la console di Operations Manager, verificare di avere installato una versione supportata di SQL Server insieme a SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="27c82-147">Before you install the Operations Manager console, make sure that you have installed a supported version of SQL Server along with the SQL Server Reporting Service.</span></span> <span data-ttu-id="27c82-148">Si consiglia inoltre di eseguire Gestione configurazione di Reporting Services di SQL Server per verificare che il servizio Reporting sia stato installato e configurato correttamente.</span><span class="sxs-lookup"><span data-stu-id="27c82-148">It is also recommended that you run SQL Server's Reporting Services Configuration Manager to verify that the Reporting Service has been correctly installed and configured.</span></span>

<span data-ttu-id="27c82-149">Per installare la console di System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="27c82-149">To install the System Center Operations Manager console:</span></span>

1.  <span data-ttu-id="27c82-150">Nel supporto di configurazione di System Center Operations Manager fare doppio clic su **SetupOM. exe**.</span><span class="sxs-lookup"><span data-stu-id="27c82-150">On the System Center Operations Manager setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="27c82-151">Nella configurazione di System Center Operations Manager 2007 R2 fare clic su **Controlla prerequisiti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-151">In System Center Operations Manager 2007 R2 Setup, click **Check Prerequisites**.</span></span>

3.  <span data-ttu-id="27c82-152">Nel Visualizzatore prerequisiti di System Center Operations Manager selezionare i componenti di System Center da installare: (**Server**; **Console**; e **PowerShell**), quindi fare clic su **Controlla**.</span><span class="sxs-lookup"><span data-stu-id="27c82-152">In the System Center Operations Manager Prerequisite Viewer, select the System Center components to be installed: (**Server**; **Console**; and **PowerShell**) and then click **Check**.</span></span> <span data-ttu-id="27c82-153">Verificare che non siano stati segnalati problemi di blocco e quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="27c82-153">Verify that no blocking issues have been reported and then click **Close**.</span></span> <span data-ttu-id="27c82-154">Se è stato segnalato un problema di blocco, correggere il problema e quindi fare clic su **Verifica** per eseguire di nuovo il test dei prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="27c82-154">If a blocking issue has been reported, correct the problem and then click **Check** to re-run the prerequisite testing.</span></span>

4.  <span data-ttu-id="27c82-155">In configurazione di System Center Operations Manager fare clic su **Installa Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="27c82-155">In System Center Operations Manager Setup, click **Install Operations Manager**.</span></span>

5.  <span data-ttu-id="27c82-156">Nella configurazione guidata di System Center Operations Manager, nella pagina **Introduzione alla configurazione guidata di System Center Operations Manager** , fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-156">In the System Center Operations Manager Setup wizard, on the **Welcome to the System Center Operations Manager Setup Wizard** page, click **Next**.</span></span>

6.  <span data-ttu-id="27c82-157">Nella pagina **contratto di licenza con l'utente finale** selezionare **Accetto i termini del contratto di licenza** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-157">On the **End-User License Agreement** page, select **I accept the terms in the license agreement** and then click **Next**.</span></span>

7.  <span data-ttu-id="27c82-158">Nella pagina di **registrazione del prodotto** Digitare il proprio nome nella casella **nome utente** e nome dell'organizzazione nella casella **organizzazione** .</span><span class="sxs-lookup"><span data-stu-id="27c82-158">On the **Product Registration** page, type your name in the **User Name** box and name of your organization in the **Organization** box.</span></span> <span data-ttu-id="27c82-159">Digitare il codice Product Key di System Center Operations Manager nella casella **immettere il codice CD di 25 cifre** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-159">Type your System Center Operations Manager product key in the **Enter your 25 digit CD Key** box and then click **Next**.</span></span>

8.  <span data-ttu-id="27c82-160">Nella pagina **configurazione personalizzata** selezionare le opzioni di System Center da installare e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-160">On the **Custom Setup** page select the System Center options to be installed and then click **Next**.</span></span> <span data-ttu-id="27c82-161">È consigliabile selezionare **server di gestione**, **interfacce utente**e **console Web** per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="27c82-161">You should select **Management Server**, **User Interfaces**, and **Web Console** to be installed.</span></span> <span data-ttu-id="27c82-162">Il **database** non deve essere selezionato e non deve essere installato.</span><span class="sxs-lookup"><span data-stu-id="27c82-162">**Database** should not be selected and should not be installed.</span></span>

9.  <span data-ttu-id="27c82-163">Nella pagina dell' **istanza del server di database SC** verificare che nella casella **Server System Center database** sia visualizzato il nome del computer in cui sono installati i database di Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="27c82-163">On the **SC Database Server Instance** page, verify that the name of the computer where the Operations Manager databases are installed appears in the **System Center Database Server** box.</span></span> <span data-ttu-id="27c82-164">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-164">Click **Next**.</span></span>

10. <span data-ttu-id="27c82-165">Nella pagina **account azione del server di gestione** selezionare **dominio o account del computer locale** e quindi immettere i valori appropriati nelle caselle **account utente**, **password**e **dominio o computer locale** .</span><span class="sxs-lookup"><span data-stu-id="27c82-165">On the **Management Server Action Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="27c82-166">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-166">Click **Next**.</span></span>

11. <span data-ttu-id="27c82-167">Nella pagina **account del servizio SDK e configurazione** selezionare **dominio o account del computer locale** e quindi immettere i valori appropriati nelle caselle **account utente**, **password**e **dominio o computer locale** .</span><span class="sxs-lookup"><span data-stu-id="27c82-167">On the **SDK and Config Service Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="27c82-168">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-168">Click **Next**.</span></span>

12. <span data-ttu-id="27c82-169">Nella pagina **report di errore di Operations Manager** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-169">On the **Operations Manager Error Reports** page click **Next**.</span></span>

13. <span data-ttu-id="27c82-170">Nella pagina del **programma Analisi utilizzo software** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-170">On the **Customer Experience Improvement Program** page click **Next**.</span></span>

14. <span data-ttu-id="27c82-171">Nella pagina **pronto per l'installazione del programma** fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="27c82-171">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="27c82-172">Nella pagina **completamento della configurazione di System Center Operations Manager** deselezionare la **chiave di crittografia backup** e **avviare le caselle** di controllo della console e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="27c82-172">On the **Completing the System Center Operations Manager Setup** page, clear the **Backup Encryption Key** and **Start the console checkboxes** and then click **Finish**.</span></span>

16. <span data-ttu-id="27c82-173">Nella configurazione di System Center Operations Manager fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="27c82-173">In System Center Operations Manager Setup click **Exit**.</span></span>

</div>

<div>

## <a name="installing-system-center-reporting-services"></a><span data-ttu-id="27c82-174">Installazione di System Center Reporting Services</span><span class="sxs-lookup"><span data-stu-id="27c82-174">Installing System Center Reporting Services</span></span>

<span data-ttu-id="27c82-175">Dopo l'installazione e la configurazione della console di System Center Operations Manager, è necessario installare System Center Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="27c82-175">After installing and configuring the System Center Operations Manager console you must then install System Center Reporting Services.</span></span> <span data-ttu-id="27c82-176">Se si usa SQL Server 2008 R2 come database back-end di Operations Manager, ciò significa che è necessario prima apportare una modifica temporanea al gruppo di sicurezza associato a SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="27c82-176">If you are using SQL Server 2008 R2 as your Operations Manager back-end database, that means that you must first make a temporary change to the security group associated with SQL Server Reporting Services.</span></span> <span data-ttu-id="27c82-177">Se si usa SQL Server 2008 R2, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="27c82-177">If you are using SQL Server 2008 R2, you must do the following:</span></span>

1.  <span data-ttu-id="27c82-178">Fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **Gestione server**.</span><span class="sxs-lookup"><span data-stu-id="27c82-178">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="27c82-179">In Server Manager espandere **configurazione**, espandere **utenti e gruppi locali**e quindi fare clic su **gruppi**.</span><span class="sxs-lookup"><span data-stu-id="27c82-179">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="27c82-180">Individuare il gruppo seguente, in cui ATL-SC-001 rappresenta il nome del computer e ARCHINST rappresenta l'istanza di SQL Server per il database System Center: **SQLServerReportServerUser $ ATL-SC-001 $\_MSRS10 50. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="27c82-180">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the System Center database: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

4.  <span data-ttu-id="27c82-181">Fare clic con il pulsante destro del mouse sul gruppo e quindi scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="27c82-181">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="27c82-182">Rinominare il gruppo eliminando \*\* \_50\*\* dal nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="27c82-182">Rename the group by deleting **\_50** from the group name.</span></span> <span data-ttu-id="27c82-183">Ad esempio: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="27c82-183">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

5.  <span data-ttu-id="27c82-184">Chiudere Server Manager.</span><span class="sxs-lookup"><span data-stu-id="27c82-184">Close Server Manager.</span></span>

<span data-ttu-id="27c82-185">A questo punto si è pronti per installare System Center Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="27c82-185">At this point you are ready to install System Center Reporting Services.</span></span> <span data-ttu-id="27c82-186">Procedi come segue.</span><span class="sxs-lookup"><span data-stu-id="27c82-186">To do this:</span></span>

1.  <span data-ttu-id="27c82-187">Nel supporto di configurazione di System Center Operations Manager 2007 R2 fare doppio clic su **SetupOM. exe**.</span><span class="sxs-lookup"><span data-stu-id="27c82-187">On the System Center Operations Manager 2007 R2 Setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="27c82-188">Nella configurazione di System Center Operations Manager 2007 R2 fare clic su **Installa report di Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="27c82-188">In System Center Operations Manager 2007 R2 Setup, click **Install Operations Manager Reporting**.</span></span>

3.  <span data-ttu-id="27c82-189">Nella pagina Configurazione guidata report di Operations Manager 2007 R2, nella pagina **installazione report di Operations Manager** , fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-189">In the System Center Operations Manager 2007 R2 Reporting Setup wizard, on the **Welcome to Operations Manager Reporting Setup** page, click **Next**.</span></span>

4.  <span data-ttu-id="27c82-190">Nella pagina **contratto di licenza con l'utente finale** selezionare **Accetto i termini del contratto di licenza** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-190">On the **End-user License Agreement** page select **I accept the terms of the license agreement** and then click **Next**.</span></span>

5.  <span data-ttu-id="27c82-191">Nella pagina di **registrazione del prodotto** verificare che il nome e il nome dell'organizzazione vengano visualizzati nelle caselle **nome utente** e **organizzazione** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-191">On the **Product Registration** page, ensure that your name and the name of your organization appear in the **User Name** and **Organization** boxes and then click **Next**.</span></span>

6.  <span data-ttu-id="27c82-192">Nella pagina **configurazione personalizzata** fare clic su **server di report** e selezionare **questo componente e tutti i componenti dipendenti verranno installati nell'unità disco locale**.</span><span class="sxs-lookup"><span data-stu-id="27c82-192">On the **Custom Setup** page, click **Reporting Server** and select **This component, and all dependent components, will be installed on local disk drive**.</span></span> <span data-ttu-id="27c82-193">Fare clic su **data warehouse** e selezionare **questo componente non sarà disponibile**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-193">Click **Data Warehouse** and select **This component will not be available**, and then click **Next**.</span></span>

7.  <span data-ttu-id="27c82-194">Nella pagina **Connetti alla pagina server di gestione radice** Digitare il nome del server di gestione radice di Operations Manager nella casella **Server** di gestione radice e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-194">On the **Connect to the Root Management Server** page, type the name of your Operations Manager root management server in the **Root Management Server** box and then click **Next**.</span></span>

8.  <span data-ttu-id="27c82-195">Nella pagina **Connect to the Operations Manager data warehouse** Digitare l'istanza di SQL Server in cui si trova il data warehouse nella casella **istanza di SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="27c82-195">On the **Connect to the Operations Manager Data Warehouse** page, type the SQL Server instance where your data warehouse is located in the **SQL Server Instance** box.</span></span> <span data-ttu-id="27c82-196">Se il data warehouse si trova nell'istanza predefinita, digitare semplicemente il nome del server, ad esempio: ATL-SQL-001. Verificare che il nome del database **OperationsManagerDW** sia visualizzato nella casella **nome** e che la porta **1433** venga visualizzata nella casella **porta di SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="27c82-196">(If your data warehouse is located in the Default instance then simply type the server name; for example: atl-sql-001.) Verify that the database name **OperationsManagerDW** appears in the **Name** box, and that port **1433** appears in the **SQL Server port** box.</span></span> <span data-ttu-id="27c82-197">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-197">Click **Next**.</span></span>

9.  <span data-ttu-id="27c82-198">Nella pagina **istanza di Reporting di SQL Server** selezionare il server di report di SQL Server nell'elenco a discesa **immettere il server di SQL Server Reporting Services** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-198">On the **SQL Server Reporting Instance** page, select your SQL Server reporting server from the **Enter the SQL Server Reporting Services Server** dropdown list and then click **Next**.</span></span>

10. <span data-ttu-id="27c82-199">Nella pagina **account di scrittura data warehouse** immettere il nome e la password dell'utente a cui assegnare inizialmente le autorizzazioni di scrittura per il data warehouse nelle caselle **account utente** e **password** .</span><span class="sxs-lookup"><span data-stu-id="27c82-199">On the **Data Warehouse Write Account** page, enter the name and password of the user to be initially assigned write permissions to the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="27c82-200">Selezionare il dominio dell'utente nell'elenco a discesa **Domain** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-200">Select the user's domain from the **Domain** dropdown list and then click **Next**.</span></span>

11. <span data-ttu-id="27c82-201">Nella pagina **account Reader dati** immettere il nome e la password dell'account utente da usare quando SQL Reporting Services esegue una query nel data warehouse nelle caselle **account utente** e **password** .</span><span class="sxs-lookup"><span data-stu-id="27c82-201">On the **Data Reader Account** page, enter the name and password of the user account to be used when SQL Reporting Services queries the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="27c82-202">Selezionare il dominio dell'account dall'elenco a discesa **Domain** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-202">Select the account domain from the **Domain** dropdown list and then click **Next**.</span></span>

12. <span data-ttu-id="27c82-203">Nella pagina **report dati operativi** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-203">On the **Operational Data Reports** page, click **Next**.</span></span>

13. <span data-ttu-id="27c82-204">Nella pagina **Microsoft Update** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27c82-204">On the **Microsoft Update** page, click **Next**.</span></span>

14. <span data-ttu-id="27c82-205">Nella pagina **pronto per l'installazione del programma** fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="27c82-205">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="27c82-206">Nella pagina **completamento della configurazione guidata componenti di report di Operations Manager** fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="27c82-206">On the **Completing the Operations Manager Reporting Components Setup Wizard** page, click **Finish**.</span></span>

16. <span data-ttu-id="27c82-207">Nella configurazione di System Center Operations Manager 2007 R2 fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="27c82-207">In System Center Operations Manager 2007 R2 Setup, click **Exit**.</span></span>

<span data-ttu-id="27c82-208">Dopo aver installato System Center Reporting, usare la procedura seguente per reimpostare il nome del gruppo di sicurezza associato ai report di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="27c82-208">After System Center reporting has been installed you then use the following procedure to reset the name of the security group associated with SQL Server reporting.</span></span> <span data-ttu-id="27c82-209">Anche in questo caso, questa procedura è obbligatoria solo se si usa SQL Server:</span><span class="sxs-lookup"><span data-stu-id="27c82-209">Again, this procedure is only required if you are using SQL Server:</span></span>

1.  <span data-ttu-id="27c82-210">Fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **Gestione server**.</span><span class="sxs-lookup"><span data-stu-id="27c82-210">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="27c82-211">In Server Manager espandere **configurazione**, espandere **utenti e gruppi locali**e quindi fare clic su **gruppi**.</span><span class="sxs-lookup"><span data-stu-id="27c82-211">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="27c82-212">Individuare il gruppo seguente, in cui ATL-SC-001 rappresenta il nome del computer e ARCHINST rappresenta l'istanza di SQL Server per i database di archiviazione e monitoraggio: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="27c82-212">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the archiving and monitoring databases: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

4.  <span data-ttu-id="27c82-213">Fare clic con il pulsante destro del mouse sul gruppo e quindi scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="27c82-213">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="27c82-214">Rinominare il gruppo aggiungendo \*\* \_50\*\* alla fine del nome del gruppo, a destra prima del nome dell'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="27c82-214">Rename the group by adding **\_50** to the end of the group name, right before the SQL Server instance name.</span></span> <span data-ttu-id="27c82-215">Ad esempio: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10\_50. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="27c82-215">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

5.  <span data-ttu-id="27c82-216">Chiudere Server Manager.</span><span class="sxs-lookup"><span data-stu-id="27c82-216">Close Server Manager.</span></span>

<span data-ttu-id="27c82-217">Se la console operativa di System Center è aperta, sarà necessario chiudere l'applicazione e quindi riavviarla. Se non si esegue questa operazione, la scheda **report** non verrà visualizzata nell'interfaccia utente della console operatore.</span><span class="sxs-lookup"><span data-stu-id="27c82-217">If the System Center Operations Console is open you will need to close the application and then restart it; if you do not do this the **Reporting** tab will not appear in the Operations Console user interface.</span></span> <span data-ttu-id="27c82-218">Tieni presente che, dopo aver riavviato la prima volta la console operativa, potrebbero essere necessari alcuni minuti prima che tutti i report di monitoraggio vengano visualizzati nella scheda **report** .</span><span class="sxs-lookup"><span data-stu-id="27c82-218">Note that, after restarting the Operations Console the first time, it could take several minutes before all the Monitoring Reports appear on the **Reporting** tab.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

