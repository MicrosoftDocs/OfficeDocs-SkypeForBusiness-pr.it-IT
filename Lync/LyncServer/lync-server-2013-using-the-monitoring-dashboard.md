---
title: 'Lync Server 2013: utilizzo del dashboard di monitoraggio'
description: 'Lync Server 2013: utilizzo del dashboard di monitoraggio.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8a68fa1e55b7d0b8305c53802ddabaa904fa214
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556042"
---
# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a>Utilizzo del dashboard di monitoraggio in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-05_

Il dashboard di monitoraggio fornisce agli amministratori una breve panoramica dell'integrità del sistema e dell'utilizzo del sistema di Microsoft Lync Server 2013. Il dashboard è stato creato per mostrare una visualizzazione aggregata delle metriche dei sistemi chiave e per farlo visualizzando:

  - Totali per il giorno corrente. Si noti che i valori visualizzati per il giorno corrente rappresentano i dati che sono stati registrati dalla mezzanotte fino all'ora corrente (in base all'ora locale del server di report). Questo significa che in genere i dati vengono visualizzati per un giorno parziale e non per un periodo di 24 ore. Ad esempio, se l'ora locale del server è 8:00, è possibile visualizzare un valore di otto ore perché sono presenti otto ore tra la mezzanotte e la data corrente di 8:00.

  - Totali per la settimana e totali di tendenza per le ultime sei settimane.

  - Totali per il mese e totali di tendenza negli ultimi sei mesi (solo per l'utilizzo del sistema).

Si noti che è possibile utilizzare il cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) per restituire l'URL utilizzato per l'accesso ai report di monitoraggio di Lync Server 2013:

    Get-CsReportingConfiguration

Per impostazione predefinita, il dashboard di monitoraggio Visualizza i dati per le metriche seguenti per la settimana corrente (e i totali di tendenza per le sei settimane precedenti):

<div>

## <a name="system-usage-metrics"></a>Metriche di utilizzo del sistema

**Registrazione**

  - Accessi utente univoci

**Peer-to-peer**

  - Totale sessioni

  - Sessioni di messaggistica istantanea

  - Sessioni audio

  - Sessioni video

  - Condivisione applicazioni

  - Totale minuti di sessioni audio

  - Minuti di sessione media. audio

**Conferenza**

  - Totale conferenze

  - Conferenze di messaggistica istantanea

  - Conferenze A/V

  - Conferenze di condivisione applicazioni

  - Conferenze Web

  - Totale organizzatori

  - Totale minuti di conferenza audio/video

  - AVG. Minuti di conferenza A/V

  - Totale conferenze PSTN

  - Totale partecipanti PSTN

  - Totale minuti partecipante PSTN

Oltre alle metriche di utilizzo del sistema, le metriche seguenti visualizzano il totale per il giorno corrente e i sei giorni precedenti (se si seleziona **visualizzazione settimanale**) o per la settimana corrente e le sei settimane precedenti se si seleziona **visualizzazione mensile**.

</div>

<div>

## <a name="per-user-call-diagnostics"></a>Diagnostica Per-User chiamata

**Utenti con errori di chiamata**

  - Totale utenti con errori di chiamata

  - Organizzatori della conferenza con errori di chiamata

**Utenti con chiamate di qualità scadente**

  - Totale utenti con chiamate di qualità scadente

</div>

<div>

## <a name="call-diagnostics"></a>Diagnostica chiamate

Peer-to-peer

  - Totale errori

  - Frequenza di errore complessiva

  - Frequenza errori di messaggistica istantanea

  - Frequenza errori audio

  - Frequenza errori di condivisione applicazioni

Conferenza

  - Totale errori

  - Frequenza di errore complessiva

  - Frequenza errori di messaggistica istantanea

  - Frequenza errori di A/V

  - Frequenza errori di condivisione applicazioni

Primi cinque server da sessioni non riuscite

</div>

<div>

## <a name="media-quality-diagnostics"></a>Diagnostica qualità multimediale

Peer-to-peer

  - Chiamate totali di qualità scadente

  - Percentuale di chiamata di qualità scadente

  - Chiamate PSTN con qualità scadente

Conferenza

  - Chiamate totali di qualità scadente

  - Percentuale di chiamata di qualità scadente

  - Chiamate PSTN con qualità scadente

Top Worst Servers dalla percentuale di chiamata di qualità scadente

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a>Utilizzo del dashboard di monitoraggio

Come indicato, per i totali predefiniti vengono visualizzati per la settimana corrente e i valori di tendenza vengono visualizzati per le ultime sei settimane. Se si preferisce visualizzare i totali per il mese corrente (così come i valori di tendenza negli ultimi sei mesi), fare clic sul collegamento **Visualizza mensilmente** nell'angolo in alto a destra del dashboard. Se si decide di visualizzare i totali mensili, il testo del collegamento verrà modificato in **visualizzazione settimanale**. È possibile tornare alla visualizzazione settimanale facendo clic su quel collegamento.

<div>


> [!TIP]  
> Il dashboard di monitoraggio consente di limitare l'esame dei totali per la settimana (o il mese) corrente e i valori di tendenza per le ultime sei settimane (o mesi). Non è possibile modificare queste date e ore. Ad esempio, non è possibile utilizzare il dashboard per visualizzare i totali dei rapporti per il periodo di tempo che inizia nove mesi fa.



</div>

I valori visualizzati nelle colonne **this week**, **this month**o **Today** sono collegati a informazioni più dettagliate sull'elemento. Tenere presente che il nome della colonna e i valori visualizzati in tale colonna spesso differiscono a seconda della metrica scelta e a seconda che sia stata selezionata la visualizzazione settimanale o la visualizzazione mensile. Ad esempio, se si fa clic sui totali visualizzati per la metrica degli **accessi univoci** per l'utente, verrà visualizzato il **rapporto di registrazione degli utenti** per il periodo di tempo specificato. È possibile tornare al dashboard di monitoraggio in qualsiasi momento facendo clic su **Dashboard**.

<div>


> [!TIP]  
> È inoltre possibile accedere alla Home page dei report di Monitoring Server facendo clic sul collegamento <STRONG>report</STRONG> nell'angolo in alto a destra del dashboard.



</div>

La colonna **trend** Visualizza un grafico a linee semplice che mostra i totali per le ultime sei settimane (o, a seconda della metrica e dell'intervallo di tempo, negli ultimi sei giorni o negli ultimi sei mesi). Questi grafici a linee semplici visualizzano un punto dati senza etichetta per ogni periodo di tempo, ad esempio un punto dati senza etichetta per ognuna delle ultime sei settimane. Tuttavia, è possibile recuperare i valori effettivi per questi grafici tenendo il puntatore del mouse sul grafico. In questo caso, una descrizione comando Visualizza i valori massimi e minimi del grafico.

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a>Esportazione di dati dal dashboard di monitoraggio

Nel dashboard di monitoraggio sono disponibili diversi modi per esportare la visualizzazione dashboard corrente. Sulla barra degli strumenti del dashboard verrà visualizzata un'icona che assomiglia a un disco floppy con una freccia verde associata. Se si fa clic su questa icona, verrà visualizzato un elenco a discesa che fornisce i seguenti formati di esportazione dei dati:

  - File XML con dati del rapporto

  - CSV (delimitato da virgole)

  - PDF

  - MHTML (archivio Web)

  - Excel

  - File TIFF

  - Word

Per esportare la visualizzazione del dashboard corrente e i relativi valori, fare clic sull'opzione di esportazione desiderata. Lync Server 2013 genera un report nel formato specificato e quindi fornisce la possibilità di aprire il report o di salvarlo. Si noti che, per impostazione predefinita, Lync Server titola il **dashboard di monitoraggio** dei report e lo salva nella cartella Downloads. Per assegnare un nome diverso al report o archiviarlo in una cartella diversa, fare clic sulla freccia accanto al pulsante **Salva** e quindi fare clic su **Salva come**. Se si sta bene con il nome del **dashboard di monitoraggio** e con il report salvato nella cartella Downloads, è possibile fare clic sul pulsante **Salva** .

È possibile che, quando si tenta di esportare i dati del dashboard, venga visualizzata una finestra di dialogo per l' **avviso di sicurezza** insieme al messaggio "le impostazioni correnti non consentono il download di questo file". Se ciò accade, eseguire le operazioni seguenti:

  - In Internet Explorer selezionare **Opzioni Internet**.

  - Nella scheda **sicurezza** della finestra di dialogo **Opzioni Internet** fare clic su **siti attendibili** e quindi su **siti**.

  - Nella finestra di dialogo **siti attendibili** fare clic su **Aggiungi** per aggiungere il Lync Server 2013 che esegue i report di Lync Server 2013 agli insiemi di siti Web attendibili.

  - Fare clic su **Chiudi** e quindi su **OK**.

Sarà quindi necessario aggiornare il dashboard di monitoraggio prima che le modifiche abbiano effetto. A tale scopo, premere F5 o fare clic sull'icona di **aggiornamento** sulla barra degli strumenti del dashboard. (L'icona di **aggiornamento** è un cerchio con una coppia di frecce verdi all'interno).

È inoltre possibile creare un foglio di calcolo di Excel che include feed di dati in tempo reale, che include collegamenti ai dati più recenti del dashboard di monitoraggio. Per creare un file dei feed di dati dal vivo, fare clic sull'icona arancione **Esporta nell'alimentazione dei dati** sulla barra degli strumenti.

Se si preferisce stampare il dashboard corrente, fare clic sull'icona della stampante sulla barra degli strumenti.

</div>

</div>

<span> </span>

</div>

</div>

</div>

