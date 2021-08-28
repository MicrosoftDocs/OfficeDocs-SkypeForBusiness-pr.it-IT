---
title: Backup dei dati di Response Group Service (RGS) in Skype for Business Server 2019
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: Informazioni su come eseguire il backup dei dati di Response Group Service (RGS) in Skype for Business Server 2019.
ms.openlocfilehash: 7e3e4116a281584da7afc1807fe58e79d2528183
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58581160"
---
# <a name="back-up-response-group-service-rgs-data"></a>Eseguire il backup dei dati di Response Group Service (RGS)

Con l Skype for Business Server aggiornamento cumulativo di luglio 2019, abbiamo incluso la possibilità di includere i dati RGS come parte del backup standard.

## <a name="rgs-data-replication"></a>Replica dei dati RGS

Per provare la funzionalità di replica dei dati RGS, attenersi alla procedura seguente:

1. Installare l'aggiornamento cumulativo di luglio in tutti i front-end (FE) del pool associato.
1. Installare il database RGS in entrambi i membri del pool associato:
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. Eseguire il cmdlet seguente in entrambi i pool per replicare i dati RGS esistenti nelle tabelle di backup in modo che i dati possano essere raccolti da RGSBackupService:
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. Abilita RGSBackupService (questo abiliterà RGSBackupService a livello globale. Se questo parametro è impostato su true, RGSBackupService avvia la sincronizzazione dei dati RGS nei pool associati (entrambi i pool devono essere CU1). Attendere alcuni minuti per iniziare. Inizialmente, lo stato di RGS BackupService sarà NotInitialized.
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. Per controllare BackupServiceStatus:
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. Per controllare DataReplication tra pool, utilizzare questi cmdlet (questi cmdlet mostrano solo i dati del pool proprietario):
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. Per controllare i dati RGS del pool proprietario e i relativi dati di backup:
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. Verificare la funzionalità del flusso di lavoro effettuando una chiamata audio a Flusso di lavoro.
1. Failover del pool di proprietari RGS.
1. Verificare la funzionalità del flusso di lavoro effettuando una chiamata audio a Flusso di lavoro.
1. Failback del pool.
1. Aggiornare i dati RGS nel pool di origine ed eseguire un altro failover per verificare che le modifiche si riflettano nel pool di backup. RGS deve comportarsi allo stesso modo in cui si comportava prima del failover.

> [!TIP]
> È consigliabile eseguire questi passaggi su una massa di dati ed eseguire frequenti failover e failback. Qualsiasi nuovo RGS creato dopo questo aggiornamento cumulativo deve essere replicato.

## <a name="rgs-cmdlets"></a>Cmdlet RGS

- Per controllare BackupServiceStatus (lo stato di esportazione deve essere Final o Steady. Lo stato dell'importazione deve essere normal. RGSBackupservice deve essere abilitato.):
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- Per sincronizzare completamente i dati RGS nel pool di backup (in questo modo verranno sincronizzati i dati RGS completi nel pool di backup).
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- Per sincronizzare completamente l'archivio file RGS nel pool di backup (in questo modo verranno sincronizzati i dati RGS completi nel pool di backup).
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- Per sincronizzare i dati delta RGS nel pool di backup (in questo modo i dati delta verranno sincronizzati nel pool di backup solo per RGS).
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- Per sincronizzare tutti i dati del modulo, incluso RGS:
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- Per disabilitare RGSBackupService (questo disabiliterà RGSBackupService a livello globale. Se questo parametro è impostato su true, RGSBackupService verrà disabilitato in tutti i pool associati.
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
