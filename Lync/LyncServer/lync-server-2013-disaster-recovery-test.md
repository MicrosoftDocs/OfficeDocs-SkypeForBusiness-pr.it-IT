---
title: 'Lync Server 2013: test del ripristino di emergenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9b17f5841cad96cb83399082f61c00194ec4828
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a><span data-ttu-id="44448-102">Test del ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44448-102">Disaster recovery test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44448-103">_**Argomento Ultima modifica:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="44448-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="44448-104">Eseguire un ripristino di sistema per un server di pool di Lync Server 2013 per testare il processo di ripristino di emergenza documentato.</span><span class="sxs-lookup"><span data-stu-id="44448-104">Perform a system recovery for a Lync Server 2013 pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="44448-105">Il test consente di simulare un errore hardware completo per un server e ha lo scopo di garantire la disponibilità dei dati, dei piani e delle risorse per il ripristino.</span><span class="sxs-lookup"><span data-stu-id="44448-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data is available for recovery.</span></span> <span data-ttu-id="44448-106">Provare ad avvicendare ogni mese un campo d'azione diverso, così da sottoporre un server diverso o di un'altra attrezzatura al test.</span><span class="sxs-lookup"><span data-stu-id="44448-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span>

<span data-ttu-id="44448-p102">La pianificazione in base alla quale le organizzazioni svolgono il test del ripristino di emergenza è soggetta a variazioni. È molto importante non ignorare o trascurare l'esecuzione del test del ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="44448-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span>

<div>


<span data-ttu-id="44448-109">Esportare la topologia, i criteri e le impostazioni di configurazione di Lync Server 2013 in un file.</span><span class="sxs-lookup"><span data-stu-id="44448-109">Export your Lync Server 2013 topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="44448-110">Questo file, tra le altre cose, può essere utilizzato per ripristinare le informazioni incluse nell'archivio di gestione centrale dopo una perdita di dati conseguente a un aggiornamento, un errore hardware o altri problemi.</span><span class="sxs-lookup"><span data-stu-id="44448-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="44448-111">Importare la topologia, i criteri e le impostazioni di configurazione di Lync Server 2013 nell'archivio di gestione centrale o nel computer locale, come illustrato nei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="44448-111">Import your Lync Server 2013 topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span>

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

<span data-ttu-id="44448-112">Per eseguire il backup dei dati di Lync Server 2013 di produzione:</span><span class="sxs-lookup"><span data-stu-id="44448-112">To back up production Lync Server 2013 data:</span></span>

  - <span data-ttu-id="44448-113">Eseguire il backup dei database RTC e LCSLog usando il processo di backup standard di SQL Server per scaricare il database in un file o un dispositivo di dump del nastro.</span><span class="sxs-lookup"><span data-stu-id="44448-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>

  - <span data-ttu-id="44448-114">Utilizzare applicazioni di terze parti per eseguire il backup dei dati in file o su nastro.</span><span class="sxs-lookup"><span data-stu-id="44448-114">Use third-party backup application to back up the data to file or to tape.</span></span>

  - <span data-ttu-id="44448-115">Creare un file di esportazione XML dell'intero database RTC utilizzando il cmdlet Export-CsUserData.</span><span class="sxs-lookup"><span data-stu-id="44448-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>

  - <span data-ttu-id="44448-116">Utilizzare il backup del file system o ricorrere a terze parti per eseguire il backup del contenuto delle riunioni e dei registri di conformità.</span><span class="sxs-lookup"><span data-stu-id="44448-116">Use the file system backup or third-party to back up meeting content and compliance logs.</span></span>

  - <span data-ttu-id="44448-117">Usare lo strumento della riga di comando Export-CsConfiguration per eseguire il backup delle impostazioni di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="44448-117">Use the Export-CsConfiguration command-line tool to back up Lync Server 2013 settings.</span></span>

<span data-ttu-id="44448-118">Il primo passaggio della procedura di failover prevede lo spostamento forzato di utenti dal pool di produzione al pool del ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="44448-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span>

<span data-ttu-id="44448-119">Lo spostamento è forzato poiché il pool di produzione non ammette il riposizionamento degli utenti.</span><span class="sxs-lookup"><span data-stu-id="44448-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="44448-120">Il processo utente di trasferimento di Lync Server 2013 è effettivamente una modifica a un attributo dell'oggetto account utente oltre a un aggiornamento di record nel database SQL RTC.</span><span class="sxs-lookup"><span data-stu-id="44448-120">The Lync Server 2013 move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span>

<span data-ttu-id="44448-121">Per il ripristino dei dati è possibile attenersi a due procedure.</span><span class="sxs-lookup"><span data-stu-id="44448-121">This data can be restored through the following two processes:</span></span>

  - <span data-ttu-id="44448-122">Il database RTC può essere ripristinato dal dispositivo di dump del backup originale da SQL Server di produzione usando il processo di ripristino standard di SQL Server oppure usando un'utilità di backup/ripristino di terze parti.</span><span class="sxs-lookup"><span data-stu-id="44448-122">RTC database can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

  - <span data-ttu-id="44448-123">I dati di contatto degli utenti possono essere ripristinati con l'utility DBIMPEXP.exe, utilizzando il file XML generato dall'esportazione di SQL Server di produzione.</span><span class="sxs-lookup"><span data-stu-id="44448-123">User contact data can be restored with the DBIMPEXP.exe utility using the XML file that was created from the production SQL Server export.</span></span>

<span data-ttu-id="44448-124">Dopo il ripristino dei dati, gli utenti possono connettersi efficacemente al pool di ripristino di emergenza Lync Server 2013 e operare come di consueto.</span><span class="sxs-lookup"><span data-stu-id="44448-124">After this data is restored, users can effectively connect to the Disaster Recovery Lync Server 2013 pool, and operate as usual.</span></span>

<span data-ttu-id="44448-125">Per consentire agli utenti di connettersi al pool di ripristino di emergenza Lync Server 2013, sarà necessaria una modifica del record DNS.</span><span class="sxs-lookup"><span data-stu-id="44448-125">To enable users to connect to the Disaster Recovery Lync Server 2013 pool, a DNS record change will be required.</span></span>

<span data-ttu-id="44448-126">I client utilizzano la configurazione automatica e i record SRV DNS di cui viene fatto riferimento al pool di produzione Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="44448-126">The production Lync Server 2013 pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

  - <span data-ttu-id="44448-127">SRV: \_SIP. \_TLS. \<domain\> /CNAME: SIP. \<dominio\></span><span class="sxs-lookup"><span data-stu-id="44448-127">SRV: \_sip.\_tls.\<domain\> /CNAME: SIP.\<domain\></span></span>

  - <span data-ttu-id="44448-128">CNAME: SIP. \<dominio\> /CVC-pool-1. \<dominio\></span><span class="sxs-lookup"><span data-stu-id="44448-128">CNAME: SIP.\<domain\> /cvc-pool-1.\<domain\></span></span>

<span data-ttu-id="44448-129">Per agevolare il failover, il record CNAME deve essere aggiornato in modo che faccia riferimento all'FQDN DROCSPool:</span><span class="sxs-lookup"><span data-stu-id="44448-129">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

  - <span data-ttu-id="44448-130">CNAME: SIP. \<dominio\> /DROCSPool. \<dominio\></span><span class="sxs-lookup"><span data-stu-id="44448-130">CNAME: SIP.\<domain\> /DROCSPool.\<domain\></span></span>

  - <span data-ttu-id="44448-131">SIP. \<dominio\></span><span class="sxs-lookup"><span data-stu-id="44448-131">Sip.\<domain\></span></span>

  - <span data-ttu-id="44448-132">AV.\<Domain\></span><span class="sxs-lookup"><span data-stu-id="44448-132">AV.\<domain\></span></span>

  - <span data-ttu-id="44448-133">webconf. \<dominio\></span><span class="sxs-lookup"><span data-stu-id="44448-133">webconf.\<domain\></span></span>

  - <span data-ttu-id="44448-134">OCSServices. \<dominio\></span><span class="sxs-lookup"><span data-stu-id="44448-134">OCSServices.\<domain\></span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="44448-135">Per procedure dettagliate per l'amministrazione e la gestione, vedere <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">backup e ripristino di Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="44448-135">For detailed administration and management procedures, see <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Backing up and restoring Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="44448-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44448-136">See Also</span></span>


[<span data-ttu-id="44448-137">Pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44448-137">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[<span data-ttu-id="44448-138">Cmdlet di backup e disponibilità elevata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44448-138">Backup and high availability cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[<span data-ttu-id="44448-139">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="44448-139">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="44448-140">Backup e ripristino di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44448-140">Backing up and restoring Lync Server 2013</span></span>](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[<span data-ttu-id="44448-141">Gestione di ripristino di emergenza, disponibilità elevata e servizio di backup di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44448-141">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

