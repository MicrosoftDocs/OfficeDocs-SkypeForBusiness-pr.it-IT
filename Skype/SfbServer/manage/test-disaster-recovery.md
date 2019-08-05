---
title: Test di ripristino di emergenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Eseguire un ripristino di sistema per un server pool di Skype for Business Server per testare il processo di ripristino di emergenza documentato
ms.openlocfilehash: d65f8bfa512a3954728e09d659b571335d32a379
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188498"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="bc583-103">Test di ripristino di emergenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bc583-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="bc583-104">Eseguire un ripristino di sistema per un server pool di Skype for Business Server per testare il processo di ripristino di emergenza documentato.</span><span class="sxs-lookup"><span data-stu-id="bc583-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="bc583-105">Questo test simula un errore hardware completo per un server e consente di garantire che le risorse, i piani e i dati siano disponibili per il ripristino.</span><span class="sxs-lookup"><span data-stu-id="bc583-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="bc583-106">Provare ad avvicendare ogni mese un campo d'azione diverso, così da sottoporre un server diverso o di un'altra attrezzatura al test.</span><span class="sxs-lookup"><span data-stu-id="bc583-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="bc583-p102">La pianificazione in base alla quale le organizzazioni svolgono il test del ripristino di emergenza è soggetta a variazioni. È molto importante non ignorare o trascurare l'esecuzione del test del ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="bc583-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="bc583-109">Esportare la topologia, i criteri e le impostazioni di configurazione di Skype for Business Server in un file.</span><span class="sxs-lookup"><span data-stu-id="bc583-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="bc583-110">Questo file, tra le altre cose, può essere utilizzato per ripristinare le informazioni incluse nell'archivio di gestione centrale dopo una perdita di dati conseguente a un aggiornamento, un errore hardware o altri problemi.</span><span class="sxs-lookup"><span data-stu-id="bc583-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="bc583-111">Importare la topologia, i criteri e le impostazioni di configurazione di Skype for Business Server in Central Management Store o nel computer locale, come illustrato nei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc583-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="bc583-112">Per eseguire il backup dei dati di produzione:</span><span class="sxs-lookup"><span data-stu-id="bc583-112">To back up production data:</span></span>

- <span data-ttu-id="bc583-113">Eseguire il backup dei database RTC e LCSLog usando il processo di backup standard di SQL Server per scaricare il database in un file o un dispositivo di dump del nastro.</span><span class="sxs-lookup"><span data-stu-id="bc583-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="bc583-114">Utilizzare applicazioni di terze parti per eseguire il backup dei dati in file o su nastro.</span><span class="sxs-lookup"><span data-stu-id="bc583-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="bc583-115">Creare un file di esportazione XML dell'intero database RTC utilizzando il cmdlet Export-CsUserData.</span><span class="sxs-lookup"><span data-stu-id="bc583-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="bc583-116">Usare il backup del file System o il backup di terze parti per eseguire il backup di contenuto della riunione e registri di conformità.</span><span class="sxs-lookup"><span data-stu-id="bc583-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="bc583-117">Usare lo strumento della riga di comando Export-CsConfiguration per eseguire il backup delle impostazioni di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bc583-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="bc583-118">Il primo passaggio della procedura di failover prevede lo spostamento forzato di utenti dal pool di produzione al pool del ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="bc583-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="bc583-119">Lo spostamento è forzato poiché il pool di produzione non ammette il riposizionamento degli utenti.</span><span class="sxs-lookup"><span data-stu-id="bc583-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="bc583-120">Il processo utente di trasferimento di Skype for Business Server è effettivamente una modifica a un attributo dell'oggetto account utente oltre a un aggiornamento di record nel database SQL RTC.</span><span class="sxs-lookup"><span data-stu-id="bc583-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="bc583-121">Questi dati possono essere ripristinati dal dispositivo di dump del backup originale dalla versione di SQL Server di produzione usando il processo di ripristino standard di SQL Server oppure usando un'utilità di backup/ripristino di terze parti.</span><span class="sxs-lookup"><span data-stu-id="bc583-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="bc583-122">Dopo il ripristino di questi dati, gli utenti possono connettersi efficacemente al pool di ripristino di emergenza e operare come di consueto.</span><span class="sxs-lookup"><span data-stu-id="bc583-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="bc583-123">Per consentire agli utenti di connettersi al pool di ripristino di emergenza, sarà necessaria una modifica del record DNS.</span><span class="sxs-lookup"><span data-stu-id="bc583-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="bc583-124">I client che usano il pool di Skype for business di produzione verranno referenziati usando i record SRV di configurazione automatica e DNS di:</span><span class="sxs-lookup"><span data-stu-id="bc583-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="bc583-125">SRV: _sip. _tls. \<dominio>/CNAME: SIP. \<> di dominio</span><span class="sxs-lookup"><span data-stu-id="bc583-125">SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="bc583-126">CNAME: SIP. \<dominio>/CVC-pool-1. \<> di dominio</span><span class="sxs-lookup"><span data-stu-id="bc583-126">CNAME: SIP.\<domain> /cvc-pool-1.\<domain></span></span>

<span data-ttu-id="bc583-127">Per agevolare il failover, il record CNAME deve essere aggiornato in modo che faccia riferimento all'FQDN DROCSPool:</span><span class="sxs-lookup"><span data-stu-id="bc583-127">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="bc583-128">CNAME: SIP.<domain></span><span class="sxs-lookup"><span data-stu-id="bc583-128">CNAME: SIP.<domain></span></span> <span data-ttu-id="bc583-129">/DROCSPool. \<> di dominio</span><span class="sxs-lookup"><span data-stu-id="bc583-129">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="bc583-130">SIP. \<> di dominio</span><span class="sxs-lookup"><span data-stu-id="bc583-130">Sip.\<domain></span></span>
- <span data-ttu-id="bc583-131">> AV\<. Domain</span><span class="sxs-lookup"><span data-stu-id="bc583-131">AV.\<domain></span></span>
- <span data-ttu-id="bc583-132">webconf. \<> di dominio</span><span class="sxs-lookup"><span data-stu-id="bc583-132">webconf.\<domain></span></span>
