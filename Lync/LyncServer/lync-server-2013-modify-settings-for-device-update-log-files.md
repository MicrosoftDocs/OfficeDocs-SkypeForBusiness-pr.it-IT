---
title: 'Lync Server 2013: modificare le impostazioni per i file di log di aggiornamento dei dispositivi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88d75086f0532205c2897f7e86d49f50072aaa89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a>Modificare le impostazioni per i file di log di aggiornamento dei dispositivi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

È possibile modificare le impostazioni per il modo in cui le informazioni sull'aggiornamento dei dispositivi vengono registrate nell'organizzazione tramite il pannello di controllo di Lync Server o Lync Server Management Shell. La tabella seguente mostra le impostazioni modificabili e gli strumenti usati per modificare le impostazioni.

Le impostazioni del log possono essere modificate e applicate a livello globale o per sito.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Per modificare</th>
<th>Utilizzo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dimensione massima (in byte) per un file di log</p></td>
<td><p>Pannello di controllo di Lync Server</p>
<p>o</p>
<p>Lync Server Management Shell</p></td>
</tr>
<tr class="even">
<td><p>La quantità massima di informazioni (in byte) che possono essere conservate nella cache</p></td>
<td><p>Pannello di controllo di Lync Server</p>
<p>o</p>
<p>Lync Server Management Shell</p></td>
</tr>
<tr class="odd">
<td><p>Frequenza (in minuti) per la scrittura di informazioni memorizzate nella cache nel file di log</p></td>
<td><p>Pannello di controllo di Lync Server</p>
<p>o</p>
<p>Lync Server Management Shell</p></td>
</tr>
<tr class="even">
<td><p>Durata (in giorni) per conservare i file di log</p></td>
<td><p>Pannello di controllo di Lync Server</p>
<p>o</p>
<p>Lync Server Management Shell</p></td>
</tr>
<tr class="odd">
<td><p>Quando (ora del giorno) per controllare i file scaduti che devono essere eliminati</p></td>
<td><p>Lync Server Management Shell</p></td>
</tr>
<tr class="even">
<td><p>Quali estensioni di file di log consentire</p></td>
<td><p>Lync Server Management Shell</p></td>
</tr>
<tr class="odd">
<td><p>Quali tipi di file di log mantenere</p></td>
<td><p>Lync Server Management Shell</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a>Per modificare le impostazioni di registrazione tramite il pannello di controllo di Lync Server

1.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **client**e quindi su **Configurazione log dei dispositivi**.

3.  Nella pagina **Configurazione log dispositivo** fare doppio clic sulla configurazione che si vuole modificare.

4.  Nella finestra di dialogo **Modifica impostazioni log** modificare una delle impostazioni seguenti:
    
      - **Dimensioni massime dei file (byte)**   specifica la dimensione massima che un file di log può diventare prima che venga eliminato. Il valore predefinito è 1.024.000 byte (1 MB).
    
      - **Le dimensioni massime della cache (byte)**   specificano la quantità massima di informazioni (in byte) che possono essere conservate nella cache dei file di log prima che la cache debba essere deselezionata e i dati vengono scritti in un file di log. Il valore predefinito è 512.000 byte (0,5 MB).
    
      - **Numero di minuti per svuotare la cache (1-60)**   indica la frequenza con cui le informazioni memorizzate nella cache dei file di log vengono scritte nel file di log effettivo. Dopo aver registrato i dati, la cache viene deselezionata. Il valore predefinito è cinque minuti.
    
      - **Numero di giorni per mantenere i file di log (1-365)**   specifica il numero di giorni in cui i file di log vengono mantenuti prima che vengano eliminati. Il valore predefinito è 10 giorni.

5.  Fare clic su **Commit**.

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a>Modifica delle impostazioni di registrazione con i cmdlet di Windows PowerShell

Le impostazioni del file di log degli aggiornamenti dei dispositivi possono essere modificate tramite Windows PowerShell e il cmdlet **Set-CsDeviceUpdateConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Lync Server 2010 con Remote PowerShell" at.



</div>

Gli esempi seguenti illustrano alcuni modi in cui è possibile usare **Set-CsDeviceUpdateConfiguration** per modificare le impostazioni.

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a>Per modificare le dimensioni massime del file di log e l'intervallo di pulizia del log

  - Il comando seguente modifica le impostazioni del log di aggiornamento del dispositivo applicate al sito Redmond. In questo esempio, la dimensione massima del file di log è impostata su 204800 byte e l'intervallo di pulitura del log è impostato su 14 giorni.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a>Per modificare l'ora di pulizia del log del giorno

  - Questo comando imposta l'ora di pulizia del log per il sito Redmond su 3:00 AM.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

Per informazioni dettagliate, vedere l'argomento della Guida relativo al cmdlet [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

