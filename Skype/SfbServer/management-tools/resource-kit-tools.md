---
title: Documentazione degli strumenti del Resource Kit di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: Questo argomento descrive gli strumenti del Resource Kit di Skype for Business Server 2015, incluso lo scopo di ogni strumento ed esempi di utilizzo. Il Resource Kit di Skype for Business Server 2015 consente di semplificare le attività di routine per gli amministratori IT che distribuiscono e gestiscono Skype for Business Server 2015. Ad esempio, lo strumento di dati Web conf può essere usato per controllare facilmente i dati caricati dagli utenti durante una riunione online. Lo strumento SEFAUtil può essere usato per configurare l'inoltro di chiamata e la risposta dei delegati per gli utenti. Consigliamo agli amministratori IT di usare questi strumenti per gestire in modo più efficace Skype for Business Server 2015.
ms.openlocfilehash: 1a0b787f8cd82291d408e3e3ad30e58e0b8a3627
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888885"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="3a522-107">Documentazione degli strumenti del Resource Kit di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3a522-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>

<span data-ttu-id="3a522-108">Questo argomento descrive gli strumenti del Resource Kit di Skype for Business Server 2015, incluso lo scopo di ogni strumento ed esempi di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="3a522-108">This topic describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="3a522-109">Il Resource Kit di Skype for Business Server 2015 consente di semplificare le attività di routine per gli amministratori IT che distribuiscono e gestiscono Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="3a522-110">Ad esempio, lo strumento di **dati Web conf** può essere usato per controllare facilmente i dati caricati dagli utenti durante una riunione online.</span><span class="sxs-lookup"><span data-stu-id="3a522-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="3a522-111">Lo strumento **SEFAUtil** può essere usato per configurare l'inoltro di chiamata e la risposta dei delegati per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="3a522-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="3a522-112">Consigliamo agli amministratori IT di usare questi strumenti per gestire in modo più efficace Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="3a522-113">Installazione degli strumenti del Resource Kit</span><span class="sxs-lookup"><span data-stu-id="3a522-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="3a522-114">Per installare il Resource Kit di Skype for Business Server 2015, scaricare [OCSReskit. msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) dall'area download.</span><span class="sxs-lookup"><span data-stu-id="3a522-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) from the Download Center.</span></span>

<span data-ttu-id="3a522-115">Eseguire **OCSResKit. msi** per eseguire un'installazione semplice.</span><span class="sxs-lookup"><span data-stu-id="3a522-115">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="3a522-116">Il file con estensione msi installa tutti gli strumenti disponibili nel percorso seguente: **% Program Files%\Skype for Business Server 2015 \ reskit**.</span><span class="sxs-lookup"><span data-stu-id="3a522-116">The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**.</span></span> <span data-ttu-id="3a522-117">Gli strumenti che sono eseguibili indipendenti si trovano in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="3a522-117">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="3a522-118">Gli strumenti che hanno anche file di supporto sono presenti nelle sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="3a522-118">Tools that also have supporting files are in their own subfolders.</span></span>

## <a name="supported-environments"></a><span data-ttu-id="3a522-119">Ambienti supportati</span><span class="sxs-lookup"><span data-stu-id="3a522-119">Supported Environments</span></span>

<span data-ttu-id="3a522-120">Il Resource Kit di Skype for Business Server 2015 deve essere installato in un server che soddisfi le specifiche richieste per Skype for Business Server 2015, in genere uno usato per eseguire Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="3a522-121">Panoramica degli strumenti di Resource Kit</span><span class="sxs-lookup"><span data-stu-id="3a522-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="3a522-122">Di seguito è riportato un elenco degli strumenti forniti in Skype for Business Server 2015 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="3a522-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="3a522-123">Una descrizione di ogni strumento, inclusi i requisiti e l'utilizzo di esempio, è illustrata nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="3a522-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>

- [<span data-ttu-id="3a522-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="3a522-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)

- [<span data-ttu-id="3a522-125">Monitoraggio del servizio criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="3a522-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)

- [<span data-ttu-id="3a522-126">Analizzatore dell'utilizzo della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="3a522-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)

- [<span data-ttu-id="3a522-127">Chiama Parkometer</span><span class="sxs-lookup"><span data-stu-id="3a522-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)

- [<span data-ttu-id="3a522-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="3a522-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)

- [<span data-ttu-id="3a522-129">Importare i dati del servizio di archiviazione</span><span class="sxs-lookup"><span data-stu-id="3a522-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)

- [<span data-ttu-id="3a522-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="3a522-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)

- [<span data-ttu-id="3a522-131">Console utente di ricerca</span><span class="sxs-lookup"><span data-stu-id="3a522-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)

- [<span data-ttu-id="3a522-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="3a522-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)

- [<span data-ttu-id="3a522-133">Visualizzatore Configurazione di rete</span><span class="sxs-lookup"><span data-stu-id="3a522-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)

- [<span data-ttu-id="3a522-134">Agente di Response Group Live</span><span class="sxs-lookup"><span data-stu-id="3a522-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)

- [<span data-ttu-id="3a522-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="3a522-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)

- [<span data-ttu-id="3a522-136">SYSPrep. ps1</span><span class="sxs-lookup"><span data-stu-id="3a522-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)

- [<span data-ttu-id="3a522-137">Migrazione degli annunci di numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="3a522-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)

- [<span data-ttu-id="3a522-138">Dati Web conf</span><span class="sxs-lookup"><span data-stu-id="3a522-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a><span data-ttu-id="3a522-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="3a522-139">ABSConfig</span></span>
<span data-ttu-id="3a522-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="3a522-140"><a name="ABSConfig"> </a></span></span>

<span data-ttu-id="3a522-141">Lo strumento di configurazione del servizio Rubrica (ABSConfig) è uno strumento di amministrazione che consente agli amministratori di personalizzare la configurazione del servizio Rubrica in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="3a522-142">Questo strumento consente inoltre agli amministratori di Skype for Business Server 2015 di ripristinare le impostazioni predefinite del servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="3a522-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>

### <a name="description"></a><span data-ttu-id="3a522-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a522-143">Description</span></span>

<span data-ttu-id="3a522-144">ABSConfig è un'applicazione di interfaccia utente grafica che consente agli amministratori di configurare gli attributi dei servizi di dominio Active Directory correlati al servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="3a522-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="3a522-145">Gli scenari principali per lo strumento sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a522-145">The primary scenarios for the tool are the following:</span></span>

- <span data-ttu-id="3a522-146">Per consentire agli amministratori di eseguire il mapping degli attributi in servizi di dominio Active Directory agli attributi per Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>

- <span data-ttu-id="3a522-147">Per consentire agli amministratori di specificare l'attributo servizi di dominio Active Directory da includere o escludere nei file del servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="3a522-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

- <span data-ttu-id="3a522-148">Per consentire agli amministratori di ripristinare le impostazioni predefinite del servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="3a522-148">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="3a522-149">Lo strumento ABSConfig può essere avviato usando il file ABSConfig. exe.</span><span class="sxs-lookup"><span data-stu-id="3a522-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="3a522-150">Lo strumento viene aperto nella scheda **configura attributi** . Questa tabella include opzioni per eseguire il mapping degli attributi dei servizi di dominio Active Directory ai campi degli attributi per Skype for Business Server 2015 e per specificare quali utenti includere o escludere nei file del servizio Rubrica in base a specifici filtri di attributi.</span><span class="sxs-lookup"><span data-stu-id="3a522-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="3a522-151">Include anche opzioni per personalizzare il valore del numero di telefono da includere nel file della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="3a522-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="3a522-152">L'opzione **Ripristina predefiniti** consente agli amministratori di ripristinare le impostazioni del servizio Rubrica per i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="3a522-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

> [!NOTE]
> <span data-ttu-id="3a522-153">La rimappatura degli attributi degli annunci in nomi di campi OC diversi può essere eseguita solo per il download di file della Rubrica e non è supportata dalla query Web Rubrica.</span><span class="sxs-lookup"><span data-stu-id="3a522-153">Re-mapping of AD attributes to different OC Field Names will only work for Address Book File Download, and is not supported by Address Book Web Query.</span></span>

### <a name="output"></a><span data-ttu-id="3a522-154">Output</span><span class="sxs-lookup"><span data-stu-id="3a522-154">Output</span></span>

<span data-ttu-id="3a522-155">ABSConfig archivia la configurazione del servizio Rubrica nel database.</span><span class="sxs-lookup"><span data-stu-id="3a522-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="3a522-156">Scopo</span><span class="sxs-lookup"><span data-stu-id="3a522-156">Purpose</span></span>

<span data-ttu-id="3a522-157">ABSConfig offre un modo semplice e rapido per personalizzare il servizio Rubrica di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-157">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>

### <a name="requirements"></a><span data-ttu-id="3a522-158">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a522-158">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="3a522-159">Computer</span><span class="sxs-lookup"><span data-stu-id="3a522-159">Computer</span></span>

<span data-ttu-id="3a522-160">ABSConfig può essere eseguito solo da un computer collegato al dominio in cui è installato Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-160">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="3a522-161">Nel caso di Skype for Business Server 2015, Enterprise Edition, questo strumento può essere eseguito in qualsiasi server front-end in cui il servizio Rubrica è abilitato durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="3a522-161">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

#### <a name="network"></a><span data-ttu-id="3a522-162">Rete</span><span class="sxs-lookup"><span data-stu-id="3a522-162">Network</span></span>

<span data-ttu-id="3a522-163">Il computer dovrebbe essere in grado di connettersi al pool Front-end e al database back-end.</span><span class="sxs-lookup"><span data-stu-id="3a522-163">The computer should be able to connect to the Front End pool and back-end database.</span></span>

#### <a name="software"></a><span data-ttu-id="3a522-164">Software</span><span class="sxs-lookup"><span data-stu-id="3a522-164">Software</span></span>

<span data-ttu-id="3a522-165">Prima di eseguire lo strumento ABSConfig, è necessario installare i componenti software seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a522-165">The following software components must be installed before running the ABSConfig tool:</span></span>

- <span data-ttu-id="3a522-166">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3a522-166">Skype for Business Server 2015</span></span>

#### <a name="users"></a><span data-ttu-id="3a522-167">Utenti</span><span class="sxs-lookup"><span data-stu-id="3a522-167">Users</span></span>

<span data-ttu-id="3a522-168">Amministratori che hanno le autorizzazioni necessarie per aggiornare la distribuzione di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-168">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>

### <a name="examples"></a><span data-ttu-id="3a522-169">Esempi</span><span class="sxs-lookup"><span data-stu-id="3a522-169">Examples</span></span>

<span data-ttu-id="3a522-170">ABSConfig può essere avviato digitando **ABSConfig. exe** al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="3a522-170">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="3a522-171">Di seguito è riportata l'interfaccia utente dello strumento ABSConfig.</span><span class="sxs-lookup"><span data-stu-id="3a522-171">Shown below is the ABSConfig tool user interface.</span></span>

![Strumento ABSConfig.exe](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a><span data-ttu-id="3a522-173">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="3a522-173">Summary</span></span>

<span data-ttu-id="3a522-174">Lo strumento ABSConfig offre agli amministratori uno strumento rapido e facile da usare per personalizzare il servizio Rubrica di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="3a522-175">Monitoraggio del servizio criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="3a522-175">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="3a522-176"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="3a522-176"><a name="bpsm"> </a></span></span>

<span data-ttu-id="3a522-177">Lo strumento Monitoraggio dei servizi per la larghezza di banda è progettato per consentire agli amministratori di visualizzare un elenco delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a522-177">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1. <span data-ttu-id="3a522-178">Tutti i servizi per i criteri di larghezza di banda (autenticazione e Core) configurati in Skype for Business Server 2015 nella topologia</span><span class="sxs-lookup"><span data-stu-id="3a522-178">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2. <span data-ttu-id="3a522-179">Le connessioni che ogni servizio apporta ad altri servizi per i criteri di larghezza di banda e agli Edge Server</span><span class="sxs-lookup"><span data-stu-id="3a522-179">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3. <span data-ttu-id="3a522-180">Tutti i collegamenti configurati nel documento di configurazione della rete e nell'utilizzo della larghezza di banda in tempo reale riportati da ognuno dei servizi per i criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="3a522-180">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

### <a name="description"></a><span data-ttu-id="3a522-181">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a522-181">Description</span></span>

<span data-ttu-id="3a522-182">Lo strumento Monitoraggio del servizio di Bandwidth Policy viene implementato come applicazione basata su GUI.</span><span class="sxs-lookup"><span data-stu-id="3a522-182">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="3a522-183">Gli amministratori avviano lo strumento eseguendo PDPMonUI. exe.</span><span class="sxs-lookup"><span data-stu-id="3a522-183">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="3a522-184">Quando lo strumento viene avviato, cerca di individuare l'elenco dei servizi per i criteri di larghezza di banda nella topologia.</span><span class="sxs-lookup"><span data-stu-id="3a522-184">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="3a522-185">Dopo aver completato l'aggiornamento iniziale, il riquadro a sinistra della finestra viene popolato con un elenco di servizi raggruppati per i cluster a cui appartengono.</span><span class="sxs-lookup"><span data-stu-id="3a522-185">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="3a522-186">Quando gli amministratori selezionano un particolare servizio per i criteri di larghezza di banda, nel riquadro a destra vengono visualizzate le informazioni relative al particolare servizio.</span><span class="sxs-lookup"><span data-stu-id="3a522-186">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="3a522-187">Il riquadro contiene anche due schede principali che visualizzano le informazioni.</span><span class="sxs-lookup"><span data-stu-id="3a522-187">That pane also has two main tabs that display information.</span></span>

#### <a name="machine-info-tab"></a><span data-ttu-id="3a522-188">Scheda info computer</span><span class="sxs-lookup"><span data-stu-id="3a522-188">Machine Info Tab</span></span>

<span data-ttu-id="3a522-189">La scheda **info computer** Mostra i dettagli del servizio dei criteri di larghezza di banda selezionato e l'elenco e lo stato di tutte le connessioni effettuate dal servizio criteri di larghezza di banda selezionato ad altri servizi.</span><span class="sxs-lookup"><span data-stu-id="3a522-189">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

#### <a name="topology-info-tab"></a><span data-ttu-id="3a522-190">Scheda informazioni topologia</span><span class="sxs-lookup"><span data-stu-id="3a522-190">Topology Info Tab</span></span>

<span data-ttu-id="3a522-191">Nella scheda **informazioni topologia** viene visualizzato un elenco di tutti i collegamenti configurati nelle impostazioni di configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="3a522-191">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="3a522-192">Per ogni collegamento viene visualizzata la capacità di larghezza di banda audio e video.</span><span class="sxs-lookup"><span data-stu-id="3a522-192">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="3a522-193">Viene inoltre visualizzata la larghezza di banda attualmente utilizzata, sia in Kbps che come percentuale della capacità.</span><span class="sxs-lookup"><span data-stu-id="3a522-193">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="3a522-194">Lo strumento usa la codifica a colori per evidenziare i collegamenti con l'utilizzo che è vicino alla capacità, che consente agli amministratori di isolare rapidamente tali collegamenti.</span><span class="sxs-lookup"><span data-stu-id="3a522-194">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

> [!NOTE]
>  <span data-ttu-id="3a522-195">Se lo strumento Monitoraggio servizi di larghezza di banda non funziona quando si connette a uno dei servizi configurati per i criteri di larghezza di banda, le informazioni nelle schede informazioni **computer** e **informazioni topologia** non verranno popolate.</span><span class="sxs-lookup"><span data-stu-id="3a522-195">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="3a522-196">Tuttavia, è possibile che lo strumento possa connettersi inizialmente, ma in seguito perde la connessione al servizio.</span><span class="sxs-lookup"><span data-stu-id="3a522-196">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="3a522-197">In questi casi, gli amministratori possono visualizzare informazioni obsolete.</span><span class="sxs-lookup"><span data-stu-id="3a522-197">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="3a522-198">È disponibile un **ultimo timestamp aggiornato** in ognuna delle schede che consentono agli amministratori di vedere quando i dati sono stati aggiornati per un particolare servizio per i criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="3a522-198">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>

### <a name="output"></a><span data-ttu-id="3a522-199">Output</span><span class="sxs-lookup"><span data-stu-id="3a522-199">Output</span></span>

<span data-ttu-id="3a522-200">Non è disponibile alcun output della riga di comando; l'output del programma è contenuto nell'interfaccia utente grafica principale (GUI).</span><span class="sxs-lookup"><span data-stu-id="3a522-200">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

### <a name="purpose"></a><span data-ttu-id="3a522-201">Scopo</span><span class="sxs-lookup"><span data-stu-id="3a522-201">Purpose</span></span>

<span data-ttu-id="3a522-202">Lo scopo dello strumento Monitoraggio dei servizi per la larghezza di banda è consentire agli amministratori la visibilità dello stato di ognuno dei servizi per i criteri di larghezza di banda definiti nella topologia.</span><span class="sxs-lookup"><span data-stu-id="3a522-202">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="3a522-203">Gli amministratori possono inoltre visualizzare l'utilizzo della larghezza di banda in tempo reale per tutti i collegamenti definiti nel documento di configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="3a522-203">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

### <a name="requirements"></a><span data-ttu-id="3a522-204">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a522-204">Requirements</span></span>

<span data-ttu-id="3a522-205">Lo strumento Monitoraggio del servizio di Bandwidth Policy deve essere eseguito in un computer che fa parte della topologia di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3a522-205">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>

### <a name="summary"></a><span data-ttu-id="3a522-206">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="3a522-206">Summary</span></span>

<span data-ttu-id="3a522-207">Lo strumento Monitoraggio dei servizi per la larghezza di banda può essere una risorsa preziosa per gli amministratori in modo che possano ispezionare lo stato di tutti i servizi dei criteri di larghezza di banda nella topologia e, cosa più importante, possono ottenere l'utilizzo della larghezza di banda in tempo reale per i collegamenti definito nelle impostazioni di configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="3a522-207">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="3a522-208">Analizzatore dell'utilizzo della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="3a522-208">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="3a522-209"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="3a522-209"><a name="bua"> </a></span></span>

<span data-ttu-id="3a522-210">L'analizzatore dell'utilizzo della larghezza di banda è uno strumento che crea report su varie visualizzazioni del consumo di larghezza di banda dagli endpoint UC in collegamenti WAN nella rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="3a522-210">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="3a522-211">Questi report possono essere usati per comprendere il modello di consumo di larghezza di banda corrente e per facilitare la pianificazione della capacità di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="3a522-211">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

### <a name="description"></a><span data-ttu-id="3a522-212">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a522-212">Description</span></span>

<span data-ttu-id="3a522-213">L'analizzatore dell'utilizzo della larghezza di banda viene implementato come applicazione basata su GUI.</span><span class="sxs-lookup"><span data-stu-id="3a522-213">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="3a522-214">Questo strumento genera report specifici per l'utilizzo dell'audio in tutta la rete e consente la pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="3a522-214">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="3a522-215">Viene inoltre iterata sulla capacità di larghezza di banda assegnata a diversi collegamenti.</span><span class="sxs-lookup"><span data-stu-id="3a522-215">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

### <a name="output"></a><span data-ttu-id="3a522-216">Output</span><span class="sxs-lookup"><span data-stu-id="3a522-216">Output</span></span>

<span data-ttu-id="3a522-217">L'analizzatore dell'utilizzo della larghezza di banda offre grafici al grafico della capacità e dell'utilizzo della larghezza di banda per l'audio per tutti i collegamenti WAN configurati nel sistema.</span><span class="sxs-lookup"><span data-stu-id="3a522-217">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

### <a name="purpose"></a><span data-ttu-id="3a522-218">Scopo</span><span class="sxs-lookup"><span data-stu-id="3a522-218">Purpose</span></span>

<span data-ttu-id="3a522-219">In qualsiasi distribuzione di voce e video, è fondamentale monitorare e comprendere l'andamento dell'utilizzo della larghezza di banda del traffico multimediale attraverso la rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="3a522-219">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="3a522-220">Lo strumento Analizzatore di utilizzo della larghezza di banda consente a un amministratore di raggiungere questo obiettivo.</span><span class="sxs-lookup"><span data-stu-id="3a522-220">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="3a522-221">Questo strumento esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a522-221">This tool does the following:</span></span>

- <span data-ttu-id="3a522-222">Genera report specifici per l'utilizzo audio in rete</span><span class="sxs-lookup"><span data-stu-id="3a522-222">Generates specific reports for audio utilization across the network</span></span>

- <span data-ttu-id="3a522-223">Facilita la pianificazione e l'iterazione della capacità più efficace sulla capacità di larghezza di banda assegnata a diversi collegamenti</span><span class="sxs-lookup"><span data-stu-id="3a522-223">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="3a522-224">L'analizzatore dell'utilizzo della larghezza di banda può generare trame grafiche della capacità e dei report di utilizzo della larghezza di banda; sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a522-224">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

- <span data-ttu-id="3a522-225">Tutti i collegamenti WAN nella rete aziendale</span><span class="sxs-lookup"><span data-stu-id="3a522-225">All the WAN links in the enterprise network</span></span>

- <span data-ttu-id="3a522-226">Filtrato da collegamenti WAN selezionati scelti</span><span class="sxs-lookup"><span data-stu-id="3a522-226">Filtered by selected WAN links that have been chosen</span></span>

- <span data-ttu-id="3a522-227">Filtrati da collegamenti WAN che hanno superato la capacità di collegamento</span><span class="sxs-lookup"><span data-stu-id="3a522-227">Filtered by WAN links that have exceeded link capacity</span></span>

- <span data-ttu-id="3a522-228">Filtrati da collegamenti WAN che sono stati sottoposti a utilizzo della larghezza di banda provisioning</span><span class="sxs-lookup"><span data-stu-id="3a522-228">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

- <span data-ttu-id="3a522-229">Filtrare in base a collegamenti WAN che hanno raggiunto livelli critici (un utilizzo della larghezza di banda maggiore di 90% della capacità di larghezza di banda del collegamento WAN)</span><span class="sxs-lookup"><span data-stu-id="3a522-229">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

- <span data-ttu-id="3a522-230">Filtrato tramite il tipo di collegamento WAN: collegamenti a siti di rete, collegamenti interregionali e collegamenti all'interno di un sito</span><span class="sxs-lookup"><span data-stu-id="3a522-230">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

- <span data-ttu-id="3a522-231">Filtrata per area di rete</span><span class="sxs-lookup"><span data-stu-id="3a522-231">Filtered by network region</span></span>

#### <a name="applications"></a><span data-ttu-id="3a522-232">Applicazioni</span><span class="sxs-lookup"><span data-stu-id="3a522-232">Applications</span></span>

<span data-ttu-id="3a522-233">L'analizzatore dell'utilizzo della larghezza di banda include le due applicazioni seguenti (strumenti):</span><span class="sxs-lookup"><span data-stu-id="3a522-233">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

- <span data-ttu-id="3a522-234">**WanLinkLogCollector. exe** questo strumento consente all'utente di immettere le informazioni richieste.</span><span class="sxs-lookup"><span data-stu-id="3a522-234">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>

- <span data-ttu-id="3a522-235">**BandwidthUtilizationAnalyzer. xlsm** un report del foglio di calcolo di Microsoft Excel viene avviato automaticamente da WanLinkLogCollector. exe.</span><span class="sxs-lookup"><span data-stu-id="3a522-235">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="3a522-236">Questa applicazione consente all'utente di applicare filtri al report come illustrato più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="3a522-236">This application allows the user to apply filters to the report as shown later in this article.</span></span>

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="3a522-237">Fasi dell'uso dell'analizzatore dell'utilizzo della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="3a522-237">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="3a522-238">Quando si usa l'analizzatore dell'utilizzo della larghezza di banda, esistono due fasi:</span><span class="sxs-lookup"><span data-stu-id="3a522-238">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

- <span data-ttu-id="3a522-239">Raccolta di log, eseguita tramite WanLinkLogCollector. exe</span><span class="sxs-lookup"><span data-stu-id="3a522-239">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

- <span data-ttu-id="3a522-240">Personalizzare i report, che vengono eseguiti tramite BandwidthUtilizationAnalyzer. xlsm</span><span class="sxs-lookup"><span data-stu-id="3a522-240">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3a522-241">Consigliamo vivamente che BandwidthUtilizationAnalyzer. xlsm non venga lanciato manualmente dagli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="3a522-241">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>

#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="3a522-242">Avvio dell'analizzatore dell'utilizzo della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="3a522-242">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="3a522-243">Avviare WanLinkLogCollector. exe al prompt dei comandi o usando Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="3a522-243">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

 <span data-ttu-id="3a522-244">**Uso di WanLinkLogCollector. exe**</span><span class="sxs-lookup"><span data-stu-id="3a522-244">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="3a522-245">Sono disponibili tre passaggi per l'uso di WanLinkLogCollector. exe:</span><span class="sxs-lookup"><span data-stu-id="3a522-245">There are three steps to using WanLinkLogCollector.exe:</span></span>

1. <span data-ttu-id="3a522-246">**Registrare la sequenza temporale** Specificare la sequenza temporale per la quale deve essere generato il report</span><span class="sxs-lookup"><span data-stu-id="3a522-246">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>

2. <span data-ttu-id="3a522-247">**Specificare le directory dei file** Specificare le informazioni sulla posizione del file</span><span class="sxs-lookup"><span data-stu-id="3a522-247">**Specify the file directories** Provide file location information</span></span>

3. <span data-ttu-id="3a522-248">**Raccogliere i registri e avviare il Visualizzatore report** Eseguire il comando per generare il report</span><span class="sxs-lookup"><span data-stu-id="3a522-248">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>

#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="3a522-249">Passaggio 1-registrare la sequenza temporale</span><span class="sxs-lookup"><span data-stu-id="3a522-249">Step 1 - Log the timeline</span></span>

<span data-ttu-id="3a522-250">La registrazione della sequenza temporale consente all'utente dello strumento di specificare quanto segue, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="3a522-250">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1. <span data-ttu-id="3a522-251">**Data di inizio** Questa è la data di inizio della sequenza temporale a cui deve essere generato il report; ad esempio, 1 agosto 2010.</span><span class="sxs-lookup"><span data-stu-id="3a522-251">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2. <span data-ttu-id="3a522-252">**Data di fine** Questa è la data di fine della sequenza temporale a cui deve essere generato il report; ad esempio, il 30 settembre 2010.</span><span class="sxs-lookup"><span data-stu-id="3a522-252">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>

     ![Date di inizio e fine per l'analisi dell'utilizzo della larghezza di banda](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="3a522-254">Passaggio 2-specificare le directory dei file</span><span class="sxs-lookup"><span data-stu-id="3a522-254">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="3a522-255">Le directory di file seguenti possono essere specificate dall'utente come illustrato.</span><span class="sxs-lookup"><span data-stu-id="3a522-255">The following file directories can be specified by the user as shown.</span></span>

- <span data-ttu-id="3a522-256">**Posizione dei file di log del server** Percorso della cartella in cui sono archiviati i registri del server dei criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="3a522-256">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="3a522-257">Si \<tratta in genere di\> \\ Fileserver<scelta di\>Fe \AppServerFiles\PDP.</span><span class="sxs-lookup"><span data-stu-id="3a522-257">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>

- <span data-ttu-id="3a522-258">**Percorso di archiviazione file temporaneo** Percorso del file temporaneo in cui vengono archiviati i file intermedi mentre viene generato il report.</span><span class="sxs-lookup"><span data-stu-id="3a522-258">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

    ![Directory di file per l'analisi dell'utilizzo della larghezza di banda](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > <span data-ttu-id="3a522-260">Verificare che l'accesso a un file sufficiente ai registri del server e alla cartella temporanea dell'archivio file venga fornito all'utente dello strumento.</span><span class="sxs-lookup"><span data-stu-id="3a522-260">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="3a522-261">Passaggio 3-raccogliere i registri e avviare il Visualizzatore report</span><span class="sxs-lookup"><span data-stu-id="3a522-261">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="3a522-262">Per raccogliere i log e avviare il Visualizzatore report, fare clic su **Esegui** come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3a522-262">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="3a522-263">Questo passaggio raccoglie i dati necessari.</span><span class="sxs-lookup"><span data-stu-id="3a522-263">This step collects the required data.</span></span>

![Raccolta dei dati per l'analisi dell'utilizzo della larghezza di banda](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

<span data-ttu-id="3a522-265">Quando la convalida dell'input è riuscita, viene visualizzato il messaggio mostrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3a522-265">When the input validation is successful, the message shown below is displayed.</span></span>

![Notifica della raccolta dei log in Bandwidth Utili](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

<span data-ttu-id="3a522-267">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a522-267">Click **OK**.</span></span> <span data-ttu-id="3a522-268">BandwidthUtilizationAnalyzer. xlsm viene avviato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3a522-268">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="3a522-269">Seguire le istruzioni nella finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="3a522-269">Follow the instructions in the message box.</span></span> <span data-ttu-id="3a522-270">Per informazioni dettagliate, vedere **uso di BandwidthUtilizationAnalyzer. xlsm** nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="3a522-270">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>


### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="3a522-271">Uso di BandwidthUtilizationAnalyzer. xlsm</span><span class="sxs-lookup"><span data-stu-id="3a522-271">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="3a522-272">Quando BandwidthUtilizationAnalyzer. xlsm viene avviato automaticamente, fare clic su **Aggiorna** come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3a522-272">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. <span data-ttu-id="3a522-274">Quando si apre una cartella di file, selezionare consolidato. csv dalla posizione specificata nella finestra di messaggio, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3a522-274">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="3a522-275">Viene inoltre visualizzata la posizione come **C:\Temp**.</span><span class="sxs-lookup"><span data-stu-id="3a522-275">It also shows the location as **C:\Temp**.</span></span>

     ![Apertura di una cartella in Bandwidth Utilization Analyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. <span data-ttu-id="3a522-277">Fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="3a522-277">Click **Import**.</span></span>

4. <span data-ttu-id="3a522-278">La trama grafica viene generata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3a522-278">The graphical plot is automatically generated.</span></span> <span data-ttu-id="3a522-279">È disponibile quando il puntatore di lavoro in background scompare.</span><span class="sxs-lookup"><span data-stu-id="3a522-279">It is available when the working-in-the-background pointer disappears.</span></span>

     ![Applicazione di filtri nella visualizzazione Report.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="3a522-281">Applicazione di filtri alla visualizzazione report</span><span class="sxs-lookup"><span data-stu-id="3a522-281">Applying Filters to the Report View</span></span>

<span data-ttu-id="3a522-282">I filtri che è possibile applicare alla visualizzazione report come illustrato di seguito sono descritti di seguito:</span><span class="sxs-lookup"><span data-stu-id="3a522-282">The filters that can be applied to the report view as shown below are described as follows:</span></span>

![Applicazione di filtri nella visualizzazione Report.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. <span data-ttu-id="3a522-284">**Nome** Filtrare per collegamenti WAN (il filtro si trova sul lato destro del grafico). Il prefisso denota i tipi di collegamento seguenti: vedere la casella verticale (blu):</span><span class="sxs-lookup"><span data-stu-id="3a522-284">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>

   - <span data-ttu-id="3a522-285">**Sito S** Collegamento WAN da un sito di rete a un'area di rete</span><span class="sxs-lookup"><span data-stu-id="3a522-285">**S Site** The WAN link from a network site to a network region</span></span>

   - <span data-ttu-id="3a522-286">**È tra siti** Collegamento WAN tra due siti di rete</span><span class="sxs-lookup"><span data-stu-id="3a522-286">**IS Inter-Site** The WAN link between two network sites</span></span>

   - <span data-ttu-id="3a522-287">**Inter-area geografica R** Collegamento WAN tra due aree geografiche di rete</span><span class="sxs-lookup"><span data-stu-id="3a522-287">**R Inter-Region** The WAN link between two network region</span></span>

2. <span data-ttu-id="3a522-288">**Limite superato** Filtrare per collegamenti WAN il cui utilizzo della larghezza di banda è maggiore della capacità di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="3a522-288">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3. <span data-ttu-id="3a522-289">**Livelli critici** Filtrare per collegamenti WAN il cui utilizzo della larghezza di banda ha raggiunto 90% o più della capacità di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="3a522-289">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4. <span data-ttu-id="3a522-290">**Sottoutilizzati** Filtrare per collegamenti WAN il cui utilizzo della larghezza di banda è inferiore al 25% della capacità di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="3a522-290">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5. <span data-ttu-id="3a522-291">**Tipo di collegamento** Filtrare in base ai tipi di collegamenti WAN seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a522-291">**Link type** Filter by the following WAN links types:</span></span>

   - <span data-ttu-id="3a522-292">Tipo di **sito di rete**</span><span class="sxs-lookup"><span data-stu-id="3a522-292">**Network site** type</span></span>

   - <span data-ttu-id="3a522-293">Tipo **inter-sito**</span><span class="sxs-lookup"><span data-stu-id="3a522-293">**Inter-site** type</span></span>

   - <span data-ttu-id="3a522-294">Tipo **di collegamento tra aree** geografiche</span><span class="sxs-lookup"><span data-stu-id="3a522-294">**Inter-Region link** type</span></span>

6. <span data-ttu-id="3a522-295">**Area geografica** Filtrare per area di rete</span><span class="sxs-lookup"><span data-stu-id="3a522-295">**Region** Filter by network region</span></span>

<span data-ttu-id="3a522-296">Le figure seguenti mostrano i filtri descritti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="3a522-296">The following figures show the previously described filters.</span></span>

<span data-ttu-id="3a522-297">Filtrare in base al **nome**.</span><span class="sxs-lookup"><span data-stu-id="3a522-297">Filter by **Name**.</span></span> <span data-ttu-id="3a522-298">Selezionare l'elenco di collegamenti che devono essere visualizzati nel grafico.</span><span class="sxs-lookup"><span data-stu-id="3a522-298">Select the list of links that need to be displayed in the graph.</span></span>

![Filtro per nome in BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

<span data-ttu-id="3a522-300">Filtrare in base al **limite superato**.</span><span class="sxs-lookup"><span data-stu-id="3a522-300">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="3a522-301">Selezionare **true** per applicare il filtro.</span><span class="sxs-lookup"><span data-stu-id="3a522-301">Select **True** to enforce the filter.</span></span>

![Filtro per Exceeded Limit.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

<span data-ttu-id="3a522-303">Filtrare in base a **livelli critici**.</span><span class="sxs-lookup"><span data-stu-id="3a522-303">Filter by **Critical levels**.</span></span> <span data-ttu-id="3a522-304">Selezionare **true** per applicare il filtro.</span><span class="sxs-lookup"><span data-stu-id="3a522-304">Select **True** to enforce the filter.</span></span>

![Filtro per Critical Levels.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

<span data-ttu-id="3a522-306">Filtrare in **base a usato**.</span><span class="sxs-lookup"><span data-stu-id="3a522-306">Filter by **Under utilized**.</span></span> <span data-ttu-id="3a522-307">Selezionare **true** per applicare il filtro.</span><span class="sxs-lookup"><span data-stu-id="3a522-307">Select **True** to enforce the filter.</span></span>

![Filtro per Under Utilized.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

<span data-ttu-id="3a522-309">Filtra per **tipo di collegamento**.</span><span class="sxs-lookup"><span data-stu-id="3a522-309">Filter by **Link Type**.</span></span> <span data-ttu-id="3a522-310">Selezionare il tipo o i tipi che devono essere visualizzati.</span><span class="sxs-lookup"><span data-stu-id="3a522-310">Select the type or types that need to be displayed.</span></span>

![Filtro per Link Type.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

<span data-ttu-id="3a522-312">Filtrare per **area geografica**.</span><span class="sxs-lookup"><span data-stu-id="3a522-312">Filter by **Region**.</span></span> <span data-ttu-id="3a522-313">Selezionare un elenco di aree di cui devono essere visualizzati i collegamenti.</span><span class="sxs-lookup"><span data-stu-id="3a522-313">Select a list of regions whose links need to be displayed.</span></span>

![Filtro per Region.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a><span data-ttu-id="3a522-315">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a522-315">Requirements</span></span>

- <span data-ttu-id="3a522-316">.NET Framework 3,5</span><span class="sxs-lookup"><span data-stu-id="3a522-316">The .NET Framework 3.5</span></span>

- <span data-ttu-id="3a522-317">Microsoft Excel 2010 o Excel 2007</span><span class="sxs-lookup"><span data-stu-id="3a522-317">Microsoft Excel 2010 or Excel 2007</span></span>

### <a name="summary"></a><span data-ttu-id="3a522-318">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="3a522-318">Summary</span></span>

<span data-ttu-id="3a522-319">L'analizzatore dell'utilizzo della larghezza di banda viene usato per tracciare l'utilizzo della larghezza di banda audio per il traffico UC attraverso la rete.</span><span class="sxs-lookup"><span data-stu-id="3a522-319">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="3a522-320">Questo strumento può essere usato per segnalare l'utilizzo della larghezza di banda video anche nella rete.</span><span class="sxs-lookup"><span data-stu-id="3a522-320">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

## <a name="call-parkometer"></a><span data-ttu-id="3a522-321">Chiama Parkometer</span><span class="sxs-lookup"><span data-stu-id="3a522-321">Call Parkometer</span></span>
<span data-ttu-id="3a522-322"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="3a522-322"><a name="callpark"> </a></span></span>

<span data-ttu-id="3a522-323">Call Parkometer è un'applicazione della riga di comando che consente di accedere facilmente al database Orbit di Call Park.</span><span class="sxs-lookup"><span data-stu-id="3a522-323">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

### <a name="description"></a><span data-ttu-id="3a522-324">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a522-324">Description</span></span>

<span data-ttu-id="3a522-325">Chiamata Parkometer è uno strumento per tenere traccia delle chiamate parcheggiate attualmente.</span><span class="sxs-lookup"><span data-stu-id="3a522-325">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="3a522-326">Raccoglie anche statistiche sulle orbite e sull'utilizzo di Call Park Server (CPS).</span><span class="sxs-lookup"><span data-stu-id="3a522-326">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="3a522-327">Questo strumento della riga di comando offre sia la lettura che l'accesso in scrittura al database di SQL Server Orbit di CPS da un computer locale o connesso in remoto.</span><span class="sxs-lookup"><span data-stu-id="3a522-327">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="3a522-328">Tutte le opzioni si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="3a522-328">All options are mutually exclusive.</span></span> <span data-ttu-id="3a522-329">La sintassi della riga di comando è la seguente:</span><span class="sxs-lookup"><span data-stu-id="3a522-329">Command-line syntax is as follows:</span></span>

- <span data-ttu-id="3a522-330">**-o** parameter: elenca tutti gli intervalli di Orbit configurati per questo pool.</span><span class="sxs-lookup"><span data-stu-id="3a522-330">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>

- <span data-ttu-id="3a522-331">**-n** parameter: elenca tutte le orbite attualmente usate in questo pool.</span><span class="sxs-lookup"><span data-stu-id="3a522-331">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="3a522-332">Le informazioni visualizzate sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a522-332">The information displayed is as follows:</span></span>

  - <span data-ttu-id="3a522-333">URI (Uniform Resource Identifier) SIP di Parkee e Parker.</span><span class="sxs-lookup"><span data-stu-id="3a522-333">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>

  - <span data-ttu-id="3a522-334">Nome host del CPS in cui è parcheggiata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="3a522-334">Host name of the CPS where the call is parked.</span></span>

  - <span data-ttu-id="3a522-335">Indicatore di data e ora di quando la chiamata è stata parcheggiata.</span><span class="sxs-lookup"><span data-stu-id="3a522-335">Time stamp of when the call was parked.</span></span>

- <span data-ttu-id="3a522-336">**-parametro f** : elenca il numero di orbite attualmente libere nel pool.</span><span class="sxs-lookup"><span data-stu-id="3a522-336">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>

- <span data-ttu-id="3a522-337">\*\*-r \<n\> \*\* Parameter-elenca le \<n\> ultime chiamate parcheggiate.</span><span class="sxs-lookup"><span data-stu-id="3a522-337">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="3a522-338">Le informazioni visualizzate sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a522-338">The information displayed is as follows:</span></span>

  - <span data-ttu-id="3a522-339">URI SIP di Parkee.</span><span class="sxs-lookup"><span data-stu-id="3a522-339">Parkee SIP URI.</span></span>

  - <span data-ttu-id="3a522-340">URI SIP di Parker.</span><span class="sxs-lookup"><span data-stu-id="3a522-340">Parker SIP URI.</span></span>

  - <span data-ttu-id="3a522-341">Nome host del CPS in cui è stata parcheggiata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="3a522-341">Host name of the CPS where the call was parked.</span></span>

  - <span data-ttu-id="3a522-342">Indicatore di data e ora di quando la chiamata è stata recuperata o eliminata.</span><span class="sxs-lookup"><span data-stu-id="3a522-342">Time stamp of when the call was retrieved or dropped.</span></span>

- <span data-ttu-id="3a522-343">**-parametro\<t\> n** -test che riservano un'orbita nel database per mostrare la casualità dei numeri di orbita assegnati.</span><span class="sxs-lookup"><span data-stu-id="3a522-343">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

### <a name="output"></a><span data-ttu-id="3a522-344">Output</span><span class="sxs-lookup"><span data-stu-id="3a522-344">Output</span></span>

<span data-ttu-id="3a522-345">In base ai parametri di input specificati al prompt dei comandi, chiama Parkometer Visualizza l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="3a522-345">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

- <span data-ttu-id="3a522-346">Tutti gli intervalli di orbita configurati per il pool</span><span class="sxs-lookup"><span data-stu-id="3a522-346">All orbit ranges that are configured for this pool</span></span>

- <span data-ttu-id="3a522-347">Chiamate attualmente parcheggiate</span><span class="sxs-lookup"><span data-stu-id="3a522-347">Currently parked calls</span></span>

- <span data-ttu-id="3a522-348">Numero di orbite libere (disponibili)</span><span class="sxs-lookup"><span data-stu-id="3a522-348">Number of free (available) orbits</span></span>

- <span data-ttu-id="3a522-349">Chiamate parcheggiate di recente</span><span class="sxs-lookup"><span data-stu-id="3a522-349">Recently parked calls</span></span>

- <span data-ttu-id="3a522-350">Orbite riservate per testare i valori dell'orbita uniforme e casuale</span><span class="sxs-lookup"><span data-stu-id="3a522-350">Reserved orbits for testing uniform and random orbit values</span></span>

### <a name="purpose"></a><span data-ttu-id="3a522-351">Scopo</span><span class="sxs-lookup"><span data-stu-id="3a522-351">Purpose</span></span>

<span data-ttu-id="3a522-352">Lo scopo dello strumento CPS è quello di consentire l'accesso della riga di comando al database CPS.</span><span class="sxs-lookup"><span data-stu-id="3a522-352">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="3a522-353">L'amministratore può visualizzare l'utilizzo di CPS e determinare il numero di orbite assegnate a un pool.</span><span class="sxs-lookup"><span data-stu-id="3a522-353">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

### <a name="requirements"></a><span data-ttu-id="3a522-354">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a522-354">Requirements</span></span>

<span data-ttu-id="3a522-355">Se questo strumento viene eseguito nello stesso computer in cui è in esecuzione CPS, non sono previsti requisiti.</span><span class="sxs-lookup"><span data-stu-id="3a522-355">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="3a522-356">Se questo strumento viene eseguito in un computer remoto, il database di SQL Server usato da Skype for Business Server 2015 deve essere configurato per consentire l'accesso remoto.</span><span class="sxs-lookup"><span data-stu-id="3a522-356">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="3a522-357">La chiamata di Parkometer deve essere configurata con una stringa di connessione al database di SQL Server per connettersi al server SQL del pool.</span><span class="sxs-lookup"><span data-stu-id="3a522-357">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="3a522-358">Questa stringa di connessione al database di SQL Server è definita nel file di configurazione **parkometer. exe. config**. Deve essere posizionato nella stessa directory in cui si trova parkometer. exe.</span><span class="sxs-lookup"><span data-stu-id="3a522-358">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="3a522-359">Il file XML seguente è un esempio di parkometer. exe. config. I parametri che devono essere configurati sono nome utente (ad esempio, mydomain\Administrator), password (ad esempio, password) e nome host, ad esempio myserver.</span><span class="sxs-lookup"><span data-stu-id="3a522-359">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

### <a name="examples"></a><span data-ttu-id="3a522-360">Esempi</span><span class="sxs-lookup"><span data-stu-id="3a522-360">Examples</span></span>

<span data-ttu-id="3a522-361">Intervalli di Orbit distribuiti: il parametro-o elenca tutti gli intervalli di orbita configurati per il pool come illustrato</span><span class="sxs-lookup"><span data-stu-id="3a522-361">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

![Intervalli dei codici orbit in Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

<span data-ttu-id="3a522-363">Chiamate attualmente parcheggiate: il parametro-n elenca tutte le orbite attualmente usate in questo pool come illustrato</span><span class="sxs-lookup"><span data-stu-id="3a522-363">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>

![Chiamate attualmente parcheggiate in Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

<span data-ttu-id="3a522-365">Numero di orbite gratuite: il parametro-f elenca il numero di orbite attualmente libere nel pool come illustrato</span><span class="sxs-lookup"><span data-stu-id="3a522-365">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>

![Codici orbit liberi in Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

<span data-ttu-id="3a522-367">Chiamate parcheggiate di recente: il parametro \<-\> r n elenca \<le\> n ultime chiamate parcheggiate come illustrato</span><span class="sxs-lookup"><span data-stu-id="3a522-367">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

![Chiamate parcheggiate di recente in Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

<span data-ttu-id="3a522-369">Verifica prenotazione in orbita: i test \<dei\> parametri-t n riservano un'orbita nel database come illustrato</span><span class="sxs-lookup"><span data-stu-id="3a522-369">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

![Prenotazione codici orbit di test in Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a><span data-ttu-id="3a522-371">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="3a522-371">Summary</span></span>

<span data-ttu-id="3a522-372">Call Parkometer è uno strumento della riga di comando che fornisce informazioni dettagliate sul server di Call Park.</span><span class="sxs-lookup"><span data-stu-id="3a522-372">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

## <a name="dbanalyze"></a><span data-ttu-id="3a522-373">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="3a522-373">DBAnalyze</span></span>
<span data-ttu-id="3a522-374"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="3a522-374"><a name="dba"> </a></span></span>

### <a name="description"></a><span data-ttu-id="3a522-375">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a522-375">Description</span></span>

<span data-ttu-id="3a522-376">DBAnalyze è uno strumento della riga di comando che consente agli amministratori di raccogliere report di analisi sui database di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-376">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="3a522-377">DBAnalyze ha le modalità seguenti: diagnostica, dati utente, conferenza, MCU e frammentazione del disco:</span><span class="sxs-lookup"><span data-stu-id="3a522-377">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

- <span data-ttu-id="3a522-378">**Modalità diagnostica** Crea un report che include informazioni sulle tabelle (numero di record, frammentazione, dimensioni dei dati, e le dimensioni degli indici), le dimensioni dei file di dati e di log, l'ultima ora di backup, la distribuzione di contatti tra server che esegue Microsoft Office Communications Server, il numero medio di autorizzazioni, contatti, contenitori, abbonamenti, pubblicazioni, endpoint per utente, eventuali utenti non correttamente ospitati, utenti non instradati, il numero medio di conferenze organizzate per utente e la versione del database.</span><span class="sxs-lookup"><span data-stu-id="3a522-378">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3a522-379">L'esecuzione della modalità diagnostica può influire sulle prestazioni del server.</span><span class="sxs-lookup"><span data-stu-id="3a522-379">Running diagnostic mode can affect server performance.</span></span>

- <span data-ttu-id="3a522-380">**Modalità dati utente** Segnala i dati relativi a contatti, contenitori, abbonamenti, pubblicazioni, autorizzazioni e gruppi di contatti per un utente specificato o per gli utenti che hanno tale utente negli elenchi contatti e autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="3a522-380">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="3a522-381">Questa modalità riporta anche i dati di riepilogo per le conferenze a cui un utente organizza o è invitato.</span><span class="sxs-lookup"><span data-stu-id="3a522-381">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

- <span data-ttu-id="3a522-382">**Modalità conferenza** Riporta i dati dettagliati per una conferenza specifica, inclusi tutti i dettagli relativi alla programmazione per la conferenza, l'elenco di invitati, l'elenco dei tipi di elementi multimediali consentiti per la conferenza, i MCU attivi (unità di controllo multipunto), l'elenco dei partecipanti attivi e lo stato di segnalazione di ogni partecipante.</span><span class="sxs-lookup"><span data-stu-id="3a522-382">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>

- <span data-ttu-id="3a522-383">**Decodificare l'ID riunione** Decodifica un ID riunione PSTN (Public Switched Telephone Network) specificato dall'opzione **/pstnid** ma non si connette al back-end per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="3a522-383">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

- <span data-ttu-id="3a522-384">**Risoluzione conferenza** Decodifica un ID riunione PSTN specificato dall'opzione **/pstnid** e visualizza le informazioni sulla Conferenza indicata dall'ID.</span><span class="sxs-lookup"><span data-stu-id="3a522-384">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

- <span data-ttu-id="3a522-385">**Modalità MCU** Riporta l'ID, il tipo di elemento multimediale, l'URL, lo stato di heartbeat, il carico delle conferenze e il carico dei partecipanti per ogni MCU nel pool.</span><span class="sxs-lookup"><span data-stu-id="3a522-385">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

- <span data-ttu-id="3a522-386">**Modalità di frammentazione del disco** Visualizza lo stato di frammentazione di tutti i dischi.</span><span class="sxs-lookup"><span data-stu-id="3a522-386">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="3a522-387">Questo strumento può essere usato per diagnosticare vari problemi o per aiutare gli amministratori con la pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="3a522-387">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="3a522-388">Ad esempio, se la maggior parte degli utenti ospitati nel server A sceglie utenti ospitati nel server B come contatti, l'amministratore può trasferire gli utenti nel server a nel server B per ridurre il traffico tra server.</span><span class="sxs-lookup"><span data-stu-id="3a522-388">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

### <a name="output"></a><span data-ttu-id="3a522-389">Output</span><span class="sxs-lookup"><span data-stu-id="3a522-389">Output</span></span>

<span data-ttu-id="3a522-390">Questo strumento restituisce i report predefiniti relativi al database di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-390">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="3a522-391">**Percorso**:%ProgramFiles%\Skype for Business Server 2015 \ reskit</span><span class="sxs-lookup"><span data-stu-id="3a522-391">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>

### <a name="purpose"></a><span data-ttu-id="3a522-392">Scopo</span><span class="sxs-lookup"><span data-stu-id="3a522-392">Purpose</span></span>

<span data-ttu-id="3a522-393">Per installare Dbanalyze. exe, copiarlo in una cartella locale e quindi eseguire lo strumento.</span><span class="sxs-lookup"><span data-stu-id="3a522-393">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="3a522-394">Per usare lo strumento, eseguire il comando seguente dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="3a522-394">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="3a522-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`Di seguito sono elencate le descrizioni delle opzioni della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="3a522-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>

![Opzioni della riga di comando per Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a><span data-ttu-id="3a522-397">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a522-397">Requirements</span></span>

 <span data-ttu-id="3a522-398">**Computer** DBAnalyze può essere eseguito solo da un computer collegato al dominio in cui è installato Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-398">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>

 <span data-ttu-id="3a522-399">**Rete** Il computer dovrebbe essere in grado di connettersi al database back-end.</span><span class="sxs-lookup"><span data-stu-id="3a522-399">**Network** The computer should be able to connect to the back-end database.</span></span>

 <span data-ttu-id="3a522-400">**Software** I componenti software di Skype for Business Server 2015 devono essere installati prima di eseguire DBAnalyze.</span><span class="sxs-lookup"><span data-stu-id="3a522-400">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>

 <span data-ttu-id="3a522-401">**Utenti** La tabella seguente Mostra gli amministratori che hanno le autorizzazioni necessarie per accedere ai database di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-401">**Users**The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>

![Tabella di autorizzazioni per Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> <span data-ttu-id="3a522-403">È necessario un account di amministratore locale per **/report: modalità disco** .</span><span class="sxs-lookup"><span data-stu-id="3a522-403">A local administrator account is required for **/report:disk** mode.</span></span>

### <a name="examples"></a><span data-ttu-id="3a522-404">Esempi</span><span class="sxs-lookup"><span data-stu-id="3a522-404">Examples</span></span>

<span data-ttu-id="3a522-405">Di seguito sono riportati alcuni esempi di comandi Dbanalyze. exe validi:</span><span class="sxs-lookup"><span data-stu-id="3a522-405">The following are examples of valid Dbanalyze.exe commands:</span></span>

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="3a522-406">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="3a522-406">Summary</span></span>

<span data-ttu-id="3a522-407">DBAnalyzer consente agli amministratori di analizzare in modo rapido e semplice i database di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-407">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>

## <a name="import-storage-service-data"></a><span data-ttu-id="3a522-408">Importare i dati del servizio di archiviazione</span><span class="sxs-lookup"><span data-stu-id="3a522-408">Import Storage Service Data</span></span>
<span data-ttu-id="3a522-409"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="3a522-409"><a name="Issd"> </a></span></span>

<span data-ttu-id="3a522-410">Lo strumento ImportStorageServiceData Resource Kit consente di riimportare i dati di Accodamento e endpoint che sono stati svuotati dal servizio di archiviazione (LYSS) di nuovo nel servizio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="3a522-410">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

### <a name="description"></a><span data-ttu-id="3a522-411">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a522-411">Description</span></span>

<span data-ttu-id="3a522-412">I dati svuotati del servizio di archiviazione avrebbero potuto essere automatici (periodici) in base allo stato dell'elemento della coda o alle dimensioni del database.</span><span class="sxs-lookup"><span data-stu-id="3a522-412">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="3a522-413">Potrebbe essere accaduto a causa della chiamata manuale del cmdlet di failover del pool o del cmdlet StorageServiceFullFlush (che richiama il cmdlet di failover del pool).</span><span class="sxs-lookup"><span data-stu-id="3a522-413">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="3a522-414">Tieni presente che i dati non devono essere reimportati idealmente se una delle dimensioni del database del servizio di archiviazione (LYSS) nei Front Ends è superiore al livello normale, perché in questo modo probabilmente causerà l'esportazione di più dati. Inoltre, gli eventuali problemi che potrebbero avere contribuito agli errori che hanno causato l'aumento della coda del servizio di archiviazione devono essere risolti prima di tutto, ad esempio gli errori degli endpoint di Exchange, i problemi di rete o altri problemi.</span><span class="sxs-lookup"><span data-stu-id="3a522-414">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

 <span data-ttu-id="3a522-415">**Scenario 1:** durante il failover del pool, i file possono essere svuotati dal servizio di archiviazione per ogni front-end.</span><span class="sxs-lookup"><span data-stu-id="3a522-415">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="3a522-416">Dopo aver completato il failover, lo strumento deve essere eseguito per reimportare i dati.</span><span class="sxs-lookup"><span data-stu-id="3a522-416">After failover is completed, the tool should be run to re-import the data.</span></span>

 <span data-ttu-id="3a522-417">**Scenario 2:** i dati vengono svuotati automaticamente ogni giorno o in risposta al database del servizio di archiviazione che supera determinate soglie di dimensione (ad esempio 60%, 80%, 90% Full).</span><span class="sxs-lookup"><span data-stu-id="3a522-417">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="3a522-418">I dati scaricati automaticamente devono essere reimportati di routine dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="3a522-418">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="3a522-419">Nella situazione precedente, se il monitoraggio SCOM Pack non è distribuito, esistono eventi per il servizio di archiviazione di Skype for Business Server relativo ai dati da svuotare dal servizio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="3a522-419">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="3a522-420">ID evento di 32075 (operazione di svuotamento completo), 32076 (il colore completo è completato), 32082 (livello di manutenzione a filo iniziato), 32083 (livello di manutenzione), 32089 (lo svuotamento si è verificato a causa del riempimento del database).</span><span class="sxs-lookup"><span data-stu-id="3a522-420">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="3a522-421">Nota Questi ID evento corrispondono alla versione RTM.</span><span class="sxs-lookup"><span data-stu-id="3a522-421">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="3a522-422">Quando un amministratore vede questi eventi, significa che ci sono file che sono stati svuotati. Questi dati devono essere di routine importati di nuovo usando questo strumento, ad esempio una volta alla settimana.</span><span class="sxs-lookup"><span data-stu-id="3a522-422">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="3a522-423">Per la versione del servizio online, se è distribuito SCOM Pack per Skype for Business Server, è possibile che vengano generati nuovi avvisi che chiedono all'amministratore di reimportare nuovamente i dati svuotati in un servizio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="3a522-423">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="3a522-424">Verrà visualizzato un evento corrispondente nel log eventi del server front-end che ha attivato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="3a522-424">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="3a522-425">L'evento darà una descrizione del percorso padre in cui si trovano i file di dati svuotati, nonché il numero di file che soddisfano i criteri di avviso.</span><span class="sxs-lookup"><span data-stu-id="3a522-425">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="3a522-426">I criteri di avviso sono che ci sono X o più file sotto il percorso padre specifico che hanno almeno Y giorni prima (dove X e Y sono preimpostati all'interno del StorageService ma possono essere ignorati modificando il file APPCONFIG). Di seguito sono illustrati due esempi di eventi che possono attivare l'avviso di integrità, con la differenza che è il percorso padre.</span><span class="sxs-lookup"><span data-stu-id="3a522-426">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="3a522-427">Una possibilità è in condivisione file del servizio Web, mentre l'altra possibilità è la directory dei dati dell'applicazione locale di ogni front-end.</span><span class="sxs-lookup"><span data-stu-id="3a522-427">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="3a522-428">ad esempio c:\ProgramData\Microsoft\Skype for Business Server 2015 \ StorageService).</span><span class="sxs-lookup"><span data-stu-id="3a522-428">( for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ).</span></span> <span data-ttu-id="3a522-429">L'amministratore eseguirà quindi questo strumento di reskit.</span><span class="sxs-lookup"><span data-stu-id="3a522-429">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="3a522-430">Questo strumento incrementerà il carico di CPU e IO nella parte anteriore in cui è in esecuzione, oltre ad altri front ends, nella situazione in cui i dati non sono di proprietà del front-end in cui viene eseguito lo strumento.</span><span class="sxs-lookup"><span data-stu-id="3a522-430">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="3a522-431">Ti consigliamo di Runng questo strumento quando i Front ends non sono sotto il carico di CPU e IO elevato, ad esempio al di fuori delle ore di punta.</span><span class="sxs-lookup"><span data-stu-id="3a522-431">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="3a522-432">In secondo luogo, questo strumento può eseguire da 2 a 3 minuti per importare un file di dati.</span><span class="sxs-lookup"><span data-stu-id="3a522-432">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="3a522-433">Tieni presente quando valuti quanto tempo verrà eseguito lo strumento.</span><span class="sxs-lookup"><span data-stu-id="3a522-433">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="3a522-434">Il file di log dettagliato generato dallo strumento verrà visualizzato per impostazione predefinita nell'archivio file.</span><span class="sxs-lookup"><span data-stu-id="3a522-434">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="3a522-435">Eliminarlo se non sono stati segnalati errori, perché il file di log può essere di decine di MB o più.</span><span class="sxs-lookup"><span data-stu-id="3a522-435">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

![Esempio di eventi nel registro eventi del server di archiviazione.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a><span data-ttu-id="3a522-437">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a522-437">Requirements</span></span>

<span data-ttu-id="3a522-438">Installare gli strumenti del Resource Kit di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-438">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="3a522-439">Lo strumento viene eseguito su computer Uniti a un dominio in cui sono installati Skype for Business Server e Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3a522-439">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="3a522-440">Lo strumento usa un cmdlet di Management Shell per identificare tutti i server front-end nel pool.</span><span class="sxs-lookup"><span data-stu-id="3a522-440">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="3a522-441">In secondo luogo, lo strumento deve essere eseguito da un computer nel pool in cui è installato il database **RtcLocal** .</span><span class="sxs-lookup"><span data-stu-id="3a522-441">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="3a522-442">Questo database viene usato dallo strumento per recuperare la posizione della condivisione di file WEBSERVICE per il pool.</span><span class="sxs-lookup"><span data-stu-id="3a522-442">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="3a522-443">Inoltre, prima di usare lo strumento, ogni server front-end deve prima consentire la comunicazione remota di Windows PowerShell tramite **Enable-PSRemoting** su ogni server front-end e il computer da cui viene eseguito lo strumento.</span><span class="sxs-lookup"><span data-stu-id="3a522-443">Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="3a522-444">In caso contrario, i comandi remoti di Windows PowerShell da questo strumento avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="3a522-444">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="3a522-445">La comunicazione remota di Windows PowerShell può essere disattivata in tutti i server front-end nel pool al termine dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="3a522-445">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="3a522-446">Infine, l'account o le credenziali che richiamano lo strumento devono avere l'autorizzazione di lettura/scrittura per la condivisione di file WebService per il pool in cui eseguono questo strumento.</span><span class="sxs-lookup"><span data-stu-id="3a522-446">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="3a522-447">In caso contrario, lo strumento non riuscirà con gli errori di autorizzazione IO.</span><span class="sxs-lookup"><span data-stu-id="3a522-447">Otherwise the tool will fail with IO Permission errors.</span></span>

> [!NOTE]
> <span data-ttu-id="3a522-448">In Windows Server 2012 la comunicazione remota di Windows PowerShell è abilitata per impostazione predefinita, ma non nel sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="3a522-448">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>

### <a name="examples"></a><span data-ttu-id="3a522-449">Esempi</span><span class="sxs-lookup"><span data-stu-id="3a522-449">Examples</span></span>

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

## <a name="lcssync"></a><span data-ttu-id="3a522-450">LCSSync</span><span class="sxs-lookup"><span data-stu-id="3a522-450">LCSSync</span></span>
<span data-ttu-id="3a522-451"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="3a522-451"><a name="LCSSync"> </a></span></span>

<span data-ttu-id="3a522-452">Lo strumento LCSSync consente di distribuire il software di comunicazione di Skype for Business Server 2015 in un ambiente con più foreste.</span><span class="sxs-lookup"><span data-stu-id="3a522-452">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="3a522-453">Questo strumento viene usato per sincronizzare utenti e gruppi di foreste di utenti diversi come un oggetto contatto di servizi di dominio Active Directory in una foresta centrale in cui è installato Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-453">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>

### <a name="description"></a><span data-ttu-id="3a522-454">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a522-454">Description</span></span>

 <span data-ttu-id="3a522-455">LCSSync usa gli oggetti contatto di servizi di dominio Active Directory sincronizzati nella foresta centrale per consentire agli utenti di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3a522-455">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="3a522-456">Per specificare Single Sign-in, l'account utente principale deve essere mappato all'oggetto contatto Active Directory Domain Services nella foresta centrale per Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-456">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="3a522-457">Questo strumento consente di eseguire tale mapping.</span><span class="sxs-lookup"><span data-stu-id="3a522-457">This tool helps perform that mapping.</span></span> <span data-ttu-id="3a522-458">Questo strumento include modelli per la creazione di agenti di gestione in Microsoft Identity Integration Server.</span><span class="sxs-lookup"><span data-stu-id="3a522-458">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

### <a name="summary"></a><span data-ttu-id="3a522-459">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="3a522-459">Summary</span></span>

<span data-ttu-id="3a522-460">Lo strumento LCSSync consente di distribuire Skype for Business Server 2015 in un ambiente con più insiemi di strutture.</span><span class="sxs-lookup"><span data-stu-id="3a522-460">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>

## <a name="lookup-user-console"></a><span data-ttu-id="3a522-461">Console utente di ricerca</span><span class="sxs-lookup"><span data-stu-id="3a522-461">Lookup User Console</span></span>
<span data-ttu-id="3a522-462"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="3a522-462"><a name="LUC"> </a></span></span>

<span data-ttu-id="3a522-463">Lo strumento LookupUserConsole Visualizza le informazioni di routing interne di Skype for Business Server su utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="3a522-463">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="3a522-464">Queste informazioni possono essere utili per il supporto Microsoft personale per la diagnosi dei problemi di distribuzione e routing.</span><span class="sxs-lookup"><span data-stu-id="3a522-464">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

### <a name="description"></a><span data-ttu-id="3a522-465">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a522-465">Description</span></span>

 <span data-ttu-id="3a522-466">L'esecuzione di LookupUserConsole. exe apre un prompt dei comandi che accetta gli indirizzi SIP e cerca di visualizzare le informazioni di routing interne di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3a522-466">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="3a522-467">Digitare **Exit** per chiudere lo strumento LookupUserConsole.</span><span class="sxs-lookup"><span data-stu-id="3a522-467">Type **exit** to quit the LookupUserConsole tool.</span></span>

### <a name="requirements"></a><span data-ttu-id="3a522-468">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a522-468">Requirements</span></span>

<span data-ttu-id="3a522-469">Installare il Resource Kit di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-469">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="3a522-470">Lo strumento viene eseguito su computer Uniti a un dominio in cui è installato Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3a522-470">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>

### <a name="examples"></a><span data-ttu-id="3a522-471">Esempi</span><span class="sxs-lookup"><span data-stu-id="3a522-471">Examples</span></span>

<span data-ttu-id="3a522-472">C: Skype for Business Server 2015 \ reskit\>LookupUserConsole. exe</span><span class="sxs-lookup"><span data-stu-id="3a522-472">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>

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

## <a name="msturnping"></a><span data-ttu-id="3a522-473">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="3a522-473">MsTurnPing</span></span>
<span data-ttu-id="3a522-474"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="3a522-474"><a name="MsTurnPing"> </a></span></span>

<span data-ttu-id="3a522-475">Lo strumento MSTurnPing consente a un amministratore del software di comunicazione di Skype for Business Server 2015 di controllare lo stato dei server che gestiscono i servizi di autenticazione audio/video e di video, nonché i server che gestiscono i servizi per i criteri di larghezza di banda nella topologia.</span><span class="sxs-lookup"><span data-stu-id="3a522-475">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

### <a name="description"></a><span data-ttu-id="3a522-476">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a522-476">Description</span></span>

<span data-ttu-id="3a522-477">Lo strumento MSTurnPing consente a un amministratore del software di comunicazione di Skype for Business Server 2015 di controllare lo stato dei server che gestiscono i servizi di autenticazione audio/video e di video, nonché i server che gestiscono i servizi per i criteri di larghezza di banda nella topologia.</span><span class="sxs-lookup"><span data-stu-id="3a522-477">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="3a522-478">Lo strumento consente all'amministratore di eseguire i test seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a522-478">The tool allows the administrator to perform the following tests:</span></span>

1. <span data-ttu-id="3a522-479">Test a/V Edge Server: lo strumento esegue i test su tutti i/V Edge Server della topologia eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a522-479">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>

   - <span data-ttu-id="3a522-480">Verificare che il servizio di autenticazione audio/video di Skype for Business Server sia avviato e possa emettere le credenziali appropriate.</span><span class="sxs-lookup"><span data-stu-id="3a522-480">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="3a522-481">Verificare che il servizio Edge audio/video di Skype for Business Server sia stato avviato e che sia possibile allocare le risorse sul bordo esterno con successo.</span><span class="sxs-lookup"><span data-stu-id="3a522-481">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2. <span data-ttu-id="3a522-482">Test del servizio criteri di larghezza di banda: lo strumento esegue i test in tutti i server che eseguono i servizi per i criteri di larghezza di banda nella topologia eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a522-482">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>

   - <span data-ttu-id="3a522-483">Verificare che il servizio di gestione della larghezza di banda (autenticazione) di Skype for Business Server sia avviato e possa emettere le credenziali appropriate.</span><span class="sxs-lookup"><span data-stu-id="3a522-483">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="3a522-484">Verificare che il servizio di gestione della larghezza di banda (Core) di Skype for Business Server sia stato avviato e possa eseguire correttamente il controllo della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="3a522-484">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="3a522-485">Questo strumento deve essere eseguito da un computer che fa parte della topologia e ha installato lo Store locale.</span><span class="sxs-lookup"><span data-stu-id="3a522-485">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

### <a name="output"></a><span data-ttu-id="3a522-486">Output</span><span class="sxs-lookup"><span data-stu-id="3a522-486">Output</span></span>

<span data-ttu-id="3a522-487">Lo strumento restituisce i risultati di ogni operazione.</span><span class="sxs-lookup"><span data-stu-id="3a522-487">The tool outputs the results of each of the operations.</span></span>

- <span data-ttu-id="3a522-488">Se viene eseguito il test **AudioVideoEdgeServer** , gli output degli strumenti sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a522-488">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="3a522-489">I risultati del test dei computer che includono il servizio di autenticazione audio/video di Skype for Business Server 2015 nella topologia</span><span class="sxs-lookup"><span data-stu-id="3a522-489">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>

  - <span data-ttu-id="3a522-490">I risultati del test dei computer che prevedono il servizio Edge audio/video di Skype for Business Server 2015 nella topologia</span><span class="sxs-lookup"><span data-stu-id="3a522-490">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>

- <span data-ttu-id="3a522-491">Se viene eseguito il test **BandwidthPolicyServer** , gli output degli strumenti sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a522-491">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="3a522-492">I risultati del test dei computer che includono il servizio di gestione dei criteri di larghezza di banda di Skype for Business Server 2015 (autenticazione) nella topologia</span><span class="sxs-lookup"><span data-stu-id="3a522-492">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>

  - <span data-ttu-id="3a522-493">I risultati del test dei computer che includono il servizio di gestione dei criteri di larghezza di banda di Skype for Business Server 2015 (Core) nella topologia</span><span class="sxs-lookup"><span data-stu-id="3a522-493">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>

### <a name="requirements"></a><span data-ttu-id="3a522-494">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a522-494">Requirements</span></span>

- <span data-ttu-id="3a522-495">Questo strumento deve essere eseguito da un computer che si trova nella topologia e che contiene lo Store locale.</span><span class="sxs-lookup"><span data-stu-id="3a522-495">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

- <span data-ttu-id="3a522-496">Lo strumento deve essere eseguito come amministratore che ha accesso allo Store locale.</span><span class="sxs-lookup"><span data-stu-id="3a522-496">The tool must be run as an administrator who has access to the local store.</span></span>

### <a name="examples"></a><span data-ttu-id="3a522-497">Esempi</span><span class="sxs-lookup"><span data-stu-id="3a522-497">Examples</span></span>

<span data-ttu-id="3a522-498">Di seguito è riportato un esempio di input dello strumento.</span><span class="sxs-lookup"><span data-stu-id="3a522-498">The following is an example of the tool input.</span></span>

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="3a522-499">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="3a522-499">Summary</span></span>

<span data-ttu-id="3a522-500">Questo strumento può essere una risorsa preziosa per gli amministratori di Skype for Business Server 2015 che vogliono controllare lo stato dei server in cui sono in uso servizi per i criteri di larghezza di banda e audio/video.</span><span class="sxs-lookup"><span data-stu-id="3a522-500">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

## <a name="network-configuration-viewer"></a><span data-ttu-id="3a522-501">Visualizzatore Configurazione di rete</span><span class="sxs-lookup"><span data-stu-id="3a522-501">Network Configuration Viewer</span></span>
<span data-ttu-id="3a522-502"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="3a522-502"><a name="NCV"> </a></span></span>

<span data-ttu-id="3a522-503">Il Visualizzatore di configurazione di rete può essere usato dagli amministratori del software di comunicazione di Skype for Business Server 2015 per visualizzare la topologia di rete di controllo di ammissione di chiamata (CAC) per un'organizzazione che ha eseguito il provisioning per consentire sessioni di comunicazione in tempo reale, ad esempio chiamate vocali o video in base alla capacità di larghezza di banda specificata.</span><span class="sxs-lookup"><span data-stu-id="3a522-503">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="3a522-504">Gli amministratori di Skype for Business Server 2015 definiscono i criteri di CAC, applicati dai servizi per i criteri di larghezza di banda installati con Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-504">Skype for Business Server 2015 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>

### <a name="description"></a><span data-ttu-id="3a522-505">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a522-505">Description</span></span>

<span data-ttu-id="3a522-506">Network Configuration Viewer (NetworkConfigurationViewer. exe) consente agli amministratori di eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a522-506">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

- <span data-ttu-id="3a522-507">Caricare e visualizzare la topologia di rete CAC da una distribuzione di Skype for Business Server 2015 in formato grafico.</span><span class="sxs-lookup"><span data-stu-id="3a522-507">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>

- <span data-ttu-id="3a522-508">Caricare e visualizzare la topologia di rete CAC da un file di log del server dei criteri di larghezza di banda in formato grafico.</span><span class="sxs-lookup"><span data-stu-id="3a522-508">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

- <span data-ttu-id="3a522-509">Salvare e archiviare la topologia di rete CAC in un formato XML sul disco.</span><span class="sxs-lookup"><span data-stu-id="3a522-509">Save and store CAC network topology in an XML format on the disk.</span></span>

- <span data-ttu-id="3a522-510">Salvare e archiviare il diagramma della topologia di rete CAC in formato JPG o BMP.</span><span class="sxs-lookup"><span data-stu-id="3a522-510">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

- <span data-ttu-id="3a522-511">Visualizzare i dati di configurazione della topologia di rete CAC.</span><span class="sxs-lookup"><span data-stu-id="3a522-511">View CAC network topology configuration data.</span></span>

- <span data-ttu-id="3a522-512">Visualizzare la topologia di rete CAC in uno stile di visualizzazione albero.</span><span class="sxs-lookup"><span data-stu-id="3a522-512">View CAC network topology in a tree-view style.</span></span>

- <span data-ttu-id="3a522-513">Definire connettori personalizzati per i collegamenti alla topologia di rete CAC, ad esempio i collegamenti da sito a area geografica, da area geografica e da sito a sito.</span><span class="sxs-lookup"><span data-stu-id="3a522-513">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

- <span data-ttu-id="3a522-514">Visualizzare le informazioni sul sito della topologia di rete CAC, le informazioni sulle aree geografiche e i collegamenti di rete con provisioning.</span><span class="sxs-lookup"><span data-stu-id="3a522-514">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

### <a name="purpose"></a><span data-ttu-id="3a522-515">Scopo</span><span class="sxs-lookup"><span data-stu-id="3a522-515">Purpose</span></span>

<span data-ttu-id="3a522-516">Visualizzare i collegamenti della topologia di rete Enterprise CAC in un'interfaccia grafica.</span><span class="sxs-lookup"><span data-stu-id="3a522-516">View enterprise CAC network topology links in a graphical interface.</span></span>

### <a name="examples"></a><span data-ttu-id="3a522-517">Esempi</span><span class="sxs-lookup"><span data-stu-id="3a522-517">Examples</span></span>

 <span data-ttu-id="3a522-518">**Caricare e visualizzare la topologia di rete CAC da una distribuzione di Skype for Business server 2015 in un formato grafico**: gli amministratori di Skype for business server 2015 possono caricare e visualizzare la configurazione della topologia di rete di CAC in qualsiasi computer Skype for business server 2015 usando l'opzione di **configurazione della rete download** , come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="3a522-518">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="3a522-519">Lo strumento non riesce a scaricare o visualizzare tale configurazione quando viene distribuita in un computer che non ha connettività con lo Store di configurazione di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-519">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>

![Download della configurazione di rete.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 <span data-ttu-id="3a522-521">**Caricare e visualizzare la topologia di rete CAC da un file di log del server dei criteri di larghezza di banda in formato grafico:** I server dei criteri di larghezza di banda di Skype for Business Server 2015 salvano la topologia di rete CAC come parte del meccanismo di registrazione nella posizione di condivisione file di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-521">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="3a522-522">Skype for Business Server 2015 gli amministratori possono visualizzare un file in formato grafico usando l'opzione di **configurazione della rete aperta** , come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3a522-522">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

![Apertura di un file di log del server criteri larghezza di banda.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

<span data-ttu-id="3a522-524">Salvare e archiviare la topologia di rete CAC in un formato XML sul disco: Skype for Business Server 2015 gli amministratori possono salvare il file di configurazione della topologia di rete CAC in un formato XML usando l'opzione **Salva una copia di configurazione di rete** , come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3a522-524">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="3a522-525">Il file di configurazione salvato può quindi essere usato offline per scopi di visualizzazione grafica.</span><span class="sxs-lookup"><span data-stu-id="3a522-525">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

![Salvataggio della configurazione di rete come file XML.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

<span data-ttu-id="3a522-527">Salvare e archiviare il diagramma della topologia di rete in formato JPG o BMP: Skype for Business Server 2015 gli amministratori possono salvare la configurazione della topologia di rete CAC in un formato grafico (formati di file JPG e BMP) usando l'opzione **Salva diagramma configurazione di rete come immagine** come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3a522-527">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

![Salvataggio della configurazione di rete come immagine.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <span data-ttu-id="3a522-529"><strong>Visualizzare i dati di configurazione della topologia di rete CAC:</strong> Skype for Business Server 2015 gli amministratori possono visualizzare i dati di configurazione della rete correlati, ad esempio aree di rete, siti di rete, profili di larghezza di banda e indirizzi IP della subnet del sito in un formato testuale usando l'opzione Visualizza dati di configurazione della rete come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3a522-529"><strong>View CAC network topology configuration data:</strong>Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

![Visualizzazione dei dati sulla configurazione di rete.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 <span data-ttu-id="3a522-531">**Visualizzare la topologia di rete CAC in uno stile di visualizzazione ad albero:** Skype for Business Server 2015 gli amministratori possono visualizzare i dati di configurazione della rete correlati in uno stile di visualizzazione ad albero grafico usando il pannello di controllo sul lato sinistro della finestra degli strumenti, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3a522-531">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

![Visualizzazione dei dati sulla configurazione di rete in una visualizzazione ad albero.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 <span data-ttu-id="3a522-533">**Definire connettori personalizzati per i collegamenti alla topologia di rete CAC, ad esempio i collegamenti da sito a area** geografica, dall'area geografica e da sito a sito: Skype for Business Server 2015 gli amministratori possono definire connettori grafici personalizzati per i collegamenti WAN della configurazione di rete CAC usando l'opzione impostazioni come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3a522-533">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="3a522-534">Questo consente di distinguere tra i vari tipi di collegamenti di rete che vengono provisionati nella configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="3a522-534">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

![Strumenti](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 <span data-ttu-id="3a522-536">**Visualizzare informazioni sul sito della topologia di rete CAC, informazioni sulle aree geografiche e criteri di larghezza di banda provisioning:** Gli amministratori di Skype for Business Server 2015 possono visualizzare informazioni relative all'area di rete CAC correlate, informazioni sul sito e informazioni sul provisioning della larghezza di banda di CAC usando le opzioni illustrate di seguito.</span><span class="sxs-lookup"><span data-stu-id="3a522-536">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="3a522-537">Ad esempio, fare clic su **informazioni** in un'area di rete o in un oggetto sito di rete.</span><span class="sxs-lookup"><span data-stu-id="3a522-537">(For example, click **Info** in a network region or network site object.)</span></span>

![Definizione di connettori personalizzati per la rete.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a><span data-ttu-id="3a522-539">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="3a522-539">Summary</span></span>

<span data-ttu-id="3a522-540">Questo strumento può essere una risorsa preziosa per gli amministratori di Skype for Business Server 2015 che desiderano visualizzare la topologia di rete CAC per la distribuzione in un formato grafico.</span><span class="sxs-lookup"><span data-stu-id="3a522-540">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

## <a name="response-group-agent-live"></a><span data-ttu-id="3a522-541">Agente di Response Group Live</span><span class="sxs-lookup"><span data-stu-id="3a522-541">Response Group Agent Live</span></span>
<span data-ttu-id="3a522-542"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="3a522-542"><a name="RGAL"> </a></span></span>

<span data-ttu-id="3a522-543">L'applicazione Response Group offre agli agenti la possibilità di accedere a informazioni in tempo reale utili usando il servizio Web incorporato.</span><span class="sxs-lookup"><span data-stu-id="3a522-543">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="3a522-544">Sfortunatamente, nessuna visualizzazione grafica di questi dati è disponibile all'esterno dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3a522-544">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="3a522-545">Lo strumento Response Group Agent Live Resource Kit risolve questo problema fornendo un modo semplice e grafico per accedere a queste informazioni, migliorate con le informazioni del software Skype for Business Communications in tempo reale, come la presenza di altri agenti.</span><span class="sxs-lookup"><span data-stu-id="3a522-545">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>

### <a name="description"></a><span data-ttu-id="3a522-546">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a522-546">Description</span></span>

<span data-ttu-id="3a522-547">Response Group Agent Live è un'applicazione Windows che fornisce funzionalità di accesso e disconnessione e alcune informazioni in tempo reale, ad esempio l'appartenenza al gruppo e il numero corrente di chiamate, agli agenti del gruppo di risposta.</span><span class="sxs-lookup"><span data-stu-id="3a522-547">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="3a522-548">Si tratta di una versione avanzata della pagina gruppi di agenti (accessibile da Skype for business.</span><span class="sxs-lookup"><span data-stu-id="3a522-548">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>

### <a name="purpose"></a><span data-ttu-id="3a522-549">Scopo</span><span class="sxs-lookup"><span data-stu-id="3a522-549">Purpose</span></span>

<span data-ttu-id="3a522-550">L'applicazione Response Group Accoda le chiamate in arrivo e le instrada ai gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="3a522-550">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="3a522-551">Per prendere decisioni informate sulle chiamate al servizio, gli agenti possono accedere a informazioni in tempo reale sui gruppi di agenti, ad esempio gli altri agenti disponibili e il numero di chiamate in attesa in ogni coda.</span><span class="sxs-lookup"><span data-stu-id="3a522-551">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="3a522-552">Queste informazioni, inizialmente accessibili solo tramite il servizio Response Group, vengono messe a disposizione in modo intuitivo dall'agente di Response Group Live.</span><span class="sxs-lookup"><span data-stu-id="3a522-552">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

#### <a name="features"></a><span data-ttu-id="3a522-553">Caratteristiche</span><span class="sxs-lookup"><span data-stu-id="3a522-553">Features</span></span>

<span data-ttu-id="3a522-554">Lo strumento di Response Group Agent Live è basato sul servizio Response Group e su Skype for Business Server 2015 SDK.</span><span class="sxs-lookup"><span data-stu-id="3a522-554">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="3a522-555">Fornisce agli agenti del gruppo di risposta le informazioni e le funzionalità disponibili nel servizio Response Group, ad esempio l'appartenenza ai gruppi, la presenza di altri agenti e il numero di chiamate in attesa.</span><span class="sxs-lookup"><span data-stu-id="3a522-555">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="3a522-556">La figura seguente illustra l'interfaccia principale di Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="3a522-556">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

![Strumento Response Group Agent Live.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

<span data-ttu-id="3a522-558">Le tre caratteristiche principali seguenti sono disponibili per gli agenti in Response Group Agent Live:</span><span class="sxs-lookup"><span data-stu-id="3a522-558">The following three main features are available for agents in Response Group Agent Live:</span></span>

- <span data-ttu-id="3a522-559">**Accesso/uscita:** Contrariamente alla pagina gruppi di agenti (accessibile da Skype for Business Server 2015), Response Group Agent Live consente solo agli agenti di accedere o disconnettersi da tutti i gruppi di agenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="3a522-559">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="3a522-560">Questa applicazione offre tre modi rapidi per l'accesso o la disconnessione degli agenti:</span><span class="sxs-lookup"><span data-stu-id="3a522-560">This application provides three quick ways for agents to sign in or out:</span></span>

  - <span data-ttu-id="3a522-561">Fare clic sui pulsanti di accesso/uscita (verde e rosso) all'interno dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3a522-561">Click the Sign-in/out (green and red) buttons within the application.</span></span>

  - <span data-ttu-id="3a522-562">Fare clic con il pulsante destro del mouse sull'icona della barra di sistema e scegliere Accedi o Disconnetti.</span><span class="sxs-lookup"><span data-stu-id="3a522-562">Right-click the system tray icon, and select sign in or sign out.</span></span>

  - <span data-ttu-id="3a522-563">Uso delle scelte rapide da tastiera configurabili.</span><span class="sxs-lookup"><span data-stu-id="3a522-563">Using configurable keyboard shortcuts.</span></span>

- <span data-ttu-id="3a522-564">**Appartenenza al gruppo:** Quando viene selezionato un gruppo di agenti, il gruppo di risposte in Live Visualizza l'elenco di agenti in questo gruppo nel riquadro destro.</span><span class="sxs-lookup"><span data-stu-id="3a522-564">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="3a522-565">Se Skype for Business Server 2015 è in uso nello stesso computer di questa applicazione, le informazioni sulla presenza e la scheda contatto vengono visualizzate nell'agente di Response Group Live.</span><span class="sxs-lookup"><span data-stu-id="3a522-565">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="3a522-566">Gli agenti possono inviare un messaggio istantaneo o chiamare altri agenti direttamente da lì.</span><span class="sxs-lookup"><span data-stu-id="3a522-566">Agents can send an IM or call other agents directly from there.</span></span>

- <span data-ttu-id="3a522-567">**Statistiche in tempo reale:** Response Group Agent Live offre statistiche in tempo reale per tutti i gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="3a522-567">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="3a522-568">La frequenza di aggiornamento è di un minuto.</span><span class="sxs-lookup"><span data-stu-id="3a522-568">The update frequency is one minute.</span></span> <span data-ttu-id="3a522-569">Quando una chiamata viene risolta da un gruppo di risposte, accanto al nome del gruppo viene aggiunto un indicatore visivo con il numero corrente di chiamate in coda.</span><span class="sxs-lookup"><span data-stu-id="3a522-569">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="3a522-570">Se si sospende il puntatore del mouse su un gruppo, viene visualizzato anche il tempo di attesa più lungo.</span><span class="sxs-lookup"><span data-stu-id="3a522-570">Pausing the pointer over a group also displays the longest waiting time.</span></span>

### <a name="requirements"></a><span data-ttu-id="3a522-571">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a522-571">Requirements</span></span>

<span data-ttu-id="3a522-572">L'agente di Response Group Live richiede .NET Framework 4,0.</span><span class="sxs-lookup"><span data-stu-id="3a522-572">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="3a522-573">Inoltre, per sfruttare le caratteristiche della presenza e della scheda contatto, Skype for business deve essere installato localmente (ed essere in funzione).</span><span class="sxs-lookup"><span data-stu-id="3a522-573">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>

#### <a name="configuration"></a><span data-ttu-id="3a522-574">Configurazione</span><span class="sxs-lookup"><span data-stu-id="3a522-574">Configuration</span></span>

<span data-ttu-id="3a522-575">Response Group Agent Live può essere personalizzato per le singole preferenze usando la finestra di dialogo Opzioni nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3a522-575">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="3a522-576">Inoltre, l'amministratore può definire l'indirizzo host predefinito modificando direttamente la proprietà defaultHostAddress del file RGAgentLive. exe. config.</span><span class="sxs-lookup"><span data-stu-id="3a522-576">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="3a522-577">Nella figura seguente è illustrata la finestra di dialogo Opzioni che gli agenti possono usare per configurare l'indirizzo host e i tasti di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="3a522-577">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="3a522-578">Per accedere a questa finestra di dialogo, fare clic sul pulsante Opzioni nell'angolo in alto a destra dell'interfaccia principale.</span><span class="sxs-lookup"><span data-stu-id="3a522-578">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

![Finestra di dialogo Options di Response Group Agent Live.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

<span data-ttu-id="3a522-580">Le tre diverse impostazioni seguenti possono essere personalizzate nella configurazione Live dell'agente di Response Group:</span><span class="sxs-lookup"><span data-stu-id="3a522-580">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

- <span data-ttu-id="3a522-581">Indirizzo host: in genere è il nome di dominio completo del pool Web che appartiene al pool di Home dell'agente.</span><span class="sxs-lookup"><span data-stu-id="3a522-581">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="3a522-582">L'indirizzo esatto del servizio Response Group viene automaticamente derivato in background da queste informazioni (accodando il percorso corretto dopo l'host).</span><span class="sxs-lookup"><span data-stu-id="3a522-582">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

- <span data-ttu-id="3a522-583">Scelte rapide: i collegamenti esatti per l'accesso/uscita possono essere personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3a522-583">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="3a522-584">L'unica limitazione è che entrambi i tasti di scelta rapida devono contenere la chiave "Windows logo" (oltre ad almeno un altro tasto).</span><span class="sxs-lookup"><span data-stu-id="3a522-584">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>

- <span data-ttu-id="3a522-585">Iniziare con Windows: l'applicazione può essere configurata per l'avvio automatico con Windows.</span><span class="sxs-lookup"><span data-stu-id="3a522-585">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

### <a name="examples"></a><span data-ttu-id="3a522-586">Esempi</span><span class="sxs-lookup"><span data-stu-id="3a522-586">Examples</span></span>

<span data-ttu-id="3a522-587">La figura seguente illustra come chiamare o inviare un messaggio istantaneo a un altro agente facendo clic con il pulsante destro del mouse sul contatto nel riquadro destro.</span><span class="sxs-lookup"><span data-stu-id="3a522-587">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

![Esecuzione di una chiamata o invio di un messaggio istantaneo.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

<span data-ttu-id="3a522-589">Nella figura seguente viene illustrato il modo in cui l'agente di Response Group Live Visualizza il numero corrente di chiamate nella coda e il tempo di attesa più lungo tra tutte le chiamate in arrivo.</span><span class="sxs-lookup"><span data-stu-id="3a522-589">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

![Visualizzazione di informazioni sulla coda.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a><span data-ttu-id="3a522-591">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="3a522-591">Summary</span></span>

<span data-ttu-id="3a522-592">L'accesso rapido e la disconnessione, l'appartenenza ai gruppi e le statistiche di base in tempo reale sono interessanti funzionalità dell'agente di Response Group che sono disponibili solo all'esterno dell'applicazione dal servizio Response Group.</span><span class="sxs-lookup"><span data-stu-id="3a522-592">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="3a522-593">Con lo strumento Response Group Agent Live Resource Kit, gli amministratori di Skype for Business Server 2015 possono consentire agli agenti di usare un'applicazione Windows che consente loro di eseguire attività in modo più rapido e grafico.</span><span class="sxs-lookup"><span data-stu-id="3a522-593">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

## <a name="sefautil"></a><span data-ttu-id="3a522-594">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="3a522-594">SEFAUtil</span></span>
<span data-ttu-id="3a522-595"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="3a522-595"><a name="SEFAUtil"> </a></span></span>

<span data-ttu-id="3a522-596">SEFAUtil (attivazione delle funzionalità di estensione secondaria) è uno strumento della riga di comando che consente agli amministratori del software di comunicazione di Skype for Business Server 2015 e agli agenti dell'helpdesk di configurare le chiamate Delegate, l'inoltro di chiamata, lo squillo simultaneo impostazioni di chiamata del team e raccolta di chiamate di gruppo per conto di un utente di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-596">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="3a522-597">Lo strumento consente inoltre agli amministratori di eseguire query sulle impostazioni di routing delle chiamate pubblicate per un determinato utente. Lo strumento SEFAUtil consente all'amministratore di abilitare/disabilitare/modificare l'inoltro di chiamata o di squillare contemporaneamente per conto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3a522-597">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="3a522-598">L'amministratore può specificare la destinazione (sotto forma di URI SIP) o usare una destinazione già pubblicata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="3a522-598">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="3a522-599">Questo strumento consente inoltre agli amministratori di aggiungere o rimuovere delegati o membri del gruppo di chiamate del team per conto dell'utente. Questo strumento è basato su Microsoft Unified Communications Managed API (UCMA) 3,0 e richiede che gli amministratori creino un'applicazione attendibile nell'Central Management store per SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="3a522-599">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>

<span data-ttu-id="3a522-600">SEFAUtil (attivazione delle funzionalità di estensione secondaria) consente agli amministratori e agli agenti di helpdesk di Skype for Business Server 2015 di configurare le chiamate Delegate, l'inoltro di chiamata, lo squillo simultaneo, le impostazioni di chiamata del team e il ritiro delle chiamate di gruppo per conto di Skype per gli utenti di Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-600">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="3a522-601">Questo strumento consente inoltre agli amministratori di eseguire query sulle impostazioni di routing delle chiamate pubblicate per un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="3a522-601">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

### <a name="description"></a><span data-ttu-id="3a522-602">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a522-602">Description</span></span>

<span data-ttu-id="3a522-603">La versione corrente di SEFAUtil è solo uno strumento della riga di comando. non è disponibile un'interfaccia utente grafica di supporto.</span><span class="sxs-lookup"><span data-stu-id="3a522-603">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="3a522-604">Questo strumento è basato su Microsoft Unified Communications Managed API (UCMA) 3,0.</span><span class="sxs-lookup"><span data-stu-id="3a522-604">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="3a522-605">Le funzionalità di questo strumento consentono agli amministratori e agli agenti helpdesk di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a522-605">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

- <span data-ttu-id="3a522-606">Visualizzare tutte le impostazioni di routing delle chiamate per un utente (include l'inoltro di chiamata, la delega, lo squillo simultaneo, la chiamata in team e il pick-up di gruppo)</span><span class="sxs-lookup"><span data-stu-id="3a522-606">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

- <span data-ttu-id="3a522-607">Abilitare/disabilitare/modificare l'impostazione di inoltro di chiamata (include la destinazione e il timer senza risposta)</span><span class="sxs-lookup"><span data-stu-id="3a522-607">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

- <span data-ttu-id="3a522-608">Abilitare/disabilitare/modificare le configurazioni immediate dell'inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="3a522-608">Enable/disable/modify call-forwarding immediate configurations</span></span>

- <span data-ttu-id="3a522-609">Abilitare/disabilitare/modificare le impostazioni di delega</span><span class="sxs-lookup"><span data-stu-id="3a522-609">Enable/disable/modify delegation settings</span></span>

- <span data-ttu-id="3a522-610">Abilitare/disabilitare/modificare le impostazioni del gruppo di chiamate team</span><span class="sxs-lookup"><span data-stu-id="3a522-610">Enable/disable/modify team-call group settings</span></span>

    > [!NOTE]
    > <span data-ttu-id="3a522-611">Nuovo strumento di SEFAUtil di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3a522-611">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="3a522-612">Abilitare/disabilitare/modificare le impostazioni di chiamata simultanea (include la destinazione)</span><span class="sxs-lookup"><span data-stu-id="3a522-612">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>

    > [!NOTE]
    > <span data-ttu-id="3a522-613">Nuovo strumento di SEFAUtil di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3a522-613">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="3a522-614">Abilitare/disabilitare/modificare le impostazioni di raccolta delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="3a522-614">Enable/disable/modify group call pickup settings</span></span>

    > [!CAUTION]
    > <span data-ttu-id="3a522-615">Nuovo strumento di SEFAUtil di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3a522-615">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

<span data-ttu-id="3a522-616">Questo strumento presenta le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a522-616">This tool has the following limitations:</span></span>

- <span data-ttu-id="3a522-617">Supportato solo per gli utenti ospitati in un pool di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3a522-617">Supported only for users homed in a Skype for Business Server pool</span></span>

- <span data-ttu-id="3a522-618">La modifica in blocco delle impostazioni di routing delle chiamate per diversi utenti non è supportata</span><span class="sxs-lookup"><span data-stu-id="3a522-618">Bulk-edit of call routing settings for several users is not supported</span></span>

### <a name="output"></a><span data-ttu-id="3a522-619">Output</span><span class="sxs-lookup"><span data-stu-id="3a522-619">Output</span></span>

<span data-ttu-id="3a522-620">La versione corrente di questo strumento fornisce l'output solo nella finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="3a522-620">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="3a522-621">Per informazioni dettagliate, vedere la sezione esempi più avanti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="3a522-621">For details, see the Examples section later in this document.</span></span>

### <a name="purpose"></a><span data-ttu-id="3a522-622">Scopo</span><span class="sxs-lookup"><span data-stu-id="3a522-622">Purpose</span></span>

<span data-ttu-id="3a522-623">Di seguito sono riportati alcuni degli scenari principali in cui può essere usato questo strumento:</span><span class="sxs-lookup"><span data-stu-id="3a522-623">Following are some of the key scenarios where this tool may be used:</span></span>

- <span data-ttu-id="3a522-624">Roberto è un dirigente ed è stato spostato in Skype for Business Server per la telefonia.</span><span class="sxs-lookup"><span data-stu-id="3a522-624">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="3a522-625">Ha delegazioni nel sistema PBX esistente.</span><span class="sxs-lookup"><span data-stu-id="3a522-625">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="3a522-626">Come parte del passaggio a Skype for Business Server 2015, l'amministratore è in grado di configurare il routing di Roberto per riflettere la configurazione di delega preesistente.</span><span class="sxs-lookup"><span data-stu-id="3a522-626">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>

- <span data-ttu-id="3a522-627">Alice è in viaggio e si rende conto che si aspetta una chiamata importante da uno dei suoi clienti.</span><span class="sxs-lookup"><span data-stu-id="3a522-627">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="3a522-628">Tuttavia, si trova in un hotel e non ha accesso a un computer.</span><span class="sxs-lookup"><span data-stu-id="3a522-628">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="3a522-629">Chiama l'helpdesk e chiede di inoltrare al numero di cellulare tutte le chiamate effettuate al suo numero di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3a522-629">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="3a522-630">Il personale dell'helpdesk è in grado di eseguire la configurazione per suo conto.</span><span class="sxs-lookup"><span data-stu-id="3a522-630">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

- <span data-ttu-id="3a522-631">Le chiamate di Joe al suo numero di lavoro andranno alla segreteria telefonica per dispositivi mobili ogni volta che è al lavoro; Tuttavia, le cose sembrano funzionare correttamente nella maggior parte degli altri percorsi.</span><span class="sxs-lookup"><span data-stu-id="3a522-631">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="3a522-632">Il tecnico dell'helpdesk è in grado di visualizzare la configurazione di routing di Joe e rileva che Joe ha squillato simultaneamente configurato per il cellulare.</span><span class="sxs-lookup"><span data-stu-id="3a522-632">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="3a522-633">Il tecnico chiede a Joe della copertura per dispositivi mobili presso il suo ufficio ed è in grado di determinare che la regola di chiamata simultanea è ciò che causa le chiamate per accedere alla segreteria telefonica di Joe quando la sua copertura di rete è scadente.</span><span class="sxs-lookup"><span data-stu-id="3a522-633">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>

- <span data-ttu-id="3a522-634">Mike è un nuovo dipendente di Contoso e si unisce a un nuovo team in cui tutti i membri sono configurati per la chiamata del team, quando viene abilitato per Skype for Business Server 2015, l'amministratore è in grado di impostare le impostazioni del gruppo di chiamate del team per includere tutti i nuovi membri del team l'amministratore aggiunge inoltre Mike come membro del gruppo di chiamate team per ognuno dei membri del team.</span><span class="sxs-lookup"><span data-stu-id="3a522-634">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

- <span data-ttu-id="3a522-635">Una pratica di servizio al cliente nel reparto risorse umane di Contoso consiste nel prestare un servizio personalizzato per tutti i chiamanti dopo la prima chiamata.</span><span class="sxs-lookup"><span data-stu-id="3a522-635">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="3a522-636">Considerato che tutti i membri del dipartimento si siedono molto vicini l'uno all'altro, è molto fastidioso per il team avere tutti i telefoni che squillano contemporaneamente alla chiamata del team.</span><span class="sxs-lookup"><span data-stu-id="3a522-636">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="3a522-637">Per garantire un servizio ottimale senza interrompere i membri del team, l'amministratore di Skype for Business Server 2015 sfrutta la funzionalità di raccolta delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="3a522-637">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="3a522-638">L'amministratore aggiunge tutti i membri del reparto a un gruppo di raccolta e comunica al reparto il numero del gruppo di pick-up.</span><span class="sxs-lookup"><span data-stu-id="3a522-638">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="3a522-639">Quando Samantha è assente dalla sua scrivania, Joe nota che squilla il telefono e procede a rispondere alla chiamata dalla sua scrivania.</span><span class="sxs-lookup"><span data-stu-id="3a522-639">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

### <a name="requirements"></a><span data-ttu-id="3a522-640">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a522-640">Requirements</span></span>

<span data-ttu-id="3a522-641">Lo strumento SEFAUtil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibile.</span><span class="sxs-lookup"><span data-stu-id="3a522-641">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="3a522-642">UCMA 3,0 deve essere installato nel computer in cui si trova.</span><span class="sxs-lookup"><span data-stu-id="3a522-642">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="3a522-643">Per eseguire lo strumento, è necessario creare una nuova applicazione attendibile con l'ID applicazione SEFAUtil in tale pool.</span><span class="sxs-lookup"><span data-stu-id="3a522-643">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="3a522-644">Creazione di una nuova applicazione attendibile per lo strumento SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="3a522-644">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="3a522-645">Lo strumento SEFAUTil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibile.</span><span class="sxs-lookup"><span data-stu-id="3a522-645">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="3a522-646">Se necessario, l'aggiunta di un pool come nuovo pool di applicazioni attendibili può essere eseguita tramite Skype for Business Server Management Shell con il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="3a522-646">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > <span data-ttu-id="3a522-647">UCMA 3,0 deve essere installato in qualsiasi computer che verrà usato per eseguire lo strumento SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="3a522-647">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

2. <span data-ttu-id="3a522-648">Un'applicazione attendibile deve essere definita nella topologia dello strumento SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="3a522-648">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="3a522-649">Per definire SEFAUtil come nuova applicazione attendibile, usare Skype for Business Server Management Shell ed eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="3a522-649">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="3a522-650">Se necessario, è possibile usare una porta diversa.</span><span class="sxs-lookup"><span data-stu-id="3a522-650">A different port can be used if needed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3a522-651">FQDN del pool: il nome di dominio completo del server o del pool che ospiterà l'applicazione SEFAUtil (in genere un server front-end di Skype for business > o pool).</span><span class="sxs-lookup"><span data-stu-id="3a522-651">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server     > or pool).</span></span>
    > <span data-ttu-id="3a522-652">FQDN del registrar del pool: il nome di dominio completo del server front end o del pool di Skype for business associato al pool di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="3a522-652">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="3a522-653">Sito del pool: ID sito del sito in cui è ospitato questo pool.</span><span class="sxs-lookup"><span data-stu-id="3a522-653">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

3. <span data-ttu-id="3a522-654">Le modifiche della topologia devono essere abilitate.</span><span class="sxs-lookup"><span data-stu-id="3a522-654">The topology changes need to be enabled.</span></span> <span data-ttu-id="3a522-655">L'attivazione delle modifiche della topologia può essere eseguita tramite Skype for Business Server Management Shell eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="3a522-655">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span>

   ```powershell
   Enable-CsToplogy
   ```

4. <span data-ttu-id="3a522-656">Se necessario, installare gli strumenti di Skype for Business Server 2015 Resource Kit nel server che verrà usato per eseguire lo strumento SEFAUtil (il server deve far parte di un pool di applicazioni attendibili).</span><span class="sxs-lookup"><span data-stu-id="3a522-656">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5. <span data-ttu-id="3a522-657">Verificare che SEFAUtil sia in corso correttamente.</span><span class="sxs-lookup"><span data-stu-id="3a522-657">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="3a522-658">A questo scopo, Esegui lo strumento da un prompt dei comandi di Windows con privilegi di amministratore per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3a522-658">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="3a522-659">Per impostazione predefinita, lo strumento si trova in: ". ..\Program Skype for Business Server 2015 \ reskit".</span><span class="sxs-lookup"><span data-stu-id="3a522-659">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="3a522-660">Per visualizzare le impostazioni di inoltro di chiamata di un utente, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="3a522-660">To display the call forwarding settings of a user, use the following command:</span></span>

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    <span data-ttu-id="3a522-661">Devono essere visualizzate le impostazioni di inoltro di chiamata dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3a522-661">The call forwarding settings of the user should be displayed.</span></span>

#### <a name="group-call-pickup"></a><span data-ttu-id="3a522-662">Risposta alle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="3a522-662">Group Call Pickup</span></span>

<span data-ttu-id="3a522-663">Il pick-up per le chiamate di gruppo richiede una configurazione aggiuntiva in Skype for Business Server 2015 per consentire la completa abilitazione della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="3a522-663">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="3a522-664">Prima di assegnare gruppi di prelievo agli utenti, vedere la documentazione del prodotto pick-up per la pianificazione e la distribuzione di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="3a522-664">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

### <a name="examples"></a><span data-ttu-id="3a522-665">Esempi</span><span class="sxs-lookup"><span data-stu-id="3a522-665">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="3a522-666">Visualizzare le impostazioni di gestione delle chiamate correnti</span><span class="sxs-lookup"><span data-stu-id="3a522-666">Display Current Call Handling Settings</span></span>

<span data-ttu-id="3a522-667">Il comando seguente Visualizza la gestione delle chiamate per l'utente.</span><span class="sxs-lookup"><span data-stu-id="3a522-667">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> <span data-ttu-id="3a522-668">Questo esempio usa l'opzione **/Server** per specificare il server Skype for business a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="3a522-668">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>

 <span data-ttu-id="3a522-669">**Output**</span><span class="sxs-lookup"><span data-stu-id="3a522-669">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="3a522-670">Impostare la destinazione di chiamata inoltra/nessuna risposta</span><span class="sxs-lookup"><span data-stu-id="3a522-670">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="3a522-671">Questo esempio imposta la destinazione per la chiamata in avanti/nessuna risposta e il ritardo della suoneria.</span><span class="sxs-lookup"><span data-stu-id="3a522-671">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="3a522-672">In questo caso, l'opzione/server non è disponibile; SEFAUtil tenta di individuare l'individuazione automatica di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-672">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 <span data-ttu-id="3a522-673">**Output**</span><span class="sxs-lookup"><span data-stu-id="3a522-673">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="3a522-674">Abilitare l'inoltro di chiamata immediatamente</span><span class="sxs-lookup"><span data-stu-id="3a522-674">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="3a522-675">Questo esempio consente immediatamente l'inoltro di chiamata a un altro utente.</span><span class="sxs-lookup"><span data-stu-id="3a522-675">This example immediately enables call-forwarding to another user.</span></span>

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="3a522-676">**Output**</span><span class="sxs-lookup"><span data-stu-id="3a522-676">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="3a522-677">Disabilitare immediatamente l'inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="3a522-677">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="3a522-678">Questo esempio disattiva immediatamente l'inoltro di chiamata.</span><span class="sxs-lookup"><span data-stu-id="3a522-678">This example immediately disables call forwarding.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
```

 <span data-ttu-id="3a522-679">**Output**</span><span class="sxs-lookup"><span data-stu-id="3a522-679">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="3a522-680">Aggiungere un utente come delegato e configurare lo squillo simultaneo dei delegati</span><span class="sxs-lookup"><span data-stu-id="3a522-680">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="3a522-681">In questo esempio viene aggiunto un utente come delegato e viene impostata la chiamata simultanea dei delegati.</span><span class="sxs-lookup"><span data-stu-id="3a522-681">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="3a522-682">**Output**</span><span class="sxs-lookup"><span data-stu-id="3a522-682">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="3a522-683">Modificare la regola di chiamata simultanea dei delegati</span><span class="sxs-lookup"><span data-stu-id="3a522-683">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="3a522-684">Questo esempio modifica la regola di chiamata simultanea impostata nell'esempio precedente sulla regola di chiamata in ritardo.</span><span class="sxs-lookup"><span data-stu-id="3a522-684">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="3a522-685">**Output**</span><span class="sxs-lookup"><span data-stu-id="3a522-685">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="3a522-686">Rimuovere il delegato</span><span class="sxs-lookup"><span data-stu-id="3a522-686">Remove the Delegate</span></span>

<span data-ttu-id="3a522-687">In questo esempio viene rimosso il delegato.</span><span class="sxs-lookup"><span data-stu-id="3a522-687">This example removes the delegate.</span></span>

> [!NOTE]
> <span data-ttu-id="3a522-688">Quando l'ultimo delegato viene rimosso, il delegare squilla viene disabilitato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3a522-688">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="3a522-689">**Output**</span><span class="sxs-lookup"><span data-stu-id="3a522-689">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="3a522-690">Aggiungere un delegato e configurare la regola di inoltro di chiamata a delegati</span><span class="sxs-lookup"><span data-stu-id="3a522-690">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="3a522-691">In questo esempio viene aggiunto un delegato e viene impostata la regola inoltro di chiamata a delegati.</span><span class="sxs-lookup"><span data-stu-id="3a522-691">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="3a522-692">**Output**</span><span class="sxs-lookup"><span data-stu-id="3a522-692">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="3a522-693">Abilitare la chiamata simultanea e impostare un numero di destinazione</span><span class="sxs-lookup"><span data-stu-id="3a522-693">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="3a522-694">Questo esempio Abilita la chiamata simultanea e imposta un numero di destinazione squillante simultaneo.</span><span class="sxs-lookup"><span data-stu-id="3a522-694">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="3a522-695">Per cambiare il numero di destinazione squillo simultaneo di un utente che ha già attivato la chiamata simultanea, Mantieni il comando con l'opzione/enablesimulring, altrimenti il numero di destinazione non verrà modificato.</span><span class="sxs-lookup"><span data-stu-id="3a522-695">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>

 <span data-ttu-id="3a522-696">**Output**</span><span class="sxs-lookup"><span data-stu-id="3a522-696">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="3a522-697">Disabilitare lo squillo simultaneo</span><span class="sxs-lookup"><span data-stu-id="3a522-697">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="3a522-698">Questo esempio disabilita la chiamata simultanea.</span><span class="sxs-lookup"><span data-stu-id="3a522-698">This example disables simultaneous ringing.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="3a522-699">**Output**</span><span class="sxs-lookup"><span data-stu-id="3a522-699">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="3a522-700">Aggiungere un membro del team per la chiamata al team e configurare lo squillo simultaneo al gruppo membri della chiamata del team</span><span class="sxs-lookup"><span data-stu-id="3a522-700">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="3a522-701">Questo esempio aggiunge un membro del team al gruppo di chiamate team di un utente e consente la chiamata simultanea al gruppo di chiamate del team.</span><span class="sxs-lookup"><span data-stu-id="3a522-701">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="3a522-702">L'aggiunta di un membro al gruppo di chiamata del team di un utente cambia automaticamente il settigs di chiamata simultanea degli utenti per simulring il gruppo di chiamate del team.</span><span class="sxs-lookup"><span data-stu-id="3a522-702">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>

 <span data-ttu-id="3a522-703">**Output**</span><span class="sxs-lookup"><span data-stu-id="3a522-703">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="3a522-704">Rimuovere un membro dal gruppo di chiamate team</span><span class="sxs-lookup"><span data-stu-id="3a522-704">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="3a522-705">Questo esempio rimuove un membro del team del gruppo di chiamate team di un utente.</span><span class="sxs-lookup"><span data-stu-id="3a522-705">This example removes a team member of the team-call group of a user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="3a522-706">Se il membro da rimuovere è l'unico membro del gruppo di chiamate del team, lo squillo simultaneo al gruppo di chiamate del team verrà disabilitato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3a522-706">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>

 <span data-ttu-id="3a522-707">**Output**</span><span class="sxs-lookup"><span data-stu-id="3a522-707">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="3a522-708">Impostare l'anello ritardato sul gruppo di chiamate team</span><span class="sxs-lookup"><span data-stu-id="3a522-708">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="3a522-709">Questo esempio cambia l'intervallo di tempo in ritardo con l'impostazione dell'ora del gruppo di chiamate team.</span><span class="sxs-lookup"><span data-stu-id="3a522-709">This example changes the delayed ring to the team-call group time setting.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="3a522-710">**Output**</span><span class="sxs-lookup"><span data-stu-id="3a522-710">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="3a522-711">Abilitare la chiamata del team</span><span class="sxs-lookup"><span data-stu-id="3a522-711">Enable Team-Call</span></span>

<span data-ttu-id="3a522-712">Questo esempio consente di abilitare la chiamata al team per un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="3a522-712">This example enables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="3a522-713">Se il gruppo di chiamata del team dell'utente non ha membri, la chiamata del team non verrà abilitata.</span><span class="sxs-lookup"><span data-stu-id="3a522-713">If the team-call group of the user has no members, team-call won't be enabled.</span></span>

 <span data-ttu-id="3a522-714">**Output**</span><span class="sxs-lookup"><span data-stu-id="3a522-714">**Output**</span></span>

#### <a name="disable-team-call"></a><span data-ttu-id="3a522-715">Disabilitare la chiamata del team</span><span class="sxs-lookup"><span data-stu-id="3a522-715">Disable Team-Call</span></span>

<span data-ttu-id="3a522-716">Questo esempio disabilita la chiamata del team per un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="3a522-716">This example disables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="3a522-717">**Output**</span><span class="sxs-lookup"><span data-stu-id="3a522-717">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="3a522-718">Abilitare il ritiro delle chiamate di gruppo e assegnare un gruppo di raccolta a un utente</span><span class="sxs-lookup"><span data-stu-id="3a522-718">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="3a522-719">In questo esempio viene assegnato un gruppo di prelievo a un utente e viene abilitato il ritiro delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="3a522-719">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="3a522-720">**Output**</span><span class="sxs-lookup"><span data-stu-id="3a522-720">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="3a522-721">Disabilitare il ritiro delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="3a522-721">Disable Group Call Pickup</span></span>

<span data-ttu-id="3a522-722">In questo esempio viene disabilitato il ritiro delle chiamate di gruppo per un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="3a522-722">This example disables Group Call Pickup for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="3a522-723">Quando si disattiva il prelievo delle chiamate di gruppo per un utente, il numero di gruppo assegnato all'utente non viene mantenuto.</span><span class="sxs-lookup"><span data-stu-id="3a522-723">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="3a522-724">Se in seguito si vuole riabilitare il ritiro delle chiamate di gruppo per l'utente, è necessario assegnare di nuovo il numero di gruppo con l'opzione/enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="3a522-724">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="3a522-725">SYSPrep. ps1</span><span class="sxs-lookup"><span data-stu-id="3a522-725">SYSPrep.ps1</span></span>
<span data-ttu-id="3a522-726"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="3a522-726"><a name="SYSPrep"> </a></span></span>

### <a name="description"></a><span data-ttu-id="3a522-727">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a522-727">Description</span></span>

<span data-ttu-id="3a522-728">SYSPrep. ps1 è uno script di Windows PowerShell che installerà i prerequisiti di Skype for Business Server 2015 seguenti nel computer del sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="3a522-728">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>

- <span data-ttu-id="3a522-729">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="3a522-729">Microsoft .Net Framework 4.5</span></span>

- <span data-ttu-id="3a522-730">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="3a522-730">Microsoft SQL Server Express</span></span>

- <span data-ttu-id="3a522-731">Versione 3,0 di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a522-731">Windows Powershell version 3.0</span></span>

- <span data-ttu-id="3a522-732">Visual C++ 2010 ridistribuibile</span><span class="sxs-lookup"><span data-stu-id="3a522-732">Visual C++ 2010 Redistributable</span></span>

- <span data-ttu-id="3a522-733">Aggiornamenti di Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="3a522-733">Internet Information Server Updates</span></span>

- <span data-ttu-id="3a522-734">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="3a522-734">Windows Identity Foundation</span></span>

- <span data-ttu-id="3a522-735">File di base di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3a522-735">Skype for Business Server 2015 Core files</span></span>

  <span data-ttu-id="3a522-736">Mentre il nome dello script è simile allo strumento di preparazione del sistema per i sistemi operativi Microsoft Windows, sono diversi.</span><span class="sxs-lookup"><span data-stu-id="3a522-736">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="3a522-737">Questo script installerà solo i prerequisiti necessari per Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-737">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="3a522-738">Dopo aver installato questi prerequisiti, lo strumento SYSPrep di Windows può quindi essere usato per creare un'immagine del server.</span><span class="sxs-lookup"><span data-stu-id="3a522-738">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

### <a name="requirements"></a><span data-ttu-id="3a522-739">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a522-739">Requirements</span></span>

<span data-ttu-id="3a522-740">Prima di eseguire lo script SYSPrep. ps1, è necessario copiare i file dei prerequisiti in una cartella locale nel computer del sistema operativo Windows Server 2008, ad esempio **D:\setup**.</span><span class="sxs-lookup"><span data-stu-id="3a522-740">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="3a522-741">Questa cartella deve includere anche una copia dei file di 2015 di Skype for Business Server, in particolare **Setup. exe.**</span><span class="sxs-lookup"><span data-stu-id="3a522-741">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="3a522-742">I file dei prerequisiti possono essere scaricati dai percorsi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a522-742">The prerequisite files can be downloaded from the following locations:</span></span>


| <span data-ttu-id="3a522-743">**Prerequisiti**</span><span class="sxs-lookup"><span data-stu-id="3a522-743">**Prerequisite**</span></span>                                | <span data-ttu-id="3a522-744">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="3a522-744">**Location**</span></span>                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| <span data-ttu-id="3a522-745">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="3a522-745">Microsoft .Net Framework 4.5</span></span>  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| <span data-ttu-id="3a522-746">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="3a522-746">Microsoft SQL Server Express 2008 R2</span></span>  <br/>     | <https://www.microsoft.com/en-us/download/details.aspx?id=23650>  <br/> |
| <span data-ttu-id="3a522-747">Versione 3,0 di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a522-747">Windows Powershell version 3.0</span></span>  <br/>           | <https://www.microsoft.com/en-us/download/details.aspx?id=34595>  <br/> |
| <span data-ttu-id="3a522-748">Visual C++ 2010 ridistribuibile</span><span class="sxs-lookup"><span data-stu-id="3a522-748">Visual C++ 2010 Redistributable</span></span>  <br/>          | <https://www.microsoft.com/en-us/download/details.aspx?id=5555>  <br/>  |
| <span data-ttu-id="3a522-749">Aggiornamenti di Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="3a522-749">Internet Information Server Updates</span></span>  <br/>      | <https://www.microsoft.com/en-us/download/details.aspx?id=34869>  <br/> |
| <span data-ttu-id="3a522-750">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="3a522-750">Windows Identity Foundation</span></span>  <br/>              | <https://www.microsoft.com/en-us/download/details.aspx?id=17331>  <br/> |
| <span data-ttu-id="3a522-751">Skype for Business Server 2015 Setup. exe</span><span class="sxs-lookup"><span data-stu-id="3a522-751">Skype for Business Server 2015 Setup.exe</span></span>  <br/> | <span data-ttu-id="3a522-752">Copia da Skype for Business Server 2015 media</span><span class="sxs-lookup"><span data-stu-id="3a522-752">Copy from Skype for Business Server 2015 media</span></span>  <br/>                   |

### <a name="parameter"></a><span data-ttu-id="3a522-753">Parametro</span><span class="sxs-lookup"><span data-stu-id="3a522-753">Parameter</span></span>

<span data-ttu-id="3a522-754">Il parametro **-SetupFolder** accetta come argomento la posizione della directory dei file di prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3a522-754">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

### <a name="examples"></a><span data-ttu-id="3a522-755">Esempi</span><span class="sxs-lookup"><span data-stu-id="3a522-755">Examples</span></span>

<span data-ttu-id="3a522-756">Per eseguire lo script SYSPrep. ps1 e installare i prerequisiti di Skype for Business Server 2015, eseguire il comando seguente da un prompt dei comandi con privilegi elevati:</span><span class="sxs-lookup"><span data-stu-id="3a522-756">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="3a522-757">Migrazione degli annunci di numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="3a522-757">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="3a522-758"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="3a522-758"><a name="UNAM"> </a></span></span>

<span data-ttu-id="3a522-759">Lo strumento di migrazione annunci numeri non assegnati consente a un amministratore di Skype for Business Server 2015 di trasferire la configurazione dei numeri non assegnati serviti dall'applicazione di annuncio da un server o pool Skype for business di origine a un destinazione Skype for Business Server o pool.</span><span class="sxs-lookup"><span data-stu-id="3a522-759">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>

### <a name="description"></a><span data-ttu-id="3a522-760">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a522-760">Description</span></span>

<span data-ttu-id="3a522-761">Lo strumento di migrazione annunci numeri non assegnati è uno script di Windows PowerShell che sposta la configurazione dei numeri non assegnati serviti dall'applicazione di annuncio di un server o pool di origine a un altro server o pool.</span><span class="sxs-lookup"><span data-stu-id="3a522-761">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="3a522-762">Quando viene eseguita, lo script di migrazione degli annunci di numeri non assegnati esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a522-762">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1. <span data-ttu-id="3a522-763">Consente di trasferire tutti i file audio usati dagli annunci di numeri non assegnati dell'applicazione di annunci ospitati nel server di origine o nel pool nell'archivio file del server o del pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3a522-763">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3a522-764">I file audio vengono rimossi dal pool di origine dopo essere stati copiati nel pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3a522-764">The audio files are removed from the source pool once they're copied to the destination pool.</span></span>

2. <span data-ttu-id="3a522-765">Consente di trasferire tutti gli annunci di numeri non assegnati configurati per l'applicazione di annuncio ospitata nel server o nel pool di origine nel server o nel pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3a522-765">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3. <span data-ttu-id="3a522-766">Riassegnare tutti gli intervalli di numeri non assegnati serviti dall'applicazione di annuncio ospitata nel server di origine o nel pool al server o al pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3a522-766">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="3a522-767">Dopo aver eseguito correttamente lo script, tutti gli intervalli di numeri non assegnati serviti dall'applicazione di annuncio ospitata nel server di origine o nel pool verranno ora serviti con la stessa configurazione dal server o dal pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3a522-767">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

### <a name="output"></a><span data-ttu-id="3a522-768">Output</span><span class="sxs-lookup"><span data-stu-id="3a522-768">Output</span></span>

<span data-ttu-id="3a522-769">Lo script **Move-CsAnnouncementConfiguration** indica nella finestra di gestione di Skype for Business Server in cui è stato eseguito l'esito positivo o negativo dell'operazione di migrazione.</span><span class="sxs-lookup"><span data-stu-id="3a522-769">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="3a522-770">Se l'esecuzione dell'operazione viene interrotta da qualsiasi errore, gli intervalli di numeri non assegnati spostati correttamente nella destinazione rimarranno nella destinazione in una maschera operativa e il resto degli intervalli di numeri non assegnati di cui eseguire la migrazione rimarrà in anche l'origine in una maschera operativa.</span><span class="sxs-lookup"><span data-stu-id="3a522-770">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="3a522-771">Per eseguire la migrazione completa del resto della configurazione, rieseguire lo script dopo avere indirizzato l'errore.</span><span class="sxs-lookup"><span data-stu-id="3a522-771">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

### <a name="purpose"></a><span data-ttu-id="3a522-772">Scopo</span><span class="sxs-lookup"><span data-stu-id="3a522-772">Purpose</span></span>

<span data-ttu-id="3a522-773">Lo script di migrazione annunci numero non assegnati può essere usato nei tre scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a522-773">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

- <span data-ttu-id="3a522-774">**Migrazione delle impostazioni di configurazione a una nuova versione di Skype for Business Server:** Contoso sta eseguendo la migrazione a Skype for Business Server 2015 e durante il processo di migrazione l'amministratore di Skype for Business Server desidera trasferire la configurazione dei numeri non assegnati serviti dall'applicazione di annuncio dalla distribuzione di Lync Server 2013 alla nuova distribuzione di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-774">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="3a522-775">Per cambiare le impostazioni di configurazione, l'amministratore di Skype for Business Server usa lo strumento di migrazione annunci numero non assegnati.</span><span class="sxs-lookup"><span data-stu-id="3a522-775">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

- <span data-ttu-id="3a522-776">**Rollback di una distribuzione da Skype for Business Server 2015 a Lync server 2013:** A causa di fattori imprevisti, Contoso deve eseguire il rollback della migrazione alla nuova distribuzione di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a522-776">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="3a522-777">Per ridurre al minimo le interruzioni del servizio, l'amministratore di Skype for Business Server usa lo strumento di migrazione annunci numero non assegnati per eseguire il rollback della configurazione dalla distribuzione di Skype for Business Server 2015 alla distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a522-777">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>

- <span data-ttu-id="3a522-778">**Spostamento di dati tra distribuzioni:** Contoso sta sostituendo tutti i server di un pool con server più recenti.</span><span class="sxs-lookup"><span data-stu-id="3a522-778">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="3a522-779">La loro strategia consiste nel distribuire un nuovo pool di Skype for Business Server 2015, trasferire tutti i dati dal vecchio al nuovo pool e quindi deprecare il vecchio pool.</span><span class="sxs-lookup"><span data-stu-id="3a522-779">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="3a522-780">Dopo la distribuzione del nuovo pool, viene usato lo strumento di migrazione annunci numeri non assegnati per trasferire la configurazione dal pool precedente a quello nuovo.</span><span class="sxs-lookup"><span data-stu-id="3a522-780">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

#### <a name="requirements"></a><span data-ttu-id="3a522-781">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a522-781">Requirements</span></span>

<span data-ttu-id="3a522-782">Di seguito sono riportati i requisiti principali necessari per eseguire correttamente lo strumento:</span><span class="sxs-lookup"><span data-stu-id="3a522-782">The following are the main requirements needed to successfully run the tool:</span></span>

1. <span data-ttu-id="3a522-783">Lo script deve essere eseguito da un computer in cui è installato Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3a522-783">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>

2. <span data-ttu-id="3a522-784">L'applicazione di annuncio deve essere distribuita correttamente nei server o nei pool di Skype for business di origine e di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3a522-784">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>

#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="3a522-785">Script Move-CsAnnouncementConfiguration</span><span class="sxs-lookup"><span data-stu-id="3a522-785">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="3a522-786">Lo script Move-CsAnnouncementConfiguration richiede i due parametri descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3a522-786">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

![Parametri di Move-CsAnnouncementConfiguration.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a><span data-ttu-id="3a522-788">Esempi</span><span class="sxs-lookup"><span data-stu-id="3a522-788">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="3a522-789">Spostamento della configurazione degli annunci di numeri non assegnati da un pool di Lync Server 2013 a un pool di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3a522-789">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="3a522-790">Questo esempio sposta gli annunci del numero non assegnati dal pool di origine (Lync Server 2013) nel pool di destinazione (Skype for Business Server 2015).</span><span class="sxs-lookup"><span data-stu-id="3a522-790">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="3a522-791">Spostamento della configurazione degli annunci di numeri non assegnati da un pool di Skype for Business Server 2015 a un pool di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a522-791">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="3a522-792">Questo esempio sposta gli annunci del numero non assegnati dal pool di origine (Skype for Business Server 2015) nel pool di destinazione (Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="3a522-792">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="3a522-793">Dati Web conf</span><span class="sxs-lookup"><span data-stu-id="3a522-793">Web Conf Data</span></span>
<span data-ttu-id="3a522-794"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="3a522-794"><a name="WebConfData"> </a></span></span>

<span data-ttu-id="3a522-795">Lo strumento di dati Web conf consente a un amministratore del software di comunicazione di Skype for Business Server 2015 di avere un maggiore controllo sui dati associati alle conferenze Web di un organizzatore.</span><span class="sxs-lookup"><span data-stu-id="3a522-795">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="3a522-796">Gli scenari includono la possibilità di eliminare i dati di una riunione di un utente specifico in base a un criterio di timestamp.</span><span class="sxs-lookup"><span data-stu-id="3a522-796">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>

### <a name="description"></a><span data-ttu-id="3a522-797">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a522-797">Description</span></span>

<span data-ttu-id="3a522-798">Questo strumento consente all'amministratore di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a522-798">This tool allows the administrator to perform the following operations:</span></span>

1. <span data-ttu-id="3a522-799">Trovare tutti i dati di Web Conferencing associati a un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="3a522-799">Find all Web conferencing data associated with a single user.</span></span>

2. <span data-ttu-id="3a522-800">Eliminare tutti i dati di Web Conferencing associati a un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="3a522-800">Delete all Web conferencing data associated with a single user.</span></span>

3. <span data-ttu-id="3a522-801">Eliminare tutti i dati di Web Conferencing associati a un singolo utente antecedente a una determinata data.</span><span class="sxs-lookup"><span data-stu-id="3a522-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4. <span data-ttu-id="3a522-802">Spostare tutti i dati di Web Conferencing associati a un singolo utente quando l'utente viene spostato da un pool a un altro.</span><span class="sxs-lookup"><span data-stu-id="3a522-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3a522-803">Gli strumenti del Resource Kit per Lync Server 2010 supportano lo spostamento di tutti i dati di Web Conferencing associati a un singolo utente quando l'utente viene spostato da un pool a un altro.</span><span class="sxs-lookup"><span data-stu-id="3a522-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="3a522-804">Questa funzionalità è ora deprecata da questo strumento a favore del parametro **MoveConferenceData** .</span><span class="sxs-lookup"><span data-stu-id="3a522-804">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="3a522-805">Per informazioni dettagliate su questo parametro, vedere il cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="3a522-805">For details about this parameter, see the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="3a522-806">Lo strumento Elimina i dati delle riunioni solo per le riunioni inattive.</span><span class="sxs-lookup"><span data-stu-id="3a522-806">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="3a522-807">Le riunioni attive (o le riunioni in sessioni) non possono essere eliminate.</span><span class="sxs-lookup"><span data-stu-id="3a522-807">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="3a522-808">Questo strumento deve essere eseguito da un computer che si trova nello stesso pool dell'utente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3a522-808">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="3a522-809">L'utente i cui dati del contenuto della riunione vengono gestiti da questo strumento deve essere ospitato nello stesso pool di utenti.</span><span class="sxs-lookup"><span data-stu-id="3a522-809">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

### <a name="output"></a><span data-ttu-id="3a522-810">Output</span><span class="sxs-lookup"><span data-stu-id="3a522-810">Output</span></span>

<span data-ttu-id="3a522-811">Questo strumento restituisce i risultati di ogni operazione:</span><span class="sxs-lookup"><span data-stu-id="3a522-811">This tool outputs the results of each of the operations:</span></span>

- <span data-ttu-id="3a522-812">Se viene eseguita una query, lo strumento restituisce l'elenco di tutte le cartelle di dati della riunione inattive che hanno l'utente come organizzatore.</span><span class="sxs-lookup"><span data-stu-id="3a522-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

- <span data-ttu-id="3a522-813">Se viene eseguita un'eliminazione, lo strumento restituisce l'elenco di tutte le cartelle di dati della riunione i cui dati verranno eliminati.</span><span class="sxs-lookup"><span data-stu-id="3a522-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

### <a name="requirements"></a><span data-ttu-id="3a522-814">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a522-814">Requirements</span></span>

<span data-ttu-id="3a522-815">Lo strumento deve essere eseguito nello stesso pool in cui è attualmente ospitato l'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="3a522-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="3a522-816">Lo strumento deve essere eseguito usando i privilegi di amministratore con l'accesso all'archivio di file di contenuto.</span><span class="sxs-lookup"><span data-stu-id="3a522-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

### <a name="examples"></a><span data-ttu-id="3a522-817">Esempi</span><span class="sxs-lookup"><span data-stu-id="3a522-817">Examples</span></span>

<span data-ttu-id="3a522-818">La tabella seguente descrive i parametri, alcuni dei quali vengono usati negli esempi.</span><span class="sxs-lookup"><span data-stu-id="3a522-818">The following table describes the parameters, some of which are used in the examples.</span></span>

![Parametri dello strumento Web Conf Data.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="3a522-820">Nell'esempio precedente viene illustrato il funzionamento di un comando di query.</span><span class="sxs-lookup"><span data-stu-id="3a522-820">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="3a522-821">L'output di un comando di questo tipo è un elenco di tutte le cartelle del contenuto della riunione interessate da questo strumento.</span><span class="sxs-lookup"><span data-stu-id="3a522-821">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="3a522-822">Il precedente è un esempio di comando Elimina.</span><span class="sxs-lookup"><span data-stu-id="3a522-822">The preceding is an example of a delete command.</span></span> <span data-ttu-id="3a522-823">Il comando Elimina consente di rimuovere tutte le cartelle riunione inattiva da questo utente.</span><span class="sxs-lookup"><span data-stu-id="3a522-823">The delete command will remove all inactive meeting folders from this user.</span></span>

### <a name="summary"></a><span data-ttu-id="3a522-824">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="3a522-824">Summary</span></span>

<span data-ttu-id="3a522-825">Questo strumento può essere una risorsa preziosa per gli amministratori che hanno bisogno di un controllo più preciso sui dati della riunione di conferenza.</span><span class="sxs-lookup"><span data-stu-id="3a522-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>


