---
title: Configurazione e monitoraggio del servizio di backup
ms.reviewer: null
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: È possibile utilizzare i Skype for Business Server Management Shell per configurare e monitorare il servizio di backup.
---

# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>Configurazione e monitoraggio del servizio di backup in Skype for Business Server

È possibile utilizzare i seguenti comandi Skype for Business Server Management Shell per configurare e monitorare il servizio di backup. Per ripristinare le informazioni sulla conferenza archiviate nell'archivio file di un pool Front End, vedere Ripristinare il contenuto delle conferenze [utilizzando il servizio di backup](#restore-conference-contents-using-the-backup-service), di seguito.

> [!NOTE]  
> RTCUniversalServerAdmins è l'unico gruppo che dispone delle autorizzazioni per eseguire **Get-CsBackupServiceStatus** per impostazione predefinita. Per utilizzare questo cmdlet, eseguire l'accesso come membro di questo gruppo. In alternativa, è possibile concedere l'accesso a questo comando ad altri gruppi, ad esempio CSAdministrator, utilizzando il cmdlet **Set-CsBackupServiceConfiguration**.

## <a name="to-see-the-backup-service-configuration"></a>Per visualizzare la configurazione del servizio di backup

Eseguire il cmdlet seguente:<br/><br/>Get-CsBackupServiceConfiguration

Il valore predefinito per SyncInterval è due minuti.

## <a name="to-set-the-backup-service-sync-interval"></a>Per impostare l'intervallo di sincronizzazione del servizio di backup

Eseguire il cmdlet seguente:<br/><br/>Set-CsBackupServiceConfiguration -SyncInterval interval

Con il comando seguente ad esempio si imposta l'intervallo su tre minuti.<br/><br/>Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> Benché sia possibile utilizzare questo cmdlet per modificare l'intervallo di sincronizzazione predefinito per il servizio di backup, non è consigliabile modificare questo valore a meno che non sia assolutamente necessario, poiché l'intervallo di sincronizzazione ha un effetto significativo sulle prestazioni e sull''obiettivo in termini di punto di ripristino (RPO, Recovery Point Objective) del servizio di backup.

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>Per ottenere lo stato del servizio di backup per un pool specifico

Eseguire il cmdlet seguente:<br/><br/>Get-CsBackupServiceStatus -PoolFqdn \<pool-FQDN>

> [!NOTE]  
> Lo stato di sincronizzazione del servizio di backup è definito in modo unidirezionale da un pool (P1) per il relativo pool di backup (P2). Lo stato di sincronizzazione da P1 a P2 può essere diverso dallo stato di sincronizzazione da P2 a P1. Per la sincronizzazione da P1 a P2, il servizio di backup è in uno stato "stazionario" se tutte le modifiche apportate a P1 vengono interamente replicate in P2 nell'intervallo di sincronizzazione. Lo stato invece è "finale" se non sono presenti ulteriori modifiche da sincronizzare da P1 a P2. Entrambi gli stati indicano uno snapshot del servizio di backup effettuato al momento dell'esecuzione del cmdlet. Questo non implica che lo stato restituito resti invariato successivamente. In particolare, lo stato "finale" rimarrà tale solo se P1 non genera modifiche dopo l'esecuzione del cmdlet. Questo si verifica in caso di failover di P1 a P2 dopo l'attivazione della modalità di sola lettura per P1 come parte della logica di esecuzione di **Invoke-CsPoolfailover**.

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>Per ottenere informazioni sulla relazione di backup per un pool specifico

Eseguire il cmdlet seguente:<br/><br/>Get-CsPoolBackupRelationship -PoolFQDN \<poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>Per forzare una sincronizzazione del servizio di backup

Eseguire il cmdlet seguente:<br/><br/>Invoke-CsBackupServiceSync -PoolFqdn \<poolFqdn> [-BackupModule {All| PresenceFocus| DataConf| CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>Ripristinare il contenuto delle conferenze tramite il servizio di backup 

Se le informazioni sulla conferenza archiviate nell'archivio file di un pool Front End non sono più disponibili, è necessario ripristinare tali informazioni in modo che gli utenti ospitati nel pool conservino i dati della conferenza. Se il pool Front End che ha perso i dati delle conferenze è associato a un altro pool Front End, è possibile utilizzare il servizio di backup per ripristinare i dati.

È inoltre necessario eseguire questa attività se si verifica un errore dell'intero pool e si deve eseguire il failover degli utenti che vi appartengono in un pool di backup. Quando viene eseguito nuovamente il failover di questi utenti nel pool originale, è necessario utilizzare questa procedura anche per copiare il contenuto della conferenza nel pool originale.

Partire dal presupposto che Pool1 è associato a Pool2, e che i dati della conferenza di Pool1 siano stati persi. È possibile utilizzare il cmdlet seguente per richiamare il servizio di backup per ripristinare il contenuto:<br/><br/>Invoke-CsBackupServiceSync -PoolFqdn \<Pool2 FQDN> -BackupModule ConfServices.DataConf

Il ripristino del contenuto della conferenza può richiedere del tempo, a seconda delle dimensioni. È possibile usare il cmdlet seguente per verificare lo stato del processo:<br/><br/>Get-CsBackupServiceStatus -PoolFqdn \<Pool2 FQDN> -BackupModule ConfServices.DataConf

Il processo è terminato quando questo cmdlet restituisce il valore di stato stabile per il modulo della conferenza dati.
