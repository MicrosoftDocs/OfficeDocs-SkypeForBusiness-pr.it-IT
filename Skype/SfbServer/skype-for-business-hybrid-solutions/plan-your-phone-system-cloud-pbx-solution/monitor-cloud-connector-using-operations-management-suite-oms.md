---
title: Monitorare Cloud Connector mediante Operations Management Suite (OMS)
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Leggere questo argomento per informazioni su come monitorare il Cloud Connector versione 2,1 e successiva usando Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: 6c63baf078dc865a4e3aef574cff30bedabf3819
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888635"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="8d109-103">Monitorare Cloud Connector mediante Operations Management Suite (OMS)</span><span class="sxs-lookup"><span data-stu-id="8d109-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

<span data-ttu-id="8d109-104">Leggere questo argomento per informazioni su come monitorare il Cloud Connector versione 2,1 e successiva usando Microsoft Operations Management Suite (OMS).</span><span class="sxs-lookup"><span data-stu-id="8d109-104">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="8d109-105">Ora è possibile monitorare il Cloud Connector versione 2,1 e la distribuzione successiva tramite Operations Management Suite (OMS), una soluzione di gestione IT cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8d109-105">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="8d109-106">Analisi del log OMS consente di monitorare e analizzare la disponibilità e le prestazioni delle risorse, incluse le macchine fisiche e virtuali.</span><span class="sxs-lookup"><span data-stu-id="8d109-106">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="8d109-107">Per altre informazioni su OMS e analisi dei log, vedere [cos'è Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span><span class="sxs-lookup"><span data-stu-id="8d109-107">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span></span>

<span data-ttu-id="8d109-108">Questo argomento contiene le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8d109-108">This topic contains the following sections:</span></span>

- <span data-ttu-id="8d109-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8d109-109">Prerequisites</span></span>

- <span data-ttu-id="8d109-110">Configurare il connettore Cloud per l'uso di OMS</span><span class="sxs-lookup"><span data-stu-id="8d109-110">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="8d109-111">Configurare OMS</span><span class="sxs-lookup"><span data-stu-id="8d109-111">Configure OMS</span></span>

- <span data-ttu-id="8d109-112">Analizzare gli avvisi nel repository di analisi del log</span><span class="sxs-lookup"><span data-stu-id="8d109-112">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="8d109-113">Set di monitoraggio consigliato</span><span class="sxs-lookup"><span data-stu-id="8d109-113">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8d109-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8d109-114">Prerequisites</span></span>

<span data-ttu-id="8d109-115">Prima di poter usare OMS per monitorare la distribuzione di Cloud Connector, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8d109-115">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="8d109-116">**Un account Azure e un'area di lavoro OMS.**</span><span class="sxs-lookup"><span data-stu-id="8d109-116">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="8d109-117">Se non si dispone già di un account Azure, sarà necessario crearne uno per usare analisi del log OMS.</span><span class="sxs-lookup"><span data-stu-id="8d109-117">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="8d109-118">Per informazioni su come creare un account Azure e configurare un'area di lavoro OMS, vedere [Introduzione a un'area di lavoro analisi log](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span><span class="sxs-lookup"><span data-stu-id="8d109-118">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="8d109-119">**Cloud Connector versione 2,1 o successiva**</span><span class="sxs-lookup"><span data-stu-id="8d109-119">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="8d109-120">**Log Analytics la ricerca di nuovi log** è necessaria per il monitoraggio del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="8d109-120">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="8d109-121">Per altre informazioni, vedere [aggiornare l'area di lavoro analisi log di Azure a nuova ricerca nel log](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span><span class="sxs-lookup"><span data-stu-id="8d109-121">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="8d109-122">Configurare il connettore Cloud per l'uso di OMS</span><span class="sxs-lookup"><span data-stu-id="8d109-122">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="8d109-123">Per usare OMS è necessario configurare l'ambiente locale del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="8d109-123">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="8d109-124">A tale scopo, è necessario l'ID e la chiave dell'area di lavoro OMS, che è possibile trovare usando il portale OMS come segue: impostazioni\>--origini connesse\> --server Windows:</span><span class="sxs-lookup"><span data-stu-id="8d109-124">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![Screenshot per l'OMS per il connettore Cloud](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="8d109-126">La modalità di configurazione del connettore Cloud per l'uso di OMS dipende dallo scenario:</span><span class="sxs-lookup"><span data-stu-id="8d109-126">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="8d109-127">**Se si sta installando un nuovo accessorio Cloud Connector o si vuole ridistribuire un accessorio**, seguire questa procedura prima di eseguire Install-CcAppliance:</span><span class="sxs-lookup"><span data-stu-id="8d109-127">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

    1. <span data-ttu-id="8d109-128">Nella sezione file CloudConnector. ini [Common] imposta il parametro OMSEnabled su true.</span><span class="sxs-lookup"><span data-stu-id="8d109-128">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

        <span data-ttu-id="8d109-129">Ogni volta che il connettore Cloud viene distribuito o aggiornato, tenterà di installare automaticamente l'agente OMS nella VM.</span><span class="sxs-lookup"><span data-stu-id="8d109-129">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="8d109-130">Abilita questa funzionalità in modo che l'agente OMS possa sopravvivere all'aggiornamento automatico di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="8d109-130">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

    2. <span data-ttu-id="8d109-131">Per configurare l'ID e la chiave OMS, eseguire set-CcCredential-AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="8d109-131">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="8d109-132">**Se si sta installando un agente OMS in un dispositivo Cloud Connector esistente**, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="8d109-132">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

    1. <span data-ttu-id="8d109-133">Nella sezione file CloudConnector. ini [Common] imposta OMSEnabled = true.</span><span class="sxs-lookup"><span data-stu-id="8d109-133">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

    2. <span data-ttu-id="8d109-134">Eseguire Import-CcConfiguration.</span><span class="sxs-lookup"><span data-stu-id="8d109-134">Run Import-CcConfiguration.</span></span> 

    3. <span data-ttu-id="8d109-135">Eseguire Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="8d109-135">Run Install-CcOMSAgent.</span></span> 

        > [!NOTE]
        > <span data-ttu-id="8d109-136">Se la credenziale OMSWorkspace non è mai stata impostata, vengono richieste le credenziali quando si esegue Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="8d109-136">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="8d109-137">**Se si vuole aggiornare l'ID o la chiave dell'area di lavoro OMS in un appliance di connessione cloud che ha già installato un agente OMS:**</span><span class="sxs-lookup"><span data-stu-id="8d109-137">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

    1. <span data-ttu-id="8d109-138">Per configurare l'ID e la chiave OMS, eseguire set-CcCredential-AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="8d109-138">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

    2. <span data-ttu-id="8d109-139">Per applicare gli aggiornamenti, eseguire Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="8d109-139">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="8d109-140">**Per tutti gli scenari, verificare che gli agenti siano connessi come segue:**</span><span class="sxs-lookup"><span data-stu-id="8d109-140">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="8d109-141">Nel portale OMS, passa a impostazioni-\> origini connesse-\> server Windows.</span><span class="sxs-lookup"><span data-stu-id="8d109-141">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="8d109-142">Verrà visualizzato un elenco di computer connessi.</span><span class="sxs-lookup"><span data-stu-id="8d109-142">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="8d109-143">Configurare OMS</span><span class="sxs-lookup"><span data-stu-id="8d109-143">Configure OMS</span></span>

<span data-ttu-id="8d109-144">Sarà quindi necessario specificare la configurazione OMS usando il portale OMS.</span><span class="sxs-lookup"><span data-stu-id="8d109-144">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="8d109-145">In particolare, è necessario:</span><span class="sxs-lookup"><span data-stu-id="8d109-145">Specifically, you will need to:</span></span>

- <span data-ttu-id="8d109-146">Specificare informazioni sui registri eventi e sui contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="8d109-146">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="8d109-147">Creare avvisi.</span><span class="sxs-lookup"><span data-stu-id="8d109-147">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="8d109-148">Specificare informazioni sui registri eventi e sui contatori delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="8d109-148">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="8d109-149">Nel portale OMS è necessario specificare le informazioni sui registri eventi e sui contatori delle prestazioni, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8d109-149">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="8d109-150">Accedere a impostazioni-\>dati-\>registri eventi di Windows e aggiungere i registri eventi per:</span><span class="sxs-lookup"><span data-stu-id="8d109-150">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="8d109-151">Lync Server</span><span class="sxs-lookup"><span data-stu-id="8d109-151">Lync Server</span></span>

   - <span data-ttu-id="8d109-152">Applicazione</span><span class="sxs-lookup"><span data-stu-id="8d109-152">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="8d109-153">È necessario immettere manualmente Lync Server nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="8d109-153">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="8d109-154">Non viene visualizzata come opzione nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="8d109-154">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="8d109-155">Per altre informazioni, vedere [origini dati del log eventi di Windows in analisi log](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="8d109-155">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="8d109-156">Accedere a impostazioni-\>dati-\> contatori delle prestazioni di Windows e aggiungere contatori delle prestazioni per:</span><span class="sxs-lookup"><span data-stu-id="8d109-156">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="8d109-157">**Contatori del livello di sistema operativo**.</span><span class="sxs-lookup"><span data-stu-id="8d109-157">**OS level counters**.</span></span> <span data-ttu-id="8d109-158">È possibile aggiungere contatori del livello di sistema operativo, ad esempio uso del processore, utilizzo della memoria, utilizzo della rete oppure usare soluzioni esistenti come capacità e prestazioni, Network Performance Monitor senza aggiungere contatori in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="8d109-158">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="8d109-159">Indipendentemente dal modo in cui si decide di monitorarli, Microsoft consiglia di monitorare questi contatori del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="8d109-159">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="8d109-160">**Contatori Skype for business**.</span><span class="sxs-lookup"><span data-stu-id="8d109-160">**Skype for Business counters**.</span></span> <span data-ttu-id="8d109-161">Ci sono numerosi contatori forniti da Skype for business.</span><span class="sxs-lookup"><span data-stu-id="8d109-161">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="8d109-162">È possibile trovare questi contatori accedendo a qualsiasi Mediation Server e aprendo performance monitor.</span><span class="sxs-lookup"><span data-stu-id="8d109-162">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="8d109-163">Questi contatori iniziano con "LS:".</span><span class="sxs-lookup"><span data-stu-id="8d109-163">These counters start with "LS:".</span></span> <span data-ttu-id="8d109-164">Microsoft consiglia di iniziare con i contatori di capacità seguenti al minimo e di aggiungerne altri interessanti:</span><span class="sxs-lookup"><span data-stu-id="8d109-164">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="8d109-165">Totale chiamate attive:</span><span class="sxs-lookup"><span data-stu-id="8d109-165">Total active calls:</span></span>

       - <span data-ttu-id="8d109-166">LS: MediationServer-chiamate in ingresso (_Total)\- Current</span><span class="sxs-lookup"><span data-stu-id="8d109-166">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

       - <span data-ttu-id="8d109-167">LS: MediationServer-chiamate in uscita (_Total)\- Current</span><span class="sxs-lookup"><span data-stu-id="8d109-167">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="8d109-168">Totale chiamate di bypass multimediali attivi:</span><span class="sxs-lookup"><span data-stu-id="8d109-168">Total active media bypass calls:</span></span>

       - <span data-ttu-id="8d109-169">LS: MediationServer-chiamata in ingresso (_Total)\- chiamate di bypass multimediali attive</span><span class="sxs-lookup"><span data-stu-id="8d109-169">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

       - <span data-ttu-id="8d109-170">LS: MediationServer-chiamate in uscita (_Total)\- chiamate di bypass multimediali attive</span><span class="sxs-lookup"><span data-stu-id="8d109-170">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="8d109-171">È necessario immettere manualmente i contatori delle prestazioni nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="8d109-171">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="8d109-172">Non vengono visualizzate come opzioni nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="8d109-172">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="8d109-173">Per altre informazioni, Vedi [origini dati delle prestazioni di Windows e Linux in analisi log](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="8d109-173">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="8d109-174">Creare avvisi</span><span class="sxs-lookup"><span data-stu-id="8d109-174">Create alerts</span></span>

<span data-ttu-id="8d109-175">In OMS sono disponibili due tipi di avvisi: numero di avvisi sui risultati e di avvisi di misura metrica.</span><span class="sxs-lookup"><span data-stu-id="8d109-175">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="8d109-176">Per altre informazioni sulla creazione di avvisi, vedere [uso delle regole di avviso in analisi log](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span><span class="sxs-lookup"><span data-stu-id="8d109-176">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="8d109-177">Quando si creano avvisi, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8d109-177">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="8d109-178">Verificare che l'avviso sia un avviso di tipo numero di risultati, ovvero la selezione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8d109-178">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="8d109-179">Le query demo richiedono che "numero di risultati" sia impostato su "maggiore di 0".</span><span class="sxs-lookup"><span data-stu-id="8d109-179">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="8d109-180">È consigliabile impostare la frequenza della finestra temporale e quella degli avvisi su 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="8d109-180">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="8d109-181">È consigliabile non abilitare "Elimina avvisi" per gli avvisi demo.</span><span class="sxs-lookup"><span data-stu-id="8d109-181">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="8d109-182">Per gli scenari di avviso tipici, Microsoft consiglia di creare una coppia di avvisi: un avviso di errore e un avviso di reimpostazione.</span><span class="sxs-lookup"><span data-stu-id="8d109-182">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="8d109-183">Per l'avviso di errore selezionare livello di gravità critico; per l'avviso Reimposta selezionare livello di gravità informativo.</span><span class="sxs-lookup"><span data-stu-id="8d109-183">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="8d109-184">Nelle sezioni seguenti viene descritto come creare avvisi di esempio.</span><span class="sxs-lookup"><span data-stu-id="8d109-184">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="8d109-185">**Creare una coppia di avvisi: "RTCMEDSRV non è in uso in Mediation Servers" e "RTCMEDSRV è di nuovo in uso in Mediation Servers"**</span><span class="sxs-lookup"><span data-stu-id="8d109-185">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="8d109-186">Per creare questa coppia di avvisi:</span><span class="sxs-lookup"><span data-stu-id="8d109-186">To create this alert pair:</span></span>

- <span data-ttu-id="8d109-187">La query per l'avviso di errore è:</span><span class="sxs-lookup"><span data-stu-id="8d109-187">The query for the error alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="8d109-188">La query usa il filtro computer in *cui il computer contiene "MediationServer"* .</span><span class="sxs-lookup"><span data-stu-id="8d109-188">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="8d109-189">Il filtro seleziona solo il computer il cui nome contiene la stringa "MediationServer".</span><span class="sxs-lookup"><span data-stu-id="8d109-189">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="8d109-190">Sostituire il filtro con il filtro del computer o semplicemente rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="8d109-190">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="8d109-191">Puoi creare filtri di stringhe complessi senza espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="8d109-191">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="8d109-192">Per altre informazioni, Vedi [operatori di stringhe](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span><span class="sxs-lookup"><span data-stu-id="8d109-192">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="8d109-193">Puoi anche scegliere di usare le espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="8d109-193">You can also choose to use regular expressions.</span></span> <span data-ttu-id="8d109-194">Inoltre, è possibile creare un gruppo di computer salvando una query di ricerca e usando il gruppo come filtro del computer nella query di avviso.</span><span class="sxs-lookup"><span data-stu-id="8d109-194">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="8d109-195">Per altre informazioni, vedere [gruppi di computer in ricerche nel log di analisi log](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span><span class="sxs-lookup"><span data-stu-id="8d109-195">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="8d109-196">Per ogni computer, la query di errore otterrà l'ultimo log eventi sia per l'avvio del servizio RTCMEDSRV che per l'arresto del servizio.</span><span class="sxs-lookup"><span data-stu-id="8d109-196">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="8d109-197">Verrà restituito un log se l'ultimo evento è l'evento di interruzione del servizio; restituirà Nothing se l'ultimo evento è l'evento Start del servizio.</span><span class="sxs-lookup"><span data-stu-id="8d109-197">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="8d109-198">In breve, la query restituisce un elenco di server il cui RTCMEDSRV viene interrotto nella finestra temporale.</span><span class="sxs-lookup"><span data-stu-id="8d109-198">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="8d109-199">La query per l'avviso di reimpostazione è:</span><span class="sxs-lookup"><span data-stu-id="8d109-199">The query for the reset alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="8d109-200">La query di reimpostazione fa esattamente la cosa opposta della query di errore.</span><span class="sxs-lookup"><span data-stu-id="8d109-200">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="8d109-201">Per ogni computer, ne restituirà uno se l'ultimo evento è l'evento Start del servizio; restituirà Nothing se l'ultimo evento è l'evento di interruzione del servizio.</span><span class="sxs-lookup"><span data-stu-id="8d109-201">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

<span data-ttu-id="8d109-202">**Creare una coppia di avvisi: "troppe chiamate simultanee in Mediation Server" e "chiamate simultanee ricadono al carico normale"**</span><span class="sxs-lookup"><span data-stu-id="8d109-202">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="8d109-203">Per creare questo avviso:</span><span class="sxs-lookup"><span data-stu-id="8d109-203">To create this alert:</span></span>

- <span data-ttu-id="8d109-204">La query per l'avviso di errore è:</span><span class="sxs-lookup"><span data-stu-id="8d109-204">The query for the error alert is:</span></span>

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="8d109-205">Per ogni computer, la query otterrà gli ultimi contatori per la chiamata in ingresso e la chiamata in uscita e somma questi due valori.</span><span class="sxs-lookup"><span data-stu-id="8d109-205">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="8d109-206">Verrà restituito un log se il valore somma supera 500; non restituirà nulla se non lo fa.</span><span class="sxs-lookup"><span data-stu-id="8d109-206">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="8d109-207">In breve, la query restituisce un elenco di server le cui chiamate simultanee sono troppe nella finestra temporale.</span><span class="sxs-lookup"><span data-stu-id="8d109-207">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="8d109-208">La query per l'avviso di reimpostazione è:</span><span class="sxs-lookup"><span data-stu-id="8d109-208">The query for the reset alert is:</span></span>

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="8d109-209">La query di reimpostazione fa esattamente la cosa opposta della query di errore.</span><span class="sxs-lookup"><span data-stu-id="8d109-209">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="8d109-210">Per ogni computer, la query otterrà gli ultimi contatori per la chiamata in ingresso e la chiamata in uscita e somma questi due valori.</span><span class="sxs-lookup"><span data-stu-id="8d109-210">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="8d109-211">Verrà restituito un log se il valore somma è minore di 500; non restituirà altro.</span><span class="sxs-lookup"><span data-stu-id="8d109-211">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

<span data-ttu-id="8d109-212">**Creare un avviso: avviso "utilizzo \> della CPU 90 o RTCMEDIARELAY interrotto nei server"**</span><span class="sxs-lookup"><span data-stu-id="8d109-212">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="8d109-213">Per creare questo avviso, la query è:</span><span class="sxs-lookup"><span data-stu-id="8d109-213">To create this alert, the query is:</span></span>

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="8d109-214">La query otterrà tutti i contatori di utilizzo del processore e l'evento di arresto del servizio da tutti i computer e restituirà un log se l'utilizzo del processore supera 90% o il servizio è sempre interrotto.</span><span class="sxs-lookup"><span data-stu-id="8d109-214">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="8d109-215">Analizzare gli avvisi nel repository di analisi del log</span><span class="sxs-lookup"><span data-stu-id="8d109-215">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="8d109-216">Per analizzare gli avvisi nel repository, usare la soluzione di gestione degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="8d109-216">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="8d109-217">Per altre informazioni, vedere [soluzione di gestione degli avvisi in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="8d109-217">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="8d109-218">Set di monitoraggio minimo consigliato</span><span class="sxs-lookup"><span data-stu-id="8d109-218">Recommended minimal monitoring set</span></span>

<span data-ttu-id="8d109-219">Per identificare i problemi relativi ai registri eventi e ai contatori delle prestazioni:</span><span class="sxs-lookup"><span data-stu-id="8d109-219">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="8d109-220">**Registri eventi.**</span><span class="sxs-lookup"><span data-stu-id="8d109-220">**Event logs.**</span></span> <span data-ttu-id="8d109-221">Per qualsiasi problema, deve essere presente una coppia di eventi, con un set di eventi per indicare che qualcosa non funziona, mentre l'altro indica che è tutto bene.</span><span class="sxs-lookup"><span data-stu-id="8d109-221">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="8d109-222">Per un determinato periodo di tempo, è l'ultimo evento registrato che indicherà se qualcosa non funziona per quel periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="8d109-222">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="8d109-223">**Contatori delle prestazioni.**</span><span class="sxs-lookup"><span data-stu-id="8d109-223">**Performance Counters.**</span></span> <span data-ttu-id="8d109-224">Deve essere presente una soglia per i contatori monitorati.</span><span class="sxs-lookup"><span data-stu-id="8d109-224">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="8d109-225">La tabella seguente elenca i servizi consigliati da Microsoft per il monitoraggio elencando gli ID evento Stop e Start:</span><span class="sxs-lookup"><span data-stu-id="8d109-225">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="8d109-226">Nome servizio</span><span class="sxs-lookup"><span data-stu-id="8d109-226">Service Name</span></span>  <br/> |<span data-ttu-id="8d109-227">Ruolo del server di destinazione</span><span class="sxs-lookup"><span data-stu-id="8d109-227">Target Server Role</span></span>  <br/> |<span data-ttu-id="8d109-228">Interrompi ID evento</span><span class="sxs-lookup"><span data-stu-id="8d109-228">Stop Event ID</span></span>  <br/> |<span data-ttu-id="8d109-229">Inizio ID evento</span><span class="sxs-lookup"><span data-stu-id="8d109-229">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8d109-230">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="8d109-230">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="8d109-231">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="8d109-231">Mediation Server</span></span>  <br/> |<span data-ttu-id="8d109-232">25003</span><span class="sxs-lookup"><span data-stu-id="8d109-232">25003</span></span>  <br/> |<span data-ttu-id="8d109-233">25002</span><span class="sxs-lookup"><span data-stu-id="8d109-233">25002</span></span>  <br/> |
|<span data-ttu-id="8d109-234">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="8d109-234">RTCSRV</span></span>  <br/> |<span data-ttu-id="8d109-235">Edge Server</span><span class="sxs-lookup"><span data-stu-id="8d109-235">Edge Server</span></span>  <br/> |<span data-ttu-id="8d109-236">12289</span><span class="sxs-lookup"><span data-stu-id="8d109-236">12289</span></span>  <br/> |<span data-ttu-id="8d109-237">12288</span><span class="sxs-lookup"><span data-stu-id="8d109-237">12288</span></span>  <br/> |
|<span data-ttu-id="8d109-238">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="8d109-238">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="8d109-239">Edge Server</span><span class="sxs-lookup"><span data-stu-id="8d109-239">Edge Server</span></span>  <br/> |<span data-ttu-id="8d109-240">19003</span><span class="sxs-lookup"><span data-stu-id="8d109-240">19003</span></span>  <br/> |<span data-ttu-id="8d109-241">19002</span><span class="sxs-lookup"><span data-stu-id="8d109-241">19002</span></span>  <br/> |
|<span data-ttu-id="8d109-242">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="8d109-242">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="8d109-243">Edge Server</span><span class="sxs-lookup"><span data-stu-id="8d109-243">Edge Server</span></span>  <br/> |<span data-ttu-id="8d109-244">22003</span><span class="sxs-lookup"><span data-stu-id="8d109-244">22003</span></span>  <br/> |<span data-ttu-id="8d109-245">22002</span><span class="sxs-lookup"><span data-stu-id="8d109-245">22002</span></span>  <br/> |

<span data-ttu-id="8d109-246">Nella tabella seguente sono elencati i problemi di rete consigliati da Microsoft per il monitoraggio:</span><span class="sxs-lookup"><span data-stu-id="8d109-246">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="8d109-247">Nome del monitor</span><span class="sxs-lookup"><span data-stu-id="8d109-247">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="8d109-248">Ruolo del server di destinazione</span><span class="sxs-lookup"><span data-stu-id="8d109-248">Target Server Role</span></span>  <br/> | <span data-ttu-id="8d109-249">Espressione ID evento successo</span><span class="sxs-lookup"><span data-stu-id="8d109-249">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="8d109-250">Espressione ID evento errore</span><span class="sxs-lookup"><span data-stu-id="8d109-250">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="8d109-251">Esempio di errore</span><span class="sxs-lookup"><span data-stu-id="8d109-251">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="8d109-252">Errore di connettività del gateway Mediation Server</span><span class="sxs-lookup"><span data-stu-id="8d109-252">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="8d109-253">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="8d109-253">Mediation Server</span></span>  <br/>   | <span data-ttu-id="8d109-254">25062</span><span class="sxs-lookup"><span data-stu-id="8d109-254">25062</span></span>                              |                                  | <span data-ttu-id="8d109-255">25002</span><span class="sxs-lookup"><span data-stu-id="8d109-255">25002</span></span>  <br/>           |
| <span data-ttu-id="8d109-256">Errore di completamento chiamata di Mediation Server a gateway</span><span class="sxs-lookup"><span data-stu-id="8d109-256">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="8d109-257">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="8d109-257">Mediation Server</span></span>  <br/>   | <span data-ttu-id="8d109-258">25064</span><span class="sxs-lookup"><span data-stu-id="8d109-258">25064</span></span>                              |                                  | <span data-ttu-id="8d109-259">25002</span><span class="sxs-lookup"><span data-stu-id="8d109-259">25002</span></span>  <br/>           |
| <span data-ttu-id="8d109-260">Problemi di rete critici</span><span class="sxs-lookup"><span data-stu-id="8d109-260">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="8d109-261">Edge Server</span><span class="sxs-lookup"><span data-stu-id="8d109-261">Edge Server</span></span>  <br/>        | <span data-ttu-id="8d109-262">14353</span><span class="sxs-lookup"><span data-stu-id="8d109-262">14353</span></span>                              |                                  | <span data-ttu-id="8d109-263">12288</span><span class="sxs-lookup"><span data-stu-id="8d109-263">12288</span></span>  <br/>           |

<span data-ttu-id="8d109-264">Di seguito sono elencati i contatori delle capacità delle chiamate da monitorare.</span><span class="sxs-lookup"><span data-stu-id="8d109-264">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="8d109-265">Questi numeri devono essere inferiori a 500 per Cloud Connector Standard Edition; minore di 50 per il Cloud Connector Minimum Edition.</span><span class="sxs-lookup"><span data-stu-id="8d109-265">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="8d109-266">LS: MediationServer-chiamate in ingresso (_Total)\- Current</span><span class="sxs-lookup"><span data-stu-id="8d109-266">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="8d109-267">LS: MediationServer-chiamate in uscita (_Total)\- Current</span><span class="sxs-lookup"><span data-stu-id="8d109-267">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="8d109-268">LS: MediationServer-chiamata in ingresso (_Total)\- chiamate di bypass multimediali attive</span><span class="sxs-lookup"><span data-stu-id="8d109-268">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="8d109-269">LS: MediationServer-chiamate in uscita (_Total)\- chiamate di bypass multimediali attive</span><span class="sxs-lookup"><span data-stu-id="8d109-269">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="8d109-270">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d109-270">See also</span></span>

<span data-ttu-id="8d109-271">Per altre informazioni sull'uso di OMS, vedere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8d109-271">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="8d109-272">Trovare i dati con ricerche log in analisi log</span><span class="sxs-lookup"><span data-stu-id="8d109-272">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="8d109-273">Informazioni di riferimento sul linguaggio di analisi del log di Azure</span><span class="sxs-lookup"><span data-stu-id="8d109-273">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="8d109-274">Informazioni sugli avvisi in analisi log</span><span class="sxs-lookup"><span data-stu-id="8d109-274">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="8d109-275">Connettere i computer Windows al servizio analisi log in Azure</span><span class="sxs-lookup"><span data-stu-id="8d109-275">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


