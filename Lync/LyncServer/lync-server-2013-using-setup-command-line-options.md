---
title: 'Lync Server 2013: uso delle opzioni della riga di comando del programma di installazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5087c8ac777e5e2fd3259f925a4217a4d47dd800
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-setup-command-line-options-in-lync-server-2013"></a>Uso delle opzioni della riga di comando di configurazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-03_

La riga di comando Setup. exe viene usata per pochissime operazioni in configurazione di Office. Invece di usare le opzioni della riga di comando per la configurazione, in genere si usa lo strumento di personalizzazione di Office e il file config. XML per la configurazione del prodotto e la personalizzazione delle funzionalità.

La riga di comando di Office Setup. exe riconosce le opzioni della riga di comando descritte nella tabella seguente.

### <a name="office-setup-command-line-options"></a>Opzioni della riga di comando per l'installazione di Office

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Opzione della riga di comando Setup</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/admin</p></td>
<td><p>Esegue lo strumento di personalizzazione di Office per creare un file di personalizzazione della configurazione (file msp).</p></td>
</tr>
<tr class="even">
<td><p>/adminfile [percorso]</p></td>
<td><p>Applica il file di personalizzazione della configurazione specificato all'installazione. È possibile specificare un percorso di un file di personalizzazione specifico (file msp) o nella cartella in cui vengono archiviati i file di personalizzazione.</p></td>
</tr>
<tr class="odd">
<td><p>/config [percorso]</p></td>
<td><p>Specifica il file config. XML usato dalla configurazione durante l'installazione. Usare l'opzione/config per specificare il file config. XML personalizzato per le installazioni di Lync 2013, ad esempio:<code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></p></td>
</tr>
<tr class="even">
<td><p>/Modify Lync</p></td>
<td><p>Usato con un file config. xml modificato per eseguire la configurazione in modalità manutenzione e apportare modifiche a un'installazione di Office esistente. Ad esempio, puoi usare l'opzione/MODIFY per aggiungere o rimuovere le caratteristiche di Lync.</p></td>
</tr>
<tr class="odd">
<td><p>/Repair Lync</p></td>
<td><p>Esegue la configurazione dal computer dell'utente per ripristinare Lync.</p></td>
</tr>
<tr class="even">
<td><p>/Uninstall Lync</p></td>
<td><p>Esegue il programma di installazione per rimuovere Lync dal computer dell'utente.</p></td>
</tr>
</tbody>
</table>


Per informazioni dettagliate sull'uso delle opzioni della riga di comando per <http://go.microsoft.com/fwlink/p/?linkid=267515>la configurazione, vedere.

</div>

<span> </span>

</div>

</div>

</div>

