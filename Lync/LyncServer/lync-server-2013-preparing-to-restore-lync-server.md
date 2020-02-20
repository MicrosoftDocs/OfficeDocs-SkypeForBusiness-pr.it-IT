---
title: 'Lync Server 2013: preparazione per il ripristino di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b397f389de461a04974fe063437caaabd9d4137
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a>Preparazione per il ripristino di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Prima di iniziare a ripristinare server e database dopo un errore, è necessario determinare gli aspetti seguenti:

  - Che cosa deve essere ripristinato.

  - L'hardware, il software, i dati e gli strumenti necessari per il ripristino.

<div>

## <a name="determining-what-to-restore"></a>Determinazione dei componenti da ripristinare

In questo argomento viene descritto come ripristinare le interruzioni di Lync Server che si verificano a livello del server, del pool o dell'archivio di gestione centrale. Se l'archivio di gestione centrale ha esito negativo, la distribuzione di Lync Server continua a funzionare, ma non è possibile apportare modifiche alla configurazione. In caso di errore di un server back-end o Standard Edition, il pool di utenti smette di funzionare. In caso di errore di qualsiasi altro server, la gravità dell'errore dipende dal ruolo del server e dal fatto che il server ospiti uno o più database.

### <a name="what-to-restore"></a>Componenti da ripristinare

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>In caso di errore di</th>
<th>Vedere questa sezione:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Server Standard Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">Ripristino di un server Standard Edition in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Archivio di gestione centrale</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Ripristino del server che ospita l'archivio di gestione centrale in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Back-end Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Ripristino di un server back-end Enterprise Edition in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Server primario di back-end con mirroring Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Ripristino di un server back-end Enterprise Edition con mirroring in Lync Server 2013-Primary</a></p></td>
</tr>
<tr class="odd">
<td><p>Server secondario di back-end con mirroring Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Ripristino di un server back-end Enterprise Edition con mirroring in Lync Server 2013-mirror</a></p></td>
</tr>
<tr class="even">
<td><p>Qualsiasi server Enterprise Edition che esegue un ruolo del server, ad esempio front end server, server perimetrale, Director, Mediation Server o Persistent Chat Server.</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Ripristino di un server membro Enterprise Edition in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Un intero pool di Lync Server</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">Ripristino di un pool di Lync Server in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Archivio file Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">Ripristino di un archivio file in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Un database di monitoraggio autonomo o un database di archiviazione</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Ripristino dei dati di monitoraggio o archiviazione in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Un database di chat persistente autonomo</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">Ripristino dei dati di chat persistente in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a>Raccolta di hardware, software e strumenti

Quando si ripristina un server, è necessario iniziare con un computer nuovo o pulito. È inoltre necessario che siano disponibili i seguenti componenti hardware e software:

  - Un server nuovo o pulito con lo stesso nome di dominio completo (FQDN) del server in cui si è verificato l'errore.
    
    <div>
    

    > [!IMPORTANT]  
    > Quando si installa il sistema operativo, assicurarsi che l'account del computer non venga eliminato in servizi di dominio Active Directory e verificare che le autorizzazioni di gruppo per l'account vengano conservate.

    
    </div>

  - Software di installazione per il sistema operativo. Per installare il sistema operativo, è possibile utilizzare le procedure di distribuzione del server e le configurazioni stabilite dall'organizzazione. Quando si ripristina il servizio, è necessario che queste procedure e i requisiti di configurazione siano disponibili.

  - Software di installazione per SQL Server 2012 o SQL Server 2008 R2. Per installare un server di database, utilizzare la versione appropriata di SQL Server, nonché le configurazioni e le procedure di distribuzione del server di database stabilite dall'organizzazione. Quando si ripristina il servizio, è necessario che queste procedure e i requisiti di configurazione siano disponibili.
    
    <div>
    

    > [!NOTE]  
    > La distribuzione guidata di Lync Server installa automaticamente SQL Server 2012 Express in ogni server Standard Edition e in qualsiasi altro server Lync Server quando è installato un archivio di configurazione locale, a meno che non sia stato preinstallato SQL Server 2012 o SQL Server 2008 R2 su il server.

    
    </div>

  - Software per l'acquisizione di immagini di sistema.
    
    <div>
    

    > [!TIP]  
    > È consigliabile acquisire una copia di immagine del sistema dopo l'installazione del sistema operativo e di SQL Server e prima di iniziare il ripristino, in modo che sia possibile utilizzare questa immagine come punto di rollback in caso di problemi durante il ripristino.

    
    </div>

  - Software di installazione di Lync Server 2013. La distribuzione guidata di Lync Server si trova nella cartella o nel supporto di installazione di \\Lync\\server\\in Setup amd64 Setup. exe.

Durante il ripristino, vengono utilizzati gli strumenti seguenti:

  - Cmdlet di Lync Server Management Shell

  - Import-CsUserData

  - Strumenti per il ripristino delle cartelle di Windows

  - Strumento di generazione topologia

  - Utilità di database di SQL Server, ad esempio SQL Server Management Studio

</div>

<div>

## <a name="preparing-to-restore-a-server"></a>Preparazione al ripristino di un server

Prima di ripristinare il server, è necessario eseguire le operazioni seguenti:

1.  Installare il sistema operativo.

2.  Se il server è un server di back-end, installare SQL Server 2012 o SQL Server 2008 R2.

3.  Ripristinare o registrare nuovamente i certificati. Per informazioni dettagliate sui certificati, vedere "requisiti di backup aggiuntivi" in [requisiti di backup e ripristino in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).

4.  Acquisire un'immagine del sistema prima di iniziare il ripristino da utilizzare come punto di rollback, in caso di problemi durante il ripristino.

<div>


> [!NOTE]  
> La distribuzione guidata di Lync Server e i cmdlet descritti nelle procedure illustrate in questo argomento e gli argomenti correlati, impostare tutti gli elenchi di controllo di accesso (ACL) necessari.



</div>

Verificare che l'hardware e il software necessari per i componenti che si intende ripristinare siano disponibili prima di iniziare il ripristino. Dopo aver installato il sistema operativo e SQL Server, la maggior parte delle operazioni delle procedure di ripristino seguenti può essere eseguita in modalità remota. Le eccezioni sono segnalate nelle procedure.

È inoltre necessario disporre del piano di backup e ripristino dell'organizzazione e delle informazioni dell'ultimo backup, ad esempio le informazioni contenute nei fogli di lavoro di questo documento (per informazioni dettagliate, vedere [backup and Restoration Worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), disponibile prima di iniziare il ripristino.

</div>

</div>

<span> </span>

</div>

</div>

</div>

