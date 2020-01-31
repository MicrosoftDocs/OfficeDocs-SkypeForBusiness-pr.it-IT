---
title: 'Lync Server 2013: Gestione configurazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb652485b03bcaee5e63bc4fc23d25fd5df958bd
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-management-in-lync-server-2013"></a><span data-ttu-id="d0848-102">Gestione della configurazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0848-102">Configuration management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0848-103">_**Argomento Ultima modifica:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="d0848-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="d0848-104">La gestione della configurazione è il processo di registrazione e monitoraggio degli asset hardware e software e delle informazioni di configurazione del sistema.</span><span class="sxs-lookup"><span data-stu-id="d0848-104">Configuration management is the process of recording and tracking hardware and software assets and system configuration information.</span></span> <span data-ttu-id="d0848-105">Viene in genere usato per tenere traccia delle licenze software, gestire una build hardware e software standard per i computer e i server client e definire gli standard di denominazione per i nuovi computer.</span><span class="sxs-lookup"><span data-stu-id="d0848-105">It is generally used to track software licenses, maintain a standard hardware and software build for client computers and servers, and define naming standards for new computers.</span></span> <span data-ttu-id="d0848-106">La gestione della configurazione riguarda in genere le categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0848-106">Configuration management generally covers the following categories:</span></span>

  - <span data-ttu-id="d0848-107">**Hardware**   in questa categoria sono riportate le attrezzature di cui dispone l'organizzazione IT, dove si trovano le attrezzature e chi usa le attrezzature.</span><span class="sxs-lookup"><span data-stu-id="d0848-107">**Hardware**   This category tracks the pieces of equipment that the IT organization owns, where equipment is located, and who uses equipment.</span></span> <span data-ttu-id="d0848-108">Queste informazioni consentono a un'organizzazione di pianificare e preventivo per gli aggiornamenti, gestire le build hardware standard, segnalare il valore degli asset IT per scopi contabili e prevenire i furti.</span><span class="sxs-lookup"><span data-stu-id="d0848-108">This information enables an organization to plan and budget for upgrades, maintain standard hardware builds, report on the value of IT assets for accounting purposes, and help prevent theft.</span></span>

  - <span data-ttu-id="d0848-109">**Software**   questa categoria consente di tenere traccia del software installato in ogni computer, i numeri di versione e la posizione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="d0848-109">**Software**   This category tracks software that is installed on each computer, the version numbers, and where the licenses are held.</span></span> <span data-ttu-id="d0848-110">Queste informazioni aiutano a pianificare gli aggiornamenti, a garantire che il software sia concesso in licenza e a rilevare la presenza di software non autorizzato (e senza licenza).</span><span class="sxs-lookup"><span data-stu-id="d0848-110">This information helps plan upgrades, to ensure that software is licensed, and detect the presence of unauthorized (and unlicensed) software.</span></span>

  - <span data-ttu-id="d0848-111">**Build standard questa**   categoria tiene traccia della build standard corrente per i computer e i server client e se i computer e i server client soddisfano questo standard.</span><span class="sxs-lookup"><span data-stu-id="d0848-111">**Standard Builds**   This category tracks the current standard build for the client computers and servers and whether the client computers and servers meet this standard.</span></span> <span data-ttu-id="d0848-112">La definizione e l'applicazione di build standard aiuta il personale di supporto perché è necessario che il personale mantenga solo un numero limitato di versioni di ogni parte del software.</span><span class="sxs-lookup"><span data-stu-id="d0848-112">Defining and enforcing standard builds helps support staff because the staff is required to maintain only a limited number of versions of each piece of software.</span></span>

  - <span data-ttu-id="d0848-113">**Aggiornamenti cumulativi e hotfix**   questa categoria tiene traccia dei Service Pack che vengono testati e approvati per l'uso e quali sono i computer aggiornati.</span><span class="sxs-lookup"><span data-stu-id="d0848-113">**Cumulative Updates and Hotfixes**   This category tracks which service packs are tested and approved for use and which computers are up to date.</span></span> <span data-ttu-id="d0848-114">Queste informazioni sono importanti per ridurre il rischio che i computer vengano compromessi e per rilevare gli utenti che hanno installato aggiornamenti non approvati.</span><span class="sxs-lookup"><span data-stu-id="d0848-114">This information is important to reduce the risk of computers being compromised and to detect users who have installed unapproved updates.</span></span>

  - <span data-ttu-id="d0848-115">**Informazioni sulla configurazione del sistema**   questa categoria tiene traccia della funzione di un sistema, dell'interazione tra gli elementi di sistema e dei processi che dipendono da un sistema che viene eseguito senza problemi.</span><span class="sxs-lookup"><span data-stu-id="d0848-115">**System Configuration Information**   This category tracks the function of a system, the interaction between system elements, and the processes that depend on a system that is running smoothly.</span></span> <span data-ttu-id="d0848-116">Ad esempio, il server proxy di terze parti può essere configurato in un singolo server.</span><span class="sxs-lookup"><span data-stu-id="d0848-116">For example, third-party proxy server may be configured on a single server.</span></span> <span data-ttu-id="d0848-117">La dipendenza del server proxy da questo server deve essere compresa e i piani di emergenza potrebbero essere necessari in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="d0848-117">The proxy server’s dependence on this server should be understood and contingency plans may be required if there is a failure.</span></span> <span data-ttu-id="d0848-118">Se il server proxy può essere configurato per comunicare anche con un altro server front-end, le dipendenze e i piani di emergenza cambieranno probabilmente.</span><span class="sxs-lookup"><span data-stu-id="d0848-118">If the proxy server can be configured to also communicate with another front-end server, dependencies and contingency plans will probably change.</span></span>

<div>

## <a name="implementing-configuration-management"></a><span data-ttu-id="d0848-119">Implementazione della gestione della configurazione</span><span class="sxs-lookup"><span data-stu-id="d0848-119">Implementing configuration management</span></span>

<span data-ttu-id="d0848-120">Dopo aver determinato gli elementi che devono essere gestiti, implementare la gestione della configurazione raccogliendo dati e segnalando i dati.</span><span class="sxs-lookup"><span data-stu-id="d0848-120">After you determine what items need managing, implement configuration management by collecting data and reporting data.</span></span> <span data-ttu-id="d0848-121">L'approccio più semplice per le piccole organizzazioni consiste nel raccogliere dati manualmente (numero e modello di computer client, sistema operativo, software installato) e salvarlo in un documento di Office Word o Office Excel.</span><span class="sxs-lookup"><span data-stu-id="d0848-121">The simplest approach for small organizations is to collect data manually (number and model of client computers, operating system, installed software) and save it in an Office Word or Office Excel document.</span></span> <span data-ttu-id="d0848-122">Per sistemi più grandi, più complessi e in continuo cambiamento, la scoperta di asset e la raccolta di informazioni dettagliate deve essere automatizzata.</span><span class="sxs-lookup"><span data-stu-id="d0848-122">For larger, more complex, and constantly changing systems, the discovery of assets and collection of detailed information must be automated.</span></span> <span data-ttu-id="d0848-123">Decidere quali informazioni sono rilevanti per l'organizzazione e registrarle in un database.</span><span class="sxs-lookup"><span data-stu-id="d0848-123">Decide what information is relevant to your organization and record it in a database.</span></span>

<span data-ttu-id="d0848-124">Il database di gestione della configurazione è uno strumento utile per supportare il personale e la gestione nelle aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0848-124">The configuration management database is a useful tool for support staff and management in the following areas:</span></span>

  - <span data-ttu-id="d0848-125">**Verifiche di sicurezza**   il database consente di identificare i server che esegue Lync Server e i sistemi di computer client che devono avere gli hotfix applicati o che hanno perso l'installazione di un Service Pack o degli aggiornamenti più recenti degli antivirus.</span><span class="sxs-lookup"><span data-stu-id="d0848-125">**Security Audits**   The database enables you to identify servers that are running Lync Server and client computer systems that must have hotfixes applied or that have missed the installation of a service pack or the latest antivirus updates.</span></span>

  - <span data-ttu-id="d0848-126">**L'installazione**   del software che identifica le versioni del software client e il loro monitoraggio aiuteranno gli amministratori a pianificare gli aggiornamenti della versione e le nuove installazioni e anche aiutando la documentazione e la conformità delle licenze.</span><span class="sxs-lookup"><span data-stu-id="d0848-126">**Software Installation**   Identifying client software versions and tracking them will aid administrators in planning version updates and new installs and also by helping with licensing documentation and compliance.</span></span>

  - <span data-ttu-id="d0848-127">**Informazioni sulla**   configurazione se si mantiene un elenco aggiornato di tutte le impostazioni modificate rispetto all'impostazione predefinita, sarà possibile risolvere i problemi in modo rapido e più efficace.</span><span class="sxs-lookup"><span data-stu-id="d0848-127">**Configuration Information**   If you maintain an up-to-date list of all settings that were changed from their default, then you'll be able to troubleshoot issues quickly and more effectively.</span></span>

  - <span data-ttu-id="d0848-128">**Pianificazione degli aggiornamenti**   se una revisione della capacità rivela che è necessario ulteriore spazio di archiviazione per i server di database Lync, è importante sapere se ogni server ha un controller RAID interno.</span><span class="sxs-lookup"><span data-stu-id="d0848-128">**Planning Upgrades**   If a capacity review reveals that additional storage space is required on your Lync database servers, it’s important to know whether each server has an internal RAID controller.</span></span> <span data-ttu-id="d0848-129">Se lo fanno, allora lo stesso modello?</span><span class="sxs-lookup"><span data-stu-id="d0848-129">If they do, then are they the same model?</span></span> <span data-ttu-id="d0848-130">Hanno lo stesso numero di dischi installati?</span><span class="sxs-lookup"><span data-stu-id="d0848-130">Do they have the same number of disks installed?</span></span> <span data-ttu-id="d0848-131">Il database di gestione della configurazione indicherà il tipo di disco che può essere installato, il numero e il percorso di aggiornamento in ogni caso.</span><span class="sxs-lookup"><span data-stu-id="d0848-131">The configuration management database will indicate the type of disk that can be installed, the number, and the upgrade path in each case.</span></span>

</div>

<div>

## <a name="tools-used-for-configuration-management"></a><span data-ttu-id="d0848-132">Strumenti usati per la gestione della configurazione</span><span class="sxs-lookup"><span data-stu-id="d0848-132">Tools used for configuration management</span></span>

<span data-ttu-id="d0848-133">Esistono molti strumenti per individuare, controllare e segnalare asset.</span><span class="sxs-lookup"><span data-stu-id="d0848-133">There are many tools to discover, audit, and report assets.</span></span> <span data-ttu-id="d0848-134">Alcuni di questi strumenti sono illustrati in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="d0848-134">Some of these tools are discussed in this section.</span></span>

  - <span data-ttu-id="d0848-135">**Script automatizzati**   è possibile scrivere semplici script per segnalare elementi come il sistema operativo, il livello di Service Pack e se il software esiste in un set di computer specifico.</span><span class="sxs-lookup"><span data-stu-id="d0848-135">**Automated Scripts**   You can write simple scripts to report items such as the operating system, service pack level, and whether software exists on a specific set of computers.</span></span> <span data-ttu-id="d0848-136">Puoi scrivere questi script nei requisiti esatti di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d0848-136">You can write these scripts to an organization’s exact requirements.</span></span> <span data-ttu-id="d0848-137">Tuttavia, il numero necessario di script e la loro complessità possono rendere gli script costosi da creare e gestire.</span><span class="sxs-lookup"><span data-stu-id="d0848-137">However, the required number of scripts and their complexity can make scripts expensive to create and maintain.</span></span>

  - <span data-ttu-id="d0848-138">**Strumenti automatici a**   seconda delle dimensioni dell'azienda e delle esigenze dell'organizzazione, è consigliabile usare gli strumenti automatici.</span><span class="sxs-lookup"><span data-stu-id="d0848-138">**Automated Tools**   Depending on the size of your business and your organizational needs, you may want to consider using automated tools.</span></span> <span data-ttu-id="d0848-139">Gli strumenti, ad esempio Microsoft endpoint Configuration Manager, incorporano modelli di report standard (ad esempio il livello di Service Pack) e consentono anche di creare report personalizzati, ad es. per un'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="d0848-139">Tools such as Microsoft Endpoint Configuration Manager incorporate standard report templates (such as service pack level) and also enable you to create customized reports, for example, for a custom application.</span></span> <span data-ttu-id="d0848-140">Microsoft endpoint Configuration Manager può essere usato anche per il report sulle configurazioni hardware e software.</span><span class="sxs-lookup"><span data-stu-id="d0848-140">The Microsoft Endpoint Configuration Manager can also be used to report on hardware and software configurations.</span></span>

</div>

<div>

## <a name="relationship-with-change-management"></a><span data-ttu-id="d0848-141">Relazione con la gestione delle modifiche</span><span class="sxs-lookup"><span data-stu-id="d0848-141">Relationship with change management</span></span>

<span data-ttu-id="d0848-142">La gestione della configurazione è strettamente correlata alla gestione delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="d0848-142">Configuration management is closely related to change management.</span></span> <span data-ttu-id="d0848-143">La gestione della configurazione identifica la necessità di modifiche e identifica e registra che si è verificata una modifica.</span><span class="sxs-lookup"><span data-stu-id="d0848-143">Configuration management identifies the need for change and identifies and records that a change has occurred.</span></span> <span data-ttu-id="d0848-144">Ad esempio, il database di gestione della configurazione può essere usato per identificare i server che richiedono un hotfix.</span><span class="sxs-lookup"><span data-stu-id="d0848-144">For example, the configuration management database can be used to identify servers that require a hotfix.</span></span> <span data-ttu-id="d0848-145">La gestione delle modifiche definisce quindi il processo per l'applicazione dell'hotfix.</span><span class="sxs-lookup"><span data-stu-id="d0848-145">Change management then defines the process for applying the hotfix.</span></span>

<span data-ttu-id="d0848-146">Viceversa, se viene implementato un nuovo aggiornamento cumulativo, il processo di gestione delle modifiche deve fornire queste informazioni al sistema di gestione della configurazione.</span><span class="sxs-lookup"><span data-stu-id="d0848-146">Conversely, if a new cumulative update is rolled out, the change management process should supply this information to the configuration management system.</span></span> <span data-ttu-id="d0848-147">Gli strumenti di gestione della configurazione dovranno probabilmente essere configurati per identificare il nuovo software in modo che possano individuare e individuare dove e quando viene distribuito il software.</span><span class="sxs-lookup"><span data-stu-id="d0848-147">The configuration management tools will probably need to be configured to identify the new software so that they can discover and track where and when the software is deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

