---
title: Documentazione degli strumenti di Skype for Business Server 2015 Resource Kit
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
description: In questo argomento vengono descritti gli strumenti del Resource Kit di Skype for Business Server 2015, incluso lo scopo di ogni strumento ed esempi del suo utilizzo. Skype for Business Server 2015 Resource Kit consente di semplificare le attività di routine per gli amministratori IT che distribuiscono e gestiscono Skype for Business Server 2015. Ad esempio, lo strumento Web Conf Data può essere utilizzato per controllare facilmente i dati caricati dagli utenti durante una riunione online. Lo strumento SEFAUtil può essere utilizzato per configurare l'inoltro di chiamata delegato e la risposta per gli utenti. Incoraggiamo gli amministratori IT a usare questi strumenti per gestire in modo più efficace Skype for Business Server 2015.
ms.openlocfilehash: c09aa7c21e90a1783c0819a0877ecb87ff250d16
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114082"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="0d931-107">Documentazione degli strumenti di Skype for Business Server 2015 Resource Kit</span><span class="sxs-lookup"><span data-stu-id="0d931-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>

<span data-ttu-id="0d931-108">In questo argomento vengono descritti gli strumenti del Resource Kit di Skype for Business Server 2015, incluso lo scopo di ogni strumento ed esempi del suo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="0d931-108">This topic describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="0d931-109">Skype for Business Server 2015 Resource Kit consente di semplificare le attività di routine per gli amministratori IT che distribuiscono e gestiscono Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="0d931-110">Ad esempio, lo **strumento Web Conf Data** può essere utilizzato per controllare facilmente i dati caricati dagli utenti durante una riunione online.</span><span class="sxs-lookup"><span data-stu-id="0d931-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="0d931-111">Lo **strumento SEFAUtil** può essere utilizzato per configurare l'inoltro di chiamata delegato e la risposta per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="0d931-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="0d931-112">Incoraggiamo gli amministratori IT a usare questi strumenti per gestire in modo più efficace Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="0d931-113">Installazione degli strumenti del Resource Kit</span><span class="sxs-lookup"><span data-stu-id="0d931-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="0d931-114">Per installare Skype for Business Server 2015 Resource Kit, [ scaricare ](https://www.microsoft.com/download/details.aspx?id=52631)OCSReskit.msidall'Area download.</span><span class="sxs-lookup"><span data-stu-id="0d931-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) from the Download Center.</span></span>

<span data-ttu-id="0d931-115">Eseguire **OCSResKit.msi** per eseguire un'installazione semplice.</span><span class="sxs-lookup"><span data-stu-id="0d931-115">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="0d931-116">Con estensione msi vengono installati tutti gli strumenti nel percorso seguente: **%Programmi%\Skype for Business Server 2015\ResKit**.</span><span class="sxs-lookup"><span data-stu-id="0d931-116">The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**.</span></span> <span data-ttu-id="0d931-117">Gli strumenti che sono eseguibili autonomi si possono trovare in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="0d931-117">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="0d931-118">Gli strumenti che dispongono anche di file di supporto sono nelle proprie sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="0d931-118">Tools that also have supporting files are in their own subfolders.</span></span>

## <a name="supported-environments"></a><span data-ttu-id="0d931-119">Ambienti supportati</span><span class="sxs-lookup"><span data-stu-id="0d931-119">Supported Environments</span></span>

<span data-ttu-id="0d931-120">Skype for Business Server 2015 Resource Kit deve essere installato in un server che soddisfi le specifiche richieste per Skype for Business Server 2015, in genere uno utilizzato per eseguire Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="0d931-121">Panoramica degli strumenti del Resource Kit</span><span class="sxs-lookup"><span data-stu-id="0d931-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="0d931-122">Di seguito è riportato un elenco degli strumenti disponibili in Skype for Business Server 2015 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="0d931-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="0d931-123">Nelle sezioni seguenti viene illustrata una descrizione di ogni strumento, inclusi i requisiti e l'utilizzo di esempio.</span><span class="sxs-lookup"><span data-stu-id="0d931-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>

- [<span data-ttu-id="0d931-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="0d931-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)

- [<span data-ttu-id="0d931-125">Monitoraggio servizio criteri larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="0d931-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)

- [<span data-ttu-id="0d931-126">Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="0d931-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)

- [<span data-ttu-id="0d931-127">Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="0d931-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)

- [<span data-ttu-id="0d931-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="0d931-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)

- [<span data-ttu-id="0d931-129">Importare i dati del servizio di archiviazione</span><span class="sxs-lookup"><span data-stu-id="0d931-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)

- [<span data-ttu-id="0d931-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="0d931-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)

- [<span data-ttu-id="0d931-131">Console utente di ricerca</span><span class="sxs-lookup"><span data-stu-id="0d931-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)

- [<span data-ttu-id="0d931-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="0d931-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)

- [<span data-ttu-id="0d931-133">Visualizzatore configurazione di rete</span><span class="sxs-lookup"><span data-stu-id="0d931-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)

- [<span data-ttu-id="0d931-134">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="0d931-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)

- [<span data-ttu-id="0d931-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="0d931-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)

- [<span data-ttu-id="0d931-136">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="0d931-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)

- [<span data-ttu-id="0d931-137">Migrazione degli annunci di numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="0d931-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)

- [<span data-ttu-id="0d931-138">Dati web conf</span><span class="sxs-lookup"><span data-stu-id="0d931-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a><span data-ttu-id="0d931-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="0d931-139">ABSConfig</span></span>
<span data-ttu-id="0d931-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="0d931-140"><a name="ABSConfig"> </a></span></span>

<span data-ttu-id="0d931-141">Lo strumento di configurazione del servizio Rubrica (ABSConfig) è uno strumento amministrativo che consente agli amministratori di personalizzare la configurazione del servizio Rubrica in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="0d931-142">Questo strumento consente inoltre agli amministratori di Skype for Business Server 2015 di ripristinare le impostazioni predefinite del servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="0d931-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>

### <a name="description"></a><span data-ttu-id="0d931-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d931-143">Description</span></span>

<span data-ttu-id="0d931-144">ABSConfig è un'applicazione dell'interfaccia utente grafica che consente agli amministratori di configurare gli attributi di Servizi di dominio Active Directory correlati al servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="0d931-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="0d931-145">Gli scenari principali per lo strumento sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-145">The primary scenarios for the tool are the following:</span></span>

- <span data-ttu-id="0d931-146">Per consentire agli amministratori di mappare gli attributi in Servizi di dominio Active Directory agli attributi per Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>

- <span data-ttu-id="0d931-147">Per consentire agli amministratori di specificare l'attributo Servizi di dominio Active Directory da includere o escludere nei file del servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="0d931-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

- <span data-ttu-id="0d931-148">Per consentire agli amministratori di ripristinare le impostazioni predefinite del servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="0d931-148">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="0d931-149">Lo strumento ABSConfig può essere avviato utilizzando il file ABSConfig.exe file.</span><span class="sxs-lookup"><span data-stu-id="0d931-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="0d931-150">Lo strumento viene aperto nella **scheda Configura** attributi. In questa tabella sono disponibili opzioni per mappare gli attributi di Servizi di dominio Active Directory ai campi attributo per Skype for Business Server 2015 e per specificare quali utenti includere o escludere nei file del servizio Rubrica in base a filtri di attributo specifici.</span><span class="sxs-lookup"><span data-stu-id="0d931-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="0d931-151">Sono inoltre disponibili opzioni per personalizzare il valore del numero di telefono da includere nel file della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="0d931-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="0d931-152">**L'opzione Ripristina valori predefiniti** consente agli amministratori di ripristinare i valori predefiniti delle impostazioni del servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="0d931-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

> [!NOTE]
> <span data-ttu-id="0d931-153">Il re-mapping degli attributi di Ad a nomi di campo OC diversi funziona solo per il download di file della Rubrica e non è supportato da Address Book Web Query.</span><span class="sxs-lookup"><span data-stu-id="0d931-153">Re-mapping of AD attributes to different OC Field Names will only work for Address Book File Download, and is not supported by Address Book Web Query.</span></span>

### <a name="output"></a><span data-ttu-id="0d931-154">Output</span><span class="sxs-lookup"><span data-stu-id="0d931-154">Output</span></span>

<span data-ttu-id="0d931-155">ABSConfig archivia la configurazione del servizio Rubrica nel database.</span><span class="sxs-lookup"><span data-stu-id="0d931-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="0d931-156">Scopo</span><span class="sxs-lookup"><span data-stu-id="0d931-156">Purpose</span></span>

<span data-ttu-id="0d931-157">ABSConfig offre un modo semplice e rapido per personalizzare il servizio Rubrica di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-157">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>

### <a name="requirements"></a><span data-ttu-id="0d931-158">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d931-158">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="0d931-159">Computer</span><span class="sxs-lookup"><span data-stu-id="0d931-159">Computer</span></span>

<span data-ttu-id="0d931-160">ABSConfig può essere eseguito solo da un computer aggiunto a un dominio in cui è installato Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-160">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="0d931-161">Nel caso di Skype for Business Server 2015, Enterprise Edition, questo strumento può essere eseguito su qualsiasi Front End Server in cui è abilitato il servizio Rubrica durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="0d931-161">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

#### <a name="network"></a><span data-ttu-id="0d931-162">Rete</span><span class="sxs-lookup"><span data-stu-id="0d931-162">Network</span></span>

<span data-ttu-id="0d931-163">Il computer dovrebbe essere in grado di connettersi al pool Front End e al database back-end.</span><span class="sxs-lookup"><span data-stu-id="0d931-163">The computer should be able to connect to the Front End pool and back-end database.</span></span>

#### <a name="software"></a><span data-ttu-id="0d931-164">Software</span><span class="sxs-lookup"><span data-stu-id="0d931-164">Software</span></span>

<span data-ttu-id="0d931-165">Prima di eseguire lo strumento ABSConfig, è necessario installare i componenti software seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-165">The following software components must be installed before running the ABSConfig tool:</span></span>

- <span data-ttu-id="0d931-166">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0d931-166">Skype for Business Server 2015</span></span>

#### <a name="users"></a><span data-ttu-id="0d931-167">Utenti</span><span class="sxs-lookup"><span data-stu-id="0d931-167">Users</span></span>

<span data-ttu-id="0d931-168">Amministratori che dispongono delle autorizzazioni necessarie per aggiornare la distribuzione di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-168">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>

### <a name="examples"></a><span data-ttu-id="0d931-169">Esempi</span><span class="sxs-lookup"><span data-stu-id="0d931-169">Examples</span></span>

<span data-ttu-id="0d931-170">ABSConfig può essere avviato digitando **ABSConfig.exe** al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="0d931-170">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="0d931-171">Di seguito è illustrata l'interfaccia utente dello strumento ABSConfig.</span><span class="sxs-lookup"><span data-stu-id="0d931-171">Shown below is the ABSConfig tool user interface.</span></span>

![Lo ABSConfig.exe.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a><span data-ttu-id="0d931-173">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="0d931-173">Summary</span></span>

<span data-ttu-id="0d931-174">Lo strumento ABSConfig fornisce agli amministratori uno strumento rapido e facile da usare per personalizzare il servizio Rubrica di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="0d931-175">Monitoraggio servizio criteri larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="0d931-175">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="0d931-176"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="0d931-176"><a name="bpsm"> </a></span></span>

<span data-ttu-id="0d931-177">Lo strumento Monitoraggio servizio criteri di larghezza di banda ha lo scopo di consentire agli amministratori di visualizzare un elenco degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-177">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1. <span data-ttu-id="0d931-178">Tutti i servizi dei criteri di larghezza di banda di Skype for Business Server 2015 configurati (autenticazione e core) nella topologia</span><span class="sxs-lookup"><span data-stu-id="0d931-178">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2. <span data-ttu-id="0d931-179">Le connessioni che ogni servizio effettua ad altri servizi di criteri di larghezza di banda e ai server perimetrali</span><span class="sxs-lookup"><span data-stu-id="0d931-179">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3. <span data-ttu-id="0d931-180">Tutti i collegamenti configurati nel documento di configurazione di rete e l'utilizzo della larghezza di banda in tempo reale, come riportato da ognuno dei servizi dei criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="0d931-180">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

### <a name="description"></a><span data-ttu-id="0d931-181">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d931-181">Description</span></span>

<span data-ttu-id="0d931-182">Lo strumento Monitoraggio servizio criteri di larghezza di banda viene implementato come applicazione basata su GUI.</span><span class="sxs-lookup"><span data-stu-id="0d931-182">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="0d931-183">Gli amministratori avviano lo strumento eseguendo PDPMonUI.exe.</span><span class="sxs-lookup"><span data-stu-id="0d931-183">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="0d931-184">All'avvio dello strumento, tenta di individuare l'elenco dei servizi dei criteri di larghezza di banda nella topologia.</span><span class="sxs-lookup"><span data-stu-id="0d931-184">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="0d931-185">Al termine dell'aggiornamento iniziale, il riquadro a sinistra della finestra viene popolato con un elenco di servizi raggruppati in base ai cluster a cui appartengono.</span><span class="sxs-lookup"><span data-stu-id="0d931-185">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="0d931-186">Quando gli amministratori selezionano un particolare servizio di criteri di larghezza di banda, nel riquadro a destra vengono visualizzate le informazioni su quel particolare servizio.</span><span class="sxs-lookup"><span data-stu-id="0d931-186">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="0d931-187">In tale riquadro sono inoltre disponibili due schede principali che visualizzano informazioni.</span><span class="sxs-lookup"><span data-stu-id="0d931-187">That pane also has two main tabs that display information.</span></span>

#### <a name="machine-info-tab"></a><span data-ttu-id="0d931-188">Scheda Informazioni computer</span><span class="sxs-lookup"><span data-stu-id="0d931-188">Machine Info Tab</span></span>

<span data-ttu-id="0d931-189">Nella **scheda Informazioni computer** vengono visualizzati i dettagli del servizio criteri larghezza di banda selezionato e l'elenco e lo stato di tutte le connessioni effettuate dal servizio criteri di larghezza di banda selezionato ad altri servizi.</span><span class="sxs-lookup"><span data-stu-id="0d931-189">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

#### <a name="topology-info-tab"></a><span data-ttu-id="0d931-190">Scheda Informazioni topologia</span><span class="sxs-lookup"><span data-stu-id="0d931-190">Topology Info Tab</span></span>

<span data-ttu-id="0d931-191">Nella **scheda Informazioni topologia** viene visualizzato un elenco di tutti i collegamenti configurati nelle impostazioni di configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="0d931-191">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="0d931-192">Per ogni collegamento viene visualizzata la capacità della larghezza di banda audio e video.</span><span class="sxs-lookup"><span data-stu-id="0d931-192">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="0d931-193">Viene inoltre visualizzata la larghezza di banda attualmente utilizzata, sia in Kbps che come percentuale della capacità.</span><span class="sxs-lookup"><span data-stu-id="0d931-193">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="0d931-194">Lo strumento utilizza la codifica a colori per evidenziare i collegamenti con un utilizzo vicino alla capacità, in modo da consentire agli amministratori di isolare rapidamente tali collegamenti.</span><span class="sxs-lookup"><span data-stu-id="0d931-194">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

> [!NOTE]
>  <span data-ttu-id="0d931-195">Se lo strumento Monitoraggio servizio criteri di larghezza di banda si verifica un  errore quando  si connette a uno dei servizi criteri di larghezza di banda configurati, le informazioni nelle schede Informazioni computer e Informazioni topologia non verranno popolate.</span><span class="sxs-lookup"><span data-stu-id="0d931-195">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="0d931-196">Tuttavia, è possibile che lo strumento inizialmente si connetta ma successivamente perda la connessione al servizio.</span><span class="sxs-lookup"><span data-stu-id="0d931-196">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="0d931-197">In questi casi, gli amministratori potrebbero visualizzare informazioni obsolete.</span><span class="sxs-lookup"><span data-stu-id="0d931-197">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="0d931-198">In ognuna delle schede è presente un timestamp Last **Updated** che consente agli amministratori di visualizzare l'ultimo aggiornamento dei dati per un particolare servizio criteri larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="0d931-198">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>

### <a name="output"></a><span data-ttu-id="0d931-199">Output</span><span class="sxs-lookup"><span data-stu-id="0d931-199">Output</span></span>

<span data-ttu-id="0d931-200">Non è disponibile alcun output della riga di comando. l'output del programma è contenuto nell'interfaccia utente grafica (GUI) principale.</span><span class="sxs-lookup"><span data-stu-id="0d931-200">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

### <a name="purpose"></a><span data-ttu-id="0d931-201">Scopo</span><span class="sxs-lookup"><span data-stu-id="0d931-201">Purpose</span></span>

<span data-ttu-id="0d931-202">Lo scopo dello strumento Monitoraggio servizio criteri di larghezza di banda è consentire agli amministratori di visualizzare lo stato di ognuno dei servizi dei criteri di larghezza di banda definiti nella topologia.</span><span class="sxs-lookup"><span data-stu-id="0d931-202">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="0d931-203">Inoltre, gli amministratori possono visualizzare l'utilizzo della larghezza di banda in tempo reale per tutti i collegamenti definiti nel documento Configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="0d931-203">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

### <a name="requirements"></a><span data-ttu-id="0d931-204">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d931-204">Requirements</span></span>

<span data-ttu-id="0d931-205">Lo strumento Monitoraggio servizio criteri di larghezza di banda deve essere eseguito in un computer che fa parte della topologia di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0d931-205">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>

### <a name="summary"></a><span data-ttu-id="0d931-206">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="0d931-206">Summary</span></span>

<span data-ttu-id="0d931-207">Lo strumento Monitoraggio servizio criteri di larghezza di banda può essere una risorsa preziosa per gli amministratori, in modo che possano esaminare lo stato di tutti i servizi dei criteri di larghezza di banda nella topologia e, cosa ancora più importante, possono ottenere l'utilizzo della larghezza di banda in tempo reale per i collegamenti definiti nelle impostazioni di configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="0d931-207">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="0d931-208">Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="0d931-208">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="0d931-209"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="0d931-209"><a name="bua"> </a></span></span>

<span data-ttu-id="0d931-210">Bandwidth Utilization Analyzer è uno strumento che crea report sulle diverse visualizzazioni del consumo di larghezza di banda da parte degli endpoint UC attraverso i collegamenti WAN nella rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="0d931-210">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="0d931-211">Questi report possono essere utilizzati per comprendere il modello di consumo corrente della larghezza di banda e per facilitare la pianificazione della capacità della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="0d931-211">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

### <a name="description"></a><span data-ttu-id="0d931-212">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d931-212">Description</span></span>

<span data-ttu-id="0d931-213">Bandwidth Utilization Analyzer viene implementato come applicazione basata su GUI.</span><span class="sxs-lookup"><span data-stu-id="0d931-213">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="0d931-214">Questo strumento genera report specifici per l'utilizzo audio in tutta la rete e consente di pianificare la capacità.</span><span class="sxs-lookup"><span data-stu-id="0d931-214">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="0d931-215">It also iterates on the bandwidth capacity that is assigned to various links.</span><span class="sxs-lookup"><span data-stu-id="0d931-215">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

### <a name="output"></a><span data-ttu-id="0d931-216">Output</span><span class="sxs-lookup"><span data-stu-id="0d931-216">Output</span></span>

<span data-ttu-id="0d931-217">Bandwidth Utilization Analyzer fornisce grafici di capacità e utilizzo della larghezza di banda per l'audio per tutti i collegamenti WAN configurati nel sistema.</span><span class="sxs-lookup"><span data-stu-id="0d931-217">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

### <a name="purpose"></a><span data-ttu-id="0d931-218">Scopo</span><span class="sxs-lookup"><span data-stu-id="0d931-218">Purpose</span></span>

<span data-ttu-id="0d931-219">In qualsiasi distribuzione vocale e video, è fondamentale monitorare e comprendere la tendenza dell'utilizzo della larghezza di banda del traffico multimediale nella rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="0d931-219">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="0d931-220">Lo strumento Bandwidth Utilization Analyzer consente a un amministratore di ottenere questo risultato.</span><span class="sxs-lookup"><span data-stu-id="0d931-220">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="0d931-221">Questo strumento esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-221">This tool does the following:</span></span>

- <span data-ttu-id="0d931-222">Genera report specifici per l'utilizzo audio in rete</span><span class="sxs-lookup"><span data-stu-id="0d931-222">Generates specific reports for audio utilization across the network</span></span>

- <span data-ttu-id="0d931-223">Consente una pianificazione e un'iterazione della capacità più efficaci sulla capacità della larghezza di banda assegnata a vari collegamenti</span><span class="sxs-lookup"><span data-stu-id="0d931-223">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="0d931-224">Bandwidth Utilization Analyzer può generare grafici di report sulla capacità e sull'utilizzo della larghezza di banda; sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-224">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

- <span data-ttu-id="0d931-225">Tutti i collegamenti WAN nella rete aziendale</span><span class="sxs-lookup"><span data-stu-id="0d931-225">All the WAN links in the enterprise network</span></span>

- <span data-ttu-id="0d931-226">Filtrato in base ai collegamenti WAN selezionati che sono stati scelti</span><span class="sxs-lookup"><span data-stu-id="0d931-226">Filtered by selected WAN links that have been chosen</span></span>

- <span data-ttu-id="0d931-227">Filtrato in base ai collegamenti WAN che hanno superato la capacità dei collegamenti</span><span class="sxs-lookup"><span data-stu-id="0d931-227">Filtered by WAN links that have exceeded link capacity</span></span>

- <span data-ttu-id="0d931-228">Filtrato in base ai collegamenti WAN che hanno utilizzato in modo insufficiente la larghezza di banda di cui è stato eseguito il provisioning</span><span class="sxs-lookup"><span data-stu-id="0d931-228">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

- <span data-ttu-id="0d931-229">Filtrare in base ai collegamenti WAN che hanno raggiunto livelli critici (un utilizzo della larghezza di banda superiore al 90% della capacità della larghezza di banda del collegamento WAN)</span><span class="sxs-lookup"><span data-stu-id="0d931-229">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

- <span data-ttu-id="0d931-230">Filtrato in base al tipo di collegamento WAN, ovvero collegamenti di rete-sito, collegamenti interregionali e collegamenti all'interno di un sito</span><span class="sxs-lookup"><span data-stu-id="0d931-230">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

- <span data-ttu-id="0d931-231">Filtrato per area di rete</span><span class="sxs-lookup"><span data-stu-id="0d931-231">Filtered by network region</span></span>

#### <a name="applications"></a><span data-ttu-id="0d931-232">Applicazioni</span><span class="sxs-lookup"><span data-stu-id="0d931-232">Applications</span></span>

<span data-ttu-id="0d931-233">Bandwidth Utilization Analyzer dispone delle due applicazioni seguenti (strumenti):</span><span class="sxs-lookup"><span data-stu-id="0d931-233">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

- <span data-ttu-id="0d931-234">**WanLinkLogCollector.exe** Questo strumento consente all'utente di immettere le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="0d931-234">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>

- <span data-ttu-id="0d931-235">**BandwidthUtilizationAnalyzer.xlsm** Un report del software per fogli di calcolo di Microsoft Excel viene avviato automaticamente da WanLinkLogCollector.exe.</span><span class="sxs-lookup"><span data-stu-id="0d931-235">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="0d931-236">Questa applicazione consente all'utente di applicare filtri al report, come illustrato più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="0d931-236">This application allows the user to apply filters to the report as shown later in this article.</span></span>

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="0d931-237">Fasi dell'utilizzo di Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="0d931-237">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="0d931-238">Quando si utilizza l'analizzatore dell'utilizzo della larghezza di banda, è necessario eseguire due fasi:</span><span class="sxs-lookup"><span data-stu-id="0d931-238">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

- <span data-ttu-id="0d931-239">Raccogliere i registri, che vengono eseguiti utilizzando WanLinkLogCollector.exe</span><span class="sxs-lookup"><span data-stu-id="0d931-239">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

- <span data-ttu-id="0d931-240">Personalizzare i report, che vengono eseguiti utilizzando BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="0d931-240">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0d931-241">È consigliabile che BandwidthUtilizationAnalyzer.xlsm non sia avviato manualmente dagli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="0d931-241">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>

#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="0d931-242">Avvio di Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="0d931-242">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="0d931-243">Avviare WanLinkLogCollector.exe al prompt dei comandi o utilizzando Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="0d931-243">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

 <span data-ttu-id="0d931-244">**Utilizzo di WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="0d931-244">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="0d931-245">Esistono tre passaggi per l'utilizzo di WanLinkLogCollector.exe:</span><span class="sxs-lookup"><span data-stu-id="0d931-245">There are three steps to using WanLinkLogCollector.exe:</span></span>

1. <span data-ttu-id="0d931-246">**Registrare la sequenza temporale** Specificare la sequenza temporale per cui deve essere generato il report</span><span class="sxs-lookup"><span data-stu-id="0d931-246">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>

2. <span data-ttu-id="0d931-247">**Specificare le directory dei file** Fornire informazioni sulla posizione dei file</span><span class="sxs-lookup"><span data-stu-id="0d931-247">**Specify the file directories** Provide file location information</span></span>

3. <span data-ttu-id="0d931-248">**Raccogliere i log e avviare il visualizzatore di report** Eseguire il comando per generare il report</span><span class="sxs-lookup"><span data-stu-id="0d931-248">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>

#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="0d931-249">Passaggio 1 - Registrare la sequenza temporale</span><span class="sxs-lookup"><span data-stu-id="0d931-249">Step 1 - Log the timeline</span></span>

<span data-ttu-id="0d931-250">La registrazione della sequenza temporale consente all'utente dello strumento di specificare quanto segue, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="0d931-250">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1. <span data-ttu-id="0d931-251">**Data di inizio** Questa è la data di inizio della sequenza temporale per cui deve essere generato il report. ad esempio, 1 agosto 2010.</span><span class="sxs-lookup"><span data-stu-id="0d931-251">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2. <span data-ttu-id="0d931-252">**Data di fine** Si tratta della data di fine della sequenza temporale per cui deve essere generato il report. ad esempio, 30 settembre 2010.</span><span class="sxs-lookup"><span data-stu-id="0d931-252">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>

     ![Date di inizio e di fine nell'utilizzo della larghezza di banda A](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="0d931-254">Passaggio 2 - Specificare le directory dei file</span><span class="sxs-lookup"><span data-stu-id="0d931-254">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="0d931-255">Le directory di file seguenti possono essere specificate dall'utente come illustrato.</span><span class="sxs-lookup"><span data-stu-id="0d931-255">The following file directories can be specified by the user as shown.</span></span>

- <span data-ttu-id="0d931-256">**Percorso dei file di registro del server** Percorso della cartella in cui vengono archiviati i registri del server dei criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="0d931-256">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="0d931-257">In genere si tratta di \<fileserver\> \\<fe \> \AppServerFiles\PDP.</span><span class="sxs-lookup"><span data-stu-id="0d931-257">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>

- <span data-ttu-id="0d931-258">**Percorso di archiviazione file temporanei** Percorso del file temporaneo in cui vengono archiviati i file intermedi durante la generazione del report.</span><span class="sxs-lookup"><span data-stu-id="0d931-258">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

    ![Directory file nell'aal utilizzo larghezza di banda](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > <span data-ttu-id="0d931-260">Verificare che all'utente dello strumento sia fornito un accesso sufficiente ai registri del server e alla cartella dell'archivio file temporaneo.</span><span class="sxs-lookup"><span data-stu-id="0d931-260">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="0d931-261">Passaggio 3 - Raccogliere i log e avviare il visualizzatore di report</span><span class="sxs-lookup"><span data-stu-id="0d931-261">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="0d931-262">Per raccogliere i log e avviare il visualizzatore di report, fare clic **su Esegui** come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0d931-262">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="0d931-263">Questo passaggio raccoglie i dati necessari.</span><span class="sxs-lookup"><span data-stu-id="0d931-263">This step collects the required data.</span></span>

![Raccolta di dati in Bandwidth Utilization Analy](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

<span data-ttu-id="0d931-265">Quando la convalida dell'input ha esito positivo, viene visualizzato il messaggio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0d931-265">When the input validation is successful, the message shown below is displayed.</span></span>

![Registri raccolti notifica nell'utilizzo della larghezza di banda](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

<span data-ttu-id="0d931-267">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0d931-267">Click **OK**.</span></span> <span data-ttu-id="0d931-268">BandwidthUtilizationAnalyzer.xlsm viene avviato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0d931-268">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="0d931-269">Seguire le istruzioni nella finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="0d931-269">Follow the instructions in the message box.</span></span> <span data-ttu-id="0d931-270">Per informazioni dettagliate, **vedere Using BandwidthUtilizationAnalyzer.xlsm** nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="0d931-270">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>


### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="0d931-271">Utilizzo di BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="0d931-271">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="0d931-272">Quando BandwidthUtilizationAnalyzer.xlsm viene avviato automaticamente, fare clic **su Aggiorna** come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0d931-272">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. <span data-ttu-id="0d931-274">Quando viene aperta una cartella di file, selezionare consolidated.csv dal percorso specificato nella finestra di messaggio, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0d931-274">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="0d931-275">Il percorso viene inoltre visualizzato **come C:\Temp**.</span><span class="sxs-lookup"><span data-stu-id="0d931-275">It also shows the location as **C:\Temp**.</span></span>

     ![Apertura di una cartella in BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. <span data-ttu-id="0d931-277">Fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="0d931-277">Click **Import**.</span></span>

4. <span data-ttu-id="0d931-278">Il grafico viene generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0d931-278">The graphical plot is automatically generated.</span></span> <span data-ttu-id="0d931-279">È disponibile quando il puntatore in background scompare.</span><span class="sxs-lookup"><span data-stu-id="0d931-279">It is available when the working-in-the-background pointer disappears.</span></span>

     ![Applicazione di filtri in Visualizzazione report.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="0d931-281">Applicazione di filtri alla visualizzazione report</span><span class="sxs-lookup"><span data-stu-id="0d931-281">Applying Filters to the Report View</span></span>

<span data-ttu-id="0d931-282">I filtri che possono essere applicati alla visualizzazione report come illustrato di seguito sono descritti di seguito:</span><span class="sxs-lookup"><span data-stu-id="0d931-282">The filters that can be applied to the report view as shown below are described as follows:</span></span>

![Applicazione di filtri in Visualizzazione report.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. <span data-ttu-id="0d931-284">**Nome** Filtra in base ai collegamenti WAN (il filtro si trova sul lato destro del grafico). Il prefisso indica i tipi di collegamento seguenti. vedi la casella verticale (blu):</span><span class="sxs-lookup"><span data-stu-id="0d931-284">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>

   - <span data-ttu-id="0d931-285">**S Site** Collegamento WAN da un sito di rete a un'area di rete</span><span class="sxs-lookup"><span data-stu-id="0d931-285">**S Site** The WAN link from a network site to a network region</span></span>

   - <span data-ttu-id="0d931-286">**IS Intersosto** Collegamento WAN tra due siti di rete</span><span class="sxs-lookup"><span data-stu-id="0d931-286">**IS Inter-Site** The WAN link between two network sites</span></span>

   - <span data-ttu-id="0d931-287">**R Inter-Region** Collegamento WAN tra due aree di rete</span><span class="sxs-lookup"><span data-stu-id="0d931-287">**R Inter-Region** The WAN link between two network region</span></span>

2. <span data-ttu-id="0d931-288">**Limite superato** Filtrare in base ai collegamenti WAN il cui utilizzo della larghezza di banda è superiore alla capacità della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="0d931-288">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3. <span data-ttu-id="0d931-289">**Livelli critici** Filtrare in base ai collegamenti WAN il cui utilizzo della larghezza di banda ha raggiunto il 90% o più della capacità della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="0d931-289">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4. <span data-ttu-id="0d931-290">**Sotto-utilizzato** Filtro in base ai collegamenti WAN il cui utilizzo della larghezza di banda è inferiore al 25% della capacità della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="0d931-290">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5. <span data-ttu-id="0d931-291">**Tipo di collegamento** Filtrare in base ai tipi di collegamenti WAN seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-291">**Link type** Filter by the following WAN links types:</span></span>

   - <span data-ttu-id="0d931-292">**Tipo di sito di** rete</span><span class="sxs-lookup"><span data-stu-id="0d931-292">**Network site** type</span></span>

   - <span data-ttu-id="0d931-293">**Tipo tra** siti</span><span class="sxs-lookup"><span data-stu-id="0d931-293">**Inter-site** type</span></span>

   - <span data-ttu-id="0d931-294">**Tipo di collegamento tra aree**</span><span class="sxs-lookup"><span data-stu-id="0d931-294">**Inter-Region link** type</span></span>

6. <span data-ttu-id="0d931-295">**Area geografica** Filtra per area di rete</span><span class="sxs-lookup"><span data-stu-id="0d931-295">**Region** Filter by network region</span></span>

<span data-ttu-id="0d931-296">Le figure seguenti mostrano i filtri descritti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0d931-296">The following figures show the previously described filters.</span></span>

<span data-ttu-id="0d931-297">Filtra per **nome**.</span><span class="sxs-lookup"><span data-stu-id="0d931-297">Filter by **Name**.</span></span> <span data-ttu-id="0d931-298">Selezionare l'elenco dei collegamenti che devono essere visualizzati nel grafico.</span><span class="sxs-lookup"><span data-stu-id="0d931-298">Select the list of links that need to be displayed in the graph.</span></span>

![Filtro in base al nome in BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

<span data-ttu-id="0d931-300">Filtra per **limite superato**.</span><span class="sxs-lookup"><span data-stu-id="0d931-300">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="0d931-301">Selezionare **True** per applicare il filtro.</span><span class="sxs-lookup"><span data-stu-id="0d931-301">Select **True** to enforce the filter.</span></span>

![Filtro per limite superato.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

<span data-ttu-id="0d931-303">Filtra per **livelli critici**.</span><span class="sxs-lookup"><span data-stu-id="0d931-303">Filter by **Critical levels**.</span></span> <span data-ttu-id="0d931-304">Selezionare **True** per applicare il filtro.</span><span class="sxs-lookup"><span data-stu-id="0d931-304">Select **True** to enforce the filter.</span></span>

![Filtro in base ai livelli critici.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

<span data-ttu-id="0d931-306">Filtro in **base a In uso**.</span><span class="sxs-lookup"><span data-stu-id="0d931-306">Filter by **Under utilized**.</span></span> <span data-ttu-id="0d931-307">Selezionare **True** per applicare il filtro.</span><span class="sxs-lookup"><span data-stu-id="0d931-307">Select **True** to enforce the filter.</span></span>

![Filtro in base a Utilizzo in corso.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

<span data-ttu-id="0d931-309">Filtra in base **al tipo di collegamento**.</span><span class="sxs-lookup"><span data-stu-id="0d931-309">Filter by **Link Type**.</span></span> <span data-ttu-id="0d931-310">Selezionare il tipo o i tipi che devono essere visualizzati.</span><span class="sxs-lookup"><span data-stu-id="0d931-310">Select the type or types that need to be displayed.</span></span>

![Filtro in base al tipo di collegamento.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

<span data-ttu-id="0d931-312">Filtra per **area**.</span><span class="sxs-lookup"><span data-stu-id="0d931-312">Filter by **Region**.</span></span> <span data-ttu-id="0d931-313">Selezionare un elenco di aree i cui collegamenti devono essere visualizzati.</span><span class="sxs-lookup"><span data-stu-id="0d931-313">Select a list of regions whose links need to be displayed.</span></span>

![Filtro in base all'area geografica.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a><span data-ttu-id="0d931-315">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d931-315">Requirements</span></span>

- <span data-ttu-id="0d931-316">Il .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="0d931-316">The .NET Framework 3.5</span></span>

- <span data-ttu-id="0d931-317">Microsoft Excel 2010 o Excel 2007</span><span class="sxs-lookup"><span data-stu-id="0d931-317">Microsoft Excel 2010 or Excel 2007</span></span>

### <a name="summary"></a><span data-ttu-id="0d931-318">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="0d931-318">Summary</span></span>

<span data-ttu-id="0d931-319">Bandwidth Utilization Analyzer viene utilizzato per tracciare l'utilizzo della larghezza di banda audio per il traffico UC attraverso la rete.</span><span class="sxs-lookup"><span data-stu-id="0d931-319">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="0d931-320">Questo strumento può essere usato anche per segnalare l'utilizzo della larghezza di banda video nella rete.</span><span class="sxs-lookup"><span data-stu-id="0d931-320">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

## <a name="call-parkometer"></a><span data-ttu-id="0d931-321">Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="0d931-321">Call Parkometer</span></span>
<span data-ttu-id="0d931-322"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="0d931-322"><a name="callpark"> </a></span></span>

<span data-ttu-id="0d931-323">Call Parkometer è un'applicazione da riga di comando che consente di accedere facilmente al database orbit del parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="0d931-323">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

### <a name="description"></a><span data-ttu-id="0d931-324">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d931-324">Description</span></span>

<span data-ttu-id="0d931-325">Call Parkometer è uno strumento per tenere traccia delle chiamate attualmente parcheggiate.</span><span class="sxs-lookup"><span data-stu-id="0d931-325">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="0d931-326">Raccoglie inoltre le statistiche relative ai orbit e all'utilizzo del server di parcheggio di chiamata (CPS).</span><span class="sxs-lookup"><span data-stu-id="0d931-326">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="0d931-327">Questo strumento da riga di comando fornisce accesso in lettura e scrittura al database orbit SQL Server CPS da un computer locale o connesso in remoto.</span><span class="sxs-lookup"><span data-stu-id="0d931-327">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="0d931-328">Tutte le opzioni si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="0d931-328">All options are mutually exclusive.</span></span> <span data-ttu-id="0d931-329">La sintassi della riga di comando è la seguente:</span><span class="sxs-lookup"><span data-stu-id="0d931-329">Command-line syntax is as follows:</span></span>

- <span data-ttu-id="0d931-330">**-o** parametro: elenca tutti gli intervalli di orbit configurati per questo pool.</span><span class="sxs-lookup"><span data-stu-id="0d931-330">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>

- <span data-ttu-id="0d931-331">**Parametro -n:** elenca tutti i orbit attualmente utilizzati nel pool.</span><span class="sxs-lookup"><span data-stu-id="0d931-331">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="0d931-332">Le informazioni visualizzate sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-332">The information displayed is as follows:</span></span>

  - <span data-ttu-id="0d931-333">URI (Uniform Resource Identifier) SIP del parkee e del parcheggiatore.</span><span class="sxs-lookup"><span data-stu-id="0d931-333">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>

  - <span data-ttu-id="0d931-334">Nome host del CPS in cui è parcheggiata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="0d931-334">Host name of the CPS where the call is parked.</span></span>

  - <span data-ttu-id="0d931-335">Timestamp del momento in cui è stata parcheggiata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="0d931-335">Time stamp of when the call was parked.</span></span>

- <span data-ttu-id="0d931-336">**Parametro -f:** elenca il numero di orbit attualmente liberi nel pool.</span><span class="sxs-lookup"><span data-stu-id="0d931-336">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>

- <span data-ttu-id="0d931-337">**-r \<n\>** : elenca le \<n\> ultime chiamate parcheggiate.</span><span class="sxs-lookup"><span data-stu-id="0d931-337">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="0d931-338">Le informazioni visualizzate sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-338">The information displayed is as follows:</span></span>

  - <span data-ttu-id="0d931-339">URI SIP Parkee.</span><span class="sxs-lookup"><span data-stu-id="0d931-339">Parkee SIP URI.</span></span>

  - <span data-ttu-id="0d931-340">URI SIP di Parker.</span><span class="sxs-lookup"><span data-stu-id="0d931-340">Parker SIP URI.</span></span>

  - <span data-ttu-id="0d931-341">Nome host del CPS in cui è stata parcheggiata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="0d931-341">Host name of the CPS where the call was parked.</span></span>

  - <span data-ttu-id="0d931-342">Timestamp del momento in cui la chiamata è stata recuperata o interrotta.</span><span class="sxs-lookup"><span data-stu-id="0d931-342">Time stamp of when the call was retrieved or dropped.</span></span>

- <span data-ttu-id="0d931-343">**-t \<n\>** parameter - verifica la prenotazione di un orbit nel database per mostrare la casualità dei numeri di orbit assegnati.</span><span class="sxs-lookup"><span data-stu-id="0d931-343">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

### <a name="output"></a><span data-ttu-id="0d931-344">Output</span><span class="sxs-lookup"><span data-stu-id="0d931-344">Output</span></span>

<span data-ttu-id="0d931-345">A seconda dei parametri di input specificati al prompt dei comandi, call parkometer visualizza il seguente output:</span><span class="sxs-lookup"><span data-stu-id="0d931-345">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

- <span data-ttu-id="0d931-346">Tutti gli intervalli di orbit configurati per questo pool</span><span class="sxs-lookup"><span data-stu-id="0d931-346">All orbit ranges that are configured for this pool</span></span>

- <span data-ttu-id="0d931-347">Chiamate attualmente parcheggiate</span><span class="sxs-lookup"><span data-stu-id="0d931-347">Currently parked calls</span></span>

- <span data-ttu-id="0d931-348">Numero di orbit gratuiti (disponibili)</span><span class="sxs-lookup"><span data-stu-id="0d931-348">Number of free (available) orbits</span></span>

- <span data-ttu-id="0d931-349">Chiamate parcheggiate di recente</span><span class="sxs-lookup"><span data-stu-id="0d931-349">Recently parked calls</span></span>

- <span data-ttu-id="0d931-350">Orbit riservati per il testing di valori di orbit casuali e uniformi</span><span class="sxs-lookup"><span data-stu-id="0d931-350">Reserved orbits for testing uniform and random orbit values</span></span>

### <a name="purpose"></a><span data-ttu-id="0d931-351">Scopo</span><span class="sxs-lookup"><span data-stu-id="0d931-351">Purpose</span></span>

<span data-ttu-id="0d931-352">Lo scopo dello strumento CPS è fornire l'accesso da riga di comando al database CPS.</span><span class="sxs-lookup"><span data-stu-id="0d931-352">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="0d931-353">L'amministratore può visualizzare l'utilizzo di CPS e determinare il numero di orbit assegnati a un pool.</span><span class="sxs-lookup"><span data-stu-id="0d931-353">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

### <a name="requirements"></a><span data-ttu-id="0d931-354">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d931-354">Requirements</span></span>

<span data-ttu-id="0d931-355">Non esistono requisiti se questo strumento viene eseguito nello stesso computer che esegue CPS.</span><span class="sxs-lookup"><span data-stu-id="0d931-355">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="0d931-356">Se questo strumento viene eseguito in un computer remoto, il database SQL Server utilizzato da Skype for Business Server 2015 deve essere configurato per consentire l'accesso remoto.</span><span class="sxs-lookup"><span data-stu-id="0d931-356">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="0d931-357">Il parkometer delle chiamate deve essere configurato con SQL Server stringa di connessione al database per connettersi alla SQL Server del pool.</span><span class="sxs-lookup"><span data-stu-id="0d931-357">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="0d931-358">Questa SQL Server di connessione al database è definita nel file di configurazione, **parkometer.exe.config**. Deve essere posizionato nella stessa directory in cui parkometer.exe si trova.</span><span class="sxs-lookup"><span data-stu-id="0d931-358">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="0d931-359">Il file XML seguente è un esempio di parkometer.exe.config. I parametri che devono essere configurati sono il nome utente (ad esempio, mydomain\Administrator), la password (ad esempio, mypassword) e il nome host (ad esempio, myserver).</span><span class="sxs-lookup"><span data-stu-id="0d931-359">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

### <a name="examples"></a><span data-ttu-id="0d931-360">Esempi</span><span class="sxs-lookup"><span data-stu-id="0d931-360">Examples</span></span>

<span data-ttu-id="0d931-361">Intervalli di orbit distribuiti: il parametro -o elenca tutti gli intervalli di orbit configurati per questo pool, come mostrato</span><span class="sxs-lookup"><span data-stu-id="0d931-361">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

![Intervalli di orbit in Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

<span data-ttu-id="0d931-363">Chiamate attualmente parcheggiate: il parametro -n elenca tutti i orbit attualmente utilizzati nel pool, come mostrato</span><span class="sxs-lookup"><span data-stu-id="0d931-363">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>

![Chiamate attualmente parcheggiate in Parcheggio di chiamata.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

<span data-ttu-id="0d931-365">Numero di orbit liberi: il parametro -f elenca il numero di orbit attualmente liberi nel pool, come mostrato</span><span class="sxs-lookup"><span data-stu-id="0d931-365">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>

![Orbite gratuite in Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

<span data-ttu-id="0d931-367">Chiamate parcheggiate di recente: il parametro -r \<n\> elenca le ultime chiamate \<n\> parcheggiate come mostrato</span><span class="sxs-lookup"><span data-stu-id="0d931-367">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

![Chiamate parcheggiate di recente in Parcheggio di chiamata.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

<span data-ttu-id="0d931-369">Prenotazione orbit di test: il parametro -t verifica la prenotazione di un \<n\> orbit nel database come mostrato</span><span class="sxs-lookup"><span data-stu-id="0d931-369">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

![Testare le prenotazioni orbit in Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a><span data-ttu-id="0d931-371">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="0d931-371">Summary</span></span>

<span data-ttu-id="0d931-372">Parcheggio di chiamata è uno strumento da riga di comando che fornisce informazioni dettagliate sul server parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="0d931-372">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

## <a name="dbanalyze"></a><span data-ttu-id="0d931-373">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="0d931-373">DBAnalyze</span></span>
<span data-ttu-id="0d931-374"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="0d931-374"><a name="dba"> </a></span></span>

### <a name="description"></a><span data-ttu-id="0d931-375">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d931-375">Description</span></span>

<span data-ttu-id="0d931-376">DBAnalyze è uno strumento da riga di comando che consente agli amministratori di raccogliere report di analisi sui database di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-376">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="0d931-377">DBAnalyze ha le modalità seguenti: diagnostica, dati utente, conferenza, MKU e frammentazione del disco:</span><span class="sxs-lookup"><span data-stu-id="0d931-377">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

- <span data-ttu-id="0d931-378">**Modalità diagnostica** Crea un report che include informazioni sulle tabelle (numero di record, frammentazione, dimensioni dei dati e dimensioni dell'indice), dimensioni dei file di dati e di registro, l'ultimo tempo di backup, la distribuzione dei contatti tra i server che eseguono Microsoft Office Communications Server, il numero medio di autorizzazioni, contatti, contenitori, sottoscrizioni, pubblicazioni, endpoint per utente, eventuali utenti ospitati in modo improprio, utenti che non possono essere instradati, numero medio di conferenze organizzate per utente, conferenze pianificate, conferenze attive e versione del database.</span><span class="sxs-lookup"><span data-stu-id="0d931-378">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0d931-379">L'esecuzione della modalità diagnostica può influire sulle prestazioni del server.</span><span class="sxs-lookup"><span data-stu-id="0d931-379">Running diagnostic mode can affect server performance.</span></span>

- <span data-ttu-id="0d931-380">**Modalità dati utente** Segnala i dati di contatto, contenitore, sottoscrizione, pubblicazione, autorizzazione e gruppo di contatti per un utente specificato o per gli utenti che dispongono di tale utente nei propri elenchi di contatti e autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="0d931-380">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="0d931-381">Questa modalità segnala anche i dati di riepilogo per le conferenze a cui un utente organizza o è invitato.</span><span class="sxs-lookup"><span data-stu-id="0d931-381">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

- <span data-ttu-id="0d931-382">**Modalità conferenza** Riporta i dati dettagliati per una conferenza specifica, inclusi tutti i dettagli della pianificazione della conferenza, l'elenco degli invitati, l'elenco dei tipi di supporti consentiti per la conferenza, le MKU attive (unità di controllo multipunto), l'elenco dei partecipanti attivi e lo stato di segnalazione di ogni partecipante.</span><span class="sxs-lookup"><span data-stu-id="0d931-382">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>

- <span data-ttu-id="0d931-383">**Decodificare l'ID riunione** Decodifica un ID riunione PSTN (Public Switched Telephone Network) specificato dall'opzione **/pstnid** ma che non si connette al back-end per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="0d931-383">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

- <span data-ttu-id="0d931-384">**Risolvere la conferenza** Decodifica un ID riunione PSTN specificato dall'opzione **/pstnid** e visualizza le informazioni sulla conferenza indicata dall'ID.</span><span class="sxs-lookup"><span data-stu-id="0d931-384">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

- <span data-ttu-id="0d931-385">**Modalità MKU** Segnala l'ID, il tipo di supporto, l'URL, lo stato heartbeat, il carico della conferenza e il carico dei partecipanti per ogni MCU nel pool.</span><span class="sxs-lookup"><span data-stu-id="0d931-385">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

- <span data-ttu-id="0d931-386">**Modalità frammentazione disco** Visualizza lo stato di frammentazione di tutti i dischi.</span><span class="sxs-lookup"><span data-stu-id="0d931-386">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="0d931-387">Questo strumento può essere utilizzato per diagnosticare vari problemi o per assistere gli amministratori nella pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="0d931-387">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="0d931-388">Ad esempio, se la maggior parte degli utenti ospitati nel server A sceglie gli utenti ospitati nel server B come contatti, l'amministratore può spostare gli utenti nel server A al server B per ridurre il traffico tra server.</span><span class="sxs-lookup"><span data-stu-id="0d931-388">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

### <a name="output"></a><span data-ttu-id="0d931-389">Output</span><span class="sxs-lookup"><span data-stu-id="0d931-389">Output</span></span>

<span data-ttu-id="0d931-390">Questo strumento genera report predefiniti sul database di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-390">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="0d931-391">**Percorso**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span><span class="sxs-lookup"><span data-stu-id="0d931-391">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>

### <a name="purpose"></a><span data-ttu-id="0d931-392">Scopo</span><span class="sxs-lookup"><span data-stu-id="0d931-392">Purpose</span></span>

<span data-ttu-id="0d931-393">Per installare Dbanalyze.exe, copiarlo in una cartella locale ed eseguire lo strumento.</span><span class="sxs-lookup"><span data-stu-id="0d931-393">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="0d931-394">Per utilizzare lo strumento, eseguire il comando seguente dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="0d931-394">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="0d931-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` Di seguito sono riportate le descrizioni delle opzioni della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="0d931-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>

![Opzioni della riga di comando per Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a><span data-ttu-id="0d931-397">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d931-397">Requirements</span></span>

 <span data-ttu-id="0d931-398">**Computer** DBAnalyze può essere eseguito solo da un computer aggiunto a un dominio in cui è installato Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-398">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>

 <span data-ttu-id="0d931-399">**Rete** Il computer dovrebbe essere in grado di connettersi al database back-end.</span><span class="sxs-lookup"><span data-stu-id="0d931-399">**Network** The computer should be able to connect to the back-end database.</span></span>

 <span data-ttu-id="0d931-400">**Software** I componenti software di Skype for Business Server 2015 devono essere installati prima di eseguire DBAnalyze.</span><span class="sxs-lookup"><span data-stu-id="0d931-400">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>

 <span data-ttu-id="0d931-401">**Utenti** La tabella seguente mostra gli amministratori che dispongono delle autorizzazioni necessarie per accedere ai database di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-401">**Users** The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>

![Tabella delle autorizzazioni per Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> <span data-ttu-id="0d931-403">Per la modalità **disco /report:disk** è necessario un account amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="0d931-403">A local administrator account is required for **/report:disk** mode.</span></span>

### <a name="examples"></a><span data-ttu-id="0d931-404">Esempi</span><span class="sxs-lookup"><span data-stu-id="0d931-404">Examples</span></span>

<span data-ttu-id="0d931-405">Di seguito sono riportati alcuni esempi di comandi Dbanalyze.exe validi:</span><span class="sxs-lookup"><span data-stu-id="0d931-405">The following are examples of valid Dbanalyze.exe commands:</span></span>

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="0d931-406">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="0d931-406">Summary</span></span>

<span data-ttu-id="0d931-407">DBAnalyzer fornisce agli amministratori un'analisi rapida e semplice dei database di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-407">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>

## <a name="import-storage-service-data"></a><span data-ttu-id="0d931-408">Importare i dati del servizio di archiviazione</span><span class="sxs-lookup"><span data-stu-id="0d931-408">Import Storage Service Data</span></span>
<span data-ttu-id="0d931-409"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="0d931-409"><a name="Issd"> </a></span></span>

<span data-ttu-id="0d931-410">Lo strumento Del Resource Kit ImportStorageServiceData consente di reimportare i dati della coda e dell'endpoint scaricati dal servizio di archiviazione (LYSS) di nuovo nel servizio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="0d931-410">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

### <a name="description"></a><span data-ttu-id="0d931-411">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d931-411">Description</span></span>

<span data-ttu-id="0d931-412">I dati scaricati dal servizio di archiviazione potrebbero essere stati automatici (periodici) in base allo stato degli elementi della coda o alle dimensioni del database.</span><span class="sxs-lookup"><span data-stu-id="0d931-412">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="0d931-413">Potrebbe essere avvenuto a causa della chiamata manuale del cmdlet di failover del pool o del cmdlet StorageServiceFullFlush (richiamato dal cmdlet di failover del pool).</span><span class="sxs-lookup"><span data-stu-id="0d931-413">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="0d931-414">Si noti che i dati dovrebbero idealmente non essere reimportati se una qualsiasi delle dimensioni del database del servizio di archiviazione (LYSS) nei front-end è al di sopra del livello normale, perché in questo modo è probabile che si esportino più dati. Inoltre, tutti i problemi che potrebbero aver contribuito a errori che hanno causato l'aumentare della coda del servizio di archiviazione devono prima essere risolti (ad esempio errori degli endpoint di Exchange, problemi di rete o altri problemi).</span><span class="sxs-lookup"><span data-stu-id="0d931-414">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

 <span data-ttu-id="0d931-415">**Scenario 1: durante** il failover del pool, i file possono essere scaricati dal servizio di archiviazione per ogni front-end.</span><span class="sxs-lookup"><span data-stu-id="0d931-415">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="0d931-416">Al termine del failover, è necessario eseguire lo strumento per reimportare i dati.</span><span class="sxs-lookup"><span data-stu-id="0d931-416">After failover is completed, the tool should be run to re-import the data.</span></span>

 <span data-ttu-id="0d931-417">**Scenario 2:** i dati vengono scaricati automaticamente ogni giorno o in risposta al database del servizio di archiviazione che supera determinate soglie di dimensione ( ad esempio 60%, 80%, 90% pieno ).</span><span class="sxs-lookup"><span data-stu-id="0d931-417">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="0d931-418">Questi dati scaricati automaticamente devono essere reimportati regolarmente dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="0d931-418">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="0d931-419">Nella situazione precedente, se il pacchetto SCOM di monitoraggio non viene distribuito, esistono eventi per il servizio di archiviazione di Skype for Business Server relativi ai dati scaricati dal servizio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="0d931-419">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="0d931-420">ID evento di 32075 (operazione di scaricamento completa avviata), 32076 (scaricamento completo completato), 32082 (scaricamento del livello di manutenzione avviato), 32083 (scaricamento del livello di manutenzione completato), 32089 (svuotamento dovuto al riempimento del database).</span><span class="sxs-lookup"><span data-stu-id="0d931-420">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="0d931-421">Nota questi ID evento corrispondono alla versione RTM.</span><span class="sxs-lookup"><span data-stu-id="0d931-421">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="0d931-422">Quando un amministratore visualizza questi eventi, significa che sono presenti file che sono stati scaricati. Questi dati devono essere regolarmente importati di nuovo usando questo strumento, ad esempio una volta alla settimana.</span><span class="sxs-lookup"><span data-stu-id="0d931-422">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="0d931-423">Per la versione del servizio online, se viene distribuito il pacchetto SCOM per il monitoraggio dell'integrità per Skype for Business Server, è possibile che venga generato un nuovo avviso che richiede all'amministratore di reimportare i dati scaricati nel servizio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="0d931-423">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="0d931-424">Nel registro eventi del front-end server sarà presente un evento corrispondente che ha attivato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="0d931-424">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="0d931-425">L'evento darà una descrizione del percorso padre in cui si trovano i file di dati scaricati, nonché il numero di file che soddisfano i criteri di avviso.</span><span class="sxs-lookup"><span data-stu-id="0d931-425">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="0d931-426">I criteri di avviso sono X o più file nel percorso padre specifico che hanno almeno Y giorni ( dove X e Y sono preimpostati all'interno di StorageService, ma possono essere ignorati modificando il file APPCONFIG). Di seguito sono riportati due esempi di eventi che possono attivare l'avviso di integrità, con la differenza che è il percorso padre.</span><span class="sxs-lookup"><span data-stu-id="0d931-426">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="0d931-427">Una possibilità è la condivisione file del servizio Web, mentre l'altra è la directory dati applicazioni locale di ogni front-end.</span><span class="sxs-lookup"><span data-stu-id="0d931-427">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="0d931-428">( ad esempio c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ).</span><span class="sxs-lookup"><span data-stu-id="0d931-428">( for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ).</span></span> <span data-ttu-id="0d931-429">L'amministratore eseguirà quindi questo strumento reskit.</span><span class="sxs-lookup"><span data-stu-id="0d931-429">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="0d931-430">Questo strumento aumenterà il carico di CPU e I/O sul front-end in cui è in esecuzione, nonché di altri front-end, nel caso in cui i dati non sono di proprietà del front-end su cui viene eseguito lo strumento.</span><span class="sxs-lookup"><span data-stu-id="0d931-430">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="0d931-431">È consigliabile eseguire questo strumento quando i front-end non sono sotto carico elevato di CPU e I/O, ad esempio al di fuori delle ore di punta.</span><span class="sxs-lookup"><span data-stu-id="0d931-431">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="0d931-432">In secondo luogo, questo strumento può richiedere da 2 a 3 minuti per importare un file di dati.</span><span class="sxs-lookup"><span data-stu-id="0d931-432">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="0d931-433">Tieni presente questo problema durante la stima della durata dell'esecuzione dello strumento.</span><span class="sxs-lookup"><span data-stu-id="0d931-433">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="0d931-434">Il file di registro dettagliato generato dallo strumento verrà visualizzato per impostazione predefinita nell'archivio file.</span><span class="sxs-lookup"><span data-stu-id="0d931-434">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="0d931-435">Eliminarlo se non vengono segnalati errori, perché il file di registro può contenere decine di MB o più.</span><span class="sxs-lookup"><span data-stu-id="0d931-435">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

![Eventi del registro eventi di Storage Server di esempio.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a><span data-ttu-id="0d931-437">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d931-437">Requirements</span></span>

<span data-ttu-id="0d931-438">Installare gli strumenti di Skype for Business Server 2015 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="0d931-438">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="0d931-439">Lo strumento viene eseguito nei computer aggiunti al dominio in cui sono installati Skype for Business Server e Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0d931-439">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="0d931-440">Lo strumento utilizza un cmdlet dalla shell di gestione per identificare tutti i Front End Server nel pool.</span><span class="sxs-lookup"><span data-stu-id="0d931-440">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="0d931-441">In secondo luogo, lo strumento deve essere eseguito da un computer del pool in cui è installato il database **RtcLocal.**</span><span class="sxs-lookup"><span data-stu-id="0d931-441">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="0d931-442">Questo database viene utilizzato dallo strumento per recuperare il percorso della condivisione file WEBSERVICE per il pool.</span><span class="sxs-lookup"><span data-stu-id="0d931-442">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="0d931-443">Inoltre, prima di utilizzare lo strumento, ogni Front End Server deve abilitare Windows PowerShell Remoting utilizzando **Enable-PSRemoting** in ogni Front End Server, nonché il computer da cui viene eseguito lo strumento.</span><span class="sxs-lookup"><span data-stu-id="0d931-443">Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="0d931-444">In caso contrario, i Windows PowerShell remoti da questo strumento avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="0d931-444">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="0d931-445">Windows PowerShell la comunicazione remota può essere disattivata in tutti i Front End Server del pool al termine.</span><span class="sxs-lookup"><span data-stu-id="0d931-445">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="0d931-446">Infine, l'account o le credenziali che richiamano lo strumento devono disporre dell'autorizzazione di lettura/scrittura per la condivisione file del servizio Web per il pool in cui sta eseguendo lo strumento.</span><span class="sxs-lookup"><span data-stu-id="0d931-446">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="0d931-447">In caso contrario, lo strumento avrà esito negativo con errori di autorizzazione I/O.</span><span class="sxs-lookup"><span data-stu-id="0d931-447">Otherwise the tool will fail with IO Permission errors.</span></span>

> [!NOTE]
> <span data-ttu-id="0d931-448">In Windows Server 2012, la Windows PowerShell remota è abilitata per impostazione predefinita, ma non nel sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="0d931-448">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>

### <a name="examples"></a><span data-ttu-id="0d931-449">Esempi</span><span class="sxs-lookup"><span data-stu-id="0d931-449">Examples</span></span>

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

## <a name="lcssync"></a><span data-ttu-id="0d931-450">LCSSync</span><span class="sxs-lookup"><span data-stu-id="0d931-450">LCSSync</span></span>
<span data-ttu-id="0d931-451"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="0d931-451"><a name="LCSSync"> </a></span></span>

<span data-ttu-id="0d931-452">Lo strumento LCSSync consente di distribuire il software di comunicazione di Skype for Business Server 2015 in un ambiente a più foreste.</span><span class="sxs-lookup"><span data-stu-id="0d931-452">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="0d931-453">Questo strumento viene utilizzato per sincronizzare utenti e gruppi di foreste di utenti diverse come oggetto contatto di Servizi di dominio Active Directory con una foresta centrale in cui è installato Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-453">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>

### <a name="description"></a><span data-ttu-id="0d931-454">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d931-454">Description</span></span>

 <span data-ttu-id="0d931-455">LCSSync utilizza gli oggetti contatto di Servizi di dominio Active Directory sincronizzati nella foresta centrale per abilitare gli utenti per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0d931-455">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="0d931-456">Per fornire l'accesso Single Sign-in, l'account utente principale deve essere mappato all'oggetto contatto di Servizi di dominio Active Directory nella foresta centrale per Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-456">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="0d931-457">Questo strumento consente di eseguire tale mapping.</span><span class="sxs-lookup"><span data-stu-id="0d931-457">This tool helps perform that mapping.</span></span> <span data-ttu-id="0d931-458">Questo strumento fornisce modelli per la creazione di agenti di gestione in Microsoft Identity Integration Server.</span><span class="sxs-lookup"><span data-stu-id="0d931-458">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

### <a name="summary"></a><span data-ttu-id="0d931-459">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="0d931-459">Summary</span></span>

<span data-ttu-id="0d931-460">Lo strumento LCSSync consente di distribuire Skype for Business Server 2015 in un ambiente a più foreste.</span><span class="sxs-lookup"><span data-stu-id="0d931-460">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>

## <a name="lookup-user-console"></a><span data-ttu-id="0d931-461">Console utente di ricerca</span><span class="sxs-lookup"><span data-stu-id="0d931-461">Lookup User Console</span></span>
<span data-ttu-id="0d931-462"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="0d931-462"><a name="LUC"> </a></span></span>

<span data-ttu-id="0d931-463">Lo strumento LookupUserConsole consente di visualizzare informazioni interne sul routing di Skype for Business Server su utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="0d931-463">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="0d931-464">Queste informazioni possono essere utili per il supporto personale di Microsoft nella diagnosi dei problemi di distribuzione e routing.</span><span class="sxs-lookup"><span data-stu-id="0d931-464">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

### <a name="description"></a><span data-ttu-id="0d931-465">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d931-465">Description</span></span>

 <span data-ttu-id="0d931-466">L'LookupUserConsole.exe aprirà un prompt dei comandi che accetta gli indirizzi SIP e tenterà di visualizzare le informazioni di routing interne di Skype for Business Server relative a essi.</span><span class="sxs-lookup"><span data-stu-id="0d931-466">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="0d931-467">Digitare **exit** per uscire dallo strumento LookupUserConsole.</span><span class="sxs-lookup"><span data-stu-id="0d931-467">Type **exit** to quit the LookupUserConsole tool.</span></span>

### <a name="requirements"></a><span data-ttu-id="0d931-468">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d931-468">Requirements</span></span>

<span data-ttu-id="0d931-469">Installare Skype for Business Server 2015 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="0d931-469">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="0d931-470">Lo strumento viene eseguito nei computer aggiunti al dominio in cui è installato Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0d931-470">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>

### <a name="examples"></a><span data-ttu-id="0d931-471">Esempi</span><span class="sxs-lookup"><span data-stu-id="0d931-471">Examples</span></span>

<span data-ttu-id="0d931-472">C:\Programmi\Skype for Business Server 2015\ResKit \>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="0d931-472">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>

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

## <a name="msturnping"></a><span data-ttu-id="0d931-473">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="0d931-473">MsTurnPing</span></span>
<span data-ttu-id="0d931-474"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="0d931-474"><a name="MsTurnPing"> </a></span></span>

<span data-ttu-id="0d931-475">Lo strumento MSTurnPing consente a un amministratore del software di comunicazione di Skype for Business Server 2015 di controllare lo stato dei server che eseguono i servizi di autenticazione Audio/Video Edge e Audio/Video, nonché dei server che eseguono i servizi di criteri di larghezza di banda nella topologia.</span><span class="sxs-lookup"><span data-stu-id="0d931-475">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

### <a name="description"></a><span data-ttu-id="0d931-476">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d931-476">Description</span></span>

<span data-ttu-id="0d931-477">Lo strumento MSTurnPing consente a un amministratore del software di comunicazione di Skype for Business Server 2015 di controllare lo stato dei server che eseguono i servizi di autenticazione Audio/Video Edge e Audio/Video, nonché dei server che eseguono i servizi di criteri di larghezza di banda nella topologia.</span><span class="sxs-lookup"><span data-stu-id="0d931-477">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="0d931-478">Lo strumento consente all'amministratore di eseguire i test seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-478">The tool allows the administrator to perform the following tests:</span></span>

1. <span data-ttu-id="0d931-479">Test A/V Edge Server: lo strumento esegue test su tutti i server A/V Edge Server della topologia eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-479">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>

   - <span data-ttu-id="0d931-480">Verifica che il servizio di autenticazione audio/video di Skype for Business Server sia stato avviato e che possa emettere credenziali appropriate.</span><span class="sxs-lookup"><span data-stu-id="0d931-480">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="0d931-481">Verificare che il servizio Skype for Business Server Audio/Video Edge sia stato avviato e che sia possibile allocare correttamente le risorse sul perimetro esterno.</span><span class="sxs-lookup"><span data-stu-id="0d931-481">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2. <span data-ttu-id="0d931-482">Test del servizio criteri di larghezza di banda: lo strumento esegue test su tutti i server che eseguono i Servizi criteri di larghezza di banda nella topologia eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-482">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>

   - <span data-ttu-id="0d931-483">Verificare che il servizio criteri di larghezza di banda di Skype for Business Server (autenticazione) sia avviato e che possa emettere credenziali appropriate.</span><span class="sxs-lookup"><span data-stu-id="0d931-483">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="0d931-484">Verifica dell'avvio del servizio Criteri di larghezza di banda (Core) di Skype for Business Server e in grado di eseguire correttamente il controllo della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="0d931-484">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="0d931-485">Questo strumento deve essere eseguito da un computer che fa parte della topologia e in cui è installato l'archivio locale.</span><span class="sxs-lookup"><span data-stu-id="0d931-485">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

### <a name="output"></a><span data-ttu-id="0d931-486">Output</span><span class="sxs-lookup"><span data-stu-id="0d931-486">Output</span></span>

<span data-ttu-id="0d931-487">Lo strumento restituisce i risultati di ognuna delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="0d931-487">The tool outputs the results of each of the operations.</span></span>

- <span data-ttu-id="0d931-488">Se viene eseguito il test **AudioVideoEdgeServer,** gli output dello strumento sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-488">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="0d931-489">Risultati dei test dei computer che forniscono il servizio di autenticazione audio/video di Skype for Business Server 2015 nella topologia</span><span class="sxs-lookup"><span data-stu-id="0d931-489">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>

  - <span data-ttu-id="0d931-490">Risultati dei test dei computer che forniscono il servizio Skype for Business Server 2015 Audio/Video Edge nella topologia</span><span class="sxs-lookup"><span data-stu-id="0d931-490">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>

- <span data-ttu-id="0d931-491">Se viene eseguito il test **BandwidthPolicyServer,** gli output dello strumento sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-491">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="0d931-492">Risultati dei test dei computer che forniscono il servizio criteri di larghezza di banda (autenticazione) di Skype for Business Server 2015 nella topologia</span><span class="sxs-lookup"><span data-stu-id="0d931-492">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>

  - <span data-ttu-id="0d931-493">Risultati dei test dei computer che forniscono il servizio criteri di larghezza di banda (Core) di Skype for Business Server 2015 nella topologia</span><span class="sxs-lookup"><span data-stu-id="0d931-493">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>

### <a name="requirements"></a><span data-ttu-id="0d931-494">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d931-494">Requirements</span></span>

- <span data-ttu-id="0d931-495">Questo strumento deve essere eseguito da un computer che si trova nella topologia e che dispone dell'archivio locale.</span><span class="sxs-lookup"><span data-stu-id="0d931-495">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

- <span data-ttu-id="0d931-496">Lo strumento deve essere eseguito come amministratore che ha accesso all'archivio locale.</span><span class="sxs-lookup"><span data-stu-id="0d931-496">The tool must be run as an administrator who has access to the local store.</span></span>

### <a name="examples"></a><span data-ttu-id="0d931-497">Esempi</span><span class="sxs-lookup"><span data-stu-id="0d931-497">Examples</span></span>

<span data-ttu-id="0d931-498">Di seguito è riportato un esempio dell'input dello strumento.</span><span class="sxs-lookup"><span data-stu-id="0d931-498">The following is an example of the tool input.</span></span>

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="0d931-499">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="0d931-499">Summary</span></span>

<span data-ttu-id="0d931-500">Questo strumento può essere una risorsa preziosa per gli amministratori di Skype for Business Server 2015 che desiderano controllare lo stato dei server che eseguono servizi di criteri audio/video e larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="0d931-500">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

## <a name="network-configuration-viewer"></a><span data-ttu-id="0d931-501">Visualizzatore configurazione di rete</span><span class="sxs-lookup"><span data-stu-id="0d931-501">Network Configuration Viewer</span></span>
<span data-ttu-id="0d931-502"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="0d931-502"><a name="NCV"> </a></span></span>

<span data-ttu-id="0d931-503">Visualizzatore configurazione di rete può essere utilizzato dagli amministratori del software di comunicazione di Skype for Business Server 2015 per visualizzare la topologia di rete CAC (Call Admission Control) per un'azienda di cui viene eseguito il provisioning per consentire sessioni di comunicazione in tempo reale, ad esempio chiamate vocali o videochiamate in base alla capacità di larghezza di banda specificata.</span><span class="sxs-lookup"><span data-stu-id="0d931-503">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="0d931-504">Gli amministratori di Skype for Business Server 2015 definiscono i criteri di controllo di ammissione di chiamata, che vengono applicati dai servizi dei criteri di larghezza di banda installati con Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-504">Skype for Business Server 2015 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>

### <a name="description"></a><span data-ttu-id="0d931-505">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d931-505">Description</span></span>

<span data-ttu-id="0d931-506">Visualizzatore configurazione di rete (NetworkConfigurationViewer.exe) consente agli amministratori di eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-506">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

- <span data-ttu-id="0d931-507">Caricare e visualizzare la topologia di rete CAC da una distribuzione di Skype for Business Server 2015 in formato grafico.</span><span class="sxs-lookup"><span data-stu-id="0d931-507">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>

- <span data-ttu-id="0d931-508">Caricare e visualizzare la topologia di rete CAC da un file di registro del server dei criteri di larghezza di banda in formato grafico.</span><span class="sxs-lookup"><span data-stu-id="0d931-508">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

- <span data-ttu-id="0d931-509">Salvare e archiviare la topologia di rete CAC in un formato XML sul disco.</span><span class="sxs-lookup"><span data-stu-id="0d931-509">Save and store CAC network topology in an XML format on the disk.</span></span>

- <span data-ttu-id="0d931-510">Salvare e archiviare il diagramma della topologia di rete CAC in formato JPG o BMP.</span><span class="sxs-lookup"><span data-stu-id="0d931-510">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

- <span data-ttu-id="0d931-511">Visualizzare i dati di configurazione della topologia di rete CAC.</span><span class="sxs-lookup"><span data-stu-id="0d931-511">View CAC network topology configuration data.</span></span>

- <span data-ttu-id="0d931-512">Visualizzare la topologia di rete del controllo di ammissione di chiamata in uno stile di visualizzazione albero.</span><span class="sxs-lookup"><span data-stu-id="0d931-512">View CAC network topology in a tree-view style.</span></span>

- <span data-ttu-id="0d931-513">Definire connettori personalizzati per i collegamenti di topologia di rete CAC (ad esempio, collegamenti da sito a area, da area a area e da sito a sito).</span><span class="sxs-lookup"><span data-stu-id="0d931-513">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

- <span data-ttu-id="0d931-514">Visualizzare le informazioni sul sito della topologia di rete CAC, le informazioni sull'area e i criteri di larghezza di banda e i collegamenti di rete di cui è stato eseguito il provisioning.</span><span class="sxs-lookup"><span data-stu-id="0d931-514">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

### <a name="purpose"></a><span data-ttu-id="0d931-515">Scopo</span><span class="sxs-lookup"><span data-stu-id="0d931-515">Purpose</span></span>

<span data-ttu-id="0d931-516">Visualizzare i collegamenti della topologia di rete del controllo di ammissione di chiamata dell'organizzazione in un'interfaccia grafica.</span><span class="sxs-lookup"><span data-stu-id="0d931-516">View enterprise CAC network topology links in a graphical interface.</span></span>

### <a name="examples"></a><span data-ttu-id="0d931-517">Esempi</span><span class="sxs-lookup"><span data-stu-id="0d931-517">Examples</span></span>

 <span data-ttu-id="0d931-518">Caricare e visualizzare la topologia di rete CAC da una distribuzione di **Skype for Business Server 2015 in** un formato grafico: gli amministratori di Skype for Business Server 2015 possono caricare e visualizzare la configurazione della topologia di rete CAC in qualsiasi computer Skype for Business Server 2015 utilizzando l'opzione **Scarica** configurazione di rete, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="0d931-518">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="0d931-519">Lo strumento non riesce a scaricare o visualizzare tale configurazione quando viene distribuito in un computer che non dispone di connettività all'archivio di configurazione di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-519">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>

![Download della configurazione di rete.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 <span data-ttu-id="0d931-521">**Caricare e visualizzare la topologia di rete CAC da un file di** registro del server dei criteri di larghezza di banda in formato grafico: I server dei criteri di larghezza di banda di Skype for Business Server 2015 salvano la topologia di rete CAC come parte del meccanismo di registrazione nel percorso di condivisione file di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-521">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="0d931-522">Gli amministratori di Skype for Business Server 2015 possono visualizzare un file di questo tipo in formato grafico utilizzando l'opzione Apri configurazione **di** rete, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0d931-522">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

![Apertura di un file di registro del server dei criteri di larghezza di banda.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

<span data-ttu-id="0d931-524">Salvare e archiviare la topologia di rete CAC in un formato XML sul disco: gli amministratori di Skype for Business  Server 2015 possono salvare il file di configurazione della topologia di rete CAC in un formato XML utilizzando l'opzione Salva una copia di Configurazione di rete, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0d931-524">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="0d931-525">Il file di configurazione salvato può quindi essere utilizzato offline per la visualizzazione grafica.</span><span class="sxs-lookup"><span data-stu-id="0d931-525">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

![Salvataggio della configurazione di rete come file XML.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

<span data-ttu-id="0d931-527">Salvare e archiviare il diagramma della topologia di rete CAC in formato JPG o BMP: gli amministratori di Skype for Business Server 2015 possono salvare la configurazione della topologia di rete CAC in un formato grafico (formati di file JPG e BMP) utilizzando l'opzione Salva diagramma configurazione di rete come immagine, come illustrato di seguito. </span><span class="sxs-lookup"><span data-stu-id="0d931-527">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

![Salvataggio della configurazione di rete come immagine.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <span data-ttu-id="0d931-529"><strong>Visualizzare i dati di configurazione della topologia di rete CAC:</strong> Gli amministratori di Skype for Business Server 2015 possono visualizzare i dati di configurazione di rete correlati, ad esempio aree di rete, siti di rete, profili di larghezza di banda e indirizzi IP della subnet del sito in formato testuale utilizzando l'opzione Visualizza dati di configurazione di rete, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0d931-529"><strong>View CAC network topology configuration data:</strong>Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

![Visualizzazione dei dati di configurazione di rete.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 <span data-ttu-id="0d931-531">Visualizzare la topologia di rete del controllo di ammissione di **chiamata in uno stile di visualizzazione albero:** Gli amministratori di Skype for Business Server 2015 possono visualizzare i dati di configurazione di rete correlati in uno stile di visualizzazione ad albero grafico utilizzando il pannello di controllo sul lato sinistro della finestra degli strumenti, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0d931-531">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

![Visualizzazione dei dati di configurazione di rete in una visualizzazione albero.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 <span data-ttu-id="0d931-533">**Definire connettori personalizzati per i** collegamenti di topologia di rete CAC ,ad esempio collegamenti da sito a area, da area a area e da sito a sito: Gli amministratori di Skype for Business Server 2015 possono definire connettori grafici personalizzati per i collegamenti WAN di configurazione della rete CAC utilizzando l'opzione Impostazioni come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0d931-533">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="0d931-534">Ciò consente di distinguere tra vari tipi di collegamenti di rete di cui viene eseguito il provisioning nella configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="0d931-534">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

![Strumenti](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 <span data-ttu-id="0d931-536">**Visualizzare le informazioni sul sito** della topologia di rete del controllo di ammissione di chiamata, le informazioni sull'area geografica e i criteri di larghezza di banda di cui è stato eseguito il provisioning: Gli amministratori di Skype for Business Server 2015 possono visualizzare le informazioni correlate sull'area di rete CAC, le informazioni sul sito e le informazioni sul provisioning della larghezza di banda del controllo di ammissione di chiamata utilizzando le opzioni illustrate di seguito.</span><span class="sxs-lookup"><span data-stu-id="0d931-536">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="0d931-537">Ad esempio, fare clic su **Informazioni** in un'area di rete o in un oggetto sito di rete.</span><span class="sxs-lookup"><span data-stu-id="0d931-537">(For example, click **Info** in a network region or network site object.)</span></span>

![Definizione di connettori personalizzati per la rete.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a><span data-ttu-id="0d931-539">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="0d931-539">Summary</span></span>

<span data-ttu-id="0d931-540">Questo strumento può essere una risorsa preziosa per gli amministratori di Skype for Business Server 2015 che desiderano visualizzare la topologia di rete CAC per la distribuzione in un formato grafico.</span><span class="sxs-lookup"><span data-stu-id="0d931-540">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

## <a name="response-group-agent-live"></a><span data-ttu-id="0d931-541">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="0d931-541">Response Group Agent Live</span></span>
<span data-ttu-id="0d931-542"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="0d931-542"><a name="RGAL"> </a></span></span>

<span data-ttu-id="0d931-543">L'applicazione Response Group offre agli agenti la possibilità di accedere a informazioni utili in tempo reale utilizzando il servizio Web incorporato.</span><span class="sxs-lookup"><span data-stu-id="0d931-543">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="0d931-544">Purtroppo, all'esterno dell'applicazione non è disponibile alcuna visualizzazione grafica di questi dati.</span><span class="sxs-lookup"><span data-stu-id="0d931-544">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="0d931-545">Lo strumento Response Group Agent Live Resource Kit risolve questo problema fornendo un modo semplice e grafico per accedere a queste informazioni, migliorato con informazioni sul software di comunicazione Skype for Business in tempo reale, ad esempio la presenza di altri agenti.</span><span class="sxs-lookup"><span data-stu-id="0d931-545">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>

### <a name="description"></a><span data-ttu-id="0d931-546">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d931-546">Description</span></span>

<span data-ttu-id="0d931-547">Response Group Agent Live è un'applicazione di Windows che fornisce funzionalità di accesso e disconnessione e alcune informazioni in tempo reale (ad esempio l'appartenenza al gruppo e il numero corrente di chiamate) agli agenti di Response Group.</span><span class="sxs-lookup"><span data-stu-id="0d931-547">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="0d931-548">Ha lo scopo di essere una versione avanzata della pagina Gruppi di agenti (accessibile da Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="0d931-548">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>

### <a name="purpose"></a><span data-ttu-id="0d931-549">Scopo</span><span class="sxs-lookup"><span data-stu-id="0d931-549">Purpose</span></span>

<span data-ttu-id="0d931-550">L'applicazione Response Group accoda le chiamate in arrivo e quindi le instrada ai gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="0d931-550">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="0d931-551">Per prendere decisioni informate sulle chiamate al servizio, gli agenti possono accedere a informazioni in tempo reale sui gruppi di agenti, ad esempio quali altri agenti sono disponibili e quante chiamate sono in attesa in ogni coda.</span><span class="sxs-lookup"><span data-stu-id="0d931-551">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="0d931-552">Queste informazioni, inizialmente accessibili solo tramite il servizio Response Group, sono rese disponibili in modo intuitivo da Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="0d931-552">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

#### <a name="features"></a><span data-ttu-id="0d931-553">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="0d931-553">Features</span></span>

<span data-ttu-id="0d931-554">Lo strumento Response Group Agent Live è basato sul servizio Response Group e su Skype for Business Server 2015 SDK.</span><span class="sxs-lookup"><span data-stu-id="0d931-554">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="0d931-555">Fornisce agli agenti di Response Group le informazioni e le funzionalità disponibili dal servizio Response Group ,ad esempio l'appartenenza a gruppi, la presenza di altri agenti e il numero di chiamate in attesa.</span><span class="sxs-lookup"><span data-stu-id="0d931-555">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="0d931-556">La figura seguente illustra l'interfaccia principale di Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="0d931-556">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

![Strumento Response Group Agent Live.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

<span data-ttu-id="0d931-558">Le tre funzionalità principali seguenti sono disponibili per gli agenti in Response Group Agent Live:</span><span class="sxs-lookup"><span data-stu-id="0d931-558">The following three main features are available for agents in Response Group Agent Live:</span></span>

- <span data-ttu-id="0d931-559">**Accesso/disconnessione:** A differenza della pagina Gruppi di agenti (accessibile da Skype for Business Server 2015), Response Group Agent Live consente solo agli agenti di accedere o disconnettersi da tutti i gruppi di agenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="0d931-559">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="0d931-560">Questa applicazione offre tre modi rapidi per l'accesso o la disconnessione degli agenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-560">This application provides three quick ways for agents to sign in or out:</span></span>

  - <span data-ttu-id="0d931-561">Fai clic sui pulsanti Accedi/Esci (verde e rosso) all'interno dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0d931-561">Click the Sign-in/out (green and red) buttons within the application.</span></span>

  - <span data-ttu-id="0d931-562">Fai clic con il pulsante destro del mouse sull'icona della barra delle applicazioni e scegli Accedi o disconnetto.</span><span class="sxs-lookup"><span data-stu-id="0d931-562">Right-click the system tray icon, and select sign in or sign out.</span></span>

  - <span data-ttu-id="0d931-563">Uso di tasti di scelta rapida configurabili.</span><span class="sxs-lookup"><span data-stu-id="0d931-563">Using configurable keyboard shortcuts.</span></span>

- <span data-ttu-id="0d931-564">**Appartenenza al gruppo:** Quando un gruppo di agenti è selezionato, Response Group Agent Live visualizza l'elenco degli agenti in questo gruppo nel riquadro destro.</span><span class="sxs-lookup"><span data-stu-id="0d931-564">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="0d931-565">Se Skype for Business Server 2015 è in esecuzione nello stesso computer dell'applicazione, le informazioni sulla presenza e la scheda contatto vengono visualizzate in Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="0d931-565">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="0d931-566">Gli agenti possono inviare un messaggio istantaneo o chiamare altri agenti direttamente da lì.</span><span class="sxs-lookup"><span data-stu-id="0d931-566">Agents can send an IM or call other agents directly from there.</span></span>

- <span data-ttu-id="0d931-567">**Statistiche in tempo reale:** Response Group Agent Live fornisce statistiche in tempo reale per tutti i gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="0d931-567">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="0d931-568">La frequenza di aggiornamento è di un minuto.</span><span class="sxs-lookup"><span data-stu-id="0d931-568">The update frequency is one minute.</span></span> <span data-ttu-id="0d931-569">Quando un Response Group risponde a una chiamata, accanto al nome del gruppo viene aggiunto un indicatore visivo con il numero corrente di chiamate in coda.</span><span class="sxs-lookup"><span data-stu-id="0d931-569">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="0d931-570">La sospensione del puntatore su un gruppo mostra anche il tempo di attesa più lungo.</span><span class="sxs-lookup"><span data-stu-id="0d931-570">Pausing the pointer over a group also displays the longest waiting time.</span></span>

### <a name="requirements"></a><span data-ttu-id="0d931-571">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d931-571">Requirements</span></span>

<span data-ttu-id="0d931-572">L'agente di Response Group Live richiede .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="0d931-572">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="0d931-573">Inoltre, per sfruttare le funzionalità di presenza e scheda contatto, Skype for Business deve essere installato in locale (ed essere in esecuzione).</span><span class="sxs-lookup"><span data-stu-id="0d931-573">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>

#### <a name="configuration"></a><span data-ttu-id="0d931-574">Configurazione</span><span class="sxs-lookup"><span data-stu-id="0d931-574">Configuration</span></span>

<span data-ttu-id="0d931-575">Response Group Agent Live può essere personalizzato in base alle singole preferenze utilizzando la finestra di dialogo Opzioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0d931-575">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="0d931-576">Inoltre, l'amministratore può definire l'indirizzo host predefinito modificando direttamente la proprietà defaultHostAddress del file RGAgentLive.exe.config predefinito.</span><span class="sxs-lookup"><span data-stu-id="0d931-576">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="0d931-577">Nella figura seguente viene illustrata la finestra di dialogo Opzioni che gli agenti possono utilizzare per configurare l'indirizzo host e i tasti di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="0d931-577">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="0d931-578">Per accedere a questa finestra di dialogo, fare clic sul pulsante Opzioni in alto a destra nell'interfaccia principale.</span><span class="sxs-lookup"><span data-stu-id="0d931-578">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

![Finestra di dialogo Opzioni live agente Response Group.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

<span data-ttu-id="0d931-580">Nella configurazione live dell'agente Response Group è possibile personalizzare le tre impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-580">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

- <span data-ttu-id="0d931-581">Indirizzo host: si tratta in genere dell'FQDN del pool Web appartenente al pool principale dell'agente.</span><span class="sxs-lookup"><span data-stu-id="0d931-581">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="0d931-582">L'indirizzo esatto del servizio Response Group viene automaticamente derivato in background da queste informazioni (aggiungendo il percorso corretto dopo l'host).</span><span class="sxs-lookup"><span data-stu-id="0d931-582">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

- <span data-ttu-id="0d931-583">Collegamenti: i collegamenti esatti per l'accesso/disconnessione possono essere personalizzati.</span><span class="sxs-lookup"><span data-stu-id="0d931-583">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="0d931-584">L'unica limitazione è che entrambi i tasti di scelta rapida devono contenere il tasto "Logo Windows" (oltre ad almeno un altro tasto).</span><span class="sxs-lookup"><span data-stu-id="0d931-584">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>

- <span data-ttu-id="0d931-585">Inizia con Windows: l'applicazione può essere configurata per l'avvio automatico con Windows.</span><span class="sxs-lookup"><span data-stu-id="0d931-585">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

### <a name="examples"></a><span data-ttu-id="0d931-586">Esempi</span><span class="sxs-lookup"><span data-stu-id="0d931-586">Examples</span></span>

<span data-ttu-id="0d931-587">Nella figura seguente viene illustrato come chiamare o inviare un messaggio istantaneo a un altro agente facendo clic con il pulsante destro del mouse sul contatto nel riquadro destro.</span><span class="sxs-lookup"><span data-stu-id="0d931-587">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

![Effettuare una chiamata o inviare un messaggio istantaneo.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

<span data-ttu-id="0d931-589">Nella figura seguente viene illustrato il modo in cui Response Group Agent Live visualizza il numero corrente di chiamate nella coda e il tempo di attesa più lungo tra tutte queste chiamate in arrivo.</span><span class="sxs-lookup"><span data-stu-id="0d931-589">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

![Visualizzazione delle informazioni sulla coda.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a><span data-ttu-id="0d931-591">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="0d931-591">Summary</span></span>

<span data-ttu-id="0d931-592">L'accesso rapido e la disconnessione, l'appartenenza ai gruppi e le statistiche di base in tempo reale sono interessanti funzionalità degli agenti di Response Group disponibili solo all'esterno dell'applicazione dal servizio Response Group.</span><span class="sxs-lookup"><span data-stu-id="0d931-592">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="0d931-593">Con lo strumento Response Group Agent Live Resource Kit, gli amministratori di Skype for Business Server 2015 possono fornire agli agenti un'applicazione Windows che consente loro di eseguire attività in modo più rapido e grafico.</span><span class="sxs-lookup"><span data-stu-id="0d931-593">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

## <a name="sefautil"></a><span data-ttu-id="0d931-594">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="0d931-594">SEFAUtil</span></span>
<span data-ttu-id="0d931-595"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="0d931-595"><a name="SEFAUtil"> </a></span></span>

<span data-ttu-id="0d931-596">SEFAUtil (attivazione della funzionalità di estensione secondaria) è uno strumento da riga di comando che consente agli amministratori del software di comunicazione e agli agenti del supporto tecnico di Skype for Business Server 2015 di configurare l'squillo delegato, l'inoltro di chiamata, lo squillo simultaneo, le impostazioni delle chiamate del team e la risposta alle chiamate di gruppo per conto di un utente di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-596">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="0d931-597">Lo strumento consente inoltre agli amministratori di eseguire query nelle impostazioni di routing delle chiamate pubblicate per un determinato utente. Lo strumento SEFAUtil consente all'amministratore di abilitare/disabilitare/modificare l'inoltro di chiamata o di squillare contemporaneamente per conto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0d931-597">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="0d931-598">L'amministratore può specificare la destinazione (sotto forma di URI SIP) o utilizzare una destinazione già pubblicata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0d931-598">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="0d931-599">Questo strumento consente inoltre agli amministratori di aggiungere o rimuovere delegati o membri del gruppo di chiamate al team per conto dell'utente. Questo strumento è basato su Microsoft Unified Communications Managed API (UCMA) 3.0 e richiede che gli amministratori creino un'applicazione attendibile nell'archivio di gestione centrale per SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="0d931-599">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>

<span data-ttu-id="0d931-600">SEFAUtil (attivazione delle funzionalità di estensione secondaria) consente agli amministratori di Skype for Business Server 2015 e agli agenti dell'helpdesk di configurare lo squillo delegato, l'inoltro di chiamata, lo squillo simultaneo, le impostazioni delle chiamate del team e il prelievo delle chiamate di gruppo per conto di un utente di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-600">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="0d931-601">Questo strumento consente inoltre agli amministratori di eseguire query nelle impostazioni di routing delle chiamate pubblicate per un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="0d931-601">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

### <a name="description"></a><span data-ttu-id="0d931-602">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d931-602">Description</span></span>

<span data-ttu-id="0d931-603">La versione corrente di SEFAUtil è solo uno strumento da riga di comando. non esiste un'interfaccia utente grafica di supporto.</span><span class="sxs-lookup"><span data-stu-id="0d931-603">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="0d931-604">Questo strumento si basa su Microsoft Unified Communications Managed API (UCMA) 3.0.</span><span class="sxs-lookup"><span data-stu-id="0d931-604">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="0d931-605">Le funzionalità di questo strumento consentono agli amministratori e agli agenti dell'helpdesk di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-605">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

- <span data-ttu-id="0d931-606">Visualizzare tutte le impostazioni di instradamento delle chiamate per un utente (include inoltro di chiamata, delega, squillo simultaneo, chiamata al team e prelievo delle chiamate di gruppo)</span><span class="sxs-lookup"><span data-stu-id="0d931-606">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

- <span data-ttu-id="0d931-607">Abilitare/disabilitare/modificare l'impostazione di inoltro di chiamata (include timer di destinazione e senza risposta)</span><span class="sxs-lookup"><span data-stu-id="0d931-607">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

- <span data-ttu-id="0d931-608">Abilitare/disabilitare/modificare le configurazioni immediate di inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="0d931-608">Enable/disable/modify call-forwarding immediate configurations</span></span>

- <span data-ttu-id="0d931-609">Abilitare/disabilitare/modificare le impostazioni di delega</span><span class="sxs-lookup"><span data-stu-id="0d931-609">Enable/disable/modify delegation settings</span></span>

- <span data-ttu-id="0d931-610">Abilitare/disabilitare/modificare le impostazioni del gruppo di chiamate al team</span><span class="sxs-lookup"><span data-stu-id="0d931-610">Enable/disable/modify team-call group settings</span></span>

    > [!NOTE]
    > <span data-ttu-id="0d931-611">Novità dello strumento SEFAUtil di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0d931-611">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="0d931-612">Abilitare/disabilitare/modificare le impostazioni di squillo simultaneo (inclusa la destinazione)</span><span class="sxs-lookup"><span data-stu-id="0d931-612">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>

    > [!NOTE]
    > <span data-ttu-id="0d931-613">Novità dello strumento SEFAUtil di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0d931-613">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="0d931-614">Abilitare/disabilitare/modificare le impostazioni di prelievo delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="0d931-614">Enable/disable/modify group call pickup settings</span></span>

    > [!CAUTION]
    > <span data-ttu-id="0d931-615">Novità dello strumento SEFAUtil di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0d931-615">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

<span data-ttu-id="0d931-616">Questo strumento presenta le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-616">This tool has the following limitations:</span></span>

- <span data-ttu-id="0d931-617">Supportato solo per gli utenti ospitati in un pool di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0d931-617">Supported only for users homed in a Skype for Business Server pool</span></span>

- <span data-ttu-id="0d931-618">La modifica in blocco delle impostazioni di routing delle chiamate per più utenti non è supportata</span><span class="sxs-lookup"><span data-stu-id="0d931-618">Bulk-edit of call routing settings for several users is not supported</span></span>

### <a name="output"></a><span data-ttu-id="0d931-619">Output</span><span class="sxs-lookup"><span data-stu-id="0d931-619">Output</span></span>

<span data-ttu-id="0d931-620">La versione corrente di questo strumento fornisce l'output solo nella finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="0d931-620">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="0d931-621">Per informazioni dettagliate, vedere la sezione Esempi più avanti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="0d931-621">For details, see the Examples section later in this document.</span></span>

### <a name="purpose"></a><span data-ttu-id="0d931-622">Scopo</span><span class="sxs-lookup"><span data-stu-id="0d931-622">Purpose</span></span>

<span data-ttu-id="0d931-623">Di seguito sono riportati alcuni degli scenari principali in cui è possibile utilizzare questo strumento:</span><span class="sxs-lookup"><span data-stu-id="0d931-623">Following are some of the key scenarios where this tool may be used:</span></span>

- <span data-ttu-id="0d931-624">Bob è un dirigente ed è stato spostato in Skype for Business Server telefonia.</span><span class="sxs-lookup"><span data-stu-id="0d931-624">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="0d931-625">Ha la delega nel sistema PBX esistente.</span><span class="sxs-lookup"><span data-stu-id="0d931-625">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="0d931-626">Come parte del passaggio a Skype for Business Server 2015, l'amministratore è in grado di configurare il routing di Bob in modo che rifletta la configurazione di delega preesiste.</span><span class="sxs-lookup"><span data-stu-id="0d931-626">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>

- <span data-ttu-id="0d931-627">Alice sta viaggiando e si rende conto di aspettarsi una chiamata importante da uno dei suoi clienti.</span><span class="sxs-lookup"><span data-stu-id="0d931-627">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="0d931-628">Tuttavia, si trova in un hotel e non ha accesso a un computer.</span><span class="sxs-lookup"><span data-stu-id="0d931-628">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="0d931-629">Chiama l'helpdesk e richiede di inoltrare al suo numero di cellulare tutte le chiamate effettuate al suo numero di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0d931-629">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="0d931-630">Il personale dell'helpdesk è in grado di eseguire la configurazione per suo conto.</span><span class="sxs-lookup"><span data-stu-id="0d931-630">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

- <span data-ttu-id="0d931-631">Le chiamate di Joe al suo numero di lavoro andranno alla segreteria telefonica mobile ogni volta che è al lavoro; Tuttavia, gli elementi sembrano funzionare correttamente nella maggior parte delle altre posizioni.</span><span class="sxs-lookup"><span data-stu-id="0d931-631">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="0d931-632">Il tecnico dell'helpdesk è in grado di visualizzare la configurazione di instradamento di Joe e scopre che Joe ha squillo simultaneo configurato sul suo cellulare.</span><span class="sxs-lookup"><span data-stu-id="0d931-632">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="0d931-633">Il tecnico chiede a Joe la copertura mobile nel suo ufficio ed è in grado di determinare che la regola di squillo simultaneo è ciò che causa le chiamate alla segreteria telefonica mobile di Joe quando la copertura di rete è scarsa.</span><span class="sxs-lookup"><span data-stu-id="0d931-633">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>

- <span data-ttu-id="0d931-634">Mike è un nuovo dipendente di Contoso e si unisce a un nuovo team in cui tutti i membri sono configurati per la chiamata al team, quando viene abilitato per Skype for Business Server 2015, l'amministratore è in grado di impostare le impostazioni del gruppo di chiamate al team in modo da includere tutti i nuovi membri del team, inoltre, l'amministratore aggiunge Mike come membro del gruppo di chiamate al team per ognuno dei membri del suo team.</span><span class="sxs-lookup"><span data-stu-id="0d931-634">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

- <span data-ttu-id="0d931-635">Una pratica del servizio clienti nel reparto risorse umane di Contoso consiste nel fornire un servizio personale a tutti i chiamanti dopo la prima chiamata.</span><span class="sxs-lookup"><span data-stu-id="0d931-635">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="0d931-636">Dato che tutti i membri del reparto siedono molto vicini tra loro, avere tutti i telefoni squillare contemporaneamente con la chiamata al team è molto dirompente per il team.</span><span class="sxs-lookup"><span data-stu-id="0d931-636">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="0d931-637">Per fornire il servizio migliore senza interrompere i membri del team, l'amministratore di Skype for Business Server 2015 sfrutta la funzionalità di prelievo delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="0d931-637">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="0d931-638">L'amministratore aggiunge tutti i membri del reparto a un gruppo di prelievo e comunica al reparto il numero del gruppo di prelievo.</span><span class="sxs-lookup"><span data-stu-id="0d931-638">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="0d931-639">Quando Samantha è assente dalla sua scrivania, Joe nota il suo telefono squillare e procede per rispondere alla chiamata dalla sua scrivania.</span><span class="sxs-lookup"><span data-stu-id="0d931-639">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

### <a name="requirements"></a><span data-ttu-id="0d931-640">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d931-640">Requirements</span></span>

<span data-ttu-id="0d931-641">Lo strumento SEFAUtil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="0d931-641">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="0d931-642">UCMA 3.0 deve essere installato in tale computer.</span><span class="sxs-lookup"><span data-stu-id="0d931-642">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="0d931-643">Per eseguire lo strumento, è necessario creare una nuova applicazione attendibile con ID applicazione SEFAUtil in tale pool.</span><span class="sxs-lookup"><span data-stu-id="0d931-643">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="0d931-644">Creazione di una nuova applicazione attendibile per lo strumento SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="0d931-644">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="0d931-645">Lo strumento SEFAUTil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="0d931-645">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="0d931-646">Se necessario, l'aggiunta di un pool come nuovo pool di applicazioni attendibili può essere eseguita tramite Skype for Business Server Management Shell con il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="0d931-646">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > <span data-ttu-id="0d931-647">UCMA 3.0 deve essere installato in qualsiasi computer che verrà utilizzato per eseguire lo strumento SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="0d931-647">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

2. <span data-ttu-id="0d931-648">È necessario definire un'applicazione attendibile nella topologia per lo strumento SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="0d931-648">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="0d931-649">Per definire SEFAUtil come nuova applicazione attendibile, utilizzare Skype for Business Server Management Shell ed eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="0d931-649">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="0d931-650">Se necessario, è possibile utilizzare una porta diversa.</span><span class="sxs-lookup"><span data-stu-id="0d931-650">A different port can be used if needed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0d931-651">FQDN pool: FQDN del server o del pool che ospiterà l'applicazione SEFAUtil (in genere un > o un pool di Server Front End Skype for Business).</span><span class="sxs-lookup"><span data-stu-id="0d931-651">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server     > or pool).</span></span>
    > <span data-ttu-id="0d931-652">FQDN funzione di registrazione pool: FQDN del server Front End Skype for Business o del pool associato a questo pool di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0d931-652">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="0d931-653">Sito pool: ID sito del sito in cui si trova il pool.</span><span class="sxs-lookup"><span data-stu-id="0d931-653">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

3. <span data-ttu-id="0d931-654">Le modifiche alla topologia devono essere abilitate.</span><span class="sxs-lookup"><span data-stu-id="0d931-654">The topology changes need to be enabled.</span></span> <span data-ttu-id="0d931-655">L'abilitazione delle modifiche alla topologia può essere eseguita tramite Skype for Business Server Management Shell eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="0d931-655">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span>

   ```powershell
   Enable-CsToplogy
   ```

4. <span data-ttu-id="0d931-656">Se necessario, installare gli strumenti del Resource Kit di Skype for Business Server 2015 nel server che verrà utilizzato per eseguire lo strumento SEFAUtil (il server deve far parte di un pool di applicazioni attendibili).</span><span class="sxs-lookup"><span data-stu-id="0d931-656">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5. <span data-ttu-id="0d931-657">Verificare che SEFAUtil sia in esecuzione correttamente.</span><span class="sxs-lookup"><span data-stu-id="0d931-657">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="0d931-658">A tale scopo, eseguire lo strumento da un prompt dei comandi di Windows con privilegi di amministratore per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0d931-658">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="0d931-659">Per impostazione predefinita, lo strumento si trova in: "...\Programmi\Skype for Business Server 2015\Reskit".</span><span class="sxs-lookup"><span data-stu-id="0d931-659">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="0d931-660">Per visualizzare le impostazioni di inoltro di chiamata di un utente, utilizzare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="0d931-660">To display the call forwarding settings of a user, use the following command:</span></span>

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    <span data-ttu-id="0d931-661">Devono essere visualizzate le impostazioni di inoltro di chiamata dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0d931-661">The call forwarding settings of the user should be displayed.</span></span>

#### <a name="group-call-pickup"></a><span data-ttu-id="0d931-662">Risposta alle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="0d931-662">Group Call Pickup</span></span>

<span data-ttu-id="0d931-663">La risposta alle chiamate di gruppo richiede una configurazione aggiuntiva in Skype for Business Server 2015 per poter essere completamente abilitata.</span><span class="sxs-lookup"><span data-stu-id="0d931-663">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="0d931-664">Prima di assegnare gruppi di prelievo agli utenti, fare riferimento alla documentazione del prodotto group call pickup per i passaggi di pianificazione e distribuzione di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="0d931-664">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

### <a name="examples"></a><span data-ttu-id="0d931-665">Esempi</span><span class="sxs-lookup"><span data-stu-id="0d931-665">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="0d931-666">Visualizzare le impostazioni correnti di gestione delle chiamate</span><span class="sxs-lookup"><span data-stu-id="0d931-666">Display Current Call Handling Settings</span></span>

<span data-ttu-id="0d931-667">Il comando seguente visualizza la gestione delle chiamate per l'utente.</span><span class="sxs-lookup"><span data-stu-id="0d931-667">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> <span data-ttu-id="0d931-668">In questo esempio viene **utilizzata l'opzione /server** per specificare Skype for Business Server a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="0d931-668">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>

 <span data-ttu-id="0d931-669">**Output**</span><span class="sxs-lookup"><span data-stu-id="0d931-669">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="0d931-670">Impostare la destinazione di inoltro di chiamata/nessuna risposta</span><span class="sxs-lookup"><span data-stu-id="0d931-670">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="0d931-671">In questo esempio vengono impostate la destinazione di inoltro/nessuna risposta della chiamata e il ritardo dell'anello.</span><span class="sxs-lookup"><span data-stu-id="0d931-671">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="0d931-672">In questo caso, l'opzione /server non è disponibile. SEFAUtil tenta di eseguire l'individuazione automatica di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-672">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+14255550126@contoso.com;user=phone
```

 <span data-ttu-id="0d931-673">**Output**</span><span class="sxs-lookup"><span data-stu-id="0d931-673">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="0d931-674">Abilita inoltro di chiamata immediatamente</span><span class="sxs-lookup"><span data-stu-id="0d931-674">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="0d931-675">In questo esempio viene immediatamente abilitata l'inoltro di chiamata a un altro utente.</span><span class="sxs-lookup"><span data-stu-id="0d931-675">This example immediately enables call-forwarding to another user.</span></span>

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="0d931-676">**Output**</span><span class="sxs-lookup"><span data-stu-id="0d931-676">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="0d931-677">Disabilitare immediatamente l'inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="0d931-677">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="0d931-678">In questo esempio viene disabilitato immediatamente l'inoltro di chiamata.</span><span class="sxs-lookup"><span data-stu-id="0d931-678">This example immediately disables call forwarding.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com /disablefwdimmediate
```

 <span data-ttu-id="0d931-679">**Output**</span><span class="sxs-lookup"><span data-stu-id="0d931-679">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="0d931-680">Aggiungere un utente come delegato e configurare lo squillo simultaneo dei delegati</span><span class="sxs-lookup"><span data-stu-id="0d931-680">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="0d931-681">In questo esempio viene aggiunto un utente come delegato e viene impostato lo squillo simultaneo dei delegati.</span><span class="sxs-lookup"><span data-stu-id="0d931-681">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="0d931-682">**Output**</span><span class="sxs-lookup"><span data-stu-id="0d931-682">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="0d931-683">Modificare la regola di squillo simultaneo dei delegati</span><span class="sxs-lookup"><span data-stu-id="0d931-683">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="0d931-684">In questo esempio la regola di squillo simultaneo impostata nell'esempio precedente viene impostata sulla regola di squillo ritardato.</span><span class="sxs-lookup"><span data-stu-id="0d931-684">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="0d931-685">**Output**</span><span class="sxs-lookup"><span data-stu-id="0d931-685">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="0d931-686">Rimuovere il delegato</span><span class="sxs-lookup"><span data-stu-id="0d931-686">Remove the Delegate</span></span>

<span data-ttu-id="0d931-687">In questo esempio viene rimosso il delegato.</span><span class="sxs-lookup"><span data-stu-id="0d931-687">This example removes the delegate.</span></span>

> [!NOTE]
> <span data-ttu-id="0d931-688">Quando viene rimosso l'ultimo delegato, lo squillo del delegato viene disabilitato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0d931-688">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="0d931-689">**Output**</span><span class="sxs-lookup"><span data-stu-id="0d931-689">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="0d931-690">Aggiungere un delegato e configurare il Call-Forward alla regola delegati</span><span class="sxs-lookup"><span data-stu-id="0d931-690">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="0d931-691">In questo esempio viene aggiunto un delegato e viene impostata la regola di inoltro di chiamata ai delegati.</span><span class="sxs-lookup"><span data-stu-id="0d931-691">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="0d931-692">**Output**</span><span class="sxs-lookup"><span data-stu-id="0d931-692">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="0d931-693">Abilitare lo squillo simultaneo e impostare un numero di destinazione</span><span class="sxs-lookup"><span data-stu-id="0d931-693">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="0d931-694">In questo esempio viene abilitata la suoneria simultanea e viene impostato un numero di destinazione di squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="0d931-694">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="0d931-695">Per modificare il numero di destinazione di squillo simultaneo di un utente che ha già attivato lo squillo simultaneo, mantenere il comando con l'opzione /enablesimulring, altrimenti il numero di destinazione non verrà modificato.</span><span class="sxs-lookup"><span data-stu-id="0d931-695">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>

 <span data-ttu-id="0d931-696">**Output**</span><span class="sxs-lookup"><span data-stu-id="0d931-696">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="0d931-697">Disabilita squillo simultaneo</span><span class="sxs-lookup"><span data-stu-id="0d931-697">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="0d931-698">In questo esempio viene disabilitato lo squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="0d931-698">This example disables simultaneous ringing.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="0d931-699">**Output**</span><span class="sxs-lookup"><span data-stu-id="0d931-699">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="0d931-700">Aggiungere un membro del team per Team-Call e configurare lo squillo simultaneo al gruppo Team-Call membri</span><span class="sxs-lookup"><span data-stu-id="0d931-700">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="0d931-701">In questo esempio viene aggiunto un membro del team al gruppo di chiamate al team di un utente e viene abilitata la chiamata simultanea al gruppo di chiamate al team.</span><span class="sxs-lookup"><span data-stu-id="0d931-701">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="0d931-702">Se si aggiunge un membro al gruppo di chiamate al team di un utente, i gruppi di squilli simultanei degli utenti verranno automaticamente impostati per la simulazione del gruppo di chiamate al team.</span><span class="sxs-lookup"><span data-stu-id="0d931-702">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>

 <span data-ttu-id="0d931-703">**Output**</span><span class="sxs-lookup"><span data-stu-id="0d931-703">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="0d931-704">Rimuovere un membro dal Team-Call gruppo</span><span class="sxs-lookup"><span data-stu-id="0d931-704">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="0d931-705">In questo esempio viene rimosso un membro del team del gruppo di chiamate al team di un utente.</span><span class="sxs-lookup"><span data-stu-id="0d931-705">This example removes a team member of the team-call group of a user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="0d931-706">Se il membro rimosso è l'unico membro del gruppo di chiamate al team, il squillo simultaneo al gruppo di chiamate al team verrà disabilitato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0d931-706">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>

 <span data-ttu-id="0d931-707">**Output**</span><span class="sxs-lookup"><span data-stu-id="0d931-707">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="0d931-708">Impostare l'anello ritardato sul Team-Call gruppo</span><span class="sxs-lookup"><span data-stu-id="0d931-708">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="0d931-709">In questo esempio l'anello ritardato viene modificato in base all'impostazione del tempo del gruppo di chiamate del team.</span><span class="sxs-lookup"><span data-stu-id="0d931-709">This example changes the delayed ring to the team-call group time setting.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="0d931-710">**Output**</span><span class="sxs-lookup"><span data-stu-id="0d931-710">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="0d931-711">Abilita Team-Call</span><span class="sxs-lookup"><span data-stu-id="0d931-711">Enable Team-Call</span></span>

<span data-ttu-id="0d931-712">In questo esempio viene abilitata la chiamata al team per un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="0d931-712">This example enables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="0d931-713">Se il gruppo di chiamate al team dell'utente non dispone di membri, la chiamata al team non verrà abilitata.</span><span class="sxs-lookup"><span data-stu-id="0d931-713">If the team-call group of the user has no members, team-call won't be enabled.</span></span>

 <span data-ttu-id="0d931-714">**Output**</span><span class="sxs-lookup"><span data-stu-id="0d931-714">**Output**</span></span>

#### <a name="disable-team-call"></a><span data-ttu-id="0d931-715">Disabilita Team-Call</span><span class="sxs-lookup"><span data-stu-id="0d931-715">Disable Team-Call</span></span>

<span data-ttu-id="0d931-716">In questo esempio viene disabilitata la chiamata al team per un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="0d931-716">This example disables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="0d931-717">**Output**</span><span class="sxs-lookup"><span data-stu-id="0d931-717">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="0d931-718">Abilitare la risposta alle chiamate di gruppo e assegnare un gruppo di prelievo a un utente</span><span class="sxs-lookup"><span data-stu-id="0d931-718">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="0d931-719">In questo esempio viene assegnato un gruppo di prelievo a un utente e viene abilitata la risposta alle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="0d931-719">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="0d931-720">**Output**</span><span class="sxs-lookup"><span data-stu-id="0d931-720">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="0d931-721">Disabilitare la risposta alle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="0d931-721">Disable Group Call Pickup</span></span>

<span data-ttu-id="0d931-722">In questo esempio viene disabilitata la risposta alle chiamate di gruppo per un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="0d931-722">This example disables Group Call Pickup for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="0d931-723">Quando si disabilita la risposta alle chiamate di gruppo per un utente, il numero di gruppo assegnato all'utente non viene conservato.</span><span class="sxs-lookup"><span data-stu-id="0d931-723">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="0d931-724">Se successivamente si desidera riattivare la risposta alle chiamate di gruppo per tale utente, è necessario assegnare di nuovo il numero di gruppo con l'opzione /enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="0d931-724">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="0d931-725">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="0d931-725">SYSPrep.ps1</span></span>
<span data-ttu-id="0d931-726"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="0d931-726"><a name="SYSPrep"> </a></span></span>

### <a name="description"></a><span data-ttu-id="0d931-727">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d931-727">Description</span></span>

<span data-ttu-id="0d931-728">SYSPrep.ps1 è uno script Windows PowerShell che installerà i prerequisiti di Skype for Business Server 2015 seguenti nel computer con sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="0d931-728">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>

- <span data-ttu-id="0d931-729">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="0d931-729">Microsoft .Net Framework 4.5</span></span>

- <span data-ttu-id="0d931-730">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="0d931-730">Microsoft SQL Server Express</span></span>

- <span data-ttu-id="0d931-731">Windows Powershell versione 3.0</span><span class="sxs-lookup"><span data-stu-id="0d931-731">Windows Powershell version 3.0</span></span>

- <span data-ttu-id="0d931-732">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="0d931-732">Visual C++ 2010 Redistributable</span></span>

- <span data-ttu-id="0d931-733">Aggiornamenti di Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="0d931-733">Internet Information Server Updates</span></span>

- <span data-ttu-id="0d931-734">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="0d931-734">Windows Identity Foundation</span></span>

- <span data-ttu-id="0d931-735">File di Skype for Business Server 2015 Core</span><span class="sxs-lookup"><span data-stu-id="0d931-735">Skype for Business Server 2015 Core files</span></span>

  <span data-ttu-id="0d931-736">Anche se il nome dello script è simile allo Strumento preparazione sistema per i sistemi operativi Microsoft Windows, sono diversi.</span><span class="sxs-lookup"><span data-stu-id="0d931-736">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="0d931-737">Questo script installerà solo i prerequisiti necessari per Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-737">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="0d931-738">Dopo aver installato questi prerequisiti, è possibile utilizzare lo strumento SYSPrep di Windows per creare un'immagine del server.</span><span class="sxs-lookup"><span data-stu-id="0d931-738">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

### <a name="requirements"></a><span data-ttu-id="0d931-739">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d931-739">Requirements</span></span>

<span data-ttu-id="0d931-740">Prima di eseguire lo script SYSPrep.ps1, è necessario copiare i file dei prerequisiti in una cartella locale nel computer con sistema operativo Windows Server 2008 , ad esempio **D:\Setup.**</span><span class="sxs-lookup"><span data-stu-id="0d931-740">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="0d931-741">Questa cartella deve includere anche una copia dei file di Skype for Business Server 2015, in particolare **Setup.exe.**</span><span class="sxs-lookup"><span data-stu-id="0d931-741">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="0d931-742">I file dei prerequisiti possono essere scaricati dai percorsi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-742">The prerequisite files can be downloaded from the following locations:</span></span>


| <span data-ttu-id="0d931-743">**Prerequisito**</span><span class="sxs-lookup"><span data-stu-id="0d931-743">**Prerequisite**</span></span>                                | <span data-ttu-id="0d931-744">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="0d931-744">**Location**</span></span>                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| <span data-ttu-id="0d931-745">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="0d931-745">Microsoft .Net Framework 4.5</span></span>  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| <span data-ttu-id="0d931-746">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="0d931-746">Microsoft SQL Server Express 2008 R2</span></span>  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| <span data-ttu-id="0d931-747">Windows Powershell versione 3.0</span><span class="sxs-lookup"><span data-stu-id="0d931-747">Windows Powershell version 3.0</span></span>  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| <span data-ttu-id="0d931-748">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="0d931-748">Visual C++ 2010 Redistributable</span></span>  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| <span data-ttu-id="0d931-749">Aggiornamenti di Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="0d931-749">Internet Information Server Updates</span></span>  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| <span data-ttu-id="0d931-750">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="0d931-750">Windows Identity Foundation</span></span>  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| <span data-ttu-id="0d931-751">Skype for Business Server 2015 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="0d931-751">Skype for Business Server 2015 Setup.exe</span></span>  <br/> | <span data-ttu-id="0d931-752">Copia da elementi multimediali di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0d931-752">Copy from Skype for Business Server 2015 media</span></span>  <br/>                   |

### <a name="parameter"></a><span data-ttu-id="0d931-753">Parametro</span><span class="sxs-lookup"><span data-stu-id="0d931-753">Parameter</span></span>

<span data-ttu-id="0d931-754">Il **parametro -SetupFolder** accetta come argomento il percorso della directory dei file dei prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0d931-754">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

### <a name="examples"></a><span data-ttu-id="0d931-755">Esempi</span><span class="sxs-lookup"><span data-stu-id="0d931-755">Examples</span></span>

<span data-ttu-id="0d931-756">Per eseguire lo script SYSPrep.ps1 e installare i prerequisiti di Skype for Business Server 2015, eseguire il comando seguente da un prompt dei comandi con privilegi elevati:</span><span class="sxs-lookup"><span data-stu-id="0d931-756">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="0d931-757">Migrazione degli annunci di numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="0d931-757">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="0d931-758"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="0d931-758"><a name="UNAM"> </a></span></span>

<span data-ttu-id="0d931-759">Lo strumento di migrazione annunci di numeri non assegnati consente a un amministratore di Skype for Business Server 2015 di spostare la configurazione dei numeri non assegnati che viene serviceata dall'applicazione annuncio da un Skype for Business Server o pool di origine a un Skype for Business Server o pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0d931-759">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>

### <a name="description"></a><span data-ttu-id="0d931-760">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d931-760">Description</span></span>

<span data-ttu-id="0d931-761">Lo strumento di migrazione annunci di numeri non assegnati è uno script di Windows PowerShell che sposta la configurazione dei numeri non assegnati a cui è stata assegnata l'applicazione di annuncio di un server o di un pool di origine in un altro server o pool.</span><span class="sxs-lookup"><span data-stu-id="0d931-761">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="0d931-762">Quando viene eseguito, lo script di migrazione Annunci numero non assegnato eseguirà le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-762">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1. <span data-ttu-id="0d931-763">Spostare tutti i file audio utilizzati dagli annunci dei numeri non assegnati dell'applicazione annuncio ospitata nel server o nel pool di origine nell'archivio file del server o del pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0d931-763">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0d931-764">I file audio vengono rimossi dal pool di origine dopo essere stati copiati nel pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0d931-764">The audio files are removed from the source pool once they're copied to the destination pool.</span></span>

2. <span data-ttu-id="0d931-765">Spostare tutti gli annunci di numeri non assegnati configurati per l'applicazione annuncio ospitata nel server o nel pool di origine nel server o nel pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0d931-765">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3. <span data-ttu-id="0d931-766">Riassegnare al server o al pool di destinazione tutti gli intervalli di numeri non assegnati che vengono utilizzati dall'applicazione annuncio ospitata nel server o nel pool di origine.</span><span class="sxs-lookup"><span data-stu-id="0d931-766">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="0d931-767">Dopo aver eseguito correttamente lo script, tutti gli intervalli di numeri non assegnati che sono stati serviced dall'applicazione annuncio ospitata nel server o nel pool di origine verranno ora serviced con la stessa configurazione da parte del server o del pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0d931-767">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

### <a name="output"></a><span data-ttu-id="0d931-768">Output</span><span class="sxs-lookup"><span data-stu-id="0d931-768">Output</span></span>

<span data-ttu-id="0d931-769">Lo script **Move-CsAnnouncementConfiguration** indica nella finestra di Skype for Business Server Management Shell da dove viene eseguito l'esito positivo o negativo dell'operazione di migrazione.</span><span class="sxs-lookup"><span data-stu-id="0d931-769">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="0d931-770">Se l'esecuzione dell'operazione viene interrotta da un errore, gli intervalli di numeri non assegnati che sono stati spostati correttamente nella destinazione rimarranno nella destinazione in un formato operativo e il resto degli intervalli di numeri non assegnati da migrare rimarrà nell'origine, nonché in un formato operativo.</span><span class="sxs-lookup"><span data-stu-id="0d931-770">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="0d931-771">Per eseguire la migrazione completa del resto della configurazione, eseguire di nuovo lo script dopo aver corretto l'errore.</span><span class="sxs-lookup"><span data-stu-id="0d931-771">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

### <a name="purpose"></a><span data-ttu-id="0d931-772">Scopo</span><span class="sxs-lookup"><span data-stu-id="0d931-772">Purpose</span></span>

<span data-ttu-id="0d931-773">Lo script di migrazione Annunci numero non assegnato può essere utilizzato nei tre scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-773">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

- <span data-ttu-id="0d931-774">**Migrazione delle impostazioni di configurazione a una nuova versione di Skype for Business Server:** Contoso è in fase di migrazione a Skype for Business Server 2015 e nell'ambito del processo di migrazione l'amministratore di Skype for Business Server desidera spostare la configurazione dei numeri non assegnati a cui è stata assegnata l'applicazione annuncio dalla distribuzione di Lync Server 2013 alla nuova distribuzione di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-774">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="0d931-775">Per spostare le impostazioni di configurazione, l'amministratore di Skype for Business Server utilizza lo strumento di migrazione annunci di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="0d931-775">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

- <span data-ttu-id="0d931-776">**Rollback di una distribuzione da Skype for Business Server 2015 a Lync Server 2013:** A causa di fattori imprevisti, Contoso deve eseguire il rollback della migrazione alla nuova distribuzione di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0d931-776">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="0d931-777">Per ridurre al minimo le interruzioni del servizio, l'amministratore di Skype for Business Server utilizza lo strumento di migrazione annunci di numeri non assegnati per eseguire il rollback della configurazione dalla distribuzione di Skype for Business Server 2015 alla distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0d931-777">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>

- <span data-ttu-id="0d931-778">**Spostamento dei dati tra distribuzioni:** Contoso sta sostituendo tutti i server di un pool con server più nuovi.</span><span class="sxs-lookup"><span data-stu-id="0d931-778">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="0d931-779">La strategia consiste nel distribuire un nuovo pool di Skype for Business Server 2015, spostare tutti i dati dal vecchio al nuovo pool e quindi deprecato il pool precedente.</span><span class="sxs-lookup"><span data-stu-id="0d931-779">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="0d931-780">Dopo la distribuzione del nuovo pool, viene utilizzato lo strumento di migrazione Annunci numero non assegnato per spostare la configurazione dal pool precedente a quello nuovo.</span><span class="sxs-lookup"><span data-stu-id="0d931-780">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

#### <a name="requirements"></a><span data-ttu-id="0d931-781">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d931-781">Requirements</span></span>

<span data-ttu-id="0d931-782">Di seguito sono riportati i requisiti principali necessari per eseguire correttamente lo strumento:</span><span class="sxs-lookup"><span data-stu-id="0d931-782">The following are the main requirements needed to successfully run the tool:</span></span>

1. <span data-ttu-id="0d931-783">Lo script deve essere eseguito da un computer in cui è installato Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0d931-783">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>

2. <span data-ttu-id="0d931-784">L'applicazione annuncio deve essere distribuita correttamente nell'origine e nella destinazione skype for business server o pool.</span><span class="sxs-lookup"><span data-stu-id="0d931-784">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>

#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="0d931-785">Move-CsAnnouncementConfiguration script</span><span class="sxs-lookup"><span data-stu-id="0d931-785">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="0d931-786">Lo script Move-CsAnnouncementConfiguration richiede i due parametri descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0d931-786">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

![Move-CsAnnouncementConfiguration parametri.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a><span data-ttu-id="0d931-788">Esempi</span><span class="sxs-lookup"><span data-stu-id="0d931-788">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="0d931-789">Spostamento della configurazione degli annunci dei numeri non assegnati da un pool di Lync Server 2013 a un pool di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0d931-789">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="0d931-790">In questo esempio gli annunci di numeri non assegnati vengono spostati dal pool di origine (Lync Server 2013) al pool di destinazione (Skype for Business Server 2015).</span><span class="sxs-lookup"><span data-stu-id="0d931-790">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="0d931-791">Spostamento della configurazione degli annunci dei numeri non assegnati da un pool di Skype for Business Server 2015 a un pool di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d931-791">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="0d931-792">In questo esempio gli annunci di numeri non assegnati vengono spostati dal pool di origine (Skype for Business Server 2015) al pool di destinazione (Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="0d931-792">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="0d931-793">Dati web conf</span><span class="sxs-lookup"><span data-stu-id="0d931-793">Web Conf Data</span></span>
<span data-ttu-id="0d931-794"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="0d931-794"><a name="WebConfData"> </a></span></span>

<span data-ttu-id="0d931-795">Lo strumento Web Conf Data Consente a un amministratore del software di comunicazione di Skype for Business Server 2015 di avere un maggiore controllo sui dati associati alle conferenze Web di un organizzatore.</span><span class="sxs-lookup"><span data-stu-id="0d931-795">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="0d931-796">Gli scenari includono la possibilità di eliminare i dati di riunione di un utente specifico in base a criteri di timestamp.</span><span class="sxs-lookup"><span data-stu-id="0d931-796">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>

### <a name="description"></a><span data-ttu-id="0d931-797">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d931-797">Description</span></span>

<span data-ttu-id="0d931-798">Questo strumento consente all'amministratore di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d931-798">This tool allows the administrator to perform the following operations:</span></span>

1. <span data-ttu-id="0d931-799">Trovare tutti i dati delle conferenze Web associati a un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="0d931-799">Find all Web conferencing data associated with a single user.</span></span>

2. <span data-ttu-id="0d931-800">Eliminare tutti i dati delle conferenze Web associati a un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="0d931-800">Delete all Web conferencing data associated with a single user.</span></span>

3. <span data-ttu-id="0d931-801">Eliminare tutti i dati delle conferenze Web associati a un singolo utente precedente a una determinata data.</span><span class="sxs-lookup"><span data-stu-id="0d931-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4. <span data-ttu-id="0d931-802">Spostare tutti i dati delle conferenze Web associati a un singolo utente quando tale utente viene spostato da un pool a un altro.</span><span class="sxs-lookup"><span data-stu-id="0d931-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0d931-803">Gli strumenti del Resource Kit per Lync Server 2010 supportano lo spostamento di tutti i dati delle conferenze Web associati a un singolo utente quando tale utente viene spostato da un pool a un altro.</span><span class="sxs-lookup"><span data-stu-id="0d931-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="0d931-804">Questa funzionalità è ora deprecata da questo strumento a favore del **parametro MoveConferenceData.**</span><span class="sxs-lookup"><span data-stu-id="0d931-804">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="0d931-805">Per informazioni dettagliate su questo parametro, vedere il cmdlet [Move-CsUser.](/powershell/module/skype/move-csuser.md?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="0d931-805">For details about this parameter, see the [Move-CsUser](/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="0d931-806">Lo strumento elimina i dati delle riunioni solo per le riunioni inattive.</span><span class="sxs-lookup"><span data-stu-id="0d931-806">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="0d931-807">Le riunioni attive (o le riunioni nelle sessioni) non possono essere eliminate.</span><span class="sxs-lookup"><span data-stu-id="0d931-807">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="0d931-808">Questo strumento deve essere eseguito da un computer che si trova nello stesso pool dell'utente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0d931-808">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="0d931-809">L'utente i cui dati del contenuto della riunione vengono gestiti da questo strumento deve essere presente nello stesso pool di utenti.</span><span class="sxs-lookup"><span data-stu-id="0d931-809">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

### <a name="output"></a><span data-ttu-id="0d931-810">Output</span><span class="sxs-lookup"><span data-stu-id="0d931-810">Output</span></span>

<span data-ttu-id="0d931-811">Questo strumento restituisce i risultati di ognuna delle operazioni:</span><span class="sxs-lookup"><span data-stu-id="0d931-811">This tool outputs the results of each of the operations:</span></span>

- <span data-ttu-id="0d931-812">Se viene eseguita una query, lo strumento restituisce l'elenco di tutte le cartelle di dati delle riunioni inattive che dispongono di tale utente come organizzatore.</span><span class="sxs-lookup"><span data-stu-id="0d931-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

- <span data-ttu-id="0d931-813">Se viene eseguita un'eliminazione, lo strumento restituisce l'elenco di tutte le cartelle di dati delle riunioni i cui dati verranno eliminati.</span><span class="sxs-lookup"><span data-stu-id="0d931-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

### <a name="requirements"></a><span data-ttu-id="0d931-814">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d931-814">Requirements</span></span>

<span data-ttu-id="0d931-815">Lo strumento deve essere eseguito nello stesso pool in cui si trova attualmente l'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="0d931-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="0d931-816">Lo strumento deve essere eseguito con privilegi di amministratore con accesso all'archivio file di contenuto.</span><span class="sxs-lookup"><span data-stu-id="0d931-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

### <a name="examples"></a><span data-ttu-id="0d931-817">Esempi</span><span class="sxs-lookup"><span data-stu-id="0d931-817">Examples</span></span>

<span data-ttu-id="0d931-818">Nella tabella seguente vengono descritti i parametri, alcuni dei quali vengono utilizzati negli esempi.</span><span class="sxs-lookup"><span data-stu-id="0d931-818">The following table describes the parameters, some of which are used in the examples.</span></span>

![Parametri dello strumento Dati conf Web.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="0d931-820">Nell'esempio precedente viene illustrato il funzionamento di un comando di query.</span><span class="sxs-lookup"><span data-stu-id="0d931-820">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="0d931-821">L'output di un comando di questo tipo sarebbe un elenco di tutte le cartelle del contenuto delle riunioni interessate da questo strumento.</span><span class="sxs-lookup"><span data-stu-id="0d931-821">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="0d931-822">Il precedente è un esempio di comando delete.</span><span class="sxs-lookup"><span data-stu-id="0d931-822">The preceding is an example of a delete command.</span></span> <span data-ttu-id="0d931-823">Il comando delete rimuoverà tutte le cartelle riunioni inattive dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0d931-823">The delete command will remove all inactive meeting folders from this user.</span></span>

### <a name="summary"></a><span data-ttu-id="0d931-824">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="0d931-824">Summary</span></span>

<span data-ttu-id="0d931-825">Questo strumento può essere una risorsa preziosa per gli amministratori che necessitano di un controllo più preciso sui dati delle riunioni di conferenza.</span><span class="sxs-lookup"><span data-stu-id="0d931-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>