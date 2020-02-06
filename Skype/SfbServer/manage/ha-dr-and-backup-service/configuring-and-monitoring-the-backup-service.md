---
title: Configurazione e monitoraggio del servizio di backup
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Puoi usare i comandi di Skype for Business Server Management Shell per configurare e monitorare il servizio di backup.
ms.openlocfilehash: 80b15b2306807fe5bfc36449e16953466e3af75c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818217"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="7f1ed-103">Configurazione e monitoraggio del servizio di backup in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7f1ed-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="7f1ed-104">Puoi usare i seguenti comandi di Skype for Business Server Management Shell per configurare e monitorare il servizio di backup.</span><span class="sxs-lookup"><span data-stu-id="7f1ed-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="7f1ed-105">Per ripristinare le informazioni sulla conferenza archiviate nell'archivio di un pool di front-end, vedere [ripristinare il contenuto della conferenza tramite il servizio di backup](#restore-conference-contents-using-the-backup-service), di seguito.</span><span class="sxs-lookup"><span data-stu-id="7f1ed-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="7f1ed-106">Il gruppo RTCUniversalServerAdmins è l'unico gruppo che dispone delle autorizzazioni per l'esecuzione di **Get-CsBackupServiceStatus** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7f1ed-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="7f1ed-107">Per usare questo cmdlet, accedere come membro di questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="7f1ed-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="7f1ed-108">In alternativa, puoi concedere l'accesso a questo comando ad altri gruppi, ad esempio CSAdministrator, usando il cmdlet **set-CsBackupServiceConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="7f1ed-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="7f1ed-109">Per visualizzare la configurazione del servizio di backup</span><span class="sxs-lookup"><span data-stu-id="7f1ed-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="7f1ed-110">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="7f1ed-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="7f1ed-111">L'impostazione predefinita per SyncInterval è due minuti.</span><span class="sxs-lookup"><span data-stu-id="7f1ed-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="7f1ed-112">Per impostare l'intervallo di sincronizzazione del servizio di backup</span><span class="sxs-lookup"><span data-stu-id="7f1ed-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="7f1ed-113">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="7f1ed-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="7f1ed-114">Ad esempio, il seguente imposta l'intervallo su tre minuti.</span><span class="sxs-lookup"><span data-stu-id="7f1ed-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="7f1ed-115">Anche se è possibile usare questo cmdlet per modificare l'intervallo di sincronizzazione predefinito per il servizio di backup, non è consigliabile farlo, a meno che non sia assolutamente necessario, dato che l'intervallo di sincronizzazione ha un impatto notevole sulle prestazioni del servizio di backup e sull'obiettivo del punto di ripristino (RPO).</span><span class="sxs-lookup"><span data-stu-id="7f1ed-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="7f1ed-116">Per ottenere lo stato del servizio di backup per un determinato pool</span><span class="sxs-lookup"><span data-stu-id="7f1ed-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="7f1ed-117">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="7f1ed-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="7f1ed-118">Lo stato di sincronizzazione del servizio di backup è definito in maniera unidirezionale da un pool (P1) al relativo pool di backup (P2).</span><span class="sxs-lookup"><span data-stu-id="7f1ed-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="7f1ed-119">Lo stato di sincronizzazione da P1 a P2 può essere diverso da quello da P2 a P1.</span><span class="sxs-lookup"><span data-stu-id="7f1ed-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="7f1ed-120">Per P1-P2, il servizio di backup si trova in uno stato "costante" se tutte le modifiche apportate in P1 vengono completamente replicate in P2 nell'intervallo di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="7f1ed-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="7f1ed-121">Si trova nello stato "Final" se non ci sono più modifiche da sincronizzare da P1 a P2.</span><span class="sxs-lookup"><span data-stu-id="7f1ed-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="7f1ed-122">Entrambi gli Stati indicano uno snapshot del servizio di backup al momento dell'esecuzione del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7f1ed-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="7f1ed-123">Non implica che lo stato restituito rimarrà come in seguito.</span><span class="sxs-lookup"><span data-stu-id="7f1ed-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="7f1ed-124">In particolare, lo stato "finale" continuerà a contenere solo se P1 non genera alcuna modifica dopo l'esecuzione del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7f1ed-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="7f1ed-125">Questo vale in caso di mancanza di P1 oltre a P2 dopo che P1 viene inserito nella modalità di sola lettura come parte della logica di esecuzione **Invoke-CsPoolFailOver** .</span><span class="sxs-lookup"><span data-stu-id="7f1ed-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="7f1ed-126">Per ottenere informazioni sulla relazione di backup per un determinato pool</span><span class="sxs-lookup"><span data-stu-id="7f1ed-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="7f1ed-127">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="7f1ed-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="7f1ed-128">Per forzare una sincronizzazione del servizio di backup</span><span class="sxs-lookup"><span data-stu-id="7f1ed-128">To force a Backup Service sync</span></span>

<span data-ttu-id="7f1ed-129">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="7f1ed-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="7f1ed-130">Ripristinare il contenuto della conferenza tramite il servizio di backup</span><span class="sxs-lookup"><span data-stu-id="7f1ed-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="7f1ed-131">Se le informazioni sulla conferenza archiviate nell'archivio di file di un pool Front-end diventano non disponibili, è necessario ripristinare queste informazioni in modo che gli utenti ospitati nel pool mantengono i dati della conferenza.</span><span class="sxs-lookup"><span data-stu-id="7f1ed-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="7f1ed-132">Se il pool Front-end che ha perso i dati della conferenza è associato a un altro pool Front-End, è possibile usare il servizio di backup per ripristinare i dati.</span><span class="sxs-lookup"><span data-stu-id="7f1ed-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="7f1ed-133">È necessario eseguire questa operazione anche se un intero pool non è riuscito e non è necessario superare gli utenti in un pool di backup.</span><span class="sxs-lookup"><span data-stu-id="7f1ed-133">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="7f1ed-134">Quando questi utenti non vengono riattivati nel pool originale, è necessario usare questa procedura per copiare il contenuto della conferenza anche di nuovo nel pool originale.</span><span class="sxs-lookup"><span data-stu-id="7f1ed-134">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="7f1ed-135">Supponiamo che pool1 sia associato a Pool2 e che i dati della conferenza in pool1 vengano persi.</span><span class="sxs-lookup"><span data-stu-id="7f1ed-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="7f1ed-136">Puoi usare il cmdlet seguente per richiamare il servizio di backup per ripristinare il contenuto:</span><span class="sxs-lookup"><span data-stu-id="7f1ed-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="7f1ed-137">Il ripristino del contenuto della conferenza può richiedere del tempo, a seconda delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="7f1ed-137">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="7f1ed-138">Puoi usare il cmdlet seguente per controllare lo stato del processo:</span><span class="sxs-lookup"><span data-stu-id="7f1ed-138">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="7f1ed-139">Il processo viene eseguito quando questo cmdlet restituisce il valore di stato costante per il modulo conferenza dati.</span><span class="sxs-lookup"><span data-stu-id="7f1ed-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
