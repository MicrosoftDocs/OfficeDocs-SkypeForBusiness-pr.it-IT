---
title: Modelli utente in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c551371c-d740-4372-bada-f0d713ec0d33
description: I modelli di utenti descritti in questa sezione costituiscono la base per le misure e le raccomandazioni per la pianificazione della capacità descritte nell'uso del modello di capacità di pianificazione degli utenti per Skype for Business Server.
ms.openlocfilehash: f1bf079fa425d98b3619eb4ccd975253784f4fbe
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816035"
---
# <a name="user-models-in-skype-for-business-server"></a>Modelli utente in Skype for Business Server
 
I modelli di utenti descritti in questa sezione costituiscono la base per le misure e le raccomandazioni per la pianificazione della capacità descritte nell' [uso del modello di capacità di pianificazione degli utenti per Skype for Business Server](user-model.md).
  
## <a name="skype-for-business-server-user-models"></a>Modelli di utenti di Skype for Business Server

La tabella seguente descrive il modello di utente per la registrazione, i contatti, la messaggistica istantanea (IM) e la presenza per Skype for Business Server.
  
**Modello utente ambiente e registrazione**

|**Categoria**|**Descrizione**|
|:-----|:-----|
|Dimensioni e distribuzione della distribuzione  <br/> |Modelliamo una distribuzione di grandi dimensioni con tre siti centrali, con un pool di front-end per ogni sito.  <br/> |
|Percentuale di utenti di Active Directory  <br/> |Supponiamo che il 70% di tutti gli utenti di Active Directory dell'organizzazione siano abilitati per Skype for Business Server. 80% degli utenti abilitati hanno eseguito l'accesso a Skype for Business Server ogni giorno (80% di concorrenza). Gli utenti simultanei sono la base per i numeri nel resto di questa sezione.  <br/> |
|Modifiche di Active Directory  <br/> |Supponiamo che il 0,5% degli utenti totali venga creato e abilitato per Skype for business in Active Directory ogni settimana e che il 0,5% degli utenti totali sia disabilitato da Active Directory e da Skype for business ogni settimana. il 5% degli utenti ha almeno un attributo Active Directory modificato ogni settimana.  <br/> |
|Gruppi di distribuzione di Active Directory  <br/> |Supponiamo che il numero di gruppi di distribuzione di Active Directory nell'organizzazione sia pari a tre volte il numero di tutti gli utenti in Active Directory. I gruppi di distribuzione hanno le dimensioni seguenti:  <br/> • 64% hanno utenti di 2-30  <br/> • il 13% ha 31-50 utenti  <br/> • 10% hanno 51-100 utenti  <br/> • il 13% ha 101-500 utenti  <br/> |
|Utenti VoIP (Voice over IP)  <br/> |60% degli utenti di Skype for Business Server sono abilitati per le comunicazioni unificate (UC), ovvero i loro numeri di telefono sono di proprietà di Skype for Business Server.  <br/> |
|Distribuzione client registrata  <br/> |il 65% dei client esegue il software Skype for business, tra cui Skype for business e Lync Phone Edition.  <br/> 30% dei client che gestiscono il software client da una versione precedente di Lync.  <br/> 5% di clienti che usano Skype for Business Web App.  <br/> Se è abilitata la mobilità, presupponiamo che il 40% degli utenti usi la mobilità in concomitanza con le altre opzioni del client registrato precedentemente citate. In questo caso, il rapporto di multiple Point of Presence (MPOP) del client è 1:1.9. Se la mobilità è disabilitata, il rapporto MPOP è 1:1.5.  <br/> |
|Distribuzione remota degli utenti  <br/> |70% degli utenti che si connettono internamente.  <br/> il 30% degli utenti che si connettono tramite un server perimetrale (può anche essere disponibile un amministratore, ma non è obbligatorio).  <br/> |
|Distribuzione di contatti  <br/> |Il numero massimo di contatti di un utente è 1.000. Meno dell'1% degli utenti ha contatti di 1.000. Meno del 25% degli utenti ha 100 o più contatti.  <br/> Media dei contatti di 80 per gli utenti con connettività cloud pubblica. Di questi utenti:  <br/> • 50% dei contatti all'interno dell'organizzazione. il 10% degli utenti sono utenti remoti, che si connettono dall'esterno del firewall.  <br/> • 40% dei contatti sono utenti Skype.  <br/> • il 10% dei contatti è proveniente da partner federati.  <br/> Media dei contatti di 50 per gli utenti senza connettività cloud pubblica. Di questi utenti:  <br/> • 80% dei contatti all'interno dell'organizzazione. il 10% degli utenti sono utenti remoti, che si connettono dall'esterno del firewall.  <br/> • il 20% dei contatti è proveniente da partner federati.  <br/> Ogni utente ha un gruppo di distribuzione nell'elenco contatti. Per i test delle prestazioni, presupponiamo che i gruppi di distribuzione siano sempre espansi.  <br/> |
|Ora della sessione  <br/> |La sessione di accesso utente media dura 12 ore. Tutti gli utenti accedono a 120 minuti dall'inizio della sessione.  <br/> |
   
**Modello utente di messaggistica istantanea e presenza**

|**Categoria**|**Descrizione**|
|:-----|:-----|
|Sessioni di messaggistica istantanea peer-to-peer  <br/> |Ogni utente calcola la media di sei sessioni di messaggistica istantanea peer-to-peer per giorno.  <br/> 10 messaggi istantanei per sessione.  <br/> Ogni messaggio è abbinato a due messaggi di informazioni SIP e 2 messaggi OK di SIP 200 (per gli indicatori di stato\<,\> ad esempio "nome sta digitando")  <br/> |
|Sessioni di messaggistica istantanea di gruppo  <br/> |Il numero medio di messaggi inviati in una sessione di messaggistica istantanea di gruppo è di 5 per utente.  <br/> Il numero medio di messaggi inviati nella parte di messaggistica istantanea di una conferenza AV è di 2 per utente.  <br/> |
|Polling presenza  <br/> |In generale, presupponiamo il polling della presenza in media di 60 sondaggi per utente per ora. Per ogni utente, assumere una media di:  <br/> • Un sondaggio per giorno della presenza degli utenti nella scheda organizzazione dell'utente, ma non nell'elenco contatti. Il numero medio di non contatti nella scheda organizzazione dell'utente è di 15 utenti. Due operazioni di visualizzazione della scheda contatto per giorno.  <br/> • Un sondaggio di presenza ogni volta che l'utente fa clic su un altro utente per avviare una conversazione, stimata in una volta all'ora.  <br/> • Sei ricerche utente per ora. Ogni volta che viene eseguita una ricerca, viene inviato un sondaggio batch per tutti gli utenti nell'elenco dei risultati di ricerca. Supponiamo che la dimensione media dei risultati della ricerca sia 20. Se i risultati della ricerca rimangono sullo schermo, il sondaggio batch viene aggiornato ogni 5 minuti; Supponiamo che ci saranno due aggiornamenti per ora.  <br/> • Quando l'utente apre o Visualizza in anteprima un messaggio di posta elettronica in Outlook, viene visualizzato un sondaggio sulla presenza degli utenti nei campi a: e CC: del messaggio di posta elettronica, stimati in cinque messaggi all'ora e quattro utenti per ogni messaggio di posta elettronica.  <br/> |
|Abbonamenti alla presenza  <br/> |Quando un utente aggiunge un altro come contatto, il primo utente sta sottoscrivendo cinque categorie di informazioni sul secondo utente. Gli aggiornamenti di queste categorie di informazioni vengono inviati automaticamente al primo utente. <br/> Per ogni client, viene inviata una richiesta di abbonamento a un singolo batch per ottenere lo stato di presenza di una media di contatti di 40, con una finestra di dialogo di 40 aggiuntiva per ottenere la presenza di contatti federati.  <br/> La presenza per i membri di un gruppo di distribuzione espanso viene trovata tramite sottoscrizioni di presenza persistente, non polling, ed è modellata come 1 espansione per ogni utente per ogni 2 ore.  <br/> Gli abbonamenti brevi si verificano quando un utente effettua l'accesso, esiste un abbonamento batch per tutti i contatti dell'utente e quindi l'utente si disconnette presto. Assumiamo 6 abbonamenti brevi per ogni utente per ora, in cui ogni sottoscrizione dura 10 minuti. <br/> |
|Pubblicazione di presenza  <br/> |Lo stato presenza viene pubblicato in media 4 pubblicazioni per utente per ora, con un massimo di 6 per utente per ora.  <br/> |
|Dimensioni del documento di presenza  <br/> |Si presume che la dimensione media di un documento di presenza completa sia 4K, con un massimo di 25K.  <br/> |
   
La tabella seguente descrive il modello di utente per l'uso della Rubrica.
  
**Modello utente utilizzo Rubrica**

|**Modalità di ricerca della Rubrica**|**L'uso**|
|:-----|:-----|
|Solo query Web della Rubrica (tutte le query eseguite dal servizio query Web Rubrica)  <br/> |Quattro query di prefisso per utente per giorno.  <br/> 60 query di ricerca esatte per utente per giorno. 40% di questi vengono raggruppati in batch, con una media di 20 contatti per query. L'altro 60% delle query è per un singolo contatto.  <br/> 25 query fotografiche per utente per giorno. 24 per una singola foto, l'altra è una query batch con una media di 20 contatti.  <br/> Una query di ricerca totale dell'organizzazione per ogni utente per giorno.  <br/> |
|Modalità mista, sia file della rubrica che query Web usate. Questa è la modalità predefinita.  <br/> |Solo due tipi di query accedono alla rete, alla foto e alle query di ricerca dell'organizzazione totale.  <br/> 25 query fotografiche per utente per giorno. 24 per una singola foto, l'altra è una query batch con una media di 20 contatti.  <br/> Una query di ricerca totale dell'organizzazione per ogni utente per giorno.  <br/> |
   
La tabella seguente descrive il modello di conferenza.
  
**Modello di conferenza**

|**Categoria**|**Descrizione**|
|:-----|:-----|
|Riunioni pianificate rispetto alle riunioni "riunione immediata"  <br/> |60% programmato, 40% non programmato.  <br/> Delle riunioni pianificate, supponiamo che al 80% vengano assegnate conferenze, ovvero occorrenze di conferenze periodiche; 10% sono riunioni aperte una tantum; 8% sono riunioni anonime una tantum e il 2% sono riunioni chiuse una sola volta.  <br/> |
|Distribuzione client di servizi di conferenza  <br/> |Per le riunioni pianificate:  <br/> • 65% degli utenti dei servizi di conferenza usano Skype for business 2016.  <br/> • il 5% degli utenti dei servizi di conferenza Usa Skype for Business Web App.  <br/> • il 30% degli utenti dei servizi di conferenza USA client precedenti, inclusi Lync 2013 e Microsoft Lync 2010.  <br/> Per le riunioni non pianificate:  <br/> • 70% degli utenti dei servizi di conferenza usano Skype for business.  <br/> • il 30% degli utenti dei servizi di conferenza USA client precedenti, inclusi Lync 2013 e Microsoft Lync 2010.  <br/> |
|Concorrenza della riunione  <br/> |il 5% degli utenti sarà in conferenze durante l'orario di lavoro. Quindi, in un pool di utenti di 80.000, almeno un numero di utenti di 4.000 potrebbe essere presente in una conferenza in qualsiasi momento.  <br/> |
|Distribuzione audio della riunione  <br/> |40% di servizi di audioconferenza misti VoIP e con accesso esterno, con un rapporto di 3:1 degli utenti VoIP per gli utenti connessi con la chiamata.  <br/> solo audio VoIP per 35%.  <br/> solo audio per conferenze telefoniche con accesso esterno per il 15%.  <br/> 10% Nessun audio (conferenze di messaggistica istantanea con una media di cinque messaggi inviati per ogni utente).  <br/> |
|Combinazione multimediale per le conferenze  <br/> |75% delle conferenze sono conferenze Web, che includono l'audio e altre modalità di collaborazione.  <br/> Per queste conferenze, gli altri metodi di collaborazione sono i seguenti:  <br/> **Nota:** Questi numeri sommano più di 100% perché una conferenza può avere più metodi di collaborazione. <br/> • 50% Aggiungi condivisione applicazioni. Supponiamo che un utente invii i dati a un massimo di 1,1 MB al secondo.  <br/> • 50% aggiungere la messaggistica istantanea (con una media di 2 messaggi per utente).  <br/> • 20% aggiungere la collaborazione ai dati, tra cui PowerPoint o lavagna in questi, una media di 2 file di PowerPoint presentati per conferenza, con una dimensione media di file di PowerPoint di 10 MB (senza video incorporato) o 30 MB (con video incorporato). Media di 20 annotazioni per lavagna.  <br/> • 20% Aggiungi video. Di questi utenti, 70% sono in conferenze abilitate per il video MultiView, in cui ogni utente riceve i flussi video di 2-3.  <br/> • 15% aggiungere note condivise.  <br/> |
|Distribuzione di partecipanti alla riunione  <br/> |50% utenti interni e autenticati.  <br/> 25% di accesso remoto, utenti autenticati.  <br/> 15% utenti anonimi.  <br/> 10% utenti federati.  <br/> |
|Distribuzione di join di riunione  <br/> |Gli utenti vengono simulati per partecipare alla riunione entro i primi 5 minuti.  <br/> |
   
In normali pool Front-End, Skype for Business Server ha una dimensione massima della riunione supportata di 250 utenti. Ogni pool può ospitare 1 250-riunione utente alla volta. Mentre si verifica questa riunione di grandi dimensioni, il pool può ospitare anche altre conferenze più piccole. Inoltre, puoi supportare riunioni fino a 1000 utenti impostando un pool dedicato per ospitare queste riunioni. Per informazioni dettagliate, vedere [pianificare le riunioni di grandi dimensioni in Skype for Business Server](../../plan-your-deployment/conferencing/large-meetings.md).
  
Le conferenze sono state simulate nel modo seguente:
  
- il 85% delle conferenze ha quattro partecipanti.
    
- il 10% delle conferenze ha sei partecipanti.
    
- il 5% delle conferenze ha 11 partecipanti.
    
- Una conferenza di grandi dimensioni per gli utenti di 250.
    
La tabella seguente fornisce informazioni dettagliate sul modello di utente per le conferenze che coinvolgono utenti con accesso esterno.
  
**Modello utenti di servizi di conferenza telefonica con accesso esterno**

|**Categoria**|**Descrizione**|
|:-----|:-----|
|Autenticato/Anonimo  <br/> |il 70% dei chiamanti si iscrive come anonimo e viene richiesto un nome registrato. 30% partecipa come utenti autenticati.  <br/> |
|Durata chiamata e musica in attesa  <br/> |Durata media della chiamata senza musica in attesa: 50 secondi.  <br/> per una media di 5 minuti, 50% degli utenti di chiamate in attesa sente musica in sospeso.  <br/> |
|DTMF (Dual-Tone Multifrequency)  <br/> |il 15% delle conferenze telefoniche con accesso esterno ha solo i responsabili del telefono. il 10% delle conferenze miste che includono utenti con accesso esterno hanno anche i responsabili del telefono.  <br/> il 20% dei responsabili telefonici USA 2 comandi DTMF per conferenza.  <br/> |
|Lingue di annunci  <br/> |Le simulazioni usano l'inglese come lingua di annuncio.  <br/> |
   
La tabella seguente fornisce informazioni dettagliate sul modello di utente per le lobby delle conferenze.
  
**Modello di utente di lobby conferenza**

|**Categoria**|**Descrizione**|
|:-----|:-----|
|Numero di utenti nella sala di attesa  <br/> |il 5% degli utenti con accesso esterno passa attraverso la sala d'attesa e il 25% degli altri utenti passa attraverso la sala d'attesa  <br/> |
|Ammissione dalla sala di attesa  <br/> |In simulazioni tutti gli utenti sono stati ammessi dal relatore prima del timeout del client.  <br/> |
   
La tabella seguente descrive il modello di utente per altre sessioni peer-to-peer.
  
**Modello utente sessioni peer-to-peer**

|**Categoria**|**Descrizione**|
|:-----|:-----|
|Condivisione applicazioni  <br/> |Ogni utente partecipa a 5 sessioni di condivisione delle applicazioni peer-to-peer al mese, per una media di 0,25 sessioni al giorno.  <br/> |
|Trasferimento di file  <br/> |Ogni utente partecipa a una sessione di trasferimento di file peer-to-peer al mese (nell'ambito di una sessione di messaggistica istantanea), per una media di 0,05 sessioni al giorno. La dimensione media del file della sessione trasferita è di 1 MB.  <br/> |
   
La tabella seguente descrive il modello di utente per i criteri.
  
**Modello di criteri utente**

|**Categoria**|**Descrizione**|
|:-----|:-----|
|Criteri di conferenza, presenza e archiviazione  <br/> |Supponiamo che esistano un criterio globale, 10 criteri di conferenza tag, 4 criteri di archiviazione e 10 criteri di presenza dei tag.  <br/> |
|Criteri vocali  <br/> |Supponiamo che esistano un criterio globale e due criteri per i tag per sito. il 100% dei siti ha un criterio per il sito e il 30% degli utenti ha un criterio per utente assegnato. Assumiamo un dial plan per ogni sito e due rotte per sito.  <br/> |
   
## <a name="busy-hour"></a>Ora occupato

Per le sessioni peer-to-peer, il carico di picco viene calcolato usando i tentativi di chiamata di ora occupato (BHCA). Questo termine del settore vocale presuppone che il 50% di tutte le chiamate per il giorno verrà completato in 20% del tempo. Viene calcolata usando la formula seguente:
  
 `BHCA=(total calls * 0.5) / 1.6`
  
Test delle prestazioni ora di occupato simulato eseguendo VoIP e altre sessioni peer-to-peer a un carico di ora occupato per almeno 1,6 ore al giorno.
  
Il carico di picco per i servizi di conferenza presuppone che il 75% di tutte le conferenze per un giorno di otto ore avvenga in quattro ore di punta. Le ore di punta hanno 1,5 volte il carico di conferenza media.
  
## <a name="enterprise-voice-to-pstn-calls"></a>VoIP aziendale per chiamate PSTN

Le ipotesi seguenti si applicano alle chiamate vocali aziendali:
  
- 60% degli utenti sono abilitati per VoIP aziendale e il 60% di questi utenti è abilitato per le chiamate PSTN.
    
- Ognuno di questi utenti abilitato per la chiamata PSTN effettua 4 chiamate PSTN durante l'ora di occupato. Ogni durata della chiamata è di 3 minuti.
    
- 65% di queste chiamate vocali PSTN usano il bypass multimediale.
    
## <a name="mobility"></a>Mobilità

si presume che il 40% degli utenti registrati sia abilitato per la mobilità. Per ogni utente abilitato alla mobilità, supponiamo che l'attività del client per dispositivi mobili sia additiva rispetto alle altre istanze di MPOP per tale utente, ad eccezione delle interazioni di conferenza, per cui il client di mobilità è solo un altro tipo di client che può essere usato per partecipare alle conferenze.
  
## <a name="persistent-chat"></a>Chat persistente

Presupponiamo che il 25% degli utenti registrati sarà coinvolto in sessioni di chat persistenti, con le caratteristiche seguenti:
  
- Media delle chat room di 1,5 per utente
    
- Ogni chat room genera 12 richieste di polling per ora, destinate a una media di 10 utenti ogni
    
## <a name="response-group-and-call-park"></a>Gruppo di risposte e parcheggio delle chiamate

Supponiamo che il 0,15% degli utenti registrati appartenga ai gruppi di risposta. Supponiamo che il 0,02% degli utenti registrati abbia chiamate parcheggiate in un dato momento.
  

