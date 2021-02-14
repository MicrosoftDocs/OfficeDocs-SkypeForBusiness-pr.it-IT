---
title: Configurazione e monitoraggio del servizio di backup
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: È possibile utilizzare i comandi di Skype for Business Server Management Shell per configurare e monitorare il servizio di backup.
ms.openlocfilehash: d38c9d0b0261fb7e1da89b3422496d94307a791d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817196"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="41806-103">Configurazione e monitoraggio del servizio di backup in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="41806-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="41806-104">È possibile utilizzare i seguenti comandi di Skype for Business Server Management Shell per configurare e monitorare il servizio di backup.</span><span class="sxs-lookup"><span data-stu-id="41806-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="41806-105">Per ripristinare le informazioni sulle conferenze archiviate nell'archivio file di un pool Front End, vedere ripristinare il contenuto delle conferenze [utilizzando il servizio di backup](#restore-conference-contents-using-the-backup-service)di seguito.</span><span class="sxs-lookup"><span data-stu-id="41806-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="41806-106">RTCUniversalServerAdmins è l'unico gruppo che dispone delle autorizzazioni per eseguire **Get-CsBackupServiceStatus** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="41806-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="41806-107">Per utilizzare questo cmdlet, eseguire l'accesso come membro di questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="41806-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="41806-108">In alternativa, è possibile concedere l'accesso a questo comando ad altri gruppi, ad esempio CSAdministrator, utilizzando il cmdlet **Set-CsBackupServiceConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="41806-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="41806-109">Per visualizzare la configurazione del servizio di backup</span><span class="sxs-lookup"><span data-stu-id="41806-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="41806-110">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="41806-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="41806-111">Il valore predefinito per SyncInterval è due minuti.</span><span class="sxs-lookup"><span data-stu-id="41806-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="41806-112">Per impostare l'intervallo di sincronizzazione del servizio di backup</span><span class="sxs-lookup"><span data-stu-id="41806-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="41806-113">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="41806-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="41806-114">Con il comando seguente ad esempio si imposta l'intervallo su tre minuti.</span><span class="sxs-lookup"><span data-stu-id="41806-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="41806-115">Benché sia possibile utilizzare questo cmdlet per modificare l'intervallo di sincronizzazione predefinito per il servizio di backup, non è consigliabile modificare questo valore a meno che non sia assolutamente necessario, poiché l'intervallo di sincronizzazione ha un effetto significativo sulle prestazioni e sull''obiettivo in termini di punto di ripristino (RPO, Recovery Point Objective) del servizio di backup.</span><span class="sxs-lookup"><span data-stu-id="41806-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="41806-116">Per ottenere lo stato del servizio di backup per un pool specifico</span><span class="sxs-lookup"><span data-stu-id="41806-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="41806-117">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="41806-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="41806-118">Lo stato di sincronizzazione del servizio di backup è definito in modo unidirezionale da un pool (P1) per il relativo pool di backup (P2).</span><span class="sxs-lookup"><span data-stu-id="41806-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="41806-119">Lo stato di sincronizzazione da P1 a P2 può essere diverso dallo stato di sincronizzazione da P2 a P1.</span><span class="sxs-lookup"><span data-stu-id="41806-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="41806-120">Per la sincronizzazione da P1 a P2, il servizio di backup è in uno stato "stazionario" se tutte le modifiche apportate a P1 vengono interamente replicate in P2 nell'intervallo di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="41806-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="41806-121">Lo stato invece è "finale" se non sono presenti ulteriori modifiche da sincronizzare da P1 a P2.</span><span class="sxs-lookup"><span data-stu-id="41806-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="41806-122">Entrambi gli stati indicano uno snapshot del servizio di backup effettuato al momento dell'esecuzione del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="41806-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="41806-123">Questo non implica che lo stato restituito resti invariato successivamente.</span><span class="sxs-lookup"><span data-stu-id="41806-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="41806-124">In particolare, lo stato "finale" rimarrà tale solo se P1 non genera modifiche dopo l'esecuzione del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="41806-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="41806-125">Questo si verifica in caso di failover di P1 a P2 dopo l'attivazione della modalità di sola lettura per P1 come parte della logica di esecuzione di **Invoke-CsPoolfailover**.</span><span class="sxs-lookup"><span data-stu-id="41806-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="41806-126">Per ottenere informazioni sulla relazione di backup per un pool specifico</span><span class="sxs-lookup"><span data-stu-id="41806-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="41806-127">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="41806-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="41806-128">Per forzare una sincronizzazione del servizio di backup</span><span class="sxs-lookup"><span data-stu-id="41806-128">To force a Backup Service sync</span></span>

<span data-ttu-id="41806-129">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="41806-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="41806-130">Ripristinare il contenuto delle conferenze tramite il servizio di backup</span><span class="sxs-lookup"><span data-stu-id="41806-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="41806-131">Se le informazioni sulla conferenza archiviate nell'archivio file di un pool Front End non sono più disponibili, è necessario ripristinare tali informazioni in modo che gli utenti ospitati nel pool conservino i dati della conferenza.</span><span class="sxs-lookup"><span data-stu-id="41806-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="41806-132">Se il pool Front End che ha perso i dati delle conferenze è associato a un altro pool Front End, è possibile utilizzare il servizio di backup per ripristinare i dati.</span><span class="sxs-lookup"><span data-stu-id="41806-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="41806-p105">È inoltre necessario eseguire questa attività se si verifica un errore dell'intero pool e si deve eseguire il failover degli utenti che vi appartengono in un pool di backup. Quando viene eseguito nuovamente il failover di questi utenti nel pool originale, è necessario utilizzare questa procedura anche per copiare il contenuto della conferenza nel pool originale.</span><span class="sxs-lookup"><span data-stu-id="41806-p105">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool. When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="41806-135">Partire dal presupposto che Pool1 è associato a Pool2, e che i dati della conferenza di Pool1 siano stati persi.</span><span class="sxs-lookup"><span data-stu-id="41806-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="41806-136">È possibile utilizzare il cmdlet seguente per richiamare il servizio di backup per ripristinare il contenuto:</span><span class="sxs-lookup"><span data-stu-id="41806-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="41806-p107">Il ripristino del contenuto della conferenza può richiedere del tempo, a seconda delle dimensioni. È possibile usare il cmdlet seguente per verificare lo stato del processo:</span><span class="sxs-lookup"><span data-stu-id="41806-p107">Restoring the conference contents may take some time, depending on their size. You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="41806-139">Il processo è terminato quando questo cmdlet restituisce il valore di stato stabile per il modulo della conferenza dati.</span><span class="sxs-lookup"><span data-stu-id="41806-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
