---
title: Backup dei dati RGS (Response Group Service) in Skype for Business Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Informazioni su come eseguire il backup dei dati di Response Group Service (RGS) in Skype for Business Server 2019.
ms.openlocfilehash: f9c62953dcb859be2aa34bdee84ca76e3303d738
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824070"
---
# <a name="back-up-response-group-service-rgs-data"></a><span data-ttu-id="97157-103">Eseguire il backup dei dati di Response Group Service (RGS)</span><span class="sxs-lookup"><span data-stu-id="97157-103">Back up Response Group Service (RGS) data</span></span>

<span data-ttu-id="97157-104">Con l'aggiornamento cumulativo di Skype for Business Server 2019 luglio è stata inclusa la possibilità di includere i dati RGS come parte del backup standard.</span><span class="sxs-lookup"><span data-stu-id="97157-104">With the Skype for Business Server 2019 July cumulative update, we’ve included the ability to include RGS data as part of the standard backup.</span></span>

## <a name="rgs-data-replication"></a><span data-ttu-id="97157-105">Replica dati RGS</span><span class="sxs-lookup"><span data-stu-id="97157-105">RGS data replication</span></span>

<span data-ttu-id="97157-106">Per provare la funzionalità di replica dei dati RGS, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="97157-106">To try RGS data replication functionality, please follow the steps below:</span></span>

1. <span data-ttu-id="97157-107">Installare l'aggiornamento cumulativo di luglio in tutti i front-end (FEs) del pool associato.</span><span class="sxs-lookup"><span data-stu-id="97157-107">Install the July cumulative update on all front-ends (FEs) of your paired pool.</span></span>
1. <span data-ttu-id="97157-108">Installare il database RGS in entrambi i membri del pool associato:</span><span class="sxs-lookup"><span data-stu-id="97157-108">Install the RGS database on both members of the paired pool:</span></span>
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. <span data-ttu-id="97157-109">Eseguire il cmdlet seguente in entrambi i pool per replicare i dati RGS esistenti nelle tabelle di backup in modo che i dati possano essere raccolti da RGSBackupService:</span><span class="sxs-lookup"><span data-stu-id="97157-109">Run the following cmdlet on both pools to replicate existing RGS Data to the backup tables so that the data can be picked up by RGSBackupService:</span></span>
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. <span data-ttu-id="97157-110">Abilita RGSBackupService (questo consentirà a RGSBackupService globalmente.</span><span class="sxs-lookup"><span data-stu-id="97157-110">Enable RGSBackupService (This will enable RGSBackupService globally.</span></span> <span data-ttu-id="97157-111">Se questo parametro è impostato su true, RGSBackupService inizierà a sincronizzare i dati RGS nei pool associati (entrambi i pool devono essere CU1).</span><span class="sxs-lookup"><span data-stu-id="97157-111">If this parameter is set to true , RGSBackupService will start syncing RGS data on paired pools (both pools needs to be CU1).</span></span> <span data-ttu-id="97157-112">Attendere alcuni minuti per iniziare.</span><span class="sxs-lookup"><span data-stu-id="97157-112">Wait for a few minutes to get it started.</span></span> <span data-ttu-id="97157-113">Inizialmente, lo stato di RGS BackupService sarà NotInitialized.):</span><span class="sxs-lookup"><span data-stu-id="97157-113">Initially, RGS BackupService status will be NotInitialized.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. <span data-ttu-id="97157-114">Per controllare BackupServiceStatus:</span><span class="sxs-lookup"><span data-stu-id="97157-114">To check BackupServiceStatus:</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. <span data-ttu-id="97157-115">Per controllare la replica tramite i pool, usare questi cmdlet (questi cmdlet mostrano solo i dati del pool di proprietari):</span><span class="sxs-lookup"><span data-stu-id="97157-115">To check DataReplication across pools, use these cmdlets (These cmdlets show only owner pool data):</span></span>
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. <span data-ttu-id="97157-116">Per controllare i dati del pool di proprietari RGS e i relativi dati di backup:</span><span class="sxs-lookup"><span data-stu-id="97157-116">To check Owner pool RGS data and its backup data:</span></span>
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. <span data-ttu-id="97157-117">Verificare la funzionalità del flusso di lavoro effettuando una chiamata audio al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="97157-117">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="97157-118">Failover del pool di proprietari RGS.</span><span class="sxs-lookup"><span data-stu-id="97157-118">Failover your RGS Owner pool.</span></span>
1. <span data-ttu-id="97157-119">Verificare la funzionalità del flusso di lavoro effettuando una chiamata audio al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="97157-119">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="97157-120">Failback del pool.</span><span class="sxs-lookup"><span data-stu-id="97157-120">Failback the pool.</span></span>
1. <span data-ttu-id="97157-121">Aggiornare i dati RGS nel pool di origine ed eseguire un altro failover per verificare che le modifiche vengano applicate al pool di backup.</span><span class="sxs-lookup"><span data-stu-id="97157-121">Update RGS Data on source pool and perform another failover to check that changes are reflected on backup pool.</span></span> <span data-ttu-id="97157-122">RGS deve comportarsi allo stesso modo in cui si comporta prima del failover.</span><span class="sxs-lookup"><span data-stu-id="97157-122">RGS should behave in same way as it was behaving before failover.</span></span>

> [!TIP]
> <span data-ttu-id="97157-123">È consigliabile eseguire questi passaggi su un blocco di dati e eseguire frequenti operazioni di failover e failbacks.</span><span class="sxs-lookup"><span data-stu-id="97157-123">It is recommended you perform these steps on a bulk of data and do frequent failover and failbacks.</span></span> <span data-ttu-id="97157-124">Qualsiasi nuovo RGS creato dopo l'aggiornamento di CU deve essere replicato.</span><span class="sxs-lookup"><span data-stu-id="97157-124">Any new RGS created after this CU update should also be replicated.</span></span>

## <a name="rgs-cmdlets"></a><span data-ttu-id="97157-125">Cmdlet RGS</span><span class="sxs-lookup"><span data-stu-id="97157-125">RGS cmdlets</span></span>

- <span data-ttu-id="97157-126">Per controllare BackupServiceStatus (lo stato di esportazione deve essere nello stato finale o stabile.</span><span class="sxs-lookup"><span data-stu-id="97157-126">To check BackupServiceStatus (The export status should be in the Final or Steady state.</span></span> <span data-ttu-id="97157-127">Lo stato di importazione deve essere nello stato Normal.</span><span class="sxs-lookup"><span data-stu-id="97157-127">The import status should be in the Normal state.</span></span> <span data-ttu-id="97157-128">RGSBackupservice deve essere abilitato.):</span><span class="sxs-lookup"><span data-stu-id="97157-128">RGSBackupservice should be enabled.):</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- <span data-ttu-id="97157-129">Per sincronizzare completamente i dati RGS nel pool di backup (verranno sincronizzati i dati completi di RGS nel pool di backup.):</span><span class="sxs-lookup"><span data-stu-id="97157-129">To Fully Sync RGS Data on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- <span data-ttu-id="97157-130">Per sincronizzare completamente il FileStore RGS nel pool di backup (verranno sincronizzati i dati completi di RGS nel pool di backup.):</span><span class="sxs-lookup"><span data-stu-id="97157-130">To Fully Sync the RGS filestore on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- <span data-ttu-id="97157-131">Per sincronizzare i dati Delta di RGS nel pool di backup (verranno sincronizzati solo i dati Delta nel pool di backup per RGS.):</span><span class="sxs-lookup"><span data-stu-id="97157-131">To Sync RGS delta data on the backup pool (This will sync delta data on backup pool for RGS only.):</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- <span data-ttu-id="97157-132">Per sincronizzare tutti i dati del modulo, tra cui RGS:</span><span class="sxs-lookup"><span data-stu-id="97157-132">To sync all module data including RGS:</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- <span data-ttu-id="97157-133">Per disabilitare RGSBackupService (verrà disabilitato RGSBackupService globalmente.</span><span class="sxs-lookup"><span data-stu-id="97157-133">To disable RGSBackupService (This will disable RGSBackupService globally.</span></span> <span data-ttu-id="97157-134">Se questo parametro è impostato su true, RGSBackupService verrà disabilitato in tutti i pool associati.):</span><span class="sxs-lookup"><span data-stu-id="97157-134">If this parameter is set to true , RGSBackupService will be disabled on all paired pools.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
