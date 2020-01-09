---
title: Uso del dashboard di monitoraggio in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 'Riepilogo: informazioni sul dashboard di monitoraggio in Skype for Business Server.'
ms.openlocfilehash: 39f5e9c2b024f73f669098c4da7eaca40ef4ea61
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992031"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a>Uso del dashboard di monitoraggio in Skype for Business Server
 
**Riepilogo:** Informazioni sul dashboard di monitoraggio in Skype for Business Server.
  
Il dashboard di monitoraggio offre agli amministratori una rapida panoramica dell'integrità del sistema e dell'uso del sistema Skype for Business Server. Il dashboard è progettato per mostrare una visualizzazione aggregata delle metriche di sistema chiave e per farlo visualizzando:
  
- Totali per il giorno corrente. Tieni presente che i valori visualizzati per il giorno corrente rappresentano i dati registrati dalla mezzanotte fino all'ora corrente (in base all'ora locale del server di report). Ciò significa che in genere verranno visualizzati i dati per un giorno parziale e non per un periodo di 24 ore. Ad esempio, se l'ora locale del server è 8:00 AM, viene visualizzato un valore di otto ore per i dati perché sono presenti otto ore tra mezzanotte e l'ora corrente di 8:00 AM.
    
- Totali per la settimana e totali delle tendenze per le ultime sei settimane.
    
- Totali per il mese e totali di tendenza per gli ultimi sei mesi (solo per l'uso del sistema).
    
Tieni presente che puoi usare il cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) per restituire l'URL usato per accedere ai report di monitoraggio di Skype for Business Server:
  
```PowerShell
Get-CsReportingConfiguration
```

Per impostazione predefinita, il dashboard di monitoraggio Mostra i dati per le metriche seguenti per la settimana corrente (e i totali delle tendenze per le sei settimane precedenti):
  
## <a name="system-usage-metrics"></a>Metriche per l'uso del sistema

 **Registrazione**
  
- Accessi utente univoci
    
  **Peer-to-peer**
  
- Totale sessioni
    
- Sessioni di messaggistica istantanea
    
- Sessioni audio
    
- Sessioni video
    
- Condivisione applicazioni
    
- Minuti totali della sessione audio
    
- Minuti media della sessione audio
    
  **Conferenza**
  
- Totale conferenze
    
- Conferenze di messaggistica istantanea
    
- Conferenze A/V
    
- Conferenze di condivisione applicazioni
    
- Conferenze Web
    
- Totale organizzatori
    
- Totale minuti di conferenza A/V
    
- AVG. Minuti della conferenza A/V
    
- Totale conferenze PSTN
    
- Totale partecipanti PSTN
    
- Minuti totali dei partecipanti PSTN
    
Oltre alle metriche per l'uso del sistema, le metriche seguenti visualizzano Total per il giorno corrente e per i sei giorni precedenti (se si seleziona la **visualizzazione settimanale**) o per la settimana corrente e per le ultime sei settimane se si seleziona **visualizzazione mensile**.
  
## <a name="per-user-call-diagnostics"></a>Diagnostica delle chiamate per utente

 **Utenti con errori di chiamata**
  
- Totale utenti con errori di chiamata
    
- Organizzatori di conferenze con errori di chiamata
    
  **Utenti con chiamate di qualità scadente**
  
- Totale utenti con chiamate di qualità scadente
    
## <a name="call-diagnostics"></a>Diagnostica chiamate

Peer-to-peer
  
- Totale errori
    
- Tasso di errore complessivo
    
- Tasso di errore di messaggistica istantanea
    
- Tasso di errore audio
    
- Tasso di errore di condivisione delle applicazioni
    
Conferenza
  
- Totale errori
    
- Tasso di errore complessivo
    
- Tasso di errore di messaggistica istantanea
    
- Tasso di errore A/V
    
- Tasso di errore di condivisione delle applicazioni
    
Primi cinque server per le sessioni non riuscite
  
## <a name="media-quality-diagnostics"></a>Diagnostica qualità multimediale

Peer-to-peer
  
- Totale chiamate di qualità scadente
    
- Percentuale di chiamata di qualità scadente
    
- Chiamate PSTN con qualità scadente
    
Conferenza
  
- Totale chiamate di qualità scadente
    
- Percentuale di chiamata di qualità scadente
    
- Chiamate PSTN con qualità scadente
    
Top server peggiore per percentuale di chiamata di qualità scadente
  
## <a name="working-with-the-monitoring-dashboard"></a>Uso del dashboard di monitoraggio

Come indicato, per i totali predefiniti vengono visualizzati per la settimana corrente e i valori di tendenza sono visualizzati per le ultime sei settimane. Se si preferisce visualizzare i totali per il mese corrente (nonché i valori di tendenza per gli ultimi sei mesi), fare clic sul collegamento **visualizzazione mensile** nell'angolo in alto a destra del dashboard. Se si decide di visualizzare i totali mensili, il testo del collegamento cambierà in **visualizzazione settimanale**. È possibile tornare alla visualizzazione settimanale facendo clic sul collegamento.
  
> [!TIP]
> Il dashboard di monitoraggio limita la visualizzazione dei totali per la settimana (o il mese) corrente e i valori di tendenza per le ultime sei settimane (o mesi). Non è possibile modificare le date e le ore. Ad esempio, non è possibile usare il dashboard per visualizzare i totali del report per il periodo di tempo che inizia nove mesi fa. 
  
I valori visualizzati nelle colonne **questa settimana**, **questo mese**o **oggi** possono essere collegati a informazioni più dettagliate sull'elemento. Tieni presente che il nome della colonna e i valori visualizzati in tale colonna saranno spesso diversi a seconda della metrica scelta e a seconda che tu abbia selezionato la visualizzazione settimanale o la visualizzazione mensile. Ad esempio, se si fa clic sui totali visualizzati per la metrica degli **accessi utente univoci** verrà visualizzato il **rapporto di registrazione utente** per il periodo di tempo specificato. È possibile tornare al dashboard di monitoraggio in qualsiasi momento facendo clic su **Dashboard**.
  
> [!TIP]
> È anche possibile accedere alla Home page dei report del server di monitoraggio facendo clic sul collegamento **report** nell'angolo in alto a destra del dashboard.
  
Nella colonna **tendenza** viene visualizzato un grafico a linee semplice che mostra i totali per le ultime sei settimane (o, a seconda delle metriche e dell'intervallo di tempo, degli ultimi sei giorni o degli ultimi sei mesi). Questi grafici a linee semplici visualizzano un punto dati senza etichetta per ogni periodo di tempo, ad esempio un punto dati senza etichetta per ognuna delle ultime sei settimane. Puoi tuttavia recuperare i valori effettivi per questi grafici tenendo il puntatore del mouse sul grafico. In questo caso, una descrizione comando Mostra i valori minimo e massimo nel grafico.
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a>Esportazione di dati dal dashboard di monitoraggio

Il dashboard di monitoraggio offre diversi modi per esportare la visualizzazione dashboard corrente. Sulla barra degli strumenti del dashboard verrà visualizzata un'icona che ha l'aspetto di un disco floppy con una freccia verde collegata. Se si fa clic su questa icona, verrà visualizzato un elenco a discesa che fornisce i formati di esportazione dei dati seguenti:
  
- File XML con i dati del report
    
- CSV (delimitato da virgola)
    
- PDF
    
- MHTML (archivio Web)
    
- Excel
    
- File TIFF
    
- Word
    
Per esportare la visualizzazione dashboard corrente (e i relativi valori), fare clic sull'opzione di esportazione desiderata. Skype for Business Server genera un report nel formato specificato e quindi consente di aprire il report o di salvarlo. Tieni presente che, per impostazione predefinita, Skype for Business Server assegna un titolo al **dashboard di monitoraggio** dei report e lo salva nella cartella download. Per assegnare un nome diverso al report o archiviarlo in un'altra cartella, fare clic sulla freccia accanto al pulsante **Salva** e quindi fare clic su **Salva come**. Se si sta bene con il **dashboard di monitoraggio** dei nomi e quando il report viene salvato nella cartella download, è sufficiente fare clic sul pulsante **Salva** .
  
Quando si prova ad esportare i dati del dashboard, è possibile che venga visualizzata una finestra di dialogo di **avviso di sicurezza** insieme al messaggio "le impostazioni correnti non consentono il download del file". Se si verifica questo problema, eseguire le operazioni seguenti:
  
- In Internet Explorer selezionare **Opzioni Internet**.
    
- Nella finestra di dialogo **Opzioni Internet** fare clic su **siti attendibili** nella scheda **sicurezza** e quindi fare clic su **siti**.
    
- Nella finestra di dialogo **siti attendibili** fare clic su **Aggiungi** per aggiungere il server Skype for business che gestisce i report di Skype for Business Server per le raccolte di siti Web attendibili.
    
- Fare clic su **Chiudi** e quindi su **OK**.
    
Sarà quindi necessario aggiornare il dashboard di monitoraggio prima che le modifiche abbiano effetto. A questo scopo, premi F5 o fai clic sull'icona **Aggiorna** nella barra degli strumenti del dashboard. L'icona di **aggiornamento** è un cerchio con una coppia di frecce verdi.
  
È anche possibile creare un foglio di calcolo di Excel che include feed di dati dinamici, che include collegamenti ai dati più recenti del dashboard di monitoraggio. Per creare un file di feed di dati in tempo reale, fare clic sull'icona arancione **Esporta in feed di dati** sulla barra degli strumenti.
  
Se si preferisce stampare il dashboard corrente, fare clic sull'icona della stampante sulla barra degli strumenti.
  

