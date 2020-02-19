---
title: 'Lync Server 2013: procedure consigliate per il backup e il ripristino'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c0995c81554073a8d10039f2f95673f013569e1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a><span data-ttu-id="21c11-102">Procedure consigliate per il backup e il ripristino di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21c11-102">Best practices for backup and restoration for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21c11-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="21c11-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="21c11-104">In questa sezione sono descritti due tipi di procedure consigliate:</span><span class="sxs-lookup"><span data-stu-id="21c11-104">This section includes two types of best practices:</span></span>

  - <span data-ttu-id="21c11-105">Procedure consigliate per il backup e il ripristino.</span><span class="sxs-lookup"><span data-stu-id="21c11-105">Best practices for backup and restoration.</span></span>

  - <span data-ttu-id="21c11-106">Procedure consigliate per ridurre al minimo l'impatto di un'emergenza.</span><span class="sxs-lookup"><span data-stu-id="21c11-106">Best practices for minimizing the impact of a disaster.</span></span>

<div>

## <a name="best-practices-for-backup-and-restoration"></a><span data-ttu-id="21c11-107">Procedure consigliate per il backup e il ripristino</span><span class="sxs-lookup"><span data-stu-id="21c11-107">Best Practices for Backup and Restoration</span></span>

<span data-ttu-id="21c11-108">Per semplificare il processo di backup e ripristino, applicare le procedure consigliate riportate di seguito quando si esegue il backup o il ripristino dei dati:</span><span class="sxs-lookup"><span data-stu-id="21c11-108">To facilitate your backup and restoration process, apply the following best practices when you back up or restore your data:</span></span>

  - <span data-ttu-id="21c11-109">Eseguire backup regolari a intervalli appropriati.</span><span class="sxs-lookup"><span data-stu-id="21c11-109">Perform regular backups at appropriate intervals.</span></span> <span data-ttu-id="21c11-110">Il tipo di backup e il piano di rotazione più semplici e comunemente utilizzati corrispondono a un backup notturno completo dell'intero database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="21c11-110">The simplest and most commonly used backup type and rotation schedule is a full, nightly backup of the entire SQL Server database.</span></span> <span data-ttu-id="21c11-111">Se quindi è necessario il ripristino, il processo di ripristino richiede un solo backup e non devono essere persi più di un giorno.</span><span class="sxs-lookup"><span data-stu-id="21c11-111">Then, if restoration is necessary, the restoration process requires only one backup, and no more than a day’s data should be lost.</span></span>

  - <span data-ttu-id="21c11-112">Se si utilizzano i cmdlet o il pannello di controllo di Lync Server per apportare modifiche alla configurazione, utilizzare il cmdlet **Export-CsConfiguration** per eseguire un backup snapshot del file di configurazione della topologia (XDS. MDF) dopo aver apportato le modifiche, in modo che le modifiche non vengano perse se è necessario ripristinare i database.</span><span class="sxs-lookup"><span data-stu-id="21c11-112">If you use cmdlets or the Lync Server Control Panel to make configuration changes, use the **Export-CsConfiguration** cmdlet to take a snapshot backup of the topology configuration file (Xds.mdf) after you make the changes, so that you won't lose the changes if you need to restore your databases.</span></span> <span data-ttu-id="21c11-113">Si noti che la configurazione è stata sottoposta a backup in formato XML e compressa come file ZIP.</span><span class="sxs-lookup"><span data-stu-id="21c11-113">Note that this configuration is backed up in XML format and compressed as a ZIP file.</span></span>

  - <span data-ttu-id="21c11-114">Verificare che la cartella condivisa che si intende utilizzare per il backup di Lync Server disponga di spazio sufficiente su disco per contenere tutti i dati di cui è stato eseguito il backup.</span><span class="sxs-lookup"><span data-stu-id="21c11-114">Make sure that the shared folder you plan to use for backing up Lync Server has sufficient disk space to hold all the backed up data.</span></span>

  - <span data-ttu-id="21c11-115">Pianificare i backup quando l'utilizzo di Lync Server è in genere basso, per migliorare le prestazioni del server e l'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="21c11-115">Schedule backups when Lync Server usage is typically low, to improve server performance and user experience.</span></span>

  - <span data-ttu-id="21c11-116">Verificare che il percorso in cui si esegue il backup dei dati sia sicuro (si consiglia una posizione remota).</span><span class="sxs-lookup"><span data-stu-id="21c11-116">Make sure that the location where you back up data is secure (we recommend a remote location).</span></span>

  - <span data-ttu-id="21c11-117">Mantenere i file di backup in cui saranno disponibili, nel caso in cui sia necessario ripristinare i dati.</span><span class="sxs-lookup"><span data-stu-id="21c11-117">Keep the backup files where they will be available, in case you need to restore the data.</span></span>

  - <span data-ttu-id="21c11-118">Pianificare e pianificare periodici test dei processi di ripristino supportati dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="21c11-118">Plan for and schedule periodic testing of the restoration processes that are supported by your organization.</span></span>

  - <span data-ttu-id="21c11-119">Convalidare i processi di backup e ripristino in anticipo per assicurarsi che funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="21c11-119">Validate your backup and restoration processes in advance to make sure that they work as expected.</span></span>

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a><span data-ttu-id="21c11-120">Procedure consigliate per ridurre al minimo le conseguenze di un'emergenza</span><span class="sxs-lookup"><span data-stu-id="21c11-120">Best Practices for Minimizing the Impact of a Disaster</span></span>

<span data-ttu-id="21c11-121">La strategia migliore per gestire le interruzioni di servizio disastrose (causate da eventi non gestibili, ad esempio guasti dell'alimentazione o errori hardware improvvisi) è quella di presumere che si verifichino e pianificare di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="21c11-121">The best strategy for dealing with disastrous service interruptions (caused by unmanageable events such as power outages or sudden hardware failures) is to assume they will happen, and to plan accordingly.</span></span>

<span data-ttu-id="21c11-122">Se i servizi Lync, con un minimo di disturbo e interruzioni, sono fondamentali per l'organizzazione, è consigliabile implementare pool associati di front end server, come descritto in [pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="21c11-122">If Lync services, with a minimum of disruption and outage, are business-critical for your organization, you should consider implementing paired pools of Front End Servers, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="21c11-123">Se uno di questi pool presenta un evento di emergenza, un amministratore può quindi cambiare gli utenti del pool in modo che vengano serviti dall'altro pool, con un minimo di tempo di inattività.</span><span class="sxs-lookup"><span data-stu-id="21c11-123">Then, if one of these pools has a disaster, an administrator can switch the users of that pool to be served by the other pool, with a minimum of downtime.</span></span>

<span data-ttu-id="21c11-124">I piani di gestione di emergenza sviluppati nell'ambito della strategia di backup e ripristino dovrebbero includere gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="21c11-124">The disaster management plans that you develop as part of your backup and restoration strategy should include the following:</span></span>

  - <span data-ttu-id="21c11-125">Mantenere il supporto software e gli aggiornamenti del software e del firmware facilmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="21c11-125">Keeping your software media, and your software and firmware updates, readily available.</span></span>

  - <span data-ttu-id="21c11-126">Gestione di record dell'hardware e del software.</span><span class="sxs-lookup"><span data-stu-id="21c11-126">Maintaining hardware and software records.</span></span>

  - <span data-ttu-id="21c11-127">Eseguire regolarmente il backup dei dati e monitorarne l'integrità.</span><span class="sxs-lookup"><span data-stu-id="21c11-127">Backing up your data regularly and monitoring the integrity of your backups.</span></span>

  - <span data-ttu-id="21c11-128">Formazione del personale sul ripristino di emergenza e sulla documentazione delle procedure ed esecuzione di esercitazioni di simulazione.</span><span class="sxs-lookup"><span data-stu-id="21c11-128">Training your staff in disaster recovery, documenting procedures, and implementing disaster recovery simulation drills.</span></span>

  - <span data-ttu-id="21c11-129">Tenere a disposizione l'hardware di scorta o, se si dispone di un contratto di servizio (SLA, Service Level Agreement), stipulare contratti con i fornitori di hardware per richiedere sostituzioni rapide.</span><span class="sxs-lookup"><span data-stu-id="21c11-129">Keeping spare hardware available, or, if you have a service level agreement (SLA), contracting with hardware vendors and suppliers for prompt replacements.</span></span>

  - <span data-ttu-id="21c11-130">Luoghi separati per la conservazione dei file di registro delle transazioni (con estensione ldf) e dei file di database (con estensione mdf).</span><span class="sxs-lookup"><span data-stu-id="21c11-130">Separating the location of your transaction log files (.ldf files) and database files (.mdf files).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

