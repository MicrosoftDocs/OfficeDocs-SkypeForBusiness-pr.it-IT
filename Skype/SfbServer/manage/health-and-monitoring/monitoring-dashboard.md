---
title: Uso del dashboard di monitoraggio in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 'Riepilogo: informazioni sul dashboard di monitoraggio in Skype for Business Server.'
ms.openlocfilehash: ac68ae2174fcd7c4266da77c2d079c2f9a31d8e5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862303"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a>Uso del dashboard di monitoraggio in Skype for Business Server
 
**Riepilogo:** Informazioni sul dashboard di monitoraggio in Skype for Business Server.
  
Il dashboard di monitoraggio offre agli amministratori una breve panoramica dell'Skype for Business Server dell'integrità del sistema e dell'utilizzo del sistema. Il dashboard è progettato per mostrare una visualizzazione aggregata delle metriche chiave del sistema e per farlo visualizzando:
  
- Totali per il giorno corrente. Si noti che i valori visualizzati per il giorno corrente rappresentano i dati registrati dalla mezzanotte fino all'ora corrente (in base all'ora locale del server di report). Ciò significa che in genere verranno visualizzati i dati per un giorno parziale e non per un periodo di 24 ore. Se, ad esempio, l'ora locale del server è 8:00, i dati verranno visualizzati in otto ore perché sono presenti otto ore tra la mezzanotte e l'ora corrente delle 8.00.
    
- Totali della settimana e totali di tendenza per le ultime sei settimane.
    
- Totali del mese e totali tendenziale degli ultimi sei mesi (solo per l'utilizzo del sistema).
    
Si noti che è possibile utilizzare il cmdlet [Get-CsReportingConfiguration](/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) per restituire l'URL utilizzato per accedere Skype for Business Server report di monitoraggio:
  
```PowerShell
Get-CsReportingConfiguration
```

Per impostazione predefinita, il dashboard di monitoraggio mostra i dati per le metriche seguenti per la settimana corrente (e i totali delle tendenze per le sei settimane precedenti):
  
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
    
- Media dei minuti di sessione audio
    
  **Conferenza**
  
- Totale conferenze
    
- Conferenze di messaggistica istantanea
    
- Conferenze audio/video
    
- Conferenze di condivisione applicazioni
    
- Conferenze Web
    
- Totale organizzatori
    
- Totale minuti di conferenza audio/video
    
- Media. Minuti conferenza audio/video
    
- Totale conferenze PSTN
    
- Totale partecipanti PSTN
    
- Totale minuti partecipante PSTN
    
Oltre alle metriche utilizzo sistema, le metriche seguenti visualizzano il totale per il giorno corrente e i sei giorni precedenti (se si seleziona **Visualizzazione** settimanale ) o per la settimana corrente e le ultime sei settimane se si seleziona Visualizzazione mensile **.**
  
## <a name="per-user-call-diagnostics"></a>Per-User di chiamata

 **Utenti con errori di chiamata**
  
- Totale utenti con errori di chiamata
    
- Organizzatori di conferenze con errori di chiamata
    
  **Utenti con chiamate di qualità scarsa**
  
- Totale utenti con chiamate di qualità scarsa
    
## <a name="call-diagnostics"></a>Diagnostica chiamate

Peer-to-peer
  
- Totale errori
    
- Frequenza di errore generale
    
- Frequenza errori di messaggistica istantanea
    
- Frequenza di errore audio
    
- Frequenza errori di condivisione applicazioni
    
Conferenza
  
- Totale errori
    
- Frequenza di errore generale
    
- Frequenza errori di messaggistica istantanea
    
- Frequenza di errore A/V
    
- Frequenza errori di condivisione applicazioni
    
Primi cinque server per sessioni non riuscite
  
## <a name="media-quality-diagnostics"></a>Diagnostica qualità multimediale

Peer-to-peer
  
- Totale chiamate di qualità scarsa
    
- Percentuale chiamate di qualità scarsa
    
- Chiamate PSTN con qualità scarsa
    
Conferenza
  
- Totale chiamate di qualità scarsa
    
- Percentuale chiamate di qualità scarsa
    
- Chiamate PSTN con qualità scarsa
    
Top worst servers by poor quality call percentage
  
## <a name="working-with-the-monitoring-dashboard"></a>Utilizzo del dashboard di monitoraggio

Come indicato, per impostazione predefinita vengono visualizzati i totali per la settimana corrente e i valori di tendenza vengono visualizzati per le ultime sei settimane. Se si preferisce visualizzare i totali per il mese corrente (nonché i valori delle tendenze degli ultimi sei mesi), fare clic sul collegamento **Visualizzazione** mensile nell'angolo superiore destro del dashboard. Se si decide di visualizzare i totali mensili, il testo del collegamento verrà modificato in **Visualizzazione settimanale.** È possibile tornare alla visualizzazione settimanale facendo clic sul collegamento.
  
> [!TIP]
> Il dashboard di monitoraggio consente di visualizzare i totali per la settimana (o il mese) corrente e i valori di tendenza per le ultime sei settimane (o mesi). Non è possibile modificare queste date e ore. Ad esempio, non è possibile utilizzare il dashboard per visualizzare i totali dei report per il periodo di tempo che inizia nove mesi fa. 
  
I valori visualizzati nelle **colonne This week**, This **month** o **Today** collegano l'utente a informazioni più dettagliate sull'elemento. Tenere presente che il nome della colonna e i valori visualizzati in tale colonna spesso variano a seconda della metrica scelta e a seconda che sia stata selezionata la visualizzazione settimanale o mensile. Ad esempio, se si fa clic  sui totali visualizzati per la metrica Accessi utente univoci, verrà visualizzato il **Rapporto** registrazione utenti per il periodo di tempo specificato. È possibile tornare al dashboard di monitoraggio in qualsiasi momento facendo clic su **Dashboard.**
  
> [!TIP]
> È inoltre possibile accedere alla home page dei report di Monitoring Server facendo clic sul **collegamento Report** nell'angolo superiore destro del dashboard.
  
La **colonna Tendenza** visualizza un semplice grafico a linee che mostra i totali delle ultime sei settimane (o, a seconda della metrica e dell'intervallo di tempo, degli ultimi sei giorni o degli ultimi sei mesi). Questi grafici a linee semplici visualizzano un punto dati senza etichetta per ogni periodo di tempo (ad esempio, un punto dati senza etichetta per ognuna delle ultime sei settimane). Tuttavia, puoi recuperare i valori effettivi per questi grafici tenendo il puntatore del mouse sul grafico. In tal caso, una descrizione comando mostra i valori massimo e minimo nel grafico.
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a>Esportazione di dati dal dashboard di monitoraggio

Il dashboard di monitoraggio offre diversi modi per esportare la visualizzazione dashboard corrente. Sulla barra degli strumenti del dashboard viene visualizzata un'icona simile a un disco floppy a cui è collegata una freccia verde. Se si fa clic su questa icona, verrà visualizzato un elenco a discesa che visualizza i formati di esportazione dati seguenti:
  
- File XML con dati del rapporto
    
- CSV (delimitato da virgole)
    
- PDF
    
- MHTML (archivio Web)
    
- Excel
    
- File TIFF
    
- Word
    
Per esportare la visualizzazione dashboard corrente e i relativi valori, fare clic sull'opzione di esportazione desiderata. Skype for Business Server viene generato un report nel formato specificato e quindi è possibile aprirlo o salvarlo. Nota che, per impostazione predefinita, Skype for Business Server il report **Monitoring Dashboard** e lo salva nella cartella Download. Per assegnare al report un nome diverso o archiviarlo in  una cartella diversa, fare clic sulla freccia accanto al pulsante Salva e quindi su **Salva con nome.** Se stai bene con nome **Monitoring Dashboard** e con il report salvato nella cartella Download puoi semplicemente fare clic sul **pulsante** Salva.
  
È possibile che, quando si tenta di  esportare i dati del dashboard, venga visualizzata una finestra di dialogo Avviso di sicurezza insieme al messaggio "Le impostazioni correnti non consentono il download di questo file". In questo caso, eseguire le operazioni seguenti:
  
- In Internet Explorer seleziona **Opzioni Internet.**
    
- Nella scheda **Protezione della** finestra di dialogo Opzioni Internet **fare** clic su **Siti attendibili** e quindi su **Siti.**
    
- Nella finestra **di dialogo**  Siti attendibili fare clic su Aggiungi per aggiungere il Skype for Business Server che esegue Skype for Business Server report alle raccolte di siti Web attendibili.
    
- Fare **clic su** Chiudi e quindi su **OK.**
    
Sarà quindi necessario aggiornare il dashboard di monitoraggio prima che le modifiche avranno effetto. A tale scopo, premere F5 o fare clic **sull'icona** Aggiorna nella barra degli strumenti del dashboard. **L'icona** Aggiorna è un cerchio con una coppia di frecce verdi al suo interno.
  
È inoltre possibile creare un foglio Excel che include feed di dati in tempo reale, che include collegamenti ai dati più recenti del dashboard di monitoraggio. Per creare un file di feed di dati in tempo reale, fare clic sull'icona **arancione** Esporta in feed di dati sulla barra degli strumenti.
  
Se si preferisce stampare il dashboard corrente, fare clic sull'icona della stampante sulla barra degli strumenti.
