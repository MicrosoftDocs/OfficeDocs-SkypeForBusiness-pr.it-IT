---
title: Uso del dashboard di monitoraggio in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 'Riepilogo: informazioni sul dashboard di monitoraggio in Skype for Business Server.'
ms.openlocfilehash: 98a96b8a513bad485a25aff76a69d787fb3079b0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827786"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a>Uso del dashboard di monitoraggio in Skype for Business Server
 
**Riepilogo:** Informazioni sul dashboard di monitoraggio in Skype for Business Server.
  
Il dashboard di monitoraggio offre agli amministratori una rapida panoramica dell'integrità e dell'utilizzo del sistema di Skype for Business Server. Il dashboard è progettato per mostrare una visualizzazione aggregata delle metriche di sistema chiave e a tale scopo visualizzando:
  
- Totali del giorno corrente. Si noti che i valori visualizzati per il giorno corrente rappresentano i dati registrati dalla mezzanotte all'ora corrente (in base all'ora locale del server di report). Ciò significa che in genere si visualizzano i dati per un giorno parziale e non per un periodo di 24 ore. Ad esempio, se l'ora locale del server è alle 8.00, verranno visualizzati otto ore di dati perché sono presenti otto ore tra la mezzanotte e l'ora corrente delle 8.00.
    
- Totali della settimana e totali delle tendenze delle ultime sei settimane.
    
- Totali del mese e totali delle tendenze degli ultimi sei mesi (solo per l'utilizzo del sistema).
    
Si noti che è possibile utilizzare il cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) per restituire l'URL utilizzato per accedere ai rapporti di monitoraggio di Skype for Business Server:
  
```PowerShell
Get-CsReportingConfiguration
```

Per impostazione predefinita, il dashboard di monitoraggio mostra i dati per le metriche seguenti per la settimana corrente (e i totali delle tendenze delle sei settimane precedenti):
  
## <a name="system-usage-metrics"></a>Metriche di utilizzo del sistema

 **Registrazione**
  
- Accessi utente univoci
    
  **Peer-to-peer**
  
- Totale sessioni
    
- Sessioni di messaggistica istantanea
    
- Sessioni audio
    
- Sessioni video
    
- Condivisione applicazioni
    
- Totale minuti sessione audio
    
- Media minuti sessione audio
    
  **Conferenza**
  
- Totale conferenze
    
- Conferenze di messaggistica istantanea
    
- Conferenze audio/video
    
- Conferenze di condivisione applicazioni
    
- Conferenze Web
    
- Totale organizzatori
    
- Totale minuti di conferenza audio/video
    
- Media Minuti conferenza audio/video
    
- Totale conferenze PSTN
    
- Totale partecipanti PSTN
    
- Totale minuti partecipante PSTN
    
Oltre alle metriche di utilizzo del sistema, le metriche seguenti visualizzano il totale per il giorno corrente e per i sei giorni precedenti (se si seleziona Visualizzazione **settimanale)** o per la settimana corrente e le ultime sei settimane se si seleziona Visualizzazione mensile. 
  
## <a name="per-user-call-diagnostics"></a>Per-User diagnostica chiamate

 **Utenti con errori di chiamata**
  
- Totale utenti con errori di chiamata
    
- Organizzatori di conferenze con errori di chiamata
    
  **Utenti con chiamate di qualità scarsa**
  
- Totale utenti con chiamate di qualità scarsa
    
## <a name="call-diagnostics"></a>Diagnostica chiamate

Peer-to-peer
  
- Totale errori
    
- Frequenza di errore complessiva
    
- Frequenza errori di messaggistica istantanea
    
- Frequenza di errore audio
    
- Frequenza errori di condivisione applicazioni
    
Conferenza
  
- Totale errori
    
- Frequenza di errore complessiva
    
- Frequenza errori di messaggistica istantanea
    
- Frequenza di errore A/V
    
- Frequenza errori di condivisione applicazioni
    
Primi cinque server per sessioni non riuscite
  
## <a name="media-quality-diagnostics"></a>Diagnostica qualità multimediale

Peer-to-peer
  
- Totale chiamate di qualità scarsa
    
- Percentuale di chiamate di qualità scarsa
    
- Chiamate PSTN con qualità scarsa
    
Conferenza
  
- Totale chiamate di qualità scarsa
    
- Percentuale di chiamate di qualità scarsa
    
- Chiamate PSTN con qualità scarsa
    
Principali server peggiori in base alla percentuale di chiamate di qualità scarsa
  
## <a name="working-with-the-monitoring-dashboard"></a>Utilizzo del dashboard di monitoraggio

Come indicato, per impostazione predefinita vengono visualizzati i totali per la settimana corrente e i valori delle tendenze delle ultime sei settimane. Se si preferisce visualizzare i totali del mese corrente e i valori di tendenza degli ultimi sei mesi, fare clic sul collegamento **Visualizzazione** mensile nell'angolo superiore destro del dashboard. Se si decide di visualizzare i totali mensili, il testo del collegamento verrà modificato in **Visualizzazione settimanale.** È possibile tornare alla visualizzazione settimanale facendo clic su tale collegamento.
  
> [!TIP]
> Il dashboard di monitoraggio limita l'analisi dei totali della settimana (o del mese) corrente e dei valori di tendenza delle ultime sei settimane (o mesi). Non è possibile modificare queste date e ore. Ad esempio, non è possibile utilizzare il dashboard per visualizzare i totali dei report per il periodo di tempo che inizia nove mesi fa. 
  
I valori visualizzati nelle colonne Questa  **settimana,** Questo **mese** o Oggi collegano l'utente a informazioni più dettagliate sull'elemento. Tenere presente che il nome della colonna e i valori visualizzati in tale colonna spesso variano a seconda della metrica scelta e a seconda che sia stata selezionata la visualizzazione settimanale o mensile. Ad esempio, se si fa clic  sui totali visualizzati per la metrica Accessi utente univoci, verrà visualizzato il **Rapporto** registrazione utenti per il periodo di tempo specificato. È possibile tornare al dashboard di monitoraggio in qualsiasi momento facendo clic su **Dashboard.**
  
> [!TIP]
> È inoltre possibile accedere alla home page dei rapporti di Monitoring Server facendo clic sul collegamento **Report** nell'angolo in alto a destra del dashboard.
  
La **colonna Tendenza** visualizza un semplice grafico a linee che mostra i totali delle ultime sei settimane (o, a seconda della metrica e dell'intervallo di tempo, degli ultimi sei giorni o degli ultimi sei mesi). Questi semplici grafici a linee visualizzano una data point senza etichetta per ogni periodo di tempo (ad esempio, una data point senza etichetta per ognuna delle ultime sei settimane). Tuttavia, puoi recuperare i valori effettivi per questi grafici tenendo il puntatore del mouse sul grafico. In questo caso, una descrizione comando mostra i valori massimo e minimo nel grafico.
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a>Esportazione di dati dal dashboard di monitoraggio

Il dashboard di monitoraggio offre diversi modi per esportare la visualizzazione dashboard corrente. Sulla barra degli strumenti del dashboard verrà visualizzata un'icona simile a un disco floppy a cui è collegata una freccia verde. Se si fa clic su questa icona, verrà visualizzato un elenco a discesa con i seguenti formati di esportazione dei dati:
  
- File XML con dati del rapporto
    
- CSV (delimitato da virgole)
    
- PDF
    
- MHTML (archivio Web)
    
- Excel
    
- File TIFF
    
- Word
    
Per esportare la visualizzazione dashboard corrente e i relativi valori, fare clic sull'opzione di esportazione desiderata. Skype for Business Server genera un report nel formato specificato e quindi consente di aprirlo o salvarlo. Si noti che, per impostazione predefinita, Skype for Business Server titoli il **report Monitoring Dashboard** e lo salva nella cartella Download. Per assegnare un nome diverso al report o archiviarlo in  una cartella diversa, fare clic sulla freccia accanto al pulsante Salva e quindi su **Salva con nome.** Se si ha il nome **Dashboard di monitoraggio** e il report viene salvato nella cartella Download, è sufficiente fare clic sul **pulsante** Salva.
  
È possibile che, quando si tenta di  esportare i dati del dashboard, venga visualizzata una finestra di dialogo avviso di sicurezza con il messaggio "Le impostazioni correnti non consentono il download di questo file". In questo caso, eseguire le operazioni seguenti:
  
- In Internet Explorer selezionare **Opzioni Internet.**
    
- Nella scheda **Protezione della** finestra di dialogo Opzioni Internet **fare** clic su **Siti attendibili** e quindi su **Siti.**
    
- Nella finestra **di dialogo**  Siti attendibili fare clic su Aggiungi per aggiungere Skype for Business Server che esegue i report di Skype for Business Server alle raccolte di siti Web attendibili.
    
- Fare **clic su** Chiudi e quindi su **OK.**
    
Sarà quindi necessario aggiornare il dashboard di monitoraggio prima che le modifiche avranno effetto. A tale scopo, premere F5 o fare clic **sull'icona** Aggiorna sulla barra degli strumenti del dashboard. **L'icona** Aggiorna è un cerchio con una coppia di frecce verdi al suo interno.
  
È inoltre possibile creare un foglio di calcolo di Excel che include feed di dati in tempo reale, che include collegamenti ai dati più recenti del dashboard di monitoraggio. Per creare un file di feed di dati in tempo reale, fare clic sull'icona arancione Esporta in **feed** dati sulla barra degli strumenti.
  
Se si preferisce stampare il dashboard corrente, fare clic sull'icona della stampante sulla barra degli strumenti.
  

