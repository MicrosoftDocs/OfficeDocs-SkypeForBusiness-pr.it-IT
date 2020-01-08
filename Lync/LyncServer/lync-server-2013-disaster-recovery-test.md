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

# <a name="disaster-recovery-test-in-lync-server-2013"></a>Test del ripristino di emergenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-01-26_

Eseguire un ripristino di sistema per un server di pool di Lync Server 2013 per testare il processo di ripristino di emergenza documentato. Il test consente di simulare un errore hardware completo per un server e ha lo scopo di garantire la disponibilità dei dati, dei piani e delle risorse per il ripristino. Provare ad avvicendare ogni mese un campo d'azione diverso, così da sottoporre un server diverso o di un'altra attrezzatura al test.

La pianificazione in base alla quale le organizzazioni svolgono il test del ripristino di emergenza è soggetta a variazioni. È molto importante non ignorare o trascurare l'esecuzione del test del ripristino di emergenza.

<div>


Esportare la topologia, i criteri e le impostazioni di configurazione di Lync Server 2013 in un file. Questo file, tra le altre cose, può essere utilizzato per ripristinare le informazioni incluse nell'archivio di gestione centrale dopo una perdita di dati conseguente a un aggiornamento, un errore hardware o altri problemi.

Importare la topologia, i criteri e le impostazioni di configurazione di Lync Server 2013 nell'archivio di gestione centrale o nel computer locale, come illustrato nei comandi seguenti:

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

Per eseguire il backup dei dati di Lync Server 2013 di produzione:

  - Eseguire il backup dei database RTC e LCSLog usando il processo di backup standard di SQL Server per scaricare il database in un file o un dispositivo di dump del nastro.

  - Utilizzare applicazioni di terze parti per eseguire il backup dei dati in file o su nastro.

  - Creare un file di esportazione XML dell'intero database RTC utilizzando il cmdlet Export-CsUserData.

  - Utilizzare il backup del file system o ricorrere a terze parti per eseguire il backup del contenuto delle riunioni e dei registri di conformità.

  - Usare lo strumento della riga di comando Export-CsConfiguration per eseguire il backup delle impostazioni di Lync Server 2013.

Il primo passaggio della procedura di failover prevede lo spostamento forzato di utenti dal pool di produzione al pool del ripristino di emergenza.

Lo spostamento è forzato poiché il pool di produzione non ammette il riposizionamento degli utenti.

Il processo utente di trasferimento di Lync Server 2013 è effettivamente una modifica a un attributo dell'oggetto account utente oltre a un aggiornamento di record nel database SQL RTC.

Per il ripristino dei dati è possibile attenersi a due procedure.

  - Il database RTC può essere ripristinato dal dispositivo di dump del backup originale da SQL Server di produzione usando il processo di ripristino standard di SQL Server oppure usando un'utilità di backup/ripristino di terze parti.

  - I dati di contatto degli utenti possono essere ripristinati con l'utility DBIMPEXP.exe, utilizzando il file XML generato dall'esportazione di SQL Server di produzione.

Dopo il ripristino dei dati, gli utenti possono connettersi efficacemente al pool di ripristino di emergenza Lync Server 2013 e operare come di consueto.

Per consentire agli utenti di connettersi al pool di ripristino di emergenza Lync Server 2013, sarà necessaria una modifica del record DNS.

I client utilizzano la configurazione automatica e i record SRV DNS di cui viene fatto riferimento al pool di produzione Lync Server 2013:

  - SRV: \_SIP. \_TLS. \<domain\> /CNAME: SIP. \<dominio\>

  - CNAME: SIP. \<dominio\> /CVC-pool-1. \<dominio\>

Per agevolare il failover, il record CNAME deve essere aggiornato in modo che faccia riferimento all'FQDN DROCSPool:

  - CNAME: SIP. \<dominio\> /DROCSPool. \<dominio\>

  - SIP. \<dominio\>

  - AV.\<Domain\>

  - webconf. \<dominio\>

  - OCSServices. \<dominio\>

<div>


> [!IMPORTANT]  
> Per procedure dettagliate per l'amministrazione e la gestione, vedere <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">backup e ripristino di Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[Cmdlet di backup e disponibilità elevata in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[Import-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Backup e ripristino di Lync Server 2013](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[Gestione di ripristino di emergenza, disponibilità elevata e servizio di backup di Lync Server 2013](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

