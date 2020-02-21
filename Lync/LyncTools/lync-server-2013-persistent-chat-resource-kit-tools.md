---
title: Strumenti del Resource Kit di Lync Server 2013 Persistent Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffd95611f3033dff992092e3be93815bd0e01915
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a><span data-ttu-id="fc5e4-102">Strumenti del Resource Kit di Lync Server 2013 Persistent Chat</span><span class="sxs-lookup"><span data-stu-id="fc5e4-102">Lync Server 2013 Persistent Chat Resource Kit Tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc5e4-103">_**Ultimo argomento modificato:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="fc5e4-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="fc5e4-104">Gli strumenti del Resource Kit di chat di Lync Server 2013 Persistent consentono di semplificare le attività di routine per gli amministratori IT che distribuiscono e gestiscono il server di chat persistente di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-104">The Lync Server 2013 Persistent Chat Resource Kit tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013 Persistent Chat Server.</span></span> <span data-ttu-id="fc5e4-105">Oltre alle istruzioni per l'installazione, in questo argomento viene descritto lo scopo di ogni strumento e gli esempi di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-105">In addition to installation instructions, this topic describes the purpose of each tool, and examples of its use.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="fc5e4-106">Installazione degli strumenti del Resource Kit</span><span class="sxs-lookup"><span data-stu-id="fc5e4-106">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="fc5e4-107">Per installare Lync Server 2013, strumenti del Resource Kit, scaricare **PersistentChatReskit. msi**.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-107">To install the Lync Server 2013, Resource Kit Tools, download **PersistentChatReskit.msi**.</span></span> <span data-ttu-id="fc5e4-108">Eseguire **PersistentChatReskit. msi** per eseguire un'installazione semplice.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-108">Run **PersistentChatReskit.msi** to do a simple installation.</span></span> <span data-ttu-id="fc5e4-109">Il file con estensione msi installa tutti gli strumenti nel percorso seguente \\: **Program\\ Files Microsoft Lync Server\\2013 Persistent Chat Server Resource Kit**.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-109">The .msi installs all the tools in the following path: \\**Program Files\\ Microsoft Lync Server 2013\\Persistent Chat Server Resource Kit**.</span></span> <span data-ttu-id="fc5e4-110">Gli strumenti che sono eseguibili indipendenti sono presenti in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-110">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="fc5e4-111">Gli strumenti che dispongono anche di file si trovano nelle rispettive sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-111">Tools that also have files are in their own subfolders.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fc5e4-112">Dopo aver installato Lync Server 2013, strumenti del Resource Kit, è necessario installare <STRONG>psexec. exe</STRONG> e copiare <STRONG>psexec. exe</STRONG> nel percorso seguente: \\ <STRONG>file di programma \ Microsoft Lync Server 2013 \ Kit\ChatStressTool delle risorse del server Chat persistente</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-112">After installing the Lync Server 2013, Resource Kit Tools, you must install <STRONG>PsExec.exe</STRONG> and copy <STRONG>PsExec.exe</STRONG> to the following path: \\<STRONG>Program Files\ Microsoft Lync Server 2013\Persistent Chat Server Resource Kit\ChatStressTool</STRONG>.</span></span> <span data-ttu-id="fc5e4-113">Se non si copia <STRONG>psexec. exe</STRONG>, lo strumento di stress Persistent Chat genererà un'eccezione di errore e non verrà eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-113">If you do not copy <STRONG>PsExec.exe</STRONG>, the Persistent Chat Stress Tool will throw an error exception, and not perform correctly.</span></span> <span data-ttu-id="fc5e4-114">Prima di eseguire lo strumento, accertarsi di rispettare questo requisito prerequisito.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-114">Make sure that you meet this prerequisite requirement prior to running the tool.</span></span> <span data-ttu-id="fc5e4-115">Per informazioni dettagliate sull'installazione di <STRONG>psexec. exe</STRONG>, vedere <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A>.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-115">For details about installing <STRONG>PsExec.exe</STRONG>, see <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="fc5e4-116">Ambienti supportati</span><span class="sxs-lookup"><span data-stu-id="fc5e4-116">Supported Environments</span></span>

<span data-ttu-id="fc5e4-117">Per ottenere prestazioni ottimali, è consigliabile installare gli strumenti di Lync Server 2013, Resource Kit nello stesso ambiente e con le stesse specifiche richieste per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-117">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="fc5e4-118">Panoramica degli strumenti del Resource Kit</span><span class="sxs-lookup"><span data-stu-id="fc5e4-118">Resource Kit Tools Overview</span></span>

<span data-ttu-id="fc5e4-119">Di seguito sono riportati gli strumenti disponibili nel Resource Kit di Lync Server 2013 Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-119">Here are the tools that are provided in the Lync Server 2013 Persistent Chat Resource Kit.</span></span> <span data-ttu-id="fc5e4-120">Nella sezione seguente viene fornita una descrizione di ogni strumento, inclusi i requisiti e l'utilizzo di esempio.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-120">The following section provides a description of each tool, including requirements and example usage.</span></span>

  - <span data-ttu-id="fc5e4-121">AffCheck</span><span class="sxs-lookup"><span data-stu-id="fc5e4-121">AffCheck</span></span>

  - <span data-ttu-id="fc5e4-122">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="fc5e4-122">ChatMonitoringSummary</span></span>

  - <span data-ttu-id="fc5e4-123">Strumento ChatStress</span><span class="sxs-lookup"><span data-stu-id="fc5e4-123">ChatStress Tool</span></span>

  - <span data-ttu-id="fc5e4-124">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="fc5e4-124">ChatUpgradeVerifier</span></span>

  - <span data-ttu-id="fc5e4-125">ChatUsageReport</span><span class="sxs-lookup"><span data-stu-id="fc5e4-125">ChatUsageReport</span></span>

  - <span data-ttu-id="fc5e4-126">ScheduleADSyncforPrincipal</span><span class="sxs-lookup"><span data-stu-id="fc5e4-126">ScheduleADSyncforPrincipal</span></span>

</div>

<div>

## <a name="affcheck"></a><span data-ttu-id="fc5e4-127">AffCheck</span><span class="sxs-lookup"><span data-stu-id="fc5e4-127">AffCheck</span></span>

<div>

## <a name="description"></a><span data-ttu-id="fc5e4-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc5e4-128">Description</span></span>

<span data-ttu-id="fc5e4-129">Lo strumento AffCheck conferma che l'utente del database back-end di chat persistente e i record di affiliazione di gruppo corrispondono a quelli dei servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-129">The AffCheck tool confirms that the Persistent Chat back-end database user and group affiliation records match that of Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="fc5e4-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc5e4-130">Requirements</span></span>

<span data-ttu-id="fc5e4-131">Lo strumento viene installato con il programma di installazione di PersistentChatResKit in un computer aggiunto a un dominio.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-131">The tool is installed with the PersistentChatResKit installer on a domain joined machine.</span></span>

<span data-ttu-id="fc5e4-132">L'account utente con cui viene eseguito lo strumento deve disporre dell'accesso in lettura al database back-end della chat persistente e ai servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-132">The user account under which the tool is run must have Read access to the Persistent Chat back-end database and Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="fc5e4-133">Usage</span><span class="sxs-lookup"><span data-stu-id="fc5e4-133">Usage</span></span>

<span data-ttu-id="fc5e4-134">Configurare il file AffCheck. exe. config seguendo le istruzioni riportate nel file di configurazione ed eseguire lo strumento AffCheck senza parametri della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-134">Configure the AffCheck.exe.config file according to the instructions in the config file and run the AffCheck tool without command-line parameters.</span></span> <span data-ttu-id="fc5e4-135">Di seguito sono riportati i contenuti del file AffCheck. exe. config predefinito.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-135">Following are the contents of the default AffCheck.exe.config.</span></span>

<span data-ttu-id="fc5e4-136">**AffCheck. exe. config:**</span><span class="sxs-lookup"><span data-stu-id="fc5e4-136">**AffCheck.exe.config:**</span></span>

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

## <a name="chatmonitoringsummary"></a><span data-ttu-id="fc5e4-137">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="fc5e4-137">ChatMonitoringSummary</span></span>

<div>

## <a name="description"></a><span data-ttu-id="fc5e4-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc5e4-138">Description</span></span>

<span data-ttu-id="fc5e4-139">Lo strumento PersistentChatMonitoringSummary sposta le informazioni di monitoraggio della chat persistente dal database di monitoraggio in un file di registro CSV specificato.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-139">The PersistentChatMonitoringSummary tool moves Persistent Chat monitoring information from the monitoring database into a specified CSV log file.</span></span>

<span data-ttu-id="fc5e4-140">Il file CSV conterrà una ripartizione delle sessioni di chat persistente per numero di sessioni totali, sessioni riuscite, errori imprevisti, errori previsti e una ripartizione degli errori imprevisti in base all'ID diagnostica, al numero di errori e alla descrizione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-140">The CSV file will contain a breakdown of Persistent Chat sessions by number of total sessions, successful sessions, unexpected failures, expected failures, and a breakdown of the unexpected failures by diagnostic ID, number of failures, and failure description.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="fc5e4-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc5e4-141">Requirements</span></span>

<span data-ttu-id="fc5e4-142">Installare gli strumenti del Resource Kit di Persistent Chat in un computer appartenente a un dominio che ha accesso al database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-142">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Monitoring database.</span></span>

<span data-ttu-id="fc5e4-143">L'account utente utilizzato per eseguire lo strumento deve disporre dell'accesso in lettura al database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-143">The user account under which the tool runs must have Read access to the Monitoring database.</span></span>

<span data-ttu-id="fc5e4-144">Il file PersistentChatMonitoringSummary. exe. config deve contenere una \<sezione connectionStrings\> che definisce la stringa di connessione al database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-144">The file, PersistentChatMonitoringSummary.exe.config, must contain a \<connectionStrings\> section that defines the connection string to the Monitoring database.</span></span> <span data-ttu-id="fc5e4-145">Deve inoltre contenere una chiave per la PersistentChatEndpointUri in cui verranno raccolti i dati di monitoraggio e il percorso di un file per il file CSV che verrà generato.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-145">It must also contain a key for the PersistentChatEndpointUri that the monitoring data will be gathered for, and a file path to a location for the CSV file that will be generated.</span></span> <span data-ttu-id="fc5e4-146">Per esempi, fare riferimento al file di configurazione installato.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-146">Refer to the installed config file for examples.</span></span> <span data-ttu-id="fc5e4-147">Il file deve trovarsi nella stessa directory dello strumento.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-147">The file must be located in the same directory as the tool.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="fc5e4-148">Usage</span><span class="sxs-lookup"><span data-stu-id="fc5e4-148">Usage</span></span>

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

<span data-ttu-id="fc5e4-149">Questi parametri definiscono la selezione dei dati:</span><span class="sxs-lookup"><span data-stu-id="fc5e4-149">These parameters define the selection of data:</span></span>

<span data-ttu-id="fc5e4-150">**StartDateTime:** Facoltativamente, specifica la data di inizio del periodo di selezione.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-150">**StartDateTime:** Optionally specifies the start date of the selection period.</span></span> <span data-ttu-id="fc5e4-151">Valore predefinito: 1/1/1753 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="fc5e4-151">Default: 1/1/1753 12:00:00 AM</span></span>

<span data-ttu-id="fc5e4-152">**EndDateTime:** Facoltativamente, specifica l'ultima data del periodo di selezione.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-152">**EndDateTime:** Optionally specifies the last date of the selection period.</span></span> <span data-ttu-id="fc5e4-153">Valore predefinito: ora</span><span class="sxs-lookup"><span data-stu-id="fc5e4-153">Default: Now</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="fc5e4-154">Esempio</span><span class="sxs-lookup"><span data-stu-id="fc5e4-154">Example</span></span>

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

## <a name="persistent-chat-stress-tool"></a><span data-ttu-id="fc5e4-155">Strumento di stress per chat persistente</span><span class="sxs-lookup"><span data-stu-id="fc5e4-155">Persistent Chat Stress Tool</span></span>

<div>

## <a name="description"></a><span data-ttu-id="fc5e4-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc5e4-156">Description</span></span>

<span data-ttu-id="fc5e4-157">Lo strumento di stress per la chat persistente rappresenta un modo semplice per simulare l'utilizzo di chat persistente per testare le prestazioni del mondo reale, compresi i modelli di utenti diversi per adattarsi meglio agli scenari di utilizzo previsti.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-157">The Persistent Chat Stress tool provides an easy way to simulate usage of Persistent Chat to test real-world performance, including varied user models to better fit your expected usage scenarios.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="fc5e4-158">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc5e4-158">Requirements</span></span>

<span data-ttu-id="fc5e4-159">Installare gli strumenti del Resource Kit di Persistent Chat su un computer aggiunto a un dominio che ha accesso al database back-end della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-159">Install the Persistent Chat Resource Kit tools onto a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="fc5e4-160">Oltre a questo computer *controller* , sono necessari diversi computer di *caricamento* .</span><span class="sxs-lookup"><span data-stu-id="fc5e4-160">In addition to this *controller* machine, you will need several *loader* machines.</span></span> <span data-ttu-id="fc5e4-161">Per tutti gli utenti di 10K nel modello utente, sarà necessario almeno 4GB di RAM libera su un computer caricatore.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-161">For every 10K users in your user model, you will need at least 4GB of free RAM on a loader machine.</span></span> <span data-ttu-id="fc5e4-162">Ad esempio, una corsa con gli utenti di 80K richiede circa 32GB di RAM sparsa su tutti i computer del caricatore.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-162">For example, a run with 80K users will require about 32GB of RAM spread across all loader machines.</span></span> <span data-ttu-id="fc5e4-163">È consigliabile disporre di almeno tre macchine del caricatore, indipendentemente dal carico previsto.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-163">We recommend that you have at least three loader machines, regardless of expected load.</span></span>

<span data-ttu-id="fc5e4-164">I computer del caricatore devono disporre di .NET 4,5 Framework e di Visual C++ 2012 Redistributable installato.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-164">Loader machines must have the .NET 4.5 Framework as well as the Visual C++ 2012 Redistributable installed.</span></span>

</div>

<div>

## <a name="configuration"></a><span data-ttu-id="fc5e4-165">Configurazione</span><span class="sxs-lookup"><span data-stu-id="fc5e4-165">Configuration</span></span>

<span data-ttu-id="fc5e4-166">Copiare i file di ChatStressTool in una cartella condivisa accessibile da tutti i computer del caricatore.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-166">Copy ChatStressTool files into a shared folder accessible from all loader machines.</span></span>

<span data-ttu-id="fc5e4-167">Creare gli utenti e i canali da utilizzare nell'esecuzione dello sforzo:</span><span class="sxs-lookup"><span data-stu-id="fc5e4-167">Create users and channels for use in the stress run:</span></span>

  - <span data-ttu-id="fc5e4-168">Creare tutti gli utenti per le chiamate del modello utente, abilitarli per Lync e impostare i criteri di Persistent Chat su abilitato.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-168">Create as many users as your user model calls for, enable them for Lync, and set their Persistent Chat policy to Enabled.</span></span>

  - <span data-ttu-id="fc5e4-169">Creare una categoria per i canali di stress e quindi creare il numero di spazi necessari per tale categoria.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-169">Create a category for your stress channels, and then create as many rooms as are needed under that category.</span></span> <span data-ttu-id="fc5e4-170">La categoria deve disporre di tutti gli utenti di stress nell'elenco **consentiti** (aggiungendo la propria unità organizzativa) e le sale di stress devono avere un'impostazione di privacy **aperta**.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-170">The category should have all stress users in its **Allowed** list (by way of adding their OU), and stress rooms should have a privacy setting of **Open**.</span></span>

  - <span data-ttu-id="fc5e4-171">Si consiglia di creare sale per la sollecitazione aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-171">We recommend creating extra stress rooms.</span></span> <span data-ttu-id="fc5e4-172">È possibile creare 50.000 sale con il seguente comando dell'interfaccia della riga di comando di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fc5e4-172">You can create 50,000 rooms with the following Windows PowerShell command-line interface command:</span></span>
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

<span data-ttu-id="fc5e4-173">Modificare i file di configurazione per adattarli alla topologia:</span><span class="sxs-lookup"><span data-stu-id="fc5e4-173">Edit the configuration files to fit your topology:</span></span>

<span data-ttu-id="fc5e4-174">In **LoaderProcess. exe. config**, impostare "controller.contoso.com" sul nome di dominio completo (FQDN) del computer del controller.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-174">In **LoaderProcess.exe.config**, change “controller.contoso.com” to the controller machine’s fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="fc5e4-175">In **StressLauncher. exe. config:**</span><span class="sxs-lookup"><span data-stu-id="fc5e4-175">In **StressLauncher.exe.config:**</span></span>

1.  <span data-ttu-id="fc5e4-176">Modificare il valore dell'impostazione "LoaderBinary" nel percorso della cartella condivisa.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-176">Change the “LoaderBinary” setting value to the shared folder’s path.</span></span>

2.  <span data-ttu-id="fc5e4-177">Modificare "AdminUser"/"AdminPassword" in credenziali che dispongono dell'accesso di amministratore ai computer del caricatore.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-177">Change “AdminUser”/”AdminPassword” to credentials that have admin access to loader machines.</span></span>

3.  <span data-ttu-id="fc5e4-178">Modificare "ChannelCategory" con il nome della categoria in cui sono stati creati i canali di sollecito.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-178">Change “ChannelCategory” to the name of the category that stress channels have been created under.</span></span>

4.  <span data-ttu-id="fc5e4-179">Modificare "UserNamePattern" e "UserPasswordPattern" in un modello corrispondente alle credenziali utente di stress.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-179">Change “UserNamePattern” and “UserPasswordPattern” to a template that matches your stress user credentials.</span></span> <span data-ttu-id="fc5e4-180">{0}viene sostituito con il numero di indice dell'utente.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-180">{0} is replaced with the user’s index number.</span></span>

5.  <span data-ttu-id="fc5e4-181">Modificare "dominio" nel dominio SIP della topologia di test.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-181">Change “Domain” to the SIP domain of your test topology.</span></span>

6.  <span data-ttu-id="fc5e4-182">Modificare "ConnectionString" in una stringa di connessione per il database back-end della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-182">Change “ConnectionString” to a connection string for your Persistent Chat back-end database.</span></span>

7.  <span data-ttu-id="fc5e4-183">Impostare "UserIndexStart" sull'indice del primo utente di stress.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-183">Change “UserIndexStart” to the index of the first stress user.</span></span>

8.  <span data-ttu-id="fc5e4-184">Modificare "LyncFQDN" con il nome di dominio completo del pool Front end.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-184">Change “LyncFQDN” to the FQDN of your Front End pool.</span></span>

9.  <span data-ttu-id="fc5e4-185">Modificare l'elenco "macchine" per includere i nomi dei computer per tutti i computer del caricatore.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-185">Modify the “Machines” list to include machine names for all of your loader machines.</span></span>

10. <span data-ttu-id="fc5e4-186">Modificare l'baseAddress dell'endpoint del servizio (il valore predefinito è "controller.contoso.com") con il nome di dominio completo del computer del controller.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-186">Change the baseAddress of the service endpoint (default is “controller.contoso.com”) to the FQDN of your controller machine.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="fc5e4-187">Usage</span><span class="sxs-lookup"><span data-stu-id="fc5e4-187">Usage</span></span>

<span data-ttu-id="fc5e4-188">Al termine della configurazione, aprire StressLauncher. exe nel computer del controller.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-188">After configuration is complete, open StressLauncher.exe on the controller machine.</span></span> <span data-ttu-id="fc5e4-189">È possibile avviare StressLauncher come qualsiasi utente.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-189">You can launch StressLauncher as any user.</span></span> <span data-ttu-id="fc5e4-190">Le credenziali in base alle quali vengono avviati i processi del caricatore nei computer del caricatore devono essere specificate nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-190">The credentials under which the loader processes start on the loader machines must be specified in the config file.</span></span> <span data-ttu-id="fc5e4-191">È inoltre necessario fornire una stringa di connessione che disponga dell'accesso in lettura al database back-end della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-191">You also must give a connection string that has Read access to the Persistent Chat back-end database.</span></span> <span data-ttu-id="fc5e4-192">Se la stringa di connessione utilizza l'autenticazione integrata di Windows, è necessario avviare StressLauncher come utente che dispone di questo accesso.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-192">If this connection string uses integrated Windows authentication, you must launch StressLauncher as a user that has this access.</span></span>

<span data-ttu-id="fc5e4-193">Modificare le impostazioni del modello utente in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-193">Alter the user model settings as needed.</span></span> <span data-ttu-id="fc5e4-194">Fare clic su **Avvia caricamento** per avviare una corsa.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-194">Click **Start Load** to initiate a run.</span></span> <span data-ttu-id="fc5e4-195">Dopo un minuto o giù di lì, gli utenti inizieranno a essere connessi e la barra di avanzamento inizierà a essere riempita.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-195">After a minute or so, users will start being signed in, and the progress bar will begin to fill.</span></span> <span data-ttu-id="fc5e4-196">A questo punto, è possibile che il computer del controller funzioni e esegua misure di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-196">At this point, you may can the controller machine working and take performance measurements.</span></span>

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a><span data-ttu-id="fc5e4-197">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="fc5e4-197">ChatUpgradeVerifier</span></span>

<div>

## <a name="description"></a><span data-ttu-id="fc5e4-198">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc5e4-198">Description</span></span>

<span data-ttu-id="fc5e4-199">ChatUpgradeVerifier è uno strumento di confronto di database specifico di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-199">ChatUpgradeVerifier is a Persistent Chat specific database comparison tool.</span></span> <span data-ttu-id="fc5e4-200">Lo strumento confronta il database di Group Chat 2007 R2 o Group Chat 2010 (2007/2010Db) al database di Persistent Chat 2013 (2013Db).</span><span class="sxs-lookup"><span data-stu-id="fc5e4-200">The tool compares either the Group Chat 2007 R2 or Group Chat 2010 Database (2007/2010Db) to the Persistent Chat 2013 Database (2013Db).</span></span>

<span data-ttu-id="fc5e4-201">Lo strumento controllerà, una per una, ogni categoria, chat room persistente e componente aggiuntivo in 2007/2010Db per vedere se viene visualizzato in 2013Db.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-201">The tool will check, one by one, each category, Persistent Chat room, and add-in in 2007/2010Db to see if it appears in the 2013Db.</span></span> <span data-ttu-id="fc5e4-202">Il confronto include la verifica di tutte le impostazioni della categoria, della chat room o del componente aggiuntivo, di qualsiasi entità nell'ambito della categoria e di qualsiasi entità in un ruolo nella categoria o nella chat.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-202">The comparison includes checking all settings on the category, chat room, or add-in, any principals in scope on the category, and any principal in a role on either the category or the chat room.</span></span> <span data-ttu-id="fc5e4-203">Se una categoria o una chat room non viene visualizzata correttamente in 2013Db, le differenze verranno restituite a un file Conflicts.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-203">If a category or a chat room does not appear correctly in the 2013Db, the differences will be output to a conflicts file.</span></span> <span data-ttu-id="fc5e4-204">Se dopo che si è verificato l'aggiornamento, il file 2007/2010Db è stato modificato e quindi questo strumento viene eseguito, si verificherà un output delle differenze per i conflitti.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-204">If, after the upgrade has occurred, the 2007/2010Db is changed and then this tool is run, there will be a differences output to the conflicts file.</span></span> <span data-ttu-id="fc5e4-205">Si noti che questa applicazione è solo uno strumento di confronto dei database e non convalida il processo di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-205">Note that this application is a database comparison tool only and does not validate the upgrade process.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="fc5e4-206">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc5e4-206">Requirements</span></span>

<span data-ttu-id="fc5e4-207">Installare gli strumenti del Resource Kit di Persistent Chat in un computer appartenente a un dominio che ha accesso ai database back-end della chat persistente (versioni precedenti e correnti per la chat persistente).</span><span class="sxs-lookup"><span data-stu-id="fc5e4-207">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end databases (previous and current versions for Persistent Chat).</span></span>

<span data-ttu-id="fc5e4-208">L'account utente utilizzato per l'esecuzione dello strumento deve disporre dell'accesso in lettura ai database di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-208">The user account under which the tool runs must have Read access to the Persistent Chat databases.</span></span>

<span data-ttu-id="fc5e4-209">Il file ChatUpgradeVerifier. exe. config deve contenere il parametro GroupChat2007R2Db o il parametro GroupChat2010Db, con una stringa di connessione al database di chat di gruppo appropriato (GroupChat 2007R2 o 2010).</span><span class="sxs-lookup"><span data-stu-id="fc5e4-209">The ChatUpgradeVerifier.exe.config file must contain either the GroupChat2007R2Db parameter or the GroupChat2010Db parameter, with a connection string to the appropriate Group Chat database (either Groupchat 2007R2 or 2010).</span></span> <span data-ttu-id="fc5e4-210">Deve contenere anche un parametro PersistentChat2013Db, con una stringa di connessione al database di Persistent Chat 2013.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-210">It must also contain a PersistentChat2013Db parameter, with a connection string to the Persistent Chat 2013 database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="fc5e4-211">Usage</span><span class="sxs-lookup"><span data-stu-id="fc5e4-211">Usage</span></span>

<span data-ttu-id="fc5e4-212">Eseguire **ChatUpgradeVerifier** senza alcun parametro.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-212">Run **ChatUpgradeVerifier** without any parameters.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="fc5e4-213">Esempio</span><span class="sxs-lookup"><span data-stu-id="fc5e4-213">Example</span></span>

<span data-ttu-id="fc5e4-214">![Esecuzione di ChatUpgradeVerifier. exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Esecuzione di ChatUpgradeVerifier. exe.")</span><span class="sxs-lookup"><span data-stu-id="fc5e4-214">![Running ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Running ChatUpgradeVerifier.exe.")</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a><span data-ttu-id="fc5e4-215">Report sull'utilizzo di chat persistente</span><span class="sxs-lookup"><span data-stu-id="fc5e4-215">Persistent Chat Usage Report</span></span>

<div>

## <a name="description"></a><span data-ttu-id="fc5e4-216">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc5e4-216">Description</span></span>

<span data-ttu-id="fc5e4-217">Lo strumento ChatUsageReport genera un rapporto HTML relativo all'utilizzo del servizio chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-217">The ChatUsageReport tool generates an HTML report of Persistent Chat service usage.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="fc5e4-218">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc5e4-218">Requirements</span></span>

<span data-ttu-id="fc5e4-219">Installare gli strumenti del Resource Kit di Persistent Chat in un computer appartenente a un dominio che ha accesso al database back-end della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-219">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="fc5e4-220">L'account utente con cui viene eseguito lo strumento deve disporre dell'accesso in lettura al database back-end della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-220">The user account under which the tool is run must have Read access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="fc5e4-221">Il file ChatUsageReport. exe. config deve contenere una \<sezione connectionStrings\> che definisce la stringa di connessione al database back-end della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-221">The file, ChatUsageReport.exe.config, must contain a \<connectionStrings\> section defining the connection string to the Persistent Chat back-end database.</span></span> <span data-ttu-id="fc5e4-222">Il contenuto del file di configurazione predefinito è incluso qui, per il riferimento.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-222">The contents of the default config file are included here, for your reference.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="fc5e4-223">Usage</span><span class="sxs-lookup"><span data-stu-id="fc5e4-223">Usage</span></span>

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
<span data-ttu-id="fc5e4-224">Questi parametri definiscono la selezione dei dati:</span><span class="sxs-lookup"><span data-stu-id="fc5e4-224">These parameters define the selection of data:</span></span>

<span data-ttu-id="fc5e4-225">**StartDate:** Facoltativamente, specifica la data di inizio dell'ora UTC del periodo di selezione.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-225">**StartDate:** Optionally specifies the UTC start date of the selection period.</span></span> <span data-ttu-id="fc5e4-226">Valore predefinito: data meno recente</span><span class="sxs-lookup"><span data-stu-id="fc5e4-226">Default: Earliest Date</span></span>

<span data-ttu-id="fc5e4-227">**EndDate:** Facoltativamente, specifica la data di fine dell'ora UTC del periodo di selezione.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-227">**EndDate:** Optionally specifies the UTC end date of the selection period.</span></span> <span data-ttu-id="fc5e4-228">Valore predefinito: ora</span><span class="sxs-lookup"><span data-stu-id="fc5e4-228">Default: Now</span></span>

<span data-ttu-id="fc5e4-229">Questi parametri definiscono come e quali dati vengono visualizzati:</span><span class="sxs-lookup"><span data-stu-id="fc5e4-229">These parameters define how and what data is displayed:</span></span>

<span data-ttu-id="fc5e4-230">**TopActiveUsers:** Se si specifica questo valore, il report includerà gli utenti n più attivi in termini di numero di messaggi inviati dall'utente nella chat room per il periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-230">**TopActiveUsers:** If this is specified, the report will include the n most active users in terms of the number of messages the user has posted in the chat room for the selected period.</span></span> <span data-ttu-id="fc5e4-231">Predefinito: 10</span><span class="sxs-lookup"><span data-stu-id="fc5e4-231">Default: 10</span></span>

<span data-ttu-id="fc5e4-232">**TopActiveRooms:** Se si specifica questo valore, il report includerà le chat room di n più attive in termini di numero di messaggi inseriti nella sala per il periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-232">**TopActiveRooms:** If this is specified, the report will include the n most active chat rooms in terms of the number of messages posted in the room for the selected period.</span></span> <span data-ttu-id="fc5e4-233">Predefinito: 10</span><span class="sxs-lookup"><span data-stu-id="fc5e4-233">Default: 10</span></span>

<span data-ttu-id="fc5e4-234">**LeastActiveRooms:** Se si specifica questo valore, il report includerà le chat room n meno attive in termini di numero di messaggi pubblicati nella chat room per il periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-234">**LeastActiveRooms:** If this is specified, the report will include the n least active chat rooms in terms of the number of messages posted in the chat room for the selected period.</span></span> <span data-ttu-id="fc5e4-235">Le sale avranno almeno un messaggio inviato.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-235">Rooms will have at least one message posted.</span></span> <span data-ttu-id="fc5e4-236">Predefinito: 10</span><span class="sxs-lookup"><span data-stu-id="fc5e4-236">Default: 10</span></span>

<span data-ttu-id="fc5e4-237">**RoomsInactiveSince:** Se viene specificato, il report includerà un elenco di chat room inattive dopo la data specificata.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-237">**RoomsInactiveSince:** If this is specified, the report will include a list of chat rooms that have been inactive since the specified date.</span></span> <span data-ttu-id="fc5e4-238">Valore predefinito: tempo intero</span><span class="sxs-lookup"><span data-stu-id="fc5e4-238">Default: Entire Time</span></span>

<span data-ttu-id="fc5e4-239">**CartellaOutput:** Cartella in cui verranno posizionate le immagini di ChatUsageReport. html e del grafico.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-239">**OutputFolder:** The folder where the ChatUsageReport.html and the graph images will be placed.</span></span> <span data-ttu-id="fc5e4-240">Tale operazione deve essere definita nel file di configurazione o nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-240">This must be defined in the config file or on the command line.</span></span>

<span data-ttu-id="fc5e4-241">È inoltre possibile specificare tutti i valori dei parametri della riga di comando nel file ChatUsageReport. exe. config che si trova nella stessa directory dello strumento.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-241">All of the command line parameter values can also be specified in the ChatUsageReport.exe.config file that is located in the same directory as the tool.</span></span> <span data-ttu-id="fc5e4-242">Se si specifica un valore nel file di configurazione e nella riga di comando, il valore della riga di comando ignorerà il valore del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-242">If any value is specified in both the config file and the command line, the command line value will override the config file value.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="fc5e4-243">Output</span><span class="sxs-lookup"><span data-stu-id="fc5e4-243">Output</span></span>

<span data-ttu-id="fc5e4-244">Il report includerà sempre l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="fc5e4-244">The report will always include the following output:</span></span>

  - <span data-ttu-id="fc5e4-245">Top n chat room più attive per numero di post di messaggio per il periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-245">Top n most active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="fc5e4-246">Top n gli utenti più attivi per numero di post di messaggio per il periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-246">Top n most active users by number of message posts for selected period.</span></span>

  - <span data-ttu-id="fc5e4-247">Top n chat room meno attive per numero di post di messaggio per il periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-247">Top n least active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="fc5e4-248">Chat room inattive per tutta la durata del database o dopo la data specificata.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-248">Chat rooms that are inactive for the entire life of the database, or since the specified date.</span></span>

  - <span data-ttu-id="fc5e4-249">Trend post giornaliero del messaggio per il periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-249">Daily message post trend for selected period.</span></span>

  - <span data-ttu-id="fc5e4-250">Trend post settimanale dei messaggi per il periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-250">Weekly message post trend for selected period.</span></span>

  - <span data-ttu-id="fc5e4-251">Trend post mensili del messaggio per il periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-251">Monthly message post trend for selected period.</span></span>

  - <span data-ttu-id="fc5e4-252">Totale messaggi di messaggio per il periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-252">Total message posts for selected period.</span></span>

  - <span data-ttu-id="fc5e4-253">Numero totale di chat room abilitate.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-253">Total number of enabled rooms.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="fc5e4-254">Esempio</span><span class="sxs-lookup"><span data-stu-id="fc5e4-254">Example</span></span>

<span data-ttu-id="fc5e4-255">Nell'esempio seguente viene generato un report di utilizzo per l'intero anno 2001 e il report viene inserito in CartellaOutput specificato nel file ChatUsageReport. exe. config.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-255">The following example generates a usage report for the entire year 2001 and places the report in the OutputFolder specified in the ChatUsageReport.exe.config.</span></span>

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
<span data-ttu-id="fc5e4-256">ChatUsageReport. exe. config:</span><span class="sxs-lookup"><span data-stu-id="fc5e4-256">ChatUsageReport.exe.config:</span></span>

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

## <a name="scheduleadsyncforprincipal"></a><span data-ttu-id="fc5e4-257">ScheduleADSyncForPrincipal</span><span class="sxs-lookup"><span data-stu-id="fc5e4-257">ScheduleADSyncForPrincipal</span></span>

<div>

## <a name="description"></a><span data-ttu-id="fc5e4-258">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc5e4-258">Description</span></span>

<span data-ttu-id="fc5e4-259">ScheduleADSyncForPrincipal è uno script di Microsoft SQL Server 2012 che deve essere eseguito direttamente dall'interno di SQL Server Management Studio quando è connesso al database back-end della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-259">ScheduleADSyncForPrincipal is a Microsoft SQL Server 2012 script that must be run directly from within SQL Server Management Studio when connected to the Persistent Chat back-end database.</span></span> <span data-ttu-id="fc5e4-260">Questo script consente di forzare la chat persistente a sincronizzare i propri record di un utente con quelli dei servizi di dominio Active Directory, anziché attendere il tempo di sincronizzazione pianificato.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-260">This script enables you to force Persistent Chat to synchronize its records of a user with those of Active Directory Domain Services, rather than waiting for the scheduled synchronization time.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="fc5e4-261">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc5e4-261">Requirements</span></span>

<span data-ttu-id="fc5e4-262">L'account utente con cui viene eseguito lo script deve disporre dell'accesso proprietario al database back-end della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fc5e4-262">The user account under which the script is run must have owner access to the Persistent Chat back-end database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="fc5e4-263">Usage</span><span class="sxs-lookup"><span data-stu-id="fc5e4-263">Usage</span></span>

<span data-ttu-id="fc5e4-264">Di seguito sono riportati i contenuti dello script predefinito:</span><span class="sxs-lookup"><span data-stu-id="fc5e4-264">Following are the contents of the default script:</span></span>

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

