---
title: 'Lync Server 2013: gestione della configurazione'
description: 'Lync Server 2013: gestione della configurazione.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5999708811cc4a34cf846a1ddd481ba38e07c62
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552152"
---
# <a name="configuration-management-in-lync-server-2013"></a><span data-ttu-id="e7451-103">Gestione della configurazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7451-103">Configuration management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7451-104">_**Ultimo argomento modificato:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="e7451-104">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="e7451-105">La gestione della configurazione è il processo di registrazione e monitoraggio delle risorse hardware e software e delle informazioni di configurazione del sistema.</span><span class="sxs-lookup"><span data-stu-id="e7451-105">Configuration management is the process of recording and tracking hardware and software assets and system configuration information.</span></span> <span data-ttu-id="e7451-106">Viene generalmente utilizzato per tenere conto delle licenze software, per gestire una configurazione hardware e software standard per i computer client e i server e definire gli standard di denominazione per i nuovi computer.</span><span class="sxs-lookup"><span data-stu-id="e7451-106">It is generally used to track software licenses, maintain a standard hardware and software build for client computers and servers, and define naming standards for new computers.</span></span> <span data-ttu-id="e7451-107">La gestione della configurazione copre generalmente le categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7451-107">Configuration management generally covers the following categories:</span></span>

  - <span data-ttu-id="e7451-108">**Hardware**     In questa categoria sono riportate le apparecchiature possedute dall'organizzazione IT, in cui si trovano le apparecchiature e che utilizzano le apparecchiature.</span><span class="sxs-lookup"><span data-stu-id="e7451-108">**Hardware**   This category tracks the pieces of equipment that the IT organization owns, where equipment is located, and who uses equipment.</span></span> <span data-ttu-id="e7451-109">Queste informazioni consentono a un'organizzazione di pianificare e preventivare gli aggiornamenti, mantenere le build hardware standard, riportare il valore delle risorse IT a fini contabili e contribuire a prevenire il furto.</span><span class="sxs-lookup"><span data-stu-id="e7451-109">This information enables an organization to plan and budget for upgrades, maintain standard hardware builds, report on the value of IT assets for accounting purposes, and help prevent theft.</span></span>

  - <span data-ttu-id="e7451-110">**Software**     Questa categoria consente di tenere traccia del software installato in ogni computer, dei numeri di versione e della posizione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="e7451-110">**Software**   This category tracks software that is installed on each computer, the version numbers, and where the licenses are held.</span></span> <span data-ttu-id="e7451-111">Queste informazioni aiutano a pianificare gli aggiornamenti, a garantire che il software venga concesso in licenza e a rilevare la presenza di software non autorizzato (e senza licenza).</span><span class="sxs-lookup"><span data-stu-id="e7451-111">This information helps plan upgrades, to ensure that software is licensed, and detect the presence of unauthorized (and unlicensed) software.</span></span>

  - <span data-ttu-id="e7451-112">**Compilazioni standard**     Questa categoria tiene traccia della build standard corrente per i computer client e i server e se i computer client e i server soddisfano questo standard.</span><span class="sxs-lookup"><span data-stu-id="e7451-112">**Standard Builds**   This category tracks the current standard build for the client computers and servers and whether the client computers and servers meet this standard.</span></span> <span data-ttu-id="e7451-113">La definizione e l'applicazione di compilazioni standard consentono al personale di supporto perché il personale è tenuto a mantenere solo un numero limitato di versioni di ogni parte del software.</span><span class="sxs-lookup"><span data-stu-id="e7451-113">Defining and enforcing standard builds helps support staff because the staff is required to maintain only a limited number of versions of each piece of software.</span></span>

  - <span data-ttu-id="e7451-114">**Aggiornamenti cumulativi e hotfix**     Questa categoria tiene traccia dei Service Pack che sono stati testati e approvati per l'utilizzo e quali computer sono aggiornati.</span><span class="sxs-lookup"><span data-stu-id="e7451-114">**Cumulative Updates and Hotfixes**   This category tracks which service packs are tested and approved for use and which computers are up to date.</span></span> <span data-ttu-id="e7451-115">Queste informazioni sono importanti per ridurre il rischio che i computer vengano compromessi e per rilevare gli utenti che hanno installato gli aggiornamenti non approvati.</span><span class="sxs-lookup"><span data-stu-id="e7451-115">This information is important to reduce the risk of computers being compromised and to detect users who have installed unapproved updates.</span></span>

  - <span data-ttu-id="e7451-116">**Informazioni sulla**     configurazione del sistema Questa categoria tiene traccia della funzione di un sistema, dell'interazione tra gli elementi del sistema e dei processi che dipendono da un sistema in esecuzione senza problemi.</span><span class="sxs-lookup"><span data-stu-id="e7451-116">**System Configuration Information**   This category tracks the function of a system, the interaction between system elements, and the processes that depend on a system that is running smoothly.</span></span> <span data-ttu-id="e7451-117">Ad esempio, il server proxy di terze parti può essere configurato in un server singolo.</span><span class="sxs-lookup"><span data-stu-id="e7451-117">For example, third-party proxy server may be configured on a single server.</span></span> <span data-ttu-id="e7451-118">La dipendenza del server proxy su questo server dovrebbe essere compresa e i piani di emergenza potrebbero essere necessari se si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="e7451-118">The proxy server’s dependence on this server should be understood and contingency plans may be required if there is a failure.</span></span> <span data-ttu-id="e7451-119">Se il server proxy può essere configurato per comunicare anche con un altro server front-end, è probabile che le dipendenze e i piani di contingenza vengano modificati.</span><span class="sxs-lookup"><span data-stu-id="e7451-119">If the proxy server can be configured to also communicate with another front-end server, dependencies and contingency plans will probably change.</span></span>

<div>

## <a name="implementing-configuration-management"></a><span data-ttu-id="e7451-120">Implementazione della gestione della configurazione</span><span class="sxs-lookup"><span data-stu-id="e7451-120">Implementing configuration management</span></span>

<span data-ttu-id="e7451-121">Dopo aver determinato gli elementi necessari per la gestione, implementare la gestione della configurazione tramite la raccolta dei dati e i dati di report.</span><span class="sxs-lookup"><span data-stu-id="e7451-121">After you determine what items need managing, implement configuration management by collecting data and reporting data.</span></span> <span data-ttu-id="e7451-122">L'approccio più semplice per le organizzazioni di piccole dimensioni consiste nel raccogliere dati manualmente (numero e modello dei computer client, del sistema operativo, del software installato) e salvarlo in un documento di Office Word o Office Excel.</span><span class="sxs-lookup"><span data-stu-id="e7451-122">The simplest approach for small organizations is to collect data manually (number and model of client computers, operating system, installed software) and save it in an Office Word or Office Excel document.</span></span> <span data-ttu-id="e7451-123">Per i sistemi più grandi, più complessi e in continua evoluzione, è necessario automatizzare l'individuazione delle risorse e la raccolta di informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="e7451-123">For larger, more complex, and constantly changing systems, the discovery of assets and collection of detailed information must be automated.</span></span> <span data-ttu-id="e7451-124">Decidere quali informazioni sono rilevanti per l'organizzazione e registrarle in un database.</span><span class="sxs-lookup"><span data-stu-id="e7451-124">Decide what information is relevant to your organization and record it in a database.</span></span>

<span data-ttu-id="e7451-125">Il database di gestione della configurazione è uno strumento utile per la gestione e il personale di supporto nelle aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7451-125">The configuration management database is a useful tool for support staff and management in the following areas:</span></span>

  - <span data-ttu-id="e7451-126">**Controlli**     di sicurezza Il database consente di identificare i server che eseguono Lync Server e i sistemi di computer client che devono avere hotfix applicati o che hanno mancato l'installazione di un Service Pack o degli aggiornamenti antivirus più recenti.</span><span class="sxs-lookup"><span data-stu-id="e7451-126">**Security Audits**   The database enables you to identify servers that are running Lync Server and client computer systems that must have hotfixes applied or that have missed the installation of a service pack or the latest antivirus updates.</span></span>

  - <span data-ttu-id="e7451-127">**Installazione**     del software Identificare le versioni del software client e monitorarle consentirà agli amministratori di pianificare gli aggiornamenti delle versioni e le nuove installazioni, contribuendo anche alla documentazione relativa alle licenze e alla conformità.</span><span class="sxs-lookup"><span data-stu-id="e7451-127">**Software Installation**   Identifying client software versions and tracking them will aid administrators in planning version updates and new installs and also by helping with licensing documentation and compliance.</span></span>

  - <span data-ttu-id="e7451-128">**Informazioni sulla configurazione**     Se si gestisce un elenco aggiornato di tutte le impostazioni che sono state modificate rispetto all'impostazione predefinita, è possibile risolvere i problemi in modo rapido e più efficace.</span><span class="sxs-lookup"><span data-stu-id="e7451-128">**Configuration Information**   If you maintain an up-to-date list of all settings that were changed from their default, then you'll be able to troubleshoot issues quickly and more effectively.</span></span>

  - <span data-ttu-id="e7451-129">**Pianificazione degli aggiornamenti**     Se una revisione della capacità rivela che è necessario ulteriore spazio di archiviazione sui server di database di Lync, è importante sapere se ogni server dispone di un controller RAID interno.</span><span class="sxs-lookup"><span data-stu-id="e7451-129">**Planning Upgrades**   If a capacity review reveals that additional storage space is required on your Lync database servers, it’s important to know whether each server has an internal RAID controller.</span></span> <span data-ttu-id="e7451-130">Se lo fanno, allora sono lo stesso modello?</span><span class="sxs-lookup"><span data-stu-id="e7451-130">If they do, then are they the same model?</span></span> <span data-ttu-id="e7451-131">Hanno lo stesso numero di dischi installati?</span><span class="sxs-lookup"><span data-stu-id="e7451-131">Do they have the same number of disks installed?</span></span> <span data-ttu-id="e7451-132">Il database di gestione della configurazione indicherà il tipo di disco che può essere installato, il numero e il percorso di aggiornamento in ogni caso.</span><span class="sxs-lookup"><span data-stu-id="e7451-132">The configuration management database will indicate the type of disk that can be installed, the number, and the upgrade path in each case.</span></span>

</div>

<div>

## <a name="tools-used-for-configuration-management"></a><span data-ttu-id="e7451-133">Strumenti utilizzati per la gestione della configurazione</span><span class="sxs-lookup"><span data-stu-id="e7451-133">Tools used for configuration management</span></span>

<span data-ttu-id="e7451-134">Sono disponibili numerosi strumenti per individuare, controllare e segnalare le risorse.</span><span class="sxs-lookup"><span data-stu-id="e7451-134">There are many tools to discover, audit, and report assets.</span></span> <span data-ttu-id="e7451-135">Alcuni di questi strumenti sono descritti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="e7451-135">Some of these tools are discussed in this section.</span></span>

  - <span data-ttu-id="e7451-136">**Script automatici**     È possibile scrivere script semplici per segnalare elementi quali il sistema operativo, il livello del Service Pack e se il software esiste su un insieme specifico di computer.</span><span class="sxs-lookup"><span data-stu-id="e7451-136">**Automated Scripts**   You can write simple scripts to report items such as the operating system, service pack level, and whether software exists on a specific set of computers.</span></span> <span data-ttu-id="e7451-137">È possibile scrivere questi script nei requisiti esatti di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e7451-137">You can write these scripts to an organization’s exact requirements.</span></span> <span data-ttu-id="e7451-138">Tuttavia, il numero necessario di script e la relativa complessità può rendere gli script costosi per la creazione e la manutenzione.</span><span class="sxs-lookup"><span data-stu-id="e7451-138">However, the required number of scripts and their complexity can make scripts expensive to create and maintain.</span></span>

  - <span data-ttu-id="e7451-139">**Strumenti automatici**     A seconda delle dimensioni dell'azienda e delle esigenze organizzative, è consigliabile utilizzare gli strumenti automatici.</span><span class="sxs-lookup"><span data-stu-id="e7451-139">**Automated Tools**   Depending on the size of your business and your organizational needs, you may want to consider using automated tools.</span></span> <span data-ttu-id="e7451-140">Strumenti quali Microsoft endpoint Configuration Manager incorporano modelli di report standard, ad esempio il livello di Service Pack, e consentono anche di creare report personalizzati, come in un'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e7451-140">Tools such as Microsoft Endpoint Configuration Manager incorporate standard report templates (such as service pack level) and also enable you to create customized reports, for example, for a custom application.</span></span> <span data-ttu-id="e7451-141">Microsoft endpoint Configuration Manager può essere utilizzato anche per il report sulle configurazioni hardware e software.</span><span class="sxs-lookup"><span data-stu-id="e7451-141">The Microsoft Endpoint Configuration Manager can also be used to report on hardware and software configurations.</span></span>

</div>

<div>

## <a name="relationship-with-change-management"></a><span data-ttu-id="e7451-142">Relazione con la gestione delle modifiche</span><span class="sxs-lookup"><span data-stu-id="e7451-142">Relationship with change management</span></span>

<span data-ttu-id="e7451-143">La gestione della configurazione è strettamente correlata alla gestione delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="e7451-143">Configuration management is closely related to change management.</span></span> <span data-ttu-id="e7451-144">La gestione della configurazione identifica la necessità di modificare e identifica e registra una modifica.</span><span class="sxs-lookup"><span data-stu-id="e7451-144">Configuration management identifies the need for change and identifies and records that a change has occurred.</span></span> <span data-ttu-id="e7451-145">Ad esempio, il database di gestione della configurazione può essere utilizzato per identificare i server che richiedono un hotfix.</span><span class="sxs-lookup"><span data-stu-id="e7451-145">For example, the configuration management database can be used to identify servers that require a hotfix.</span></span> <span data-ttu-id="e7451-146">Change Management quindi definisce il processo per l'applicazione dell'hotfix.</span><span class="sxs-lookup"><span data-stu-id="e7451-146">Change management then defines the process for applying the hotfix.</span></span>

<span data-ttu-id="e7451-147">Viceversa, se viene implementato un nuovo aggiornamento cumulativo, il processo di gestione delle modifiche dovrebbe fornire tali informazioni al sistema di gestione della configurazione.</span><span class="sxs-lookup"><span data-stu-id="e7451-147">Conversely, if a new cumulative update is rolled out, the change management process should supply this information to the configuration management system.</span></span> <span data-ttu-id="e7451-148">È probabile che gli strumenti di gestione della configurazione debbano essere configurati per identificare il nuovo software in modo che possano individuare e tenere presenti la posizione e la distribuzione del software.</span><span class="sxs-lookup"><span data-stu-id="e7451-148">The configuration management tools will probably need to be configured to identify the new software so that they can discover and track where and when the software is deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

