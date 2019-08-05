---
title: Note sulla versione
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
description: In questo articolo vengono illustrati i miglioramenti cumulativi nelle sale di Microsoft teams.
ms.openlocfilehash: f6fc9bb36a4b34d9e900666bf14df0c4d0893c46
ms.sourcegitcommit: baa425d7a07429e6fe84b4f27c76243cf755c1a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2019
ms.locfileid: "36184828"
---
# <a name="release-notes"></a>Note sulla versione 

In questo articolo vengono illustrati i miglioramenti cumulativi nelle sale di Microsoft teams.


##  <a name="version-history"></a>Cronologia versioni

| Rilascio | Pubblicato in <br>Microsoft Store | 
| ---     | ---  |
| 4.0.105.0 | 07/10/2019   |
| 4.0.85.0 | 04/08/2019   |
| 4.0.78.0 | 03/14/2019   |
| 4.0.76.0 | 03/04/2019   |
| 4.0.64.0 | 12/14/2018   |
| 4.0.51.0 | 11/17/2018   | 
| 4.0.31.0 | 10/16/2018   | 
| 4.0.27.0 |  10/1/2018    | 
| 4.0.19.0 |  08/31/2018    |   
| 4.0.18.0 |  08/27/2018    |   
| 4.0.8.0 |  07/06/2018    |   
| 3.1.115.0|  06/18/2018    |
| 3.1.113.0|  06/13/2018    |   
| 3.1.112.0|  06/05/2018    |   
| 3.1.104.0|  04/16/2018    |            
| 3.1.100.0|  03/16/2018    |            
| 3.1.99.0 | 3/14/2018      |  
| 3.1.98.0    | 3/8/2018    |   
|  3.0.16.0    |  11/27/2017   |
| 3.0.15.0 | 10/3/2017  |            
| 3.0.12.0 |  9/1/2017  |            
| 3.0.8.0 | 11/16/2017 | 
| 3.0.6.0 | 11/16/2017 | 
| 2.0.2.0  | 03/15/2017 | 
| RTM (1.0.8) | 12/7/2016  | 

## <a name="microsoft-teams-rooms-feature-introduction-and-issue-resolution"></a>Funzionalità di introduzione e risoluzione dei problemi di Microsoft teams rooms
### <a name="401050-07102019"></a>4.0.105.0 (07/10/2019)

Introdotti in questo aggiornamento:
- Skype room System Store app rebranding in "Microsoft teams room"
- Allineamento dell'interfaccia utente della console Microsoft teams in Microsoft Teams
- Aggiornamento tema per mantenere solo l'immagine di sfondo personalizzata davanti alle visualizzazioni della sala mentre si rende il colore di sfondo della console per garantire i controlli dell'interfaccia utente della console soddisfano i requisiti di accessibilità
- Barra universale per i controlli delle chiamate in riunione per le chiamate di Team/riunioni per assicurare un'esperienza coerente con Microsoft teams PC/Web/client mobili<sup>1</sup>
- Valutazione della qualità della chiamata dopo le chiamate di teams/meeting<sup>1</sup>
- Ricevere/render Microsoft Whitebord in Microsoft teams fronte sala della visualizzazione della sala quando è condiviso da PC/Web/mobile teams client<sup>1</sup>  <sup>2</sup>
- Supporto rimosso per l'aggiornamento a Windows 10 versione 1809 a causa di problemi di compatibilità riscontrati con il client della sala Microsoft teams. Il supporto per la versione 19H1 di Windows 10 verrà aggiunto nelle versioni future

<sup>1</sup> implementazione del servizio Microsoft teams con teams Rings. Questa funzionalità può essere disponibile prima o dopo l'aggiornamento client di 4.0.105.0

<sup>2</sup> richiede agli amministratori IT di attivare Microsoft whiteboard Web. Inoltre, se si ha il tocco anteriore della visualizzazione della sala, è necessario calibrare più schermi di tocco usando le impostazioni di Windows con il dispositivo amministratore login per iniziare a usare Microsoft whiteboard per Collboration dalla visualizzazione della sala dopo la condivisione in teams meeting

### <a name="40850-0482019"></a>4.0.85.0 (04/8/2019)

Introdotti in questo aggiornamento:

- Risolve un problema con la caratteristica "Invia feedback" 
- Ottimizzazioni in preparazione del prossimo aggiornamento del dispositivo MTR a Windows 10 versione 1809

### <a name="40780-03142019"></a>4.0.78.0 (03/14/2019)

Introdotti in questo aggiornamento:

- Correzione di un bug "blocca all'avvio dell'app" che ha influenzato i dispositivi nella build legacy di Windows 10 RS2.  


### <a name="40760-03042019"></a>4.0.76.0 (03/04/2019)

Introdotti in questo aggiornamento:

- Tastierino DTMF per riunioni P2P di Microsoft teams e chiamate PSTN. Per rendere Microsoft teams il client chiamante predefinito, gli amministratori devono impostare IsTeamsDefaultClient su true
- Aggiungere il video in arrivo di un partecipante remoto a schermo intero davanti al display della sala. Usare il comando "Aggiungi" dall'elenco dei partecipanti nella console
- Miglioramenti apportati alle notifiche della sala di attesa con aggiunta della notifica della chat room
- La visualizzazione della sala rimuove l'icona del cast quando il segnale Bluetooth non è abilitato nel dispositivo sistema di sala
- Correzione di un problema di controllo del volume in riunioni Teams


### <a name="40640-12142018"></a>4.0.64.0 (12/14/2018)

Introdotti in questo aggiornamento:

- Visualizzare i contenuti su entrambi i fronti della sala (per) vengono visualizzati su sistemi room a doppio schermo
- Miglioramenti dell'interfaccia utente per l'uso della chat room
- Supporto lato client TLS 1,2. Per i clienti locali, l'abilitazione di comunicazione su TLS 1,2 per le sale di Microsoft teams richiede Skype for Business Server 2015 cummulative Update 9 (CU9) o Skype for conBusiness server 2019 cummulative Update 1 (CU1).

### <a name="40510-11172018"></a>4.0.51.0 (11/17/2018)

Introdotti in questo aggiornamento:

- Supporto dual display (fronte sala) per riunioni Teams 

### <a name="40310-10162018"></a>4.0.31.0 (10/16/2018)

Introdotti in questo aggiornamento:

- Correzioni di qualità e affidabilità

### <a name="40270-1012018"></a>4.0.27.0 (10/1/2018)

Introdotti in questo aggiornamento:
 
- Modifiche al codice necessarie per preparare l'app Microsoft teams Rooms per l'aggiornamento successivo di Windows 10 versione 1803
- Risolvere il problema di formattazione con EULA localizzati-in particolare in norvegese-che impedisce di avanzare oltre la finestra configurazione OOBE di EULA
- Le modifiche al codice necessarie per l'esecuzione dell'applicazione Microsoft teams Rooms nei sistemi room Lync legacy. Vedere altre informazioni [qui](https://aka.ms/lrsupgrade).
 
### <a name="40190-8312018"></a>4.0.19.0 (8/31/2018)
Introdotti in questo aggiornamento:

- Hotfix per l'avvio dell'applicazione Crestron che normalmente sarebbe accessibile premendo il pulsante App nei dispositivi Crestron SR. Il riavvio dell'app Microsoft teams Rooms è obbligatorio dopo l'installazione di 4.0.19.0. 

### <a name="40180-08272018"></a>4.0.18.0 (08/27/2018)
Introdotti in questo aggiornamento:

- Miglioramenti della funzionalità "segnala un problema" in modalità Teams (equivalente a "Invia feedback" in modalità Skype for business)
- Abilitare la possibilità di ripiego da teams in modalità Skype for business per le chiamate SIP
- Miglioramenti dell'accessibilità (Assistente vocale, Magnifier)
- Riavvia automaticamente l'app quando necessario dopo l'applicazione delle modifiche al provisioning XML
- Correzioni varie

### <a name="4080-07062018"></a>4.0.8.0 (07/06/2018)

Introdotti in questo aggiornamento:
- Questo aggiornamento consente alle riunioni di Skype for business *e* teams di supportare i dispositivi per sistemi room.  I team sono disattivati per impostazione predefinita dopo l'applicazione dell'aggiornamento.  Gli amministratori possono abilitare i team localmente nelle impostazioni del dispositivo o tramite un push XML remoto.

### <a name="311150-06182018"></a>3.1.115.0 (06/18/2018)

Introdotti in questo aggiornamento:

- Correggere l'errore di indirizzo osservato in alcuni sistemi durante l'avvio dell'app.

### <a name="311130-06132018"></a>3.1.113.0 (06/13/2018)
Introdotti in questo aggiornamento:

- Modifiche che consentono a Microsoft di gestire in modo più flessibile gli aggiornamenti di Windows.
- Nessuna modifica dell'esperienza utente finale.

### <a name="311120-06052018"></a>3.1.112.0 (06/05/2018)

Introdotti in questo aggiornamento:

- Correzione per risolvere i problemi di reattività della console osservati nei dispositivi Surface Pro 2017 connessi a due schermi di front-of-room e a un video di acquisizione
- Controllo automatico per verificare che il sistema esegua lo script di provisioning più recente.

### <a name="311040-04162018"></a>3.1.104.0 (04/16/2018)

Introdotti in questo aggiornamento:

- Correzione per migliorare il comportamento di tastiera su schermo (tastiera su schermo) nei sistemi basati su Windows 10 versione 1709
- Miglioramenti per la preparazione per gli aggiornamenti futuri del sistema operativo

### <a name="311000-03162018"></a>3.1.100.0 (03/16/2018)

Introdotti in questo aggiornamento: 

- Applicazione aggiornata per migliorare la telemetria.

### <a name="31990-03142018"></a>3.1.99.0 (03/14/2018)

Introdotti in questo aggiornamento:

- Risolve un problema che può verificarsi in caso di problemi di riunione intermittente.
- Risolve un problema noto per determinare l'esperienza di un dispositivo "blocca".

### <a name="31980--382018"></a>3.1.98.0 (3/8/2018)

Introdotti in questo aggiornamento:

- Correzioni di bug/crash per migliorare la stabilità
- Supporto per la console con dimensioni variabili
- Scaricamento audio periferico (whitelist multimediale aggiuntivo)
- Ottimizzazioni che consentiranno ai professionisti IT di creare immagini fai da te con Windows 10 versione 1709 gennaio Update e versioni successive.  

<!--### 3.1.97.0 (00/00/0000)
Introduced in this update:  
- Support for [Lenovo Hub 500](https://www3.lenovo.com/us/en/hub500)  hardware only.  -->


### <a name="30160-11272017"></a>3.0.16.0 (11/27/2017)

Introdotti in questo aggiornamento:
 
- Risolve un problema con la caratteristica "Invia feedback".

### <a name="30150-1032017"></a>3.0.15.0 (10/3/2017)

Introdotti in questo aggiornamento:

- Supporto per l'hardware Dock della [serie MSR Polycom](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)
- Supporto per [Logitech Brio](https://www.logitech.com/en-us/product/brio)
- Risolve un problema in cui le visualizzazioni (console e front-of-room) non riescono ad accedere alla modalità sospensione quando non è presente alcuna attività nella sala.


### <a name="30120-912017"></a>3.0.12.0 (9/1/2017)

Introdotti in questo aggiornamento:

- Viene eseguito su un tablet Surface Pro (2017)  
- Supporta l'aggiornamento di Windows 10 Enterprise Creator (lingua inglese, Build 1703)
- Supporto per l'hardware Dock di [Crestron Sr](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system)
- Supporto OEM per i controlli ambiente (Crestron)

La versione a 64 bit di Windows 10 Enterprise Anniversary Edition (lingua inglese, versione 1607) non è più supportata da Microsoft teams Rooms Release 3.0.12.0 (Update 3).

### <a name="3080-842017"></a>3.0.8.0 (8/4/2017)

Introdotti in questo aggiornamento:

- Risolve i problemi osservati durante la ricerca di utenti federati tramite il campo di ricerca partecipanti. Precedente a questa correzione, i risultati della ricerca per gli utenti federati esterni potrebbero non essere stati risolti correttamente e restituiti invece risultati non corretti.

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017)

Introdotti in questo aggiornamento:

- Supporto per due schermi (per la parità di sistema legacy)
- Informabilità (temi predefiniti e la possibilità di impostare un tema personalizzato)
- Possibilità di inviare commenti e suggerimenti per le build pubbliche
- Telemetria migliorata intorno all'affidabilità delle riunioni
- Ulteriore Reporting OMS
- Possibilità per l'amministratore IT di configurare i dispositivi in remoto  <!--  - Front-of-Room UX shows room details pre-meeting U2  -->


### <a name="2020-03152017"></a>2.0.2.0 (03/15/2017)

Introdotti in questo aggiornamento:

- Selezione dell'utente in-app dei dispositivi USB audio e video della sala riunioni
- Report di stato della console di sala integrata per i clienti che usano Microsoft Operations Management Suite, ora Azure monitor  

### <a name="release-to-market--1272016"></a>Immissione sul mercato (12/7/2016)

**Caratteristiche:**

 **Creato per Skype for business**
  
- Join One-Touch delle riunioni Skype
- Esperienza di riunione Skype ottimizzata per le camere con schermo HD video e audio a banda larga HD
- Tutti i partecipanti possono connettersi alla riunione Skype usando il loro dispositivo di scelta ovunque si trovino
- Invitare persone dalla directory in cui è possibile visualizzare immediatamente la propria disponibilità o tramite una telefonata
- Supporta i servizi di conferenza PSTN Skype for business e le chiamate PSTN per sostituire il telefono da conferenza autonomo in camera

  **Trasformare una sala riunioni**
  
- App di riunione Skype dedicata ottimizzata per il centro di controllo di tocco della tabella e grande fronte della visualizzazione della sala
- Riutilizzare gli investimenti esistenti nella parte anteriore della visualizzazione della sala o dei proiettori
- Funziona in tutti i tipi di spazi riunioni da spazi di Calco a sale riunioni di grandi dimensioni
- I dispositivi audio e video di Skype for business certificati sono disponibili per varie dimensioni della sala
- Incorporamento di una connessione cablata per la condivisione del desktop di Project nella sala e alla riunione Skype

  **Facile da implementare, semplice da gestire**
  
- Dispositivo always-on che risveglierà automaticamente i display quando rileva persone nella sala
- Implementazione e aggiornamento semplici della UWP (Universal Windows Platform) Skype meeting app
- Windows AppLocker blocca il dispositivo nell'app riunione Skype
- Monitorato e gestito come dispositivo Windows 10 Enterprise tramite Intune e SCCM (MDM)
- Affidabilità di livello aziendale
- Basso sforzo di formazione degli utenti finali grazie all'interfaccia utente di Skype familiare
- Viene eseguito su Surface Pro 4 Tablet

<a name="See"> </a>  
## <a name="see-also"></a>Vedere anche

[Guida di Microsoft teams rooms](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Preparare l'ambiente](srs-v2-prep.md)

[Supporto per Microsoft teams Rooms Current Branch Versions](srs2-lifecycle-support.md)

[Problemi noti per le sale di Microsoft Teams](known-issues.md)

[Pianificare le sale di Microsoft Teams](skype-room-systems-v2-0.md)

[Gestire le sale di Microsoft Teams](skype-room-systems-v2.md)
