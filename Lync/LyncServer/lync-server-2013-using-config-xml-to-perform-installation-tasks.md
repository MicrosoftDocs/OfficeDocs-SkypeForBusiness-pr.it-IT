---
title: 'Lync Server 2013: utilizzo del file config. XML per eseguire le attività di installazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Config.xml to perform installation tasks
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48183332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2933da3fc52cc6a5c23f74806ff3a4e81dcb2ba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a>Utilizzo di config. XML per eseguire le attività di installazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-02_

Anche se lo strumento di personalizzazione di Office è lo strumento principale per l'installazione della personalizzazione, gli amministratori possono utilizzare il file config. XML per specificare ulteriori istruzioni di installazione che non sono disponibili nel set di strumenti. È possibile eseguire le personalizzazioni seguenti solo mediante il file Config.xml:

  - Specificare il percorso del punto di installazione di rete.

  - Selezionare i prodotti da installare.

  - Configurare la registrazione e il percorso del file di personalizzazione dell'installazione e degli aggiornamenti software.

  - Specificare le opzioni di installazione, ad esempio il nome utente.

  - Copiare l'origine di installazione locale nel computer dell'utente senza installare Office.

  - Aggiungere o rimuovere lingue dall'installazione.

È consigliabile utilizzare il file config. XML per configurare l'installazione invisibile all'utente di Lync 2013.

Per impostazione predefinita, il file config. XML memorizzato nella cartella di base del prodotto, \\ad esempio Product. WW) indirizza il programma di installazione per l'installazione del prodotto. Ad esempio, il file config. XML nella cartella seguente consente di installare Lync 2013:

  - \\\\condivisione\\\\server Lync15\\Lync. WW \\config. XML

Nella tabella seguente sono elencati gli elementi config. XML più comunemente utilizzati per l'installazione di Lync 2013.

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
<td><p>Specifica come vengono gestite caratteristiche specifiche del prodotto durante l'installazione. Utilizzare gli attributi seguenti per impedire l'installazione di servizi di integrazione applicativa, che include componenti condivisi che interferiscono con Outlook 2010:</p>
<ul>
<li><p>ID =&quot;LOBiMain&quot;</p></li>
<li><p>Stato =&quot;assente&quot;</p></li>
<li><p>Children =&quot;Force&quot;</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Schermo</p></td>
<td><p>Livello di interfaccia utente visualizzato all'utente dal programma di installazione. Tra gli attributi tipici sono inclusi i seguenti:</p>
<ul>
<li><p>CompletionNotice =&quot;Yes&quot; | &quot;No&quot;(impostazione predefinita)</p></li>
<li><p>AcceptEula =&quot;Yes&quot; | &quot;No&quot;(impostazione predefinita)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Registrazione</p></td>
<td><p>Opzioni per il tipo di registrazione eseguita dal programma di installazione. Tra gli attributi tipici sono inclusi i seguenti:</p>
<ul>
<li><p>Type =&quot;off&quot; | &quot;standard&quot;(impostazione predefinita) | &quot;Verbose&quot;</p></li>
<li><p>Template = "nomefile. txt" (il nome del file di registro)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Impostazione</p></td>
<td><p>Specifica i valori per le proprietà di Windows Installer. Tra gli attributi tipici sono inclusi i seguenti:</p>
<ul>
<li><p>Impostazione ID =&quot;Name&quot; (il nome della proprietà di Windows Installer)</p></li>
<li><p>Valore =&quot;valore&quot; (valore da assegnare alla proprietà)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>DistributionPoint</p></td>
<td><p>Percorso completo del punto di installazione di rete da cui deve essere eseguita l'installazione Include l'attributo location:</p>
<ul>
<li><p>Location = "percorso"</p></li>
</ul></td>
</tr>
</tbody>
</table>


Nell'esempio seguente viene illustrato un file config. XML per una tipica installazione invisibile all'utente di Lync 2013.

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

Informazioni dettagliate sull'utilizzo del file config. XML per eseguire le attività di installazione e manutenzione di Office <https://go.microsoft.com/fwlink/p/?linkid=267514>sono disponibili all'indirizzo.

<div>

## <a name="to-customize-the-configxml-file"></a>Per personalizzare il file config. XML

1.  Aprire il file config. XML utilizzando uno strumento di editor di testo, ad esempio il blocco note.

2.  Individuare le righe che contengono gli elementi che si desidera modificare.

3.  Modificare la voce dell'elemento con le opzioni Silent che si desidera utilizzare. Assicurarsi di rimuovere i delimitatori dei commenti, "\<\!--" e "--\>". Utilizzare ad esempio la sintassi seguente:
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  Salvare il file Config.xml.

</div>

</div>

<span> </span>

</div>

</div>

</div>

