---
title: 'Lync Server 2013: utilizzo delle opzioni della riga di comando del programma di installazione'
description: 'Lync Server 2013: utilizzo delle opzioni della riga di comando del programma di installazione.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15c3490ead090766462ce83cb13ffe62355032cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580242"
---
# <a name="using-setup-command-line-options-in-lync-server-2013"></a>Utilizzo delle opzioni della riga di comando del programma di installazione in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-03_

La riga di comando di Setup.exe consente di eseguire un numero limitato di operazioni di configurazione di Office. Invece di usare le opzioni della riga di comando di Setup, in genere si usa lo Strumento di personalizzazione di Office e il file the Config.xml per la personalizzazione delle caratteristiche e della configurazione del prodotto.

La riga di comando di Setup.exe di Office riconosce le opzioni descritte nella tabella seguente.

### <a name="office-setup-command-line-options"></a>Opzioni della riga di comando del programma di installazione di Office

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Opzione della riga di comando</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/admin</p></td>
<td><p>Esegue lo Strumento di personalizzazione di Office per creare un file di personalizzazione della configurazione (file con estensione msp).</p></td>
</tr>
<tr class="even">
<td><p>/adminfile [percorso]</p></td>
<td><p>Applica all'installazione il file di personalizzazione dell'installazione specificato. È possibile specificare il percorso di un determinato file di personalizzazione dell'installazione (msp) o della cartella in cui sono archiviati i file di personalizzazione.</p></td>
</tr>
<tr class="odd">
<td><p>/config [percorso]</p></td>
<td><p>Specifica il file Config.xml utilizzato durante l'installazione. Utilizzare l'opzione/config per specificare il file Config.xml personalizzato per le installazioni di Lync 2013, ad esempio: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></p></td>
</tr>
<tr class="even">
<td><p>/modify Lync</p></td>
<td><p>Usato con un file Config.xml modificato per eseguire il programma di installazione in modalità manutenzione e apportare modifiche a un'installazione di Office esistente. È ad esempio possibile usare l'opzione /modify per aggiungere o rimuovere caratteristiche di Lync.</p></td>
</tr>
<tr class="odd">
<td><p>/repair Lync</p></td>
<td><p>Esegue il programma di installazione nel computer dell'utente per ripristinare Lync.</p></td>
</tr>
<tr class="even">
<td><p>/uninstall Lync</p></td>
<td><p>Esegue il programma di installazione per rimuovere Lync dal computer dell'utente.</p></td>
</tr>
</tbody>
</table>


Per informazioni dettagliate sull'utilizzo delle opzioni della riga di comando del programma di installazione, vedere <https://go.microsoft.com/fwlink/p/?linkid=267515> .

</div>

<span> </span>

</div>

</div>

</div>

