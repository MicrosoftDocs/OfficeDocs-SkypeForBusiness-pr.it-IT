---
title: 'Lync Server 2013: Configurazione e monitoraggio del servizio di backup'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66a800014b3327e83426c9f758b7d5359c1ce6c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a>Configurazione e monitoraggio del servizio di backup in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Puoi usare i comandi di Lync Server Management Shell seguenti per configurare e monitorare il servizio di backup.

<div>


> [!NOTE]  
> Il gruppo RTCUniversalServerAdmins è l'unico gruppo che dispone delle autorizzazioni per l'esecuzione di <STRONG>Get-CsBackupServiceStatus</STRONG> per impostazione predefinita. Per usare questo cmdlet, accedere come membro di questo gruppo. In alternativa, puoi concedere l'accesso a questo comando ad altri gruppi, ad esempio CSAdministrator, usando il cmdlet <STRONG>set-CsBackupServiceConfiguration</STRONG> .



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a>Per visualizzare la configurazione del servizio di backup

Eseguire il cmdlet seguente:

    Get-CsBackupServiceConfiguration

L'impostazione predefinita per SyncInterval è due minuti.

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a>Per impostare l'intervallo di sincronizzazione del servizio di backup

Eseguire il cmdlet seguente:

    Set-CsBackupServiceConfiguration -SyncInterval interval

Ad esempio, il seguente imposta l'intervallo su tre minuti.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> Anche se è possibile usare questo cmdlet per modificare l'intervallo di sincronizzazione predefinito per il servizio di backup, non è consigliabile farlo, a meno che non sia assolutamente necessario, dato che l'intervallo di sincronizzazione ha un impatto notevole sulle prestazioni del servizio di backup e sull'obiettivo del punto di ripristino (RPO).



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>Per ottenere lo stato del servizio di backup per un determinato pool

Eseguire il cmdlet seguente:

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> Lo stato di sincronizzazione del servizio di backup è definito in maniera unidirezionale da un pool (P1) al relativo pool di backup (P2). Lo stato di sincronizzazione da P1 a P2 può essere diverso da quello da P2 a P1. Per P1-P2, il servizio di backup si trova in uno stato "costante" se tutte le modifiche apportate in P1 vengono completamente replicate in P2 nell'intervallo di sincronizzazione. Si trova nello stato "Final" se non ci sono più modifiche da sincronizzare da P1 a P2. Entrambi gli Stati indicano uno snapshot del servizio di backup al momento dell'esecuzione del cmdlet. Non implica che lo stato restituito rimarrà come in seguito. In particolare, lo stato "finale" continuerà a contenere solo se P1 non genera alcuna modifica dopo l'esecuzione del cmdlet. Questo vale in caso di mancanza di P1 oltre a P2 dopo che P1 viene inserito nella modalità di sola lettura come parte della logica di esecuzione <STRONG>Invoke-CsPoolFailOver</STRONG> .



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>Per ottenere informazioni sulla relazione di backup per un determinato pool

Eseguire il cmdlet seguente:

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a>Per forzare una sincronizzazione del servizio di backup

Eseguire il cmdlet seguente:

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

