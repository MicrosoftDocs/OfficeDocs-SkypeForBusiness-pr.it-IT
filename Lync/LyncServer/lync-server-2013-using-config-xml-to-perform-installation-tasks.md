---
title: 'Lync Server 2013: uso di config. XML per eseguire attività di installazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Config.xml to perform installation tasks
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48183332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3fb6f4c77375781b6c5d767087ad61f3ec6401b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a>Uso di config. XML per eseguire attività di installazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-02_

Anche se lo strumento di personalizzazione di Office (OCT) è lo strumento principale per l'installazione di personalizzazione, gli amministratori possono usare il file config. XML per specificare altre istruzioni per l'installazione che non sono disponibili in ottobre. Le personalizzazioni seguenti possono essere eseguite solo usando il file config. XML:

  - Specificare il percorso del punto di installazione della rete.

  - Selezionare i prodotti da installare.

  - Configurare la registrazione e la posizione del file di personalizzazione della configurazione e degli aggiornamenti software.

  - Specificare le opzioni di installazione, ad esempio nome utente.

  - Copiare l'origine di installazione locale (LIS) nel computer dell'utente senza installare Office.

  - Aggiungere o rimuovere lingue dall'installazione.

È consigliabile usare il file config. XML per configurare l'installazione invisibile di Lync 2013.

Per impostazione predefinita, il file config. xml archiviato nella cartella principale del prodotto, ad esempio \\Product. WW) indirizza la configurazione per l'installazione di tale prodotto. Ad esempio, il file config. XML nella cartella seguente installa Lync 2013:

  - \\\\condivisione\\\\del server\\Lync15 Lync. \\WW config. XML

Gli elementi config. XML usati più comunemente per l'installazione di Lync 2013 sono elencati nella tabella seguente.

### <a name="configxml-elements"></a>Elementi config. XML

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Elemento</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configurazione</p></td>
<td><p>Elemento di primo livello (obbligatorio). Contiene l'attributo Product, ad esempio: Product = Lync</p></td>
</tr>
<tr class="even">
<td><p>OptionState</p></td>
<td><p>Specifica il modo in cui vengono gestite le caratteristiche specifiche del prodotto durante l'installazione. Usare gli attributi seguenti per impedire l'installazione di servizi di integrazione applicativa, che includono componenti condivisi che interferiscono con Outlook 2010:</p>
<ul>
<li><p>ID =&quot;LOBiMain&quot;</p></li>
<li><p>Stato =&quot;assente&quot;</p></li>
<li><p>Children =&quot;Force&quot;</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Visualizzare</p></td>
<td><p>Il livello di interfaccia utente visualizzato per l'installazione per l'utente. Gli attributi tipici includono i seguenti:</p>
<ul>
<li><p>CompletionNotice =&quot;Sì&quot; | &quot;No&quot;(impostazione predefinita)</p></li>
<li><p>AcceptEula =&quot;Sì&quot; | &quot;No&quot;(impostazione predefinita)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Registrazione</p></td>
<td><p>Opzioni per il tipo di registrazione eseguito dall'installazione. Gli attributi tipici includono i seguenti:</p>
<ul>
<li><p>Digitare =&quot;off&quot; | &quot;standard&quot;(impostazione predefinita) | &quot;Verbose&quot;</p></li>
<li><p>Template = "nomefile. txt" (il nome del file di log)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Impostazione</p></td>
<td><p>Specifica i valori per le proprietà di Windows Installer. Gli attributi tipici includono i seguenti:</p>
<ul>
<li><p>Impostazione di ID&quot;=&quot; Name (nome della proprietà di Windows Installer)</p></li>
<li><p>Valore =&quot;valore&quot; (il valore da assegnare alla proprietà)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>DistributionPoint</p></td>
<td><p>Percorso completo del punto di installazione di rete da cui eseguire l'installazione. Include l'attributo location:</p>
<ul>
<li><p>Location = "Path"</p></li>
</ul></td>
</tr>
</tbody>
</table>


L'esempio seguente mostra un file config. XML per una tipica installazione silenziosa di Lync 2013.

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

Informazioni dettagliate sull'uso del file config. XML per eseguire attività di installazione e manutenzione di Office sono <http://go.microsoft.com/fwlink/p/?linkid=267514>disponibili all'indirizzo.

<div>

## <a name="to-customize-the-configxml-file"></a>Per personalizzare il file config. XML

1.  Aprire il file config. XML usando uno strumento di editor di testo, ad esempio Blocco note.

2.  Individuare le righe che contengono gli elementi che si desidera modificare.

3.  Modificare la voce dell'elemento con le opzioni Silent che si desidera utilizzare. Assicurati di rimuovere i delimitatori di commento, "\<\!--" e "--\>". Ad esempio, usare la sintassi seguente:
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  Salvare il file config. XML.

</div>

</div>

<span> </span>

</div>

</div>

</div>

