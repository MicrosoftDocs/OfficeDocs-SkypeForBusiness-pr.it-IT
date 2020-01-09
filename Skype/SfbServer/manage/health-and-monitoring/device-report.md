---
title: Report dispositivo in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
description: 'Riepilogo: informazioni sul report del dispositivo in Skype for Business Server.'
ms.openlocfilehash: 9b9198d8080c8f1e22e59e2cd496bb7fb318eaae
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992413"
---
# <a name="device-report-in-skype-for-business-server"></a>Report dispositivo in Skype for Business Server
 
**Riepilogo:** Informazioni sul report sul dispositivo in Skype for Business Server.
  
Il report del dispositivo potrebbe essere meglio intitolato il rapporto microfono e altoparlanti; Questo perché il report del dispositivo recupera le metriche correlate alle chiamate, ad esempio la percentuale di chiamata scadente, l'eco e il tempo di cambio vocale, raggruppate per i microfoni e gli altoparlanti usati nella chiamata. Se si è interessati ai telefoni IP (detti anche "dispositivi"), usare invece il report sull' [inventario dei telefoni IP in Skype for Business Server](ip-phone-inventory-report.md) .
  
Il report del dispositivo è estremamente utile per gli amministratori per determinare se un determinato tipo di dispositivo sta vivendo alti volumi di chiamate di qualità scadente rispetto ad altri. A sua volta, questo potrebbe influenzare qualsiasi decisione da apportare quando arriva il momento di acquistare nuovi dispositivi o di sostituire i dispositivi esistenti.
  
Per impostazione predefinita, le informazioni visualizzate nel report del dispositivo si basano anche sul microfono (il dispositivo di acquisizione) e gli altoparlanti/auricolare (il dispositivo di rendering) usati nella chiamata. Supponi ad esempio di avere diversi utenti che usano il dispositivo di acquisizione seguente e il dispositivo di rendering seguente: per impostazione predefinita, le informazioni visualizzate nel report del dispositivo si basano anche sul microfono (il dispositivo di acquisizione) e gli altoparlanti/auricolare (il dispositivo di rendering) usati nella chiamata. Supponi ad esempio di avere diversi utenti che usano il dispositivo di acquisizione seguente e il dispositivo di rendering seguente:
  
- Dispositivo di acquisizione: microfono (SoundMAX Integrated Digital HD audio)
    
- Dispositivo di rendering: auricolare Headset (Microsoft LifeChat LX-3000)
    
Se gli utenti hanno apportato un totale di 254 chiamate, nel report verrà visualizzata una voce simile alla seguente:
  
|**Dispositivo di acquisizione**|**Dispositivo di rendering**|**Volume chiamata**|
|:-----|:-----|:-----|
|Microfono (SoundMAX Integrated Digital audio HD)  <br/> |Auricolare (Microsoft LifeChat LX-3000)  <br/> |254  <br/> |
   
Supponiamo che tu abbia un certo numero di utenti che usano lo stesso dispositivo di acquisizione, ma un dispositivo di rendering diverso. In questo caso, nel report verrà visualizzata una seconda voce, una per la combinazione univoca di dispositivo di acquisizione e dispositivo di rendering:
  
|**Dispositivo di acquisizione**|**Dispositivo di rendering**|**Volume chiamata**|
|:-----|:-----|:-----|
|Microfono (SoundMAX Integrated Digital audio HD)  <br/> |Auricolare (Microsoft LifeChat LX-3000)  <br/> |254  <br/> |
|Microfono (SoundMAX Integrated Digital audio HD)  <br/> |Altoparlanti (SoundMAX Integrated Digital HD audio)  <br/> |319  <br/> |
   
Se si preferisce visualizzare i totali combinati per un dispositivo specifico, ad esempio per il dispositivo di acquisizione SoundMAX, indipendentemente dal dispositivo di rendering usato, selezionare l'opzione appropriata nell'elenco a discesa tipo di dispositivo (dispositivo di acquisizione o dispositivo di rendering). Se si seleziona dispositivo di acquisizione in questo esempio, verrà restituito un output simile al seguente:
  
|**Dispositivo di acquisizione**|**Volume chiamata**|
|:-----|:-----|
|Microfono (SoundMAX Integrated Digital audio HD)  <br/> |573  <br/> |
   
## <a name="accessing-the-device-report"></a>Accesso al report del dispositivo

Il report del dispositivo è in genere accessibile dalla Home page dei report di monitoraggio. Tuttavia, se si sta visualizzando il [report dettagli chiamata in Skype for Business Server](call-detail-report.md) , è possibile eseguire il drill-down per il report del dispositivo per un dispositivo specifico facendo clic su una delle metriche seguenti:
  
- Dispositivo di acquisizione
    
- Dispositivo di rendering
    
Dal report dispositivo è possibile eseguire il drill-down [nel report elenco chiamate in Skype for Business Server](call-list-report-0.md) facendo clic su una delle metriche seguenti:
  
- Volume chiamata
    
- Percentuale di chiamata scadente
    
## <a name="making-the-best-use-of-the-device-report"></a>Sfruttare al meglio il report del dispositivo

Quando si tratta di nomi di dispositivi, il report del dispositivo è estremamente dettagliato; Supponiamo ad esempio di avere i seguenti dispositivi di acquisizione:
  
- Aastra 3002 microfono (2-Aastra 3002)
    
- Aastra 3002 microfono (3-Aastra 3002)
    
- Aastra 3002 microfono (Aastra 3002)
    
- Aastra 6725ip
    
- Microfono 6725ip Aastra (10-Aastra 6725ip)
    
- Microfono 6725ip Aastra (10-Aastra 6725ip)-V0
    
- Microfono 6725ip Aastra (2-Aastra 6725ip)
    
- Microfono 6725ip Aastra (3-Aastra 6725ip)
    
- Microfono 6725ip Aastra (4-Aastra 6725ip)
    
- Microfono 6725ip Aastra (5-Aastra 6725ip)
    
- Microfono 6725ip Aastra (6-Aastra 6725ip)
    
- Microfono 6725ip Aastra (7-Aastra 6725ip)
    
- Microfono 6725ip Aastra (9-Aastra 6725ip)
    
- Microfono 6725ip Aastra (9-Aastra 6725ip)-V0
    
- Microfono 6725ip Aastra (Aastra 6725ip)
    
- Microfono 6725ip Aastra (Aastra 6725ip)-V0
    
- Microfono 6725ip Aastra (dispositivo audio USB)
    
- Microfono 6725ip Aastra (dispositivo audio USB)-V0
    
> [!NOTE]
> Tieni presente che i nomi dei dispositivi di acquisizione potrebbero non essere uguali se stai usando versioni localizzate di Skype for Business Server. Un dispositivo denominato Aastra 6725ip Microphone (Aastra 6725ip)-V0 in inglese USA potrebbe avere un nome diverso in francese o spagnolo. 
  
Spesso si vorrà questo livello di dettaglio; in altri casi, tuttavia, potresti essere interessato al numero di chiamate che usano qualsiasi microfono Aastra, indipendentemente dal tipo di modello. Un modo per ottenere informazioni come questo consiste nell'esportare i dati del report del dispositivo in Microsoft Excel e quindi salvare i dati in un file con valori delimitati da virgole, ad esempio C:\Data\ Devices_Report. csv. Puoi quindi usare un set di comandi simili a questi per importare. File CSV in Windows PowerShell e riportare il numero totale di chiamate effettuate con un dispositivo di acquisizione Aastra:
  
```PowerShell
$devices = Import-Csv "C:\Data\Device_Report.csv
$sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
$sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
$x
```

Questo restituirà un singolo valore che rappresenta il numero totale di chiamate effettuate con un dispositivo di acquisizione di Aastra. Ad esempio: 384

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Ad esempio, il report dispositivo consente di filtrare in base a elementi come il tipo di chiamata, ovvero la chiamata a una chiamata client, una conferenza telefonica o una chiamata PSTN (Public Switched Telephone Network). È anche possibile scegliere la modalità di raggruppamento dei dati. In questo caso, i dispositivi vengono raggruppati per ora, giorno, settimana o mese.
  
Nella tabella seguente sono elencati i filtri che è possibile usare con il report del dispositivo.
  
**Filtri di report per dispositivi**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Da** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**A** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**Causa interruttore vocale** <br/> |Motivo per cui una chiamata deve essere inserita in modalità half duplex per evitare l'eco. In modalità half duplex, la comunicazione può viaggiare in una sola direzione alla volta, in modo analogo a quando gli utenti si alternano quando comunicano con un walkie-talkie. Selezionare una delle opzioni seguenti:  <br/> Tutti Nessuno cattivo timestamp Echo DNLP (Dynamic Nonlinear Processor) bassa complessità di stato del dispositivo non valido post-AEC Echo (annullamento dell'eco acustica) |
|**Causa eco** <br/> |Motivo per cui l'eco sopra il livello accettato è stato rilevato in una chiamata. (In telecomunicazioni Echo è un riflesso del suono, lo stesso fenomeno che si sente se si urla in fondo a un pozzo). Selezionare una delle opzioni seguenti:  <br/> Tutti Non valido timestamp post-AEC Echo (annullamento dell'eco acustica) ANLP (Adaptive Nonlinear Processor) DNLP (Dynamic Nonlinear Processor) ritaglio del microfono |
|**Tipo di chiamata** <br/> |Indica il tipo di chiamata effettuata. Selezionare una delle opzioni seguenti:  <br/> Tutti Chiamata in conferenza telefonica chiamata PSTN |
|**Tipo di accesso** <br/> |Indica se il client ha effettuato l'accesso alla rete interna o alla rete esterna quando è stata inserita la chiamata. Selezionare una delle opzioni seguenti:  <br/> Tutti Interni esterni |
|**Tipo di rete** <br/> |Indica il tipo di rete a cui il client è connesso quando è stata inserita la chiamata. Selezionare una delle opzioni seguenti:  <br/> Tutti Wireless cablata |
|**VPN** <br/> |Indica se un client esterno usa una connessione VPN (Virtual Private Network) quando la chiamata è stata inserita. Selezionare una delle opzioni seguenti:  <br/> Tutti VPN non VPN |
|**Tipo di dispositivo** <br/> |Indica il tipo di dispositivo. Selezionare una delle opzioni seguenti:  <br/> Dispositivo di rendering device Capture/rendering device Pair |
|**Nome dispositivo** <br/> |Nome del dispositivo di acquisizione o rendering. È possibile immettere il nome completo del dispositivo o qualsiasi parte del nome del dispositivo. Ad esempio, per trovare il microfono del dispositivo (Microsoft LifeCam VX-1000.), è possibile immettere il nome completo del dispositivo nel modo seguente:  <br/> Microfono (Microsoft LifeCam VX-1000.)  <br/> In alternativa, è possibile immettere solo una parte del nome. Ad esempio:  <br/> LifeCam  <br/> Tieni presente che il filtro precedente restituisce qualsiasi dispositivo che contiene la stringa "LifeCam" in qualsiasi punto del nome.  <br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report del dispositivo.
  
**Metriche del report del dispositivo**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Dispositivo di acquisizione** <br/> |Sì  <br/> |Dispositivo, ad esempio un microfono o una webcam, usato per la trasmissione di audio.  <br/> |
|**Dispositivo di rendering** <br/> |Sì  <br/> |Dispositivo, ad esempio un auricolare o un altoparlante, usato per ricevere l'audio.  <br/> |
|**Volume chiamata** <br/> |Sì  <br/> |Numero totale di chiamate inserite.  <br/> |
|**Percentuale di chiamata scadente** <br/> |Sì  <br/> |Percentuale di chiamate classificate come "scadente". Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.  <br/> |
|**Utenti univoci** <br/> |Sì  <br/> |Utenti univoci che hanno usato il dispositivo. Se un utente ha usato il dispositivo 13 volte, conta come un utente univoco, come un utente che ha usato solo il dispositivo una sola volta.  <br/> |
|**Rapporto tra il tempo di cambio vocale** <br/> |Sì  <br/> |Percentuale della chiamata che deve essere eseguita in modalità half duplex per evitare l'eco. In modalità half duplex, la comunicazione può viaggiare in una sola direzione alla volta, in modo analogo a quando gli utenti si alternano quando comunicano con un walkie-talkie.  <br/> |
|**Rapporto del microfono non funzionante** <br/> |Sì  <br/> |Percentuale della chiamata in cui il dispositivo di acquisizione non funzionava a un livello accettabile. Un valore elevato suggerisce che i problemi di qualità con la chiamata sono dovuti principalmente al dispositivo di acquisizione che non funziona come previsto.  <br/> |
|**Rapporto tra l'altoparlante non funziona** <br/> |Sì  <br/> |Percentuale della chiamata in cui il dispositivo di rendering non funzionava a un livello accettabile. Un valore elevato suggerisce che i problemi di qualità con la chiamata sono dovuti principalmente al dispositivo di rendering che non funziona come previsto.  <br/> |
|**Chiamate con interruttore vocale (%)** <br/> |Sì  <br/> |Percentuale delle chiamate totali che dovevano essere inserite nella modalità half duplex. In modalità half duplex, la comunicazione può viaggiare in una sola direzione alla volta, in modo analogo a quando gli utenti si alternano quando comunicano con un walkie-talkie.  <br/> |
|**Microfono Echo in (%)** <br/> |Sì  <br/> |Percentuale di tempo in cui Echo è stato rilevato nel flusso di acquisizione del microfono. In genere, i valori sono bassi per gli auricolari o i dispositivi portatili e più in alto per i telefoni con altoparlante o per gli altoparlanti autonomi. Per i dispositivi che supportano l'annullamento dell'eco acustica a bordo, i valori elevati indicano la perdita di eco. Per altri dispositivi, questa metrica non deve essere usata per valutare la qualità del dispositivo.  <br/> |
|**Invio Echo (%)** <br/> |Sì  <br/> |Percentuale di eco trasmessa ad altri utenti.  <br/> |
|**Chiamate con Echo (%)** <br/> |Sì  <br/> |Percentuale delle chiamate totali con echo che supera il livello accettabile.  <br/> |
   

