---
title: 'Lync Server 2013: procedure consigliate per gli ambienti Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c31d39ae7537fc53fc4e72c8b1c57863b2ba189
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="best-practices-for-lync-server-2013-environments"></a><span data-ttu-id="8c6ec-102">Procedure consigliate per gli ambienti di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c6ec-102">Best practices for Lync Server 2013 environments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c6ec-103">_**Ultimo argomento modificato:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="8c6ec-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="8c6ec-104">I seguenti principi generali devono essere applicati alle operazioni in continuo del sistema:</span><span class="sxs-lookup"><span data-stu-id="8c6ec-104">The following general principles should be applied to ongoing operations of your system:</span></span>

  - <span data-ttu-id="8c6ec-105">**Understand and utilize MOF**   MOF è una raccolta di procedure consigliate, principi e modelli che forniscono alle organizzazioni informazioni tecniche sulla gestione delle risorse IT, ad esempio le operazioni quotidiane di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-105">**Understand and utilize MOF**   MOF is a collection of best practices, principles, and models that provide organizations technical guidance about the management of IT assets, such as daily Lync Server 2013 operations.</span></span> <span data-ttu-id="8c6ec-106">Le seguenti linee guida MOF consentono di raggiungere l'affidabilità, la disponibilità, la supportabilità e la gestibilità del sistema di produzione mission-critical per i prodotti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-106">Following MOF guidelines can help you achieve mission-critical production system reliability, availability, supportability, and manageability for Microsoft products.</span></span> <span data-ttu-id="8c6ec-107">Per ulteriori informazioni, vedere [Microsoft Operations Framework 4,0](https://go.microsoft.com/fwlink/p/?linkid=40939).</span><span class="sxs-lookup"><span data-stu-id="8c6ec-107">For more information, see [Microsoft Operations Framework 4.0](https://go.microsoft.com/fwlink/p/?linkid=40939).</span></span>

  - <span data-ttu-id="8c6ec-108">**Informazioni sulle procedure consigliate per Lync Server 2013**   si consiglia di implementare una procedura pratica e collaudata per la gestione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-108">**Learn about best practices for Lync Server 2013**   We recommend that you implement practical and proven procedures to manage Lync Server 2013.</span></span> <span data-ttu-id="8c6ec-109">L'utilizzo di metodi sperimentati, testati e documentati per la gestione delle operazioni può essere più efficace rispetto allo sviluppo di metodi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-109">By using tried, tested, and documented methods of managing operations may be more efficient than developing your own methods.</span></span>

  - <span data-ttu-id="8c6ec-110">**Le operazioni separate nei processi giornalieri, settimanali e mensili**   documentano le attività operative richieste che verranno eseguite regolarmente.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-110">**Separate operations into daily, weekly, and monthly processes**   Document the required operational tasks that you'll regularly perform.</span></span> <span data-ttu-id="8c6ec-111">Documentare la modalità di esecuzione delle attività consente di verificare che le informazioni vengano conservate quando si verifica una modifica nell'ambiente operativo, ad esempio quando vengono distribuite nuove tecnologie o se vengono apportate modifiche del personale.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-111">Documenting how you perform tasks helps make sure that your information is preserved when there is a change in your operational environment such as when new technologies are deployed or staff changes occur.</span></span> <span data-ttu-id="8c6ec-112">È consigliabile separare le attività operative in carichi di lavoro gestibili, in cui le attività vengono eseguite giornalmente, settimanalmente e mensilmente.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-112">We recommend that operational tasks be separated into manageable workloads where tasks are performed daily, weekly, and monthly.</span></span> <span data-ttu-id="8c6ec-113">Le attività quotidiane concentreranno gli sforzi sul funzionamento di un sistema e le attività mensili si concentreranno maggiormente sul garantire l'integrità a lungo termine di un sistema.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-113">Daily tasks would focus efforts on the functioning of a system, and monthly tasks would focus more on ensuring the long-term health of a system.</span></span>
    
    <span data-ttu-id="8c6ec-114">Questo documento può essere utilizzato in ambienti che distribuiscono solo i componenti di messaggistica istantanea/presenza (IM/P) o IM/P con VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-114">This document can be used in environments deploying only instant messaging/presence (IM/P) components or IM/P with Enterprise Voice.</span></span> <span data-ttu-id="8c6ec-115">Quando le attività o gli elementi di elenco di controllo sono specifici di VoIP aziendale, questo viene menzionato e se l'ambiente in uso non include VoIP aziendale, la parte potrebbe essere ignorata.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-115">When tasks or checklist items are specific to Enterprise Voice, this is mentioned and if your environment does not include Enterprise Voice the portion may be skipped.</span></span>

  - <span data-ttu-id="8c6ec-116">**Distribuire gli strumenti necessari per l'utilizzo di Lync Server 2013**   sono disponibili numerosi strumenti che consentono di risolvere i problemi, automatizzare le attività e monitorare e gestire l'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-116">**Deploy the tools that are required for operating Lync Server 2013**   Many tools are available to help troubleshoot issues, automate tasks, and help monitor and maintain the Lync Server 2013 environment.</span></span> <span data-ttu-id="8c6ec-117">Definire un insieme standard di strumenti per l'organizzazione, in modo che le attività eseguite dal team operativo vengano eseguite in modo accurato, efficiente, coerente e controllato.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-117">Define a standard set of tools for your organization so the tasks that are performed by the operations team are performed accurately, efficiently, consistently, and in a controlled manner.</span></span> <span data-ttu-id="8c6ec-118">È inoltre consigliabile implementare processi per tenere traccia degli incidenti e delle principali modifiche alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-118">You should also implement processes to track incidents and major configuration changes.</span></span>

<div>

## <a name="reference"></a><span data-ttu-id="8c6ec-119">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="8c6ec-119">Reference</span></span>

<span data-ttu-id="8c6ec-120">A vantaggio dei lettori che non hanno già familiarità con le nozioni di base della gestione dei server in generale, viene fornita una panoramica delle procedure di gestione dei server.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-120">For the benefit of readers not already familiar with the basics of server management in general, we provide an overview of server management practices.</span></span> <span data-ttu-id="8c6ec-121">I lettori che hanno già familiarità con la gestione del server possono scegliere di ignorare questa sezione.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-121">Readers already familiar with server management may choose to skip this section.</span></span>

<span data-ttu-id="8c6ec-122">Le procedure consigliate sono consigli che si basano sulla conoscenza e sull'esperienza acquisita dai professionisti IT in molti ambienti.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-122">Best practices are recommendations that are based on the knowledge and experience that IT professionals have gained across many environments.</span></span> <span data-ttu-id="8c6ec-123">Essi forniscono procedure standard per le attività tipiche che gli amministratori di Lync Server devono eseguire giornalmente e elencano gli strumenti da utilizzare per la gestione di un ambiente Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-123">They provide standard procedures for typical tasks that your Lync Server administrators must perform daily, and list the tools that they should use to manage a Lync Server environment.</span></span>

<span data-ttu-id="8c6ec-124">Di seguito sono riportate le attività tipiche per gli amministratori di Lync:</span><span class="sxs-lookup"><span data-stu-id="8c6ec-124">Typical tasks for Lync administrators include the following:</span></span>

  - <span data-ttu-id="8c6ec-125">**La gestione**   della capacità e della disponibilità definisce come e cosa misurare per prevedere i requisiti di capacità futuri e per segnalare la capacità, l'affidabilità e la disponibilità dei sistemi.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-125">**Capacity and Availability Management**   Define how and what to measure to predict future capacity requirements and to report about the capacity, reliability, and availability of your systems.</span></span> <span data-ttu-id="8c6ec-126">È necessario verificare che i server in cui è in esecuzione Lync Server siano dimensionati per gestire il carico del sistema e che i tempi di inattività non pianificati siano conservati nei livelli definiti nel contratto di servizio (SLA, Service Level Agreement).</span><span class="sxs-lookup"><span data-stu-id="8c6ec-126">You must verify that servers that are running Lync Server are sized to handle the load on the system, and that unplanned downtime is kept under the levels defined in the service level agreement (SLA).</span></span> <span data-ttu-id="8c6ec-127">Inoltre, è necessario aggiornare l'hardware per continuare a soddisfare i requisiti definiti.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-127">Additionally, you'll have to upgrade hardware to continue to meet the defined requirements.</span></span>

  - <span data-ttu-id="8c6ec-128">**Change Management and Configuration Management**   Control come vengono apportate modifiche ai sistemi it.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-128">**Change Management and Configuration Management**   Control how changes are made to IT systems.</span></span> <span data-ttu-id="8c6ec-129">Questo dovrebbe includere i test, i commenti e i piani di emergenza, la documentazione di tutte le modifiche e l'approvazione dalla gestione se si verificano problemi.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-129">This should include testing, application feedback and contingency plans, documentation of all changes, and approval from management if issues occur.</span></span> <span data-ttu-id="8c6ec-130">Tenere traccia di un record delle risorse hardware e software e delle relative configurazioni.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-130">Keep a record of your software and hardware assets and their configurations.</span></span>

  - <span data-ttu-id="8c6ec-131">\*\*\*\*   Struttura di amministrazione di sistema metodi standard per eseguire attività amministrative quali l'amministrazione di database e l'amministrazione del sito.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-131">**System Administration**   Outline standard methods for doing administrative tasks such as database administration and site administration.</span></span>

  - <span data-ttu-id="8c6ec-132">**L'amministrazione**   della sicurezza ha un criterio dettagliato e una pianificazione che protegge la riservatezza dei dati, l'integrità dei dati e la disponibilità dei dati dell'infrastruttura IT.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-132">**Security Administration**   Have a detailed policy and plan that protects data confidentiality, data integrity, and data availability of the IT infrastructure.</span></span> <span data-ttu-id="8c6ec-133">Ciò include attività quotidiane e attività correlate alla gestione e alla modifica dell'infrastruttura di sicurezza IT.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-133">This includes day-to-day activities and tasks that are related to maintaining and adjusting the IT security infrastructure.</span></span>

  - <span data-ttu-id="8c6ec-134">**Risoluzione dei problemi relativi ai sistemi**   di struttura per la gestione di problemi imprevisti, inclusi i passaggi per evitare problemi simili in futuro.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-134">**System Troubleshooting**   Outline methods for dealing with unexpected issues, including steps to prevent similar issues in the future.</span></span>

  - <span data-ttu-id="8c6ec-135">**I contratti**   di servizio mantengono un insieme di obiettivi per le prestazioni dei sistemi IT e misurano regolarmente le prestazioni rispetto a tali obiettivi.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-135">**Service Level Agreements**   Maintain a set of goals for the performance of the IT systems and regularly measure performance against these goals.</span></span>

  - <span data-ttu-id="8c6ec-136">**Document**Documentation procedure standard, ad esempio le informazioni di configurazione e gli insegnamenti appresi, e renderli disponibili per i membri del personale che ne hanno bisogno.   </span><span class="sxs-lookup"><span data-stu-id="8c6ec-136">**Documentation**   Document standard procedures, such as configuration information and lessons learned, and make them available to the staff members that need them.</span></span> <span data-ttu-id="8c6ec-137">Quando vengono apportate modifiche alla configurazione, aggiornare la documentazione di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="8c6ec-137">As changes to the configuration are made, update the documentation accordingly.</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="8c6ec-138">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="8c6ec-138">Related Sections</span></span>

<span data-ttu-id="8c6ec-139">Esaminare gli argomenti seguenti relativi alle operazioni di sistema prima di procedere:</span><span class="sxs-lookup"><span data-stu-id="8c6ec-139">Review the following topics concerning system operations before proceeding:</span></span>

  - [<span data-ttu-id="8c6ec-140">Gestione della capacità e della disponibilità in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c6ec-140">Capacity and availability management in Lync Server 2013</span></span>](lync-server-2013-capacity-and-availability-management.md)

  - [<span data-ttu-id="8c6ec-141">Gestione delle modifiche in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c6ec-141">Change management in Lync Server 2013</span></span>](lync-server-2013-change-management.md)

  - [<span data-ttu-id="8c6ec-142">Gestione della configurazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c6ec-142">Configuration management in Lync Server 2013</span></span>](lync-server-2013-configuration-management.md)

  - [<span data-ttu-id="8c6ec-143">Amministrazione di sistema in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c6ec-143">System administration in Lync Server 2013</span></span>](lync-server-2013-system-administration.md)

  - [<span data-ttu-id="8c6ec-144">Contratti a livello di servizio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c6ec-144">Service level agreements in Lync Server 2013</span></span>](lync-server-2013-service-level-agreements.md)

  - [<span data-ttu-id="8c6ec-145">Documentazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c6ec-145">Documentation in Lync Server 2013</span></span>](lync-server-2013-documentation.md)

  - [<span data-ttu-id="8c6ec-146">Procedure standard in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c6ec-146">Standard procedures in Lync Server 2013</span></span>](lync-server-2013-standard-procedures.md)

  - [<span data-ttu-id="8c6ec-147">Procedure di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c6ec-147">Emergency procedures in Lync Server 2013</span></span>](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8c6ec-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c6ec-148">See Also</span></span>


[<span data-ttu-id="8c6ec-149">Microsoft Operations Framework 4,0</span><span class="sxs-lookup"><span data-stu-id="8c6ec-149">Microsoft Operations Framework 4.0</span></span>](https://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

