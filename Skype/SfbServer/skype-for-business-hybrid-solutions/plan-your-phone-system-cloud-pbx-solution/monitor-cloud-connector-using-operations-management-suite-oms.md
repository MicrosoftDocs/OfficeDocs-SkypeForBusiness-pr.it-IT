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
description: Leggere questo argomento per informazioni su come monitorare il Cloud Connector versione 2,1 e versioni successive tramite Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: eca2f56bf564e376717a42bd8d297710905f8dc6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359092"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="9a012-103">Monitorare Cloud Connector mediante Operations Management Suite (OMS)</span><span class="sxs-lookup"><span data-stu-id="9a012-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

> [!Important]
> <span data-ttu-id="9a012-104">Cloud Connector Edition si ritirerà il 31 luglio 2021 insieme a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="9a012-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="9a012-105">Dopo che l'organizzazione ha eseguito l'aggiornamento ai team, informazioni su come connettere la rete di telefonia locale ai team che utilizzano il [routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="9a012-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="9a012-106">Leggere questo argomento per informazioni su come monitorare il Cloud Connector versione 2,1 e versioni successive tramite Microsoft Operations Management Suite (OMS).</span><span class="sxs-lookup"><span data-stu-id="9a012-106">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="9a012-107">È ora possibile monitorare il Cloud Connector versione 2,1 e successive tramite Operations Management Suite (OMS), una soluzione di gestione IT di Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="9a012-107">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="9a012-108">L'analisi dei log OMS consente di monitorare e analizzare la disponibilità e le prestazioni delle risorse, incluse le macchine fisiche e virtuali.</span><span class="sxs-lookup"><span data-stu-id="9a012-108">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="9a012-109">Per ulteriori informazioni su OMS e analisi dei log, vedere [che cos'è Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span><span class="sxs-lookup"><span data-stu-id="9a012-109">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span></span>

<span data-ttu-id="9a012-110">In questa sezione sono contenute le seguenti sezioni:</span><span class="sxs-lookup"><span data-stu-id="9a012-110">This topic contains the following sections:</span></span>

- <span data-ttu-id="9a012-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="9a012-111">Prerequisites</span></span>

- <span data-ttu-id="9a012-112">Configurare il connettore Cloud per l'utilizzo di OMS</span><span class="sxs-lookup"><span data-stu-id="9a012-112">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="9a012-113">Configurare OMS</span><span class="sxs-lookup"><span data-stu-id="9a012-113">Configure OMS</span></span>

- <span data-ttu-id="9a012-114">Analizzare gli avvisi nel repository di analisi dei log</span><span class="sxs-lookup"><span data-stu-id="9a012-114">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="9a012-115">Set di monitoraggio consigliato</span><span class="sxs-lookup"><span data-stu-id="9a012-115">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9a012-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="9a012-116">Prerequisites</span></span>

<span data-ttu-id="9a012-117">Prima di poter utilizzare OMS per monitorare la distribuzione dei connettori cloud, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a012-117">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="9a012-118">**Un account di Azure e un'area di lavoro OMS.**</span><span class="sxs-lookup"><span data-stu-id="9a012-118">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="9a012-119">Se non si dispone già di un account di Azure, sarà necessario crearne uno per utilizzare analisi del registro OMS.</span><span class="sxs-lookup"><span data-stu-id="9a012-119">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="9a012-120">Per informazioni su come creare un account di Azure e configurare un'area di lavoro OMS, vedere [Introduzione a un'area di lavoro di analisi dei log](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span><span class="sxs-lookup"><span data-stu-id="9a012-120">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="9a012-121">**Cloud Connector versione 2,1 o successiva**</span><span class="sxs-lookup"><span data-stu-id="9a012-121">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="9a012-122">**Log Analytics il nuovo log Search** è necessario per il monitoraggio dei connettori cloud.</span><span class="sxs-lookup"><span data-stu-id="9a012-122">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="9a012-123">Per ulteriori informazioni, vedere [upgrade your Azure log Analytics Workspace to New Log Search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span><span class="sxs-lookup"><span data-stu-id="9a012-123">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="9a012-124">Configurare il connettore Cloud per l'utilizzo di OMS</span><span class="sxs-lookup"><span data-stu-id="9a012-124">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="9a012-125">È necessario configurare l'ambiente locale del connettore Cloud per l'utilizzo di OMS.</span><span class="sxs-lookup"><span data-stu-id="9a012-125">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="9a012-126">A tale scopo, è necessario l'ID e la chiave dell'area di lavoro OMS, che è possibile trovare utilizzando il portale OMS come segue: impostazioni-- \> origini connesse-- \> server Windows:</span><span class="sxs-lookup"><span data-stu-id="9a012-126">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![Screenshot per il connettore Cloud OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="9a012-128">La modalità di configurazione del connettore Cloud per l'utilizzo di OMS dipende dallo scenario:</span><span class="sxs-lookup"><span data-stu-id="9a012-128">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="9a012-129">**Se si sta installando un nuovo accessorio Cloud Connector o si desidera ridistribuire un dispositivo**, attenersi alla seguente procedura prima di eseguire Install-CcAppliance:</span><span class="sxs-lookup"><span data-stu-id="9a012-129">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

    1. <span data-ttu-id="9a012-130">Nella sezione file CloudConnector.ini [Common] impostare il parametro OMSEnabled su true.</span><span class="sxs-lookup"><span data-stu-id="9a012-130">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

        <span data-ttu-id="9a012-131">Ogni volta che il connettore Cloud viene distribuito o aggiornato, tenterà di installare l'agente OMS automaticamente sulle macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="9a012-131">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="9a012-132">Abilitare questa funzionalità in modo che l'agente OMS possa sopravvivere all'aggiornamento automatico del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="9a012-132">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

    2. <span data-ttu-id="9a012-133">Per configurare l'ID OMS e la chiave, eseguire set-CcCredential-AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="9a012-133">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="9a012-134">**Se si sta installando un agente OMS su un dispositivo di connessione cloud esistente**, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="9a012-134">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

    1. <span data-ttu-id="9a012-135">Nella sezione file CloudConnector.ini [Common] impostare OMSEnabled = true.</span><span class="sxs-lookup"><span data-stu-id="9a012-135">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

    2. <span data-ttu-id="9a012-136">Eseguire Import-CcConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9a012-136">Run Import-CcConfiguration.</span></span> 

    3. <span data-ttu-id="9a012-137">Eseguire Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="9a012-137">Run Install-CcOMSAgent.</span></span> 

        > [!NOTE]
        > <span data-ttu-id="9a012-138">Se non è mai stata impostata la credenziale OMSWorkspace, viene richiesto di utilizzare le credenziali quando si esegue Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="9a012-138">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="9a012-139">**Se si desidera aggiornare l'ID dell'area di lavoro OMS o la chiave in un dispositivo di connessione cloud che ha già installato un agente OMS:**</span><span class="sxs-lookup"><span data-stu-id="9a012-139">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

    1. <span data-ttu-id="9a012-140">Per configurare l'ID OMS e la chiave, eseguire set-CcCredential-AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="9a012-140">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

    2. <span data-ttu-id="9a012-141">Per applicare gli aggiornamenti, eseguire Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="9a012-141">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="9a012-142">**Per tutti gli scenari, verificare che gli agenti siano connessi come indicato di seguito:**</span><span class="sxs-lookup"><span data-stu-id="9a012-142">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="9a012-143">Nel portale OMS accedere a origini connesse alle impostazioni \> - \> server Windows.</span><span class="sxs-lookup"><span data-stu-id="9a012-143">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="9a012-144">Verrà visualizzato un elenco di computer connessi.</span><span class="sxs-lookup"><span data-stu-id="9a012-144">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="9a012-145">Configurare OMS</span><span class="sxs-lookup"><span data-stu-id="9a012-145">Configure OMS</span></span>

<span data-ttu-id="9a012-146">Successivamente, è necessario specificare la configurazione OMS tramite il portale OMS.</span><span class="sxs-lookup"><span data-stu-id="9a012-146">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="9a012-147">In particolare, sarà necessario:</span><span class="sxs-lookup"><span data-stu-id="9a012-147">Specifically, you will need to:</span></span>

- <span data-ttu-id="9a012-148">Specificare informazioni sui registri eventi e sui contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="9a012-148">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="9a012-149">Creazione avvisi</span><span class="sxs-lookup"><span data-stu-id="9a012-149">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="9a012-150">Specificare informazioni sui registri eventi e sui contatori delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="9a012-150">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="9a012-151">Nel portale OMS, è necessario specificare le informazioni sui registri eventi e sui contatori delle prestazioni, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9a012-151">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="9a012-152">Passare a impostazioni- \> dati- \> registri eventi di Windows e aggiungere registri eventi per:</span><span class="sxs-lookup"><span data-stu-id="9a012-152">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="9a012-153">Lync Server</span><span class="sxs-lookup"><span data-stu-id="9a012-153">Lync Server</span></span>

   - <span data-ttu-id="9a012-154">Applicazione</span><span class="sxs-lookup"><span data-stu-id="9a012-154">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="9a012-155">È necessario immettere manualmente Lync Server nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="9a012-155">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="9a012-156">Non viene visualizzata come opzione nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="9a012-156">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="9a012-157">Per ulteriori informazioni, vedere [origini dati del registro eventi di Windows nell'analisi dei log](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="9a012-157">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="9a012-158">Andare a Settings- \> data- \> Windows Performance Counters e aggiungere contatori delle prestazioni per:</span><span class="sxs-lookup"><span data-stu-id="9a012-158">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="9a012-159">**Contatori del livello del sistema operativo**.</span><span class="sxs-lookup"><span data-stu-id="9a012-159">**OS level counters**.</span></span> <span data-ttu-id="9a012-160">È possibile aggiungere contatori a livello di sistema operativo, ad esempio l'utilizzo del processore, l'utilizzo della memoria, l'utilizzo della rete oppure è possibile utilizzare soluzioni esistenti quali capacità e prestazioni, Network Performance Monitor senza aggiungere contatori in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="9a012-160">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="9a012-161">Indipendentemente dal modo in cui si decide di monitorarli, Microsoft consiglia di monitorare questi contatori del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="9a012-161">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="9a012-162">**Contatori Skype for business**.</span><span class="sxs-lookup"><span data-stu-id="9a012-162">**Skype for Business counters**.</span></span> <span data-ttu-id="9a012-163">Sono disponibili numerosi contatori forniti da Skype for business.</span><span class="sxs-lookup"><span data-stu-id="9a012-163">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="9a012-164">È possibile trovare questi contatori accedendo a qualsiasi Mediation Server e aprendo il monitoraggio delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="9a012-164">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="9a012-165">Questi contatori iniziano con "LS:".</span><span class="sxs-lookup"><span data-stu-id="9a012-165">These counters start with "LS:".</span></span> <span data-ttu-id="9a012-166">Microsoft consiglia di iniziare con i contatori di capacità seguenti almeno e aggiungere altri che sono di interesse:</span><span class="sxs-lookup"><span data-stu-id="9a012-166">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="9a012-167">Totale chiamate attive:</span><span class="sxs-lookup"><span data-stu-id="9a012-167">Total active calls:</span></span>

       - <span data-ttu-id="9a012-168">LS: MediationServer-chiamate in entrata (_Total) \- correnti</span><span class="sxs-lookup"><span data-stu-id="9a012-168">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

       - <span data-ttu-id="9a012-169">LS: MediationServer-chiamate in uscita (_Total) \- correnti</span><span class="sxs-lookup"><span data-stu-id="9a012-169">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="9a012-170">Totale chiamate di bypass multimediale attivo:</span><span class="sxs-lookup"><span data-stu-id="9a012-170">Total active media bypass calls:</span></span>

       - <span data-ttu-id="9a012-171">LS: MediationServer-chiamate in entrata (_Total) \- chiamate di bypass multimediale attive</span><span class="sxs-lookup"><span data-stu-id="9a012-171">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

       - <span data-ttu-id="9a012-172">LS: MediationServer-chiamate in uscita (_Total) le \- chiamate di bypass multimediale attivo</span><span class="sxs-lookup"><span data-stu-id="9a012-172">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="9a012-173">È necessario immettere manualmente i contatori delle prestazioni nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="9a012-173">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="9a012-174">Non vengono visualizzate come opzioni nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="9a012-174">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="9a012-175">Per ulteriori informazioni, vedere [Windows and Linux Performance Data Sources in log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="9a012-175">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="9a012-176">Creare avvisi</span><span class="sxs-lookup"><span data-stu-id="9a012-176">Create alerts</span></span>

<span data-ttu-id="9a012-177">Sono disponibili due tipi di avvisi in OMS: numero di avvisi sui risultati e avvisi di misura metrica.</span><span class="sxs-lookup"><span data-stu-id="9a012-177">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="9a012-178">Per ulteriori informazioni sulla creazione di avvisi, vedere [utilizzo delle regole di avviso nell'analisi dei log](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span><span class="sxs-lookup"><span data-stu-id="9a012-178">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="9a012-179">Quando si creano avvisi, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9a012-179">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="9a012-180">Verificare che l'avviso sia un avviso di numero di risultati, che è la selezione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9a012-180">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="9a012-181">Le query demo richiedono che il "numero di risultati" sia impostato su "maggiore di 0".</span><span class="sxs-lookup"><span data-stu-id="9a012-181">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="9a012-182">Si consiglia di impostare la frequenza delle finestre temporali e degli avvisi su 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="9a012-182">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="9a012-183">Si consiglia di non abilitare "Ometti avvisi" per gli avvisi demo.</span><span class="sxs-lookup"><span data-stu-id="9a012-183">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="9a012-184">Per gli scenari di avviso tipici, Microsoft consiglia di creare una coppia di avvisi: un avviso di errore e un avviso di reimpostazione.</span><span class="sxs-lookup"><span data-stu-id="9a012-184">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="9a012-185">Per l'avviso di errore, selezionare livello di gravità critico. per l'avviso Reimposta, selezionare livello di gravità informativo.</span><span class="sxs-lookup"><span data-stu-id="9a012-185">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="9a012-186">Nelle sezioni seguenti viene descritto come creare avvisi di esempio.</span><span class="sxs-lookup"><span data-stu-id="9a012-186">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="9a012-187">**Creare una coppia di avvisi: "RTCMEDSRV non è in esecuzione in Mediation Server" e "RTCMEDSRV è tornato in esecuzione in Mediation Server"**</span><span class="sxs-lookup"><span data-stu-id="9a012-187">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="9a012-188">Per creare questa coppia di avvisi:</span><span class="sxs-lookup"><span data-stu-id="9a012-188">To create this alert pair:</span></span>

- <span data-ttu-id="9a012-189">La query per l'avviso di errore è la seguente:</span><span class="sxs-lookup"><span data-stu-id="9a012-189">The query for the error alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="9a012-190">La query utilizza il filtro computer in  *cui il computer contiene "MediationServer"*  .</span><span class="sxs-lookup"><span data-stu-id="9a012-190">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="9a012-191">Il filtro seleziona solo il computer il cui nome contiene la stringa "MediationServer".</span><span class="sxs-lookup"><span data-stu-id="9a012-191">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="9a012-192">È necessario sostituire il filtro con il proprio filtro del computer o semplicemente rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="9a012-192">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="9a012-193">È possibile creare filtri stringa complessi senza espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="9a012-193">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="9a012-194">Per ulteriori informazioni, vedere [String Operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span><span class="sxs-lookup"><span data-stu-id="9a012-194">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="9a012-195">È anche possibile scegliere di utilizzare le espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="9a012-195">You can also choose to use regular expressions.</span></span> <span data-ttu-id="9a012-196">Inoltre, è possibile creare un gruppo di computer salvando una query di ricerca e usando quel gruppo come filtro del computer nella query di avviso.</span><span class="sxs-lookup"><span data-stu-id="9a012-196">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="9a012-197">Per ulteriori informazioni, vedere [gruppi di computer nelle ricerche dei log di analisi](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups)log.</span><span class="sxs-lookup"><span data-stu-id="9a012-197">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="9a012-198">Per ogni computer, la query di errore otterrà l'ultimo registro eventi sia per l'avvio del servizio di RTCMEDSRV che per l'arresto del servizio.</span><span class="sxs-lookup"><span data-stu-id="9a012-198">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="9a012-199">Restituirà un log se l'ultimo evento è l'evento di arresto del servizio; restituirà Nothing se l'ultimo evento è l'evento di avvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="9a012-199">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="9a012-200">In breve, la query restituisce un elenco di server la cui RTCMEDSRV viene interrotta nella finestra temporale.</span><span class="sxs-lookup"><span data-stu-id="9a012-200">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="9a012-201">La query per l'avviso di reimpostazione è:</span><span class="sxs-lookup"><span data-stu-id="9a012-201">The query for the reset alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="9a012-202">La query di reimpostazione fa esattamente l'operazione opposta alla query di errore.</span><span class="sxs-lookup"><span data-stu-id="9a012-202">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="9a012-203">Per ogni computer, ne restituirà uno se l'ultimo evento è l'evento di avvio del servizio. restituirà Nothing se l'ultimo evento è l'evento di arresto del servizio.</span><span class="sxs-lookup"><span data-stu-id="9a012-203">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

<span data-ttu-id="9a012-204">**Creare una coppia di avvisi: "troppe chiamate simultanee in Mediation Server" e "le chiamate simultanee ricadono sul carico normale"**</span><span class="sxs-lookup"><span data-stu-id="9a012-204">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="9a012-205">Per creare questo avviso:</span><span class="sxs-lookup"><span data-stu-id="9a012-205">To create this alert:</span></span>

- <span data-ttu-id="9a012-206">La query per l'avviso di errore è la seguente:</span><span class="sxs-lookup"><span data-stu-id="9a012-206">The query for the error alert is:</span></span>

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="9a012-207">Per ogni computer, la query otterrà gli ultimi contatori per le chiamate in ingresso e in uscita e somma i due valori.</span><span class="sxs-lookup"><span data-stu-id="9a012-207">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="9a012-208">Restituirà un log se il valore della somma è superiore a 500; non restituirà alcun valore se non lo è.</span><span class="sxs-lookup"><span data-stu-id="9a012-208">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="9a012-209">In breve, la query restituisce un elenco di server le cui chiamate simultanee sono troppe nella finestra temporale.</span><span class="sxs-lookup"><span data-stu-id="9a012-209">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="9a012-210">La query per l'avviso di reimpostazione è:</span><span class="sxs-lookup"><span data-stu-id="9a012-210">The query for the reset alert is:</span></span>

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="9a012-211">La query di reimpostazione fa esattamente l'operazione opposta alla query di errore.</span><span class="sxs-lookup"><span data-stu-id="9a012-211">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="9a012-212">Per ogni computer, la query otterrà gli ultimi contatori per le chiamate in ingresso e in uscita e somma i due valori.</span><span class="sxs-lookup"><span data-stu-id="9a012-212">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="9a012-213">Se il valore della somma è inferiore a 500, verrà restituito un log. in caso contrario, non restituirà alcun valore.</span><span class="sxs-lookup"><span data-stu-id="9a012-213">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

<span data-ttu-id="9a012-214">**Creare un avviso: "avviso di utilizzo della CPU \> 90 o RTCMEDIARELAY interrotto nei server"**</span><span class="sxs-lookup"><span data-stu-id="9a012-214">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="9a012-215">Per creare questo avviso, la query è:</span><span class="sxs-lookup"><span data-stu-id="9a012-215">To create this alert, the query is:</span></span>

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="9a012-216">La query otterrà tutti i contatori di utilizzo del processore e l'evento di arresto del servizio da tutti i computer e restituirà un log se l'utilizzo del processore supera il 90% o il servizio non viene mai interrotto.</span><span class="sxs-lookup"><span data-stu-id="9a012-216">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="9a012-217">Analizzare gli avvisi nel repository di analisi dei log</span><span class="sxs-lookup"><span data-stu-id="9a012-217">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="9a012-218">Per analizzare gli avvisi nell'archivio, utilizzare la soluzione di gestione avvisi.</span><span class="sxs-lookup"><span data-stu-id="9a012-218">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="9a012-219">Per ulteriori informazioni, vedere [Alert Management Solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="9a012-219">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="9a012-220">Set di monitoraggio minimo consigliato</span><span class="sxs-lookup"><span data-stu-id="9a012-220">Recommended minimal monitoring set</span></span>

<span data-ttu-id="9a012-221">Per identificare i problemi relativi ai registri eventi e ai contatori delle prestazioni:</span><span class="sxs-lookup"><span data-stu-id="9a012-221">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="9a012-222">**Registri eventi.**</span><span class="sxs-lookup"><span data-stu-id="9a012-222">**Event logs.**</span></span> <span data-ttu-id="9a012-223">Per qualsiasi problema, deve essere presente una coppia di eventi, con un insieme di eventi per indicare che qualcosa non va, mentre l'altro indica che è tutto a posto.</span><span class="sxs-lookup"><span data-stu-id="9a012-223">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="9a012-224">Per un determinato periodo di tempo, è l'ultimo evento registrato che indicherà se qualcosa non funziona per il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="9a012-224">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="9a012-225">**Contatori delle prestazioni.**</span><span class="sxs-lookup"><span data-stu-id="9a012-225">**Performance Counters.**</span></span> <span data-ttu-id="9a012-226">Deve essere presente una soglia per i contatori monitorati.</span><span class="sxs-lookup"><span data-stu-id="9a012-226">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="9a012-227">Nella tabella seguente sono elencati i servizi che Microsoft consiglia di monitorare elencando gli ID evento Stop e Start:</span><span class="sxs-lookup"><span data-stu-id="9a012-227">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="9a012-228">Nome del servizio</span><span class="sxs-lookup"><span data-stu-id="9a012-228">Service Name</span></span>  <br/> |<span data-ttu-id="9a012-229">Ruolo del server di destinazione</span><span class="sxs-lookup"><span data-stu-id="9a012-229">Target Server Role</span></span>  <br/> |<span data-ttu-id="9a012-230">Interrompere l'ID evento</span><span class="sxs-lookup"><span data-stu-id="9a012-230">Stop Event ID</span></span>  <br/> |<span data-ttu-id="9a012-231">ID evento di avvio</span><span class="sxs-lookup"><span data-stu-id="9a012-231">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9a012-232">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="9a012-232">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="9a012-233">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="9a012-233">Mediation Server</span></span>  <br/> |<span data-ttu-id="9a012-234">25003</span><span class="sxs-lookup"><span data-stu-id="9a012-234">25003</span></span>  <br/> |<span data-ttu-id="9a012-235">25002</span><span class="sxs-lookup"><span data-stu-id="9a012-235">25002</span></span>  <br/> |
|<span data-ttu-id="9a012-236">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="9a012-236">RTCSRV</span></span>  <br/> |<span data-ttu-id="9a012-237">Edge Server</span><span class="sxs-lookup"><span data-stu-id="9a012-237">Edge Server</span></span>  <br/> |<span data-ttu-id="9a012-238">12289</span><span class="sxs-lookup"><span data-stu-id="9a012-238">12289</span></span>  <br/> |<span data-ttu-id="9a012-239">12288</span><span class="sxs-lookup"><span data-stu-id="9a012-239">12288</span></span>  <br/> |
|<span data-ttu-id="9a012-240">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="9a012-240">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="9a012-241">Edge Server</span><span class="sxs-lookup"><span data-stu-id="9a012-241">Edge Server</span></span>  <br/> |<span data-ttu-id="9a012-242">19003</span><span class="sxs-lookup"><span data-stu-id="9a012-242">19003</span></span>  <br/> |<span data-ttu-id="9a012-243">19002</span><span class="sxs-lookup"><span data-stu-id="9a012-243">19002</span></span>  <br/> |
|<span data-ttu-id="9a012-244">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="9a012-244">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="9a012-245">Edge Server</span><span class="sxs-lookup"><span data-stu-id="9a012-245">Edge Server</span></span>  <br/> |<span data-ttu-id="9a012-246">22003</span><span class="sxs-lookup"><span data-stu-id="9a012-246">22003</span></span>  <br/> |<span data-ttu-id="9a012-247">22002</span><span class="sxs-lookup"><span data-stu-id="9a012-247">22002</span></span>  <br/> |

<span data-ttu-id="9a012-248">Nella tabella seguente sono elencati i problemi di rete che Microsoft consiglia di monitorare:</span><span class="sxs-lookup"><span data-stu-id="9a012-248">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="9a012-249">Nome del monitoraggio</span><span class="sxs-lookup"><span data-stu-id="9a012-249">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="9a012-250">Ruolo del server di destinazione</span><span class="sxs-lookup"><span data-stu-id="9a012-250">Target Server Role</span></span>  <br/> | <span data-ttu-id="9a012-251">Espressione dell'ID evento di esito positivo</span><span class="sxs-lookup"><span data-stu-id="9a012-251">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="9a012-252">Espressione dell'ID evento di errore</span><span class="sxs-lookup"><span data-stu-id="9a012-252">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="9a012-253">Esempio di errore</span><span class="sxs-lookup"><span data-stu-id="9a012-253">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="9a012-254">Mediation Server all'errore di connettività del gateway</span><span class="sxs-lookup"><span data-stu-id="9a012-254">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="9a012-255">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="9a012-255">Mediation Server</span></span>  <br/>   | <span data-ttu-id="9a012-256">25062</span><span class="sxs-lookup"><span data-stu-id="9a012-256">25062</span></span>                              |                                  | <span data-ttu-id="9a012-257">25002</span><span class="sxs-lookup"><span data-stu-id="9a012-257">25002</span></span>  <br/>           |
| <span data-ttu-id="9a012-258">Errore di completamento delle chiamate del gateway Mediation Server</span><span class="sxs-lookup"><span data-stu-id="9a012-258">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="9a012-259">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="9a012-259">Mediation Server</span></span>  <br/>   | <span data-ttu-id="9a012-260">25064</span><span class="sxs-lookup"><span data-stu-id="9a012-260">25064</span></span>                              |                                  | <span data-ttu-id="9a012-261">25002</span><span class="sxs-lookup"><span data-stu-id="9a012-261">25002</span></span>  <br/>           |
| <span data-ttu-id="9a012-262">Problemi di rete critici</span><span class="sxs-lookup"><span data-stu-id="9a012-262">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="9a012-263">Edge Server</span><span class="sxs-lookup"><span data-stu-id="9a012-263">Edge Server</span></span>  <br/>        | <span data-ttu-id="9a012-264">14353</span><span class="sxs-lookup"><span data-stu-id="9a012-264">14353</span></span>                              |                                  | <span data-ttu-id="9a012-265">12288</span><span class="sxs-lookup"><span data-stu-id="9a012-265">12288</span></span>  <br/>           |

<span data-ttu-id="9a012-266">Di seguito sono elencati i contatori delle capacità di chiamata che devono essere monitorati.</span><span class="sxs-lookup"><span data-stu-id="9a012-266">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="9a012-267">Questi numeri devono essere inferiori a 500 per Cloud Connector Standard Edition; meno di 50 per l'edizione minima del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="9a012-267">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="9a012-268">LS: MediationServer-chiamate in entrata (_Total) \- correnti</span><span class="sxs-lookup"><span data-stu-id="9a012-268">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="9a012-269">LS: MediationServer-chiamate in uscita (_Total) \- correnti</span><span class="sxs-lookup"><span data-stu-id="9a012-269">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="9a012-270">LS: MediationServer-chiamate in entrata (_Total) \- chiamate di bypass multimediale attive</span><span class="sxs-lookup"><span data-stu-id="9a012-270">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="9a012-271">LS: MediationServer-chiamate in uscita (_Total) le \- chiamate di bypass multimediale attivo</span><span class="sxs-lookup"><span data-stu-id="9a012-271">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="9a012-272">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a012-272">See also</span></span>

<span data-ttu-id="9a012-273">Per ulteriori informazioni sull'utilizzo di OMS, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a012-273">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="9a012-274">Trovare i dati utilizzando le ricerche log nell'analisi dei log</span><span class="sxs-lookup"><span data-stu-id="9a012-274">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="9a012-275">Informazioni di riferimento sul linguaggio del registro di Azure</span><span class="sxs-lookup"><span data-stu-id="9a012-275">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="9a012-276">Informazioni sugli avvisi nell'analisi del log</span><span class="sxs-lookup"><span data-stu-id="9a012-276">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="9a012-277">Connettere i computer Windows al servizio di analisi dei log in Azure</span><span class="sxs-lookup"><span data-stu-id="9a012-277">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


