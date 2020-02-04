---
title: Documentazione degli strumenti del Resource Kit di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 511a4ee9920237e1671a44a2f7481b40fbeb8e1a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-resource-kit-tools-documentation"></a><span data-ttu-id="7f995-102">Documentazione degli strumenti del Resource Kit di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f995-102">Lync Server 2013 Resource Kit Tools Documentation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f995-103">_**Argomento Ultima modifica:** 2014-01-09_</span><span class="sxs-lookup"><span data-stu-id="7f995-103">_**Topic Last Modified:** 2014-01-09_</span></span>

<span data-ttu-id="7f995-104">In questo argomento vengono descritti gli strumenti che fanno parte del Resource Kit di Lync Server 2013, tra cui lo scopo di ogni strumento e gli esempi del relativo utilizzo. Gli strumenti di Lync Server 2013, Resource Kit aiutano a semplificare le attività di routine per gli amministratori IT che distribuiscono e gestiscono Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-104">This topic describes the tools that are part of the Lync Server 2013 Resource Kit, including the purpose of each tool, and examples of its use.The Lync Server 2013, Resource Kit Tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="7f995-105">Ad esempio, lo strumento di **dati Web conf** può essere usato per controllare facilmente i dati caricati dagli utenti durante una riunione online.</span><span class="sxs-lookup"><span data-stu-id="7f995-105">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="7f995-106">Lo strumento **SEFAUtil** può essere usato per configurare l'inoltro di chiamata e la risposta dei delegati per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="7f995-106">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="7f995-107">Consigliamo agli amministratori IT di usare questi strumenti per gestire in modo più efficace Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-107">We encourage IT administrators to use these tools to more effectively manage Lync Server 2013.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="7f995-108">Installazione degli strumenti del Resource Kit</span><span class="sxs-lookup"><span data-stu-id="7f995-108">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="7f995-109">Per installare Lync Server 2013, strumenti Resource Kit, scaricare **OCSReskit. msi**.</span><span class="sxs-lookup"><span data-stu-id="7f995-109">To install the Lync Server 2013, Resource Kit Tools, download **OCSReskit.msi**.</span></span> <span data-ttu-id="7f995-110">È possibile scaricare il programma di installazione di strumenti Resource Kit dall'area [http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429)download.</span><span class="sxs-lookup"><span data-stu-id="7f995-110">You can download the Resource Kit Tools installer from the Download Center at [http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429).</span></span>

<span data-ttu-id="7f995-111">Eseguire **OCSResKit. msi** per eseguire un'installazione semplice.</span><span class="sxs-lookup"><span data-stu-id="7f995-111">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="7f995-112">Il file con estensione msi installa tutti gli strumenti disponibili nel percorso seguente: **% programmi\\% Microsoft Lync Server\\2013 reskit**.</span><span class="sxs-lookup"><span data-stu-id="7f995-112">The .msi installs all the tools in the following path: **%Program Files%\\Microsoft Lync Server 2013\\ResKit**.</span></span> <span data-ttu-id="7f995-113">Gli strumenti che sono eseguibili indipendenti si trovano in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="7f995-113">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="7f995-114">Gli strumenti che includono anche i file sono presenti nelle sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="7f995-114">Tools that also have files are in their own subfolders.</span></span>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="7f995-115">Ambienti supportati</span><span class="sxs-lookup"><span data-stu-id="7f995-115">Supported Environments</span></span>

<span data-ttu-id="7f995-116">Per ottenere prestazioni ottimali, gli strumenti di Lync Server 2013, Resource Kit devono essere installati nello stesso ambiente e con le stesse specifiche necessarie per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-116">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="7f995-117">Panoramica degli strumenti di Resource Kit</span><span class="sxs-lookup"><span data-stu-id="7f995-117">Resource Kit Tools Overview</span></span>

<span data-ttu-id="7f995-118">L'elenco seguente descrive gli strumenti disponibili nel Resource Kit di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-118">The following list describes the tools that are provided in the Lync Server 2013 Resource Kit.</span></span> <span data-ttu-id="7f995-119">Una descrizione di ogni strumento, inclusi i requisiti e l'utilizzo di esempio, è illustrata nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="7f995-119">A description of each tool, including the requirements and example usage is covered in the following section.</span></span>

  - <span data-ttu-id="7f995-120">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="7f995-120">ABSConfig</span></span>

  - <span data-ttu-id="7f995-121">Monitoraggio del servizio criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="7f995-121">Bandwidth Policy Service Monitor</span></span>

  - <span data-ttu-id="7f995-122">Analizzatore dell'utilizzo della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="7f995-122">Bandwidth Utilization Analyzer</span></span>

  - <span data-ttu-id="7f995-123">Chiama Parkometer</span><span class="sxs-lookup"><span data-stu-id="7f995-123">Call Parkometer</span></span>

  - <span data-ttu-id="7f995-124">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="7f995-124">CleanupStorageServiceData</span></span>

  - <span data-ttu-id="7f995-125">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="7f995-125">DBAnalyze</span></span>

  - <span data-ttu-id="7f995-126">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="7f995-126">ImportStorageServiceData</span></span>

  - <span data-ttu-id="7f995-127">LCSSync</span><span class="sxs-lookup"><span data-stu-id="7f995-127">LCSSync</span></span>

  - <span data-ttu-id="7f995-128">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="7f995-128">LookupUserConsole</span></span>

  - <span data-ttu-id="7f995-129">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="7f995-129">MsTurnPing</span></span>

  - <span data-ttu-id="7f995-130">Visualizzatore Configurazione di rete</span><span class="sxs-lookup"><span data-stu-id="7f995-130">Network Configuration Viewer</span></span>

  - <span data-ttu-id="7f995-131">Agente di Response Group Live</span><span class="sxs-lookup"><span data-stu-id="7f995-131">Response Group Agent Live</span></span>

  - <span data-ttu-id="7f995-132">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="7f995-132">SEFAUtil</span></span>

  - <span data-ttu-id="7f995-133">SYSPrep. ps1</span><span class="sxs-lookup"><span data-stu-id="7f995-133">SYSPrep.ps1</span></span>

  - <span data-ttu-id="7f995-134">Migrazione degli annunci di numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="7f995-134">Unassigned Number Announcements Migration</span></span>

  - <span data-ttu-id="7f995-135">Dati Web conf</span><span class="sxs-lookup"><span data-stu-id="7f995-135">Web Conf Data</span></span>

</div>

<div>

## <a name="absconfig"></a><span data-ttu-id="7f995-136">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="7f995-136">ABSConfig</span></span>

<span data-ttu-id="7f995-137">Lo strumento di configurazione del servizio Rubrica (ABSConfig) è uno strumento di amministrazione che consente agli amministratori di personalizzare la configurazione del servizio Rubrica in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-137">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Lync Server 2013.</span></span> <span data-ttu-id="7f995-138">Questo strumento consente inoltre agli amministratori di Lync Server 2013 di ripristinare le impostazioni predefinite del servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="7f995-138">This tool also enables Lync Server 2013 administrators to restore the default Address Book Service settings.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7f995-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f995-139">Description</span></span>

<span data-ttu-id="7f995-140">ABSConfig è un'applicazione di interfaccia utente grafica che consente agli amministratori di configurare gli attributi dei servizi di dominio Active Directory correlati al servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="7f995-140">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="7f995-141">Gli scenari principali per lo strumento sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f995-141">The primary scenarios for the tool are the following:</span></span>

  - <span data-ttu-id="7f995-142">Per consentire agli amministratori di eseguire il mapping degli attributi in servizi di dominio Active Directory agli attributi per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-142">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Lync Server 2013.</span></span>

  - <span data-ttu-id="7f995-143">Per consentire agli amministratori di specificare l'attributo servizi di dominio Active Directory da includere o escludere nei file del servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="7f995-143">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

  - <span data-ttu-id="7f995-144">Per consentire agli amministratori di ripristinare le impostazioni predefinite del servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="7f995-144">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="7f995-145">Lo strumento ABSConfig può essere avviato usando il file absConfig. exe.</span><span class="sxs-lookup"><span data-stu-id="7f995-145">The ABSConfig tool can be started by using the absConfig.exe file.</span></span> <span data-ttu-id="7f995-146">Lo strumento viene aperto nella scheda **configura attributi** . Questa tabella include opzioni per eseguire il mapping degli attributi dei servizi di dominio Active Directory ai campi degli attributi per Lync Server 2013 e per specificare quali utenti includere o escludere nei file del servizio Rubrica in base a specifici filtri di attributi.</span><span class="sxs-lookup"><span data-stu-id="7f995-146">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Lync Server 2013 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="7f995-147">Include anche opzioni per personalizzare il valore del numero di telefono da includere nel file della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="7f995-147">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="7f995-148">L'opzione **Ripristina predefiniti** consente agli amministratori di ripristinare le impostazioni del servizio Rubrica per i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="7f995-148">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

</div>

<div>

## <a name="changes-from-lync-server-2010"></a><span data-ttu-id="7f995-149">Modifiche da Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7f995-149">Changes from Lync Server 2010</span></span>

<span data-ttu-id="7f995-150">Nello strumento di configurazione ABS di Lync Server 2013 gli attributi (righe) potrebbero essere rimossi deselezionando la casella di controllo "Enable" per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="7f995-150">In Lync Server 2013 ABS Configuration tool, attributes (rows) may be removed by unchecking the “enable” checkbox for the attribute.</span></span> <span data-ttu-id="7f995-151">Questo ha lo stesso effetto dell'eliminazione della riga in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7f995-151">This has the same effect as deleting the row in Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f995-152">La casella di controllo Enable si trova nella colonna estrema destra; potrebbe essere necessario scorrere verso destra per visualizzare la colonna</span><span class="sxs-lookup"><span data-stu-id="7f995-152">The enable checkbox is in the far right column; you may need to scroll right to see the column</span></span>



</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="7f995-153">Output</span><span class="sxs-lookup"><span data-stu-id="7f995-153">Output</span></span>

<span data-ttu-id="7f995-154">ABSConfig archivia la configurazione del servizio Rubrica nel database.</span><span class="sxs-lookup"><span data-stu-id="7f995-154">ABSConfig stores the Address Book Service configuration in the database.</span></span>

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="7f995-155">Scopo</span><span class="sxs-lookup"><span data-stu-id="7f995-155">Purpose</span></span>

<span data-ttu-id="7f995-156">ABSConfig offre un modo semplice e rapido per personalizzare il servizio Rubrica di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-156">ABSConfig provides a quick and easy way to customize Lync Server 2013 Address Book Service.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7f995-157">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f995-157">Requirements</span></span>

<div>

## <a name="computer"></a><span data-ttu-id="7f995-158">Computer</span><span class="sxs-lookup"><span data-stu-id="7f995-158">Computer</span></span>

<span data-ttu-id="7f995-159">ABSConfig può essere eseguito solo da un computer collegato al dominio in cui è installato Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-159">ABSConfig can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span> <span data-ttu-id="7f995-160">Nel caso di Lync Server 2013, Enterprise Edition, questo strumento può essere eseguito in qualsiasi server front-end in cui è abilitato il servizio Rubrica durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="7f995-160">In the case of Lync Server 2013, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

</div>

<div>

## <a name="network"></a><span data-ttu-id="7f995-161">Rete</span><span class="sxs-lookup"><span data-stu-id="7f995-161">Network</span></span>

<span data-ttu-id="7f995-162">Il computer dovrebbe essere in grado di connettersi al pool Front-end e al database back-end.</span><span class="sxs-lookup"><span data-stu-id="7f995-162">The computer should be able to connect to the Front End pool and back-end database.</span></span>

</div>

<div>

## <a name="software"></a><span data-ttu-id="7f995-163">Software</span><span class="sxs-lookup"><span data-stu-id="7f995-163">Software</span></span>

<span data-ttu-id="7f995-164">Prima di eseguire lo strumento ABSConfig, è necessario installare i componenti software seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f995-164">The following software components must be installed before running the ABSConfig tool:</span></span>

  - <span data-ttu-id="7f995-165">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f995-165">Microsoft Lync Server 2013</span></span>

</div>

<div>

## <a name="users"></a><span data-ttu-id="7f995-166">Utenti</span><span class="sxs-lookup"><span data-stu-id="7f995-166">Users</span></span>

<span data-ttu-id="7f995-167">Amministratori che hanno le autorizzazioni necessarie per aggiornare la distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-167">Administrators who have the permissions required to update the Lync Server 2013 deployment.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7f995-168">Esempi</span><span class="sxs-lookup"><span data-stu-id="7f995-168">Examples</span></span>

<span data-ttu-id="7f995-169">ABSConfig può essere avviato digitando **ABSConfig. exe** al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="7f995-169">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="7f995-170">Di seguito è riportata l'interfaccia utente dello strumento ABSConfig.</span><span class="sxs-lookup"><span data-stu-id="7f995-170">Shown below is the ABSConfig tool user interface.</span></span>

<span data-ttu-id="7f995-171">![Strumento ABSConfig.exe](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "Strumento ABSConfig.exe")</span><span class="sxs-lookup"><span data-stu-id="7f995-171">![The ABSConfig.exe tool.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "The ABSConfig.exe tool.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="7f995-172">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="7f995-172">Summary</span></span>

<span data-ttu-id="7f995-173">Lo strumento ABSConfig offre agli amministratori uno strumento rapido e facile da usare per personalizzare il servizio Rubrica di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-173">The ABSConfig tool provides administrators a quick and easy to use tool to customize Lync Server 2013 Address Book Service.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="7f995-174">Monitoraggio del servizio criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="7f995-174">Bandwidth Policy Service Monitor</span></span>

<span data-ttu-id="7f995-175">Lo strumento Monitoraggio dei servizi per la larghezza di banda è progettato per consentire agli amministratori di visualizzare un elenco delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f995-175">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1.  <span data-ttu-id="7f995-176">Tutti i servizi per i criteri di larghezza di banda di Lync Server 2013 (autenticazione e Core) configurati nella topologia</span><span class="sxs-lookup"><span data-stu-id="7f995-176">All the configured Lync Server 2013 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2.  <span data-ttu-id="7f995-177">Le connessioni che ogni servizio apporta ad altri servizi per i criteri di larghezza di banda e agli Edge Server</span><span class="sxs-lookup"><span data-stu-id="7f995-177">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3.  <span data-ttu-id="7f995-178">Tutti i collegamenti configurati nel documento di configurazione della rete e nell'utilizzo della larghezza di banda in tempo reale riportati da ognuno dei servizi per i criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="7f995-178">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7f995-179">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f995-179">Description</span></span>

<span data-ttu-id="7f995-180">Lo strumento Monitoraggio del servizio di Bandwidth Policy viene implementato come applicazione basata su GUI.</span><span class="sxs-lookup"><span data-stu-id="7f995-180">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="7f995-181">Gli amministratori avviano lo strumento eseguendo PDPMonUI. exe.</span><span class="sxs-lookup"><span data-stu-id="7f995-181">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="7f995-182">Quando lo strumento viene avviato, cerca di individuare l'elenco dei servizi per i criteri di larghezza di banda nella topologia.</span><span class="sxs-lookup"><span data-stu-id="7f995-182">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="7f995-183">Dopo aver completato l'aggiornamento iniziale, il riquadro a sinistra della finestra viene popolato con un elenco di servizi raggruppati per i cluster a cui appartengono.</span><span class="sxs-lookup"><span data-stu-id="7f995-183">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="7f995-184">Quando gli amministratori selezionano un particolare servizio per i criteri di larghezza di banda, nel riquadro a destra vengono visualizzate le informazioni relative al particolare servizio.</span><span class="sxs-lookup"><span data-stu-id="7f995-184">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="7f995-185">Il riquadro contiene anche due schede principali che visualizzano le informazioni.</span><span class="sxs-lookup"><span data-stu-id="7f995-185">That pane also has two main tabs that display information.</span></span>

<div>

## <a name="machine-info-tab"></a><span data-ttu-id="7f995-186">Scheda info computer</span><span class="sxs-lookup"><span data-stu-id="7f995-186">Machine Info Tab</span></span>

<span data-ttu-id="7f995-187">La scheda **info computer** Mostra i dettagli del servizio dei criteri di larghezza di banda selezionato e l'elenco e lo stato di tutte le connessioni effettuate dal servizio criteri di larghezza di banda selezionato ad altri servizi.</span><span class="sxs-lookup"><span data-stu-id="7f995-187">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

</div>

<div>

## <a name="topology-info-tab"></a><span data-ttu-id="7f995-188">Scheda informazioni topologia</span><span class="sxs-lookup"><span data-stu-id="7f995-188">Topology Info Tab</span></span>

<span data-ttu-id="7f995-189">Nella scheda **informazioni topologia** viene visualizzato un elenco di tutti i collegamenti configurati nelle impostazioni di configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="7f995-189">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="7f995-190">Per ogni collegamento viene visualizzata la capacità di larghezza di banda audio e video.</span><span class="sxs-lookup"><span data-stu-id="7f995-190">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="7f995-191">Viene inoltre visualizzata la larghezza di banda attualmente utilizzata, sia in Kbps che come percentuale della capacità.</span><span class="sxs-lookup"><span data-stu-id="7f995-191">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="7f995-192">Lo strumento usa la codifica a colori per evidenziare i collegamenti con l'utilizzo che è vicino alla capacità, che consente agli amministratori di isolare rapidamente tali collegamenti.</span><span class="sxs-lookup"><span data-stu-id="7f995-192">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f995-193">Se lo strumento Monitoraggio servizi di larghezza di banda non funziona quando si connette a uno dei servizi configurati per i criteri di larghezza di banda, le informazioni nelle schede informazioni <STRONG>computer</STRONG> e <STRONG>informazioni topologia</STRONG> non verranno popolate.</span><span class="sxs-lookup"><span data-stu-id="7f995-193">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the <STRONG>Machine Info</STRONG> and the <STRONG>Topology Info</STRONG> tabs won’t be populated.</span></span> <span data-ttu-id="7f995-194">Tuttavia, è possibile che lo strumento possa connettersi inizialmente, ma in seguito perde la connessione al servizio.</span><span class="sxs-lookup"><span data-stu-id="7f995-194">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="7f995-195">In questi casi, gli amministratori possono visualizzare informazioni obsolete.</span><span class="sxs-lookup"><span data-stu-id="7f995-195">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="7f995-196">È disponibile un <STRONG>ultimo timestamp aggiornato</STRONG> in ognuna delle schede che consentono agli amministratori di vedere quando i dati sono stati aggiornati per un particolare servizio per i criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="7f995-196">There is a <STRONG>Last Updated</STRONG> time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="7f995-197">Output</span><span class="sxs-lookup"><span data-stu-id="7f995-197">Output</span></span>

<span data-ttu-id="7f995-198">Non è disponibile alcun output della riga di comando; l'output del programma è contenuto nell'interfaccia utente grafica principale (GUI).</span><span class="sxs-lookup"><span data-stu-id="7f995-198">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="7f995-199">Scopo</span><span class="sxs-lookup"><span data-stu-id="7f995-199">Purpose</span></span>

<span data-ttu-id="7f995-200">Lo scopo dello strumento Monitoraggio dei servizi per la larghezza di banda è consentire agli amministratori la visibilità dello stato di ognuno dei servizi per i criteri di larghezza di banda definiti nella topologia.</span><span class="sxs-lookup"><span data-stu-id="7f995-200">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="7f995-201">Gli amministratori possono inoltre visualizzare l'utilizzo della larghezza di banda in tempo reale per tutti i collegamenti definiti nel documento di configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="7f995-201">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7f995-202">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f995-202">Requirements</span></span>

<span data-ttu-id="7f995-203">Lo strumento Monitoraggio dei servizi per la larghezza di banda deve essere eseguito in un computer che fa parte della topologia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7f995-203">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Lync Server topology.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="7f995-204">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="7f995-204">Summary</span></span>

<span data-ttu-id="7f995-205">Lo strumento Monitoraggio dei servizi per la larghezza di banda può essere una risorsa preziosa per gli amministratori in modo che possano ispezionare lo stato di tutti i servizi dei criteri di larghezza di banda nella topologia e, cosa più importante, possono ottenere l'utilizzo della larghezza di banda in tempo reale per i collegamenti definito nelle impostazioni di configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="7f995-205">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="7f995-206">Analizzatore dell'utilizzo della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="7f995-206">Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="7f995-207">L'analizzatore dell'utilizzo della larghezza di banda è uno strumento che crea report su varie visualizzazioni del consumo di larghezza di banda dagli endpoint UC in collegamenti WAN nella rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="7f995-207">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="7f995-208">Questi report possono essere usati per comprendere il modello di consumo di larghezza di banda corrente e per facilitare la pianificazione della capacità di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="7f995-208">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7f995-209">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f995-209">Description</span></span>

<span data-ttu-id="7f995-210">L'analizzatore dell'utilizzo della larghezza di banda viene implementato come applicazione basata su GUI.</span><span class="sxs-lookup"><span data-stu-id="7f995-210">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="7f995-211">Questo strumento genera report specifici per l'utilizzo dell'audio in tutta la rete e consente la pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="7f995-211">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="7f995-212">Viene inoltre iterata sulla capacità di larghezza di banda assegnata a diversi collegamenti.</span><span class="sxs-lookup"><span data-stu-id="7f995-212">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="7f995-213">Output</span><span class="sxs-lookup"><span data-stu-id="7f995-213">Output</span></span>

<span data-ttu-id="7f995-214">L'analizzatore dell'utilizzo della larghezza di banda offre grafici al grafico della capacità e dell'utilizzo della larghezza di banda per l'audio per tutti i collegamenti WAN configurati nel sistema.</span><span class="sxs-lookup"><span data-stu-id="7f995-214">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="7f995-215">Scopo</span><span class="sxs-lookup"><span data-stu-id="7f995-215">Purpose</span></span>

<span data-ttu-id="7f995-216">In qualsiasi distribuzione di voce e video, è fondamentale monitorare e comprendere l'andamento dell'utilizzo della larghezza di banda del traffico multimediale attraverso la rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="7f995-216">In any voice and video deployment, it’s critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="7f995-217">Lo strumento Analizzatore di utilizzo della larghezza di banda consente a un amministratore di raggiungere questo obiettivo.</span><span class="sxs-lookup"><span data-stu-id="7f995-217">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="7f995-218">Questo strumento esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f995-218">This tool does the following:</span></span>

  - <span data-ttu-id="7f995-219">Genera report specifici per l'utilizzo audio in rete</span><span class="sxs-lookup"><span data-stu-id="7f995-219">Generates specific reports for audio utilization across the network</span></span>

  - <span data-ttu-id="7f995-220">Facilita la pianificazione e l'iterazione della capacità più efficace sulla capacità di larghezza di banda assegnata a diversi collegamenti</span><span class="sxs-lookup"><span data-stu-id="7f995-220">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="7f995-221">L'analizzatore dell'utilizzo della larghezza di banda può generare trame grafiche della capacità e dei report di utilizzo della larghezza di banda; sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f995-221">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

  - <span data-ttu-id="7f995-222">Tutti i collegamenti WAN nella rete aziendale</span><span class="sxs-lookup"><span data-stu-id="7f995-222">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="7f995-223">Filtrato da collegamenti WAN selezionati scelti</span><span class="sxs-lookup"><span data-stu-id="7f995-223">Filtered by selected WAN links that have been chosen</span></span>

  - <span data-ttu-id="7f995-224">Filtrati da collegamenti WAN che hanno superato la capacità di collegamento</span><span class="sxs-lookup"><span data-stu-id="7f995-224">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="7f995-225">Filtrati da collegamenti WAN che sono stati sottoposti a utilizzo della larghezza di banda provisioning</span><span class="sxs-lookup"><span data-stu-id="7f995-225">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

  - <span data-ttu-id="7f995-226">Filtrare in base a collegamenti WAN che hanno raggiunto livelli critici (un utilizzo della larghezza di banda maggiore di 90% della capacità di larghezza di banda del collegamento WAN)</span><span class="sxs-lookup"><span data-stu-id="7f995-226">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="7f995-227">Filtrato tramite il tipo di collegamento WAN: collegamenti a siti di rete, collegamenti interregionali e collegamenti all'interno di un sito</span><span class="sxs-lookup"><span data-stu-id="7f995-227">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

  - <span data-ttu-id="7f995-228">Filtrata per area di rete</span><span class="sxs-lookup"><span data-stu-id="7f995-228">Filtered by network region</span></span>

<div>

## <a name="applications"></a><span data-ttu-id="7f995-229">Applicazioni</span><span class="sxs-lookup"><span data-stu-id="7f995-229">Applications</span></span>

<span data-ttu-id="7f995-230">L'analizzatore dell'utilizzo della larghezza di banda include le due applicazioni seguenti (strumenti):</span><span class="sxs-lookup"><span data-stu-id="7f995-230">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

  - <span data-ttu-id="7f995-231">**WanLinkLogCollector. exe**   questo strumento consente all'utente di immettere le informazioni richieste.</span><span class="sxs-lookup"><span data-stu-id="7f995-231">**WanLinkLogCollector.exe**   This tool enables its user to input the required information.</span></span>

  - <span data-ttu-id="7f995-232">**BandwidthUtilizationAnalyzer. xlsm**  un report del foglio di calcolo di Microsoft Excel viene avviato automaticamente da WanLinkLogCollector. exe.</span><span class="sxs-lookup"><span data-stu-id="7f995-232">**BandwidthUtilizationAnalyzer.xlsm**  A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="7f995-233">Questa applicazione consente all'utente di applicare filtri al report come illustrato più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="7f995-233">This application allows the user to apply filters to the report as shown later in this article.</span></span>

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="7f995-234">Fasi dell'uso dell'analizzatore dell'utilizzo della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="7f995-234">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="7f995-235">Quando si usa l'analizzatore dell'utilizzo della larghezza di banda, esistono due fasi:</span><span class="sxs-lookup"><span data-stu-id="7f995-235">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

  - <span data-ttu-id="7f995-236">Raccolta di log, eseguita tramite WanLinkLogCollector. exe</span><span class="sxs-lookup"><span data-stu-id="7f995-236">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

  - <span data-ttu-id="7f995-237">Personalizzare i report, che vengono eseguiti tramite BandwidthUtilizationAnalyzer. xlsm</span><span class="sxs-lookup"><span data-stu-id="7f995-237">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7f995-238">Consigliamo vivamente che BandwidthUtilizationAnalyzer. xlsm non venga lanciato manualmente dagli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="7f995-238">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="7f995-239">Avvio dell'analizzatore dell'utilizzo della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="7f995-239">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="7f995-240">Avviare WanLinkLogCollector. exe al prompt dei comandi o usando Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="7f995-240">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

<span data-ttu-id="7f995-241">**Uso di WanLinkLogCollector. exe**</span><span class="sxs-lookup"><span data-stu-id="7f995-241">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="7f995-242">Sono disponibili tre passaggi per l'uso di WanLinkLogCollector. exe:</span><span class="sxs-lookup"><span data-stu-id="7f995-242">There are three steps to using WanLinkLogCollector.exe:</span></span>

1.  <span data-ttu-id="7f995-243">**Registrare la sequenza temporale**   specificare la sequenza temporale per la quale deve essere generato il report</span><span class="sxs-lookup"><span data-stu-id="7f995-243">**Log the timeline**   Provide the timeline that the report needs to be generated for</span></span>

2.  <span data-ttu-id="7f995-244">**Specificare le directory**   di file che includono le informazioni sulla posizione del file</span><span class="sxs-lookup"><span data-stu-id="7f995-244">**Specify the file directories**   Provide file location information</span></span>

3.  <span data-ttu-id="7f995-245">**Raccogliere i log e avviare il Visualizzatore**  di report eseguire il comando per generare il report</span><span class="sxs-lookup"><span data-stu-id="7f995-245">**Collect the logs and launch the report viewer**  Execute the command to generate the report</span></span>

<div>

## <a name="step-1---log-the-timeline"></a><span data-ttu-id="7f995-246">Passaggio 1-registrare la sequenza temporale</span><span class="sxs-lookup"><span data-stu-id="7f995-246">Step 1 - Log the timeline</span></span>

<span data-ttu-id="7f995-247">La registrazione della sequenza temporale consente all'utente dello strumento di specificare quanto segue, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="7f995-247">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1.  <span data-ttu-id="7f995-248">**Data di inizio** Questa è la data di inizio della sequenza temporale a cui deve essere generato il report; ad esempio, 1 agosto 2010.</span><span class="sxs-lookup"><span data-stu-id="7f995-248">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2.  <span data-ttu-id="7f995-249">**Data di fine** Questa è la data di fine della sequenza temporale a cui deve essere generato il report; ad esempio, il 30 settembre 2010.</span><span class="sxs-lookup"><span data-stu-id="7f995-249">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>
    
    <span data-ttu-id="7f995-250">![Date di inizio e fine per l'analisi dell'utilizzo della larghezza di banda](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Date di inizio e fine per l'analisi dell'utilizzo della larghezza di banda")</span><span class="sxs-lookup"><span data-stu-id="7f995-250">![Start and End dates in the Bandwidth Utilization A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Start and End dates in the Bandwidth Utilization A")</span></span>  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="7f995-251">Passaggio 2-specificare le directory dei file</span><span class="sxs-lookup"><span data-stu-id="7f995-251">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="7f995-252">Le directory di file seguenti possono essere specificate dall'utente come illustrato.</span><span class="sxs-lookup"><span data-stu-id="7f995-252">The following file directories can be specified by the user as shown.</span></span>

  - <span data-ttu-id="7f995-253">**Posizione dei file di log del server** Percorso della cartella in cui sono archiviati i registri del server dei criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="7f995-253">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="7f995-254">Si tratta in \<genere di\>\\\<una scelta Fileserver\>\\di\\Fe AppServerFiles PDP.</span><span class="sxs-lookup"><span data-stu-id="7f995-254">This is typically in \<fileserver\>\\\<choice of FE\>\\AppServerFiles\\PDP.</span></span>

  - <span data-ttu-id="7f995-255">**Percorso di archiviazione file temporaneo** Percorso del file temporaneo in cui vengono archiviati i file intermedi mentre viene generato il report.</span><span class="sxs-lookup"><span data-stu-id="7f995-255">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

<span data-ttu-id="7f995-256">![Directory di file per l'analisi dell'utilizzo della larghezza di banda](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Directory di file per l'analisi dell'utilizzo della larghezza di banda")</span><span class="sxs-lookup"><span data-stu-id="7f995-256">![File directories in the Bandwidth Utilization Anal](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "File directories in the Bandwidth Utilization Anal")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f995-257">Verificare che l'accesso a un file sufficiente ai registri del server e alla cartella temporanea dell'archivio file venga fornito all'utente dello strumento.</span><span class="sxs-lookup"><span data-stu-id="7f995-257">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="7f995-258">Passaggio 3-raccogliere i registri e avviare il Visualizzatore report</span><span class="sxs-lookup"><span data-stu-id="7f995-258">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="7f995-259">Per raccogliere i log e avviare il Visualizzatore report, fare clic su **Esegui** come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="7f995-259">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="7f995-260">Questo passaggio raccoglie i dati necessari.</span><span class="sxs-lookup"><span data-stu-id="7f995-260">This step collects the required data.</span></span>

<span data-ttu-id="7f995-261">![Raccolta dei dati per l'analisi dell'utilizzo della larghezza di banda](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Raccolta dei dati per l'analisi dell'utilizzo della larghezza di banda")</span><span class="sxs-lookup"><span data-stu-id="7f995-261">![Collecting data in the Bandwidth Utilization Analy](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Collecting data in the Bandwidth Utilization Analy")</span></span>

<span data-ttu-id="7f995-262">Quando la convalida dell'input è riuscita, viene visualizzato il messaggio mostrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="7f995-262">When the input validation is successful, the message shown below is displayed.</span></span>

<span data-ttu-id="7f995-263">![Notifica della raccolta dei log in Bandwidth Utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Notifica della raccolta dei log in Bandwidth Utili")</span><span class="sxs-lookup"><span data-stu-id="7f995-263">![Logs collected notification in the Bandwidth Utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Logs collected notification in the Bandwidth Utili")</span></span>

<span data-ttu-id="7f995-264">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f995-264">Click **OK**.</span></span> <span data-ttu-id="7f995-265">BandwidthUtilizationAnalyzer. xlsm viene avviato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7f995-265">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="7f995-266">Seguire le istruzioni nella finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="7f995-266">Follow the instructions in the message box.</span></span> <span data-ttu-id="7f995-267">Per informazioni dettagliate, vedere **uso di BandwidthUtilizationAnalyzer. xlsm** nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="7f995-267">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>

</div>

<div>


<span data-ttu-id="7f995-268">**Uso di BandwidthUtilizationAnalyzer. xlsm**</span><span class="sxs-lookup"><span data-stu-id="7f995-268">**Using BandwidthUtilizationAnalyzer.xlsm**</span></span>

1.  <span data-ttu-id="7f995-269">Quando BandwidthUtilizationAnalyzer. xlsm viene avviato automaticamente, fare clic su **Aggiorna** come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="7f995-269">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>
    
    <span data-ttu-id="7f995-270">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span><span class="sxs-lookup"><span data-stu-id="7f995-270">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span></span>

2.  <span data-ttu-id="7f995-271">Quando si apre una cartella di file, selezionare consolidato. csv dalla posizione specificata nella finestra di messaggio, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="7f995-271">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="7f995-272">Viene inoltre visualizzata la posizione **C:\\Temp**.</span><span class="sxs-lookup"><span data-stu-id="7f995-272">It also shows the location as **C:\\Temp**.</span></span>
    
    <span data-ttu-id="7f995-273">![Apertura di una cartella in Bandwidth Utilization Analyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Apertura di una cartella in Bandwidth Utilization Analyzer.")</span><span class="sxs-lookup"><span data-stu-id="7f995-273">![Opening a folder in BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Opening a folder in BandwidthUtilizationAnalyzer.")</span></span>

3.  <span data-ttu-id="7f995-274">Fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="7f995-274">Click **Import**.</span></span>

4.  <span data-ttu-id="7f995-275">La trama grafica viene generata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7f995-275">The graphical plot is automatically generated.</span></span> <span data-ttu-id="7f995-276">È disponibile quando il puntatore di lavoro in background scompare.</span><span class="sxs-lookup"><span data-stu-id="7f995-276">It is available when the working-in-the-background pointer disappears.</span></span>
    
    <span data-ttu-id="7f995-277">![Applicazione di filtri nella visualizzazione Report.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applicazione di filtri nella visualizzazione Report.")</span><span class="sxs-lookup"><span data-stu-id="7f995-277">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="7f995-278">Applicazione di filtri alla visualizzazione report</span><span class="sxs-lookup"><span data-stu-id="7f995-278">Applying Filters to the Report View</span></span>

<span data-ttu-id="7f995-279">I filtri che è possibile applicare alla visualizzazione report come illustrato di seguito sono descritti di seguito:</span><span class="sxs-lookup"><span data-stu-id="7f995-279">The filters that can be applied to the report view as shown below are described as follows:</span></span>

<span data-ttu-id="7f995-280">![Applicazione di filtri nella visualizzazione Report.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applicazione di filtri nella visualizzazione Report.")</span><span class="sxs-lookup"><span data-stu-id="7f995-280">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

1.  <span data-ttu-id="7f995-281">**Nome** Filtrare per collegamenti WAN (il filtro si trova sul lato destro del grafico). Il prefisso denota i tipi di collegamento seguenti: vedere la casella verticale (blu):</span><span class="sxs-lookup"><span data-stu-id="7f995-281">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>
    
      - <span data-ttu-id="7f995-282">**Sito S** Collegamento WAN da un sito di rete a un'area di rete</span><span class="sxs-lookup"><span data-stu-id="7f995-282">**S Site** The WAN link from a network site to a network region</span></span>
    
      - <span data-ttu-id="7f995-283">**È tra siti** Collegamento WAN tra due siti di rete</span><span class="sxs-lookup"><span data-stu-id="7f995-283">**IS Inter-Site** The WAN link between two network sites</span></span>
    
      - <span data-ttu-id="7f995-284">**Inter-area geografica R** Collegamento WAN tra due aree geografiche di rete</span><span class="sxs-lookup"><span data-stu-id="7f995-284">**R Inter-Region** The WAN link between two network region</span></span>

2.  <span data-ttu-id="7f995-285">**Limite superato** Filtrare per collegamenti WAN il cui utilizzo della larghezza di banda è maggiore della capacità di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="7f995-285">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3.  <span data-ttu-id="7f995-286">**Livelli critici** Filtrare per collegamenti WAN il cui utilizzo della larghezza di banda ha raggiunto 90% o più della capacità di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="7f995-286">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4.  <span data-ttu-id="7f995-287">**Sottoutilizzati** Filtrare per collegamenti WAN il cui utilizzo della larghezza di banda è inferiore al 25% della capacità di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="7f995-287">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5.  <span data-ttu-id="7f995-288">**Tipo di collegamento** Filtrare in base ai tipi di collegamenti WAN seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f995-288">**Link type** Filter by the following WAN links types:</span></span>
    
      - <span data-ttu-id="7f995-289">Tipo di **sito di rete**</span><span class="sxs-lookup"><span data-stu-id="7f995-289">**Network site** type</span></span>
    
      - <span data-ttu-id="7f995-290">Tipo **inter-sito**</span><span class="sxs-lookup"><span data-stu-id="7f995-290">**Inter-site** type</span></span>
    
      - <span data-ttu-id="7f995-291">Tipo **di collegamento tra aree** geografiche</span><span class="sxs-lookup"><span data-stu-id="7f995-291">**Inter-Region link** type</span></span>

6.  <span data-ttu-id="7f995-292">**Area geografica** Filtrare per area di rete</span><span class="sxs-lookup"><span data-stu-id="7f995-292">**Region** Filter by network region</span></span>

<span data-ttu-id="7f995-293">Le figure seguenti mostrano i filtri descritti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="7f995-293">The following figures show the previously described filters.</span></span>

<span data-ttu-id="7f995-294">Filtrare in base al **nome**.</span><span class="sxs-lookup"><span data-stu-id="7f995-294">Filter by **Name**.</span></span> <span data-ttu-id="7f995-295">Selezionare l'elenco di collegamenti che devono essere visualizzati nel grafico.</span><span class="sxs-lookup"><span data-stu-id="7f995-295">Select the list of links that need to be displayed in the graph.</span></span>

<span data-ttu-id="7f995-296">![Filtro per nome in BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtro per nome in BandwidthUtilizationAnalyzer.")</span><span class="sxs-lookup"><span data-stu-id="7f995-296">![Filtering by Name in BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtering by Name in BandwidthUtilizationAnalyzer.")</span></span>

<span data-ttu-id="7f995-297">Filtrare in base al **limite superato**.</span><span class="sxs-lookup"><span data-stu-id="7f995-297">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="7f995-298">Selezionare **true** per applicare il filtro.</span><span class="sxs-lookup"><span data-stu-id="7f995-298">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="7f995-299">![Filtro per Exceeded Limit.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtro per Exceeded Limit.")</span><span class="sxs-lookup"><span data-stu-id="7f995-299">![Filtering by Exceeded Limit.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtering by Exceeded Limit.")</span></span>

<span data-ttu-id="7f995-300">Filtrare in base a **livelli critici**.</span><span class="sxs-lookup"><span data-stu-id="7f995-300">Filter by **Critical levels**.</span></span> <span data-ttu-id="7f995-301">Selezionare **true** per applicare il filtro.</span><span class="sxs-lookup"><span data-stu-id="7f995-301">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="7f995-302">![Filtro per Critical Levels.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtro per Critical Levels.")</span><span class="sxs-lookup"><span data-stu-id="7f995-302">![Filtering by Critical Levels.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtering by Critical Levels.")</span></span>

<span data-ttu-id="7f995-303">Filtrare in **base a usato**.</span><span class="sxs-lookup"><span data-stu-id="7f995-303">Filter by **Under utilized**.</span></span> <span data-ttu-id="7f995-304">Selezionare **true** per applicare il filtro.</span><span class="sxs-lookup"><span data-stu-id="7f995-304">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="7f995-305">![Filtro per Under Utilized.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtro per Under Utilized.")</span><span class="sxs-lookup"><span data-stu-id="7f995-305">![Filtering by Under Utilized.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtering by Under Utilized.")</span></span>

<span data-ttu-id="7f995-306">Filtra per **tipo di collegamento**.</span><span class="sxs-lookup"><span data-stu-id="7f995-306">Filter by **Link Type**.</span></span> <span data-ttu-id="7f995-307">Selezionare il tipo o i tipi che devono essere visualizzati.</span><span class="sxs-lookup"><span data-stu-id="7f995-307">Select the type or types that need to be displayed.</span></span>

<span data-ttu-id="7f995-308">![Filtro per Link Type.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtro per Link Type.")</span><span class="sxs-lookup"><span data-stu-id="7f995-308">![Filtering by Link Type.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtering by Link Type.")</span></span>

<span data-ttu-id="7f995-309">Filtrare per **area geografica**.</span><span class="sxs-lookup"><span data-stu-id="7f995-309">Filter by **Region**.</span></span> <span data-ttu-id="7f995-310">Selezionare un elenco di aree di cui devono essere visualizzati i collegamenti.</span><span class="sxs-lookup"><span data-stu-id="7f995-310">Select a list of regions whose links need to be displayed.</span></span>

<span data-ttu-id="7f995-311">![Filtro per Region.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtro per Region.")</span><span class="sxs-lookup"><span data-stu-id="7f995-311">![Filtering by Region.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtering by Region.")</span></span>

</div>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7f995-312">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f995-312">Requirements</span></span>

  - <span data-ttu-id="7f995-313">.NET Framework 3,5</span><span class="sxs-lookup"><span data-stu-id="7f995-313">The .NET Framework 3.5</span></span>

  - <span data-ttu-id="7f995-314">Microsoft Excel 2010 o Excel 2007</span><span class="sxs-lookup"><span data-stu-id="7f995-314">Microsoft Excel 2010 or Excel 2007</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="7f995-315">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="7f995-315">Summary</span></span>

<span data-ttu-id="7f995-316">L'analizzatore dell'utilizzo della larghezza di banda viene usato per tracciare l'utilizzo della larghezza di banda audio per il traffico UC attraverso la rete.</span><span class="sxs-lookup"><span data-stu-id="7f995-316">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="7f995-317">Questo strumento può essere usato per segnalare l'utilizzo della larghezza di banda video anche nella rete.</span><span class="sxs-lookup"><span data-stu-id="7f995-317">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

</div>

</div>

<div>

## <a name="call-parkometer"></a><span data-ttu-id="7f995-318">Chiama Parkometer</span><span class="sxs-lookup"><span data-stu-id="7f995-318">Call Parkometer</span></span>

<span data-ttu-id="7f995-319">Call Parkometer è un'applicazione della riga di comando che consente di accedere facilmente al database Orbit di Call Park.</span><span class="sxs-lookup"><span data-stu-id="7f995-319">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7f995-320">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f995-320">Description</span></span>

<span data-ttu-id="7f995-321">Chiamata Parkometer è uno strumento per tenere traccia delle chiamate parcheggiate attualmente.</span><span class="sxs-lookup"><span data-stu-id="7f995-321">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="7f995-322">Raccoglie anche statistiche sulle orbite e sull'utilizzo di Call Park Server (CPS).</span><span class="sxs-lookup"><span data-stu-id="7f995-322">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="7f995-323">Questo strumento della riga di comando offre sia la lettura che l'accesso in scrittura al database di SQL Server Orbit di CPS da un computer locale o connesso in remoto.</span><span class="sxs-lookup"><span data-stu-id="7f995-323">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="7f995-324">Tutte le opzioni si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="7f995-324">All options are mutually exclusive.</span></span> <span data-ttu-id="7f995-325">La sintassi della riga di comando è la seguente:</span><span class="sxs-lookup"><span data-stu-id="7f995-325">Command-line syntax is as follows:</span></span>

  - <span data-ttu-id="7f995-326">**-o** Parameter-elenca tutti gli intervalli di Orbit configurati per questo pool.</span><span class="sxs-lookup"><span data-stu-id="7f995-326">**–o** parameter—lists all orbit ranges configured for this pool.</span></span>

  - <span data-ttu-id="7f995-327">**– parametro n** : elenca tutte le orbite attualmente usate in questo pool.</span><span class="sxs-lookup"><span data-stu-id="7f995-327">**–n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="7f995-328">Le informazioni visualizzate sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f995-328">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="7f995-329">URI (Uniform Resource Identifier) SIP di Parkee e Parker.</span><span class="sxs-lookup"><span data-stu-id="7f995-329">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>
    
      - <span data-ttu-id="7f995-330">Nome host del CPS in cui è parcheggiata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7f995-330">Host name of the CPS where the call is parked.</span></span>
    
      - <span data-ttu-id="7f995-331">Indicatore di data e ora di quando la chiamata è stata parcheggiata.</span><span class="sxs-lookup"><span data-stu-id="7f995-331">Time stamp of when the call was parked.</span></span>

  - <span data-ttu-id="7f995-332">**-parametro f** -elenca il numero di orbite attualmente libere nel pool.</span><span class="sxs-lookup"><span data-stu-id="7f995-332">**–f** parameter—lists the number of currently free orbits in the pool.</span></span>

  - <span data-ttu-id="7f995-333">**-parametro \<r\> n** -elenca le \<n\> ultime chiamate parcheggiate.</span><span class="sxs-lookup"><span data-stu-id="7f995-333">**–r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="7f995-334">Le informazioni visualizzate sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f995-334">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="7f995-335">URI SIP di Parkee.</span><span class="sxs-lookup"><span data-stu-id="7f995-335">Parkee SIP URI.</span></span>
    
      - <span data-ttu-id="7f995-336">URI SIP di Parker.</span><span class="sxs-lookup"><span data-stu-id="7f995-336">Parker SIP URI.</span></span>
    
      - <span data-ttu-id="7f995-337">Nome host del CPS in cui è stata parcheggiata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7f995-337">Host name of the CPS where the call was parked.</span></span>
    
      - <span data-ttu-id="7f995-338">Indicatore di data e ora di quando la chiamata è stata recuperata o eliminata.</span><span class="sxs-lookup"><span data-stu-id="7f995-338">Time stamp of when the call was retrieved or dropped.</span></span>

  - <span data-ttu-id="7f995-339">**-parametro\<t\> n** -test che riservano un'orbita nel database per mostrare la casualità dei numeri di orbita assegnati.</span><span class="sxs-lookup"><span data-stu-id="7f995-339">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="7f995-340">Output</span><span class="sxs-lookup"><span data-stu-id="7f995-340">Output</span></span>

<span data-ttu-id="7f995-341">In base ai parametri di input specificati al prompt dei comandi, chiama Parkometer Visualizza l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="7f995-341">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

  - <span data-ttu-id="7f995-342">Tutti gli intervalli di orbita configurati per il pool</span><span class="sxs-lookup"><span data-stu-id="7f995-342">All orbit ranges that are configured for this pool</span></span>

  - <span data-ttu-id="7f995-343">Chiamate attualmente parcheggiate</span><span class="sxs-lookup"><span data-stu-id="7f995-343">Currently parked calls</span></span>

  - <span data-ttu-id="7f995-344">Numero di orbite libere (disponibili)</span><span class="sxs-lookup"><span data-stu-id="7f995-344">Number of free (available) orbits</span></span>

  - <span data-ttu-id="7f995-345">Chiamate parcheggiate di recente</span><span class="sxs-lookup"><span data-stu-id="7f995-345">Recently parked calls</span></span>

  - <span data-ttu-id="7f995-346">Orbite riservate per testare i valori dell'orbita uniforme e casuale</span><span class="sxs-lookup"><span data-stu-id="7f995-346">Reserved orbits for testing uniform and random orbit values</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="7f995-347">Scopo</span><span class="sxs-lookup"><span data-stu-id="7f995-347">Purpose</span></span>

<span data-ttu-id="7f995-348">Lo scopo dello strumento CPS è quello di consentire l'accesso della riga di comando al database CPS.</span><span class="sxs-lookup"><span data-stu-id="7f995-348">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="7f995-349">L'amministratore può visualizzare l'utilizzo di CPS e determinare il numero di orbite assegnate a un pool.</span><span class="sxs-lookup"><span data-stu-id="7f995-349">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7f995-350">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f995-350">Requirements</span></span>

<span data-ttu-id="7f995-351">Se questo strumento viene eseguito nello stesso computer in cui è in esecuzione CPS, non sono previsti requisiti.</span><span class="sxs-lookup"><span data-stu-id="7f995-351">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="7f995-352">Se questo strumento viene eseguito in un computer remoto, il database di SQL Server usato da Lync Server 2013 deve essere configurato per consentire l'accesso remoto.</span><span class="sxs-lookup"><span data-stu-id="7f995-352">If this tool is run on a remote computer, the SQL Server database used by Lync Server 2013 must be configured to allow remote access.</span></span> <span data-ttu-id="7f995-353">La chiamata di Parkometer deve essere configurata con una stringa di connessione al database di SQL Server per connettersi al server SQL del pool.</span><span class="sxs-lookup"><span data-stu-id="7f995-353">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool’s SQL Server.</span></span> <span data-ttu-id="7f995-354">Questa stringa di connessione al database di SQL Server è definita nel file di configurazione **parkometer. exe. config**. Deve essere posizionato nella stessa directory in cui si trova parkometer. exe.</span><span class="sxs-lookup"><span data-stu-id="7f995-354">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="7f995-355">Il file XML seguente è un esempio di parkometer. exe. config. I parametri che devono essere configurati sono nome utente (ad esempio,\\amministratore di dominio), password (ad esempio, password) e nome host (ad esempio, MyServer).</span><span class="sxs-lookup"><span data-stu-id="7f995-355">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
       <add key="SQL" value="server=myserver\RTC;
    database=cpsdyn;
    User Id=mydomain\Administrator;
    Password=mypassword.;
    Integrated Security=false;"/>
      </appSettings>
    </configuration>
```

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7f995-356">Esempi</span><span class="sxs-lookup"><span data-stu-id="7f995-356">Examples</span></span>

<span data-ttu-id="7f995-357">Intervalli di Orbit distribuiti: il parametro-o elenca tutti gli intervalli di orbita configurati per il pool come illustrato</span><span class="sxs-lookup"><span data-stu-id="7f995-357">Deployed orbit ranges: the –o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

<span data-ttu-id="7f995-358">![Intervalli dei codici orbit in Call Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Intervalli dei codici orbit in Call Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="7f995-358">![Orbit ranges in Call Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Orbit ranges in Call Parkometer.")</span></span>

<span data-ttu-id="7f995-359">Chiamate parcheggiate attualmente: il parametro – n elenca tutte le orbite attualmente usate in questo pool come illustrato</span><span class="sxs-lookup"><span data-stu-id="7f995-359">Currently parked calls: the –n parameter lists all currently used orbits on this pool as shown</span></span>

<span data-ttu-id="7f995-360">![Chiamate attualmente parcheggiate in Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Chiamate attualmente parcheggiate in Call Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="7f995-360">![Currently-parked calls in Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Currently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="7f995-361">Numero di orbite gratuite: il parametro – f elenca il numero di orbite attualmente libere nel pool come illustrato</span><span class="sxs-lookup"><span data-stu-id="7f995-361">Number of free orbits: the –f parameter lists the number of currently free orbits in the pool as shown</span></span>

<span data-ttu-id="7f995-362">![Codici orbit liberi in Call Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Codici orbit liberi in Call Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="7f995-362">![Free orbits in Call Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Free orbits in Call Parkometer.")</span></span>

<span data-ttu-id="7f995-363">Chiamate parcheggiate di recente: il parametro \<–\> r n elenca \<le\> chiamate n per ultimo parcheggiate come illustrato</span><span class="sxs-lookup"><span data-stu-id="7f995-363">Recently parked calls: the –r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

<span data-ttu-id="7f995-364">![Chiamate parcheggiate di recente in Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Chiamate parcheggiate di recente in Call Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="7f995-364">![Recently-parked calls in Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Recently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="7f995-365">Prenota l'orbita di test: i \<test\> dei parametri-t n che riservano un'orbita nel database come illustrato</span><span class="sxs-lookup"><span data-stu-id="7f995-365">Test orbit reservation: the –t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

<span data-ttu-id="7f995-366">![Prenotazione codici orbit di test in Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Prenotazione codici orbit di test in Call Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="7f995-366">![Test orbit reservations in Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Test orbit reservations in Call Parkometer.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="7f995-367">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="7f995-367">Summary</span></span>

<span data-ttu-id="7f995-368">Call Parkometer è uno strumento della riga di comando che fornisce informazioni dettagliate sul server di Call Park.</span><span class="sxs-lookup"><span data-stu-id="7f995-368">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a><span data-ttu-id="7f995-369">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="7f995-369">CleanupStorageServiceData</span></span>

<span data-ttu-id="7f995-370">Lo strumento CleanupStorageServiceData Resource Kit consente l'eliminazione di dati orfani dal database usato dal servizio di archiviazione di Lync Server (LYSS).</span><span class="sxs-lookup"><span data-stu-id="7f995-370">The CleanupStorageServiceData resource kit tool allows for deleting of orphaned data from the database used by the Lync Server Storage Service (LYSS).</span></span> <span data-ttu-id="7f995-371">Una funzione del servizio di archiviazione consiste nel buffer di comunicazione tra Lync Server e diversi endpoint di archiviazione dei dati back-end, ad esempio SQL Server e Exchange.</span><span class="sxs-lookup"><span data-stu-id="7f995-371">One function of the storage service is to buffer communication between Lync Server and various back-end data storage endpoints, like SQL Server and Exchange.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7f995-372">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f995-372">Description</span></span>

<span data-ttu-id="7f995-373">Per supportare la disponibilità elevata, LYSS accetta e salva temporaneamente le copie dei dati in più server front-end nel pool e rimuove i dati dopo che è stata recapitata nella posizione finale di archiviazione a lungo termine.</span><span class="sxs-lookup"><span data-stu-id="7f995-373">To support high availability, LYSS accepts and saves copies of the data on multiple front end servers in the pool temporarily, and removes that data once it has been delivered to its final long-term storage location.</span></span> <span data-ttu-id="7f995-374">Ci sono situazioni anomale che potrebbero verificarsi durante il normale funzionamento, quando un server potrebbe arrestarsi in modo anomalo o provare un problema di elaborazione e alcuni dati potrebbero non essere ripuliti correttamente.</span><span class="sxs-lookup"><span data-stu-id="7f995-374">There are unusual situations which may occur during otherwise normal operation, when a server might crash or experience a processing issue, and some data might not get cleaned up properly.</span></span> <span data-ttu-id="7f995-375">Questi dati sono inoffensivi, ma consumano risorse di elaborazione limitate.</span><span class="sxs-lookup"><span data-stu-id="7f995-375">This data is harmless, but it does consume limited processing resources.</span></span> <span data-ttu-id="7f995-376">Gran parte della normale manutenzione dei dati necessaria è automatizzata, ma questo strumento consente l'identificazione e la rimozione sicuri di tali dati orfani quando non è possibile la rimozione automatica.</span><span class="sxs-lookup"><span data-stu-id="7f995-376">Much of the normal required data maintenance is automated, but this tool allows for the safe identification and removal of such orphaned data when automated removal is not possible.</span></span> <span data-ttu-id="7f995-377">L'uso di questo strumento è indicato quando viene generato un avviso di System Center Operations Manager (SCOM) di monitoraggio dell'integrità, che chiede all'amministratore di rimuovere i dati non necessari dai database locali di LYSS nel pool.</span><span class="sxs-lookup"><span data-stu-id="7f995-377">Usage of this tool is indicated when a health monitoring System Center Operations Manager (SCOM) alert is raised which asks the administrator to remove the unneeded data from the local LYSS databases in the pool.</span></span> <span data-ttu-id="7f995-378">Verrà visualizzato un evento corrispondente nel log eventi sul front-end che ha attivato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="7f995-378">There will be a corresponding event in the event log on the front end which triggered the alert.</span></span> <span data-ttu-id="7f995-379">I dettagli dell'evento conterranno informazioni sulla quantità di dati orfani contenuti nel front-end e viene generata quando tali dati superano determinati valori di soglia predefiniti</span><span class="sxs-lookup"><span data-stu-id="7f995-379">The event details will contain information about the amount of orphaned data contained on the front end, and is raised when that data exceeds certain pre-determine thresholds</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7f995-380">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f995-380">Requirements</span></span>

<span data-ttu-id="7f995-381">Installare gli strumenti di Lync Server 2013, Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="7f995-381">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="7f995-382">Lo strumento viene eseguito in computer Uniti a un dominio in cui sono installati Lync Server e Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7f995-382">The tool runs on domain-joined machines where Lync Server and Lync Server 2013 Management Shell are installed.</span></span> <span data-ttu-id="7f995-383">Lo strumento usa un cmdlet di Management Shell per identificare tutti i server front-end nel pool.</span><span class="sxs-lookup"><span data-stu-id="7f995-383">The tool uses a cmdlet from the management shell to identify all Front End servers in the pool.</span></span> <span data-ttu-id="7f995-384">In secondo luogo, lo strumento deve essere eseguito da un computer nel pool in cui è installato il database **RtcLocal** .</span><span class="sxs-lookup"><span data-stu-id="7f995-384">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="7f995-385">Questo database viene usato dallo strumento CleanupStorageServiceData per ottenere i dettagli di connessione necessari per comunicare con il servizio di routing di Lync Server. Infine, l'account o le credenziali che richiamano lo strumento devono avere l'autorizzazione di lettura/scrittura per la condivisione di file a cui si vuole scrivere il log di output. Questo strumento dipende inoltre dal pool che si trova in uno stato stabile.</span><span class="sxs-lookup"><span data-stu-id="7f995-385">This database is used by the CleanupStorageServiceData tool to get the connection details needed to communicate with the Lync Server Routing Service.Finally, the account or credential invoking the tool must have read/write permission to the file share to which they want to write the output log.Also, this tool depends on the pool being in a stable state.</span></span> <span data-ttu-id="7f995-386">In sostanza, questo significa che ogni server front-end dovrebbe essere installato e in esecuzione, l'istanza di SQL Server LYNCLOCAL e il database LYSS devono essere in grado di connettersi e ogni gruppo di routing deve avere un set completo di 1 server front-end primari e due front end s secondari ervers.</span><span class="sxs-lookup"><span data-stu-id="7f995-386">In essence this means that every Front End server is expected to be up and running, the SQL Server LYNCLOCAL instance and LYSS database must be able to be connected to, and each routing group must have a complete set of 1 primary Front End servers and 2 secondary Front End servers.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7f995-387">Esempi</span><span class="sxs-lookup"><span data-stu-id="7f995-387">Examples</span></span>

<span data-ttu-id="7f995-388">C:\\programmi\\Microsoft Lync Server 2013\\reskit\\StorageService\> ImportStorageServiceData. exe</span><span class="sxs-lookup"><span data-stu-id="7f995-388">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData.exe</span></span>

    Description:
    This tool will remove orphaned data from the Storage Service database
    for a pool. You are required to run this tool on a machine inside the
    pool which has the Lync Server Management Shell installed and has RtcLocal database installed.
    Usage: Default behavior is to clean up orphaned data from the all the 
           Storage Service databases in the current pool.
    Additional Options:
    -Verbose    : Turn verbose output on.
    -LogPath    : The UNC path to which to write the log.
    ------------------------------------------------------------------------------
    Please wait while we initialize...
    Found 4 front end servers
    Replica Instances for LYSS Service
    Address: server2.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server1.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server3.vdomain.com - Primaries: 7 Secondaries: 14
    Primary Total Count = 28, Secondary Total Count = 56
    Finding and removing orphaned data for 28 routing groups
    Removing 1 stale groups from FE server.vdomain.com
    No stale routing groups detected on FE server2.vdomain.com
    No stale routing groups detected on FE server1.vdomain.com
    No stale routing groups detected on FE server3.vdomain.com
    Searching for stale queue items
    Removed 20 stale queue items for routing group 17D5435AE40259F7BBDF1866776386E4
    No stale queue items found for routing group 1975349662315F90B119DACB4F2AE3AD
    No stale queue items found for routing group 1A23E3D58BDB5A458A0B73F34AB7ACBE
    No stale queue items found for routing group 1AC91E3A1029535A80123121989CEADC
    No stale queue items found for routing group 3313935458E35B9B9759E08A15D251E6
    No stale queue items found for routing group 39BB0035B06B5427873FC6099720462A
    No stale queue items found for routing group 40721948E7B55CE893A53E911F76D185
    No stale queue items found for routing group 4501E04EAE4856059346949FF817C220
    No stale queue items found for routing group 4D833C98801F546F8E45E417EE028E2E
    No stale queue items found for routing group 5AD77443AD955A22A876749BE66D5317
    No stale queue items found for routing group 69844A271E6C5633A1F2B46A42287DD6
    No stale queue items found for routing group 69DA3BE407A95C7284EB4B1337718C93
    No stale queue items found for routing group 8437358AB34A5CC8967D5EF39494AB8D
    No stale queue items found for routing group 8ED455B1789655359816E1C5BF4C430F
    No stale queue items found for routing group 904F6C9B8AC951AE8B3C86684D3832E4
    No stale queue items found for routing group 90AAB3AE9A1950E0ADE7809A27021D63
    No stale queue items found for routing group 944F5724C65C5F93900DC1C8C898B102
    No stale queue items found for routing group 9E8A2630250C51769E39F63F0FB552BA
    No stale queue items found for routing group A11E27AE439A582288D4657EDA86B565
    No stale queue items found for routing group A9B10C76E764556FAEA3E47301EDF518
    No stale queue items found for routing group AEA2699E74ED59848ACEA7896699430D
    No stale queue items found for routing group B269961603E75065AFDA4F4F006DA5E4
    No stale queue items found for routing group BB873D9A3DA959DAB2FD743E5AA619F7
    No stale queue items found for routing group BCC6A48FBA2454B79B9EDB276657A404
    No stale queue items found for routing group C8EF4805722B5F6C876EBC0440B420FD
    No stale queue items found for routing group CA38EBDAC4845489ACE208C2240E4056
    No stale queue items found for routing group F5921887DB025C5F908CE42DB7F1AEE8
    No stale queue items found for routing group F9E606A825395422B3BF7A01ECBB7B1F
    Writing log: M:\Dev\Server\ResKit\StorageService\CleanupStorageServiceData.Log_20121009_151040
    Tool has finished execution.  Errors encountered: 0
    C:\Program Files\Microsoft Lync Server 2013\ResKit\StorageService>

</div>

</div>

<div>

## <a name="dbanalyze"></a><span data-ttu-id="7f995-389">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="7f995-389">DBAnalyze</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7f995-390">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f995-390">Description</span></span>

<span data-ttu-id="7f995-391">DBAnalyze è uno strumento della riga di comando che consente agli amministratori di raccogliere report di analisi sui database di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-391">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Lync Server 2013 databases.</span></span> <span data-ttu-id="7f995-392">DBAnalyze ha le modalità seguenti: diagnostica, dati utente, conferenza, MCU e frammentazione del disco:</span><span class="sxs-lookup"><span data-stu-id="7f995-392">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

  - <span data-ttu-id="7f995-393">**La modalità**   diagnostica crea un report che include informazioni sulle tabelle (numero di record, frammentazione, dimensioni dei dati e dimensioni degli indici, dimensioni dei file di dati e di log, l'ultima ora di backup, distribuzione di contatti tra i server che esegue Microsoft Office Communications Server, il numero medio di autorizzazioni, contatti, contenitori, abbonamenti, pubblicazioni, endpoint per utente, utenti non correttamente ospitati, utenti non instradabili, numero medio di conferenze organizzate per utente, programmate conferenze, conferenze attive e versione del database.</span><span class="sxs-lookup"><span data-stu-id="7f995-393">**Diagnostic mode**   Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can’t be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f995-394">L'esecuzione della modalità diagnostica può influire sulle prestazioni del server.</span><span class="sxs-lookup"><span data-stu-id="7f995-394">Running diagnostic mode can affect server performance.</span></span>

    
    </div>

  - <span data-ttu-id="7f995-395">La   **modalità dati utente** segnala il contatto, il contenitore, l'abbonamento, la pubblicazione, l'autorizzazione e i dati del gruppo di contatti per un utente specificato o per gli utenti che hanno tale utente negli elenchi contatti e autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="7f995-395">**User data mode**  Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="7f995-396">Questa modalità riporta anche i dati di riepilogo per le conferenze a cui un utente organizza o è invitato.</span><span class="sxs-lookup"><span data-stu-id="7f995-396">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

  - <span data-ttu-id="7f995-397">**La modalità**   conferenza riporta i dati dettagliati per una conferenza specifica, inclusi tutti i dettagli relativi alla programmazione per la conferenza, l'elenco di invitati, l'elenco dei tipi di elementi multimediali consentiti per la conferenza, il MCU attivo (unità di controllo multipunto), l'elenco dei partecipanti attivi e lo stato di segnalazione di ogni partecipante.</span><span class="sxs-lookup"><span data-stu-id="7f995-397">**Conference mode**   Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant’s signaling state.</span></span>

  - <span data-ttu-id="7f995-398">**Decodificare l'ID**  riunione decodifica un ID riunione PSTN (Public Switched Telephone Network) specificato dall'opzione **/pstnid** , ma non si connette al back-end per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="7f995-398">**Decode Meeting ID**  Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

  - <span data-ttu-id="7f995-399">**Resolve Conference**   consente di decodificare un ID riunione PSTN specificato dall'opzione **/pstnid** e di visualizzare le informazioni sulla Conferenza indicata dall'ID.</span><span class="sxs-lookup"><span data-stu-id="7f995-399">**Resolve conference**   Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

  - <span data-ttu-id="7f995-400">**La modalità**  MCU segnala l'ID, il tipo di elemento multimediale, l'URL, lo stato di heartbeat, il carico delle conferenze e il carico dei partecipanti per ogni MCU nel pool.</span><span class="sxs-lookup"><span data-stu-id="7f995-400">**MCUs mode**  Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

  - <span data-ttu-id="7f995-401">**La modalità**  di frammentazione del disco Visualizza lo stato di frammentazione di tutti i dischi.</span><span class="sxs-lookup"><span data-stu-id="7f995-401">**Disk fragmentation mode**  Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="7f995-402">Questo strumento può essere usato per diagnosticare vari problemi o per aiutare gli amministratori con la pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="7f995-402">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="7f995-403">Ad esempio, se la maggior parte degli utenti ospitati nel server A sceglie utenti ospitati nel server B come contatti, l'amministratore può trasferire gli utenti nel server a nel server B per ridurre il traffico tra server.</span><span class="sxs-lookup"><span data-stu-id="7f995-403">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="7f995-404">Output</span><span class="sxs-lookup"><span data-stu-id="7f995-404">Output</span></span>

<span data-ttu-id="7f995-405">Questo strumento restituisce i report predefiniti relativi al database di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-405">This tool outputs predefined reports about the Lync Server 2013 database.</span></span> <span data-ttu-id="7f995-406">**Percorso:** % ProgramFiles%\\Microsoft Lync Server 2013\\reskit</span><span class="sxs-lookup"><span data-stu-id="7f995-406">**Path:** %ProgramFiles%\\Microsoft Lync Server 2013\\Reskit</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="7f995-407">Scopo</span><span class="sxs-lookup"><span data-stu-id="7f995-407">Purpose</span></span>

<span data-ttu-id="7f995-408">Per installare Dbanalyze. exe, copiarlo in una cartella locale e quindi eseguire lo strumento.</span><span class="sxs-lookup"><span data-stu-id="7f995-408">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="7f995-409">Per usare lo strumento, eseguire il comando seguente dalla riga di comando.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span><span class="sxs-lookup"><span data-stu-id="7f995-409">To use the tool, run the following command from the command line.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span></span> <span data-ttu-id="7f995-410">Di seguito sono elencate le descrizioni delle opzioni della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="7f995-410">The descriptions for the command-line options are shown below.</span></span>

<span data-ttu-id="7f995-411">![Opzioni della riga di comando per Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Opzioni della riga di comando per Dbanalyze.exe.")</span><span class="sxs-lookup"><span data-stu-id="7f995-411">![Command line options for Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Command line options for Dbanalyze.exe.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7f995-412">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f995-412">Requirements</span></span>

<span data-ttu-id="7f995-413">**Computer** DBAnalyze può essere eseguito solo da un computer collegato al dominio in cui è installato Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-413">**Computer** DBAnalyze can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span>

<span data-ttu-id="7f995-414">**Rete** Il computer dovrebbe essere in grado di connettersi al database back-end.</span><span class="sxs-lookup"><span data-stu-id="7f995-414">**Network** The computer should be able to connect to the back-end database.</span></span>

<span data-ttu-id="7f995-415">**Software** I componenti software di Lync Server 2013 devono essere installati prima di eseguire DBAnalyze.</span><span class="sxs-lookup"><span data-stu-id="7f995-415">**Software** Lync Server 2013 software components must be installed before running DBAnalyze.</span></span>

<span data-ttu-id="7f995-416">**Utenti** La tabella seguente Mostra gli amministratori che dispongono delle autorizzazioni necessarie per accedere ai database di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-416">**Users**The table below shows the administrators who have the necessary permissions to access Lync Server 2013 databases.</span></span>

<span data-ttu-id="7f995-417">![Tabella di autorizzazioni per Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Tabella di autorizzazioni per Dbanalyze.exe.")</span><span class="sxs-lookup"><span data-stu-id="7f995-417">![Permissions table for Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Permissions table for Dbanalyze.exe.")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f995-418">È necessario un account di amministratore locale per <STRONG>/report: modalità disco</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="7f995-418">A local administrator account is required for <STRONG>/report:disk</STRONG> mode.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7f995-419">Esempi</span><span class="sxs-lookup"><span data-stu-id="7f995-419">Examples</span></span>

<span data-ttu-id="7f995-420">Di seguito sono riportati alcuni esempi di comandi Dbanalyze. exe validi:</span><span class="sxs-lookup"><span data-stu-id="7f995-420">The following are examples of valid Dbanalyze.exe commands:</span></span>

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a><span data-ttu-id="7f995-421">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="7f995-421">Summary</span></span>

<span data-ttu-id="7f995-422">DBAnalyzer consente agli amministratori di analizzare rapidamente e facilmente i database di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-422">DBAnalyzer provides administrators a quick and easy to analyze Lync Server 2013 databases.</span></span>

</div>

</div>

<div>

## <a name="importstorageservicedata"></a><span data-ttu-id="7f995-423">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="7f995-423">ImportStorageServiceData</span></span>

<span data-ttu-id="7f995-424">Lo strumento ImportStorageServiceData Resource Kit consente di riimportare i dati di Accodamento e endpoint che sono stati svuotati dal servizio di archiviazione (LYSS) di nuovo nel servizio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="7f995-424">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7f995-425">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f995-425">Description</span></span>

<span data-ttu-id="7f995-426">I dati svuotati del servizio di archiviazione avrebbero potuto essere automatici (periodici) in base allo stato dell'elemento della coda o alle dimensioni del database.</span><span class="sxs-lookup"><span data-stu-id="7f995-426">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="7f995-427">Potrebbe essere accaduto a causa della chiamata manuale del cmdlet di failover del pool o del cmdlet StorageServiceFullFlush (che richiama il cmdlet di failover del pool).</span><span class="sxs-lookup"><span data-stu-id="7f995-427">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="7f995-428">Tieni presente che i dati non devono essere reimportati idealmente se una delle dimensioni del database del servizio di archiviazione (LYSS) nei Front Ends è superiore al livello normale, perché in questo modo probabilmente causerà l'esportazione di più dati. Inoltre, gli eventuali problemi che potrebbero avere contribuito agli errori che hanno causato l'aumento della coda del servizio di archiviazione devono essere risolti prima di tutto, ad esempio gli errori degli endpoint di Exchange, i problemi di rete o altri problemi.</span><span class="sxs-lookup"><span data-stu-id="7f995-428">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

<span data-ttu-id="7f995-429">**Scenario 1:** durante il failover del pool, i file possono essere svuotati dal servizio di archiviazione per ogni front-end.</span><span class="sxs-lookup"><span data-stu-id="7f995-429">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="7f995-430">Dopo aver completato il failover, lo strumento deve essere eseguito per reimportare i dati.</span><span class="sxs-lookup"><span data-stu-id="7f995-430">After failover is completed, the tool should be run to re-import the data.</span></span>

<span data-ttu-id="7f995-431">**Scenario 2:** i dati vengono svuotati automaticamente ogni giorno o in risposta al database del servizio di archiviazione che supera determinate soglie di dimensione (ad esempio 60%, 80%, 90% Full).</span><span class="sxs-lookup"><span data-stu-id="7f995-431">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="7f995-432">I dati scaricati automaticamente devono essere reimportati di routine dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="7f995-432">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="7f995-433">Nella situazione precedente, se il monitoraggio SCOM Pack non è distribuito, esistono eventi per il servizio di archiviazione di Lync Server relativo ai dati da svuotare dal servizio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="7f995-433">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Lync Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="7f995-434">ID evento di 32075 (operazione di svuotamento completo), 32076 (il colore completo è completato), 32082 (livello di manutenzione a filo iniziato), 32083 (livello di manutenzione), 32089 (lo svuotamento si è verificato a causa del riempimento del database).</span><span class="sxs-lookup"><span data-stu-id="7f995-434">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="7f995-435">Nota Questi ID evento corrispondono alla versione RTM.</span><span class="sxs-lookup"><span data-stu-id="7f995-435">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="7f995-436">Quando un amministratore vede questi eventi, significa che ci sono file che sono stati svuotati. Questi dati devono essere di routine importati di nuovo usando questo strumento, ad esempio una volta alla settimana.</span><span class="sxs-lookup"><span data-stu-id="7f995-436">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="7f995-437">Per la versione del servizio online, se è distribuito SCOM Pack per Lync Server, è possibile che vengano generati nuovi avvisi che chiedano all'amministratore di reimportare nuovamente i dati svuotati in un servizio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="7f995-437">For the Online Service release, if health monitoring SCOM pack for Lync Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="7f995-438">Verrà visualizzato un evento corrispondente nel log eventi del server front-end che ha attivato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="7f995-438">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="7f995-439">L'evento darà una descrizione del percorso padre in cui si trovano i file di dati svuotati, nonché il numero di file che soddisfano i criteri di avviso.</span><span class="sxs-lookup"><span data-stu-id="7f995-439">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="7f995-440">I criteri di avviso sono che ci sono X o più file sotto il percorso padre specifico che hanno almeno Y giorni prima (dove X e Y sono preimpostati all'interno del StorageService ma possono essere ignorati modificando il file APPCONFIG). Di seguito sono illustrati due esempi di eventi che possono attivare l'avviso di integrità, con la differenza che è il percorso padre.</span><span class="sxs-lookup"><span data-stu-id="7f995-440">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="7f995-441">Una possibilità è in condivisione file del servizio Web, mentre l'altra possibilità è la directory dei dati dell'applicazione locale di ogni front-end.</span><span class="sxs-lookup"><span data-stu-id="7f995-441">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="7f995-442">(ad esempio c:\\ProgramData\\Microsoft\\Lync Server\\StorageService).</span><span class="sxs-lookup"><span data-stu-id="7f995-442">( for example c:\\ProgramData\\Microsoft\\Lync Server\\StorageService ).</span></span> <span data-ttu-id="7f995-443">L'amministratore eseguirà quindi questo strumento di reskit.</span><span class="sxs-lookup"><span data-stu-id="7f995-443">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="7f995-444">Questo strumento incrementerà il carico di CPU e IO nella parte anteriore in cui è in esecuzione, oltre ad altri front ends, nella situazione in cui i dati non sono di proprietà del front-end in cui viene eseguito lo strumento.</span><span class="sxs-lookup"><span data-stu-id="7f995-444">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="7f995-445">Ti consigliamo di Runng questo strumento quando i Front ends non sono sotto il carico di CPU e IO elevato, ad esempio al di fuori delle ore di punta.</span><span class="sxs-lookup"><span data-stu-id="7f995-445">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="7f995-446">In secondo luogo, questo strumento può eseguire da 2 a 3 minuti per importare un file di dati.</span><span class="sxs-lookup"><span data-stu-id="7f995-446">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="7f995-447">Tieni presente quando valuti quanto tempo verrà eseguito lo strumento. Il file di log dettagliato generato dallo strumento verrà visualizzato per impostazione predefinita nell'archivio file.</span><span class="sxs-lookup"><span data-stu-id="7f995-447">Keep this in mind when estimating how long tool will be running.The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="7f995-448">Eliminarlo se non sono stati segnalati errori, perché il file di log può essere di decine di MB o più.</span><span class="sxs-lookup"><span data-stu-id="7f995-448">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

<span data-ttu-id="7f995-449">![Esempio di eventi nel registro eventi del server di archiviazione.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Esempio di eventi nel registro eventi del server di archiviazione.")</span><span class="sxs-lookup"><span data-stu-id="7f995-449">![Sample Storage Server event log events.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Sample Storage Server event log events.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7f995-450">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f995-450">Requirements</span></span>

<span data-ttu-id="7f995-451">Installare gli strumenti di Lync Server 2013, Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="7f995-451">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="7f995-452">Lo strumento viene eseguito in computer Uniti a un dominio in cui sono installati Lync Server e Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7f995-452">The tool runs on domain-joined machines where Lync Server and Lync Server Management Shell are installed.</span></span> <span data-ttu-id="7f995-453">Lo strumento usa un cmdlet di Management Shell per identificare tutti i server front-end nel pool.</span><span class="sxs-lookup"><span data-stu-id="7f995-453">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="7f995-454">In secondo luogo, lo strumento deve essere eseguito da un computer nel pool in cui è installato il database **RtcLocal** .</span><span class="sxs-lookup"><span data-stu-id="7f995-454">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="7f995-455">Questo database viene usato dallo strumento per recuperare la posizione della condivisione di file WEBSERVICE per il pool. Inoltre, prima di usare lo strumento, ogni server front-end deve prima consentire la comunicazione remota di Windows PowerShell tramite **Enable-PSRemoting** su ogni server front-end e il computer da cui viene eseguito lo strumento.</span><span class="sxs-lookup"><span data-stu-id="7f995-455">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="7f995-456">In caso contrario, i comandi remoti di Windows PowerShell da questo strumento avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="7f995-456">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="7f995-457">La comunicazione remota di Windows PowerShell può essere disattivata in tutti i server front-end nel pool al termine dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="7f995-457">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="7f995-458">Infine, l'account o le credenziali che richiamano lo strumento devono avere l'autorizzazione di lettura/scrittura per la condivisione di file WebService per il pool in cui eseguono questo strumento.</span><span class="sxs-lookup"><span data-stu-id="7f995-458">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="7f995-459">In caso contrario, lo strumento non riuscirà con gli errori di autorizzazione IO.</span><span class="sxs-lookup"><span data-stu-id="7f995-459">Otherwise the tool will fail with IO Permission errors.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f995-460">In Windows Server 2012 la comunicazione remota di Windows PowerShell è abilitata per impostazione predefinita, ma non nel sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="7f995-460">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7f995-461">Esempi</span><span class="sxs-lookup"><span data-stu-id="7f995-461">Examples</span></span>

    >  C:\StorageService>ImportStorageServiceData.exe
    Description:
    This tool will re-import Storage Service (LYSS) flushed queue data back in.  For a pool: you are required to run this tool on a machine inside the pool which has the Lync Server Management Shell installed.  Additionally, all front end machines need to have Windows Powershell Remoting enabled before executing this tool by executing Enable-PSRemoting.  Also, please ensure that all Storage Service instance DB Size are at the 'Normal' level (verify this by viewing Eventlog events). Otherwise re-importing may cause data to be flushed out again if any Storage Service instance DB size level goes above 'Normal'.
    Usage: Default behavior is to Import data from web service file share as well as any files on all Front End machines in pool.
    Additional Options:
    -Verbose                    : Turn verbose output on.
    
    -StorageServiceHostName     : Host Name of Storage Service WCF endpoint.  ( Default=localhost netnamedpipe binding. )
                                        
    -FileSharePath              : Import only all data from just under the UNC path specified.
    
    ActivityID: cc3b62ff-bb66-4e61-a6e2-96cb3626315c. <-- Use this to correlate with StorageService trace logs if troubleshooting.
    Type Server name (TCP binding) or press <enter> for localhost (NamePipe binding):
    Using NetNamedPipeBinding...
    OnTopologyChanged Event received
    Web Service File Share: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService
    
    Front Ends:
    server.vdomain.com
    server2.vdomain.com
    server1.vdomain.com
    server3.vdomain.com
    Looking under directory: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService for exported data.
    # Files found: 8
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    Items deserialized: 20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml
    
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d
    3832e4__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c
    86684d3832e4__0.xml
    
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml
    
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server2.vdom
    ain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42
    287dd6__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2
    b46a42287dd6__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml
    
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=1
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15
    d251e6__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759
    e08a15d251e6__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=1
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346949ff8
    17c220__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346
    949ff817c220__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml: succeeded: 20, failed: 0
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml
    
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=20
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be6
    6d5317__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876
    749be66d5317__0.xml
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml: succeeded: 20, failed: 0
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=20
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda
    86b565__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4
    657eda86b565__0.xml
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml: succeeded: 20, failed: 0
    All files have been imported into Storage Service for path: \\dc.vdomain.com\OcsFileStore\co1-WebSer
    vices-1\StorageService
    Importing files for: server.vdomain.com
    No files founds.
    Importing files for: server2.vdomain.com
    No files founds.
    Importing files for: server1.vdomain.com
    No files founds.
    Importing files for: server3.vdomain.com
    No files founds.
    Writing log: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\ImportStorageServiceData
    Log20120910_1609SS
    Tool has finished execution.
    >  C:\StorageService>

</div>

</div>

<div>

## <a name="lcssync"></a><span data-ttu-id="7f995-462">LCSSync</span><span class="sxs-lookup"><span data-stu-id="7f995-462">LCSSync</span></span>

<span data-ttu-id="7f995-463">Lo strumento LCSSync consente di distribuire il software di comunicazione di Lync Server 2013 in un ambiente con più insiemi di strutture.</span><span class="sxs-lookup"><span data-stu-id="7f995-463">The LCSSync tool helps to deploy Lync Server 2013 communications software in a multi-forest environment.</span></span> <span data-ttu-id="7f995-464">Questo strumento viene usato per sincronizzare utenti e gruppi di foreste di utenti diversi come un oggetto contatto di servizi di dominio Active Directory in una foresta centrale in cui è installato Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-464">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Lync Server 2013 is installed.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7f995-465">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f995-465">Description</span></span>

<span data-ttu-id="7f995-466">LCSSync usa gli oggetti contatto di servizi di dominio Active Directory sincronizzati nella foresta centrale per consentire agli utenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7f995-466">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Lync Server.</span></span> <span data-ttu-id="7f995-467">Per specificare Single Sign-in, l'account utente principale deve essere mappato all'oggetto contatto Active Directory Domain Services nella foresta centrale per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-467">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Lync Server 2013.</span></span> <span data-ttu-id="7f995-468">Questo strumento consente di eseguire tale mapping.</span><span class="sxs-lookup"><span data-stu-id="7f995-468">This tool helps perform that mapping.</span></span> <span data-ttu-id="7f995-469">Questo strumento include modelli per la creazione di agenti di gestione in Microsoft Identity Integration Server.</span><span class="sxs-lookup"><span data-stu-id="7f995-469">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="7f995-470">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="7f995-470">Summary</span></span>

<span data-ttu-id="7f995-471">Lo strumento LCSSync consente di distribuire Lync Server in un ambiente con più insiemi di strutture.</span><span class="sxs-lookup"><span data-stu-id="7f995-471">The LCSSync tool helps to deploy Lync Server in a multi-forest environment.</span></span>

</div>

</div>

<div>

## <a name="lookupuserconsole"></a><span data-ttu-id="7f995-472">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="7f995-472">LookupUserConsole</span></span>

<span data-ttu-id="7f995-473">Lo strumento LookupUserConsole Visualizza le informazioni di routing interne di Lync Server su utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="7f995-473">The LookupUserConsole tool displays internal Lync Server routing information about specific users.</span></span> <span data-ttu-id="7f995-474">Queste informazioni possono essere utili per il supporto Microsoft personale per la diagnosi dei problemi di distribuzione e routing.</span><span class="sxs-lookup"><span data-stu-id="7f995-474">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7f995-475">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f995-475">Description</span></span>

<span data-ttu-id="7f995-476">L'esecuzione di LookupUserConsole. exe aprirà un prompt dei comandi che accetta gli indirizzi SIP e tenta di visualizzare le informazioni di routing interne di Lync Server che li riguardano.</span><span class="sxs-lookup"><span data-stu-id="7f995-476">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Lync Server routing information relating them.</span></span> <span data-ttu-id="7f995-477">Digitare **Exit** per chiudere lo strumento LookupUserConsole.</span><span class="sxs-lookup"><span data-stu-id="7f995-477">Type **exit** to quit the LookupUserConsole tool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7f995-478">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f995-478">Requirements</span></span>

<span data-ttu-id="7f995-479">Installare gli strumenti di Lync Server 2013, Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="7f995-479">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="7f995-480">Lo strumento viene eseguito in computer Uniti a un dominio in cui è installato Lync Server</span><span class="sxs-lookup"><span data-stu-id="7f995-480">The tool runs on domain-joined machines where Lync Server is installed</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7f995-481">Esempi</span><span class="sxs-lookup"><span data-stu-id="7f995-481">Examples</span></span>

<span data-ttu-id="7f995-482">C:\\programmi\\Microsoft Lync Server 2013\\reskit\>LookupUserConsole. exe</span><span class="sxs-lookup"><span data-stu-id="7f995-482">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole.exe</span></span>

    > sip:john.doe@vdomain.com
    
      Execution time (ms):                            171.094
      Exeuction result:                               Success
      SIP URI:                                        sip:john.doe@vdomain.com
      User info:
        SID:                                          S-1-5-21-2831376166-29632525...    Display name:                                     John Doe
        Grouping ID:                                  00000000-0000-0000-0000-...
        Line URI:                                     <null>
        Policy assignment:                            TenantId={00000000--0000-000....
        SIP enabled:                                  True
        UC enabled:                                   False
        Tenant ID:                                    00000000-0000-0000-0000-...  Cluster info:
        Active cluster:                               pool0.vdomain.com
        Backup registrar cluster:                     <null>
        Deployment location:                          <null>
        Home Front-End FQDN:                          SERVER.vdomain.com
        Primary Registrar cluster:                    pool0.vdomain.com
        Remote Director external SIP FQDN:            <null>
        Remote Director internal SIP FQDN:            <null>
        Remote Director Web FQDN:                     <null>
        Routing group ID:                             4501e04e-ae48-5605-9346...
        Service tag ID:                               1266953005
        User Front-End resolved:                      True
        User in local forest:                         True
        User in remote forest:                        False
        User in split domain:                         False
        User-Services cluster:                        pool0.vdomain.com
    
    > sip:nouser@vdomain.com
    
      Execution time (ms):                            948.7574
      Exeuction result:                               UserDoesNotExist
    
    > exit

</div>

</div>

<div>

## <a name="msturnping"></a><span data-ttu-id="7f995-483">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="7f995-483">MsTurnPing</span></span>

<span data-ttu-id="7f995-484">Lo strumento MSTurnPing consente a un amministratore del software di comunicazione di Microsoft Lync Server 2013 di controllare lo stato dei server che gestiscono i servizi di autenticazione audio/video e di video, nonché i server che gestiscono i servizi per i criteri di larghezza di banda nella topologia.</span><span class="sxs-lookup"><span data-stu-id="7f995-484">The MSTurnPing tool allows an administrator of Microsoft Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7f995-485">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f995-485">Description</span></span>

<span data-ttu-id="7f995-486">Lo strumento MSTurnPing consente a un amministratore del software di comunicazione di Lync Server 2013 di controllare lo stato dei server che gestiscono i servizi audio/video e di autenticazione audio/video, nonché i server che gestiscono i servizi per i criteri di larghezza di banda nella topologia.</span><span class="sxs-lookup"><span data-stu-id="7f995-486">The MSTurnPing tool allows an administrator of Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="7f995-487">Lo strumento consente all'amministratore di eseguire i test seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f995-487">The tool allows the administrator to perform the following tests:</span></span>

1.  <span data-ttu-id="7f995-488">Test a/V Edge Server: lo strumento esegue i test su tutti i/V Edge Server della topologia eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f995-488">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="7f995-489">Verificare che il servizio di autenticazione audio/video di Lync Server sia avviato e possa emettere le credenziali appropriate.</span><span class="sxs-lookup"><span data-stu-id="7f995-489">Verifying that the Lync Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="7f995-490">Verificando che il servizio Edge audio/video di Lync Server sia stato avviato e possa allocare le risorse sul bordo esterno correttamente.</span><span class="sxs-lookup"><span data-stu-id="7f995-490">Verifying that the Lync Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2.  <span data-ttu-id="7f995-491">Test del servizio criteri di larghezza di banda: lo strumento esegue i test in tutti i server che eseguono i servizi per i criteri di larghezza di banda nella topologia eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f995-491">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="7f995-492">Verificare che il servizio di criteri di larghezza di banda di Lync Server (autenticazione) sia avviato e possa emettere credenziali appropriate.</span><span class="sxs-lookup"><span data-stu-id="7f995-492">Verifying that the Lync Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="7f995-493">Verificare che il servizio di criteri di larghezza di banda di Lync Server sia stato avviato e che sia possibile eseguire il controllo della larghezza di banda correttamente.</span><span class="sxs-lookup"><span data-stu-id="7f995-493">Verifying that the Lync Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="7f995-494">Questo strumento deve essere eseguito da un computer che fa parte della topologia e ha installato lo Store locale.</span><span class="sxs-lookup"><span data-stu-id="7f995-494">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="7f995-495">Output</span><span class="sxs-lookup"><span data-stu-id="7f995-495">Output</span></span>

<span data-ttu-id="7f995-496">Lo strumento restituisce i risultati di ogni operazione.</span><span class="sxs-lookup"><span data-stu-id="7f995-496">The tool outputs the results of each of the operations.</span></span>

  - <span data-ttu-id="7f995-497">Se viene eseguito il test **AudioVideoEdgeServer** , gli output degli strumenti sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f995-497">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="7f995-498">Risultati del test dei computer che includono il servizio di autenticazione audio/video di Lync Server nella topologia</span><span class="sxs-lookup"><span data-stu-id="7f995-498">The test results of the computers that provide the Lync Server Audio/Video Authentication service in the topology</span></span>
    
      - <span data-ttu-id="7f995-499">Risultati del test dei computer che includono il servizio Edge audio/video di Lync Server nella topologia</span><span class="sxs-lookup"><span data-stu-id="7f995-499">The test results of the computers that provide the Lync Server Audio/Video Edge service in the topology</span></span>

  - <span data-ttu-id="7f995-500">Se viene eseguito il test **BandwidthPolicyServer** , gli output degli strumenti sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f995-500">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="7f995-501">Risultati del test dei computer che includono il servizio di criteri di larghezza di banda di Lync Server (autenticazione) nella topologia</span><span class="sxs-lookup"><span data-stu-id="7f995-501">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Authentication) in the topology</span></span>
    
      - <span data-ttu-id="7f995-502">I risultati del test dei computer che includono il servizio dei criteri di larghezza di banda di Lync Server nella topologia</span><span class="sxs-lookup"><span data-stu-id="7f995-502">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Core) in the topology</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7f995-503">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f995-503">Requirements</span></span>

  - <span data-ttu-id="7f995-504">Questo strumento deve essere eseguito da un computer che si trova nella topologia e che contiene lo Store locale.</span><span class="sxs-lookup"><span data-stu-id="7f995-504">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

  - <span data-ttu-id="7f995-505">Lo strumento deve essere eseguito come amministratore che ha accesso allo Store locale.</span><span class="sxs-lookup"><span data-stu-id="7f995-505">The tool must be run as an administrator who has access to the local store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7f995-506">Esempi</span><span class="sxs-lookup"><span data-stu-id="7f995-506">Examples</span></span>

<span data-ttu-id="7f995-507">Di seguito è riportato un esempio di input dello strumento.</span><span class="sxs-lookup"><span data-stu-id="7f995-507">The following is an example of the tool input.</span></span>

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a><span data-ttu-id="7f995-508">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="7f995-508">Summary</span></span>

<span data-ttu-id="7f995-509">Questo strumento può essere una risorsa preziosa per gli amministratori di Lync Server 2013 che vogliono controllare lo stato dei server in cui sono in uso servizi per i criteri di larghezza di banda e audio/video.</span><span class="sxs-lookup"><span data-stu-id="7f995-509">This tool can be a valuable resource to Lync Server 2013 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a><span data-ttu-id="7f995-510">Visualizzatore Configurazione di rete</span><span class="sxs-lookup"><span data-stu-id="7f995-510">Network Configuration Viewer</span></span>

<span data-ttu-id="7f995-511">Il Visualizzatore di configurazione di rete può essere usato dagli amministratori del software di comunicazione di Microsoft Lync Server 2013 per visualizzare la topologia di rete di controllo di ammissione di chiamata (CAC) per un'organizzazione che ha eseguito il provisioning per consentire sessioni di comunicazione in tempo reale, ad esempio Voice o videochiamate in base alla capacità di larghezza di banda specificata.</span><span class="sxs-lookup"><span data-stu-id="7f995-511">Network Configuration Viewer can be used by Microsoft Lync Server 2013 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="7f995-512">Gli amministratori di Lync Server 2013 definiscono i criteri CAC applicati dai servizi per i criteri di larghezza di banda installati con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-512">Lync Server 2013 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Lync Server 2013.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7f995-513">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f995-513">Description</span></span>

<span data-ttu-id="7f995-514">Network Configuration Viewer (NetworkConfigurationViewer. exe) consente agli amministratori di eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f995-514">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

  - <span data-ttu-id="7f995-515">Caricare e visualizzare la topologia di rete CAC da una distribuzione di Lync Server 2013 in un formato grafico.</span><span class="sxs-lookup"><span data-stu-id="7f995-515">Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format.</span></span>

  - <span data-ttu-id="7f995-516">Caricare e visualizzare la topologia di rete CAC da un file di log del server dei criteri di larghezza di banda in formato grafico.</span><span class="sxs-lookup"><span data-stu-id="7f995-516">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

  - <span data-ttu-id="7f995-517">Salvare e archiviare la topologia di rete CAC in un formato XML sul disco.</span><span class="sxs-lookup"><span data-stu-id="7f995-517">Save and store CAC network topology in an XML format on the disk.</span></span>

  - <span data-ttu-id="7f995-518">Salvare e archiviare il diagramma della topologia di rete CAC in formato JPG o BMP.</span><span class="sxs-lookup"><span data-stu-id="7f995-518">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

  - <span data-ttu-id="7f995-519">Visualizzare i dati di configurazione della topologia di rete CAC.</span><span class="sxs-lookup"><span data-stu-id="7f995-519">View CAC network topology configuration data.</span></span>

  - <span data-ttu-id="7f995-520">Visualizzare la topologia di rete CAC in uno stile di visualizzazione albero.</span><span class="sxs-lookup"><span data-stu-id="7f995-520">View CAC network topology in a tree-view style.</span></span>

  - <span data-ttu-id="7f995-521">Definire connettori personalizzati per i collegamenti alla topologia di rete CAC, ad esempio i collegamenti da sito a area geografica, da area geografica e da sito a sito.</span><span class="sxs-lookup"><span data-stu-id="7f995-521">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

  - <span data-ttu-id="7f995-522">Visualizzare le informazioni sul sito della topologia di rete CAC, le informazioni sulle aree geografiche e i collegamenti di rete con provisioning.</span><span class="sxs-lookup"><span data-stu-id="7f995-522">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="7f995-523">Scopo</span><span class="sxs-lookup"><span data-stu-id="7f995-523">Purpose</span></span>

<span data-ttu-id="7f995-524">Visualizzare i collegamenti della topologia di rete Enterprise CAC in un'interfaccia grafica.</span><span class="sxs-lookup"><span data-stu-id="7f995-524">View enterprise CAC network topology links in a graphical interface.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7f995-525">Esempi</span><span class="sxs-lookup"><span data-stu-id="7f995-525">Examples</span></span>

<span data-ttu-id="7f995-526">**Caricare e visualizzare la topologia di rete CAC da una distribuzione di Lync Server 2013 in un formato grafico:** Gli amministratori di Lync Server 2013 possono caricare e visualizzare la configurazione della topologia di rete CAC in qualsiasi computer Lync Server 2013 usando l'opzione di **configurazione della rete download** , come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="7f995-526">**Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format:** Lync Server 2013 administrators can load and view CAC network topology configuration on any Lync Server 2013 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="7f995-527">Lo strumento non riesce a scaricare o visualizzare tale configurazione quando viene distribuita in un computer in cui non è disponibile la connettività allo Store di configurazione di Lync.</span><span class="sxs-lookup"><span data-stu-id="7f995-527">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Lync configuration store.</span></span>

<span data-ttu-id="7f995-528">![Download della configurazione di rete.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Download della configurazione di rete.")</span><span class="sxs-lookup"><span data-stu-id="7f995-528">![Downloading the network configuration.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Downloading the network configuration.")</span></span>

<span data-ttu-id="7f995-529">**Caricare e visualizzare la topologia di rete CAC da un file di log del server dei criteri di larghezza di banda in formato grafico:** I server dei criteri di larghezza di banda di Lync Server 2013 salvano la topologia di rete CAC come parte del meccanismo di registrazione nel percorso di condivisione file di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-529">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Lync Server 2013 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Lync Server 2013 file share location.</span></span> <span data-ttu-id="7f995-530">Gli amministratori di Lync Server possono visualizzare un file di questo tipo in un formato grafico usando l'opzione di **configurazione della rete aperta** , come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="7f995-530">Lync Server administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

<span data-ttu-id="7f995-531">![Apertura di un file di log del server criteri larghezza di banda.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Apertura di un file di log del server criteri larghezza di banda.")</span><span class="sxs-lookup"><span data-stu-id="7f995-531">![Opening a Bandwidth Policy Server log file.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Opening a Bandwidth Policy Server log file.")</span></span>

<span data-ttu-id="7f995-532">Salvare e archiviare la topologia di rete CAC in un formato XML sul disco: gli amministratori di Lync Server 2013 possono salvare il file di configurazione della topologia di rete CAC in un formato XML usando l'opzione **Salva una copia di configurazione di rete** , come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="7f995-532">Save and store CAC network topology in an XML format on the disk: Lync Server 2013 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="7f995-533">Il file di configurazione salvato può quindi essere usato offline per scopi di visualizzazione grafica.</span><span class="sxs-lookup"><span data-stu-id="7f995-533">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

<span data-ttu-id="7f995-534">![Salvataggio della configurazione di rete come file XML.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Salvataggio della configurazione di rete come file XML.")</span><span class="sxs-lookup"><span data-stu-id="7f995-534">![Saving the network configuration as an XML file.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Saving the network configuration as an XML file.")</span></span>

<span data-ttu-id="7f995-535">Salvare e archiviare il diagramma della topologia di rete CAC in formato JPG o BMP: gli amministratori di Lync Server 2013 possono salvare la configurazione della topologia di rete CAC in un formato grafico (formati di file JPG e BMP) usando l'opzione **Salva diagramma configurazione di rete come immagine** come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="7f995-535">Save and Store CAC network topology diagram in JPG or BMP format: Lync Server 2013 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

<span data-ttu-id="7f995-536">![Salvataggio della configurazione di rete come immagine.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Salvataggio della configurazione di rete come immagine.")</span><span class="sxs-lookup"><span data-stu-id="7f995-536">![Saving the network configuration as a picture.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Saving the network configuration as a picture.")</span></span>

<span data-ttu-id="7f995-537">**Visualizzare i dati di configurazione della topologia di rete CAC:** Gli amministratori di Lync Server 2013 possono visualizzare i dati di configurazione della rete correlati, ad esempio aree di rete, siti di rete, profili di larghezza di banda e indirizzi IP della subnet del sito in un formato testuale usando l'opzione Visualizza dati di configurazione della rete come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="7f995-537">**View CAC network topology configuration data:** Lync Server 2013 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

<span data-ttu-id="7f995-538">![Visualizzazione dei dati sulla configurazione di rete.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Visualizzazione dei dati sulla configurazione di rete.")</span><span class="sxs-lookup"><span data-stu-id="7f995-538">![Viewing network configuration data.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Viewing network configuration data.")</span></span>

<span data-ttu-id="7f995-539">**Visualizzare la topologia di rete CAC in uno stile di visualizzazione ad albero:** Lync Server 2013 gli amministratori possono visualizzare i dati di configurazione della rete correlati in uno stile di visualizzazione ad albero grafico usando il pannello di controllo sul lato sinistro della finestra degli strumenti, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="7f995-539">**View CAC network topology in a tree-view style:** Lync Server 2013 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

<span data-ttu-id="7f995-540">![Visualizzazione dei dati sulla configurazione di rete in una visualizzazione ad albero.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Visualizzazione dei dati sulla configurazione di rete in una visualizzazione ad albero.")</span><span class="sxs-lookup"><span data-stu-id="7f995-540">![Viewing network configuration data in a tree-view.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Viewing network configuration data in a tree-view.")</span></span>

<span data-ttu-id="7f995-541">**Definire connettori personalizzati per i collegamenti alla topologia di rete CAC, ad esempio i collegamenti da sito a area** geografica, dall'area geografica e da sito a sito: Gli amministratori di Lync Server 2013 possono definire connettori grafici personalizzati per i collegamenti WAN della configurazione di rete CAC usando l'opzione impostazioni come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="7f995-541">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Lync Server 2013 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="7f995-542">Questo consente di distinguere tra i vari tipi di collegamenti di rete che vengono provisionati nella configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="7f995-542">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

<span data-ttu-id="7f995-543">![Definire i connettori personalizzati per la topologia di rete Controllo di ammissione di chiamata](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Definire i connettori personalizzati per la topologia di rete Controllo di ammissione di chiamata")</span><span class="sxs-lookup"><span data-stu-id="7f995-543">![Define custom connectors for CAC network topology](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Define custom connectors for CAC network topology")</span></span>

<span data-ttu-id="7f995-544">**Visualizzare informazioni sul sito della topologia di rete CAC, informazioni sulle aree geografiche e criteri di larghezza di banda provisioning:** Gli amministratori di Lync Server 2013 possono visualizzare informazioni relative all'area di rete CAC correlate, informazioni sul sito e informazioni sul provisioning della larghezza di banda di CAC usando le opzioni illustrate di seguito.</span><span class="sxs-lookup"><span data-stu-id="7f995-544">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Lync Server 2013 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="7f995-545">Ad esempio, fare clic su **informazioni** in un'area di rete o in un oggetto sito di rete.</span><span class="sxs-lookup"><span data-stu-id="7f995-545">(For example, click **Info** in a network region or network site object.)</span></span>

<span data-ttu-id="7f995-546">![Definizione di connettori personalizzati per la rete.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Definizione di connettori personalizzati per la rete.")</span><span class="sxs-lookup"><span data-stu-id="7f995-546">![Defining custom connectors for your network.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Defining custom connectors for your network.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="7f995-547">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="7f995-547">Summary</span></span>

<span data-ttu-id="7f995-548">Questo strumento può essere una risorsa preziosa per gli amministratori di Lync Server 2013 che desiderano visualizzare la topologia di rete CAC per la distribuzione in un formato grafico.</span><span class="sxs-lookup"><span data-stu-id="7f995-548">This tool can be a valuable resource to Lync Server 2013 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

</div>

</div>

<div>

## <a name="response-group-agent-live"></a><span data-ttu-id="7f995-549">Agente di Response Group Live</span><span class="sxs-lookup"><span data-stu-id="7f995-549">Response Group Agent Live</span></span>

<span data-ttu-id="7f995-550">L'applicazione Response Group offre agli agenti la possibilità di accedere a informazioni in tempo reale utili usando il servizio Web incorporato.</span><span class="sxs-lookup"><span data-stu-id="7f995-550">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="7f995-551">Sfortunatamente, nessuna visualizzazione grafica di questi dati è disponibile all'esterno dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7f995-551">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="7f995-552">Lo strumento Response Group Agent Live Resource Kit risolve questo problema fornendo un modo semplice e grafico per accedere a queste informazioni, migliorate con le informazioni del software Microsoft Lync 2013 per le comunicazioni in tempo reale, come la presenza di altri agenti.</span><span class="sxs-lookup"><span data-stu-id="7f995-552">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Microsoft Lync 2013 communications software information such as the presence of other agents.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7f995-553">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f995-553">Description</span></span>

<span data-ttu-id="7f995-554">Response Group Agent Live è un'applicazione Windows che fornisce funzionalità di accesso e disconnessione e alcune informazioni in tempo reale, ad esempio l'appartenenza al gruppo e il numero corrente di chiamate, agli agenti del gruppo di risposta.</span><span class="sxs-lookup"><span data-stu-id="7f995-554">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="7f995-555">Si tratta di una versione avanzata della pagina gruppi di agenti (accessibile da Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-555">It is meant to be an enhanced version of the Agent Groups page (accessible from Lync 2013.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="7f995-556">Scopo</span><span class="sxs-lookup"><span data-stu-id="7f995-556">Purpose</span></span>

<span data-ttu-id="7f995-557">L'applicazione Response Group Accoda le chiamate in arrivo e le instrada ai gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="7f995-557">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="7f995-558">Per prendere decisioni informate sulle chiamate al servizio, gli agenti possono accedere a informazioni in tempo reale sui gruppi di agenti, ad esempio gli altri agenti disponibili e il numero di chiamate in attesa in ogni coda.</span><span class="sxs-lookup"><span data-stu-id="7f995-558">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="7f995-559">Queste informazioni, inizialmente accessibili solo tramite il servizio Response Group, vengono messe a disposizione in modo intuitivo dall'agente di Response Group Live.</span><span class="sxs-lookup"><span data-stu-id="7f995-559">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

<div>

## <a name="features"></a><span data-ttu-id="7f995-560">Caratteristiche</span><span class="sxs-lookup"><span data-stu-id="7f995-560">Features</span></span>

<span data-ttu-id="7f995-561">Lo strumento di Response Group Agent Live viene compilato nel servizio Response Group e nell'SDK di Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-561">The Response Group Agent Live tool is built on the Response Group service and the Microsoft Lync 2013 SDK.</span></span> <span data-ttu-id="7f995-562">Fornisce agli agenti del gruppo di risposta le informazioni e le funzionalità disponibili nel servizio Response Group, ad esempio l'appartenenza ai gruppi, la presenza di altri agenti e il numero di chiamate in attesa.</span><span class="sxs-lookup"><span data-stu-id="7f995-562">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="7f995-563">La figura seguente illustra l'interfaccia principale di Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="7f995-563">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

<span data-ttu-id="7f995-564">![Strumento Response Group Agent Live.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "Strumento Response Group Agent Live.")</span><span class="sxs-lookup"><span data-stu-id="7f995-564">![The Response Group Agent Live tool.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "The Response Group Agent Live tool.")</span></span>

<span data-ttu-id="7f995-565">Le tre caratteristiche principali seguenti sono disponibili per gli agenti in Response Group Agent Live:</span><span class="sxs-lookup"><span data-stu-id="7f995-565">The following three main features are available for agents in Response Group Agent Live:</span></span>

  - <span data-ttu-id="7f995-566">**Accesso/uscita:** Contrariamente alla pagina gruppi di agenti (accessibile da Lync 2013), Response Group Agent Live consente solo agli agenti di accedere o disconnettersi da tutti i gruppi di agenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="7f995-566">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Lync 2013), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="7f995-567">Questa applicazione offre tre modi rapidi per l'accesso o la disconnessione degli agenti:</span><span class="sxs-lookup"><span data-stu-id="7f995-567">This application provides three quick ways for agents to sign in or out:</span></span>
    
      - <span data-ttu-id="7f995-568">Fare clic sui pulsanti di accesso/uscita (verde e rosso) all'interno dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7f995-568">Click the Sign-in/out (green and red) buttons within the application.</span></span>
    
      - <span data-ttu-id="7f995-569">Fare clic con il pulsante destro del mouse sull'icona della barra di sistema e scegliere Accedi o Disconnetti.</span><span class="sxs-lookup"><span data-stu-id="7f995-569">Right-click the system tray icon, and select sign in or sign out.</span></span>
    
      - <span data-ttu-id="7f995-570">Uso delle scelte rapide da tastiera configurabili.</span><span class="sxs-lookup"><span data-stu-id="7f995-570">Using configurable keyboard shortcuts.</span></span>

  - <span data-ttu-id="7f995-571">**Appartenenza al gruppo:** Quando viene selezionato un gruppo di agenti, il gruppo di risposte in Live Visualizza l'elenco di agenti in questo gruppo nel riquadro destro.</span><span class="sxs-lookup"><span data-stu-id="7f995-571">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="7f995-572">Se Lync 2013 è in uso nello stesso computer di questa applicazione, le informazioni sulla presenza e la scheda contatto vengono visualizzate nell'agente di Response Group Live.</span><span class="sxs-lookup"><span data-stu-id="7f995-572">If Lync 2013 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="7f995-573">Gli agenti possono inviare un messaggio istantaneo o chiamare altri agenti direttamente da lì.</span><span class="sxs-lookup"><span data-stu-id="7f995-573">Agents can send an IM or call other agents directly from there.</span></span>

  - <span data-ttu-id="7f995-574">**Statistiche in tempo reale:** Response Group Agent Live offre statistiche in tempo reale per tutti i gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="7f995-574">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="7f995-575">La frequenza di aggiornamento è di un minuto.</span><span class="sxs-lookup"><span data-stu-id="7f995-575">The update frequency is one minute.</span></span> <span data-ttu-id="7f995-576">Quando una chiamata viene risolta da un gruppo di risposte, accanto al nome del gruppo viene aggiunto un indicatore visivo con il numero corrente di chiamate in coda.</span><span class="sxs-lookup"><span data-stu-id="7f995-576">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="7f995-577">Se si sospende il puntatore del mouse su un gruppo, viene visualizzato anche il tempo di attesa più lungo.</span><span class="sxs-lookup"><span data-stu-id="7f995-577">Pausing the pointer over a group also displays the longest waiting time.</span></span>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7f995-578">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f995-578">Requirements</span></span>

<span data-ttu-id="7f995-579">L'agente di Response Group Live richiede .NET Framework 4,0.</span><span class="sxs-lookup"><span data-stu-id="7f995-579">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="7f995-580">Inoltre, per sfruttare le caratteristiche della presenza e della scheda contatto, Lync 2013 deve essere installato localmente (ed essere in funzione).</span><span class="sxs-lookup"><span data-stu-id="7f995-580">In addition, to take advantage of the presence and contact card features, Lync 2013 must be installed locally (and be running).</span></span>

<div>

## <a name="configuration"></a><span data-ttu-id="7f995-581">Configurazione</span><span class="sxs-lookup"><span data-stu-id="7f995-581">Configuration</span></span>

<span data-ttu-id="7f995-582">Response Group Agent Live può essere personalizzato per le singole preferenze usando la finestra di dialogo Opzioni nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7f995-582">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="7f995-583">Inoltre, l'amministratore può definire l'indirizzo host predefinito modificando direttamente la proprietà defaultHostAddress del file RGAgentLive. exe. config.</span><span class="sxs-lookup"><span data-stu-id="7f995-583">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="7f995-584">Nella figura seguente è illustrata la finestra di dialogo Opzioni che gli agenti possono usare per configurare l'indirizzo host e i tasti di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="7f995-584">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="7f995-585">Per accedere a questa finestra di dialogo, fare clic sul pulsante Opzioni nell'angolo in alto a destra dell'interfaccia principale.</span><span class="sxs-lookup"><span data-stu-id="7f995-585">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

<span data-ttu-id="7f995-586">![Finestra di dialogo Options di Response Group Agent Live.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "Finestra di dialogo Options di Response Group Agent Live.")</span><span class="sxs-lookup"><span data-stu-id="7f995-586">![The Response Group Agent Live Options dialog box.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "The Response Group Agent Live Options dialog box.")</span></span>

<span data-ttu-id="7f995-587">Le tre diverse impostazioni seguenti possono essere personalizzate nella configurazione Live dell'agente di Response Group:</span><span class="sxs-lookup"><span data-stu-id="7f995-587">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

  - <span data-ttu-id="7f995-588">Indirizzo host: in genere è il nome di dominio completo del pool Web che appartiene al pool di Home dell'agente.</span><span class="sxs-lookup"><span data-stu-id="7f995-588">Host address: This is typically the web pool FQDN belonging to the agent’s home pool.</span></span> <span data-ttu-id="7f995-589">L'indirizzo esatto del servizio Response Group viene automaticamente derivato in background da queste informazioni (accodando il percorso corretto dopo l'host).</span><span class="sxs-lookup"><span data-stu-id="7f995-589">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

  - <span data-ttu-id="7f995-590">Scelte rapide: i collegamenti esatti per l'accesso/uscita possono essere personalizzati.</span><span class="sxs-lookup"><span data-stu-id="7f995-590">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="7f995-591">L'unica limitazione è che entrambi i tasti di scelta rapida devono contenere la chiave "Windows logo" (oltre ad almeno un altro tasto).</span><span class="sxs-lookup"><span data-stu-id="7f995-591">The only limitation is that both shortcuts must contain the “Windows Logo” key (in addition to at least another key).</span></span>

  - <span data-ttu-id="7f995-592">Iniziare con Windows: l'applicazione può essere configurata per l'avvio automatico con Windows.</span><span class="sxs-lookup"><span data-stu-id="7f995-592">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7f995-593">Esempi</span><span class="sxs-lookup"><span data-stu-id="7f995-593">Examples</span></span>

<span data-ttu-id="7f995-594">La figura seguente illustra come chiamare o inviare un messaggio istantaneo a un altro agente facendo clic con il pulsante destro del mouse sul contatto nel riquadro destro.</span><span class="sxs-lookup"><span data-stu-id="7f995-594">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

<span data-ttu-id="7f995-595">![Esecuzione di una chiamata o invio di un messaggio istantaneo.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Esecuzione di una chiamata o invio di un messaggio istantaneo.")</span><span class="sxs-lookup"><span data-stu-id="7f995-595">![Making a call or sending an IM.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Making a call or sending an IM.")</span></span>

<span data-ttu-id="7f995-596">Nella figura seguente viene illustrato il modo in cui l'agente di Response Group Live Visualizza il numero corrente di chiamate nella coda e il tempo di attesa più lungo tra tutte le chiamate in arrivo.</span><span class="sxs-lookup"><span data-stu-id="7f995-596">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

<span data-ttu-id="7f995-597">![Visualizzazione di informazioni sulla coda.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Visualizzazione di informazioni sulla coda.")</span><span class="sxs-lookup"><span data-stu-id="7f995-597">![Viewing queue information.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Viewing queue information.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="7f995-598">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="7f995-598">Summary</span></span>

<span data-ttu-id="7f995-599">L'accesso rapido e la disconnessione, l'appartenenza ai gruppi e le statistiche di base in tempo reale sono interessanti funzionalità dell'agente di Response Group che sono disponibili solo all'esterno dell'applicazione dal servizio Response Group.</span><span class="sxs-lookup"><span data-stu-id="7f995-599">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="7f995-600">Con lo strumento Response Group Agent Live Resource Kit, gli amministratori di Lync possono consentire agli agenti di usare un'applicazione Windows che consente loro di eseguire attività in modo più rapido e grafico.</span><span class="sxs-lookup"><span data-stu-id="7f995-600">With the Response Group Agent Live Resource Kit tool, Lync administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

</div>

</div>

<div>

## <a name="sefautil"></a><span data-ttu-id="7f995-601">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="7f995-601">SEFAUtil</span></span>

<span data-ttu-id="7f995-602">SEFAUtil (attivazione delle funzionalità di estensione secondaria) è uno strumento della riga di comando che consente agli amministratori del software di comunicazione di Microsoft Lync Server 2013 e agli agenti dell'helpdesk di configurare le chiamate Delegate, l'inoltro di chiamata, lo squillo simultaneo, la chiamata del team impostazioni e raccolta di chiamate di gruppo per conto di un utente di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-602">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Microsoft Lync Server 2013 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="7f995-603">Lo strumento consente inoltre agli amministratori di eseguire query sulle impostazioni di routing delle chiamate pubblicate per un determinato utente. Lo strumento SEFAUtil consente all'amministratore di abilitare/disabilitare/modificare l'inoltro di chiamata o di squillare contemporaneamente per conto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7f995-603">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="7f995-604">L'amministratore può specificare la destinazione (sotto forma di URI SIP) o usare una destinazione già pubblicata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="7f995-604">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="7f995-605">Questo strumento consente inoltre agli amministratori di aggiungere o rimuovere delegati o membri del gruppo di chiamate del team per conto dell'utente. Questo strumento è basato su Microsoft Unified Communications Managed API (UCMA) 3,0 e richiede che gli amministratori creino un'applicazione attendibile nell'Central Management store per SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="7f995-605">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil</span></span>

<span data-ttu-id="7f995-606">SEFAUtil (attivazione delle funzionalità di estensione secondaria) consente agli amministratori e agli agenti dell'helpdesk di Lync Server 2013 di configurare le chiamate con delegati, l'inoltro di chiamata, la suoneria simultanea, le impostazioni per la chiamata del team e il pickup delle chiamate di gruppo per conto di un utente di Lync Server 2013 .</span><span class="sxs-lookup"><span data-stu-id="7f995-606">SEFAUtil (secondary extension feature activation) enables Lync Server 2013 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="7f995-607">Questo strumento consente inoltre agli amministratori di eseguire query sulle impostazioni di routing delle chiamate pubblicate per un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="7f995-607">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7f995-608">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f995-608">Description</span></span>

<span data-ttu-id="7f995-609">La versione corrente di SEFAUtil è solo uno strumento della riga di comando. non è disponibile un'interfaccia utente grafica di supporto.</span><span class="sxs-lookup"><span data-stu-id="7f995-609">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="7f995-610">Questo strumento è basato su Microsoft Unified Communications Managed API (UCMA) 3,0.</span><span class="sxs-lookup"><span data-stu-id="7f995-610">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="7f995-611">Le funzionalità di questo strumento consentono agli amministratori e agli agenti helpdesk di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f995-611">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

  - <span data-ttu-id="7f995-612">Visualizzare tutte le impostazioni di routing delle chiamate per un utente (include l'inoltro di chiamata, la delega, lo squillo simultaneo, la chiamata in team e il pick-up di gruppo)</span><span class="sxs-lookup"><span data-stu-id="7f995-612">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

  - <span data-ttu-id="7f995-613">Abilitare/disabilitare/modificare l'impostazione di inoltro di chiamata (include la destinazione e il timer senza risposta)</span><span class="sxs-lookup"><span data-stu-id="7f995-613">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

  - <span data-ttu-id="7f995-614">Abilitare/disabilitare/modificare le configurazioni immediate dell'inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="7f995-614">Enable/disable/modify call-forwarding immediate configurations</span></span>

  - <span data-ttu-id="7f995-615">Abilitare/disabilitare/modificare le impostazioni di delega</span><span class="sxs-lookup"><span data-stu-id="7f995-615">Enable/disable/modify delegation settings</span></span>

  - <span data-ttu-id="7f995-616">Abilitare/disabilitare/modificare le impostazioni del gruppo di chiamate team</span><span class="sxs-lookup"><span data-stu-id="7f995-616">Enable/disable/modify team-call group settings</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f995-617">Nuovo strumento SEFAUtil di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f995-617">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="7f995-618">Abilitare/disabilitare/modificare le impostazioni di chiamata simultanea (include la destinazione)</span><span class="sxs-lookup"><span data-stu-id="7f995-618">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f995-619">Nuovo strumento SEFAUtil di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f995-619">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="7f995-620">Abilitare/disabilitare/modificare le impostazioni di raccolta delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="7f995-620">Enable/disable/modify group call pickup settings</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="7f995-621">Nuovo strumento SEFAUtil di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f995-621">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

<span data-ttu-id="7f995-622">Questo strumento presenta le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f995-622">This tool has the following limitations:</span></span>

  - <span data-ttu-id="7f995-623">Supportato solo per gli utenti ospitati in un pool di Lync Server</span><span class="sxs-lookup"><span data-stu-id="7f995-623">Supported only for users homed in a Lync Server pool</span></span>

  - <span data-ttu-id="7f995-624">La modifica in blocco delle impostazioni di routing delle chiamate per diversi utenti non è supportata</span><span class="sxs-lookup"><span data-stu-id="7f995-624">Bulk-edit of call routing settings for several users is not supported</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="7f995-625">Output</span><span class="sxs-lookup"><span data-stu-id="7f995-625">Output</span></span>

<span data-ttu-id="7f995-626">La versione corrente di questo strumento fornisce l'output solo nella finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="7f995-626">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="7f995-627">Per informazioni dettagliate, vedere la sezione esempi più avanti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="7f995-627">For details, see the Examples section later in this document.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="7f995-628">Scopo</span><span class="sxs-lookup"><span data-stu-id="7f995-628">Purpose</span></span>

<span data-ttu-id="7f995-629">Di seguito sono riportati alcuni degli scenari principali in cui può essere usato questo strumento:</span><span class="sxs-lookup"><span data-stu-id="7f995-629">Following are some of the key scenarios where this tool may be used:</span></span>

  - <span data-ttu-id="7f995-630">Roberto è un dirigente ed è stato spostato nella telefonia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7f995-630">Bob is an executive and has been moved to Lync Server telephony.</span></span> <span data-ttu-id="7f995-631">Ha delegazioni nel sistema PBX esistente.</span><span class="sxs-lookup"><span data-stu-id="7f995-631">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="7f995-632">Come parte del passaggio a Lync, l'amministratore è in grado di configurare il routing di Roberto per riflettere la configurazione di delega preesistente.</span><span class="sxs-lookup"><span data-stu-id="7f995-632">As part of the move to Lync, the administrator is able to configure Bob’s routing to reflect his pre-existing delegation configuration.</span></span>

  - <span data-ttu-id="7f995-633">Alice è in viaggio e si rende conto che si aspetta una chiamata importante da uno dei suoi clienti.</span><span class="sxs-lookup"><span data-stu-id="7f995-633">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="7f995-634">Tuttavia, si trova in un hotel e non ha accesso a un computer.</span><span class="sxs-lookup"><span data-stu-id="7f995-634">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="7f995-635">Chiama l'helpdesk e chiede di inoltrare al numero di cellulare tutte le chiamate effettuate al suo numero di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7f995-635">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="7f995-636">Il personale dell'helpdesk è in grado di eseguire la configurazione per suo conto.</span><span class="sxs-lookup"><span data-stu-id="7f995-636">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

  - <span data-ttu-id="7f995-637">Le chiamate di Joe al suo numero di lavoro andranno alla segreteria telefonica per dispositivi mobili ogni volta che è al lavoro; Tuttavia, le cose sembrano funzionare correttamente nella maggior parte degli altri percorsi.</span><span class="sxs-lookup"><span data-stu-id="7f995-637">Joe’s calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="7f995-638">Il tecnico dell'helpdesk è in grado di visualizzare la configurazione di routing di Joe e rileva che Joe ha squillato simultaneamente configurato per il cellulare.</span><span class="sxs-lookup"><span data-stu-id="7f995-638">The helpdesk technician is able to view Joe’s routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="7f995-639">Il tecnico chiede a Joe della copertura per dispositivi mobili presso il suo ufficio ed è in grado di determinare che la regola di chiamata simultanea è ciò che causa le chiamate per accedere alla segreteria telefonica di Joe quando la sua copertura di rete è scadente.</span><span class="sxs-lookup"><span data-stu-id="7f995-639">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe’s mobile voicemail when his network coverage is poor.</span></span>

  - <span data-ttu-id="7f995-640">Mike è un nuovo dipendente di Contoso e si unisce a un nuovo team in cui tutti i membri sono configurati per la chiamata del team, quando viene abilitato per Microsoft Lync, l'amministratore è in grado di impostare le impostazioni del gruppo di chiamate del team per includere tutti i nuovi membri del team, inoltre l' l'amministratore aggiunge Mike come membro del gruppo di chiamate team per ognuno dei membri del team.</span><span class="sxs-lookup"><span data-stu-id="7f995-640">Mike is a new employee at Contoso and he’s joining a new team on which all members are configured for team-call, when being enabled for Microsoft Lync, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

  - <span data-ttu-id="7f995-641">Una pratica di servizio al cliente nel reparto risorse umane di Contoso consiste nel prestare un servizio personalizzato per tutti i chiamanti dopo la prima chiamata.</span><span class="sxs-lookup"><span data-stu-id="7f995-641">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="7f995-642">Considerato che tutti i membri del dipartimento si siedono molto vicini l'uno all'altro, è molto fastidioso per il team avere tutti i telefoni che squillano contemporaneamente alla chiamata del team.</span><span class="sxs-lookup"><span data-stu-id="7f995-642">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="7f995-643">Per garantire un servizio ottimale senza interrompere i membri del team, l'amministratore di Lync sfrutta la funzionalità di raccolta delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="7f995-643">To provide the best service without disrupting the team members, the Lync administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="7f995-644">L'amministratore aggiunge tutti i membri del reparto a un gruppo di raccolta e comunica al reparto il numero del gruppo di pick-up.</span><span class="sxs-lookup"><span data-stu-id="7f995-644">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="7f995-645">Quando Samantha è assente dalla sua scrivania, Joe nota che squilla il telefono e procede a rispondere alla chiamata dalla sua scrivania.</span><span class="sxs-lookup"><span data-stu-id="7f995-645">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7f995-646">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f995-646">Requirements</span></span>

<span data-ttu-id="7f995-647">Lo strumento SEFAUtil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibile.</span><span class="sxs-lookup"><span data-stu-id="7f995-647">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="7f995-648">UCMA 3,0 deve essere installato nel computer in cui si trova.</span><span class="sxs-lookup"><span data-stu-id="7f995-648">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="7f995-649">Per eseguire lo strumento, è necessario creare una nuova applicazione attendibile con l'ID applicazione SEFAUtil in tale pool.</span><span class="sxs-lookup"><span data-stu-id="7f995-649">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

<span data-ttu-id="7f995-650">**Creazione di una nuova applicazione attendibile per lo strumento SEFAUtil**</span><span class="sxs-lookup"><span data-stu-id="7f995-650">**Creating a new Trusted Application for the SEFAUtil tool**</span></span>

1.  <span data-ttu-id="7f995-651">Lo strumento SEFAUTil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibile.</span><span class="sxs-lookup"><span data-stu-id="7f995-651">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="7f995-652">Se necessario, l'aggiunta di un pool come nuovo pool di applicazioni attendibili può essere eseguita tramite Lync Server Management Shell con il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="7f995-652">If needed, adding a pool as a new trusted application pool can be done via the Lync Server Management Shell with the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f995-653">UCMA 3,0 deve essere installato in qualsiasi computer che verrà usato per eseguire lo strumento SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="7f995-653">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

    
    </div>

2.  <span data-ttu-id="7f995-654">Un'applicazione attendibile deve essere definita nella topologia dello strumento SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="7f995-654">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="7f995-655">Per definire SEFAUtil come nuova applicazione attendibile, usare Lync Server Management Shell ed eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="7f995-655">To define SEFAUtil as a new trusted application, use the Lync Server Management Shell and execute the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f995-656">Se necessario, è possibile usare una porta diversa.</span><span class="sxs-lookup"><span data-stu-id="7f995-656">A different port can be used if needed.</span></span>

    
    </div>

3.  <span data-ttu-id="7f995-657">Le modifiche della topologia devono essere abilitate.</span><span class="sxs-lookup"><span data-stu-id="7f995-657">The topology changes need to be enabled.</span></span> <span data-ttu-id="7f995-658">L'attivazione delle modifiche della topologia può essere eseguita tramite Lync Server Management Shell eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="7f995-658">Enabling the topology changes can be done via the Lync Server Management Shell by executing the following cmdlet:</span></span>
    
        Enable-CsToplogy

4.  <span data-ttu-id="7f995-659">Se necessario, installare gli strumenti del Resource Kit di Lync Server 2013 nel server che verrà usato per eseguire lo strumento SEFAUtil (il server deve far parte di un pool di applicazioni attendibili).</span><span class="sxs-lookup"><span data-stu-id="7f995-659">If needed, install the Lync Server 2013 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5.  <span data-ttu-id="7f995-660">Verificare che SEFAUtil sia in corso correttamente.</span><span class="sxs-lookup"><span data-stu-id="7f995-660">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="7f995-661">A questo scopo, Esegui lo strumento da un prompt dei comandi di Windows con privilegi di amministratore per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7f995-661">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="7f995-662">Per impostazione predefinita, lo strumento si trova in: "... \\File\\di programma Microsoft Lync Server\\2013 reskit ".</span><span class="sxs-lookup"><span data-stu-id="7f995-662">By default the tool will be located in: “…\\Program Files\\Microsoft Lync Server 2013\\Reskit”.</span></span> <span data-ttu-id="7f995-663">Per visualizzare le impostazioni di inoltro di chiamata di un utente, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="7f995-663">To display the call forwarding settings of a user, use the following command:</span></span>
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    <span data-ttu-id="7f995-664">Devono essere visualizzate le impostazioni di inoltro di chiamata dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7f995-664">The call forwarding settings of the user should be displayed.</span></span>

<div>

## <a name="group-call-pickup"></a><span data-ttu-id="7f995-665">Risposta alle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="7f995-665">Group Call Pickup</span></span>

<span data-ttu-id="7f995-666">Il ritiro delle chiamate di gruppo richiede una configurazione aggiuntiva in Lync Server per consentire la completa abilitazione.</span><span class="sxs-lookup"><span data-stu-id="7f995-666">Group Call Pickup requires additional configuration in Lync Server for the capability to be fully enabled.</span></span> <span data-ttu-id="7f995-667">Prima di assegnare gruppi di prelievo agli utenti, vedere la documentazione del prodotto pick-up per la pianificazione e la distribuzione di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7f995-667">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7f995-668">Esempi</span><span class="sxs-lookup"><span data-stu-id="7f995-668">Examples</span></span>

<div>

## <a name="display-current-call-handling-settings"></a><span data-ttu-id="7f995-669">Visualizzare le impostazioni di gestione delle chiamate correnti</span><span class="sxs-lookup"><span data-stu-id="7f995-669">Display Current Call Handling Settings</span></span>

<span data-ttu-id="7f995-670">Il comando seguente Visualizza la gestione delle chiamate per l'utente.</span><span class="sxs-lookup"><span data-stu-id="7f995-670">The following command displays the call handling for the user.</span></span> `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> <span data-ttu-id="7f995-671">Questo esempio usa l'opzione <STRONG>/Server</STRONG> per specificare il server Lync a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="7f995-671">This example uses the <STRONG>/server</STRONG> switch to specify the Lync Server to connect to.</span></span>



</div>

<span data-ttu-id="7f995-672">**Output**</span><span class="sxs-lookup"><span data-stu-id="7f995-672">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="7f995-673">Impostare la destinazione di chiamata inoltra/nessuna risposta</span><span class="sxs-lookup"><span data-stu-id="7f995-673">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="7f995-674">Questo esempio imposta la destinazione per la chiamata in avanti/nessuna risposta e il ritardo della suoneria.</span><span class="sxs-lookup"><span data-stu-id="7f995-674">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="7f995-675">In questo caso, l'opzione/server non è disponibile; SEFAUtil tenta di individuare l'individuazione automatica del server Lync.</span><span class="sxs-lookup"><span data-stu-id="7f995-675">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Lync Server.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

<span data-ttu-id="7f995-676">**Output**</span><span class="sxs-lookup"><span data-stu-id="7f995-676">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="7f995-677">Abilitare l'inoltro di chiamata immediatamente</span><span class="sxs-lookup"><span data-stu-id="7f995-677">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="7f995-678">Questo esempio consente immediatamente l'inoltro di chiamata a un altro utente.</span><span class="sxs-lookup"><span data-stu-id="7f995-678">This example immediately enables call-forwarding to another user.</span></span>

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

<span data-ttu-id="7f995-679">**Output**</span><span class="sxs-lookup"><span data-stu-id="7f995-679">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="7f995-680">Disabilitare immediatamente l'inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="7f995-680">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="7f995-681">Questo esempio disattiva immediatamente l'inoltro di chiamata.</span><span class="sxs-lookup"><span data-stu-id="7f995-681">This example immediately disables call forwarding.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

<span data-ttu-id="7f995-682">**Output**</span><span class="sxs-lookup"><span data-stu-id="7f995-682">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="7f995-683">Aggiungere un utente come delegato e configurare lo squillo simultaneo dei delegati</span><span class="sxs-lookup"><span data-stu-id="7f995-683">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="7f995-684">In questo esempio viene aggiunto un utente come delegato e viene impostata la chiamata simultanea dei delegati.</span><span class="sxs-lookup"><span data-stu-id="7f995-684">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

<span data-ttu-id="7f995-685">**Output**</span><span class="sxs-lookup"><span data-stu-id="7f995-685">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="7f995-686">Modificare la regola di chiamata simultanea dei delegati</span><span class="sxs-lookup"><span data-stu-id="7f995-686">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="7f995-687">Questo esempio modifica la regola di chiamata simultanea impostata nell'esempio precedente sulla regola di chiamata in ritardo.</span><span class="sxs-lookup"><span data-stu-id="7f995-687">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

<span data-ttu-id="7f995-688">**Output**</span><span class="sxs-lookup"><span data-stu-id="7f995-688">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a><span data-ttu-id="7f995-689">Rimuovere il delegato</span><span class="sxs-lookup"><span data-stu-id="7f995-689">Remove the Delegate</span></span>

<span data-ttu-id="7f995-690">In questo esempio viene rimosso il delegato.</span><span class="sxs-lookup"><span data-stu-id="7f995-690">This example removes the delegate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f995-691">Quando l'ultimo delegato viene rimosso, il delegare squilla viene disabilitato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7f995-691">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

<span data-ttu-id="7f995-692">**Output**</span><span class="sxs-lookup"><span data-stu-id="7f995-692">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="7f995-693">Aggiungere un delegato e configurare la regola di inoltro di chiamata a delegati</span><span class="sxs-lookup"><span data-stu-id="7f995-693">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="7f995-694">In questo esempio viene aggiunto un delegato e viene impostata la regola inoltro di chiamata a delegati.</span><span class="sxs-lookup"><span data-stu-id="7f995-694">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

<span data-ttu-id="7f995-695">**Output**</span><span class="sxs-lookup"><span data-stu-id="7f995-695">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="7f995-696">Abilitare la chiamata simultanea e impostare un numero di destinazione</span><span class="sxs-lookup"><span data-stu-id="7f995-696">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="7f995-697">Questo esempio Abilita la chiamata simultanea e imposta un numero di destinazione squillante simultaneo.</span><span class="sxs-lookup"><span data-stu-id="7f995-697">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> <span data-ttu-id="7f995-698">Per cambiare il numero di destinazione squillo simultaneo di un utente che ha già attivato la chiamata simultanea, Mantieni il comando con l'opzione/enablesimulring, altrimenti il numero di destinazione non verrà modificato.</span><span class="sxs-lookup"><span data-stu-id="7f995-698">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>



</div>

<span data-ttu-id="7f995-699">**Output**</span><span class="sxs-lookup"><span data-stu-id="7f995-699">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a><span data-ttu-id="7f995-700">Disabilitare lo squillo simultaneo</span><span class="sxs-lookup"><span data-stu-id="7f995-700">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="7f995-701">Questo esempio disabilita la chiamata simultanea.</span><span class="sxs-lookup"><span data-stu-id="7f995-701">This example disables simultaneous ringing.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

<span data-ttu-id="7f995-702">**Output**</span><span class="sxs-lookup"><span data-stu-id="7f995-702">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="7f995-703">Aggiungere un membro del team per la chiamata al team e configurare lo squillo simultaneo al gruppo membri della chiamata del team</span><span class="sxs-lookup"><span data-stu-id="7f995-703">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="7f995-704">Questo esempio aggiunge un membro del team al gruppo di chiamate team di un utente e consente la chiamata simultanea al gruppo di chiamate del team.</span><span class="sxs-lookup"><span data-stu-id="7f995-704">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="7f995-705">L'aggiunta di un membro al gruppo di chiamata del team di un utente cambia automaticamente il settigs di chiamata simultanea degli utenti per simulring il gruppo di chiamate del team.</span><span class="sxs-lookup"><span data-stu-id="7f995-705">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>



</div>

<span data-ttu-id="7f995-706">**Output**</span><span class="sxs-lookup"><span data-stu-id="7f995-706">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="7f995-707">Rimuovere un membro dal gruppo di chiamate team</span><span class="sxs-lookup"><span data-stu-id="7f995-707">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="7f995-708">Questo esempio rimuove un membro del team del gruppo di chiamate team di un utente.</span><span class="sxs-lookup"><span data-stu-id="7f995-708">This example removes a team member of the team-call group of a user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> <span data-ttu-id="7f995-709">Se il membro da rimuovere è l'unico membro del gruppo di chiamate del team, lo squillo simultaneo al gruppo di chiamate del team verrà disabilitato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7f995-709">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>



</div>

<span data-ttu-id="7f995-710">**Output**</span><span class="sxs-lookup"><span data-stu-id="7f995-710">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="7f995-711">Impostare l'anello ritardato sul gruppo di chiamate team</span><span class="sxs-lookup"><span data-stu-id="7f995-711">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="7f995-712">Questo esempio cambia l'intervallo di tempo in ritardo con l'impostazione dell'ora del gruppo di chiamate team.</span><span class="sxs-lookup"><span data-stu-id="7f995-712">This example changes the delayed ring to the team-call group time setting.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

<span data-ttu-id="7f995-713">**Output**</span><span class="sxs-lookup"><span data-stu-id="7f995-713">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a><span data-ttu-id="7f995-714">Abilitare la chiamata del team</span><span class="sxs-lookup"><span data-stu-id="7f995-714">Enable Team-Call</span></span>

<span data-ttu-id="7f995-715">Questo esempio consente di abilitare la chiamata al team per un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="7f995-715">This example enables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="7f995-716">Se il gruppo di chiamata del team dell'utente non ha membri, la chiamata del team non verrà abilitata.</span><span class="sxs-lookup"><span data-stu-id="7f995-716">If the team-call group of the user has no members, team-call won’t be enabled.</span></span>



</div>

<span data-ttu-id="7f995-717">**Output**</span><span class="sxs-lookup"><span data-stu-id="7f995-717">**Output**</span></span>

</div>

<div>

## <a name="disable-team-call"></a><span data-ttu-id="7f995-718">Disabilitare la chiamata del team</span><span class="sxs-lookup"><span data-stu-id="7f995-718">Disable Team-Call</span></span>

<span data-ttu-id="7f995-719">Questo esempio disabilita la chiamata del team per un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="7f995-719">This example disables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

<span data-ttu-id="7f995-720">**Output**</span><span class="sxs-lookup"><span data-stu-id="7f995-720">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="7f995-721">Abilitare il ritiro delle chiamate di gruppo e assegnare un gruppo di raccolta a un utente</span><span class="sxs-lookup"><span data-stu-id="7f995-721">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="7f995-722">In questo esempio viene assegnato un gruppo di prelievo a un utente e viene abilitato il ritiro delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="7f995-722">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

<span data-ttu-id="7f995-723">**Output**</span><span class="sxs-lookup"><span data-stu-id="7f995-723">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a><span data-ttu-id="7f995-724">Disabilitare il ritiro delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="7f995-724">Disable Group Call Pickup</span></span>

<span data-ttu-id="7f995-725">In questo esempio viene disabilitato il ritiro delle chiamate di gruppo per un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="7f995-725">This example disables Group Call Pickup for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> <span data-ttu-id="7f995-726">Quando si disattiva il prelievo delle chiamate di gruppo per un utente, il numero di gruppo assegnato all'utente non viene mantenuto.</span><span class="sxs-lookup"><span data-stu-id="7f995-726">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="7f995-727">Se in seguito si vuole riabilitare il ritiro delle chiamate di gruppo per l'utente, è necessario assegnare di nuovo il numero di gruppo con l'opzione/enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="7f995-727">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a><span data-ttu-id="7f995-728">SYSPrep. ps1</span><span class="sxs-lookup"><span data-stu-id="7f995-728">SYSPrep.ps1</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7f995-729">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f995-729">Description</span></span>

<span data-ttu-id="7f995-730">SYSPrep. ps1 è uno script di Windows PowerShell che installerà i prerequisiti di Lync Server 2013 seguenti nel computer del sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="7f995-730">SYSPrep.ps1 is a Windows PowerShell script that will install the following Lync Server 2013 prerequisites on your Windows Server 2008 operating system machine.</span></span>

  - <span data-ttu-id="7f995-731">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="7f995-731">Microsoft .Net Framework 4.5</span></span>

  - <span data-ttu-id="7f995-732">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="7f995-732">Microsoft SQL Server Express</span></span>

  - <span data-ttu-id="7f995-733">Versione 3,0 di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f995-733">Windows Powershell version 3.0</span></span>

  - <span data-ttu-id="7f995-734">Visual C++ 2010 ridistribuibile</span><span class="sxs-lookup"><span data-stu-id="7f995-734">Visual C++ 2010 Redistributable</span></span>

  - <span data-ttu-id="7f995-735">Aggiornamenti di Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="7f995-735">Internet Information Server Updates</span></span>

  - <span data-ttu-id="7f995-736">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="7f995-736">Windows Identity Foundation</span></span>

  - <span data-ttu-id="7f995-737">File di base di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f995-737">Lync Server 2013 Core files</span></span>

<span data-ttu-id="7f995-738">Mentre il nome dello script è simile allo strumento di preparazione del sistema per i sistemi operativi Microsoft Windows, sono diversi.</span><span class="sxs-lookup"><span data-stu-id="7f995-738">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="7f995-739">Questo script installerà solo i prerequisiti necessari per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-739">This script will only install the required prerequisites for Lync Server 2013.</span></span> <span data-ttu-id="7f995-740">Dopo aver installato questi prerequisiti, lo strumento SYSPrep di Windows può quindi essere usato per creare un'immagine del server.</span><span class="sxs-lookup"><span data-stu-id="7f995-740">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7f995-741">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f995-741">Requirements</span></span>

<span data-ttu-id="7f995-742">Prima di eseguire lo script SYSPrep. ps1, è necessario copiare i file dei prerequisiti in una cartella locale nel computer del sistema operativo Windows Server 2008, ad esempio **D\\: Setup**.</span><span class="sxs-lookup"><span data-stu-id="7f995-742">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\\Setup)**.</span></span> <span data-ttu-id="7f995-743">Questa cartella deve includere anche una copia dei file di 2013 di Lync Server, in particolare **Setup. exe.**</span><span class="sxs-lookup"><span data-stu-id="7f995-743">This folder must also include a copy of the Lync Server 2013 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="7f995-744">I file dei prerequisiti possono essere scaricati dai percorsi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f995-744">The prerequisite files can be downloaded from the following locations:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f995-745">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7f995-745">Prerequisite</span></span></th>
<th><span data-ttu-id="7f995-746">Posizione</span><span class="sxs-lookup"><span data-stu-id="7f995-746">Location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f995-747">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="7f995-747">Microsoft .Net Framework 4.5</span></span></p></td>
<td><p>http://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f995-748">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="7f995-748">Microsoft SQL Server Express 2008 R2</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f995-749">Versione 3,0 di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f995-749">Windows Powershell version 3.0</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f995-750">Visual C++ 2010 ridistribuibile</span><span class="sxs-lookup"><span data-stu-id="7f995-750">Visual C++ 2010 Redistributable</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f995-751">Aggiornamenti di Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="7f995-751">Internet Information Server Updates</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f995-752">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="7f995-752">Windows Identity Foundation</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f995-753">Lync Server 2013 Setup. exe</span><span class="sxs-lookup"><span data-stu-id="7f995-753">Lync Server 2013 Setup.exe</span></span></p></td>
<td><p><span data-ttu-id="7f995-754">Copia da Lync Server 2013 media</span><span class="sxs-lookup"><span data-stu-id="7f995-754">Copy from Lync Server 2013 media</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a><span data-ttu-id="7f995-755">Parametro</span><span class="sxs-lookup"><span data-stu-id="7f995-755">Parameter</span></span>

<span data-ttu-id="7f995-756">Il parametro **– SetupFolder** accetta come argomento la posizione della directory dei file di prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7f995-756">The **–SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7f995-757">Esempi</span><span class="sxs-lookup"><span data-stu-id="7f995-757">Examples</span></span>

<span data-ttu-id="7f995-758">Per eseguire lo script SYSPrep. ps1 e installare i prerequisiti di Lync Server 2013, eseguire il comando seguente da un prompt dei comandi con privilegi elevati:</span><span class="sxs-lookup"><span data-stu-id="7f995-758">To run the SYSPrep.ps1 script and install the Lync Server 2013 prerequisites, run the following command from an elevated command prompt:</span></span>

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="7f995-759">Migrazione degli annunci di numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="7f995-759">Unassigned Number Announcements Migration</span></span>

<span data-ttu-id="7f995-760">Lo strumento di migrazione annunci numeri non assegnati consente a un amministratore di Lync di trasferire la configurazione dei numeri non assegnati serviti dall'applicazione di annuncio da un server o pool di origine Lync a un server o a un pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7f995-760">The Unassigned Number Announcements Migration tool enables a Lync administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Lync Server or Pool to a destination Lync Server or Pool.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7f995-761">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f995-761">Description</span></span>

<span data-ttu-id="7f995-762">Lo strumento di migrazione annunci numeri non assegnati è uno script di Windows PowerShell che sposta la configurazione dei numeri non assegnati serviti dall'applicazione di annuncio di un server o pool di origine a un altro server o pool.</span><span class="sxs-lookup"><span data-stu-id="7f995-762">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="7f995-763">Quando viene eseguita, lo script di migrazione degli annunci di numeri non assegnati esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f995-763">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1.  <span data-ttu-id="7f995-764">Consente di trasferire tutti i file audio usati dagli annunci di numeri non assegnati dell'applicazione di annunci ospitati nel server di origine o nel pool nell'archivio file del server o del pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7f995-764">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f995-765">i file audio vengono rimossi dal pool di origine dopo essere stati copiati nel pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7f995-765">the audio files are removed from the source pool once they’re copied to the destination pool.</span></span>

    
    </div>

2.  <span data-ttu-id="7f995-766">Consente di trasferire tutti gli annunci di numeri non assegnati configurati per l'applicazione di annuncio ospitata nel server o nel pool di origine nel server o nel pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7f995-766">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3.  <span data-ttu-id="7f995-767">Riassegnare tutti gli intervalli di numeri non assegnati serviti dall'applicazione di annuncio ospitata nel server di origine o nel pool al server o al pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7f995-767">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="7f995-768">Dopo aver eseguito correttamente lo script, tutti gli intervalli di numeri non assegnati serviti dall'applicazione di annuncio ospitata nel server di origine o nel pool verranno ora serviti con la stessa configurazione dal server o dal pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7f995-768">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="7f995-769">Output</span><span class="sxs-lookup"><span data-stu-id="7f995-769">Output</span></span>

<span data-ttu-id="7f995-770">Lo script **Move-CsAnnouncementConfiguration** indica nella finestra di Lync Management Shell da dove è stato eseguito l'esito positivo o negativo dell'operazione di migrazione.</span><span class="sxs-lookup"><span data-stu-id="7f995-770">The **Move-CsAnnouncementConfiguration** script indicates in the Lync Management Shell window from where it’s executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="7f995-771">Se l'esecuzione dell'operazione viene interrotta da qualsiasi errore, gli intervalli di numeri non assegnati spostati correttamente nella destinazione rimarranno nella destinazione in una maschera operativa e il resto degli intervalli di numeri non assegnati di cui eseguire la migrazione rimarrà in anche l'origine in una maschera operativa.</span><span class="sxs-lookup"><span data-stu-id="7f995-771">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="7f995-772">Per eseguire la migrazione completa del resto della configurazione, rieseguire lo script dopo avere indirizzato l'errore.</span><span class="sxs-lookup"><span data-stu-id="7f995-772">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="7f995-773">Scopo</span><span class="sxs-lookup"><span data-stu-id="7f995-773">Purpose</span></span>

<span data-ttu-id="7f995-774">Lo script di migrazione annunci numero non assegnati può essere usato nei tre scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f995-774">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

  - <span data-ttu-id="7f995-775">**Migrazione delle impostazioni di configurazione a una nuova versione di Lync Server:** Contoso sta eseguendo la migrazione a Lync Server 2013 e come parte del processo di migrazione l'amministratore di Lync Server vuole trasferire la configurazione dei numeri non assegnati serviti dall'applicazione di annuncio dalla distribuzione di Lync Server 2010 alla nuova distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-775">**Migrating configuration settings to a new version of Lync Server:** Contoso is in the process of migrating to Lync Server 2013 and as part of the migration process the Lync Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2010 deployment to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="7f995-776">Per cambiare le impostazioni di configurazione, l'amministratore di Lync Server usa lo strumento di migrazione annunci numero non assegnati.</span><span class="sxs-lookup"><span data-stu-id="7f995-776">To move the configuration settings, the Lync Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

  - <span data-ttu-id="7f995-777">**Rollback di una distribuzione da Lync server 2013 a Lync server 2010:** A causa di fattori imprevisti, Contoso deve eseguire il rollback della migrazione alla nuova distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f995-777">**Rolling back a deployment from Lync Server 2013 to Lync Server 2010:** Due unexpected factors, Contoso has to roll back the migration to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="7f995-778">Per ridurre al minimo le interruzioni del servizio, l'amministratore di Lync Server usa lo strumento di migrazione annunci numero non assegnati per eseguire il rollback della configurazione dalla distribuzione di Lync Server 2013 alla distribuzione di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7f995-778">To minimize disruptions to the service, the Lync Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Lync Server 2013 deployment to the Lync Server 2010 deployment.</span></span>

  - <span data-ttu-id="7f995-779">**Spostamento di dati tra distribuzioni di Lync:** Contoso sta sostituendo tutti i server di un pool con server più recenti.</span><span class="sxs-lookup"><span data-stu-id="7f995-779">**Moving data between Lync deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="7f995-780">La loro strategia consiste nel distribuire un nuovo pool di Lync Server 2013, trasferire tutti i dati dal vecchio al nuovo pool e quindi deprecare il vecchio pool.</span><span class="sxs-lookup"><span data-stu-id="7f995-780">Their strategy is to deploy a new Lync Server 2013 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="7f995-781">Dopo la distribuzione del nuovo pool, viene usato lo strumento di migrazione annunci numeri non assegnati per trasferire la configurazione dal pool precedente a quello nuovo.</span><span class="sxs-lookup"><span data-stu-id="7f995-781">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

<div>

## <a name="requirements"></a><span data-ttu-id="7f995-782">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f995-782">Requirements</span></span>

<span data-ttu-id="7f995-783">Di seguito sono riportati i requisiti principali necessari per eseguire correttamente lo strumento:</span><span class="sxs-lookup"><span data-stu-id="7f995-783">The following are the main requirements needed to successfully run the tool:</span></span>

1.  <span data-ttu-id="7f995-784">Lo script deve essere eseguito da un computer in cui è installato Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7f995-784">The script must be run from a computer that has Lync Server 2013 Management Shell installed.</span></span>

2.  <span data-ttu-id="7f995-785">L'applicazione di annuncio deve essere distribuita correttamente nei server o nei pool di Lync di origine e di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7f995-785">The announcement application has to be successfully deployed in the source and destination Lync Servers or Pools.</span></span>

<div>

## <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="7f995-786">Script Move-CsAnnouncementConfiguration</span><span class="sxs-lookup"><span data-stu-id="7f995-786">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="7f995-787">Lo script Move-CsAnnouncementConfiguration richiede i due parametri descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7f995-787">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

<span data-ttu-id="7f995-788">![Parametri di Move-CsAnnouncementConfiguration.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Parametri di Move-CsAnnouncementConfiguration.")</span><span class="sxs-lookup"><span data-stu-id="7f995-788">![Move-CsAnnouncementConfiguration parameters.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration parameters.")</span></span>

</div>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7f995-789">Esempi</span><span class="sxs-lookup"><span data-stu-id="7f995-789">Examples</span></span>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="7f995-790">Spostamento della configurazione degli annunci di numeri non assegnati da un pool di Lync Server 2010 a un pool di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f995-790">Moving the Unassigned Number Announcements Configuration from a Lync Server 2010 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="7f995-791">Questo esempio sposta gli annunci del numero non assegnati dal pool di origine (Lync Server 2010) nel pool di destinazione (Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="7f995-791">This example moves the unassigned number announcements from the source pool (Lync Server 2010) to the destination pool (Lync Server 2013).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a><span data-ttu-id="7f995-792">Spostamento della configurazione degli annunci di numeri non assegnati da un pool di Lync Server 2013 a un pool di Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7f995-792">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Lync Server 2010 Pool</span></span>

<span data-ttu-id="7f995-793">Questo esempio sposta gli annunci del numero non assegnati dal pool di origine (Lync Server 2013) nel pool di destinazione (Lync Server 2010).</span><span class="sxs-lookup"><span data-stu-id="7f995-793">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Lync Server 2010).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a><span data-ttu-id="7f995-794">Dati Web conf</span><span class="sxs-lookup"><span data-stu-id="7f995-794">Web Conf Data</span></span>

<span data-ttu-id="7f995-795">Lo strumento di dati Web conf consente a un amministratore del software di comunicazione di Lync Server 2013 di avere un maggiore controllo sui dati associati alle conferenze Web di un organizzatore.</span><span class="sxs-lookup"><span data-stu-id="7f995-795">The Web Conf Data Tool allows an administrator of Lync Server 2013 communications software to have more control over the data associated with an organizer’s Web conferences.</span></span> <span data-ttu-id="7f995-796">Gli scenari includono la possibilità di eliminare i dati di una riunione di un utente specifico in base a un criterio di timestamp.</span><span class="sxs-lookup"><span data-stu-id="7f995-796">Scenarios include the ability to delete a specific user’s meeting data based on a time stamp criteria.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="7f995-797">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f995-797">Description</span></span>

<span data-ttu-id="7f995-798">Questo strumento consente all'amministratore di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f995-798">This tool allows the administrator to perform the following operations:</span></span>

1.  <span data-ttu-id="7f995-799">Trovare tutti i dati di Web Conferencing associati a un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="7f995-799">Find all Web conferencing data associated with a single user.</span></span>

2.  <span data-ttu-id="7f995-800">Eliminare tutti i dati di Web Conferencing associati a un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="7f995-800">Delete all Web conferencing data associated with a single user.</span></span>

3.  <span data-ttu-id="7f995-801">Eliminare tutti i dati di Web Conferencing associati a un singolo utente antecedente a una determinata data.</span><span class="sxs-lookup"><span data-stu-id="7f995-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4.  <span data-ttu-id="7f995-802">Spostare tutti i dati di Web Conferencing associati a un singolo utente quando l'utente viene spostato da un pool a un altro.</span><span class="sxs-lookup"><span data-stu-id="7f995-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f995-803">Gli strumenti del Resource Kit per Lync Server 2010 supportano lo spostamento di tutti i dati di Web Conferencing associati a un singolo utente quando l'utente viene spostato da un pool a un altro.</span><span class="sxs-lookup"><span data-stu-id="7f995-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="7f995-804">Questa funzionalità è ora deprecata da questo strumento a favore del parametro <STRONG>MoveConferenceData</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="7f995-804">That functionality is now deprecated from this tool in favor of the <STRONG>MoveConferenceData</STRONG> parameter.</span></span> <span data-ttu-id="7f995-805">Per informazioni dettagliate su questo parametro, vedere il cmdlet <A href="https://technet.microsoft.com/en-us/library/gg398528(v=ocs.15)">Move-CsUser</A> .</span><span class="sxs-lookup"><span data-stu-id="7f995-805">For details about this parameter, see the <A href="https://technet.microsoft.com/en-us/library/gg398528(v=ocs.15)">Move-CsUser</A> cmdlet.</span></span>



</div>

<span data-ttu-id="7f995-806">Lo strumento Elimina i dati delle riunioni solo per le riunioni inattive.</span><span class="sxs-lookup"><span data-stu-id="7f995-806">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="7f995-807">Le riunioni attive (o le riunioni in sessioni) non possono essere eliminate.</span><span class="sxs-lookup"><span data-stu-id="7f995-807">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="7f995-808">Questo strumento deve essere eseguito da un computer che si trova nello stesso pool dell'utente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7f995-808">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="7f995-809">L'utente i cui dati del contenuto della riunione vengono gestiti da questo strumento deve essere ospitato nello stesso pool di utenti.</span><span class="sxs-lookup"><span data-stu-id="7f995-809">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="7f995-810">Output</span><span class="sxs-lookup"><span data-stu-id="7f995-810">Output</span></span>

<span data-ttu-id="7f995-811">Questo strumento restituisce i risultati di ogni operazione:</span><span class="sxs-lookup"><span data-stu-id="7f995-811">This tool outputs the results of each of the operations:</span></span>

  - <span data-ttu-id="7f995-812">Se viene eseguita una query, lo strumento restituisce l'elenco di tutte le cartelle di dati della riunione inattive che hanno l'utente come organizzatore.</span><span class="sxs-lookup"><span data-stu-id="7f995-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

  - <span data-ttu-id="7f995-813">Se viene eseguita un'eliminazione, lo strumento restituisce l'elenco di tutte le cartelle di dati della riunione i cui dati verranno eliminati.</span><span class="sxs-lookup"><span data-stu-id="7f995-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="7f995-814">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f995-814">Requirements</span></span>

<span data-ttu-id="7f995-815">Lo strumento deve essere eseguito nello stesso pool in cui è attualmente ospitato l'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="7f995-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="7f995-816">Lo strumento deve essere eseguito usando i privilegi di amministratore con l'accesso all'archivio di file di contenuto.</span><span class="sxs-lookup"><span data-stu-id="7f995-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="7f995-817">Esempi</span><span class="sxs-lookup"><span data-stu-id="7f995-817">Examples</span></span>

<span data-ttu-id="7f995-818">La tabella seguente descrive i parametri, alcuni dei quali vengono usati negli esempi.</span><span class="sxs-lookup"><span data-stu-id="7f995-818">The following table describes the parameters, some of which are used in the examples.</span></span>

<span data-ttu-id="7f995-819">![Parametri dello strumento Web Conf Data.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Parametri dello strumento Web Conf Data.")</span><span class="sxs-lookup"><span data-stu-id="7f995-819">![Web Conf Data Tool parameters.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web Conf Data Tool parameters.")</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

<span data-ttu-id="7f995-820">Nell'esempio precedente viene illustrato il funzionamento di un comando di query.</span><span class="sxs-lookup"><span data-stu-id="7f995-820">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="7f995-821">L'output di un comando di questo tipo è un elenco di tutte le cartelle del contenuto della riunione interessate da questo strumento.</span><span class="sxs-lookup"><span data-stu-id="7f995-821">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

<span data-ttu-id="7f995-822">Il precedente è un esempio di comando Elimina.</span><span class="sxs-lookup"><span data-stu-id="7f995-822">The preceding is an example of a delete command.</span></span> <span data-ttu-id="7f995-823">Il comando Elimina consente di rimuovere tutte le cartelle riunione inattiva da questo utente.</span><span class="sxs-lookup"><span data-stu-id="7f995-823">The delete command will remove all inactive meeting folders from this user.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="7f995-824">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="7f995-824">Summary</span></span>

<span data-ttu-id="7f995-825">Questo strumento può essere una risorsa preziosa per gli amministratori che hanno bisogno di un controllo più preciso sui dati della riunione di conferenza.</span><span class="sxs-lookup"><span data-stu-id="7f995-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>
