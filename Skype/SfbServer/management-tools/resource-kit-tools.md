---
title: Documentazione degli strumenti del Resource Kit di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: In questo argomento vengono descritti gli strumenti del Resource Kit di Skype for Business Server 2015, tra cui lo scopo di ogni strumento e gli esempi di utilizzo. Il Resource Kit di Skype for Business Server 2015 contribuisce a semplificare le attività di routine per gli amministratori IT che distribuiscono e gestiscono Skype for Business Server 2015. Ad esempio, è possibile utilizzare lo strumento di dati di Web conf per controllare facilmente i dati caricati dagli utenti durante una riunione online. Lo strumento SEFAUtil può essere utilizzato per configurare l'inoltro delle chiamate Delegate e la risposta per gli utenti. Si consiglia agli amministratori IT di utilizzare questi strumenti per gestire in modo più efficace Skype for Business Server 2015.
ms.openlocfilehash: bf1a1d946c998466b118e0ab2038044a48d90970
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822036"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="33458-107">Documentazione degli strumenti del Resource Kit di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="33458-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>

<span data-ttu-id="33458-108">In questo argomento vengono descritti gli strumenti del Resource Kit di Skype for Business Server 2015, tra cui lo scopo di ogni strumento e gli esempi di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="33458-108">This topic describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="33458-109">Il Resource Kit di Skype for Business Server 2015 contribuisce a semplificare le attività di routine per gli amministratori IT che distribuiscono e gestiscono Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="33458-110">Ad esempio, è possibile utilizzare lo strumento di **dati di Web conf** per controllare facilmente i dati caricati dagli utenti durante una riunione online.</span><span class="sxs-lookup"><span data-stu-id="33458-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="33458-111">Lo strumento **SEFAUtil** può essere utilizzato per configurare l'inoltro delle chiamate Delegate e la risposta per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="33458-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="33458-112">Si consiglia agli amministratori IT di utilizzare questi strumenti per gestire in modo più efficace Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="33458-113">Installazione degli strumenti del Resource Kit</span><span class="sxs-lookup"><span data-stu-id="33458-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="33458-114">Per installare il Resource Kit di Skype for Business Server 2015, scaricare [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) dall'area download.</span><span class="sxs-lookup"><span data-stu-id="33458-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) from the Download Center.</span></span>

<span data-ttu-id="33458-115">Eseguire **OCSResKit.msi** per eseguire un'installazione semplice.</span><span class="sxs-lookup"><span data-stu-id="33458-115">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="33458-116">Con estensione msi vengono installati tutti gli strumenti nel percorso seguente: **% Program Files%\Skype for Business Server 2015 \ reskit**.</span><span class="sxs-lookup"><span data-stu-id="33458-116">The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**.</span></span> <span data-ttu-id="33458-117">Gli strumenti che sono eseguibili indipendenti sono presenti in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="33458-117">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="33458-118">Gli strumenti che dispongono anche di file di supporto sono presenti nelle rispettive sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="33458-118">Tools that also have supporting files are in their own subfolders.</span></span>

## <a name="supported-environments"></a><span data-ttu-id="33458-119">Ambienti supportati</span><span class="sxs-lookup"><span data-stu-id="33458-119">Supported Environments</span></span>

<span data-ttu-id="33458-120">Il Resource Kit di Skype for Business Server 2015 deve essere installato in un server che soddisfi le specifiche richieste per Skype for Business Server 2015, in genere uno utilizzato per eseguire Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="33458-121">Panoramica degli strumenti del Resource Kit</span><span class="sxs-lookup"><span data-stu-id="33458-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="33458-122">Di seguito è riportato un elenco degli strumenti forniti in Skype for Business Server 2015 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="33458-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="33458-123">Una descrizione di ogni strumento, inclusi i requisiti e l'utilizzo di esempio, è illustrata nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="33458-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>

- [<span data-ttu-id="33458-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="33458-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)

- [<span data-ttu-id="33458-125">Monitoraggio del servizio criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="33458-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)

- [<span data-ttu-id="33458-126">Analizzatore dell'utilizzo della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="33458-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)

- [<span data-ttu-id="33458-127">Chiamata Parkometer</span><span class="sxs-lookup"><span data-stu-id="33458-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)

- [<span data-ttu-id="33458-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="33458-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)

- [<span data-ttu-id="33458-129">Importare i dati del servizio di archiviazione</span><span class="sxs-lookup"><span data-stu-id="33458-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)

- [<span data-ttu-id="33458-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="33458-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)

- [<span data-ttu-id="33458-131">Console utente di ricerca</span><span class="sxs-lookup"><span data-stu-id="33458-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)

- [<span data-ttu-id="33458-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="33458-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)

- [<span data-ttu-id="33458-133">Visualizzatore di configurazione di rete</span><span class="sxs-lookup"><span data-stu-id="33458-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)

- [<span data-ttu-id="33458-134">Agente di Response Group Live</span><span class="sxs-lookup"><span data-stu-id="33458-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)

- [<span data-ttu-id="33458-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="33458-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)

- [<span data-ttu-id="33458-136">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="33458-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)

- [<span data-ttu-id="33458-137">Migrazione degli annunci di numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="33458-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)

- [<span data-ttu-id="33458-138">Dati Web conf</span><span class="sxs-lookup"><span data-stu-id="33458-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a><span data-ttu-id="33458-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="33458-139">ABSConfig</span></span>
<span data-ttu-id="33458-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="33458-140"><a name="ABSConfig"> </a></span></span>

<span data-ttu-id="33458-141">Lo strumento di configurazione del servizio di gestione della Rubrica (ABSConfig) è uno strumento di amministrazione che consente agli amministratori di personalizzare la configurazione del servizio Rubrica in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="33458-142">Questo strumento consente inoltre agli amministratori di Skype for Business Server 2015 di ripristinare le impostazioni predefinite del servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="33458-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>

### <a name="description"></a><span data-ttu-id="33458-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33458-143">Description</span></span>

<span data-ttu-id="33458-144">ABSConfig è un'applicazione per l'interfaccia utente grafica che consente agli amministratori di configurare gli attributi di servizi di dominio Active Directory correlati al servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="33458-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="33458-145">Gli scenari principali per lo strumento sono gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="33458-145">The primary scenarios for the tool are the following:</span></span>

- <span data-ttu-id="33458-146">Per consentire agli amministratori di eseguire il mapping degli attributi in servizi di dominio Active Directory agli attributi di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>

- <span data-ttu-id="33458-147">Per consentire agli amministratori di specificare l'attributo servizi di dominio Active Directory da includere o escludere nei file del servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="33458-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

- <span data-ttu-id="33458-148">Per consentire agli amministratori di ripristinare le impostazioni predefinite del servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="33458-148">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="33458-149">È possibile avviare lo strumento ABSConfig utilizzando il file ABSConfig.exe.</span><span class="sxs-lookup"><span data-stu-id="33458-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="33458-150">Lo strumento verrà aperto alla scheda **Configure Attributes** . In questa tabella sono disponibili opzioni per il mapping degli attributi dei servizi di dominio Active Directory ai campi degli attributi per Skype for Business Server 2015 e per specificare quali utenti includere o escludere nei file del servizio Rubrica basati su filtri di attributi specifici.</span><span class="sxs-lookup"><span data-stu-id="33458-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="33458-151">Sono inoltre disponibili opzioni per personalizzare il valore del numero di telefono da includere nel file della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="33458-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="33458-152">L'opzione **Ripristina valori predefiniti** consente agli amministratori di ripristinare le impostazioni del servizio Rubrica in valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="33458-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

> [!NOTE]
> <span data-ttu-id="33458-153">La rimappatura degli attributi di Active Directory a diversi nomi di campi OC funzionerà solo per il download dei file della Rubrica e non è supportata dalla query Web della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="33458-153">Re-mapping of AD attributes to different OC Field Names will only work for Address Book File Download, and is not supported by Address Book Web Query.</span></span>

### <a name="output"></a><span data-ttu-id="33458-154">Output</span><span class="sxs-lookup"><span data-stu-id="33458-154">Output</span></span>

<span data-ttu-id="33458-155">ABSConfig archivia la configurazione del servizio Rubrica nel database.</span><span class="sxs-lookup"><span data-stu-id="33458-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="33458-156">Finalità</span><span class="sxs-lookup"><span data-stu-id="33458-156">Purpose</span></span>

<span data-ttu-id="33458-157">ABSConfig offre un modo semplice e rapido per personalizzare il servizio Rubrica di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-157">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>

### <a name="requirements"></a><span data-ttu-id="33458-158">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33458-158">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="33458-159">Computer</span><span class="sxs-lookup"><span data-stu-id="33458-159">Computer</span></span>

<span data-ttu-id="33458-160">ABSConfig può essere eseguito solo da un computer aggiunto al dominio in cui è installato Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-160">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="33458-161">Nel caso di Skype for Business Server 2015, Enterprise Edition, questo strumento può essere eseguito in tutti i front end server con il servizio Rubrica abilitato durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="33458-161">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

#### <a name="network"></a><span data-ttu-id="33458-162">Rete</span><span class="sxs-lookup"><span data-stu-id="33458-162">Network</span></span>

<span data-ttu-id="33458-163">Il computer deve essere in grado di connettersi al pool Front end e al database back-end.</span><span class="sxs-lookup"><span data-stu-id="33458-163">The computer should be able to connect to the Front End pool and back-end database.</span></span>

#### <a name="software"></a><span data-ttu-id="33458-164">Software</span><span class="sxs-lookup"><span data-stu-id="33458-164">Software</span></span>

<span data-ttu-id="33458-165">Prima di eseguire lo strumento ABSConfig, è necessario installare i componenti software seguenti:</span><span class="sxs-lookup"><span data-stu-id="33458-165">The following software components must be installed before running the ABSConfig tool:</span></span>

- <span data-ttu-id="33458-166">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="33458-166">Skype for Business Server 2015</span></span>

#### <a name="users"></a><span data-ttu-id="33458-167">Utenti</span><span class="sxs-lookup"><span data-stu-id="33458-167">Users</span></span>

<span data-ttu-id="33458-168">Amministratori che dispongono delle autorizzazioni necessarie per aggiornare la distribuzione di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-168">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>

### <a name="examples"></a><span data-ttu-id="33458-169">Esempi</span><span class="sxs-lookup"><span data-stu-id="33458-169">Examples</span></span>

<span data-ttu-id="33458-170">ABSConfig può essere avviato digitando **ABSConfig.exe** al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="33458-170">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="33458-171">Di seguito è riportata l'interfaccia utente dello strumento ABSConfig.</span><span class="sxs-lookup"><span data-stu-id="33458-171">Shown below is the ABSConfig tool user interface.</span></span>

![Lo strumento di ABSConfig.exe.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a><span data-ttu-id="33458-173">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="33458-173">Summary</span></span>

<span data-ttu-id="33458-174">Lo strumento ABSConfig offre agli amministratori uno strumento rapido e facile da usare per personalizzare il servizio Rubrica di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="33458-175">Monitoraggio del servizio criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="33458-175">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="33458-176"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="33458-176"><a name="bpsm"> </a></span></span>

<span data-ttu-id="33458-177">Lo strumento di monitoraggio dei criteri di larghezza di banda è progettato per consentire agli amministratori di visualizzare un elenco di quanto segue:</span><span class="sxs-lookup"><span data-stu-id="33458-177">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1. <span data-ttu-id="33458-178">Tutti i servizi di criteri di larghezza di banda di Skype for Business Server configurati 2015 (autenticazione e Core) nella topologia</span><span class="sxs-lookup"><span data-stu-id="33458-178">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2. <span data-ttu-id="33458-179">Le connessioni che ogni servizio apporta ad altri servizi di criteri di larghezza di banda e ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="33458-179">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3. <span data-ttu-id="33458-180">Tutti i collegamenti configurati nel documento di configurazione di rete e nell'utilizzo della larghezza di banda in tempo reale riportati da ciascuno dei servizi di criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="33458-180">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

### <a name="description"></a><span data-ttu-id="33458-181">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33458-181">Description</span></span>

<span data-ttu-id="33458-182">Lo strumento di monitoraggio dei criteri di larghezza di banda è implementato come applicazione basata su GUI.</span><span class="sxs-lookup"><span data-stu-id="33458-182">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="33458-183">Gli amministratori avviano lo strumento eseguendo PDPMonUI.exe.</span><span class="sxs-lookup"><span data-stu-id="33458-183">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="33458-184">Quando lo strumento viene avviato, cerca di individuare l'elenco dei servizi per i criteri di larghezza di banda nella topologia.</span><span class="sxs-lookup"><span data-stu-id="33458-184">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="33458-185">Dopo aver eseguito l'aggiornamento iniziale, il riquadro a sinistra della finestra viene popolato con un elenco di servizi raggruppati per i cluster a cui appartengono.</span><span class="sxs-lookup"><span data-stu-id="33458-185">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="33458-186">Quando gli amministratori selezionano un particolare servizio per i criteri di larghezza di banda, nel riquadro a destra vengono visualizzate le informazioni relative a quel particolare servizio.</span><span class="sxs-lookup"><span data-stu-id="33458-186">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="33458-187">Nel riquadro sono inoltre disponibili due schede principali che consentono di visualizzare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="33458-187">That pane also has two main tabs that display information.</span></span>

#### <a name="machine-info-tab"></a><span data-ttu-id="33458-188">Scheda informazioni sul computer</span><span class="sxs-lookup"><span data-stu-id="33458-188">Machine Info Tab</span></span>

<span data-ttu-id="33458-189">Nella scheda **informazioni sul computer** vengono visualizzati i dettagli del servizio dei criteri di larghezza di banda selezionato e l'elenco e lo stato di tutte le connessioni effettuate dal servizio criteri di larghezza di banda selezionato ad altri servizi.</span><span class="sxs-lookup"><span data-stu-id="33458-189">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

#### <a name="topology-info-tab"></a><span data-ttu-id="33458-190">Scheda informazioni sulla topologia</span><span class="sxs-lookup"><span data-stu-id="33458-190">Topology Info Tab</span></span>

<span data-ttu-id="33458-191">Nella scheda **informazioni sulla topologia** viene visualizzato un elenco di tutti i collegamenti configurati nelle impostazioni di configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="33458-191">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="33458-192">Per ogni collegamento viene visualizzata la capacità di larghezza di banda audio e video.</span><span class="sxs-lookup"><span data-stu-id="33458-192">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="33458-193">Inoltre, viene visualizzata la larghezza di banda attualmente utilizzata, sia in Kbps che come percentuale della capacità.</span><span class="sxs-lookup"><span data-stu-id="33458-193">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="33458-194">Lo strumento utilizza la codifica a colori per evidenziare i collegamenti che dispongono di un utilizzo vicino alla capacità, consentendo agli amministratori di isolare rapidamente tali collegamenti.</span><span class="sxs-lookup"><span data-stu-id="33458-194">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

> [!NOTE]
>  <span data-ttu-id="33458-195">Se lo strumento Monitoraggio servizi di larghezza di banda verifica un errore durante la connessione a uno dei servizi di criteri di larghezza di banda configurati, le informazioni contenute nelle schede informazioni **computer** e **topologia** non verranno popolate.</span><span class="sxs-lookup"><span data-stu-id="33458-195">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="33458-196">Tuttavia, è possibile che lo strumento possa connettersi inizialmente, ma in seguito perde la connessione al servizio.</span><span class="sxs-lookup"><span data-stu-id="33458-196">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="33458-197">In questi casi, gli amministratori possono visualizzare le informazioni obsolete.</span><span class="sxs-lookup"><span data-stu-id="33458-197">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="33458-198">È presente un timestamp dell' **Ultimo aggiornamento** su ognuna delle schede che consentono agli amministratori di visualizzare l'ultimo aggiornamento dei dati per un particolare servizio criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="33458-198">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>

### <a name="output"></a><span data-ttu-id="33458-199">Output</span><span class="sxs-lookup"><span data-stu-id="33458-199">Output</span></span>

<span data-ttu-id="33458-200">Non è disponibile alcun output della riga di comando. l'output del programma è contenuto all'interno dell'interfaccia utente grafica principale (GUI).</span><span class="sxs-lookup"><span data-stu-id="33458-200">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

### <a name="purpose"></a><span data-ttu-id="33458-201">Finalità</span><span class="sxs-lookup"><span data-stu-id="33458-201">Purpose</span></span>

<span data-ttu-id="33458-202">Lo strumento di monitoraggio dei criteri di larghezza di banda consente agli amministratori di visualizzare lo stato di ogni servizio dei criteri di larghezza di banda definito nella topologia.</span><span class="sxs-lookup"><span data-stu-id="33458-202">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="33458-203">Gli amministratori possono inoltre visualizzare l'utilizzo della larghezza di banda in tempo reale per tutti i collegamenti definiti nel documento di configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="33458-203">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

### <a name="requirements"></a><span data-ttu-id="33458-204">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33458-204">Requirements</span></span>

<span data-ttu-id="33458-205">È necessario eseguire lo strumento di monitoraggio dei criteri di larghezza di banda su un computer che fa parte della topologia di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="33458-205">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>

### <a name="summary"></a><span data-ttu-id="33458-206">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="33458-206">Summary</span></span>

<span data-ttu-id="33458-207">Lo strumento di monitoraggio dei criteri di larghezza di banda può essere una risorsa importante per gli amministratori in modo che possano ispezionare lo stato di tutti i servizi dei criteri di larghezza di banda nella topologia e, soprattutto, possono ottenere l'utilizzo della larghezza di banda in tempo reale per i collegamenti definiti nelle impostazioni di configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="33458-207">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="33458-208">Analizzatore dell'utilizzo della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="33458-208">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="33458-209"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="33458-209"><a name="bua"> </a></span></span>

<span data-ttu-id="33458-210">L'analizzatore dell'utilizzo della larghezza di banda è uno strumento che consente di creare report su diverse visualizzazioni del consumo di larghezza di banda da parte degli endpoint UC tra i collegamenti WAN nella rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="33458-210">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="33458-211">Questi report possono essere utilizzati per comprendere il modello di consumo di larghezza di banda corrente e per facilitare la pianificazione della capacità della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="33458-211">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

### <a name="description"></a><span data-ttu-id="33458-212">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33458-212">Description</span></span>

<span data-ttu-id="33458-213">L'analizzatore dell'utilizzo della larghezza di banda viene implementato come applicazione basata su GUI.</span><span class="sxs-lookup"><span data-stu-id="33458-213">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="33458-214">Questo strumento genera report in modo specifico per l'utilizzo dell'audio in rete e contribuisce alla pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="33458-214">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="33458-215">Inoltre, viene eseguita una iterazione sulla capacità di larghezza di banda assegnata a vari collegamenti.</span><span class="sxs-lookup"><span data-stu-id="33458-215">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

### <a name="output"></a><span data-ttu-id="33458-216">Output</span><span class="sxs-lookup"><span data-stu-id="33458-216">Output</span></span>

<span data-ttu-id="33458-217">L'analizzatore dell'utilizzo della larghezza di banda fornisce grafici al grafico della capacità e dell'utilizzo della larghezza di banda per l'audio per tutti i collegamenti WAN configurati nel sistema.</span><span class="sxs-lookup"><span data-stu-id="33458-217">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

### <a name="purpose"></a><span data-ttu-id="33458-218">Finalità</span><span class="sxs-lookup"><span data-stu-id="33458-218">Purpose</span></span>

<span data-ttu-id="33458-219">In qualsiasi distribuzione di voce e video, è importante monitorare e comprendere l'andamento dell'utilizzo della larghezza di banda del traffico multimediale in tutta la rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="33458-219">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="33458-220">Lo strumento Analizzatore utilizzo larghezza di banda consente a un amministratore di raggiungere questo obiettivo.</span><span class="sxs-lookup"><span data-stu-id="33458-220">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="33458-221">Questo strumento esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33458-221">This tool does the following:</span></span>

- <span data-ttu-id="33458-222">Genera relazioni specifiche per l'utilizzo dell'audio in rete</span><span class="sxs-lookup"><span data-stu-id="33458-222">Generates specific reports for audio utilization across the network</span></span>

- <span data-ttu-id="33458-223">Consente di eseguire una pianificazione e un'iterazione della capacità più efficace sulla capacità di larghezza di banda assegnata a vari collegamenti</span><span class="sxs-lookup"><span data-stu-id="33458-223">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="33458-224">L'analizzatore dell'utilizzo della larghezza di banda può generare trame grafiche dei rapporti di utilizzo e capacità della larghezza di banda. sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="33458-224">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

- <span data-ttu-id="33458-225">Tutti i collegamenti WAN nella rete aziendale</span><span class="sxs-lookup"><span data-stu-id="33458-225">All the WAN links in the enterprise network</span></span>

- <span data-ttu-id="33458-226">Filtrato da collegamenti WAN selezionati che sono stati scelti</span><span class="sxs-lookup"><span data-stu-id="33458-226">Filtered by selected WAN links that have been chosen</span></span>

- <span data-ttu-id="33458-227">Filtrato tramite collegamenti WAN che hanno superato la capacità dei collegamenti</span><span class="sxs-lookup"><span data-stu-id="33458-227">Filtered by WAN links that have exceeded link capacity</span></span>

- <span data-ttu-id="33458-228">Filtrato mediante collegamenti WAN che sono stati sottoposti a utilizzo della larghezza di banda provisioning</span><span class="sxs-lookup"><span data-stu-id="33458-228">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

- <span data-ttu-id="33458-229">Filtrare mediante collegamenti WAN che hanno raggiunto livelli critici (un utilizzo della larghezza di banda superiore al 90% della capacità di larghezza di banda del collegamento WAN)</span><span class="sxs-lookup"><span data-stu-id="33458-229">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

- <span data-ttu-id="33458-230">Filtro in base al tipo di collegamento WAN: collegamenti a siti di rete, collegamenti interregionali e collegamenti all'interno di un sito</span><span class="sxs-lookup"><span data-stu-id="33458-230">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

- <span data-ttu-id="33458-231">Filtrato in base all'area di rete</span><span class="sxs-lookup"><span data-stu-id="33458-231">Filtered by network region</span></span>

#### <a name="applications"></a><span data-ttu-id="33458-232">Applicazioni</span><span class="sxs-lookup"><span data-stu-id="33458-232">Applications</span></span>

<span data-ttu-id="33458-233">Analizzatore dell'utilizzo della larghezza di banda contiene le due applicazioni seguenti (strumenti):</span><span class="sxs-lookup"><span data-stu-id="33458-233">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

- <span data-ttu-id="33458-234">**WanLinkLogCollector.exe** Questo strumento consente all'utente di immettere le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="33458-234">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>

- <span data-ttu-id="33458-235">**BandwidthUtilizationAnalyzer.xlsm** Un report software del foglio di calcolo di Microsoft Excel viene avviato automaticamente da WanLinkLogCollector.exe.</span><span class="sxs-lookup"><span data-stu-id="33458-235">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="33458-236">Questa applicazione consente all'utente di applicare filtri al rapporto come mostrato più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="33458-236">This application allows the user to apply filters to the report as shown later in this article.</span></span>

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="33458-237">Fasi dell'utilizzo dell'analizzatore dell'utilizzo della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="33458-237">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="33458-238">Quando si utilizza l'analizzatore dell'utilizzo della larghezza di banda sono presenti due fasi:</span><span class="sxs-lookup"><span data-stu-id="33458-238">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

- <span data-ttu-id="33458-239">Raccolta di registri, eseguiti tramite WanLinkLogCollector.exe</span><span class="sxs-lookup"><span data-stu-id="33458-239">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

- <span data-ttu-id="33458-240">Personalizzare i report, eseguiti tramite BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="33458-240">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="33458-241">È consigliabile che BandwidthUtilizationAnalyzer.xlsm non venga avviato manualmente dagli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="33458-241">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>

#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="33458-242">Avvio dell'analizzatore dell'utilizzo della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="33458-242">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="33458-243">Avviare WanLinkLogCollector.exe al prompt dei comandi o tramite Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="33458-243">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

 <span data-ttu-id="33458-244">**Utilizzo di WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="33458-244">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="33458-245">Sono disponibili tre passaggi per l'utilizzo di WanLinkLogCollector.exe:</span><span class="sxs-lookup"><span data-stu-id="33458-245">There are three steps to using WanLinkLogCollector.exe:</span></span>

1. <span data-ttu-id="33458-246">**Registrare la sequenza temporale** Specificare la sequenza temporale per la quale deve essere generato il report</span><span class="sxs-lookup"><span data-stu-id="33458-246">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>

2. <span data-ttu-id="33458-247">**Specificare le directory di file** Fornire informazioni sul percorso del file</span><span class="sxs-lookup"><span data-stu-id="33458-247">**Specify the file directories** Provide file location information</span></span>

3. <span data-ttu-id="33458-248">**Raccolta dei registri e avvio del Visualizzatore di report** Eseguire il comando per generare il report</span><span class="sxs-lookup"><span data-stu-id="33458-248">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>

#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="33458-249">Passaggio 1-registrare la sequenza temporale</span><span class="sxs-lookup"><span data-stu-id="33458-249">Step 1 - Log the timeline</span></span>

<span data-ttu-id="33458-250">La registrazione della sequenza temporale consente all'utente dello strumento di specificare quanto segue come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="33458-250">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1. <span data-ttu-id="33458-251">**Data di inizio** Questa è la data di inizio della sequenza temporale per la quale deve essere generato il report. ad esempio, 2010 agosto 1.</span><span class="sxs-lookup"><span data-stu-id="33458-251">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2. <span data-ttu-id="33458-252">**Data di fine** Questa è la data di fine della sequenza temporale per la quale deve essere generato il report. ad esempio, settembre 30, 2010.</span><span class="sxs-lookup"><span data-stu-id="33458-252">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>

     ![Date di inizio e di fine nell'utilizzo della larghezza di banda A](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="33458-254">Passaggio 2: specificare le directory dei file</span><span class="sxs-lookup"><span data-stu-id="33458-254">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="33458-255">Le directory dei file seguenti possono essere specificate dall'utente come illustrato.</span><span class="sxs-lookup"><span data-stu-id="33458-255">The following file directories can be specified by the user as shown.</span></span>

- <span data-ttu-id="33458-256">**Percorso dei file di registro del server** Percorso della cartella in cui sono archiviati i registri del server dei criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="33458-256">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="33458-257">Si tratta in genere di \<fileserver\> \\<scelta di Fe \> \AppServerFiles\PDP.</span><span class="sxs-lookup"><span data-stu-id="33458-257">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>

- <span data-ttu-id="33458-258">**Percorso di archiviazione file temporaneo** Percorso temporaneo del file in cui vengono archiviati i file intermedi durante la generazione del report.</span><span class="sxs-lookup"><span data-stu-id="33458-258">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

    ![Directory dei file nell'utilizzo della larghezza di banda anale](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > <span data-ttu-id="33458-260">Verificare che all'utente dello strumento sia disponibile un numero sufficiente di accessi ai registri del server e alla cartella temporanea dell'archivio file.</span><span class="sxs-lookup"><span data-stu-id="33458-260">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="33458-261">Passaggio 3: raccolta dei registri e avvio del Visualizzatore di report</span><span class="sxs-lookup"><span data-stu-id="33458-261">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="33458-262">Per raccogliere i registri e avviare il Visualizzatore di report, fare clic su **Esegui** come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="33458-262">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="33458-263">Questo passaggio consente di raccogliere i dati necessari.</span><span class="sxs-lookup"><span data-stu-id="33458-263">This step collects the required data.</span></span>

![Raccolta di dati nell'utilizzo della larghezza di banda anale](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

<span data-ttu-id="33458-265">Quando la convalida dell'input ha esito positivo, viene visualizzato il messaggio mostrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="33458-265">When the input validation is successful, the message shown below is displayed.</span></span>

![Registri di notifica raccolti nella larghezza di banda utili](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

<span data-ttu-id="33458-267">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="33458-267">Click **OK**.</span></span> <span data-ttu-id="33458-268">BandwidthUtilizationAnalyzer.xlsm viene avviato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="33458-268">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="33458-269">Seguire le istruzioni riportate nella finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="33458-269">Follow the instructions in the message box.</span></span> <span data-ttu-id="33458-270">Per ulteriori informazioni, vedere **utilizzo di BandwidthUtilizationAnalyzer.xlsm** nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="33458-270">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>


### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="33458-271">Utilizzo di BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="33458-271">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="33458-272">Quando viene avviato automaticamente BandwidthUtilizationAnalyzer.xlsm, fare clic su **Aggiorna** come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="33458-272">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. <span data-ttu-id="33458-274">Quando si apre una cartella di file, selezionare consolidated.csv dal percorso specificato nella finestra di messaggio come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="33458-274">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="33458-275">Viene inoltre visualizzato il percorso come **C:\Temp**.</span><span class="sxs-lookup"><span data-stu-id="33458-275">It also shows the location as **C:\Temp**.</span></span>

     ![Apertura di una cartella in BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. <span data-ttu-id="33458-277">Fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="33458-277">Click **Import**.</span></span>

4. <span data-ttu-id="33458-278">La trama grafica viene generata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="33458-278">The graphical plot is automatically generated.</span></span> <span data-ttu-id="33458-279">È disponibile quando il puntatore di lavoro in background scompare.</span><span class="sxs-lookup"><span data-stu-id="33458-279">It is available when the working-in-the-background pointer disappears.</span></span>

     ![Applicazione di filtri nella visualizzazione report.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="33458-281">Applicazione di filtri alla visualizzazione del report</span><span class="sxs-lookup"><span data-stu-id="33458-281">Applying Filters to the Report View</span></span>

<span data-ttu-id="33458-282">I filtri che è possibile applicare alla visualizzazione del rapporto come illustrato di seguito sono descritti nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="33458-282">The filters that can be applied to the report view as shown below are described as follows:</span></span>

![Applicazione di filtri nella visualizzazione report.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. <span data-ttu-id="33458-284">**Nome** Filtrare in base ai collegamenti WAN (il filtro è a destra del grafico). Il prefisso indica i tipi di collegamento seguenti. vedere la casella verticale (blu):</span><span class="sxs-lookup"><span data-stu-id="33458-284">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>

   - <span data-ttu-id="33458-285">**Sito S** Collegamento WAN da un sito di rete a un'area di rete</span><span class="sxs-lookup"><span data-stu-id="33458-285">**S Site** The WAN link from a network site to a network region</span></span>

   - <span data-ttu-id="33458-286">**È tra siti** Collegamento WAN tra due siti di rete</span><span class="sxs-lookup"><span data-stu-id="33458-286">**IS Inter-Site** The WAN link between two network sites</span></span>

   - <span data-ttu-id="33458-287">**Inter-Region R** Collegamento WAN tra due aree di rete</span><span class="sxs-lookup"><span data-stu-id="33458-287">**R Inter-Region** The WAN link between two network region</span></span>

2. <span data-ttu-id="33458-288">**Limite superato** Filtra mediante collegamenti WAN il cui utilizzo della larghezza di banda è superiore alla capacità della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="33458-288">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3. <span data-ttu-id="33458-289">**Livelli critici** Filtra mediante collegamenti WAN il cui utilizzo della larghezza di banda ha raggiunto il 90% o superiore alla capacità della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="33458-289">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4. <span data-ttu-id="33458-290">**Sottoutilizzati** Filtra mediante collegamenti WAN il cui utilizzo della larghezza di banda è stato inferiore al 25% della capacità della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="33458-290">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5. <span data-ttu-id="33458-291">**Tipo di collegamento** Filtrare in base ai seguenti tipi di collegamenti WAN:</span><span class="sxs-lookup"><span data-stu-id="33458-291">**Link type** Filter by the following WAN links types:</span></span>

   - <span data-ttu-id="33458-292">Tipo di **sito di rete**</span><span class="sxs-lookup"><span data-stu-id="33458-292">**Network site** type</span></span>

   - <span data-ttu-id="33458-293">Tipo **tra siti**</span><span class="sxs-lookup"><span data-stu-id="33458-293">**Inter-site** type</span></span>

   - <span data-ttu-id="33458-294">Tipo **di collegamento tra aree** geografiche</span><span class="sxs-lookup"><span data-stu-id="33458-294">**Inter-Region link** type</span></span>

6. <span data-ttu-id="33458-295">**Area geografica** Filtrare in base all'area di rete</span><span class="sxs-lookup"><span data-stu-id="33458-295">**Region** Filter by network region</span></span>

<span data-ttu-id="33458-296">Nelle figure seguenti vengono illustrati i filtri descritti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="33458-296">The following figures show the previously described filters.</span></span>

<span data-ttu-id="33458-297">Filtrare in base al **nome**.</span><span class="sxs-lookup"><span data-stu-id="33458-297">Filter by **Name**.</span></span> <span data-ttu-id="33458-298">Selezionare l'elenco dei collegamenti che devono essere visualizzati nel grafico.</span><span class="sxs-lookup"><span data-stu-id="33458-298">Select the list of links that need to be displayed in the graph.</span></span>

![Filtro in base al nome in BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

<span data-ttu-id="33458-300">Filtrare in base al **limite superato**.</span><span class="sxs-lookup"><span data-stu-id="33458-300">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="33458-301">Selezionare **true** per applicare il filtro.</span><span class="sxs-lookup"><span data-stu-id="33458-301">Select **True** to enforce the filter.</span></span>

![Filtro in base al limite superato.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

<span data-ttu-id="33458-303">Filtrare in base ai **livelli critici**.</span><span class="sxs-lookup"><span data-stu-id="33458-303">Filter by **Critical levels**.</span></span> <span data-ttu-id="33458-304">Selezionare **true** per applicare il filtro.</span><span class="sxs-lookup"><span data-stu-id="33458-304">Select **True** to enforce the filter.</span></span>

![Filtro in base a livelli critici.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

<span data-ttu-id="33458-306">Filtro in **base a utilizzato**.</span><span class="sxs-lookup"><span data-stu-id="33458-306">Filter by **Under utilized**.</span></span> <span data-ttu-id="33458-307">Selezionare **true** per applicare il filtro.</span><span class="sxs-lookup"><span data-stu-id="33458-307">Select **True** to enforce the filter.</span></span>

![Filtro in base a utilizzato.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

<span data-ttu-id="33458-309">Filtro in base al **tipo di collegamento**.</span><span class="sxs-lookup"><span data-stu-id="33458-309">Filter by **Link Type**.</span></span> <span data-ttu-id="33458-310">Selezionare il tipo o i tipi che devono essere visualizzati.</span><span class="sxs-lookup"><span data-stu-id="33458-310">Select the type or types that need to be displayed.</span></span>

![Filtro in base al tipo di collegamento.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

<span data-ttu-id="33458-312">Filtrare in base all' **area geografica**.</span><span class="sxs-lookup"><span data-stu-id="33458-312">Filter by **Region**.</span></span> <span data-ttu-id="33458-313">Selezionare un elenco di aree di cui devono essere visualizzati i collegamenti.</span><span class="sxs-lookup"><span data-stu-id="33458-313">Select a list of regions whose links need to be displayed.</span></span>

![Filtro in base all'area geografica.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a><span data-ttu-id="33458-315">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33458-315">Requirements</span></span>

- <span data-ttu-id="33458-316">.NET Framework 3,5</span><span class="sxs-lookup"><span data-stu-id="33458-316">The .NET Framework 3.5</span></span>

- <span data-ttu-id="33458-317">Microsoft Excel 2010 o Excel 2007</span><span class="sxs-lookup"><span data-stu-id="33458-317">Microsoft Excel 2010 or Excel 2007</span></span>

### <a name="summary"></a><span data-ttu-id="33458-318">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="33458-318">Summary</span></span>

<span data-ttu-id="33458-319">L'analizzatore dell'utilizzo della larghezza di banda viene utilizzato per tracciare l'utilizzo della larghezza di banda audio per il traffico UC sulla rete.</span><span class="sxs-lookup"><span data-stu-id="33458-319">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="33458-320">Questo strumento può essere utilizzato per segnalare l'utilizzo della larghezza di banda video anche sulla rete.</span><span class="sxs-lookup"><span data-stu-id="33458-320">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

## <a name="call-parkometer"></a><span data-ttu-id="33458-321">Chiamata Parkometer</span><span class="sxs-lookup"><span data-stu-id="33458-321">Call Parkometer</span></span>
<span data-ttu-id="33458-322"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="33458-322"><a name="callpark"> </a></span></span>

<span data-ttu-id="33458-323">Call Parkometer è un'applicazione della riga di comando che consente di accedere facilmente al database di orbit del parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="33458-323">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

### <a name="description"></a><span data-ttu-id="33458-324">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33458-324">Description</span></span>

<span data-ttu-id="33458-325">Call Parkometer è uno strumento che consente di monitorare le chiamate attualmente parcheggiate.</span><span class="sxs-lookup"><span data-stu-id="33458-325">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="33458-326">Raccoglie anche le statistiche sulle orbite e sull'utilizzo del server parcheggio di chiamata (CPS).</span><span class="sxs-lookup"><span data-stu-id="33458-326">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="33458-327">Questo strumento da riga di comando fornisce sia la lettura che l'accesso in scrittura al database di SQL Server Orbit di CPS da un computer locale o connesso in remoto.</span><span class="sxs-lookup"><span data-stu-id="33458-327">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="33458-328">Tutte le opzioni sono mutualmente esclusive.</span><span class="sxs-lookup"><span data-stu-id="33458-328">All options are mutually exclusive.</span></span> <span data-ttu-id="33458-329">La sintassi della riga di comando è la seguente:</span><span class="sxs-lookup"><span data-stu-id="33458-329">Command-line syntax is as follows:</span></span>

- <span data-ttu-id="33458-330">**-o** parameter: elenca tutti gli intervalli di Orbit configurati per il pool.</span><span class="sxs-lookup"><span data-stu-id="33458-330">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>

- <span data-ttu-id="33458-331">**-n** parameter: elenca tutte le orbite attualmente utilizzate nel pool.</span><span class="sxs-lookup"><span data-stu-id="33458-331">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="33458-332">Di seguito sono riportate le informazioni visualizzate:</span><span class="sxs-lookup"><span data-stu-id="33458-332">The information displayed is as follows:</span></span>

  - <span data-ttu-id="33458-333">URI (Uniform Resource Identifier) SIP del parcheggiato e del Parker.</span><span class="sxs-lookup"><span data-stu-id="33458-333">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>

  - <span data-ttu-id="33458-334">Nome host del CPS in cui è parcheggiata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="33458-334">Host name of the CPS where the call is parked.</span></span>

  - <span data-ttu-id="33458-335">Indicatore di data e ora di quando la chiamata è stata parcheggiata.</span><span class="sxs-lookup"><span data-stu-id="33458-335">Time stamp of when the call was parked.</span></span>

- <span data-ttu-id="33458-336">**-f** parameter: elenca il numero di orbite attualmente libere nel pool.</span><span class="sxs-lookup"><span data-stu-id="33458-336">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>

- <span data-ttu-id="33458-337">**-r \<n\>** Parameter: elenca le \<n\> ultime chiamate parcheggiate.</span><span class="sxs-lookup"><span data-stu-id="33458-337">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="33458-338">Di seguito sono riportate le informazioni visualizzate:</span><span class="sxs-lookup"><span data-stu-id="33458-338">The information displayed is as follows:</span></span>

  - <span data-ttu-id="33458-339">URI SIP del parcheggio.</span><span class="sxs-lookup"><span data-stu-id="33458-339">Parkee SIP URI.</span></span>

  - <span data-ttu-id="33458-340">URI SIP Parker.</span><span class="sxs-lookup"><span data-stu-id="33458-340">Parker SIP URI.</span></span>

  - <span data-ttu-id="33458-341">Nome host del CPS in cui la chiamata è stata parcheggiata.</span><span class="sxs-lookup"><span data-stu-id="33458-341">Host name of the CPS where the call was parked.</span></span>

  - <span data-ttu-id="33458-342">Indicatore di data e ora di quando la chiamata è stata recuperata o eliminata.</span><span class="sxs-lookup"><span data-stu-id="33458-342">Time stamp of when the call was retrieved or dropped.</span></span>

- <span data-ttu-id="33458-343">**-t \<n\>** parametri-test che conservano un'orbita nel database per mostrare la casualità dei numeri di orbita assegnati.</span><span class="sxs-lookup"><span data-stu-id="33458-343">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

### <a name="output"></a><span data-ttu-id="33458-344">Output</span><span class="sxs-lookup"><span data-stu-id="33458-344">Output</span></span>

<span data-ttu-id="33458-345">In base ai parametri di input specificati al prompt dei comandi, la chiamata a Parkometer Visualizza l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="33458-345">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

- <span data-ttu-id="33458-346">Tutti gli intervalli di Orbit configurati per il pool</span><span class="sxs-lookup"><span data-stu-id="33458-346">All orbit ranges that are configured for this pool</span></span>

- <span data-ttu-id="33458-347">Chiamate attualmente parcheggiate</span><span class="sxs-lookup"><span data-stu-id="33458-347">Currently parked calls</span></span>

- <span data-ttu-id="33458-348">Numero di orbite libere (disponibili)</span><span class="sxs-lookup"><span data-stu-id="33458-348">Number of free (available) orbits</span></span>

- <span data-ttu-id="33458-349">Chiamate parcheggiate di recente</span><span class="sxs-lookup"><span data-stu-id="33458-349">Recently parked calls</span></span>

- <span data-ttu-id="33458-350">Orbite riservate per testare valori di Orbit uniformi e casuali</span><span class="sxs-lookup"><span data-stu-id="33458-350">Reserved orbits for testing uniform and random orbit values</span></span>

### <a name="purpose"></a><span data-ttu-id="33458-351">Finalità</span><span class="sxs-lookup"><span data-stu-id="33458-351">Purpose</span></span>

<span data-ttu-id="33458-352">Lo strumento CPS ha lo scopo di fornire l'accesso da riga di comando al database CPS.</span><span class="sxs-lookup"><span data-stu-id="33458-352">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="33458-353">L'amministratore può visualizzare l'utilizzo di CPS e determinare il numero di orbite assegnate a un pool.</span><span class="sxs-lookup"><span data-stu-id="33458-353">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

### <a name="requirements"></a><span data-ttu-id="33458-354">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33458-354">Requirements</span></span>

<span data-ttu-id="33458-355">Se lo strumento viene eseguito nello stesso computer in cui è in esecuzione CPS, non è previsto alcun requisito.</span><span class="sxs-lookup"><span data-stu-id="33458-355">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="33458-356">Se lo strumento viene eseguito in un computer remoto, il database di SQL Server utilizzato da Skype for Business Server 2015 deve essere configurato in modo da consentire l'accesso remoto.</span><span class="sxs-lookup"><span data-stu-id="33458-356">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="33458-357">La chiamata Parkometer deve essere configurata con una stringa di connessione al database di SQL Server per la connessione al server SQL del pool.</span><span class="sxs-lookup"><span data-stu-id="33458-357">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="33458-358">La stringa di connessione del database di SQL Server è definita nel file di configurazione **parkometer.exe.config**. Deve essere collocato nella stessa directory in cui si trova parkometer.exe.</span><span class="sxs-lookup"><span data-stu-id="33458-358">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="33458-359">Il file XML seguente è un esempio di parkometer.exe.config. I parametri che devono essere configurati sono il nome utente (ad esempio, mydomain\Administrator), la password (ad esempio, password) e il nome host, ad esempio myserver.</span><span class="sxs-lookup"><span data-stu-id="33458-359">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

### <a name="examples"></a><span data-ttu-id="33458-360">Esempi</span><span class="sxs-lookup"><span data-stu-id="33458-360">Examples</span></span>

<span data-ttu-id="33458-361">Intervalli di Orbit distribuiti: il parametro-o elenca tutti gli intervalli di Orbit configurati per il pool come illustrato</span><span class="sxs-lookup"><span data-stu-id="33458-361">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

![Intervalli di Orbit in Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

<span data-ttu-id="33458-363">Chiamate attualmente parcheggiate: il parametro-n elenca tutte le orbite attualmente utilizzate in questo pool come illustrato</span><span class="sxs-lookup"><span data-stu-id="33458-363">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>

![Chiamate al momento parcheggiate in Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

<span data-ttu-id="33458-365">Numero di orbite libere: il parametro-f elenca il numero di orbite attualmente libere nel pool come mostrato</span><span class="sxs-lookup"><span data-stu-id="33458-365">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>

![Orbite gratuite in Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

<span data-ttu-id="33458-367">Chiamate parcheggiate di recente: il parametro-r \<n\> elenca le \<n\> ultime chiamate parcheggiate come mostrato</span><span class="sxs-lookup"><span data-stu-id="33458-367">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

![Chiamate parcheggiate di recente in Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

<span data-ttu-id="33458-369">Test Orbit Reservation: i test dei parametri-t che riservano \<n\> un'orbita nel database come illustrato</span><span class="sxs-lookup"><span data-stu-id="33458-369">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

![Testare le prenotazioni in orbita in Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a><span data-ttu-id="33458-371">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="33458-371">Summary</span></span>

<span data-ttu-id="33458-372">Call Parkometer è uno strumento da riga di comando che fornisce informazioni dettagliate sul server parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="33458-372">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

## <a name="dbanalyze"></a><span data-ttu-id="33458-373">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="33458-373">DBAnalyze</span></span>
<span data-ttu-id="33458-374"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="33458-374"><a name="dba"> </a></span></span>

### <a name="description"></a><span data-ttu-id="33458-375">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33458-375">Description</span></span>

<span data-ttu-id="33458-376">DBAnalyze è uno strumento da riga di comando che consente agli amministratori di raccogliere i report di analisi sui database di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-376">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="33458-377">In DBAnalyze sono disponibili le seguenti modalità: diagnostica, dati utente, conferenza, MCU e frammentazione del disco:</span><span class="sxs-lookup"><span data-stu-id="33458-377">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

- <span data-ttu-id="33458-378">**Modalità diagnostica** Crea un report in cui sono incluse informazioni sulle tabelle (numero di record, frammentazione, dimensioni dei dati e dimensioni dell'indice) dimensioni dei file di dati e di log, l'ultimo tempo di backup, la distribuzione dei contatti tra i server che eseguono Microsoft Office Communications Server, il numero medio di autorizzazioni, contatti, contenitori, abbonamenti, pubblicazioni, endpoint per utente, tutti gli utenti che non possono essere instradati, il numero medio di conferenze organizzate per utente, conferenze pianificate, conferenze attive</span><span class="sxs-lookup"><span data-stu-id="33458-378">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>

    > [!NOTE]
    > <span data-ttu-id="33458-379">L'esecuzione della modalità diagnostica può influire sulle prestazioni del server.</span><span class="sxs-lookup"><span data-stu-id="33458-379">Running diagnostic mode can affect server performance.</span></span>

- <span data-ttu-id="33458-380">**Modalità dati utente** Segnala i dati relativi a contatti, contenitori, abbonamenti, pubblicazioni, autorizzazioni e gruppi di contatti per un utente specificato o per gli utenti che dispongono di tale utente negli elenchi di contatti e autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="33458-380">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="33458-381">Questa modalità segnala anche i dati di riepilogo per le conferenze a cui un utente organizza o è invitato.</span><span class="sxs-lookup"><span data-stu-id="33458-381">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

- <span data-ttu-id="33458-382">**Modalità conferenza** Segnala i dati dettagliati per una conferenza specifica, inclusi tutti i dettagli relativi alla programmazione per la conferenza, l'elenco degli invitati, l'elenco dei tipi di contenuto multimediale consentiti per la conferenza, i MCU attivi (unità di controllo multipunto), l'elenco dei partecipanti attivi e lo stato di segnalazione di ogni partecipante.</span><span class="sxs-lookup"><span data-stu-id="33458-382">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>

- <span data-ttu-id="33458-383">**Decodifica ID riunione** Consente di decodificare un ID riunione PSTN (Public Switched Telephone Network) specificato dall'opzione **/pstnid** ma non viene connesso al back-end per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="33458-383">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

- <span data-ttu-id="33458-384">**Risoluzione conferenza** Consente di decodificare un ID riunione PSTN specificato dall'opzione **/pstnid** e di visualizzare le informazioni sulla conferenza indicate dall'ID.</span><span class="sxs-lookup"><span data-stu-id="33458-384">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

- <span data-ttu-id="33458-385">**Modalità MCU** Segnala l'ID, il tipo di supporto, l'URL, lo stato del battito cardiaco, il carico delle conferenze e il carico dei partecipanti per ogni MCU del pool.</span><span class="sxs-lookup"><span data-stu-id="33458-385">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

- <span data-ttu-id="33458-386">**Modalità di frammentazione del disco** Visualizza lo stato di frammentazione di tutti i dischi.</span><span class="sxs-lookup"><span data-stu-id="33458-386">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="33458-387">Questo strumento può essere utilizzato per diagnosticare diversi problemi o per assistere gli amministratori nella pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="33458-387">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="33458-388">Ad esempio, se la maggior parte degli utenti ospitati nel server A sceglie gli utenti ospitati nel server B come contatti, l'amministratore può spostare gli utenti nel server a nel server B per ridurre il traffico tra server.</span><span class="sxs-lookup"><span data-stu-id="33458-388">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

### <a name="output"></a><span data-ttu-id="33458-389">Output</span><span class="sxs-lookup"><span data-stu-id="33458-389">Output</span></span>

<span data-ttu-id="33458-390">Questo strumento restituisce i report predefiniti relativi al database di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-390">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="33458-391">**Percorso**:%ProgramFiles%\Skype for Business Server 2015 \ reskit</span><span class="sxs-lookup"><span data-stu-id="33458-391">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>

### <a name="purpose"></a><span data-ttu-id="33458-392">Finalità</span><span class="sxs-lookup"><span data-stu-id="33458-392">Purpose</span></span>

<span data-ttu-id="33458-393">Per installare Dbanalyze.exe, copiarlo in una cartella locale e quindi eseguire lo strumento.</span><span class="sxs-lookup"><span data-stu-id="33458-393">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="33458-394">Per utilizzare lo strumento, eseguire il comando riportato di seguito dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="33458-394">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="33458-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` Di seguito sono riportate le descrizioni delle opzioni della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="33458-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>

![Opzioni della riga di comando per Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a><span data-ttu-id="33458-397">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33458-397">Requirements</span></span>

 <span data-ttu-id="33458-398">**Computer** DBAnalyze può essere eseguito solo da un computer aggiunto al dominio in cui è installato Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-398">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>

 <span data-ttu-id="33458-399">**Rete** Il computer deve essere in grado di connettersi al database back-end.</span><span class="sxs-lookup"><span data-stu-id="33458-399">**Network** The computer should be able to connect to the back-end database.</span></span>

 <span data-ttu-id="33458-400">**Software** I componenti software di Skype for Business Server 2015 devono essere installati prima di eseguire DBAnalyze.</span><span class="sxs-lookup"><span data-stu-id="33458-400">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>

 <span data-ttu-id="33458-401">**Utenti** Nella tabella seguente sono riportati gli amministratori che dispongono delle autorizzazioni necessarie per accedere ai database di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-401">**Users** The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>

![Tabella delle autorizzazioni per Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> <span data-ttu-id="33458-403">Per **/report: modalità disco** è necessario un account di amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="33458-403">A local administrator account is required for **/report:disk** mode.</span></span>

### <a name="examples"></a><span data-ttu-id="33458-404">Esempi</span><span class="sxs-lookup"><span data-stu-id="33458-404">Examples</span></span>

<span data-ttu-id="33458-405">Di seguito sono riportati alcuni esempi di comandi di Dbanalyze.exe validi:</span><span class="sxs-lookup"><span data-stu-id="33458-405">The following are examples of valid Dbanalyze.exe commands:</span></span>

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="33458-406">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="33458-406">Summary</span></span>

<span data-ttu-id="33458-407">DBAnalyzer offre agli amministratori una soluzione rapida e semplice per l'analisi dei database di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-407">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>

## <a name="import-storage-service-data"></a><span data-ttu-id="33458-408">Importare i dati del servizio di archiviazione</span><span class="sxs-lookup"><span data-stu-id="33458-408">Import Storage Service Data</span></span>
<span data-ttu-id="33458-409"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="33458-409"><a name="Issd"> </a></span></span>

<span data-ttu-id="33458-410">Lo strumento ImportStorageServiceData Resource Kit consente di riimportare i dati di coda e di endpoint che sono stati scaricati dal servizio di archiviazione (LYSS) nuovamente nel servizio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="33458-410">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

### <a name="description"></a><span data-ttu-id="33458-411">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33458-411">Description</span></span>

<span data-ttu-id="33458-412">I dati scaricati dal servizio di archiviazione avrebbero potuto essere automatici (periodici) in base allo stato della coda o alle dimensioni del database.</span><span class="sxs-lookup"><span data-stu-id="33458-412">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="33458-413">Potrebbe essere accaduto a causa della chiamata manuale del cmdlet di failover del pool oppure del cmdlet StorageServiceFullFlush (che richiama il cmdlet di failover del pool).</span><span class="sxs-lookup"><span data-stu-id="33458-413">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="33458-414">Si noti che i dati non devono essere reimportati idealmente se una delle dimensioni del database del servizio di archiviazione (LYSS) ai front-end è superiore al livello normale, perché in questo modo è probabile che vengano esportati più dati da esportare. Inoltre, tutti i problemi che potrebbero aver contribuito a errori che hanno causato la crescita della coda del servizio di archiviazione devono essere prima risolti (ad esempio, errori di endpoint di Exchange, problemi di rete o altri problemi).</span><span class="sxs-lookup"><span data-stu-id="33458-414">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

 <span data-ttu-id="33458-415">**Scenario 1:** durante il failover del pool, i file possono essere scaricati dal servizio di archiviazione per ogni front-end.</span><span class="sxs-lookup"><span data-stu-id="33458-415">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="33458-416">Dopo aver completato il failover, è necessario eseguire lo strumento per importare di nuovo i dati.</span><span class="sxs-lookup"><span data-stu-id="33458-416">After failover is completed, the tool should be run to re-import the data.</span></span>

 <span data-ttu-id="33458-417">**Scenario 2:** i dati vengono scaricati automaticamente ogni giorno o in risposta al database del servizio di archiviazione che supera le soglie di determinate dimensioni, ad esempio 60%, 80%, 90% Full.</span><span class="sxs-lookup"><span data-stu-id="33458-417">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="33458-418">I dati scaricati automaticamente devono essere reimportati di routine dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="33458-418">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="33458-419">Nella situazione precedente, se il Monitoring SCOM Pack non è distribuito, esistono eventi per il servizio di archiviazione di Skype for Business Server relativo ai dati scaricati dal servizio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="33458-419">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="33458-420">ID evento di 32075 (operazione full Flush è stato avviato), 32076 (Full Flush è stato completato), 32082 (livello di manutenzione incasso iniziato), 32083 (livello di manutenzione incasso completo), 32089 (si è verificato un errore a causa del riempimento del database).</span><span class="sxs-lookup"><span data-stu-id="33458-420">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="33458-421">Nota Questi ID di evento corrispondono alla versione RTM.</span><span class="sxs-lookup"><span data-stu-id="33458-421">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="33458-422">Quando un amministratore Visualizza questi eventi, significa che sono presenti file che sono stati scaricati. Questi dati devono essere importati di nuovo usando questo strumento, ad esempio una volta alla settimana.</span><span class="sxs-lookup"><span data-stu-id="33458-422">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="33458-423">Per la versione del servizio online, se il monitoraggio dell'integrità SCOM Pack per Skype for Business Server è distribuito, sono disponibili nuovi avvisi che possono essere generati dall'amministratore per reimportare nuovamente i dati scaricati nel servizio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="33458-423">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="33458-424">Nel log eventi del front end server è presente un evento corrispondente che ha attivato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="33458-424">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="33458-425">L'evento fornirà una descrizione del percorso padre in cui si trovano i file di dati scaricati, nonché il numero di file che soddisfano i criteri di avviso.</span><span class="sxs-lookup"><span data-stu-id="33458-425">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="33458-426">I criteri di avviso sono che sono presenti X o più file sotto il percorso padre specifico che hanno almeno Y giorni (dove X e Y sono preimpostati all'interno di StorageService ma possono essere ignorati cambiando il file APPCONFIG). Di seguito sono riportati due esempi di eventi che possono attivare l'avviso di integrità, con la differenza che è il percorso padre.</span><span class="sxs-lookup"><span data-stu-id="33458-426">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="33458-427">Una possibilità è in condivisione file del servizio Web, mentre l'altra possibilità è la directory dei dati dell'applicazione locale di ogni front-end.</span><span class="sxs-lookup"><span data-stu-id="33458-427">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="33458-428">(ad esempio, c:\ProgramData\Microsoft\Skype for Business Server 2015 \ StorageService).</span><span class="sxs-lookup"><span data-stu-id="33458-428">( for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ).</span></span> <span data-ttu-id="33458-429">L'amministratore eseguirà quindi questo strumento reskit.</span><span class="sxs-lookup"><span data-stu-id="33458-429">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="33458-430">Questo strumento aumenterà il carico di CPU e IO sul front-end in cui è in esecuzione, oltre ad altri front-end, nella situazione in cui i dati non sono posseduti dal front-end in cui viene eseguito lo strumento.</span><span class="sxs-lookup"><span data-stu-id="33458-430">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="33458-431">Si consiglia di Runng questo strumento quando i front-end non sono sotto carico elevato di CPU e IO, ad esempio al di fuori delle ore di punta.</span><span class="sxs-lookup"><span data-stu-id="33458-431">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="33458-432">In secondo luogo, questo strumento può includere da 2 a 3 minuti per importare un file di dati.</span><span class="sxs-lookup"><span data-stu-id="33458-432">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="33458-433">Tenere presente questo valore quando si stima la durata dell'esecuzione dello strumento.</span><span class="sxs-lookup"><span data-stu-id="33458-433">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="33458-434">Il file di registro dettagliato generato dallo strumento verrà visualizzato per impostazione predefinita nell'archivio file.</span><span class="sxs-lookup"><span data-stu-id="33458-434">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="33458-435">Eliminarlo se non sono stati segnalati errori, in quanto il file di registro può essere pari o superiore a 10 MB.</span><span class="sxs-lookup"><span data-stu-id="33458-435">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

![Eventi del registro eventi del server di archiviazione di esempio.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a><span data-ttu-id="33458-437">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33458-437">Requirements</span></span>

<span data-ttu-id="33458-438">Installare gli strumenti del Resource Kit di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-438">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="33458-439">Lo strumento viene eseguito su computer aggiunti a un dominio in cui sono installati Skype for Business Server e Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="33458-439">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="33458-440">Lo strumento utilizza un cmdlet dalla shell di gestione per identificare tutti i Front End Server nel pool.</span><span class="sxs-lookup"><span data-stu-id="33458-440">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="33458-441">In secondo luogo, è necessario eseguire lo strumento da un computer del pool in cui è installato il database di **RtcLocal** .</span><span class="sxs-lookup"><span data-stu-id="33458-441">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="33458-442">Questo database viene utilizzato dallo strumento per recuperare il percorso della condivisione file WEBSERVICE per il pool.</span><span class="sxs-lookup"><span data-stu-id="33458-442">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="33458-443">Inoltre, prima di utilizzare lo strumento, ogni Front End Server deve innanzitutto abilitare la comunicazione remota di Windows PowerShell tramite **Enable-PSRemoting** in ogni Front End Server, nonché il computer da cui viene eseguito lo strumento.</span><span class="sxs-lookup"><span data-stu-id="33458-443">Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="33458-444">In caso contrario, i comandi remoti di Windows PowerShell da questo strumento avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="33458-444">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="33458-445">La comunicazione remota di Windows PowerShell può essere disattivata in tutti i Front End Server nel pool dopo che è stata completata.</span><span class="sxs-lookup"><span data-stu-id="33458-445">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="33458-446">Infine, l'account o la credenziale che richiama lo strumento deve disporre dell'autorizzazione di lettura/scrittura per la condivisione file WebService per il pool in cui è in esecuzione lo strumento.</span><span class="sxs-lookup"><span data-stu-id="33458-446">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="33458-447">In caso contrario, lo strumento avrà esito negativo con errori di autorizzazione di IO.</span><span class="sxs-lookup"><span data-stu-id="33458-447">Otherwise the tool will fail with IO Permission errors.</span></span>

> [!NOTE]
> <span data-ttu-id="33458-448">In Windows Server 2012, la comunicazione remota di Windows PowerShell è abilitata per impostazione predefinita, ma non nel sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="33458-448">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>

### <a name="examples"></a><span data-ttu-id="33458-449">Esempi</span><span class="sxs-lookup"><span data-stu-id="33458-449">Examples</span></span>

```console
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
```

## <a name="lcssync"></a><span data-ttu-id="33458-450">LCSSync</span><span class="sxs-lookup"><span data-stu-id="33458-450">LCSSync</span></span>
<span data-ttu-id="33458-451"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="33458-451"><a name="LCSSync"> </a></span></span>

<span data-ttu-id="33458-452">Lo strumento LCSSync consente di distribuire il software di comunicazione di Skype for Business Server 2015 in un ambiente con più foreste.</span><span class="sxs-lookup"><span data-stu-id="33458-452">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="33458-453">Questo strumento viene utilizzato per sincronizzare gli utenti e i gruppi provenienti da foreste di utenti diverse come un oggetto contatto di servizi di dominio Active Directory in una foresta centrale in cui è installato Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-453">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>

### <a name="description"></a><span data-ttu-id="33458-454">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33458-454">Description</span></span>

 <span data-ttu-id="33458-455">LCSSync utilizza gli oggetti contatto di servizi di dominio Active Directory sincronizzati nella foresta centrale per consentire agli utenti di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="33458-455">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="33458-456">Per fornire l'accesso Single Sign-in, è necessario eseguire il mapping dell'account utente primario all'oggetto contatto dei servizi di dominio Active Directory nella foresta centrale per Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-456">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="33458-457">Questo strumento consente di eseguire tale mapping.</span><span class="sxs-lookup"><span data-stu-id="33458-457">This tool helps perform that mapping.</span></span> <span data-ttu-id="33458-458">Questo strumento fornisce modelli per la creazione di agenti di gestione in Microsoft Identity Integration Server.</span><span class="sxs-lookup"><span data-stu-id="33458-458">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

### <a name="summary"></a><span data-ttu-id="33458-459">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="33458-459">Summary</span></span>

<span data-ttu-id="33458-460">Lo strumento LCSSync consente di distribuire Skype for Business Server 2015 in un ambiente con più foreste.</span><span class="sxs-lookup"><span data-stu-id="33458-460">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>

## <a name="lookup-user-console"></a><span data-ttu-id="33458-461">Console utente di ricerca</span><span class="sxs-lookup"><span data-stu-id="33458-461">Lookup User Console</span></span>
<span data-ttu-id="33458-462"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="33458-462"><a name="LUC"> </a></span></span>

<span data-ttu-id="33458-463">Lo strumento LookupUserConsole consente di visualizzare le informazioni di routing interne di Skype for Business Server relative a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="33458-463">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="33458-464">Tali informazioni possono essere utili per il supporto tecnico di Microsoft nella diagnostica dei problemi di distribuzione e routing.</span><span class="sxs-lookup"><span data-stu-id="33458-464">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

### <a name="description"></a><span data-ttu-id="33458-465">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33458-465">Description</span></span>

 <span data-ttu-id="33458-466">L'esecuzione di LookupUserConsole.exe aprirà un prompt dei comandi che accetta gli indirizzi SIP e tenta di visualizzare le informazioni di routing interne di Skype for Business Server correlate.</span><span class="sxs-lookup"><span data-stu-id="33458-466">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="33458-467">Digitare **Exit** per chiudere lo strumento LookupUserConsole.</span><span class="sxs-lookup"><span data-stu-id="33458-467">Type **exit** to quit the LookupUserConsole tool.</span></span>

### <a name="requirements"></a><span data-ttu-id="33458-468">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33458-468">Requirements</span></span>

<span data-ttu-id="33458-469">Installare il Resource Kit di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-469">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="33458-470">Lo strumento viene eseguito nei computer aggiunti a un dominio in cui è installato Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="33458-470">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>

### <a name="examples"></a><span data-ttu-id="33458-471">Esempi</span><span class="sxs-lookup"><span data-stu-id="33458-471">Examples</span></span>

<span data-ttu-id="33458-472">C:\Program Skype for Business Server 2015 \ reskit \>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="33458-472">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>

```console
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
```

## <a name="msturnping"></a><span data-ttu-id="33458-473">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="33458-473">MsTurnPing</span></span>
<span data-ttu-id="33458-474"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="33458-474"><a name="MsTurnPing"> </a></span></span>

<span data-ttu-id="33458-475">Lo strumento MSTurnPing consente a un amministratore del software di comunicazione di Skype for Business Server 2015 di controllare lo stato dei server che eseguono i servizi di autenticazione audio/video e i server che eseguono i servizi di criteri di larghezza di banda nella topologia.</span><span class="sxs-lookup"><span data-stu-id="33458-475">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

### <a name="description"></a><span data-ttu-id="33458-476">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33458-476">Description</span></span>

<span data-ttu-id="33458-477">Lo strumento MSTurnPing consente a un amministratore del software di comunicazione di Skype for Business Server 2015 di controllare lo stato dei server che eseguono i servizi di autenticazione audio/video e i server che eseguono i servizi di criteri di larghezza di banda nella topologia.</span><span class="sxs-lookup"><span data-stu-id="33458-477">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="33458-478">Lo strumento consente all'amministratore di eseguire i test seguenti:</span><span class="sxs-lookup"><span data-stu-id="33458-478">The tool allows the administrator to perform the following tests:</span></span>

1. <span data-ttu-id="33458-479">Test a/V Edge Server: lo strumento esegue test su tutti i server a/V Edge nella topologia eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33458-479">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>

   - <span data-ttu-id="33458-480">Verificare che il servizio di autenticazione audio/video di Skype for Business Server sia stato avviato e che possa emettere credenziali appropriate.</span><span class="sxs-lookup"><span data-stu-id="33458-480">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="33458-481">Verifica del corretto avvio del servizio Web di Skype for Business Server per l'audio/video Edge ed è in grado di allocare correttamente le risorse sul perimetro esterno.</span><span class="sxs-lookup"><span data-stu-id="33458-481">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2. <span data-ttu-id="33458-482">Test del servizio criteri di larghezza di banda: lo strumento esegue test su tutti i server che eseguono i servizi dei criteri di larghezza di banda nella topologia eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33458-482">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>

   - <span data-ttu-id="33458-483">Verificare che il servizio criteri di larghezza di banda di Skype for Business Server (autenticazione) sia avviato e possa emettere credenziali appropriate.</span><span class="sxs-lookup"><span data-stu-id="33458-483">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="33458-484">Verificare che il servizio criteri di larghezza di banda di Skype for Business Server (Core) sia stato avviato e che sia in grado di eseguire correttamente il controllo della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="33458-484">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="33458-485">Questo strumento deve essere eseguito da un computer che fa parte della topologia e l'archivio locale è installato.</span><span class="sxs-lookup"><span data-stu-id="33458-485">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

### <a name="output"></a><span data-ttu-id="33458-486">Output</span><span class="sxs-lookup"><span data-stu-id="33458-486">Output</span></span>

<span data-ttu-id="33458-487">Lo strumento restituisce i risultati di ciascuna delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="33458-487">The tool outputs the results of each of the operations.</span></span>

- <span data-ttu-id="33458-488">Se viene eseguito il test di **AudioVideoEdgeServer** , gli output dello strumento sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="33458-488">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="33458-489">I risultati del test dei computer che forniscono il servizio di autenticazione audio/video di Skype for Business Server 2015 nella topologia</span><span class="sxs-lookup"><span data-stu-id="33458-489">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>

  - <span data-ttu-id="33458-490">I risultati del test dei computer che forniscono il servizio audio/video Edge di Skype for Business Server 2015 nella topologia</span><span class="sxs-lookup"><span data-stu-id="33458-490">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>

- <span data-ttu-id="33458-491">Se viene eseguito il test di **BandwidthPolicyServer** , gli output dello strumento sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="33458-491">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="33458-492">I risultati del test dei computer che forniscono il servizio criteri di larghezza di banda di Skype for Business Server 2015 (autenticazione) nella topologia</span><span class="sxs-lookup"><span data-stu-id="33458-492">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>

  - <span data-ttu-id="33458-493">I risultati del test dei computer che forniscono il servizio criteri di larghezza di banda di Skype for Business Server 2015 (Core) nella topologia</span><span class="sxs-lookup"><span data-stu-id="33458-493">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>

### <a name="requirements"></a><span data-ttu-id="33458-494">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33458-494">Requirements</span></span>

- <span data-ttu-id="33458-495">Questo strumento deve essere eseguito da un computer presente nella topologia e con l'archivio locale.</span><span class="sxs-lookup"><span data-stu-id="33458-495">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

- <span data-ttu-id="33458-496">Lo strumento deve essere eseguito come un amministratore che ha accesso all'archivio locale.</span><span class="sxs-lookup"><span data-stu-id="33458-496">The tool must be run as an administrator who has access to the local store.</span></span>

### <a name="examples"></a><span data-ttu-id="33458-497">Esempi</span><span class="sxs-lookup"><span data-stu-id="33458-497">Examples</span></span>

<span data-ttu-id="33458-498">Di seguito è riportato un esempio di input dello strumento.</span><span class="sxs-lookup"><span data-stu-id="33458-498">The following is an example of the tool input.</span></span>

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="33458-499">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="33458-499">Summary</span></span>

<span data-ttu-id="33458-500">Questo strumento può essere una risorsa importante per gli amministratori di Skype for Business Server 2015 che desiderano controllare lo stato dei server che eseguono i servizi di criteri di larghezza di banda e audio/video.</span><span class="sxs-lookup"><span data-stu-id="33458-500">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

## <a name="network-configuration-viewer"></a><span data-ttu-id="33458-501">Visualizzatore di configurazione di rete</span><span class="sxs-lookup"><span data-stu-id="33458-501">Network Configuration Viewer</span></span>
<span data-ttu-id="33458-502"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="33458-502"><a name="NCV"> </a></span></span>

<span data-ttu-id="33458-503">Il Visualizzatore di configurazione di rete può essere utilizzato dagli amministratori del software di comunicazione di Skype for Business Server 2015 per visualizzare la topologia di rete di controllo di ammissione di chiamata per un'azienda di cui è stato effettuato il provisioning per consentire sessioni di comunicazione in tempo reale, quali chiamate vocali o video in base alla capacità di larghezza di banda specificata.</span><span class="sxs-lookup"><span data-stu-id="33458-503">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="33458-504">Gli amministratori di Skype for Business Server 2015 definiscono i criteri di CAC, applicati dai servizi per i criteri di larghezza di banda installati con Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-504">Skype for Business Server 2015 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>

### <a name="description"></a><span data-ttu-id="33458-505">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33458-505">Description</span></span>

<span data-ttu-id="33458-506">Il Visualizzatore di configurazione di rete (NetworkConfigurationViewer.exe) consente agli amministratori di eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="33458-506">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

- <span data-ttu-id="33458-507">Caricare e visualizzare la topologia di rete CAC da una distribuzione di Skype for Business Server 2015 in formato grafico.</span><span class="sxs-lookup"><span data-stu-id="33458-507">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>

- <span data-ttu-id="33458-508">Caricare e visualizzare la topologia di rete CAC da un file di registro del server dei criteri di larghezza di banda in formato grafico.</span><span class="sxs-lookup"><span data-stu-id="33458-508">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

- <span data-ttu-id="33458-509">Salvare e archiviare la topologia di rete CAC in un formato XML sul disco.</span><span class="sxs-lookup"><span data-stu-id="33458-509">Save and store CAC network topology in an XML format on the disk.</span></span>

- <span data-ttu-id="33458-510">Salvare e archiviare il diagramma della topologia di rete CAC in formato JPG o BMP.</span><span class="sxs-lookup"><span data-stu-id="33458-510">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

- <span data-ttu-id="33458-511">Visualizzare i dati di configurazione della topologia di rete CAC.</span><span class="sxs-lookup"><span data-stu-id="33458-511">View CAC network topology configuration data.</span></span>

- <span data-ttu-id="33458-512">Visualizzare la topologia di rete CAC in uno stile di visualizzazione ad albero.</span><span class="sxs-lookup"><span data-stu-id="33458-512">View CAC network topology in a tree-view style.</span></span>

- <span data-ttu-id="33458-513">Definire i connettori personalizzati per i collegamenti alla topologia di rete CAC (ad esempio, da siti a area geografica, dall'area geografica e da sito a sito).</span><span class="sxs-lookup"><span data-stu-id="33458-513">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

- <span data-ttu-id="33458-514">Visualizzare le informazioni sul sito della topologia di rete CAC, le informazioni sulle aree geografiche e i criteri di larghezza di banda e collegamenti di rete.</span><span class="sxs-lookup"><span data-stu-id="33458-514">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

### <a name="purpose"></a><span data-ttu-id="33458-515">Finalità</span><span class="sxs-lookup"><span data-stu-id="33458-515">Purpose</span></span>

<span data-ttu-id="33458-516">Visualizzare i collegamenti alla topologia di rete Enterprise CAC in un'interfaccia grafica.</span><span class="sxs-lookup"><span data-stu-id="33458-516">View enterprise CAC network topology links in a graphical interface.</span></span>

### <a name="examples"></a><span data-ttu-id="33458-517">Esempi</span><span class="sxs-lookup"><span data-stu-id="33458-517">Examples</span></span>

 <span data-ttu-id="33458-518">**Caricare e visualizzare la topologia di rete CAC da una distribuzione di Skype for Business server 2015 in formato grafico**: gli amministratori di Skype for business server 2015 possono caricare e visualizzare la configurazione della topologia di rete di CAC su qualsiasi computer Skype for business server 2015 utilizzando l'opzione **Download Network Configuration** come mostrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="33458-518">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="33458-519">Lo strumento non riesce a scaricare o visualizzare una configurazione di questo tipo quando viene distribuita in un computer in cui non è presente la connettività all'archivio di configurazione di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-519">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>

![Download della configurazione di rete.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 <span data-ttu-id="33458-521">**Caricare e visualizzare la topologia di rete CAC da un file di registro del server dei criteri di larghezza di banda in formato grafico:** I server dei criteri di larghezza di banda di Skype for Business Server 2015 salvano la topologia di rete CAC come parte del meccanismo di registrazione nel percorso di condivisione file di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-521">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="33458-522">Gli amministratori di Skype for Business Server 2015 possono visualizzare un file di questo tipo in formato grafico utilizzando l'opzione di **configurazione della rete aperta** come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="33458-522">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

![Apertura di un file di registro del server del criterio larghezza di banda.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

<span data-ttu-id="33458-524">Salvare e archiviare la topologia di rete CAC in un formato XML sul disco: gli amministratori di Skype for Business Server 2015 possono salvare il file di configurazione della topologia di rete CAC in formato XML utilizzando l'opzione **Salva una copia di configurazione di rete** , come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="33458-524">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="33458-525">Il file di configurazione salvato può quindi essere utilizzato offline per scopi di visualizzazione grafica.</span><span class="sxs-lookup"><span data-stu-id="33458-525">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

![Salvataggio della configurazione di rete come file XML.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

<span data-ttu-id="33458-527">Salvare e archiviare il diagramma della topologia di rete CAC in formato JPG o BMP: gli amministratori di Skype for Business Server 2015 possono salvare la configurazione della topologia di rete CAC in formato grafico (formati di file JPG e BMP) utilizzando l'opzione **Salva diagramma configurazione di rete come immagine** come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="33458-527">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

![Salvataggio della configurazione di rete come immagine.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <span data-ttu-id="33458-529"><strong>Visualizzare i dati di configurazione della topologia di rete CAC:</strong> Gli amministratori di Skype for Business Server 2015 possono visualizzare i dati relativi alla configurazione della rete, ad esempio aree di rete, siti di rete, profili larghezza di banda e indirizzi IP subnet sito in un formato testuale utilizzando l'opzione Visualizza dati di configurazione della rete come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="33458-529"><strong>View CAC network topology configuration data:</strong>Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

![Visualizzazione dei dati di configurazione di rete.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 <span data-ttu-id="33458-531">**Visualizzare la topologia di rete CAC in uno stile di visualizzazione ad albero:** Gli amministratori di Skype for Business Server 2015 possono visualizzare i dati relativi alla configurazione di rete in uno stile di visualizzazione albero grafico utilizzando il pannello di controllo a sinistra della finestra degli strumenti, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="33458-531">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

![Visualizzazione dei dati di configurazione di rete in una visualizzazione struttura ad albero.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 <span data-ttu-id="33458-533">**Definire i connettori personalizzati per i collegamenti alla topologia di rete CAC (quali collegamenti da sito a area** geografica e da sito a sito): Gli amministratori di Skype for Business Server 2015 possono definire connettori grafici personalizzati per i collegamenti WAN di configurazione di rete di CAC utilizzando l'opzione impostazioni come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="33458-533">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="33458-534">In questo modo è possibile distinguere tra vari tipi di collegamenti di rete di cui è stato effettuato il provisioning nella configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="33458-534">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

![Strumenti](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 <span data-ttu-id="33458-536">**Visualizzare le informazioni sul sito della topologia di rete CAC, informazioni sulle aree e criteri di larghezza di banda provisioning:** Gli amministratori di Skype for Business Server 2015 possono visualizzare le informazioni relative all'area di rete CAC, le informazioni sul sito e le informazioni sul provisioning della larghezza di banda CAC utilizzando le opzioni illustrate di seguito.</span><span class="sxs-lookup"><span data-stu-id="33458-536">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="33458-537">Ad esempio, fare clic su **info** in un'area di rete o in un oggetto sito di rete.</span><span class="sxs-lookup"><span data-stu-id="33458-537">(For example, click **Info** in a network region or network site object.)</span></span>

![Definizione dei connettori personalizzati per la rete.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a><span data-ttu-id="33458-539">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="33458-539">Summary</span></span>

<span data-ttu-id="33458-540">Questo strumento può essere una risorsa importante per gli amministratori di Skype for Business Server 2015 che desiderano visualizzare la topologia di rete CAC per la distribuzione in formato grafico.</span><span class="sxs-lookup"><span data-stu-id="33458-540">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

## <a name="response-group-agent-live"></a><span data-ttu-id="33458-541">Agente di Response Group Live</span><span class="sxs-lookup"><span data-stu-id="33458-541">Response Group Agent Live</span></span>
<span data-ttu-id="33458-542"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="33458-542"><a name="RGAL"> </a></span></span>

<span data-ttu-id="33458-543">L'applicazione Response Group fornisce agli agenti la possibilità di accedere alle informazioni in tempo reale utili utilizzando il servizio Web incorporato.</span><span class="sxs-lookup"><span data-stu-id="33458-543">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="33458-544">Purtroppo, nessuna visualizzazione grafica di questi dati è disponibile all'esterno dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="33458-544">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="33458-545">Lo strumento Response Group Agent Live Resource Kit risolve questo problema fornendo una modalità semplice e grafica per accedere a queste informazioni, migliorate con le informazioni sul software di Skype for business in tempo reale per le comunicazioni, ad esempio la presenza di altri agenti.</span><span class="sxs-lookup"><span data-stu-id="33458-545">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>

### <a name="description"></a><span data-ttu-id="33458-546">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33458-546">Description</span></span>

<span data-ttu-id="33458-547">Response Group Agent Live è un'applicazione di Windows che fornisce funzionalità di accesso e disconnessione e alcune informazioni in tempo reale, ad esempio l'appartenenza a un gruppo e il numero corrente di chiamate, agli agenti di Response Group.</span><span class="sxs-lookup"><span data-stu-id="33458-547">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="33458-548">È destinata a essere una versione avanzata della pagina gruppi di agenti (accessibile da Skype for business.</span><span class="sxs-lookup"><span data-stu-id="33458-548">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>

### <a name="purpose"></a><span data-ttu-id="33458-549">Finalità</span><span class="sxs-lookup"><span data-stu-id="33458-549">Purpose</span></span>

<span data-ttu-id="33458-550">L'applicazione Response Group Accoda le chiamate in arrivo e quindi le instrada ai gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="33458-550">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="33458-551">Per prendere decisioni informate sulle chiamate al servizio, gli agenti possono accedere alle informazioni in tempo reale sui gruppi di agenti, ad esempio gli altri agenti disponibili e il numero di chiamate in attesa in ogni coda.</span><span class="sxs-lookup"><span data-stu-id="33458-551">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="33458-552">Queste informazioni, inizialmente accessibili solo tramite il servizio Response Group, vengono rese disponibili in modo intuitivo dall'agente di Response Group Live.</span><span class="sxs-lookup"><span data-stu-id="33458-552">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

#### <a name="features"></a><span data-ttu-id="33458-553">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="33458-553">Features</span></span>

<span data-ttu-id="33458-554">Lo strumento Response Group Agent Live è basato sul servizio Response Group e su Skype for Business Server 2015 SDK.</span><span class="sxs-lookup"><span data-stu-id="33458-554">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="33458-555">Fornisce agli agenti di Response Group le informazioni e le funzionalità disponibili dal servizio Response Group, ad esempio l'appartenenza ai gruppi, la presenza di altri agenti e il numero di chiamate in attesa.</span><span class="sxs-lookup"><span data-stu-id="33458-555">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="33458-556">Nella figura seguente viene illustrata l'interfaccia principale di Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="33458-556">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

![Strumento di Response Group Agent Live.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

<span data-ttu-id="33458-558">Sono disponibili le tre funzionalità principali seguenti per gli agenti di Response Group Agent Live:</span><span class="sxs-lookup"><span data-stu-id="33458-558">The following three main features are available for agents in Response Group Agent Live:</span></span>

- <span data-ttu-id="33458-559">**Accesso/uscita:** Contrariamente alla pagina gruppi di agenti (accessibile da Skype for Business Server 2015), Response Group Agent Live consente solo agli agenti di accedere o uscire contemporaneamente da tutti i gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="33458-559">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="33458-560">Questa applicazione offre tre modi rapidi per gli agenti di accedere o uscire:</span><span class="sxs-lookup"><span data-stu-id="33458-560">This application provides three quick ways for agents to sign in or out:</span></span>

  - <span data-ttu-id="33458-561">Fare clic sui pulsanti di accesso/uscita (verde e rosso) all'interno dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="33458-561">Click the Sign-in/out (green and red) buttons within the application.</span></span>

  - <span data-ttu-id="33458-562">Fare clic con il pulsante destro del mouse sull'icona del vassoio di sistema e scegliere Accedi o Disconnetti.</span><span class="sxs-lookup"><span data-stu-id="33458-562">Right-click the system tray icon, and select sign in or sign out.</span></span>

  - <span data-ttu-id="33458-563">Utilizzo di tasti di scelta rapida configurabili.</span><span class="sxs-lookup"><span data-stu-id="33458-563">Using configurable keyboard shortcuts.</span></span>

- <span data-ttu-id="33458-564">**Appartenenza ai gruppi:** Quando si seleziona un gruppo di agenti, Response Group Agent Live Visualizza l'elenco degli agenti di questo gruppo nel riquadro destro.</span><span class="sxs-lookup"><span data-stu-id="33458-564">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="33458-565">Se Skype for Business Server 2015 è in esecuzione nello stesso computer in cui si trova questa applicazione, le informazioni sulla presenza e la scheda contatto vengono visualizzate nell'agente Response Group Live.</span><span class="sxs-lookup"><span data-stu-id="33458-565">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="33458-566">Gli agenti possono inviare un messaggio istantaneo o chiamare altri agenti direttamente da qui.</span><span class="sxs-lookup"><span data-stu-id="33458-566">Agents can send an IM or call other agents directly from there.</span></span>

- <span data-ttu-id="33458-567">**Statistiche in tempo reale:** Agente di Response Group Live fornisce statistiche in tempo reale per tutti i gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="33458-567">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="33458-568">La frequenza di aggiornamento è di un minuto.</span><span class="sxs-lookup"><span data-stu-id="33458-568">The update frequency is one minute.</span></span> <span data-ttu-id="33458-569">Quando una chiamata viene risolta da un Response Group, viene aggiunto un indicatore visivo accanto al nome del gruppo con il numero corrente di chiamate in coda.</span><span class="sxs-lookup"><span data-stu-id="33458-569">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="33458-570">La sospensione del puntatore su un gruppo Visualizza anche il tempo di attesa più lungo.</span><span class="sxs-lookup"><span data-stu-id="33458-570">Pausing the pointer over a group also displays the longest waiting time.</span></span>

### <a name="requirements"></a><span data-ttu-id="33458-571">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33458-571">Requirements</span></span>

<span data-ttu-id="33458-572">L'agente Response Group Live richiede .NET Framework 4,0.</span><span class="sxs-lookup"><span data-stu-id="33458-572">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="33458-573">Inoltre, per sfruttare le funzionalità di presenza e scheda contatto, Skype for business deve essere installato localmente (ed essere in esecuzione).</span><span class="sxs-lookup"><span data-stu-id="33458-573">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>

#### <a name="configuration"></a><span data-ttu-id="33458-574">Configurazione</span><span class="sxs-lookup"><span data-stu-id="33458-574">Configuration</span></span>

<span data-ttu-id="33458-575">L'agente di Response Group Live può essere personalizzato per le preferenze individuali utilizzando la finestra di dialogo Opzioni nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="33458-575">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="33458-576">Inoltre, l'amministratore può definire l'indirizzo host predefinito modificando direttamente la proprietà defaultHostAddress del file RGAgentLive.exe.config.</span><span class="sxs-lookup"><span data-stu-id="33458-576">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="33458-577">Nella figura seguente è illustrata la finestra di dialogo Opzioni che gli agenti possono utilizzare per configurare l'indirizzo host e i tasti di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="33458-577">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="33458-578">È possibile accedere a questa finestra di dialogo facendo clic sul pulsante Opzioni nell'angolo in alto a destra dell'interfaccia principale.</span><span class="sxs-lookup"><span data-stu-id="33458-578">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

![La finestra di dialogo Opzioni di Response Group Agent Live.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

<span data-ttu-id="33458-580">Nella configurazione di Response Group Agent Live è possibile personalizzare le tre diverse impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33458-580">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

- <span data-ttu-id="33458-581">Indirizzo host: questo è in genere l'FQDN del pool Web che appartiene al pool di origine dell'agente.</span><span class="sxs-lookup"><span data-stu-id="33458-581">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="33458-582">L'indirizzo esatto del servizio Response Group viene automaticamente derivato in background da queste informazioni (accodando il percorso destro dopo l'host).</span><span class="sxs-lookup"><span data-stu-id="33458-582">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

- <span data-ttu-id="33458-583">Tasti di scelta rapida: i collegamenti esatti per l'accesso/uscita possono essere personalizzati.</span><span class="sxs-lookup"><span data-stu-id="33458-583">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="33458-584">L'unica limitazione è che entrambi i tasti di scelta rapida devono contenere il tasto "Windows logo" (oltre ad almeno un altro tasto).</span><span class="sxs-lookup"><span data-stu-id="33458-584">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>

- <span data-ttu-id="33458-585">Iniziare con Windows: l'applicazione può essere configurata per l'avvio automatico con Windows.</span><span class="sxs-lookup"><span data-stu-id="33458-585">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

### <a name="examples"></a><span data-ttu-id="33458-586">Esempi</span><span class="sxs-lookup"><span data-stu-id="33458-586">Examples</span></span>

<span data-ttu-id="33458-587">Nella figura seguente viene illustrato come chiamare o inviare un messaggio istantaneo a un altro agente facendo clic con il pulsante destro del mouse sul contatto nel riquadro destro.</span><span class="sxs-lookup"><span data-stu-id="33458-587">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

![Effettuare una chiamata o inviare un messaggio istantaneo.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

<span data-ttu-id="33458-589">Nella figura seguente viene illustrato il modo in cui agente di Response Group Live Visualizza il numero corrente di chiamate nella coda e il tempo di attesa più lungo tra tutte le chiamate in arrivo.</span><span class="sxs-lookup"><span data-stu-id="33458-589">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

![Visualizzazione delle informazioni sulla coda.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a><span data-ttu-id="33458-591">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="33458-591">Summary</span></span>

<span data-ttu-id="33458-592">L'accesso rapido e l'accesso, l'appartenenza a gruppi e le statistiche di base in tempo reale sono interessanti funzionalità di agente di Response Group disponibili solo all'esterno dell'applicazione dal servizio Response Group.</span><span class="sxs-lookup"><span data-stu-id="33458-592">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="33458-593">Con lo strumento Response Group Agent Live Resource Kit, gli amministratori di Skype for Business Server 2015 possono fornire ai propri agenti un'applicazione Windows che consenta di eseguire le attività in modo più rapido e grafico.</span><span class="sxs-lookup"><span data-stu-id="33458-593">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

## <a name="sefautil"></a><span data-ttu-id="33458-594">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="33458-594">SEFAUtil</span></span>
<span data-ttu-id="33458-595"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="33458-595"><a name="SEFAUtil"> </a></span></span>

<span data-ttu-id="33458-596">SEFAUtil (Secondary Extension feature Activation) è uno strumento da riga di comando che consente agli amministratori di software di comunicazione di Skype for Business Server 2015 e ai consulenti helpdesk di configurare l'attivazione di suonerie Delegate, l'inoltro di chiamata, lo squillo simultaneo, le impostazioni di chiamata del team e il ritiro delle chiamate di gruppo per conto di un utente Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-596">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="33458-597">Lo strumento consente inoltre agli amministratori di eseguire query sulle impostazioni di routing delle chiamate pubblicate per un utente specifico. Lo strumento SEFAUtil consente all'amministratore di abilitare/disabilitare/modificare l'inoltro delle chiamate o squillare contemporaneamente per conto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="33458-597">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="33458-598">L'amministratore può specificare la destinazione (nel formato di un URI SIP) oppure utilizzare una destinazione che è già stata pubblicata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="33458-598">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="33458-599">Questo strumento consente inoltre agli amministratori di aggiungere o rimuovere i delegati o i membri del gruppo di chiamata del team per conto dell'utente. Questo strumento è basato su Microsoft Unified Communications Managed API (UCMA) 3,0 e richiede che gli amministratori creino un'applicazione attendibile nell'archivio di gestione centrale per SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="33458-599">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>

<span data-ttu-id="33458-600">SEFAUtil (funzione di estensione secondaria) consente agli amministratori e ai consulenti helpdesk di Skype for Business Server 2015 di configurare lo squillo di delegati, l'inoltro di chiamata, lo squillo simultaneo, le impostazioni di chiamata del team e il ritiro delle chiamate di gruppo per conto di un utente di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-600">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="33458-601">Questo strumento consente inoltre agli amministratori di eseguire query sulle impostazioni di routing delle chiamate pubblicate per un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="33458-601">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

### <a name="description"></a><span data-ttu-id="33458-602">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33458-602">Description</span></span>

<span data-ttu-id="33458-603">La versione corrente di SEFAUtil è solo uno strumento da riga di comando. non è disponibile un'interfaccia utente grafica di supporto.</span><span class="sxs-lookup"><span data-stu-id="33458-603">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="33458-604">Questo strumento si basa su Microsoft Unified Communications Managed API (UCMA) 3,0.</span><span class="sxs-lookup"><span data-stu-id="33458-604">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="33458-605">Le funzionalità di questo strumento consentono agli amministratori e agli agenti del supporto tecnico di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33458-605">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

- <span data-ttu-id="33458-606">Visualizzare tutte le impostazioni di routing delle chiamate per un utente (include l'inoltro di chiamata, la delega, lo squillo simultaneo, la chiamata di team e il prelievo delle chiamate di gruppo)</span><span class="sxs-lookup"><span data-stu-id="33458-606">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

- <span data-ttu-id="33458-607">Abilitazione/disabilitazione/modifica dell'impostazione di inoltro di chiamata (include il timer di destinazione e no-answer)</span><span class="sxs-lookup"><span data-stu-id="33458-607">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

- <span data-ttu-id="33458-608">Abilitare/disabilitare/modificare le configurazioni immediate di inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="33458-608">Enable/disable/modify call-forwarding immediate configurations</span></span>

- <span data-ttu-id="33458-609">Abilitazione/disabilitazione/modifica delle impostazioni di delega</span><span class="sxs-lookup"><span data-stu-id="33458-609">Enable/disable/modify delegation settings</span></span>

- <span data-ttu-id="33458-610">Abilitare/disabilitare/modificare le impostazioni del gruppo di chiamata del team</span><span class="sxs-lookup"><span data-stu-id="33458-610">Enable/disable/modify team-call group settings</span></span>

    > [!NOTE]
    > <span data-ttu-id="33458-611">Nuovo strumento di SEFAUtil di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="33458-611">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="33458-612">Abilitazione/disabilitazione/modifica delle impostazioni di squillo simultaneo (include la destinazione)</span><span class="sxs-lookup"><span data-stu-id="33458-612">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>

    > [!NOTE]
    > <span data-ttu-id="33458-613">Nuovo strumento di SEFAUtil di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="33458-613">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="33458-614">Abilitazione/disabilitazione/modifica delle impostazioni di prelievo delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="33458-614">Enable/disable/modify group call pickup settings</span></span>

    > [!CAUTION]
    > <span data-ttu-id="33458-615">Nuovo strumento di SEFAUtil di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="33458-615">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

<span data-ttu-id="33458-616">Questo strumento presenta le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33458-616">This tool has the following limitations:</span></span>

- <span data-ttu-id="33458-617">Supportato solo per gli utenti ospitati in un pool di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="33458-617">Supported only for users homed in a Skype for Business Server pool</span></span>

- <span data-ttu-id="33458-618">La modifica in blocco delle impostazioni di routing delle chiamate per più utenti non è supportata</span><span class="sxs-lookup"><span data-stu-id="33458-618">Bulk-edit of call routing settings for several users is not supported</span></span>

### <a name="output"></a><span data-ttu-id="33458-619">Output</span><span class="sxs-lookup"><span data-stu-id="33458-619">Output</span></span>

<span data-ttu-id="33458-620">La versione corrente di questo strumento fornisce l'output solo nella finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="33458-620">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="33458-621">Per ulteriori informazioni, vedere la sezione Examples più avanti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="33458-621">For details, see the Examples section later in this document.</span></span>

### <a name="purpose"></a><span data-ttu-id="33458-622">Finalità</span><span class="sxs-lookup"><span data-stu-id="33458-622">Purpose</span></span>

<span data-ttu-id="33458-623">Di seguito sono riportati alcuni degli scenari principali in cui è possibile utilizzare questo strumento:</span><span class="sxs-lookup"><span data-stu-id="33458-623">Following are some of the key scenarios where this tool may be used:</span></span>

- <span data-ttu-id="33458-624">Bob è un dirigente ed è stato spostato in Skype for Business Server telefonia.</span><span class="sxs-lookup"><span data-stu-id="33458-624">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="33458-625">Ha una delega per il sistema PBX esistente.</span><span class="sxs-lookup"><span data-stu-id="33458-625">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="33458-626">Come parte dello spostamento in Skype for Business Server 2015, l'amministratore è in grado di configurare il routing di Roberto per riflettere la configurazione della delega preesistente.</span><span class="sxs-lookup"><span data-stu-id="33458-626">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>

- <span data-ttu-id="33458-627">Alice è in viaggio e si rende conto che è in attesa di una chiamata importante da uno dei suoi clienti.</span><span class="sxs-lookup"><span data-stu-id="33458-627">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="33458-628">Tuttavia, si trova in un hotel e non ha accesso a un computer.</span><span class="sxs-lookup"><span data-stu-id="33458-628">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="33458-629">Chiama il supporto tecnico e richiede di inoltrare al proprio numero di cellulare tutte le chiamate effettuate al proprio numero di lavoro.</span><span class="sxs-lookup"><span data-stu-id="33458-629">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="33458-630">Il personale del supporto tecnico è in grado di eseguire la configurazione per suo conto.</span><span class="sxs-lookup"><span data-stu-id="33458-630">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

- <span data-ttu-id="33458-631">Le chiamate di Joe al suo numero di lavoro stanno per passare alla segreteria telefonica mobile ogni volta che è al lavoro; Tuttavia, la maggior parte delle altre posizioni sembra funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="33458-631">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="33458-632">Il tecnico dell'helpdesk è in grado di visualizzare la configurazione di routing di Joe e rileva che Joe ha squillato simultaneamente configurato sul suo cellulare.</span><span class="sxs-lookup"><span data-stu-id="33458-632">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="33458-633">Il tecnico chiede a Joe la copertura per dispositivi mobili nel suo ufficio ed è in grado di determinare che la regola di squillo simultaneo è ciò che sta causando la chiamata per andare alla segreteria telefonica di Joe quando la sua copertura di rete è scadente.</span><span class="sxs-lookup"><span data-stu-id="33458-633">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>

- <span data-ttu-id="33458-634">Mike è un nuovo dipendente di contoso ed entra a far parte di un nuovo team in cui tutti i membri sono configurati per il team-Call, quando viene abilitato per Skype for Business Server 2015, l'amministratore è in grado di impostare le impostazioni del gruppo di chiamate del team per includere tutti i nuovi membri del team, inoltre, l'amministratore aggiunge Mike come membro del gruppo di chiamata del team per</span><span class="sxs-lookup"><span data-stu-id="33458-634">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

- <span data-ttu-id="33458-635">Una pratica del servizio clienti nel reparto risorse umane di Contoso è quella di fornire un servizio personale per tutti i chiamanti dopo la prima chiamata.</span><span class="sxs-lookup"><span data-stu-id="33458-635">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="33458-636">Dato che tutti i membri del dipartimento siedono molto vicini l'uno all'altro, tutti i telefoni che squillano contemporaneamente con il team-Call sono molto sconvolgenti per il team.</span><span class="sxs-lookup"><span data-stu-id="33458-636">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="33458-637">Per fornire il miglior servizio senza interrompere i membri del team, l'amministratore di Skype for Business Server 2015 si avvale della funzionalità di prelievo delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="33458-637">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="33458-638">L'amministratore aggiunge tutti i membri del reparto a un gruppo di prelievo e comunica al reparto il numero del gruppo di prelievo.</span><span class="sxs-lookup"><span data-stu-id="33458-638">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="33458-639">Quando Samantha è assente dalla sua scrivania, Joe si accorge di squillare il telefono e procede a rispondere alla telefonata dalla sua scrivania.</span><span class="sxs-lookup"><span data-stu-id="33458-639">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

### <a name="requirements"></a><span data-ttu-id="33458-640">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33458-640">Requirements</span></span>

<span data-ttu-id="33458-641">Lo strumento SEFAUtil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="33458-641">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="33458-642">UCMA 3,0 deve essere installato nel computer in questione.</span><span class="sxs-lookup"><span data-stu-id="33458-642">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="33458-643">Per eseguire lo strumento, è necessario creare una nuova applicazione attendibile con l'ID dell'applicazione SEFAUtil in tale pool.</span><span class="sxs-lookup"><span data-stu-id="33458-643">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="33458-644">Creazione di una nuova applicazione attendibile per lo strumento SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="33458-644">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="33458-645">Lo strumento SEFAUTil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="33458-645">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="33458-646">Se necessario, l'aggiunta di un pool come nuovo pool di applicazioni attendibili può essere completata tramite Skype for Business Server Management Shell con il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="33458-646">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > <span data-ttu-id="33458-647">UCMA 3,0 deve essere installato in qualsiasi computer che verrà utilizzato per eseguire lo strumento SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="33458-647">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

2. <span data-ttu-id="33458-648">È necessario definire un'applicazione attendibile nella topologia per lo strumento SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="33458-648">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="33458-649">Per definire SEFAUtil come nuova applicazione attendibile, utilizzare Skype for Business Server Management Shell ed eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="33458-649">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="33458-650">Se necessario, è possibile utilizzare una porta diversa.</span><span class="sxs-lookup"><span data-stu-id="33458-650">A different port can be used if needed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="33458-651">FQDN pool: il nome di dominio completo del server o del pool che ospiterà l'applicazione SEFAUtil (in genere un server front end di Skype for business > o pool).</span><span class="sxs-lookup"><span data-stu-id="33458-651">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server     > or pool).</span></span>
    > <span data-ttu-id="33458-652">FQDN del registrar del pool: il nome di dominio completo del server o del pool Front End di Skype for business associato al pool di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="33458-652">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="33458-653">Sito pool: l'ID del sito in cui è ospitato il pool.</span><span class="sxs-lookup"><span data-stu-id="33458-653">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

3. <span data-ttu-id="33458-654">Le modifiche alla topologia devono essere attivate.</span><span class="sxs-lookup"><span data-stu-id="33458-654">The topology changes need to be enabled.</span></span> <span data-ttu-id="33458-655">L'abilitazione delle modifiche alla topologia può essere eseguita tramite Skype for Business Server Management Shell eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="33458-655">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span>

   ```powershell
   Enable-CsToplogy
   ```

4. <span data-ttu-id="33458-656">Se necessario, installare gli strumenti di Skype for Business Server 2015 Resource Kit nel server che verrà utilizzato per eseguire lo strumento SEFAUtil (il server deve far parte di un pool di applicazioni attendibili).</span><span class="sxs-lookup"><span data-stu-id="33458-656">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5. <span data-ttu-id="33458-657">Verificare che SEFAUtil sia in esecuzione correttamente.</span><span class="sxs-lookup"><span data-stu-id="33458-657">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="33458-658">A tale scopo, eseguire lo strumento da un prompt dei comandi di Windows con privilegi di amministratore per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="33458-658">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="33458-659">Per impostazione predefinita, lo strumento sarà disponibile in: ". ..\Program Skype for Business Server 2015 \ reskit".</span><span class="sxs-lookup"><span data-stu-id="33458-659">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="33458-660">Per visualizzare le impostazioni di inoltro di chiamata di un utente, utilizzare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="33458-660">To display the call forwarding settings of a user, use the following command:</span></span>

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    <span data-ttu-id="33458-661">Le impostazioni di inoltro di chiamata dell'utente devono essere visualizzate.</span><span class="sxs-lookup"><span data-stu-id="33458-661">The call forwarding settings of the user should be displayed.</span></span>

#### <a name="group-call-pickup"></a><span data-ttu-id="33458-662">Risposta alle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="33458-662">Group Call Pickup</span></span>

<span data-ttu-id="33458-663">Il prelievo delle chiamate di gruppo richiede una configurazione aggiuntiva in Skype for Business Server 2015 affinché la funzionalità sia abilitata completamente.</span><span class="sxs-lookup"><span data-stu-id="33458-663">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="33458-664">Prima di assegnare i gruppi di prelievo agli utenti, fare riferimento alla documentazione del prodotto di prelievo delle chiamate di gruppo per i passaggi di pianificazione e distribuzione di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="33458-664">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

### <a name="examples"></a><span data-ttu-id="33458-665">Esempi</span><span class="sxs-lookup"><span data-stu-id="33458-665">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="33458-666">Visualizzazione delle impostazioni di gestione delle chiamate correnti</span><span class="sxs-lookup"><span data-stu-id="33458-666">Display Current Call Handling Settings</span></span>

<span data-ttu-id="33458-667">Il comando seguente consente di visualizzare la gestione delle chiamate per l'utente.</span><span class="sxs-lookup"><span data-stu-id="33458-667">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> <span data-ttu-id="33458-668">In questo esempio viene utilizzata l'opzione **/Server** per specificare il server Skype for business a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="33458-668">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>

 <span data-ttu-id="33458-669">**Output**</span><span class="sxs-lookup"><span data-stu-id="33458-669">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="33458-670">Impostare la destinazione di chiamata forward/no answer</span><span class="sxs-lookup"><span data-stu-id="33458-670">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="33458-671">In questo esempio viene impostata la destinazione di chiamata forward/No Answer e il ritardo dell'anello.</span><span class="sxs-lookup"><span data-stu-id="33458-671">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="33458-672">In questo caso, l'opzione/server non è disponibile. SEFAUtil tenta di individuare l'individuazione automatica di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-672">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+14255550126@contoso.com;user=phone
```

 <span data-ttu-id="33458-673">**Output**</span><span class="sxs-lookup"><span data-stu-id="33458-673">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="33458-674">Abilitazione immediata dell'inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="33458-674">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="33458-675">In questo esempio viene immediatamente abilitato l'inoltro di chiamata a un altro utente.</span><span class="sxs-lookup"><span data-stu-id="33458-675">This example immediately enables call-forwarding to another user.</span></span>

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="33458-676">**Output**</span><span class="sxs-lookup"><span data-stu-id="33458-676">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="33458-677">Disabilitare immediatamente l'inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="33458-677">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="33458-678">In questo esempio viene disabilitato immediatamente l'inoltro di chiamata.</span><span class="sxs-lookup"><span data-stu-id="33458-678">This example immediately disables call forwarding.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com /disablefwdimmediate
```

 <span data-ttu-id="33458-679">**Output**</span><span class="sxs-lookup"><span data-stu-id="33458-679">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="33458-680">Aggiungere un utente come delegato e impostare lo squillo simultaneo dei delegati</span><span class="sxs-lookup"><span data-stu-id="33458-680">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="33458-681">In questo esempio viene aggiunto un utente come delegato e viene impostato lo squillo simultaneo dei delegati.</span><span class="sxs-lookup"><span data-stu-id="33458-681">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="33458-682">**Output**</span><span class="sxs-lookup"><span data-stu-id="33458-682">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="33458-683">Modificare la regola di chiamata simultanea dei delegati</span><span class="sxs-lookup"><span data-stu-id="33458-683">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="33458-684">In questo esempio viene modificata la regola di chiamata simultanea configurata nell'esempio precedente alla regola di chiamata ritardata.</span><span class="sxs-lookup"><span data-stu-id="33458-684">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="33458-685">**Output**</span><span class="sxs-lookup"><span data-stu-id="33458-685">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="33458-686">Rimuovere il delegato</span><span class="sxs-lookup"><span data-stu-id="33458-686">Remove the Delegate</span></span>

<span data-ttu-id="33458-687">In questo esempio viene rimosso il delegato.</span><span class="sxs-lookup"><span data-stu-id="33458-687">This example removes the delegate.</span></span>

> [!NOTE]
> <span data-ttu-id="33458-688">Quando l'ultimo delegato viene rimosso, il delegare squillo viene disabilitato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="33458-688">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="33458-689">**Output**</span><span class="sxs-lookup"><span data-stu-id="33458-689">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="33458-690">Aggiungere un delegato e impostare l'Call-Forward per la regola delegati</span><span class="sxs-lookup"><span data-stu-id="33458-690">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="33458-691">In questo esempio viene aggiunto un delegato e viene impostata la regola dei delegati di chiamata inoltrata.</span><span class="sxs-lookup"><span data-stu-id="33458-691">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="33458-692">**Output**</span><span class="sxs-lookup"><span data-stu-id="33458-692">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="33458-693">Abilitare lo squillo simultaneo e impostare un numero di destinazione</span><span class="sxs-lookup"><span data-stu-id="33458-693">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="33458-694">In questo esempio viene abilitato lo squillo simultaneo e viene impostato un numero di destinazione di squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="33458-694">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="33458-695">Per modificare il numero di destinazione di squillo simultaneo di un utente che ha già attivato lo squillo simultaneo, mantenere il comando con l'opzione/enablesimulring, altrimenti il numero di destinazione non verrà modificato.</span><span class="sxs-lookup"><span data-stu-id="33458-695">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>

 <span data-ttu-id="33458-696">**Output**</span><span class="sxs-lookup"><span data-stu-id="33458-696">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="33458-697">Disabilitare lo squillo simultaneo</span><span class="sxs-lookup"><span data-stu-id="33458-697">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="33458-698">In questo esempio viene disabilitato lo squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="33458-698">This example disables simultaneous ringing.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="33458-699">**Output**</span><span class="sxs-lookup"><span data-stu-id="33458-699">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="33458-700">Aggiungere un membro del team per Team-Call e configurare lo squillo simultaneo nel gruppo dei membri Team-Call</span><span class="sxs-lookup"><span data-stu-id="33458-700">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="33458-701">In questo esempio viene aggiunto un membro del team al gruppo di chiamata del team di un utente e viene abilitato lo squillo simultaneo al gruppo di chiamata del team.</span><span class="sxs-lookup"><span data-stu-id="33458-701">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="33458-702">L'aggiunta di un membro al gruppo di chiamata del team di un utente commuterà automaticamente la settigs di suoneria simultanea degli utenti per simulring il gruppo di chiamata del team.</span><span class="sxs-lookup"><span data-stu-id="33458-702">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>

 <span data-ttu-id="33458-703">**Output**</span><span class="sxs-lookup"><span data-stu-id="33458-703">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="33458-704">Rimuovere un membro dal gruppo Team-Call</span><span class="sxs-lookup"><span data-stu-id="33458-704">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="33458-705">In questo esempio viene rimosso un membro del team del gruppo di chiamata del team di un utente.</span><span class="sxs-lookup"><span data-stu-id="33458-705">This example removes a team member of the team-call group of a user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="33458-706">Se il membro che si sta rimuovendo è l'unico membro del gruppo di chiamata del team, lo squillo simultaneo al gruppo di chiamata del team verrà disabilitato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="33458-706">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>

 <span data-ttu-id="33458-707">**Output**</span><span class="sxs-lookup"><span data-stu-id="33458-707">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="33458-708">Impostare l'anello ritardato sul gruppo Team-Call</span><span class="sxs-lookup"><span data-stu-id="33458-708">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="33458-709">In questo esempio viene modificato l'anello ritardato nell'impostazione di tempo del gruppo di chiamata del team.</span><span class="sxs-lookup"><span data-stu-id="33458-709">This example changes the delayed ring to the team-call group time setting.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="33458-710">**Output**</span><span class="sxs-lookup"><span data-stu-id="33458-710">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="33458-711">Abilitare Team-Call</span><span class="sxs-lookup"><span data-stu-id="33458-711">Enable Team-Call</span></span>

<span data-ttu-id="33458-712">In questo esempio viene abilitata la chiamata di team per un utente specificato.</span><span class="sxs-lookup"><span data-stu-id="33458-712">This example enables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="33458-713">Se il gruppo di chiamata del team dell'utente non dispone di membri, la chiamata del team non verrà abilitata.</span><span class="sxs-lookup"><span data-stu-id="33458-713">If the team-call group of the user has no members, team-call won't be enabled.</span></span>

 <span data-ttu-id="33458-714">**Output**</span><span class="sxs-lookup"><span data-stu-id="33458-714">**Output**</span></span>

#### <a name="disable-team-call"></a><span data-ttu-id="33458-715">Disattiva Team-Call</span><span class="sxs-lookup"><span data-stu-id="33458-715">Disable Team-Call</span></span>

<span data-ttu-id="33458-716">In questo esempio viene disabilitata la chiamata del team per un utente specificato.</span><span class="sxs-lookup"><span data-stu-id="33458-716">This example disables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="33458-717">**Output**</span><span class="sxs-lookup"><span data-stu-id="33458-717">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="33458-718">Attivazione del prelievo delle chiamate di gruppo e assegnazione di un gruppo di prelievo a un utente</span><span class="sxs-lookup"><span data-stu-id="33458-718">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="33458-719">In questo esempio viene assegnato un gruppo di prelievo a un utente e viene abilitato il prelievo delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="33458-719">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="33458-720">**Output**</span><span class="sxs-lookup"><span data-stu-id="33458-720">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="33458-721">Disattiva prelievo delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="33458-721">Disable Group Call Pickup</span></span>

<span data-ttu-id="33458-722">In questo esempio viene disabilitato il prelievo delle chiamate di gruppo per un utente specificato.</span><span class="sxs-lookup"><span data-stu-id="33458-722">This example disables Group Call Pickup for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="33458-723">Quando si disattiva il prelievo delle chiamate di gruppo per un utente, il numero del gruppo assegnato all'utente non viene mantenuto.</span><span class="sxs-lookup"><span data-stu-id="33458-723">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="33458-724">Se successivamente si desidera riabilitare il prelievo delle chiamate di gruppo per tale utente, è necessario assegnare di nuovo il numero di gruppo con l'opzione/enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="33458-724">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="33458-725">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="33458-725">SYSPrep.ps1</span></span>
<span data-ttu-id="33458-726"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="33458-726"><a name="SYSPrep"> </a></span></span>

### <a name="description"></a><span data-ttu-id="33458-727">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33458-727">Description</span></span>

<span data-ttu-id="33458-728">SYSPrep.ps1 è uno script di Windows PowerShell che installerà i prerequisiti Skype for Business Server 2015 seguenti nel computer del sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="33458-728">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>

- <span data-ttu-id="33458-729">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="33458-729">Microsoft .Net Framework 4.5</span></span>

- <span data-ttu-id="33458-730">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="33458-730">Microsoft SQL Server Express</span></span>

- <span data-ttu-id="33458-731">Windows PowerShell versione 3,0</span><span class="sxs-lookup"><span data-stu-id="33458-731">Windows Powershell version 3.0</span></span>

- <span data-ttu-id="33458-732">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="33458-732">Visual C++ 2010 Redistributable</span></span>

- <span data-ttu-id="33458-733">Aggiornamenti di Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="33458-733">Internet Information Server Updates</span></span>

- <span data-ttu-id="33458-734">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="33458-734">Windows Identity Foundation</span></span>

- <span data-ttu-id="33458-735">File di base di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="33458-735">Skype for Business Server 2015 Core files</span></span>

  <span data-ttu-id="33458-736">Sebbene il nome dello script sia analogo a quello dello strumento di preparazione del sistema per i sistemi operativi Microsoft Windows, sono diversi.</span><span class="sxs-lookup"><span data-stu-id="33458-736">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="33458-737">Lo script installerà solo i prerequisiti necessari per Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-737">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="33458-738">Dopo aver installato i prerequisiti, lo strumento SYSPrep di Windows può quindi essere utilizzato per creare un'immagine del server.</span><span class="sxs-lookup"><span data-stu-id="33458-738">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

### <a name="requirements"></a><span data-ttu-id="33458-739">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33458-739">Requirements</span></span>

<span data-ttu-id="33458-740">Prima di eseguire lo script SYSPrep.ps1, è necessario copiare i file prerequisiti in una cartella locale nel computer del sistema operativo Windows Server 2008 (ad esempio, **D:\setup)**.</span><span class="sxs-lookup"><span data-stu-id="33458-740">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="33458-741">Questa cartella deve includere anche una copia dei file di Skype for Business Server 2015, in particolare **Setup.exe.**</span><span class="sxs-lookup"><span data-stu-id="33458-741">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="33458-742">È possibile scaricare i file prerequisiti dalle seguenti posizioni:</span><span class="sxs-lookup"><span data-stu-id="33458-742">The prerequisite files can be downloaded from the following locations:</span></span>


| <span data-ttu-id="33458-743">**Prerequisito**</span><span class="sxs-lookup"><span data-stu-id="33458-743">**Prerequisite**</span></span>                                | <span data-ttu-id="33458-744">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="33458-744">**Location**</span></span>                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| <span data-ttu-id="33458-745">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="33458-745">Microsoft .Net Framework 4.5</span></span>  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| <span data-ttu-id="33458-746">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="33458-746">Microsoft SQL Server Express 2008 R2</span></span>  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| <span data-ttu-id="33458-747">Windows PowerShell versione 3,0</span><span class="sxs-lookup"><span data-stu-id="33458-747">Windows Powershell version 3.0</span></span>  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| <span data-ttu-id="33458-748">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="33458-748">Visual C++ 2010 Redistributable</span></span>  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| <span data-ttu-id="33458-749">Aggiornamenti di Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="33458-749">Internet Information Server Updates</span></span>  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| <span data-ttu-id="33458-750">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="33458-750">Windows Identity Foundation</span></span>  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| <span data-ttu-id="33458-751">Skype for Business Server 2015 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="33458-751">Skype for Business Server 2015 Setup.exe</span></span>  <br/> | <span data-ttu-id="33458-752">Copia da supporto di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="33458-752">Copy from Skype for Business Server 2015 media</span></span>  <br/>                   |

### <a name="parameter"></a><span data-ttu-id="33458-753">Parametro</span><span class="sxs-lookup"><span data-stu-id="33458-753">Parameter</span></span>

<span data-ttu-id="33458-754">Il parametro **-SetupFolder** accetta come argomento il percorso della directory dei file prerequisiti</span><span class="sxs-lookup"><span data-stu-id="33458-754">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

### <a name="examples"></a><span data-ttu-id="33458-755">Esempi</span><span class="sxs-lookup"><span data-stu-id="33458-755">Examples</span></span>

<span data-ttu-id="33458-756">Per eseguire lo script SYSPrep.ps1 e installare i prerequisiti di Skype for Business Server 2015, eseguire il comando seguente da un prompt dei comandi con privilegi elevati:</span><span class="sxs-lookup"><span data-stu-id="33458-756">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="33458-757">Migrazione degli annunci di numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="33458-757">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="33458-758"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="33458-758"><a name="UNAM"> </a></span></span>

<span data-ttu-id="33458-759">Lo strumento di migrazione annunci numeri non assegnati consente a un amministratore di Skype for Business Server 2015 di spostare la configurazione dei numeri non assegnati serviti dall'applicazione annuncio da un server o pool Skype for business di origine a un server o a un pool di Skype for business di destinazione.</span><span class="sxs-lookup"><span data-stu-id="33458-759">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>

### <a name="description"></a><span data-ttu-id="33458-760">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33458-760">Description</span></span>

<span data-ttu-id="33458-761">Lo strumento di migrazione annunci numeri non assegnati è uno script di Windows PowerShell che consente di spostare la configurazione dei numeri non assegnati serviti dall'applicazione Annuncio di un server o di un pool di origine in un altro server o pool.</span><span class="sxs-lookup"><span data-stu-id="33458-761">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="33458-762">Quando viene eseguito, lo script di migrazione degli annunci dei numeri non assegnati eseguirà le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33458-762">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1. <span data-ttu-id="33458-763">Spostare tutti i file audio utilizzati dagli annunci di numeri non assegnati dell'applicazione Annuncio ospitati nel server o nel pool di origine nell'archivio file del server o del pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="33458-763">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="33458-764">I file audio vengono rimossi dal pool di origine dopo essere stati copiati nel pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="33458-764">The audio files are removed from the source pool once they're copied to the destination pool.</span></span>

2. <span data-ttu-id="33458-765">Spostare tutti gli annunci di numeri non assegnati configurati per l'applicazione annuncio ospitata nel server o nel pool di origine nel server o nel pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="33458-765">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3. <span data-ttu-id="33458-766">Riassegnare tutti gli intervalli di numeri non assegnati serviti dall'applicazione annuncio ospitata nel server o nel pool di origine al server o al pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="33458-766">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="33458-767">Dopo aver eseguito correttamente lo script, tutti gli intervalli di numeri non assegnati che sono stati serviti dall'applicazione annuncio ospitata nel server o nel pool di origine verranno ora serviti con la stessa configurazione dal server o dal pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="33458-767">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

### <a name="output"></a><span data-ttu-id="33458-768">Output</span><span class="sxs-lookup"><span data-stu-id="33458-768">Output</span></span>

<span data-ttu-id="33458-769">Lo script **Move-CsAnnouncementConfiguration** indica nella finestra della shell di gestione di Skype for Business Server da cui è stato eseguito l'esito positivo o negativo dell'operazione di migrazione.</span><span class="sxs-lookup"><span data-stu-id="33458-769">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="33458-770">Se l'esecuzione dell'operazione viene interrotta da un errore, gli intervalli di numeri non assegnati che sono stati spostati nella destinazione rimarranno nella destinazione in un modulo operativo e il resto degli intervalli di numeri non assegnati di cui eseguire la migrazione rimarrà nell'origine anche in un modulo operativo.</span><span class="sxs-lookup"><span data-stu-id="33458-770">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="33458-771">Per eseguire la migrazione completa del resto della configurazione, rieseguire lo script dopo l'indirizzamento dell'errore.</span><span class="sxs-lookup"><span data-stu-id="33458-771">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

### <a name="purpose"></a><span data-ttu-id="33458-772">Finalità</span><span class="sxs-lookup"><span data-stu-id="33458-772">Purpose</span></span>

<span data-ttu-id="33458-773">Lo script di migrazione degli annunci dei numeri non assegnati può essere utilizzato nei tre scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="33458-773">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

- <span data-ttu-id="33458-774">**Migrazione delle impostazioni di configurazione a una nuova versione di Skype for Business Server:** Contoso è in fase di migrazione a Skype for Business Server 2015 e come parte del processo di migrazione, l'amministratore di Skype for Business Server desidera spostare la configurazione dei numeri non assegnati serviti dall'applicazione annuncio dalla distribuzione di Lync Server 2013 alla nuova distribuzione di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-774">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="33458-775">Per spostare le impostazioni di configurazione, l'amministratore di Skype for Business Server utilizza lo strumento di migrazione annunci numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="33458-775">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

- <span data-ttu-id="33458-776">**Rollback di una distribuzione da Skype for Business Server 2015 a Lync server 2013:** A causa di fattori imprevisti, Contoso deve eseguire il rollback della migrazione alla nuova distribuzione di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33458-776">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="33458-777">Per ridurre al minimo le interruzioni del servizio, l'amministratore di Skype for Business Server utilizza lo strumento di migrazione degli annunci dei numeri non assegnati per eseguire il rollback della configurazione dalla distribuzione di Skype for Business Server 2015 alla distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="33458-777">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>

- <span data-ttu-id="33458-778">**Spostamento dei dati tra le distribuzioni:** Contoso è in fase di sostituzione di tutti i server di un pool con server più recenti.</span><span class="sxs-lookup"><span data-stu-id="33458-778">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="33458-779">La strategia è quella di distribuire un nuovo pool di Skype for Business Server 2015, spostare tutti i dati dal vecchio al nuovo pool e quindi deprecare il pool precedente.</span><span class="sxs-lookup"><span data-stu-id="33458-779">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="33458-780">Dopo la distribuzione del nuovo pool, lo strumento di migrazione annunci di numeri non assegnati viene utilizzato per spostare la configurazione dal pool precedente a quello nuovo.</span><span class="sxs-lookup"><span data-stu-id="33458-780">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

#### <a name="requirements"></a><span data-ttu-id="33458-781">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33458-781">Requirements</span></span>

<span data-ttu-id="33458-782">Di seguito sono riportati i requisiti principali necessari per eseguire correttamente lo strumento:</span><span class="sxs-lookup"><span data-stu-id="33458-782">The following are the main requirements needed to successfully run the tool:</span></span>

1. <span data-ttu-id="33458-783">Lo script deve essere eseguito da un computer in cui è installato Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="33458-783">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>

2. <span data-ttu-id="33458-784">L'applicazione annuncio deve essere distribuita correttamente nei pool e nei server Skype for business di origine e di destinazione.</span><span class="sxs-lookup"><span data-stu-id="33458-784">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>

#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="33458-785">Script Move-CsAnnouncementConfiguration</span><span class="sxs-lookup"><span data-stu-id="33458-785">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="33458-786">Lo script Move-CsAnnouncementConfiguration richiede i due parametri descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="33458-786">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

![Parametri Move-CsAnnouncementConfiguration.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a><span data-ttu-id="33458-788">Esempi</span><span class="sxs-lookup"><span data-stu-id="33458-788">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="33458-789">Spostamento della configurazione degli annunci dei numeri non assegnati da un pool di Lync Server 2013 a un pool di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="33458-789">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="33458-790">In questo esempio vengono spostati gli annunci dei numeri non assegnati dal pool di origine (Lync Server 2013) al pool di destinazione (Skype for Business Server 2015).</span><span class="sxs-lookup"><span data-stu-id="33458-790">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="33458-791">Spostamento della configurazione degli annunci dei numeri non assegnati da un pool di Skype for Business Server 2015 a un pool di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33458-791">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="33458-792">In questo esempio vengono spostati gli annunci dei numeri non assegnati dal pool di origine (Skype for Business Server 2015) al pool di destinazione (Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="33458-792">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="33458-793">Dati Web conf</span><span class="sxs-lookup"><span data-stu-id="33458-793">Web Conf Data</span></span>
<span data-ttu-id="33458-794"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="33458-794"><a name="WebConfData"> </a></span></span>

<span data-ttu-id="33458-795">Lo strumento di dati Web conf consente a un amministratore del software di comunicazione di Skype for Business Server 2015 di avere un maggiore controllo sui dati associati alle conferenze Web di un organizzatore.</span><span class="sxs-lookup"><span data-stu-id="33458-795">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="33458-796">Gli scenari includono la possibilità di eliminare i dati di una riunione di un utente specifico in base a criteri timestamp.</span><span class="sxs-lookup"><span data-stu-id="33458-796">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>

### <a name="description"></a><span data-ttu-id="33458-797">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33458-797">Description</span></span>

<span data-ttu-id="33458-798">Questo strumento consente all'amministratore di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33458-798">This tool allows the administrator to perform the following operations:</span></span>

1. <span data-ttu-id="33458-799">Individuare tutti i dati di Web Conferencing associati a un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="33458-799">Find all Web conferencing data associated with a single user.</span></span>

2. <span data-ttu-id="33458-800">Eliminare tutti i dati di Web Conferencing associati a un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="33458-800">Delete all Web conferencing data associated with a single user.</span></span>

3. <span data-ttu-id="33458-801">Eliminare tutti i dati di Web Conferencing associati a un singolo utente antecedente a una determinata data.</span><span class="sxs-lookup"><span data-stu-id="33458-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4. <span data-ttu-id="33458-802">Spostare tutti i dati di Web Conferencing associati a un singolo utente quando l'utente viene spostato da un pool a un altro.</span><span class="sxs-lookup"><span data-stu-id="33458-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

    > [!NOTE]
    > <span data-ttu-id="33458-803">Gli strumenti del Resource Kit per Lync Server 2010 supportano lo spostamento di tutti i dati di Web Conferencing associati a un singolo utente quando l'utente viene spostato da un pool a un altro.</span><span class="sxs-lookup"><span data-stu-id="33458-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="33458-804">Questa funzionalità è ora obsoleta da questo strumento a favore del parametro **MoveConferenceData** .</span><span class="sxs-lookup"><span data-stu-id="33458-804">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="33458-805">Per informazioni dettagliate su questo parametro, vedere il cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="33458-805">For details about this parameter, see the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="33458-806">Lo strumento consente di eliminare i dati delle riunioni solo per le riunioni inattive.</span><span class="sxs-lookup"><span data-stu-id="33458-806">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="33458-807">Le riunioni attive (o le riunioni in sessioni) non possono essere eliminate.</span><span class="sxs-lookup"><span data-stu-id="33458-807">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="33458-808">Questo strumento deve essere eseguito da un computer che si trova nello stesso pool dell'utente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="33458-808">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="33458-809">L'utente i cui dati del contenuto della riunione vengono gestiti da questo strumento deve essere ospitato nello stesso pool di utenti.</span><span class="sxs-lookup"><span data-stu-id="33458-809">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

### <a name="output"></a><span data-ttu-id="33458-810">Output</span><span class="sxs-lookup"><span data-stu-id="33458-810">Output</span></span>

<span data-ttu-id="33458-811">Questo strumento restituisce i risultati di ciascuna delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33458-811">This tool outputs the results of each of the operations:</span></span>

- <span data-ttu-id="33458-812">Se viene eseguita una query, lo strumento restituisce l'elenco di tutte le cartelle di dati riunione inattive che dispongono di tale utente come organizzatore.</span><span class="sxs-lookup"><span data-stu-id="33458-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

- <span data-ttu-id="33458-813">Se viene eseguita un'operazione di eliminazione, lo strumento restituisce l'elenco di tutte le cartelle di dati riunione i cui dati verranno eliminati.</span><span class="sxs-lookup"><span data-stu-id="33458-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

### <a name="requirements"></a><span data-ttu-id="33458-814">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33458-814">Requirements</span></span>

<span data-ttu-id="33458-815">Lo strumento deve essere eseguito nello stesso pool in cui è attualmente ospitato l'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="33458-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="33458-816">È necessario eseguire lo strumento utilizzando i privilegi di amministratore con accesso all'archivio file di contenuto.</span><span class="sxs-lookup"><span data-stu-id="33458-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

### <a name="examples"></a><span data-ttu-id="33458-817">Esempi</span><span class="sxs-lookup"><span data-stu-id="33458-817">Examples</span></span>

<span data-ttu-id="33458-818">Nella tabella seguente vengono descritti i parametri, alcuni dei quali sono utilizzati negli esempi.</span><span class="sxs-lookup"><span data-stu-id="33458-818">The following table describes the parameters, some of which are used in the examples.</span></span>

![Parametri degli strumenti di dati Web conf.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="33458-820">Nell'esempio precedente viene illustrato il funzionamento di un comando di query.</span><span class="sxs-lookup"><span data-stu-id="33458-820">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="33458-821">L'output di un comando di questo tipo è un elenco di tutte le cartelle del contenuto delle riunioni che potrebbero essere intaccate da questo strumento.</span><span class="sxs-lookup"><span data-stu-id="33458-821">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="33458-822">Il precedente è un esempio di un comando Delete.</span><span class="sxs-lookup"><span data-stu-id="33458-822">The preceding is an example of a delete command.</span></span> <span data-ttu-id="33458-823">Il comando Delete rimuoverà tutte le cartelle riunione inattive dall'utente.</span><span class="sxs-lookup"><span data-stu-id="33458-823">The delete command will remove all inactive meeting folders from this user.</span></span>

### <a name="summary"></a><span data-ttu-id="33458-824">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="33458-824">Summary</span></span>

<span data-ttu-id="33458-825">Questo strumento può essere una risorsa importante per gli amministratori che hanno bisogno di un controllo più preciso sui dati delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="33458-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>


