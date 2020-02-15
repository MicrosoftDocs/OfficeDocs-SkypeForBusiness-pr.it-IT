---
title: 'Lync Server 2013: modificare le impostazioni per i file di registro di aggiornamento dei dispositivi'
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
ms.openlocfilehash: 770682cfed17d9b029688275469351c1cfdf9f4d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a>Modificare le impostazioni per i file di log degli aggiornamenti dei dispositivi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

È possibile modificare le impostazioni relative al modo in cui le informazioni sugli aggiornamenti dei dispositivi vengono registrate nell'organizzazione utilizzando il pannello di controllo di Lync Server o Lync Server Management Shell. Nella tabella seguente vengono illustrate le impostazioni modificabili e gli strumenti utilizzati per modificare le impostazioni.

Le impostazioni del registro possono essere modificate e applicate a livello globale o per sito.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Per modificare</th>
<th>Uso</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dimensione massima, espressa in byte, di un file di registro</p></td>
<td><p>Pannello di controllo di Lync Server</p>
<p>-oppure-</p>
<p>Lync Server Management Shell</p></td>
</tr>
<tr class="even">
<td><p>La quantità massima di informazioni (in byte) che possono essere conservate nella cache</p></td>
<td><p>Pannello di controllo di Lync Server</p>
<p>-oppure-</p>
<p>Lync Server Management Shell</p></td>
</tr>
<tr class="odd">
<td><p>Frequenza (in minuti) per la scrittura di informazioni memorizzate nella cache nel file di registro</p></td>
<td><p>Pannello di controllo di Lync Server</p>
<p>-oppure-</p>
<p>Lync Server Management Shell</p></td>
</tr>
<tr class="even">
<td><p>Durata (in giorni) per mantenere i file di registro</p></td>
<td><p>Pannello di controllo di Lync Server</p>
<p>-oppure-</p>
<p>Lync Server Management Shell</p></td>
</tr>
<tr class="odd">
<td><p>Quando (ora del giorno) per controllare i file scaduti che devono essere eliminati</p></td>
<td><p>Lync Server Management Shell</p></td>
</tr>
<tr class="even">
<td><p>Le estensioni di file di registro da consentire</p></td>
<td><p>Lync Server Management Shell</p></td>
</tr>
<tr class="odd">
<td><p>Quali tipi di file di registro mantenere</p></td>
<td><p>Lync Server Management Shell</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a>Per modificare le impostazioni di registrazione tramite il pannello di controllo di Lync Server

1.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **client**e quindi su **Configurazione log dispositivo**.

3.  Nella pagina **Configurazione log dispositivo** fare doppio clic sulla configurazione che si desidera modificare.

4.  Nella finestra di dialogo **Modifica impostazione log** modificare una delle impostazioni seguenti:
    
      - **Dimensioni massime file (byte)**   consente di specificare la dimensione massima che un file di registro può diventare prima che venga eliminato. Il valore predefinito è 1.024.000 byte (1 MB).
    
      - **Dimensioni massime cache (byte)**   consente di specificare la quantità massima di informazioni (in byte) che possono essere conservate nella cache dei file di registro prima che la cache debba essere deselezionata e che i dati vengano scritti in un file di registro. Il valore predefinito è 512.000 byte (0,5 MB).
    
      - **Il numero di minuti in cui svuotare la cache (1-60)**   indica la frequenza con cui le informazioni archiviate nella cache dei file di registro vengono scritte nel file di registro effettivo. Dopo la registrazione dei dati, la cache viene svuotata. Il valore predefinito è 5 minuti.
    
      - **Numero di giorni di conservazione dei file di registro (1-365)**   specifica il numero di giorni in cui i file di registro vengono mantenuti prima che vengano eliminati. Il valore predefinito è 10 giorni.

5.  Fare clic su **Commit**.

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a>Modifica delle impostazioni di registrazione tramite i cmdlet di Windows PowerShell

È possibile modificare le impostazioni dei file di registro di aggiornamento del dispositivo utilizzando Windows PowerShell e il cmdlet **Set-CsDeviceUpdateConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 using Remote PowerShell" at.



</div>

Negli esempi riportati di seguito vengono illustrati alcuni dei modi in cui è possibile utilizzare **Set-CsDeviceUpdateConfiguration** per modificare le impostazioni.

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a>Per modificare la dimensione massima del file di registro e l'intervallo di pulizia dei registri

  - Il comando seguente consente di modificare le impostazioni del registro degli aggiornamenti dei dispositivi applicati al sito Redmond. In questo esempio, la dimensione massima del file di registro è impostata su 204800 byte e l'intervallo di pulizia dei registri è impostato su 14 giorni.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a>Per modificare l'ora del giorno per la pulizia dei log

  - Questo comando consente di impostare il tempo di pulizia dei registri per il sito Redmond su 3:00 AM.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

