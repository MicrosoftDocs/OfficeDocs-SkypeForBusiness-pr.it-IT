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
ms.openlocfilehash: c0b274d933fbb1c9f47b219a492403bd1c5f58d5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a>Test di ripristino di emergenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-01-26_

Eseguire un ripristino del sistema per un server pool di Lync Server 2013 per testare il processo di ripristino di emergenza documentato. Questo test simula un errore hardware completo per un server e contribuisce a garantire che le risorse, i piani e i dati siano disponibili per il ripristino. Provare a ruotare lo stato attivo del test ogni mese in modo che l'organizzazione verifichi ogni volta l'errore di un server o di un altro dispositivo diverso.

Si noti che la pianificazione in base alla quale le organizzazioni eseguono i test di ripristino di emergenza variano. È molto importante che i test di ripristino di emergenza non vengano ignorati o trascurati.

<div>


Esportare la topologia, i criteri e le impostazioni di configurazione di Lync Server 2013 in un file. Tra le altre cose, questo file può essere utilizzato per ripristinare queste informazioni nell'archivio di gestione centrale dopo un aggiornamento, un errore hardware o un altro problema che ha provocato la perdita di dati.

Importare la topologia, i criteri e le impostazioni di configurazione di Lync Server 2013 nell'archivio di gestione centrale o nel computer locale, come illustrato nei comandi seguenti:

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

Per eseguire il backup dei dati di Lync Server 2013 di produzione:

  - Eseguire il backup dei database RTC e LCSLog utilizzando il processo di backup standard di SQL Server per eseguire il dump del database in un dispositivo di dump di file o nastri.

  - Utilizzare un'applicazione di backup di terze parti per eseguire il backup dei dati in file o su nastro.

  - Utilizzare il cmdlet Export-CsUserData per creare un'esportazione XML dell'intero database RTC.

  - Utilizzare il backup del file System o di terze parti per eseguire il back up del contenuto delle riunioni e dei registri di conformità.

  - Utilizzare lo strumento da riga di comando Export-CsConfiguration per eseguire il backup delle impostazioni di Lync Server 2013.

Il primo passaggio della procedura di failover include uno spostamento forzato degli utenti dal pool di produzione al pool di ripristino di emergenza.

Si tratta di uno spostamento forzato poiché il pool di produzione non è disponibile per accettare la rilocazione dell'utente.

Il processo utente di spostamento di Lync Server 2013 è in effetti una modifica a un attributo dell'oggetto account utente oltre a un aggiornamento dei record sul database SQL RTC.

Questi dati possono essere ripristinati mediante i due processi seguenti:

  - Il database RTC può essere ripristinato dal dispositivo di dump del backup originale da SQL Server di produzione utilizzando il processo di ripristino di SQL Server standard oppure utilizzando un'utilità di backup/ripristino di terze parti.

  - I dati dei contatti utente possono essere ripristinati con l'utilità DBIMPEXP. exe utilizzando il file XML creato dall'esportazione SQL Server di produzione.

Dopo aver ripristinato i dati, gli utenti possono connettersi efficacemente al pool di ripristino di emergenza Lync Server 2013 e funzionare come di consueto.

Per consentire agli utenti di connettersi al pool di ripristino di emergenza Lync Server 2013, sarà necessaria una modifica di record DNS.

Il pool di produzione Lync Server 2013 verrà referenziato dai client che utilizzano la configurazione automatica e i record DNS SRV di:

  - SRV: \_SIP. \_TLS. \<domain\> /CNAME: SIP. \<dominio\>

  - CNAME: SIP. \</CVC-pool-1.\> di dominio \<dominio\>

Per semplificare il failover, è necessario che il record CNAME sia aggiornato per fare riferimento al nome di dominio completo di DROCSPool:

  - CNAME: SIP. \</DROCSPool.\> di dominio \<dominio\>

  - SIP. \<dominio\>

  - AV.\<Domain\>

  - webconf. \<dominio\>

  - OCSServices. \<dominio\>

<div>


> [!IMPORTANT]  
> Per le procedure dettagliate per l'amministrazione e la gestione, vedere <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">backup e ripristino di Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[Cmdlet per backup e disponibilità elevata in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[Import-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Backup e ripristino di Lync Server 2013](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[Gestione di ripristino di emergenza, disponibilità elevata e servizio di backup di Lync Server 2013](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

