---
title: Test di ripristino di emergenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Eseguire un ripristino del sistema per un server pool di Skype for Business Server per testare il processo di ripristino di emergenza documentato
ms.openlocfilehash: 92515a59f4ada2589a371cc9384c63a376e96cf8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832816"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="75e94-103">Test di ripristino di emergenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="75e94-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="75e94-104">Eseguire un ripristino del sistema per un server pool di Skype for Business Server per testare il processo di ripristino di emergenza documentato.</span><span class="sxs-lookup"><span data-stu-id="75e94-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="75e94-105">Questo test simula un errore hardware completo per un server e contribuisce a garantire che le risorse, i piani e i dati siano disponibili per il ripristino.</span><span class="sxs-lookup"><span data-stu-id="75e94-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="75e94-106">Provare a ruotare lo stato attivo del test ogni mese in modo che l'organizzazione verifichi ogni volta l'errore di un server o di un altro dispositivo diverso.</span><span class="sxs-lookup"><span data-stu-id="75e94-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="75e94-107">Si noti che la pianificazione in base alla quale le organizzazioni eseguono i test di ripristino di emergenza variano.</span><span class="sxs-lookup"><span data-stu-id="75e94-107">Note that the schedule by which organizations perform Disaster Recovery testing will vary.</span></span> <span data-ttu-id="75e94-108">È molto importante che i test di ripristino di emergenza non vengano ignorati o trascurati.</span><span class="sxs-lookup"><span data-stu-id="75e94-108">It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="75e94-109">Esportare la topologia, i criteri e le impostazioni di configurazione di Skype for Business Server in un file.</span><span class="sxs-lookup"><span data-stu-id="75e94-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="75e94-110">Tra le altre cose, questo file può essere utilizzato per ripristinare queste informazioni nell'archivio di gestione centrale dopo un aggiornamento, un errore hardware o un altro problema che ha provocato la perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="75e94-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="75e94-111">Importare la topologia, i criteri e le impostazioni di configurazione di Skype for Business Server nell'archivio di gestione centrale o nel computer locale, come illustrato nei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="75e94-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="75e94-112">Per eseguire il backup dei dati di produzione:</span><span class="sxs-lookup"><span data-stu-id="75e94-112">To back up production data:</span></span>

- <span data-ttu-id="75e94-113">Eseguire il backup dei database RTC e LCSLog utilizzando il processo di backup standard di SQL Server per eseguire il dump del database in un dispositivo di dump di file o nastri.</span><span class="sxs-lookup"><span data-stu-id="75e94-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="75e94-114">Utilizzare un'applicazione di backup di terze parti per eseguire il backup dei dati in file o su nastro.</span><span class="sxs-lookup"><span data-stu-id="75e94-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="75e94-115">Utilizzare il cmdlet Export-CsUserData per creare un'esportazione XML dell'intero database RTC.</span><span class="sxs-lookup"><span data-stu-id="75e94-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="75e94-116">Utilizzare il backup del file System o il backup di terze parti per eseguire il backup dei contenuti delle riunioni e dei registri di conformità.</span><span class="sxs-lookup"><span data-stu-id="75e94-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="75e94-117">Utilizzare lo strumento da riga di comando Export-CsConfiguration per eseguire il backup delle impostazioni di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="75e94-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="75e94-118">Il primo passaggio della procedura di failover include uno spostamento forzato degli utenti dal pool di produzione al pool di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="75e94-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="75e94-119">Si tratta di uno spostamento forzato poiché il pool di produzione non è disponibile per accettare la rilocazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="75e94-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="75e94-120">Il processo di spostamento degli utenti di Skype for Business Server è in effetti una modifica a un attributo dell'oggetto account utente oltre a un aggiornamento dei record sul database SQL RTC.</span><span class="sxs-lookup"><span data-stu-id="75e94-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="75e94-121">Questi dati possono essere ripristinati dal dispositivo di dump del backup originale dal SQL Server di produzione utilizzando il processo di ripristino di SQL Server standard o utilizzando un'utilità di backup/ripristino di terze parti.</span><span class="sxs-lookup"><span data-stu-id="75e94-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="75e94-122">Dopo aver ripristinato i dati, gli utenti possono connettersi efficacemente al pool di ripristino di emergenza e funzionare come di consueto.</span><span class="sxs-lookup"><span data-stu-id="75e94-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="75e94-123">Per consentire agli utenti di connettersi al pool di ripristino di emergenza, sarà necessaria una modifica di record DNS.</span><span class="sxs-lookup"><span data-stu-id="75e94-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="75e94-124">Il pool di produzione Skype for business verrà referenziato dai client che utilizzano la configurazione automatica e i record DNS SRV di:</span><span class="sxs-lookup"><span data-stu-id="75e94-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="75e94-125">SRV: _sip. _tls.\<domain></span><span class="sxs-lookup"><span data-stu-id="75e94-125">SRV: _sip._tls.\<domain></span></span> <span data-ttu-id="75e94-126">/CNAME: SIP.\<domain></span><span class="sxs-lookup"><span data-stu-id="75e94-126">/CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="75e94-127">CNAME: SIP.\<domain></span><span class="sxs-lookup"><span data-stu-id="75e94-127">CNAME: SIP.\<domain></span></span> <span data-ttu-id="75e94-128">/cvc-pool-1.\<domain></span><span class="sxs-lookup"><span data-stu-id="75e94-128">/cvc-pool-1.\<domain></span></span>

<span data-ttu-id="75e94-129">Per semplificare il failover, è necessario che il record CNAME sia aggiornato per fare riferimento al nome di dominio completo di DROCSPool:</span><span class="sxs-lookup"><span data-stu-id="75e94-129">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="75e94-130">CNAME: SIP.<domain></span><span class="sxs-lookup"><span data-stu-id="75e94-130">CNAME: SIP.<domain></span></span> <span data-ttu-id="75e94-131">/DROCSPool.\<domain></span><span class="sxs-lookup"><span data-stu-id="75e94-131">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="75e94-132">SIP.\<domain></span><span class="sxs-lookup"><span data-stu-id="75e94-132">Sip.\<domain></span></span>
- <span data-ttu-id="75e94-133">AV.\<domain></span><span class="sxs-lookup"><span data-stu-id="75e94-133">AV.\<domain></span></span>
- <span data-ttu-id="75e94-134">webconf.\<domain></span><span class="sxs-lookup"><span data-stu-id="75e94-134">webconf.\<domain></span></span>
