---
title: 'Lync Server 2013: Configurazione e monitoraggio del servizio di backup'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9992f0466ceb2e01fa54cb2b2d511eeb96af755a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="432c1-102">Configurazione e monitoraggio del servizio di backup in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="432c1-102">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="432c1-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="432c1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="432c1-104">Puoi usare i comandi di Lync Server Management Shell seguenti per configurare e monitorare il servizio di backup.</span><span class="sxs-lookup"><span data-stu-id="432c1-104">You can use the following Lync Server Management Shell commands to configure and monitor the Backup Service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="432c1-105">Il gruppo RTCUniversalServerAdmins è l'unico gruppo che dispone delle autorizzazioni per l'esecuzione di <STRONG>Get-CsBackupServiceStatus</STRONG> per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="432c1-105">The RTCUniversalServerAdmins group is the only group that has permissions to run <STRONG>Get-CsBackupServiceStatus</STRONG> by default.</span></span> <span data-ttu-id="432c1-106">Per usare questo cmdlet, accedere come membro di questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="432c1-106">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="432c1-107">In alternativa, puoi concedere l'accesso a questo comando ad altri gruppi, ad esempio CSAdministrator, usando il cmdlet <STRONG>set-CsBackupServiceConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="432c1-107">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="432c1-108">Per visualizzare la configurazione del servizio di backup</span><span class="sxs-lookup"><span data-stu-id="432c1-108">To see the Backup Service configuration</span></span>

<span data-ttu-id="432c1-109">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="432c1-109">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="432c1-110">L'impostazione predefinita per SyncInterval è due minuti.</span><span class="sxs-lookup"><span data-stu-id="432c1-110">The default for SyncInterval is two minutes.</span></span>

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="432c1-111">Per impostare l'intervallo di sincronizzazione del servizio di backup</span><span class="sxs-lookup"><span data-stu-id="432c1-111">To set the Backup Service sync interval</span></span>

<span data-ttu-id="432c1-112">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="432c1-112">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="432c1-113">Ad esempio, il seguente imposta l'intervallo su tre minuti.</span><span class="sxs-lookup"><span data-stu-id="432c1-113">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> <span data-ttu-id="432c1-114">Anche se è possibile usare questo cmdlet per modificare l'intervallo di sincronizzazione predefinito per il servizio di backup, non è consigliabile farlo, a meno che non sia assolutamente necessario, dato che l'intervallo di sincronizzazione ha un impatto notevole sulle prestazioni del servizio di backup e sull'obiettivo del punto di ripristino (RPO).</span><span class="sxs-lookup"><span data-stu-id="432c1-114">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="432c1-115">Per ottenere lo stato del servizio di backup per un determinato pool</span><span class="sxs-lookup"><span data-stu-id="432c1-115">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="432c1-116">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="432c1-116">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> <span data-ttu-id="432c1-117">Lo stato di sincronizzazione del servizio di backup è definito in maniera unidirezionale da un pool (P1) al relativo pool di backup (P2).</span><span class="sxs-lookup"><span data-stu-id="432c1-117">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="432c1-118">Lo stato di sincronizzazione da P1 a P2 può essere diverso da quello da P2 a P1.</span><span class="sxs-lookup"><span data-stu-id="432c1-118">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="432c1-119">Per P1-P2, il servizio di backup si trova in uno stato "costante" se tutte le modifiche apportate in P1 vengono completamente replicate in P2 nell'intervallo di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="432c1-119">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="432c1-120">Si trova nello stato "Final" se non ci sono più modifiche da sincronizzare da P1 a P2.</span><span class="sxs-lookup"><span data-stu-id="432c1-120">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="432c1-121">Entrambi gli Stati indicano uno snapshot del servizio di backup al momento dell'esecuzione del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="432c1-121">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="432c1-122">Non implica che lo stato restituito rimarrà come in seguito.</span><span class="sxs-lookup"><span data-stu-id="432c1-122">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="432c1-123">In particolare, lo stato "finale" continuerà a contenere solo se P1 non genera alcuna modifica dopo l'esecuzione del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="432c1-123">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="432c1-124">Questo vale in caso di mancanza di P1 oltre a P2 dopo che P1 viene inserito nella modalità di sola lettura come parte della logica di esecuzione <STRONG>Invoke-CsPoolFailOver</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="432c1-124">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the <STRONG>Invoke-CsPoolfailover</STRONG> execution logic.</span></span>



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="432c1-125">Per ottenere informazioni sulla relazione di backup per un determinato pool</span><span class="sxs-lookup"><span data-stu-id="432c1-125">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="432c1-126">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="432c1-126">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="432c1-127">Per forzare una sincronizzazione del servizio di backup</span><span class="sxs-lookup"><span data-stu-id="432c1-127">To force a Backup Service sync</span></span>

<span data-ttu-id="432c1-128">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="432c1-128">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

