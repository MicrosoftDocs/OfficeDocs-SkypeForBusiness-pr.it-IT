---
title: 'Lync Server 2013: test di ripristino di emergenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35b9aa12f7b3ae9b0c160147ad473976c92ab32e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a><span data-ttu-id="3f85a-102">Test di ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f85a-102">Disaster recovery test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f85a-103">_**Ultimo argomento modificato:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="3f85a-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="3f85a-104">Eseguire un ripristino del sistema per un server pool di Lync Server 2013 per testare il processo di ripristino di emergenza documentato.</span><span class="sxs-lookup"><span data-stu-id="3f85a-104">Perform a system recovery for a Lync Server 2013 pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="3f85a-105">Questo test simula un errore hardware completo per un server e contribuisce a garantire che le risorse, i piani e i dati siano disponibili per il ripristino.</span><span class="sxs-lookup"><span data-stu-id="3f85a-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data is available for recovery.</span></span> <span data-ttu-id="3f85a-106">Provare a ruotare lo stato attivo del test ogni mese in modo che l'organizzazione verifichi ogni volta l'errore di un server o di un altro dispositivo diverso.</span><span class="sxs-lookup"><span data-stu-id="3f85a-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span>

<span data-ttu-id="3f85a-107">Si noti che la pianificazione in base alla quale le organizzazioni eseguono i test di ripristino di emergenza variano.</span><span class="sxs-lookup"><span data-stu-id="3f85a-107">Note that the schedule by which organizations perform Disaster Recovery testing will vary.</span></span> <span data-ttu-id="3f85a-108">È molto importante che i test di ripristino di emergenza non vengano ignorati o trascurati.</span><span class="sxs-lookup"><span data-stu-id="3f85a-108">It is very important that disaster recovery testing is not ignored or neglected.</span></span>

<div>


<span data-ttu-id="3f85a-109">Esportare la topologia, i criteri e le impostazioni di configurazione di Lync Server 2013 in un file.</span><span class="sxs-lookup"><span data-stu-id="3f85a-109">Export your Lync Server 2013 topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="3f85a-110">Tra le altre cose, questo file può essere utilizzato per ripristinare queste informazioni nell'archivio di gestione centrale dopo un aggiornamento, un errore hardware o un altro problema che ha provocato la perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="3f85a-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="3f85a-111">Importare la topologia, i criteri e le impostazioni di configurazione di Lync Server 2013 nell'archivio di gestione centrale o nel computer locale, come illustrato nei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f85a-111">Import your Lync Server 2013 topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span>

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

<span data-ttu-id="3f85a-112">Per eseguire il backup dei dati di Lync Server 2013 di produzione:</span><span class="sxs-lookup"><span data-stu-id="3f85a-112">To back up production Lync Server 2013 data:</span></span>

  - <span data-ttu-id="3f85a-113">Eseguire il backup dei database RTC e LCSLog utilizzando il processo di backup standard di SQL Server per eseguire il dump del database in un dispositivo di dump di file o nastri.</span><span class="sxs-lookup"><span data-stu-id="3f85a-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>

  - <span data-ttu-id="3f85a-114">Utilizzare un'applicazione di backup di terze parti per eseguire il backup dei dati in file o su nastro.</span><span class="sxs-lookup"><span data-stu-id="3f85a-114">Use third-party backup application to back up the data to file or to tape.</span></span>

  - <span data-ttu-id="3f85a-115">Utilizzare il cmdlet Export-CsUserData per creare un'esportazione XML dell'intero database RTC.</span><span class="sxs-lookup"><span data-stu-id="3f85a-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>

  - <span data-ttu-id="3f85a-116">Utilizzare il backup del file System o di terze parti per eseguire il back up del contenuto delle riunioni e dei registri di conformità.</span><span class="sxs-lookup"><span data-stu-id="3f85a-116">Use the file system backup or third-party to back up meeting content and compliance logs.</span></span>

  - <span data-ttu-id="3f85a-117">Utilizzare lo strumento da riga di comando Export-CsConfiguration per eseguire il backup delle impostazioni di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f85a-117">Use the Export-CsConfiguration command-line tool to back up Lync Server 2013 settings.</span></span>

<span data-ttu-id="3f85a-118">Il primo passaggio della procedura di failover include uno spostamento forzato degli utenti dal pool di produzione al pool di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="3f85a-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span>

<span data-ttu-id="3f85a-119">Si tratta di uno spostamento forzato poiché il pool di produzione non è disponibile per accettare la rilocazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3f85a-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="3f85a-120">Il processo utente di spostamento di Lync Server 2013 è in effetti una modifica a un attributo dell'oggetto account utente oltre a un aggiornamento dei record sul database SQL RTC.</span><span class="sxs-lookup"><span data-stu-id="3f85a-120">The Lync Server 2013 move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span>

<span data-ttu-id="3f85a-121">Questi dati possono essere ripristinati mediante i due processi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f85a-121">This data can be restored through the following two processes:</span></span>

  - <span data-ttu-id="3f85a-122">Il database RTC può essere ripristinato dal dispositivo di dump del backup originale da SQL Server di produzione utilizzando il processo di ripristino di SQL Server standard oppure utilizzando un'utilità di backup/ripristino di terze parti.</span><span class="sxs-lookup"><span data-stu-id="3f85a-122">RTC database can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

  - <span data-ttu-id="3f85a-123">I dati dei contatti utente possono essere ripristinati con l'utilità DBIMPEXP. exe utilizzando il file XML creato dall'esportazione SQL Server di produzione.</span><span class="sxs-lookup"><span data-stu-id="3f85a-123">User contact data can be restored with the DBIMPEXP.exe utility using the XML file that was created from the production SQL Server export.</span></span>

<span data-ttu-id="3f85a-124">Dopo aver ripristinato i dati, gli utenti possono connettersi efficacemente al pool di ripristino di emergenza Lync Server 2013 e funzionare come di consueto.</span><span class="sxs-lookup"><span data-stu-id="3f85a-124">After this data is restored, users can effectively connect to the Disaster Recovery Lync Server 2013 pool, and operate as usual.</span></span>

<span data-ttu-id="3f85a-125">Per consentire agli utenti di connettersi al pool di ripristino di emergenza Lync Server 2013, sarà necessaria una modifica di record DNS.</span><span class="sxs-lookup"><span data-stu-id="3f85a-125">To enable users to connect to the Disaster Recovery Lync Server 2013 pool, a DNS record change will be required.</span></span>

<span data-ttu-id="3f85a-126">Il pool di produzione Lync Server 2013 verrà referenziato dai client che utilizzano la configurazione automatica e i record DNS SRV di:</span><span class="sxs-lookup"><span data-stu-id="3f85a-126">The production Lync Server 2013 pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

  - <span data-ttu-id="3f85a-127">SRV: \_SIP. \_TLS. \<domain\> /CNAME: SIP. \<dominio\></span><span class="sxs-lookup"><span data-stu-id="3f85a-127">SRV: \_sip.\_tls.\<domain\> /CNAME: SIP.\<domain\></span></span>

  - <span data-ttu-id="3f85a-128">CNAME: SIP. \</CVC-pool-1.\> di dominio \<dominio\></span><span class="sxs-lookup"><span data-stu-id="3f85a-128">CNAME: SIP.\<domain\> /cvc-pool-1.\<domain\></span></span>

<span data-ttu-id="3f85a-129">Per semplificare il failover, è necessario che il record CNAME sia aggiornato per fare riferimento al nome di dominio completo di DROCSPool:</span><span class="sxs-lookup"><span data-stu-id="3f85a-129">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

  - <span data-ttu-id="3f85a-130">CNAME: SIP. \</DROCSPool.\> di dominio \<dominio\></span><span class="sxs-lookup"><span data-stu-id="3f85a-130">CNAME: SIP.\<domain\> /DROCSPool.\<domain\></span></span>

  - <span data-ttu-id="3f85a-131">SIP. \<dominio\></span><span class="sxs-lookup"><span data-stu-id="3f85a-131">Sip.\<domain\></span></span>

  - <span data-ttu-id="3f85a-132">AV.\<Domain\></span><span class="sxs-lookup"><span data-stu-id="3f85a-132">AV.\<domain\></span></span>

  - <span data-ttu-id="3f85a-133">webconf. \<dominio\></span><span class="sxs-lookup"><span data-stu-id="3f85a-133">webconf.\<domain\></span></span>

  - <span data-ttu-id="3f85a-134">OCSServices. \<dominio\></span><span class="sxs-lookup"><span data-stu-id="3f85a-134">OCSServices.\<domain\></span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3f85a-135">Per le procedure dettagliate per l'amministrazione e la gestione, vedere <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">backup e ripristino di Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3f85a-135">For detailed administration and management procedures, see <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Backing up and restoring Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3f85a-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f85a-136">See Also</span></span>


[<span data-ttu-id="3f85a-137">Pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f85a-137">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[<span data-ttu-id="3f85a-138">Cmdlet per backup e disponibilità elevata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f85a-138">Backup and high availability cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[<span data-ttu-id="3f85a-139">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="3f85a-139">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="3f85a-140">Backup e ripristino di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f85a-140">Backing up and restoring Lync Server 2013</span></span>](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[<span data-ttu-id="3f85a-141">Gestione di ripristino di emergenza, disponibilità elevata e servizio di backup di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f85a-141">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

