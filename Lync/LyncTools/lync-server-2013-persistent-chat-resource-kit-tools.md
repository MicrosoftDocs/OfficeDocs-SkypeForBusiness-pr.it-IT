---
title: Strumenti del Resource Kit di chat persistenti di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c851be7bb7046021cc2d37c88ef03bdea60c95a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a><span data-ttu-id="4075a-102">Strumenti del Resource Kit di chat persistenti di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4075a-102">Lync Server 2013 Persistent Chat Resource Kit Tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4075a-103">_**Argomento Ultima modifica:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="4075a-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="4075a-104">Gli strumenti di Resource Kit di chat persistenti di Lync Server 2013 consentono di semplificare le attività di routine per gli amministratori IT che distribuiscono e gestiscono il server di chat persistente di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4075a-104">The Lync Server 2013 Persistent Chat Resource Kit tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013 Persistent Chat Server.</span></span> <span data-ttu-id="4075a-105">Oltre alle istruzioni per l'installazione, questo argomento descrive lo scopo di ogni strumento e gli esempi del relativo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="4075a-105">In addition to installation instructions, this topic describes the purpose of each tool, and examples of its use.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="4075a-106">Installazione degli strumenti del Resource Kit</span><span class="sxs-lookup"><span data-stu-id="4075a-106">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="4075a-107">Per installare Lync Server 2013, strumenti Resource Kit, scaricare **PersistentChatReskit. msi**.</span><span class="sxs-lookup"><span data-stu-id="4075a-107">To install the Lync Server 2013, Resource Kit Tools, download **PersistentChatReskit.msi**.</span></span> <span data-ttu-id="4075a-108">Eseguire **PersistentChatReskit. msi** per eseguire un'installazione semplice.</span><span class="sxs-lookup"><span data-stu-id="4075a-108">Run **PersistentChatReskit.msi** to do a simple installation.</span></span> <span data-ttu-id="4075a-109">Il file \\con estensione msi installa tutti gli strumenti disponibili nel percorso seguente: \*\*programmi Microsoft Lync Server\\2013 Persistent Chat Server Resource Kit.\\ \*\*</span><span class="sxs-lookup"><span data-stu-id="4075a-109">The .msi installs all the tools in the following path: \\**Program Files\\ Microsoft Lync Server 2013\\Persistent Chat Server Resource Kit**.</span></span> <span data-ttu-id="4075a-110">Gli strumenti che sono eseguibili indipendenti si trovano in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="4075a-110">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="4075a-111">Gli strumenti che includono anche i file sono presenti nelle sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="4075a-111">Tools that also have files are in their own subfolders.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4075a-112">Dopo l'installazione di Lync Server 2013, strumenti Resource Kit, è necessario installare <STRONG>psexec. exe</STRONG> e copiare <STRONG>psexec. exe</STRONG> nel percorso seguente: \\ <STRONG>file di programma \ Microsoft Lync Server 2013 \ Persistent Chat Server Resource Kit\ChatStressTool</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4075a-112">After installing the Lync Server 2013, Resource Kit Tools, you must install <STRONG>PsExec.exe</STRONG> and copy <STRONG>PsExec.exe</STRONG> to the following path: \\<STRONG>Program Files\ Microsoft Lync Server 2013\Persistent Chat Server Resource Kit\ChatStressTool</STRONG>.</span></span> <span data-ttu-id="4075a-113">Se non si copia <STRONG>psexec. exe</STRONG>, lo strumento di stress della chat persistente genererà un'eccezione di errore e non verrà eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="4075a-113">If you do not copy <STRONG>PsExec.exe</STRONG>, the Persistent Chat Stress Tool will throw an error exception, and not perform correctly.</span></span> <span data-ttu-id="4075a-114">Verificare di soddisfare questo requisito preliminare prima di eseguire lo strumento.</span><span class="sxs-lookup"><span data-stu-id="4075a-114">Make sure that you meet this prerequisite requirement prior to running the tool.</span></span> <span data-ttu-id="4075a-115">Per informazioni dettagliate sull'installazione di <STRONG>psexec. exe</STRONG>, vedere <A href="http://go.microsoft.com/fwlink/p/?linkid=282246">http://go.microsoft.com/fwlink/p/?LinkId=282246</A>.</span><span class="sxs-lookup"><span data-stu-id="4075a-115">For details about installing <STRONG>PsExec.exe</STRONG>, see <A href="http://go.microsoft.com/fwlink/p/?linkid=282246">http://go.microsoft.com/fwlink/p/?LinkId=282246</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="4075a-116">Ambienti supportati</span><span class="sxs-lookup"><span data-stu-id="4075a-116">Supported Environments</span></span>

<span data-ttu-id="4075a-117">Per ottenere prestazioni ottimali, gli strumenti di Lync Server 2013, Resource Kit devono essere installati nello stesso ambiente e con le stesse specifiche necessarie per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4075a-117">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="4075a-118">Panoramica degli strumenti di Resource Kit</span><span class="sxs-lookup"><span data-stu-id="4075a-118">Resource Kit Tools Overview</span></span>

<span data-ttu-id="4075a-119">Ecco gli strumenti disponibili nel Resource Kit di Lync Server 2013 Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="4075a-119">Here are the tools that are provided in the Lync Server 2013 Persistent Chat Resource Kit.</span></span> <span data-ttu-id="4075a-120">La sezione seguente fornisce una descrizione di ogni strumento, inclusi i requisiti e l'utilizzo di esempio.</span><span class="sxs-lookup"><span data-stu-id="4075a-120">The following section provides a description of each tool, including requirements and example usage.</span></span>

  - <span data-ttu-id="4075a-121">AffCheck</span><span class="sxs-lookup"><span data-stu-id="4075a-121">AffCheck</span></span>

  - <span data-ttu-id="4075a-122">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="4075a-122">ChatMonitoringSummary</span></span>

  - <span data-ttu-id="4075a-123">Strumento ChatStress</span><span class="sxs-lookup"><span data-stu-id="4075a-123">ChatStress Tool</span></span>

  - <span data-ttu-id="4075a-124">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="4075a-124">ChatUpgradeVerifier</span></span>

  - <span data-ttu-id="4075a-125">ChatUsageReport</span><span class="sxs-lookup"><span data-stu-id="4075a-125">ChatUsageReport</span></span>

  - <span data-ttu-id="4075a-126">ScheduleADSyncforPrincipal</span><span class="sxs-lookup"><span data-stu-id="4075a-126">ScheduleADSyncforPrincipal</span></span>

</div>

<div>

## <a name="affcheck"></a><span data-ttu-id="4075a-127">AffCheck</span><span class="sxs-lookup"><span data-stu-id="4075a-127">AffCheck</span></span>

<div>

## <a name="description"></a><span data-ttu-id="4075a-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4075a-128">Description</span></span>

<span data-ttu-id="4075a-129">Lo strumento AffCheck conferma che l'utente del database back-end della chat persistente e i record di affiliazione del gruppo corrispondono a quelli dei servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4075a-129">The AffCheck tool confirms that the Persistent Chat back-end database user and group affiliation records match that of Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="4075a-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4075a-130">Requirements</span></span>

<span data-ttu-id="4075a-131">Lo strumento viene installato con il programma di installazione di PersistentChatResKit in un computer unito a un dominio.</span><span class="sxs-lookup"><span data-stu-id="4075a-131">The tool is installed with the PersistentChatResKit installer on a domain joined machine.</span></span>

<span data-ttu-id="4075a-132">L'account utente in cui viene eseguito lo strumento deve avere accesso in lettura al database back-end della chat persistente e ai servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4075a-132">The user account under which the tool is run must have Read access to the Persistent Chat back-end database and Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="4075a-133">L'uso</span><span class="sxs-lookup"><span data-stu-id="4075a-133">Usage</span></span>

<span data-ttu-id="4075a-134">Configura il file AffCheck. exe. config in base alle istruzioni nel file di configurazione ed Esegui lo strumento AffCheck senza parametri della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="4075a-134">Configure the AffCheck.exe.config file according to the instructions in the config file and run the AffCheck tool without command-line parameters.</span></span> <span data-ttu-id="4075a-135">Di seguito sono riportati i contenuti dell'impostazione predefinita AffCheck. exe. config.</span><span class="sxs-lookup"><span data-stu-id="4075a-135">Following are the contents of the default AffCheck.exe.config.</span></span>

<span data-ttu-id="4075a-136">**AffCheck. exe. config:**</span><span class="sxs-lookup"><span data-stu-id="4075a-136">**AffCheck.exe.config:**</span></span>

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
        <!--Domain Controller IP Address-->
        <add key="LDAP" value="LDAP://0.0.0.0/"/>
        
        <!-- Domain DN  This is case sensitive, it must match exactly-->
        <add key="DomainComponent" value ="DC=DOMAIN,DC=COM"/>
        
        <!--Domain Administrator Login and Password-->
        <add key="DomainLogin" value="DOMAIN\Administrator"/>
        <add key="DomainPassword" value ="password"/>
        
        <!-- Connection string to Group Chat Database-->
        <add key="ConnectionString" value="data source=SQL_SERVER\INSTANCE;initial catalog=DATABASE_NAME;integrated security=SSPI"/>
        
        <!--Check group affiliations-->
        <add key="CheckGroups" value="true"/>
        
        <!--Check user affilations-->
        <add key="CheckUsers" value="true"/>
        
        <!--List all affiliations if there is a mismatch between database and active directory-->
        <add key="ListAffiliations" value="true"/>
    
        <!--If you need to offset the results of the number of affilations in AD(can be negative to add to AD parent count)-->
        <add key="Offset" value ="0"/>
    
        <!--If you need to ignore certain parents, provide a semi colon delimitted list.-->
        <add key="Ignore" value ="DC=uatest,DC=test,DC=contoso,DC=com;DC=test,DC=contoso,DC=com"/>
      </appSettings>
    </configuration>
  ```
</div>

</div>

<div>

## <a name="chatmonitoringsummary"></a><span data-ttu-id="4075a-137">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="4075a-137">ChatMonitoringSummary</span></span>

<div>

## <a name="description"></a><span data-ttu-id="4075a-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4075a-138">Description</span></span>

<span data-ttu-id="4075a-139">Lo strumento PersistentChatMonitoringSummary sposta le informazioni di monitoraggio della chat persistente dal database di monitoraggio in un file di log CSV specificato.</span><span class="sxs-lookup"><span data-stu-id="4075a-139">The PersistentChatMonitoringSummary tool moves Persistent Chat monitoring information from the monitoring database into a specified CSV log file.</span></span>

<span data-ttu-id="4075a-140">Il file CSV conterrà una ripartizione delle sessioni di chat persistenti in base al numero di sessioni totali, sessioni di successo, errori imprevisti, errori previsti e una ripartizione degli errori imprevisti per ID diagnostica, numero di errori e Descrizione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="4075a-140">The CSV file will contain a breakdown of Persistent Chat sessions by number of total sessions, successful sessions, unexpected failures, expected failures, and a breakdown of the unexpected failures by diagnostic ID, number of failures, and failure description.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="4075a-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4075a-141">Requirements</span></span>

<span data-ttu-id="4075a-142">Installare gli strumenti del Resource Kit della chat persistente in un computer collegato al dominio che abbia accesso al database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="4075a-142">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Monitoring database.</span></span>

<span data-ttu-id="4075a-143">L'account utente in cui viene eseguito lo strumento deve avere accesso in lettura al database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="4075a-143">The user account under which the tool runs must have Read access to the Monitoring database.</span></span>

<span data-ttu-id="4075a-144">Il file PersistentChatMonitoringSummary. exe. config deve contenere una \<sezione connectionStrings\> che definisce la stringa di connessione al database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="4075a-144">The file, PersistentChatMonitoringSummary.exe.config, must contain a \<connectionStrings\> section that defines the connection string to the Monitoring database.</span></span> <span data-ttu-id="4075a-145">Deve inoltre contenere una chiave per il PersistentChatEndpointUri in cui verranno raccolti i dati di monitoraggio e un percorso di file in una posizione per il file CSV che verrà generato.</span><span class="sxs-lookup"><span data-stu-id="4075a-145">It must also contain a key for the PersistentChatEndpointUri that the monitoring data will be gathered for, and a file path to a location for the CSV file that will be generated.</span></span> <span data-ttu-id="4075a-146">Per gli esempi, vedere il file di configurazione installato.</span><span class="sxs-lookup"><span data-stu-id="4075a-146">Refer to the installed config file for examples.</span></span> <span data-ttu-id="4075a-147">Il file deve trovarsi nella stessa directory dello strumento.</span><span class="sxs-lookup"><span data-stu-id="4075a-147">The file must be located in the same directory as the tool.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="4075a-148">L'uso</span><span class="sxs-lookup"><span data-stu-id="4075a-148">Usage</span></span>

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

<span data-ttu-id="4075a-149">Questi parametri definiscono la selezione dei dati:</span><span class="sxs-lookup"><span data-stu-id="4075a-149">These parameters define the selection of data:</span></span>

<span data-ttu-id="4075a-150">**StartDateTime:** Facoltativamente, specifica la data di inizio del periodo di selezione.</span><span class="sxs-lookup"><span data-stu-id="4075a-150">**StartDateTime:** Optionally specifies the start date of the selection period.</span></span> <span data-ttu-id="4075a-151">Impostazione predefinita: 1/1/1753 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="4075a-151">Default: 1/1/1753 12:00:00 AM</span></span>

<span data-ttu-id="4075a-152">**EndDateTime:** Facoltativamente, specifica l'ultima data del periodo di selezione.</span><span class="sxs-lookup"><span data-stu-id="4075a-152">**EndDateTime:** Optionally specifies the last date of the selection period.</span></span> <span data-ttu-id="4075a-153">Impostazione predefinita: ora</span><span class="sxs-lookup"><span data-stu-id="4075a-153">Default: Now</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="4075a-154">Esempio</span><span class="sxs-lookup"><span data-stu-id="4075a-154">Example</span></span>

```Batch
    C:\Users\Administrator.VDOMAIN>Desktop\PersistentChatMonitoringSummary.exe
    Reading database connection information, Persistent Chat endpoint uri, and csv output path information from the application config file...
    Connecting to Monitoring database with connection string specified in the application config file...
    Gathering Persistent Chat Session Summary information between "1/1/1753 12:00:00 AM" and "11/19/2012 10:11:25 AM" for Persistent Chat Endpoint Uri "persistentChatEndpointUri@domain.com"...
    Press enter to continue or hit ctr-c if these settings are incorrect...
    
    The summary information about Persistent Chat sessions from the Monitoring database has been output to C:\PersistentChatMonitoring_dd4ace24-4c8a-4a3d-8fd4-591bdfacf47b.csv
    Press enter to exit...
```

</div>

</div>

<div>

## <a name="persistent-chat-stress-tool"></a><span data-ttu-id="4075a-155">Strumento di stress per la chat persistente</span><span class="sxs-lookup"><span data-stu-id="4075a-155">Persistent Chat Stress Tool</span></span>

<div>

## <a name="description"></a><span data-ttu-id="4075a-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4075a-156">Description</span></span>

<span data-ttu-id="4075a-157">Lo strumento di stress per la chat persistente offre un modo semplice per simulare l'uso della chat persistente per testare le prestazioni reali, inclusi i vari modelli di utenti per adattarsi meglio agli scenari di utilizzo previsti.</span><span class="sxs-lookup"><span data-stu-id="4075a-157">The Persistent Chat Stress tool provides an easy way to simulate usage of Persistent Chat to test real-world performance, including varied user models to better fit your expected usage scenarios.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="4075a-158">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4075a-158">Requirements</span></span>

<span data-ttu-id="4075a-159">Installare gli strumenti del Resource Kit di chat persistenti in un computer collegato al dominio che abbia accesso al database back-end della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4075a-159">Install the Persistent Chat Resource Kit tools onto a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="4075a-160">Oltre a questo *controller* , è necessario disporre di diversi computer di *caricamento* .</span><span class="sxs-lookup"><span data-stu-id="4075a-160">In addition to this *controller* machine, you will need several *loader* machines.</span></span> <span data-ttu-id="4075a-161">Per tutti gli utenti di 10K nel modello utente, è necessario almeno 4GB di RAM gratuita in un caricatore.</span><span class="sxs-lookup"><span data-stu-id="4075a-161">For every 10K users in your user model, you will need at least 4GB of free RAM on a loader machine.</span></span> <span data-ttu-id="4075a-162">Ad esempio, una corsa con gli utenti di 80K richiederà circa 32GB di RAM distribuiti in tutti i computer Loader.</span><span class="sxs-lookup"><span data-stu-id="4075a-162">For example, a run with 80K users will require about 32GB of RAM spread across all loader machines.</span></span> <span data-ttu-id="4075a-163">È consigliabile disporre di almeno tre computer loader, indipendentemente dal carico previsto.</span><span class="sxs-lookup"><span data-stu-id="4075a-163">We recommend that you have at least three loader machines, regardless of expected load.</span></span>

<span data-ttu-id="4075a-164">I computer Loader devono avere il Framework .NET 4,5 e l'installazione di Visual C++ 2012 ridistribuibile.</span><span class="sxs-lookup"><span data-stu-id="4075a-164">Loader machines must have the .NET 4.5 Framework as well as the Visual C++ 2012 Redistributable installed.</span></span>

</div>

<div>

## <a name="configuration"></a><span data-ttu-id="4075a-165">Configurazione</span><span class="sxs-lookup"><span data-stu-id="4075a-165">Configuration</span></span>

<span data-ttu-id="4075a-166">Copiare i file di ChatStressTool in una cartella condivisa accessibile da tutti i computer Loader.</span><span class="sxs-lookup"><span data-stu-id="4075a-166">Copy ChatStressTool files into a shared folder accessible from all loader machines.</span></span>

<span data-ttu-id="4075a-167">Creare utenti e canali da usare durante l'esecuzione della sollecitazione:</span><span class="sxs-lookup"><span data-stu-id="4075a-167">Create users and channels for use in the stress run:</span></span>

  - <span data-ttu-id="4075a-168">Consente di creare il numero di utenti che richiede il modello utente, abilitarli per Lync e impostare i criteri di persistenza della chat su Enabled.</span><span class="sxs-lookup"><span data-stu-id="4075a-168">Create as many users as your user model calls for, enable them for Lync, and set their Persistent Chat policy to Enabled.</span></span>

  - <span data-ttu-id="4075a-169">Creare una categoria per i canali di stress e quindi creare il numero di sale necessario in tale categoria.</span><span class="sxs-lookup"><span data-stu-id="4075a-169">Create a category for your stress channels, and then create as many rooms as are needed under that category.</span></span> <span data-ttu-id="4075a-170">La categoria dovrebbe avere tutti gli utenti di stress nell'elenco **consentiti** (tramite l'aggiunta della propria UO) e le sale di stress dovrebbero avere un'impostazione di privacy **aperta**.</span><span class="sxs-lookup"><span data-stu-id="4075a-170">The category should have all stress users in its **Allowed** list (by way of adding their OU), and stress rooms should have a privacy setting of **Open**.</span></span>

  - <span data-ttu-id="4075a-171">È consigliabile creare sale di stress extra.</span><span class="sxs-lookup"><span data-stu-id="4075a-171">We recommend creating extra stress rooms.</span></span> <span data-ttu-id="4075a-172">È possibile creare sale di 50.000 con il comando di interfaccia della riga di comando di Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="4075a-172">You can create 50,000 rooms with the following Windows PowerShell command-line interface command:</span></span>
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

<span data-ttu-id="4075a-173">Modificare i file di configurazione per adattarli alla topologia:</span><span class="sxs-lookup"><span data-stu-id="4075a-173">Edit the configuration files to fit your topology:</span></span>

<span data-ttu-id="4075a-174">In **LoaderProcess. exe. config**modificare "controller.contoso.com" con il nome di dominio completo (FQDN) del computer del controller.</span><span class="sxs-lookup"><span data-stu-id="4075a-174">In **LoaderProcess.exe.config**, change “controller.contoso.com” to the controller machine’s fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="4075a-175">In **StressLauncher. exe. config:**</span><span class="sxs-lookup"><span data-stu-id="4075a-175">In **StressLauncher.exe.config:**</span></span>

1.  <span data-ttu-id="4075a-176">Modificare il valore dell'impostazione "LoaderBinary" nel percorso della cartella condivisa.</span><span class="sxs-lookup"><span data-stu-id="4075a-176">Change the “LoaderBinary” setting value to the shared folder’s path.</span></span>

2.  <span data-ttu-id="4075a-177">Modificare "AdminUser"/"AdminPassword" in credenziali con accesso amministratore ai computer Loader.</span><span class="sxs-lookup"><span data-stu-id="4075a-177">Change “AdminUser”/”AdminPassword” to credentials that have admin access to loader machines.</span></span>

3.  <span data-ttu-id="4075a-178">Modificare "ChannelCategory" con il nome della categoria in cui sono stati creati i canali di sollecitazione.</span><span class="sxs-lookup"><span data-stu-id="4075a-178">Change “ChannelCategory” to the name of the category that stress channels have been created under.</span></span>

4.  <span data-ttu-id="4075a-179">Modificare "UserNamePattern" e "UserPasswordPattern" in un modello che corrisponda alle credenziali utente di stress.</span><span class="sxs-lookup"><span data-stu-id="4075a-179">Change “UserNamePattern” and “UserPasswordPattern” to a template that matches your stress user credentials.</span></span> <span data-ttu-id="4075a-180">{0}viene sostituito con il numero di indice dell'utente.</span><span class="sxs-lookup"><span data-stu-id="4075a-180">{0} is replaced with the user’s index number.</span></span>

5.  <span data-ttu-id="4075a-181">Modificare "Domain" nel dominio SIP della topologia di test.</span><span class="sxs-lookup"><span data-stu-id="4075a-181">Change “Domain” to the SIP domain of your test topology.</span></span>

6.  <span data-ttu-id="4075a-182">Modificare "ConnectionString" in una stringa di connessione per il database back-end della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4075a-182">Change “ConnectionString” to a connection string for your Persistent Chat back-end database.</span></span>

7.  <span data-ttu-id="4075a-183">Modificare "UserIndexStart" con l'indice del primo utente di stress.</span><span class="sxs-lookup"><span data-stu-id="4075a-183">Change “UserIndexStart” to the index of the first stress user.</span></span>

8.  <span data-ttu-id="4075a-184">Modificare "LyncFQDN" con il nome di dominio completo del pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="4075a-184">Change “LyncFQDN” to the FQDN of your Front End pool.</span></span>

9.  <span data-ttu-id="4075a-185">Modificare l'elenco "macchine" per includere i nomi dei computer per tutti i computer del caricatore.</span><span class="sxs-lookup"><span data-stu-id="4075a-185">Modify the “Machines” list to include machine names for all of your loader machines.</span></span>

10. <span data-ttu-id="4075a-186">Modificare il baseAddress dell'endpoint del servizio (il valore predefinito è "controller.contoso.com") con il nome di dominio completo del computer del controller.</span><span class="sxs-lookup"><span data-stu-id="4075a-186">Change the baseAddress of the service endpoint (default is “controller.contoso.com”) to the FQDN of your controller machine.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="4075a-187">L'uso</span><span class="sxs-lookup"><span data-stu-id="4075a-187">Usage</span></span>

<span data-ttu-id="4075a-188">Al termine della configurazione, aprire StressLauncher. exe nel computer del controller.</span><span class="sxs-lookup"><span data-stu-id="4075a-188">After configuration is complete, open StressLauncher.exe on the controller machine.</span></span> <span data-ttu-id="4075a-189">Puoi avviare StressLauncher come qualsiasi utente.</span><span class="sxs-lookup"><span data-stu-id="4075a-189">You can launch StressLauncher as any user.</span></span> <span data-ttu-id="4075a-190">Le credenziali in cui vengono avviati i processi del caricatore nei computer Loader devono essere specificate nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4075a-190">The credentials under which the loader processes start on the loader machines must be specified in the config file.</span></span> <span data-ttu-id="4075a-191">Devi anche fornire una stringa di connessione che abbia accesso in lettura al database back-end della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4075a-191">You also must give a connection string that has Read access to the Persistent Chat back-end database.</span></span> <span data-ttu-id="4075a-192">Se la stringa di connessione usa l'autenticazione integrata di Windows, è necessario avviare StressLauncher come utente con questo accesso.</span><span class="sxs-lookup"><span data-stu-id="4075a-192">If this connection string uses integrated Windows authentication, you must launch StressLauncher as a user that has this access.</span></span>

<span data-ttu-id="4075a-193">Modificare le impostazioni del modello utente in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="4075a-193">Alter the user model settings as needed.</span></span> <span data-ttu-id="4075a-194">Fare clic su **Avvia caricamento** per avviare una corsa.</span><span class="sxs-lookup"><span data-stu-id="4075a-194">Click **Start Load** to initiate a run.</span></span> <span data-ttu-id="4075a-195">Dopo un minuto o giù di lì, gli utenti inizieranno a essere connessi e l'indicatore di stato inizierà a riempirsi.</span><span class="sxs-lookup"><span data-stu-id="4075a-195">After a minute or so, users will start being signed in, and the progress bar will begin to fill.</span></span> <span data-ttu-id="4075a-196">A questo punto, è possibile che la macchina di controllo funzioni e prenda misure di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="4075a-196">At this point, you may can the controller machine working and take performance measurements.</span></span>

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a><span data-ttu-id="4075a-197">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="4075a-197">ChatUpgradeVerifier</span></span>

<div>

## <a name="description"></a><span data-ttu-id="4075a-198">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4075a-198">Description</span></span>

<span data-ttu-id="4075a-199">ChatUpgradeVerifier è uno strumento di confronto di database specifico per la chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4075a-199">ChatUpgradeVerifier is a Persistent Chat specific database comparison tool.</span></span> <span data-ttu-id="4075a-200">Lo strumento confronta il database di Group Chat 2007 R2 o Group Chat 2010 (2007/2010Db) con il database Persistent Chat 2013 (2013Db).</span><span class="sxs-lookup"><span data-stu-id="4075a-200">The tool compares either the Group Chat 2007 R2 or Group Chat 2010 Database (2007/2010Db) to the Persistent Chat 2013 Database (2013Db).</span></span>

<span data-ttu-id="4075a-201">Lo strumento controllerà, uno alla volta, ogni categoria, chat room persistente e componente aggiuntivo in 2007/2010Db per vedere se viene visualizzato nel 2013Db.</span><span class="sxs-lookup"><span data-stu-id="4075a-201">The tool will check, one by one, each category, Persistent Chat room, and add-in in 2007/2010Db to see if it appears in the 2013Db.</span></span> <span data-ttu-id="4075a-202">Il confronto include il controllo di tutte le impostazioni della categoria, della chat room o del componente aggiuntivo, di tutte le entità nell'ambito della categoria e di qualsiasi entità di un ruolo nella categoria o nella chat room.</span><span class="sxs-lookup"><span data-stu-id="4075a-202">The comparison includes checking all settings on the category, chat room, or add-in, any principals in scope on the category, and any principal in a role on either the category or the chat room.</span></span> <span data-ttu-id="4075a-203">Se una categoria o una chat room non viene visualizzata correttamente in 2013Db, le differenze verranno restituite a un file Conflicts.</span><span class="sxs-lookup"><span data-stu-id="4075a-203">If a category or a chat room does not appear correctly in the 2013Db, the differences will be output to a conflicts file.</span></span> <span data-ttu-id="4075a-204">Se, dopo l'aggiornamento, il file 2007/2010Db viene modificato e quindi viene eseguito questo strumento, verrà visualizzato un output delle differenze per i conflitti.</span><span class="sxs-lookup"><span data-stu-id="4075a-204">If, after the upgrade has occurred, the 2007/2010Db is changed and then this tool is run, there will be a differences output to the conflicts file.</span></span> <span data-ttu-id="4075a-205">Tieni presente che questa applicazione è solo uno strumento di confronto di database e non convalida il processo di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="4075a-205">Note that this application is a database comparison tool only and does not validate the upgrade process.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="4075a-206">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4075a-206">Requirements</span></span>

<span data-ttu-id="4075a-207">Installare gli strumenti del Resource Kit della chat persistente in un computer collegato al dominio che abbia accesso ai database back-end della chat persistente (versioni precedenti e correnti per la chat persistente).</span><span class="sxs-lookup"><span data-stu-id="4075a-207">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end databases (previous and current versions for Persistent Chat).</span></span>

<span data-ttu-id="4075a-208">L'account utente in cui viene eseguito lo strumento deve avere accesso in lettura ai database della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4075a-208">The user account under which the tool runs must have Read access to the Persistent Chat databases.</span></span>

<span data-ttu-id="4075a-209">Il file ChatUpgradeVerifier. exe. config deve contenere il parametro GroupChat2007R2Db o il parametro GroupChat2010Db, con una stringa di connessione al database di chat di gruppo appropriato (GroupChat 2007R2 o 2010).</span><span class="sxs-lookup"><span data-stu-id="4075a-209">The ChatUpgradeVerifier.exe.config file must contain either the GroupChat2007R2Db parameter or the GroupChat2010Db parameter, with a connection string to the appropriate Group Chat database (either Groupchat 2007R2 or 2010).</span></span> <span data-ttu-id="4075a-210">Deve inoltre contenere un parametro PersistentChat2013Db, con una stringa di connessione al database della chat persistente di 2013.</span><span class="sxs-lookup"><span data-stu-id="4075a-210">It must also contain a PersistentChat2013Db parameter, with a connection string to the Persistent Chat 2013 database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="4075a-211">L'uso</span><span class="sxs-lookup"><span data-stu-id="4075a-211">Usage</span></span>

<span data-ttu-id="4075a-212">Eseguire **ChatUpgradeVerifier** senza parametri.</span><span class="sxs-lookup"><span data-stu-id="4075a-212">Run **ChatUpgradeVerifier** without any parameters.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="4075a-213">Esempio</span><span class="sxs-lookup"><span data-stu-id="4075a-213">Example</span></span>

<span data-ttu-id="4075a-214">![Eseguire ChatUpgradeVerifier. exe.] (images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Eseguire ChatUpgradeVerifier. exe.")</span><span class="sxs-lookup"><span data-stu-id="4075a-214">![Running ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Running ChatUpgradeVerifier.exe.")</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a><span data-ttu-id="4075a-215">Report sull'utilizzo della chat persistente</span><span class="sxs-lookup"><span data-stu-id="4075a-215">Persistent Chat Usage Report</span></span>

<div>

## <a name="description"></a><span data-ttu-id="4075a-216">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4075a-216">Description</span></span>

<span data-ttu-id="4075a-217">Lo strumento ChatUsageReport genera un report HTML di utilizzo del servizio chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4075a-217">The ChatUsageReport tool generates an HTML report of Persistent Chat service usage.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="4075a-218">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4075a-218">Requirements</span></span>

<span data-ttu-id="4075a-219">Installare gli strumenti del Resource Kit della chat persistente in un computer collegato al dominio che abbia accesso al database back-end della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4075a-219">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="4075a-220">L'account utente in cui viene eseguito lo strumento deve avere accesso in lettura al database back-end della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4075a-220">The user account under which the tool is run must have Read access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="4075a-221">Il file ChatUsageReport. exe. config deve contenere una \<sezione connectionStrings\> che definisce la stringa di connessione al database back-end della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4075a-221">The file, ChatUsageReport.exe.config, must contain a \<connectionStrings\> section defining the connection string to the Persistent Chat back-end database.</span></span> <span data-ttu-id="4075a-222">Il contenuto del file di configurazione predefinito è incluso qui, per il riferimento.</span><span class="sxs-lookup"><span data-stu-id="4075a-222">The contents of the default config file are included here, for your reference.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="4075a-223">L'uso</span><span class="sxs-lookup"><span data-stu-id="4075a-223">Usage</span></span>

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
<span data-ttu-id="4075a-224">Questi parametri definiscono la selezione dei dati:</span><span class="sxs-lookup"><span data-stu-id="4075a-224">These parameters define the selection of data:</span></span>

<span data-ttu-id="4075a-225">**StartDate:** Facoltativamente, specifica la data di inizio UTC del periodo di selezione.</span><span class="sxs-lookup"><span data-stu-id="4075a-225">**StartDate:** Optionally specifies the UTC start date of the selection period.</span></span> <span data-ttu-id="4075a-226">Impostazione predefinita: data meno recente</span><span class="sxs-lookup"><span data-stu-id="4075a-226">Default: Earliest Date</span></span>

<span data-ttu-id="4075a-227">**EndDate:** Facoltativamente, specifica la data di fine dell'ora UTC del periodo di selezione.</span><span class="sxs-lookup"><span data-stu-id="4075a-227">**EndDate:** Optionally specifies the UTC end date of the selection period.</span></span> <span data-ttu-id="4075a-228">Impostazione predefinita: ora</span><span class="sxs-lookup"><span data-stu-id="4075a-228">Default: Now</span></span>

<span data-ttu-id="4075a-229">Questi parametri definiscono la modalità e i dati visualizzati:</span><span class="sxs-lookup"><span data-stu-id="4075a-229">These parameters define how and what data is displayed:</span></span>

<span data-ttu-id="4075a-230">**TopActiveUsers:** Se specificato, il report includerà l'n utenti più attivi in termini di numero di messaggi pubblicati dall'utente nella chat room per il periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="4075a-230">**TopActiveUsers:** If this is specified, the report will include the n most active users in terms of the number of messages the user has posted in the chat room for the selected period.</span></span> <span data-ttu-id="4075a-231">Impostazione predefinita: 10</span><span class="sxs-lookup"><span data-stu-id="4075a-231">Default: 10</span></span>

<span data-ttu-id="4075a-232">**TopActiveRooms:** Se specificato, il report includerà la n chat room più attiva in termini di numero di messaggi pubblicati nella sala per il periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="4075a-232">**TopActiveRooms:** If this is specified, the report will include the n most active chat rooms in terms of the number of messages posted in the room for the selected period.</span></span> <span data-ttu-id="4075a-233">Impostazione predefinita: 10</span><span class="sxs-lookup"><span data-stu-id="4075a-233">Default: 10</span></span>

<span data-ttu-id="4075a-234">**LeastActiveRooms:** Se specificato, il report includerà le chat room meno attive in termini di numero di messaggi pubblicati nella chat room per il periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="4075a-234">**LeastActiveRooms:** If this is specified, the report will include the n least active chat rooms in terms of the number of messages posted in the chat room for the selected period.</span></span> <span data-ttu-id="4075a-235">Le camere avranno almeno un messaggio pubblicato.</span><span class="sxs-lookup"><span data-stu-id="4075a-235">Rooms will have at least one message posted.</span></span> <span data-ttu-id="4075a-236">Impostazione predefinita: 10</span><span class="sxs-lookup"><span data-stu-id="4075a-236">Default: 10</span></span>

<span data-ttu-id="4075a-237">**RoomsInactiveSince:** Se specificato, il report includerà un elenco di chat room inattive a partire dalla data specificata.</span><span class="sxs-lookup"><span data-stu-id="4075a-237">**RoomsInactiveSince:** If this is specified, the report will include a list of chat rooms that have been inactive since the specified date.</span></span> <span data-ttu-id="4075a-238">Impostazione predefinita: tempo intero</span><span class="sxs-lookup"><span data-stu-id="4075a-238">Default: Entire Time</span></span>

<span data-ttu-id="4075a-239">**CartellaOutput:** Cartella in cui verranno inserite le immagini ChatUsageReport. html e Graph.</span><span class="sxs-lookup"><span data-stu-id="4075a-239">**OutputFolder:** The folder where the ChatUsageReport.html and the graph images will be placed.</span></span> <span data-ttu-id="4075a-240">Questa operazione deve essere definita nel file di configurazione o nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="4075a-240">This must be defined in the config file or on the command line.</span></span>

<span data-ttu-id="4075a-241">Tutti i valori dei parametri della riga di comando possono essere specificati anche nel file ChatUsageReport. exe. config che si trova nella stessa directory dello strumento.</span><span class="sxs-lookup"><span data-stu-id="4075a-241">All of the command line parameter values can also be specified in the ChatUsageReport.exe.config file that is located in the same directory as the tool.</span></span> <span data-ttu-id="4075a-242">Se viene specificato un valore nel file di configurazione e nella riga di comando, il valore della riga di comando sovrascriverà il valore del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4075a-242">If any value is specified in both the config file and the command line, the command line value will override the config file value.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="4075a-243">Output</span><span class="sxs-lookup"><span data-stu-id="4075a-243">Output</span></span>

<span data-ttu-id="4075a-244">Il report includerà sempre l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="4075a-244">The report will always include the following output:</span></span>

  - <span data-ttu-id="4075a-245">Prime n chat room più attive per numero di post di messaggio per il periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="4075a-245">Top n most active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="4075a-246">Primi n utenti più attivi per numero di post di messaggio per periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="4075a-246">Top n most active users by number of message posts for selected period.</span></span>

  - <span data-ttu-id="4075a-247">Principali n meno chat room attive in base al numero di post di messaggio per il periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="4075a-247">Top n least active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="4075a-248">Chat room inattive per l'intera durata del database o dalla data specificata.</span><span class="sxs-lookup"><span data-stu-id="4075a-248">Chat rooms that are inactive for the entire life of the database, or since the specified date.</span></span>

  - <span data-ttu-id="4075a-249">Tendenza post giornaliera del messaggio per il periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="4075a-249">Daily message post trend for selected period.</span></span>

  - <span data-ttu-id="4075a-250">Tendenza post settimanale del messaggio per il periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="4075a-250">Weekly message post trend for selected period.</span></span>

  - <span data-ttu-id="4075a-251">Tendenza post mensile per il periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="4075a-251">Monthly message post trend for selected period.</span></span>

  - <span data-ttu-id="4075a-252">Totale post di messaggio per periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="4075a-252">Total message posts for selected period.</span></span>

  - <span data-ttu-id="4075a-253">Numero totale di sale abilitate.</span><span class="sxs-lookup"><span data-stu-id="4075a-253">Total number of enabled rooms.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="4075a-254">Esempio</span><span class="sxs-lookup"><span data-stu-id="4075a-254">Example</span></span>

<span data-ttu-id="4075a-255">L'esempio seguente genera un report sull'utilizzo per l'intero anno 2001 e inserisce il report in CartellaOutput specificato in ChatUsageReport. exe. config.</span><span class="sxs-lookup"><span data-stu-id="4075a-255">The following example generates a usage report for the entire year 2001 and places the report in the OutputFolder specified in the ChatUsageReport.exe.config.</span></span>

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
<span data-ttu-id="4075a-256">ChatUsageReport. exe. config:</span><span class="sxs-lookup"><span data-stu-id="4075a-256">ChatUsageReport.exe.config:</span></span>

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <connectionStrings>
        <!-- The PersistentChat connection string must be defined in this file. -->
        <add name="PersistentChat" connectionString="Data Source=contoso.com\RTC;Initial Catalog=mgc;Integrated Security=SSPI"/>
      </connectionStrings>
      <appSettings>
        <!-- The OutputFolder must be defined here or on the command line. -->
        <add key="OutputFolder" value="."/>
        <!-- The values below are the same as the application defaults. -->
        <add key="StartDate" value="01/01/0001"/>
        <add key="EndDate" value="12/31/9999"/>
        <add key="TopActiveUsers" value="10"/>
        <add key="TopActiveRooms" value="10"/>
        <add key="LeastActiveRooms" value="10"/>
        <add key="RoomsInactiveSince" value="01/01/0001"/>
      </appSettings>
    </configuration></configuration>
```
</div>

</div>

<div>

## <a name="scheduleadsyncforprincipal"></a><span data-ttu-id="4075a-257">ScheduleADSyncForPrincipal</span><span class="sxs-lookup"><span data-stu-id="4075a-257">ScheduleADSyncForPrincipal</span></span>

<div>

## <a name="description"></a><span data-ttu-id="4075a-258">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4075a-258">Description</span></span>

<span data-ttu-id="4075a-259">ScheduleADSyncForPrincipal è uno script di Microsoft SQL Server 2012 che deve essere eseguito direttamente da SQL Server Management Studio quando è connesso al database back-end della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4075a-259">ScheduleADSyncForPrincipal is a Microsoft SQL Server 2012 script that must be run directly from within SQL Server Management Studio when connected to the Persistent Chat back-end database.</span></span> <span data-ttu-id="4075a-260">Questo script consente di forzare la chat persistente a sincronizzare i propri record di un utente con quelli dei servizi di dominio Active Directory, invece di attendere il tempo di sincronizzazione programmato.</span><span class="sxs-lookup"><span data-stu-id="4075a-260">This script enables you to force Persistent Chat to synchronize its records of a user with those of Active Directory Domain Services, rather than waiting for the scheduled synchronization time.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="4075a-261">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4075a-261">Requirements</span></span>

<span data-ttu-id="4075a-262">L'account utente in cui viene eseguito lo script deve avere accesso proprietario al database back-end della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4075a-262">The user account under which the script is run must have owner access to the Persistent Chat back-end database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="4075a-263">L'uso</span><span class="sxs-lookup"><span data-stu-id="4075a-263">Usage</span></span>

<span data-ttu-id="4075a-264">Di seguito sono riportati i contenuti dello script predefinito:</span><span class="sxs-lookup"><span data-stu-id="4075a-264">Following are the contents of the default script:</span></span>

```Powershell
    /*
    This script will schedule a principal for a forced AD synchronization cycle
    
    If you're using Sql Server Management Studio, pressing Ctrl+Shift+M will 
    allow you to specify values for the template parameter.
    */
    
        insert into
          tblPrincipalMeta
          (
           prinID
          ,prinAffiliationsDirty
          ,prinAttributesDirty
          ,prinDeleted
          )
          select
            prinID
           ,1
           ,1
           ,0
          from
            tblPrincipal
          where
            prinID not in (select prinID from tblPrincipalMeta) and
            prinID = <PrinID,int,0>
     
        update
          tblPrincipalMeta
        set
          prinAffiliationsDirty = 1
         ,prinAttributesDirty = 1
         ,tryCount = 0
         ,nextTry = null
        where
         prinID = <PrinID,int,0>
```

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

