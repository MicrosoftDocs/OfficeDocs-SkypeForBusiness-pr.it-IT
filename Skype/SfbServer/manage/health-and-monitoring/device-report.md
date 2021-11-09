---
title: Device Report in Skype for Business Server
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
ms.assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
description: 'Riepilogo: informazioni sul Rapporto dispositivi in Skype for Business Server.'
ms.openlocfilehash: 29ea62f7578b491a940a47663668d0bc83ec5402
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835264"
---
# <a name="device-report-in-skype-for-business-server"></a>Device Report in Skype for Business Server
 
**Riepilogo:** Informazioni su Report dispositivi in Skype for Business Server.
  
Il Rapporto dispositivi potrebbe anche essere intitolato Rapporto altoparlanti e microfono perché il Rapporto dispositivi recupera le metriche relative alle chiamate (ad esempio, la percentuale di chiamate con qualità insufficiente, l'eco e il tempo commutazione vocale) raggruppate in base ai microfoni e agli altoparlanti utilizzati nella chiamata. Se sei interessato ai telefoni IP (anche comunemente denominati "dispositivi"), usa invece il Rapporto inventario ip Telefono [in Skype for Business Server.](ip-phone-inventory-report.md)
  
Il Rapporto dispositivi è estremamente utile agli amministratori per stabilire se un tipo specifico di dispositivo riporta volumi elevati di chiamate con qualità insufficiente rispetto ad altri. Questo può influire sulle decisioni da prendere in merito all'acquisto di nuovi dispositivi o alla sostituzione dei dispositivi esistenti.
  
Per impostazione predefinita, le informazioni visualizzate nel Rapporto dispositivi si basano sul microfono (il dispositivo di acquisizione) e gli altoparlanti/auricolari (il dispositivo di rendering) utilizzati nella chiamata. Ad esempio, si supponga che vari utenti debbano utilizzare il dispositivo di acquisizione e il dispositivo di rendering seguenti:
  
- Dispositivo di acquisizione -- Microfono (HD Audio integrato digitale SoundMAX)
    
- Dispositivo di rendering -- Auricolare e microtelefono (Microsoft LifeChat LX-3000)
    
Se gli utenti hanno eseguito un totale di 254 chiamate, nel rapporto verrà visualizzata una voce simile alla seguente:
  
|**Dispositivo di acquisizione**|**Dispositivo di rendering**|**Volume chiamata**|
|:-----|:-----|:-----|
|Microfono (HD Audio integrato digitale SoundMAX)  <br/> |Auricolare e microtelefono (Microsoft LifeChat LX-3000)  <br/> |254  <br/> |
   
Ora si supponga che un certo numero di utenti utilizzi lo stesso dispositivo di acquisizione ma un dispositivo di rendering diverso. In tal caso, nel report verrà visualizzata una voce nella seconda riga per tale combinazione univoca di dispositivo di acquisizione e dispositivo di rendering:
  
|**Dispositivo di acquisizione**|**Dispositivo di rendering**|**Volume chiamata**|
|:-----|:-----|:-----|
|Microfono (HD Audio integrato digitale SoundMAX)  <br/> |Auricolare e microtelefono (Microsoft LifeChat LX-3000)  <br/> |254  <br/> |
|Microfono (HD Audio integrato digitale SoundMAX)  <br/> |Altoparlanti (HD Audio integrato digitale SoundMAX)  <br/> |319  <br/> |
   
Se si desidera visualizzare i totali combinati per un determinato dispositivo (ad esempio, per il dispositivo di acquisizione SoundMAX, indipendentemente dal dispositivo di rendering utilizzato), selezionare l'opzione appropriata dall'elenco a discesa Tipo di dispositivo (Dispositivo di acquisizione o Dispositivo di rendering). Se nell'esempio si seleziona Dispositivo di acquisizione, si riceverà il seguente output:
  
|**Dispositivo di acquisizione**|**Volume chiamata**|
|:-----|:-----|
|Microfono (HD Audio integrato digitale SoundMAX)  <br/> |573  <br/> |
   
## <a name="accessing-the-device-report"></a>Accesso al Rapporto dispositivi

In genere è possibile accedere al Rapporto dispositivi dalla home page Relazioni monitoraggio. Tuttavia, se stai visualizzando il Rapporto dettagli chiamata [in Skype for Business Server](call-detail-report.md) puoi eseguire il drill-down al Rapporto dispositivi per un dispositivo specifico facendo clic su una delle metriche seguenti:
  
- Dispositivo di acquisizione
    
- Dispositivo di rendering
    
Dal Rapporto dispositivi è possibile eseguire il drill-down al Rapporto elenco chiamate [in Skype for Business Server](call-list-report-0.md) facendo clic su una delle metriche seguenti:
  
- Volume chiamata
    
- Percentuale chiamate di livello insufficiente
    
## <a name="making-the-best-use-of-the-device-report"></a>Utilizzo del Rapporto dispositivi

Il Rapporto dispositivi è molto dettagliato in merito ai nomi dei dispositivi. Ad esempio, si supponga di disporre dei dispositivi di acquisizione seguenti:
  
- Microfono Aastra 3002 (2- Aastra 3002)
    
- Microfono Aastra 3002 (3- Aastra 3002)
    
- Microfono Aastra 3002 (Aastra 3002)
    
- Aastra 6725ip
    
- Microfono Aastra 6725ip (10- Aastra 6725ip)
    
- Microfono Aastra 6725ip (10- Aastra 6725ip)-V0
    
- Microfono Aastra 6725ip (2- Aastra 6725ip)
    
- Microfono Aastra 6725ip (3- Aastra 6725ip)
    
- Microfono Aastra 6725ip (4- Aastra 6725ip)
    
- Microfono Aastra 6725ip (5- Aastra 6725ip)
    
- Microfono Aastra 6725ip (6- Aastra 6725ip)
    
- Microfono Aastra 6725ip (7- Aastra 6725ip)
    
- Microfono Aastra 6725ip (9- Aastra 6725ip)
    
- Microfono Aastra 6725ip (9- Aastra 6725ip)-V0
    
- Microfono Aastra 6725ip (Aastra 6725ip)
    
- Microfono Aastra 6725ip (Aastra 6725ip)-V0
    
- Microfono Aastra 6725ip (dispositivo audio USB)
    
- Microfono Aastra 6725ip (dispositivo audio USB)-V0
    
> [!NOTE]
> Tieni presente che i nomi dei dispositivi di acquisizione potrebbero non essere uguali se stai eseguendo versioni localizzate di Skype for Business Server. Un dispositivo denominato Aastra 6725ip Microphone (Aastra 6725ip)-V0 in inglese (Stati Uniti) potrebbe avere un nome diverso in francese o spagnolo. 
  
Anche se spesso è utile questo livello di dettaglio, a volte si potrebbe essere interessati solo al numero di chiamate che utilizzano qualsiasi microfono Aastra, indipendentemente dal numero del modello. Un modo per ottenere questo tipo di informazioni è esportare i dati del Rapporto dispositivi in Microsoft Excel e salvare i dati in un file di valori delimitati da virgole (ad esempio, C:\Data\Devices_Report.csv). È possibile utilizzare un insieme di comandi simili a questi per importare il file CSV in Windows PowerShell e restituire il numero totale di chiamate eseguite utilizzando un dispositivo di acquisizione Aastra:
  
```PowerShell
$devices = Import-Csv "C:\Data\Device_Report.csv
$sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
$sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
$x
```

Verrà restituito un unico valore che rappresenta il numero totale di chiamate eseguite utilizzando un dispositivo di acquisizione Aastra. Ad esempio: 384

## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Ad esempio, il Rapporto dispositivi consente di filtrare in base a elementi quali il tipo di chiamata (ossia se la chiamata è di tipo client) una conferenza telefonica o una chiamata PSTN (Public Switched Telephone Network). È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso i dispositivi sono raggruppabili per ora, giorno, settimana o mese.
  
Nella tabella seguente sono elencati i filtri applicabili al Rapporto dispositivi.
  
**Filtri del Rapporto dispositivi**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Causa commutazione vocale** <br/> |Motivo per cui è stato necessario effettuare una chiamata in modalità half-duplex per evitare l'eco. In modalità half-duplex la comunicazione può viaggiare in una sola direzione alla volta, in modo analogo ai turni effettuati dagli utenti in una comunicazione con un walkie-talkie. Selezionare una delle opzioni seguenti:  <br/> [All] Nessuno Timestamp non valido Echo DNLP (processore dinamico non lineare) Bassa complessità Stato del dispositivo Non valido Eco post-AEC (annullamento eco acustico) |
|**Causa eco** <br/> |Motivo per cui in una chiamata è stato rilevato l'eco sopra il livello accettato (nelle telecomunicazioni l'eco è un riflesso del suono, lo stesso effetto che si produce gridando verso il fondo di un pozzo). Selezionare una delle opzioni seguenti:  <br/> [All] Nessuno Timestamp non valido Eco post-AEC (annullamento eco acustico) ANLP (processore adattivo non lineare) DNLP (processore dinamico non lineare) Ritaglio microfono |
|**Tipo di chiamata** <br/> |Indica il tipo di chiamata effettuata. Selezionare una delle opzioni seguenti:  <br/> [All] Chiamata client Chiamata PSTN Conferenza telefonica |
|**Tipo di accesso** <br/> |Indica se al momento dell'esecuzione della chiamata il client era connesso alla rete interna o alla rete esterna. Selezionare una delle opzioni seguenti:  <br/> [All] Internal External |
|**Tipo di rete** <br/> |Indica il tipo di rete alla quale era connesso il client quando è stata effettuata la chiamata. Selezionare una delle opzioni seguenti:  <br/> [All] Wireless cablata |
|**VPN** <br/> |Indica se un client esterno stava utilizzando una connessione VPN (Virtual Private Network) al momento della chiamata. Selezionare una delle opzioni seguenti:  <br/> [All] VPN non VPN |
|**Tipo di dispositivo** <br/> |Indica il tipo di dispositivo. Selezionare una delle opzioni seguenti:  <br/> Coppia dispositivo di acquisizione/rendering dispositivo di rendering |
|**Nome dispositivo** <br/> |Nome del dispositivo di acquisizione o di rendering. È possibile immettere il nome completo del dispositivo o una parte di esso. Ad esempio, per trovare il dispositivo Microfono (Microsoft LifeCam VX-1000.), è possibile immettere il nome del dispositivo completo come segue:  <br/> Microfono (Microsoft LifeCam VX-1000.)  <br/> In alternativa, è possibile immettere solo una parte del nome, ad esempio:  <br/> LifeCam  <br/> Si noti che il filtro precedente restituisce qualsiasi dispositivo il cui nome contenga la stringa "LifeCam" in qualsiasi punto.  <br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel Rapporto dispositivi.
  
**Metriche del rapporto dispositivi**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Dispositivo di acquisizione** <br/> |Sì  <br/> |Dispositivo (ad esempio un microfono o una webcam) utilizzato per la trasmissione dell'audio.  <br/> |
|**Dispositivo di rendering** <br/> |Sì  <br/> |Dispositivo (ad esempio cuffie o altoparlanti) utilizzato per la ricezione dell'audio.  <br/> |
|**Volume chiamata** <br/> |Sì  <br/> |Numero totale di chiamate effettuate.  <br/> |
|**Percentuale chiamate di livello insufficiente** <br/> |Sì  <br/> |Percentuale di chiamate classificate come "di livello insufficiente". Una chiamata di livello insufficiente è una chiamata in cui almeno una delle metriche misurate supera il valore consentito (ad esempio una chiamata che presenta eccessiva instabilità).  <br/> |
|**Utenti univoci** <br/> |Sì  <br/> |Utenti univoci che hanno utilizzato il dispositivo. Se un utente ha utilizzato 13 volte il dispositivo, verrà conteggiato come utente univoco, come un utente che ha utilizzato il dispositivo una sola volta.  <br/> |
|**Rapporto di tempo commutazione vocale** <br/> |Sì  <br/> |Percentuale della chiamata che è stato necessario effettuare in modalità half-duplex per evitare l'eco. In modalità half-duplex la comunicazione può viaggiare in una sola direzione alla volta, in modo analogo ai turni effettuati dagli utenti in una comunicazione con un walkie-talkie.  <br/> |
|**Rapporto di microfono non funzionante** <br/> |Sì  <br/> |Percentuale della chiamata in cui il dispositivo di acquisizione non ha funzionato a un livello accettabile. Un valore elevato indica che i problemi di qualità della chiamata erano principalmente dovuti a un funzionamento improprio del dispositivo di acquisizione.  <br/> |
|**Rapporto di altoparlante non funzionante** <br/> |Sì  <br/> |Percentuale della chiamata in cui il dispositivo di rendering non ha funzionato a un livello accettabile. Un valore elevato indica che i problemi di qualità della chiamata erano principalmente dovuti a un funzionamento improprio del dispositivo di rendering.  <br/> |
|**Chiamate con commutazione vocale (%)** <br/> |Sì  <br/> |Percentuale delle chiamate totali che è stato necessario effettuare in modalità half-duplex. In modalità half-duplex la comunicazione può viaggiare in una sola direzione alla volta, in modo analogo ai turni effettuati dagli utenti in una comunicazione con un walkie-talkie.  <br/> |
|**Eco microfono in ingresso (%)** <br/> |Sì  <br/> |Percentuale di tempo in cui è stata rilevata l'eco nel flusso di acquisizione del microfono. In genere, i valori sono bassi per cuffie o ricevitori e superiori per i telefoni degli altoparlanti o gli altoparlanti autonomi. Per i dispositivi che supportano l'annullamento dell'eco acustico a bordo, valori elevati indicano una perdita di eco. Per altri dispositivi, questa metrica non deve essere usata per valutare la qualità del dispositivo.  <br/> |
|**Invio eco (%)** <br/> |Sì  <br/> |Percentuale di eco trasmesso ad altri utenti.  <br/> |
|**Chiamate con eco (%)** <br/> |Sì  <br/> |Percentuale delle chiamate totali con eco superiore al livello accettabile.  <br/> |
   

