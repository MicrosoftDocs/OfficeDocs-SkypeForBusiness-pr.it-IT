---
title: 'Lync Server 2013: utilizzo di Microsoft SQL Server 2008 R2 come database di System Center Operations Manager'
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
ms.openlocfilehash: 51dbff3748f342bd630c33fc867a4249b386c00c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518823"
---
# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a><span data-ttu-id="fb65c-102">Utilizzo di Microsoft SQL Server 2008 R2 come database di System Center Operations Manager per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb65c-102">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb65c-103">_**Ultimo argomento modificato:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="fb65c-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="fb65c-104">Per utilizzare SQL Server 2008 R2 come database back-end, completare la procedura descritta in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="fb65c-104">To use SQL Server 2008 R2 as your back-end database, complete the steps detailed in this topic.</span></span>

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a><span data-ttu-id="fb65c-105">Configurazione di SQL Server 2008 R2 e SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="fb65c-105">Configuring SQL Server 2008 R2 and SQL Server Reporting Services</span></span>

<span data-ttu-id="fb65c-106">Prima di iniziare a installare System Center Operations Manager, è necessario apportare due modifiche alla configurazione di SQL Server 2008 R2 e SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="fb65c-106">Before you begin installing System Center Operations Manager you must make two changes to your SQL Server 2008 R2 and your SQL Server Reporting Services configuration.</span></span> <span data-ttu-id="fb65c-107">Queste modifiche sono necessarie solo se si utilizza SQL Server 2008 R2 come database di Operations Manager. In primo luogo, eseguire le operazioni seguenti nel computer che ospiterà il database di Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="fb65c-107">(These changes are required only if you are using SQL Server 2008 R2 as your Operations Manager database.) First, do the following on the computer that will host your Operations Manager database:</span></span>

1.  <span data-ttu-id="fb65c-108">Fare clic sul pulsante **Start**, quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-108">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="fb65c-109">Nella finestra di dialogo **Esegui** Digitare **C: \\ Program Files \\ Microsoft SQL Server \\ MSRS10 \_ 50. ARCHINST \\ Reporting Services \\ ReportServer** e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="fb65c-109">In the **Run** dialog box, type **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer** and then press ENTER.</span></span>

3.  <span data-ttu-id="fb65c-110">Nella cartella **ReportServer** aprire il file **rsreportserver.config** nel Blocco note o in un altro editor di testo.</span><span class="sxs-lookup"><span data-stu-id="fb65c-110">In the **ReportServer** folder, open the file **rsreportserver.config** in Notepad or any other text editor.</span></span>

4.  <span data-ttu-id="fb65c-111">Quasi all'inizio del file è presente una serie di nodi "Add Key".</span><span class="sxs-lookup"><span data-stu-id="fb65c-111">Near the beginning of the file you will see a series of "Add Key" nodes.</span></span> <span data-ttu-id="fb65c-112">Individuare la voce che inizia con l' \*\* \< aggiunta di Key = "SecureConnectionLevel"\*\* e impostare il valore su **0**:</span><span class="sxs-lookup"><span data-stu-id="fb65c-112">Find the entry that begins **\<Add Key="SecureConnectionLevel"** and set the value to **0**:</span></span>
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  <span data-ttu-id="fb65c-113">Salvare il file **rsreportserver.config** e chiudere l'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="fb65c-113">Save the file **rsreportserver.config** and then close your text editor.</span></span>

<span data-ttu-id="fb65c-p103">Dopo avere aggiornato il file di configurazione del server di report, è necessario assegnare il certificato corretto a SQL Server Reporting Services. A questo scopo:</span><span class="sxs-lookup"><span data-stu-id="fb65c-p103">After updating the Report Server configuration file you must then assign the correct certificate to SQL Server Reporting Services. To do that:</span></span>

1.  <span data-ttu-id="fb65c-116">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft SQL Server 2008 R2**, **strumenti di configurazione**e quindi fare clic su **Gestione configurazione Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-116">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="fb65c-117">Nella finestra di dialogo **Connessione configurazione Reporting Services** verificare che nella casella **Nome server** sia presente il nome del server.</span><span class="sxs-lookup"><span data-stu-id="fb65c-117">In the **Reporting Services Configuration Connection** dialog box, make sure that the name of your server appears in the **Server Name** box.</span></span> <span data-ttu-id="fb65c-118">Selezionare l'istanza di SQL Server che ospiterà il database di Operations Manager (ad esempio, **ARCHINST**) dall'elenco a discesa **istanza del server di report** e quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-118">Select the SQL Server instance that will host your Operations Manager database (for example, **ARCHINST**) from the **Report Server Instance** drop-down list and then click **Connect**.</span></span>

3.  <span data-ttu-id="fb65c-119">In Gestione configurazione Reporting Services fare clic su **URL servizio Web**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-119">In Reporting Services Configuration Manager, click **Web Service URL**.</span></span>

4.  <span data-ttu-id="fb65c-p105">Nella pagina **URL servizio Web** selezionare il certificato da utilizzare per l'istanza di Reporting Services nell'elenco a discesa **Certificato SSL**, quindi fare clic su **Applica**. Dopo alcuni secondi comparirà una coppia di URL in **URL servizio Web ReportServer**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-p105">On the **Web Service URL** page, select the certificate to be used for your Reporting Services from the **SSL Certificate** dropdown list and then click **Apply**. After a few seconds, you will see a pair of URLs listed under **Report Server Web Service URLs**.</span></span>

5.  <span data-ttu-id="fb65c-122">Fare clic su entrambi gli URL per verificare di poter accedere a SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="fb65c-122">Click both of the URLs to verify that you can access SQL Server Reporting Services.</span></span>

6.  <span data-ttu-id="fb65c-123">Chiudere Gestione configurazione Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="fb65c-123">Close Reporting Services Configuration Manager.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="fb65c-124">Creazione di un database System Center Operations Manager per l'utilizzo con SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="fb65c-124">Creating a System Center Operations Manager database for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="fb65c-125">Se si desidera configurare System Center Operations Manager per l'utilizzo di un database di SQL Server 2008 R2, è necessario creare manualmente il database di Operations Manager nel computer in cui è in esecuzione SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="fb65c-125">If you want to configure System Center Operations Manager to use a SQL Server 2008 R2 database, you will need to "manually" create the Operations Manager database on the computer running SQL Server 2008 R2.</span></span> <span data-ttu-id="fb65c-126">(Di nuovo, questi passaggi non sono necessari se si utilizza SQL Server 2005 o SQL Server 2008 come database back-end).</span><span class="sxs-lookup"><span data-stu-id="fb65c-126">(Again, these steps are not required if you are using SQL Server 2005 or SQL Server 2008 as your back-end database.)</span></span>

<span data-ttu-id="fb65c-127">Per creare manualmente un database di Operations Manager, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb65c-127">To manually create an Operations Manager database do the following:</span></span>

1.  <span data-ttu-id="fb65c-128">Nel supporto di installazione di System Center Operations Manager 2007 R2, nella \\ cartella SupportTools amd64 fare doppio clic su **DBCreateWizard.exe**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-128">On the System Center Operations Manager 2007 R2 setup media, in the SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="fb65c-129">Nella pagina iniziale della **Configurazione guidata database** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-129">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="fb65c-130">Nella pagina **Informazioni database** lasciare invariate tutte le impostazioni e fare clic su **Avanti**</span><span class="sxs-lookup"><span data-stu-id="fb65c-130">On the **Database Information** page leave all the settings as-is and then click **Next**</span></span>

4.  <span data-ttu-id="fb65c-131">Nella pagina **Configurazione gruppo di gestione** Digitare un nome per il gruppo di gestione, ad esempio **il monitoraggio di Lync Server**, nella casella **nome gruppo di gestione** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-131">On the **Management Group Configuration** page type a name for your Management Group (for example, **Lync Server Monitoring**) in the **Management Group name** box and then click **Next**.</span></span>

5.  <span data-ttu-id="fb65c-132">Nella pagina **Segnalazioni errori di Operations Manager** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-132">On the **Operations Manager Error Reports** page click **Next**.</span></span>

6.  <span data-ttu-id="fb65c-133">Nella pagina **Riepilogo** fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-133">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="fb65c-134">Creazione di un data warehouse di System Center Operations Manager per l'utilizzo con SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="fb65c-134">Creating a System Center Operations Manager data warehouse for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="fb65c-135">Microsoft Lync Server 2013 viene fornito con tre nuovi report di System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="fb65c-135">Microsoft Lync Server 2013 ships with three new System Center Operations Manager reports:</span></span>

  - <span data-ttu-id="fb65c-136">Report di disponibilità dello **scenario end to end**     Questo rapporto descrive in dettaglio la disponibilità/tempo di uptime per i servizi chiave di Lync Server, ad esempio la registrazione o la presenza.</span><span class="sxs-lookup"><span data-stu-id="fb65c-136">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="fb65c-137">**Rapporto capacità**     Utilizzando le informazioni sui contatori delle prestazioni, questo rapporto illustra le tendenze per i componenti di sistema, ad esempio la disponibilità della memoria e l'utilizzo del processore</span><span class="sxs-lookup"><span data-stu-id="fb65c-137">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="fb65c-138">**Report componente**     In questo report sono elencati i generatori di avvisi principali raggruppati in base al componente Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb65c-138">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="fb65c-139">Per utilizzare questi nuovi rapporti, è necessario installare un data warehouse di System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="fb65c-139">In order to use these new reports you must install a System Center Operations Manager data warehouse.</span></span> <span data-ttu-id="fb65c-140">(Un data warehouse fornisce l'archiviazione a lungo termine dei dati delle operazioni). Per utilizzare un data warehouse con SQL Server 2008 R2, è necessario eseguire i passaggi seguenti nel computer che ospita il database di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="fb65c-140">(A data warehouse provides for long-term storage of operations data.) To use a data warehouse with SQL Server 2008 R2 you must carry out the following steps on the computer that hosts your SQL Server database:</span></span>

1.  <span data-ttu-id="fb65c-141">Nel supporto di installazione di System Center Operations Manager, nella \\ cartella Setup SupportTools \\ amd64 fare doppio clic su **DBCreateWizard.exe**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-141">On the System Center Operations Manager setup media, in the Setup\\SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="fb65c-142">Nella pagina iniziale della **Configurazione guidata database** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-142">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="fb65c-143">Nella pagina **Informazioni database** selezionare **Database data warehouse di Operations Manager** nell'elenco a discesa **Tipo database**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-143">On the **Database Information** page, select **Operations Manager Data Warehouse Database** from the **Database Type** dropdown list and then click **Next**.</span></span>

4.  <span data-ttu-id="fb65c-144">Nella pagina **Riepilogo** fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-144">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a><span data-ttu-id="fb65c-145">Installazione della console di System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="fb65c-145">Installing the System Center Operations Manager console</span></span>

<span data-ttu-id="fb65c-146">La console di Operations Manager è lo strumento principale utilizzato per gestire System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="fb65c-146">The Operations Manager console is the primary tool used to manage System Center Operations Manager.</span></span> <span data-ttu-id="fb65c-147">Prima di installare la console di Operations Manager, verificare di aver installato una versione supportata di SQL Server insieme a SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="fb65c-147">Before you install the Operations Manager console, make sure that you have installed a supported version of SQL Server along with the SQL Server Reporting Service.</span></span> <span data-ttu-id="fb65c-148">È inoltre consigliabile eseguire Gestione configurazione Reporting Services di SQL Server per verificare che Reporting Service sia installato e configurato correttamente.</span><span class="sxs-lookup"><span data-stu-id="fb65c-148">It is also recommended that you run SQL Server's Reporting Services Configuration Manager to verify that the Reporting Service has been correctly installed and configured.</span></span>

<span data-ttu-id="fb65c-149">Per installare la console di System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="fb65c-149">To install the System Center Operations Manager console:</span></span>

1.  <span data-ttu-id="fb65c-150">Nel supporto di installazione di System Center Operations Manager fare doppio clic su **SetupOM.exe**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-150">On the System Center Operations Manager setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="fb65c-151">Nel programma di installazione di System Center Operations Manager 2007 R2 fare clic su **Controlla prerequisiti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-151">In System Center Operations Manager 2007 R2 Setup, click **Check Prerequisites**.</span></span>

3.  <span data-ttu-id="fb65c-152">Nel Visualizzatore prerequisiti di System Center Operations Manager selezionare i componenti di System Center da installare: (**Server**; **Console**; e **PowerShell**), quindi fare clic su **Controlla**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-152">In the System Center Operations Manager Prerequisite Viewer, select the System Center components to be installed: (**Server**; **Console**; and **PowerShell**) and then click **Check**.</span></span> <span data-ttu-id="fb65c-153">Verificare che non siano stati riscontrati problemi gravi e quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-153">Verify that no blocking issues have been reported and then click **Close**.</span></span> <span data-ttu-id="fb65c-154">Se viene segnalato un problema grave, correggerlo e fare clic su **Controlla** per ripetere il test dei prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="fb65c-154">If a blocking issue has been reported, correct the problem and then click **Check** to re-run the prerequisite testing.</span></span>

4.  <span data-ttu-id="fb65c-155">Nel programma di installazione di System Center Operations Manager fare clic su **Installa Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-155">In System Center Operations Manager Setup, click **Install Operations Manager**.</span></span>

5.  <span data-ttu-id="fb65c-156">Nell'installazione guidata di System Center Operations Manager, nella pagina **installazione guidata di System Center Operations Manager** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-156">In the System Center Operations Manager Setup wizard, on the **Welcome to the System Center Operations Manager Setup Wizard** page, click **Next**.</span></span>

6.  <span data-ttu-id="fb65c-157">Nella pagina **Contratto di licenza con l'utente finale** selezionare **Accetto i termini del Contratto di licenza** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-157">On the **End-User License Agreement** page, select **I accept the terms in the license agreement** and then click **Next**.</span></span>

7.  <span data-ttu-id="fb65c-158">Nella pagina **Registrazione prodotto** digitare il proprio nome nella casella **Nome utente** e il nome dell'organizzazione nella casella **Organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-158">On the **Product Registration** page, type your name in the **User Name** box and name of your organization in the **Organization** box.</span></span> <span data-ttu-id="fb65c-159">Digitare il codice Product Key di System Center Operations Manager nella casella **immettere il codice CD di 25 cifre** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-159">Type your System Center Operations Manager product key in the **Enter your 25 digit CD Key** box and then click **Next**.</span></span>

8.  <span data-ttu-id="fb65c-p111">Nella pagina **Installazione personalizzata** selezionare le opzioni di System Center da installare, quindi fare clic su **Avanti**. È consigliabile selezionare **Server di gestione**, **Interfacce utente** e **Console Web** per l'installazione, ma non selezionare e installare **Database**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-p111">On the **Custom Setup** page select the System Center options to be installed and then click **Next**. You should select **Management Server**, **User Interfaces**, and **Web Console** to be installed. **Database** should not be selected and should not be installed.</span></span>

9.  <span data-ttu-id="fb65c-163">Nella pagina dell' **istanza del server database SC** verificare che il nome del computer in cui sono installati i database di Operations Manager sia visualizzato nella casella **server database System Center** .</span><span class="sxs-lookup"><span data-stu-id="fb65c-163">On the **SC Database Server Instance** page, verify that the name of the computer where the Operations Manager databases are installed appears in the **System Center Database Server** box.</span></span> <span data-ttu-id="fb65c-164">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-164">Click **Next**.</span></span>

10. <span data-ttu-id="fb65c-p113">Nella pagina **Account azione server di gestione** selezionare **Dominio o account computer locale** e immettere i valori appropriati nelle caselle **Account utente**, **Password** e **Dominio o computer locale**. Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-p113">On the **Management Server Action Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes. Click **Next**.</span></span>

11. <span data-ttu-id="fb65c-p114">Nella pagina **SDK e account servizio di configurazione** selezionare **Dominio o account computer locale** e immettere i valori appropriati nelle caselle **Account utente**, **Password** e **Dominio o computer locale**. Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-p114">On the **SDK and Config Service Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes. Click **Next**.</span></span>

12. <span data-ttu-id="fb65c-169">Nella pagina **Segnalazioni errori di Operations Manager** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-169">On the **Operations Manager Error Reports** page click **Next**.</span></span>

13. <span data-ttu-id="fb65c-170">Nella pagina **Analisi utilizzo software** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-170">On the **Customer Experience Improvement Program** page click **Next**.</span></span>

14. <span data-ttu-id="fb65c-171">Nella pagina **Installazione del programma** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-171">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="fb65c-172">Nella pagina finale dell'**Installazione di System Center Operations Manager** deselezionare le caselle di controllo **Backup chiave di crittografia** e **Avvia console**, quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-172">On the **Completing the System Center Operations Manager Setup** page, clear the **Backup Encryption Key** and **Start the console checkboxes** and then click **Finish**.</span></span>

16. <span data-ttu-id="fb65c-173">Nel programma di installazione di System Center Operations Manager fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-173">In System Center Operations Manager Setup click **Exit**.</span></span>

</div>

<div>

## <a name="installing-system-center-reporting-services"></a><span data-ttu-id="fb65c-174">Installazione di System Center Reporting Services</span><span class="sxs-lookup"><span data-stu-id="fb65c-174">Installing System Center Reporting Services</span></span>

<span data-ttu-id="fb65c-175">Dopo aver installato e configurato la console di System Center Operations Manager, è necessario installare System Center Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="fb65c-175">After installing and configuring the System Center Operations Manager console you must then install System Center Reporting Services.</span></span> <span data-ttu-id="fb65c-176">Se si utilizza SQL Server 2008 R2 come database back-end di Operations Manager, significa che è innanzitutto necessario apportare una modifica temporanea al gruppo di sicurezza associato a SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="fb65c-176">If you are using SQL Server 2008 R2 as your Operations Manager back-end database, that means that you must first make a temporary change to the security group associated with SQL Server Reporting Services.</span></span> <span data-ttu-id="fb65c-177">Se si utilizza SQL Server 2008 R2, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb65c-177">If you are using SQL Server 2008 R2, you must do the following:</span></span>

1.  <span data-ttu-id="fb65c-178">Fare clic su **Start**, scegliere **Strumenti di amministrazione**, quindi **Server Manager**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-178">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="fb65c-179">In Server Manager espandere **Configurazione** e **Utenti e gruppi locali**, quindi fare clic su **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-179">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="fb65c-180">Individuare il gruppo seguente, in cui ATL-SC-001 rappresenta il nome del computer e ARCHINST rappresenta l'istanza di SQL Server per il database System Center: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10 \_ 50. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-180">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the System Center database: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

4.  <span data-ttu-id="fb65c-181">Fare clic con il pulsante destro del mouse sul gruppo e quindi scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-181">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="fb65c-182">Rinominare il gruppo eliminando \*\* \_ 50\*\* dal nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="fb65c-182">Rename the group by deleting **\_50** from the group name.</span></span> <span data-ttu-id="fb65c-183">Ad esempio: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-183">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

5.  <span data-ttu-id="fb65c-184">Chiudere Server Manager.</span><span class="sxs-lookup"><span data-stu-id="fb65c-184">Close Server Manager.</span></span>

<span data-ttu-id="fb65c-p117">A questo punto è possibile installare System Center Reporting Services. Procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="fb65c-p117">At this point you are ready to install System Center Reporting Services. To do this:</span></span>

1.  <span data-ttu-id="fb65c-187">Nel supporto di installazione di System Center Operations Manager 2007 R2 fare doppio clic su **SetupOM.exe**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-187">On the System Center Operations Manager 2007 R2 Setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="fb65c-188">In System Center Operations Manager 2007 R2 Setup fare clic su **Install Operations Manager Reporting**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-188">In System Center Operations Manager 2007 R2 Setup, click **Install Operations Manager Reporting**.</span></span>

3.  <span data-ttu-id="fb65c-189">Nell'installazione guidata di Reporting System Center Operations Manager 2007 R2, nella pagina **installazione report di Operations Manager** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-189">In the System Center Operations Manager 2007 R2 Reporting Setup wizard, on the **Welcome to Operations Manager Reporting Setup** page, click **Next**.</span></span>

4.  <span data-ttu-id="fb65c-190">Nella pagina **Contratto di licenza con l'utente finale** selezionare **Accetto i termini del Contratto di licenza** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-190">On the **End-user License Agreement** page select **I accept the terms of the license agreement** and then click **Next**.</span></span>

5.  <span data-ttu-id="fb65c-191">Nella pagina **Registrazione prodotto** verificare che nelle caselle **Nome utente** e **Organizzazione** siano presenti il proprio nome e il nome dell'organizzazione, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-191">On the **Product Registration** page, ensure that your name and the name of your organization appear in the **User Name** and **Organization** boxes and then click **Next**.</span></span>

6.  <span data-ttu-id="fb65c-p118">Nella pagina **Installazione personalizzata** fare clic su **Server di report** e selezionare **Il componente e tutti i componenti secondari verranno installati sul disco rigido locale**. Fare clic su **Data warehouse** e selezionare **Il componente non sarà disponibile**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-p118">On the **Custom Setup** page, click **Reporting Server** and select **This component, and all dependent components, will be installed on local disk drive**. Click **Data Warehouse** and select **This component will not be available**, and then click **Next**.</span></span>

7.  <span data-ttu-id="fb65c-194">Nella pagina **Connetti al server di gestione principale** digitare il nome del server di gestione principale di Operations Manager nella casella **Server di gestione principale** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-194">On the **Connect to the Root Management Server** page, type the name of your Operations Manager root management server in the **Root Management Server** box and then click **Next**.</span></span>

8.  <span data-ttu-id="fb65c-p119">Nella pagina **Connetti al data warehouse Operations Manager**, nella casella **Istanza di SQL Server**, digitare l'istanza di SQL Server in cui si trova il data warehouse (se il data warehouse si trova nell'istanza predefinita, è sufficiente digitare il nome del server, ad esempio atl-sql-001). Verificare che nella casella **Nome** sia riportato il nome **OperationsManagerDW** e che nella casella **Porta SQL Server** sia presente **1433**. Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-p119">On the **Connect to the Operations Manager Data Warehouse** page, type the SQL Server instance where your data warehouse is located in the **SQL Server Instance** box. (If your data warehouse is located in the Default instance then simply type the server name; for example: atl-sql-001.) Verify that the database name **OperationsManagerDW** appears in the **Name** box, and that port **1433** appears in the **SQL Server port** box. Click **Next**.</span></span>

9.  <span data-ttu-id="fb65c-198">Nella pagina **Istanza di SQL Server Reporting Services** selezionare il server di report di SQL Server nell'elenco a discesa **Immettere il server SQL Server Reporting Services** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-198">On the **SQL Server Reporting Instance** page, select your SQL Server reporting server from the **Enter the SQL Server Reporting Services Server** dropdown list and then click **Next**.</span></span>

10. <span data-ttu-id="fb65c-p120">Nella pagina **Account scrittura data warehouse**, nelle caselle **Account utente** e **Password** immettere il nome e la password dell'utente a cui assegnare inizialmente le autorizzazioni di scrittura per il data warehouse. Selezionare il dominio dell'utente nell'elenco a discesa **Dominio** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-p120">On the **Data Warehouse Write Account** page, enter the name and password of the user to be initially assigned write permissions to the data warehouse in the **User Account** and **Password** boxes. Select the user's domain from the **Domain** dropdown list and then click **Next**.</span></span>

11. <span data-ttu-id="fb65c-p121">Nella pagina **Account lettore dati**, nelle caselle **Account utente** e **Password** immettere il nome utente e la password dell'account utente da utilizzare per le query di SQL Reporting Services sul data warehouse. Selezionare il dominio dell'account nell'elenco a discesa **Dominio** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-p121">On the **Data Reader Account** page, enter the name and password of the user account to be used when SQL Reporting Services queries the data warehouse in the **User Account** and **Password** boxes. Select the account domain from the **Domain** dropdown list and then click **Next**.</span></span>

12. <span data-ttu-id="fb65c-203">Nella pagina **Rapporti dati operativi** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-203">On the **Operational Data Reports** page, click **Next**.</span></span>

13. <span data-ttu-id="fb65c-204">Nella pagina **Microsoft Update**fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-204">On the **Microsoft Update** page, click **Next**.</span></span>

14. <span data-ttu-id="fb65c-205">Nella pagina **Installazione del programma** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-205">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="fb65c-206">Nella pagina **Completamento dell'installazione guidata componenti di report di Operations Manager** fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-206">On the **Completing the Operations Manager Reporting Components Setup Wizard** page, click **Finish**.</span></span>

16. <span data-ttu-id="fb65c-207">In System Center Operations Manager 2007 R2 Setup fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-207">In System Center Operations Manager 2007 R2 Setup, click **Exit**.</span></span>

<span data-ttu-id="fb65c-208">Dopo aver installato i report di System Center, utilizzare la procedura seguente per reimpostare il nome del gruppo di sicurezza associato ai report di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fb65c-208">After System Center reporting has been installed you then use the following procedure to reset the name of the security group associated with SQL Server reporting.</span></span> <span data-ttu-id="fb65c-209">Questa procedura è di nuovo obbligatoria solo se si utilizza SQL Server:</span><span class="sxs-lookup"><span data-stu-id="fb65c-209">Again, this procedure is only required if you are using SQL Server:</span></span>

1.  <span data-ttu-id="fb65c-210">Fare clic su **Start**, scegliere **Strumenti di amministrazione**, quindi **Server Manager**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-210">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="fb65c-211">In Server Manager espandere **Configurazione** e **Utenti e gruppi locali**, quindi fare clic su **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-211">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="fb65c-212">Individuare il gruppo seguente, in cui ATL-SC-001 rappresenta il nome del computer e ARCHINST rappresenta l'istanza di SQL Server per i database di archiviazione e monitoraggio: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-212">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the archiving and monitoring databases: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

4.  <span data-ttu-id="fb65c-213">Fare clic con il pulsante destro del mouse sul gruppo e quindi scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-213">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="fb65c-214">Rinominare il gruppo aggiungendo \*\* \_ 50\*\* alla fine del nome del gruppo, subito prima del nome dell'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fb65c-214">Rename the group by adding **\_50** to the end of the group name, right before the SQL Server instance name.</span></span> <span data-ttu-id="fb65c-215">Ad esempio: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10 \_ 50. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-215">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

5.  <span data-ttu-id="fb65c-216">Chiudere Server Manager.</span><span class="sxs-lookup"><span data-stu-id="fb65c-216">Close Server Manager.</span></span>

<span data-ttu-id="fb65c-p124">Se la Console operatore di System Center è aperta, è necessario chiudere l'applicazione e riavviarla, altrimenti la scheda **Report** non comparirà nell'interfaccia utente della Console operatore. Tenere presente che, dopo il primo riavvio della Console operatore, è possibile che siano necessari alcuni minuti perché vengano visualizzati tutti i report di monitoraggio nella scheda **Report**.</span><span class="sxs-lookup"><span data-stu-id="fb65c-p124">If the System Center Operations Console is open you will need to close the application and then restart it; if you do not do this the **Reporting** tab will not appear in the Operations Console user interface. Note that, after restarting the Operations Console the first time, it could take several minutes before all the Monitoring Reports appear on the **Reporting** tab.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

