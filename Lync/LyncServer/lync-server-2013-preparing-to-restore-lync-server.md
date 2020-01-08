---
title: 'Lync Server 2013: preparazione per il ripristino di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a470a338d05436be942201e6df6a864f955ac87c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a>Preparazione per il ripristino di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Prima di iniziare il ripristino di server e database dopo un errore, è necessario determinare quanto segue:

  - Ciò che deve essere ripristinato.

  - Hardware, software, dati e strumenti necessari per il ripristino.

<div>

## <a name="determining-what-to-restore"></a>Determinazione del ripristino

Questo argomento descrive come ripristinare il livello di interruzioni del server Lync che si verificano nel server, nel pool o nell'Central Management store. Se l'archivio di gestione centrale non riesce, la distribuzione di Lync Server continuerà a funzionare, ma non è possibile apportare modifiche alla configurazione. Se un server back-end o un server Standard Edition non riesce, il pool di utenti smette di funzionare. Se un altro server non riesce, la grandezza dell'errore dipende dal ruolo del server in cui è in corso il server e se il server ospita uno o più database.

### <a name="what-to-restore"></a>Cosa ripristinare

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Se non è riuscito</th>
<th>Vedere questa sezione:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Server Standard Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">Ripristino di un server Standard Edition in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Central Management store</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Ripristino del server che ospita l'archivio di gestione centrale in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Back-end Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Ripristino di un server back-end Enterprise Edition in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Server primario di back-end con mirroring Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Ripristino di un server back-end Enterprise Edition con mirroring in Lync Server 2013-primario</a></p></td>
</tr>
<tr class="odd">
<td><p>Server secondario di back-end Enterprise Edition con mirroring</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Ripristino di un server back-end Enterprise Edition con mirroring in Lync Server 2013-mirror</a></p></td>
</tr>
<tr class="even">
<td><p>Qualsiasi server aziendale che gestisce un ruolo del server, ad esempio un server front-end, un server perimetrale, un Director, un Mediation Server o un server di chat persistente.</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Ripristino di un server membro di Enterprise Edition in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Intero pool di Lync Server</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">Ripristino di un pool di Lync Server in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Archivio file di Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">Ripristino di un archivio di file in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Un database di monitoraggio autonomo o un database di archiviazione</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Ripristinare il monitoraggio o l'archiviazione dei dati in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Un database di chat persistente autonomo</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">Ripristino dei dati della chat persistente in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a>Raccolta di hardware, software e strumenti

Quando si ripristina un server, è necessario iniziare con un computer nuovo o pulito. Inoltre, è necessario che siano disponibili i seguenti componenti hardware e software:

  - Un server pulito o nuovo con lo stesso nome di dominio completo (FQDN) del server che ha fallito.
    
    <div>
    

    > [!IMPORTANT]  
    > Quando si installa il sistema operativo, assicurarsi di non eliminare l'account del computer in servizi di dominio Active Directory e verificare che le autorizzazioni di gruppo per l'account vengano mantenute.

    
    </div>

  - Software di installazione per il sistema operativo. Per installare il sistema operativo, usare le procedure e le configurazioni di distribuzione del server stabilite dall'organizzazione. Quando si ripristina il servizio, è necessario che siano disponibili le procedure e i requisiti di configurazione.

  - Software di installazione per SQL Server 2012 o SQL Server 2008 R2. Per installare un server di database, usare la versione appropriata di SQL Server e le procedure e le configurazioni di distribuzione del server di database stabilite dall'organizzazione. Quando si ripristina il servizio, è necessario che siano disponibili le procedure e i requisiti di configurazione.
    
    <div>
    

    > [!NOTE]  
    > La distribuzione guidata di Lync Server installa automaticamente SQL Server 2012 Express in ogni server Standard Edition e in qualsiasi altro server Lync Server in cui è installato un archivio di configurazione locale, a meno che non sia stato preinstallato SQL Server 2012 o SQL Server 2008 R2 in il server.

    
    </div>

  - Software per l'acquisizione di immagini di sistema.
    
    <div>
    

    > [!TIP]  
    > È consigliabile prendere una copia di immagine del sistema dopo l'installazione del sistema operativo e di SQL Server e prima di iniziare il ripristino, in modo che sia possibile usare questa immagine come punto di rollback nel caso in cui qualcosa vada storto durante il ripristino.

    
    </div>

  - Software di installazione di Lync Server 2013. La distribuzione guidata di Lync Server si trova nella cartella di installazione o nel supporto di \\Lync\\server\\in Setup amd64 Setup. exe.

Durante il ripristino si usano gli strumenti seguenti:

  - Cmdlet di Lync Server Management Shell

  - Import-CsUserData

  - Strumenti per il ripristino delle cartelle di Windows

  - Generatore di topologie

  - Utilità per database di SQL Server, ad esempio SQL Server Management Studio

</div>

<div>

## <a name="preparing-to-restore-a-server"></a>Preparazione del ripristino di un server

Prima di ripristinare il server, è necessario eseguire la procedura seguente:

1.  Installare il sistema operativo.

2.  Se il server è un server di back-end, installare SQL Server 2012 o SQL Server 2008 R2.

3.  Ripristinare o registrare nuovamente i certificati. Per informazioni dettagliate sui certificati, vedere "requisiti di backup aggiuntivi" nei [requisiti di backup e ripristino in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).

4.  Scattare un'immagine del sistema prima di avviare il ripristino da usare come punto di rollback, in caso di problemi durante il ripristino.

<div>


> [!NOTE]  
> La distribuzione guidata di Lync Server e i cmdlet descritti nelle procedure descritte in questo argomento e gli argomenti correlati impostano tutti gli elenchi di controllo di accesso (ACL) necessari.



</div>

Verificare che l'hardware e il software necessari per i componenti che si prevede di ripristinare siano disponibili prima di avviare il ripristino. Dopo aver installato il sistema operativo e SQL Server, è possibile eseguire la maggior parte dei passaggi delle procedure di ripristino seguenti in remoto. Le eccezioni sono note nelle procedure.

Si dovrebbe anche avere il piano di backup e ripristino dell'organizzazione e le informazioni dell'ultimo backup, ad esempio le informazioni contenute nei fogli di lavoro di questo documento (per informazioni dettagliate, vedere [fogli di lavoro di backup e ripristino per Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), disponibile prima di iniziare il ripristino.

</div>

</div>

<span> </span>

</div>

</div>

</div>

