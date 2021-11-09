---
title: Modelli utente in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c551371c-d740-4372-bada-f0d713ec0d33
description: I modelli utente descritti qui forniscono la base per le misurazioni e i consigli di pianificazione della capacità descritti in Capacity planning user model usage for Skype for Business Server.
ms.openlocfilehash: 22f5d45c5b8c5f75979e061814c03a5b9ffc3e8d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846349"
---
# <a name="user-models-in-skype-for-business-server"></a>Modelli utente in Skype for Business Server
 
I modelli utente descritti qui forniscono la base per le misurazioni e i consigli di pianificazione della capacità descritti in [Capacity planning user model usage for Skype for Business Server](user-model.md).
  
## <a name="skype-for-business-server-user-models"></a>Skype for Business Server Modelli utente

Nella tabella seguente viene descritto il modello utente per la registrazione, i contatti, la messaggistica istantanea e la presenza per Skype for Business Server.
  
**Modello utente per ambiente e registrazione**

|**Categoria**|**Descrizione**|
|:-----|:-----|
|Dimensione e distribuzione  <br/> |Viene creato un modello di distribuzione estesa con tre siti centrali e un pool Front End per sito.  <br/> |
|Percentuale di utenti di Active Directory  <br/> |Si presuppone che il 70% di tutti gli utenti di Active Directory nell'organizzazione siano abilitati per Skype for Business Server. L'80% di tali utenti abilitati è connesso a Skype for Business Server ogni giorno (80% di concorrenza). Gli utenti simultanei rappresentano la base per i valori indicati nel resto di questa sezione.  <br/> |
|Cambiamenti in Active Directory  <br/> |Si presuppone che lo 0,5% degli utenti totali sia stato creato e abilitato per Skype for Business in Active Directory ogni settimana e che lo 0,5% degli utenti totali sia disabilitato da Active Directory e da Skype for Business ogni settimana. Per il 5% degli utenti viene modificato almeno un attributo di Active Directory ogni settimana.  <br/> |
|Gruppi di distribuzione di Active Directory  <br/> |Si parte dal presupposto che il numero di gruppi di distribuzione di Active Directory nell'organizzazione sia pari a tre volte il numero di tutti gli utenti in Active Directory. Le dimensioni dei gruppi di distribuzione sono le seguenti:  <br/> • Il 64% ha 2-30 utenti  <br/> • Il 13% ha 31-50 utenti  <br/> • Il 10% ha 51-100 utenti  <br/> • Il 13% ha 101-500 utenti  <br/> |
|Utenti di VoIP (Voice over IP)  <br/> |Il 60% Skype for Business Server utenti sono abilitati per le comunicazioni unificate (UC), ovvero i loro numeri di telefono sono di proprietà di Skype for Business Server.  <br/> |
|Distribuzione dei client registrati  <br/> |Il 65% dei client esegue Skype for Business software, tra cui Skype for Business Lync Telefono Edition.  <br/> 30% dei client che eseguono software client da una versione precedente di Lync.  <br/> 5% dei client che usano Skype for Business Web App.  <br/> Se la mobilità è abilitata, presupporremo che il 40% degli utenti utilizzi la mobilità contemporaneamente alle altre opzioni client registrate citate in precedenza. In questo caso, il rapporto MPOP (Multiple Point of Presence) del client è 1:1,9. Se l'utilizzo dei dispositivi mobili è disabilitato, il rapporto MPOP invece è pari a 1:1,5.  <br/> |
|Distribuzione degli utenti remoti  <br/> |Il 70% degli utenti si connette internamente.  <br/> 30% degli utenti che si connettono tramite un server perimetrale (è anche possibile avere un Director qui, ma non è necessario).  <br/> |
|Distribuzione dei contatti  <br/> |Il numero massimo di contatti di cui può disporre un utente è 1.000. Meno dell'1% degli utenti dispone di 1.000 contatti. Meno del 25% degli utenti dispone di 100 o più contatti.  <br/> Media di 80 contatti per gli utenti con connettività a cloud pubblici. Di questi utenti:  <br/> • Il 50% dei contatti si trova all'interno dell'organizzazione. Il 10% di questi utenti è rappresentato da utenti remoti che si connettono dall'esterno del firewall.  <br/> • Il 40% dei contatti è Skype utenti.  <br/> • Il 10% dei contatti è di partner federati.  <br/> Media di 50 contatti per gli utenti senza connettività a cloud pubblici. Di questi utenti:  <br/> • L'80% dei contatti si trova all'interno dell'organizzazione. Il 10% di questi utenti è rappresentato da utenti remoti che si connettono dall'esterno del firewall.  <br/> • Il 20% dei contatti è di partner federati.  <br/> Ogni utente dispone di un gruppo di distribuzione nell'elenco contatti. Per i test delle prestazioni, si presuppone che i gruppi di distribuzione siano sempre espansi.  <br/> |
|Durata delle sessioni  <br/> |La sessione di accesso utente dura in media 12 ore. Tutti gli utenti eseguono l'accesso entro 120 minuti dall'avvio della sessione.  <br/> |
   
**Modello utente per messaggistica istantanea e presenza**

|**Categoria**|**Descrizione**|
|:-----|:-----|
|Sessioni di messaggistica istantanea peer-to-peer  <br/> |Ogni utente esegue in media sei sessioni di messaggistica istantanea peer-to-peer al giorno.  <br/> 10 messaggi istantanei per sessione.  <br/> A ogni messaggio corrispondono due messaggi SIP INFO e 2 messaggi SIP 200 OK (per gli indicatori di stato, ad esempio " \<Name\> sta digitando")  <br/> |
|Sessioni di messaggistica istantanea di gruppo  <br/> |Il numero medio di messaggi inviati in una sessione di sola messaggistica istantanea di gruppo è 5 per utente.  <br/> Il numero medio di messaggi inviati nella parte di messaggistica istantanea di una conferenza AV è 2 per utente.  <br/> |
|Polling della presenza  <br/> |In generale, si presuppongono 60 polling di presenza per utente all'ora. Per ogni utente si presuppone una media di:  <br/> • Un sondaggio al giorno della presenza di utenti nella scheda dell'organizzazione dell'utente (ma non nell'elenco Contatti). Il numero medio di non contatti nella scheda dell'organizzazione dell'utente è 15 utenti. Due operazioni di visualizzazione di schede contatto al giorno.  <br/> • Un polling della presenza ogni volta che l'utente fa clic su un altro utente per avviare una conversazione, stimata in una volta all'ora.  <br/> • Sei ricerche utente all'ora. Ogni volta che viene eseguita una ricerca, viene inviato un polling in batch per tutti gli utenti nell'elenco dei risultati della ricerca. Si presuppone che la dimensione media dei risultati della ricerca sia 20. Se i risultati della ricerca rimangono sullo schermo, il polling del batch viene aggiornato ogni 5 minuti. presuppongiamo che siano presenti due aggiornamenti di questo tipo all'ora.  <br/> • Quando l'utente apre o visualizza in anteprima un messaggio di posta elettronica in Outlook, viene eseguito un polling della presenza di utenti nei campi A: e CC: del messaggio di posta elettronica, stimato in cinque messaggi di posta elettronica all'ora e quattro utenti per posta elettronica.  <br/> |
|Sottoscrizioni della presenza  <br/> |Quando un utente ne aggiunge un altro come contatto, il primo utente sottoscrive cinque categorie di informazioni sul secondo utente. Gli aggiornamenti di queste categorie di informazioni vengono inviati automaticamente al primo utente. <br/> Per ogni client, viene inviata una singola richiesta di sottoscrizione batch per ottenere lo stato di presenza di una media di 40 contatti, con ulteriori 40 finestre di dialogo per ottenere la presenza dei contatti federati.  <br/> Le informazioni sulla presenza per i membri di un gruppo di distribuzione espanso vengono trovate mediante sottoscrizioni della presenza persistenti e non mediante il polling. Il modello prevede un'espansione per utente ogni due ore.  <br/> Le sottoscrizioni brevi si verificano quando un utente esegue l'accesso, esiste una sottoscrizione batch per tutti i contatti dell'utente e quindi l'utente si disconnette presto. Si presuppongono sei sottoscrizioni brevi per utente all'ora, ognuna della durata di 10 minuti. <br/> |
|Pubblicazione della presenza  <br/> |Lo stato di presenza viene pubblicato con una media di quattro pubblicazioni per utente all'ora, con un massimo di sei pubblicazioni per utente all'ora.  <br/> |
|Dimensione del documento delle informazioni sulla presenza  <br/> |Si presuppone che la dimensione media di un documento completo di informazioni sulla presenza corrisponda a 4 K, fino a un massimo di 25 K.  <br/> |
   
Nella tabella riportata di seguito viene descritto il modello utente per l'utilizzo della Rubrica.
  
**Modello utente per l'utilizzo della Rubrica**

|**Modalità di ricerca nella Rubrica**|**Usage**|
|:-----|:-----|
|Solo query Web nella Rubrica (tutte le query eseguite dal servizio Address Book Web Query)  <br/> |Quattro query di prefisso per utente al giorno.  <br/> 60 query di ricerca esatta per utente al giorno. Il 40% di queste è eseguito in batch, con una media di 20 contatti per query. L'altro 60% delle query è per un singolo contatto.  <br/> 25 query di foto per utente al giorno. 24 per una singola foto, l'altra è una query in batch con una media di 20 contatti.  <br/> Una query di ricerca in tutta l'organizzazione per utente al giorno.  <br/> |
|Modalità mista con utilizzo sia di query nel file della Rubrica che di query Web. Questa è la modalità predefinita.  <br/> |Solo due tipi di query vanno in rete, ovvero le query di ricerca di foto e quelle di ricerca in tutta l'organizzazione.  <br/> 25 query di foto per utente al giorno. 24 per una singola foto, l'altra è una query in batch con una media di 20 contatti.  <br/> Una query di ricerca in tutta l'organizzazione per utente al giorno.  <br/> |
   
Nella tabella seguente viene descritto il modello per i servizi di conferenza.
  
**Modello per i servizi di conferenza**

|**Categoria**|**Descrizione**|
|:-----|:-----|
|Riunioni pianificate e riunioni immediate  <br/> |60% pianificate, 40% non pianificate.  <br/> Tra le riunioni pianificate si presuppone che all'80% siano assegnate conferenze, che sono occorrenze di conferenze ricorrenti. Il 10% è una riunione aperta una sola volta; L'8% è una sola volta riunioni anonime e il 2% riunioni chiuse una sola volta.  <br/> |
|Distribuzione dei client per i servizi di conferenza  <br/> |Per le riunioni pianificate:  <br/> • Il 65% degli utenti delle conferenze Skype for Business 2016.  <br/> • Il 5% degli utenti delle conferenze utilizza Skype for Business Web App.  <br/> • Il 30% degli utenti delle conferenze utilizza client precedenti, tra cui Lync 2013 e Microsoft Lync 2010.  <br/> Per le riunioni non pianificate:  <br/> • Il 70% degli utenti delle conferenze utilizza Skype for Business.  <br/> • Il 30% degli utenti delle conferenze utilizza client precedenti, tra cui Lync 2013 e Microsoft Lync 2010.  <br/> |
|Concorrenza riunione  <br/> |Il 5% degli utenti sarà in conferenza durante le ore lavorative. Per un pool di 80.000 utenti, pertanto, fino a 4.000 utenti potrebbe essere in conferenza contemporaneamente.  <br/> |
|Distribuzione dell'audio delle riunioni  <br/> |40% misto di audio VoIP e conferenza telefonica con accesso esterno, con un rapporto di 3:1 di utenti VoIP rispetto agli utenti connessi tramite chiamata in ingresso.  <br/> 35% solo audio VoIP.  <br/> 15% solo audio di conferenza telefonica con accesso esterno.  <br/> 10% senza audio (conferenze solo con messaggi istantanei, con una media di cinque messaggi inviati per utente).  <br/> |
|Combinazioni multimediali per le conferenze  <br/> |Il 75% delle conferenze è rappresentato da conferenze Web, che includono funzionalità audio e altre modalità di collaborazione.  <br/> Per queste conferenze, gli altri metodi di collaborazione sono i seguenti:  <br/> **Nota:** Questi numeri sono superiori al 100% perché una conferenza può avere più metodi di collaborazione. <br/> • Aggiungere al 50% la condivisione delle applicazioni. Si presuppone che un utente invii dati fino a un massimo di 1,1 MB al secondo.  <br/> • Il 50% aggiunge messaggi istantanei (con una media di 2 messaggi per utente).  <br/> • 20% aggiungere collaborazione dati, tra cui PowerPoint o lavagna In questi, una media di 2 file PowerPoint presentati per conferenza, con una dimensione media dei file di PowerPoint di 10 MB (senza video incorporato) o 30 MB (con video incorporato). Media di 20 annotazioni per lavagna.  <br/> • 20% aggiungere video. Di questi utenti, il 70% partecipa a conferenze abilitate per il video multiview, in cui ogni utente riceve 2-3 flussi video.  <br/> • Il 15% aggiunge note condivise.  <br/> |
|Distribuzione dei partecipanti alle riunioni  <br/> |50% utenti interni autenticati.  <br/> 25% utenti autenticati con accesso remoto.  <br/> 15% utenti anonimi.  <br/> 10% utenti federati.  <br/> |
|Distribuzione della partecipazione alle riunioni  <br/> |Si presuppone la partecipazione degli utenti alla riunione entro i primi cinque minuti.  <br/> |
   
Nei pool Front End regolari, Skype for Business Server una dimensione massima supportata per le riunioni di 250 utenti. Ogni pool può ospitare una riunione da 250 utenti per volta. Mentre è in corso una riunione di dimensioni così elevate, il pool può ospitare anche altre conferenze più ridotte. È inoltre possibile supportare riunioni a cui partecipano fino a 1000 utenti configurando un pool dedicato per ospitare tali riunioni. Per informazioni dettagliate, vedere [Plan for large meetings in Skype for Business Server](../../plan-your-deployment/conferencing/large-meetings.md).
  
Sono state simulate le conferenze seguenti:
  
- 85% di conferenze con quattro partecipanti.
    
- 10% di conferenze con sei partecipanti.
    
- 5% di conferenze con 11 partecipanti.
    
- Una conferenza estesa con 250 utenti.
    
Nella tabella seguente sono disponibili informazioni dettagliate sul modello utente per le conferenze che coinvolgono utenti connessi tramite chiamate in ingresso.
  
**Modello utente per conferenze telefoniche con accesso esterno**

|**Categoria**|**Descrizione**|
|:-----|:-----|
|Autenticato/anonimo  <br/> |Il 70% dei chiamanti partecipa in modalità anonima e deve specificare un nome registrato. Il 30% partecipa come utente autenticato.  <br/> |
|Durata delle chiamate e musica di attesa  <br/> |Durata media della chiamata senza musica di attesa: 50 secondi.  <br/> Il 50% degli utenti che chiamano ascoltano la musica di attesa per una media di 5 minuti.  <br/> |
|Multifrequenza (DTMF)  <br/> |Per il 15% delle conferenze telefoniche con accesso esterno è presente un coordinatore della chiamata. Anche per il 10% delle conferenze miste che includono utenti connessi tramite chiamate in ingresso sono presenti coordinatori della chiamata.  <br/> Il 20% dei coordinatori utilizza due comandi DTMF per conferenza.  <br/> |
|Lingue degli annunci  <br/> |Nelle simulazioni viene utilizzato l'inglese come lingua degli annunci.  <br/> |
   
Nella tabella seguente sono disponibili informazioni dettagliate sul modello utente per le sale di attesa delle conferenze.
  
**Modello utente per le sale di attesa delle conferenze**

|**Categoria**|**Descrizione**|
|:-----|:-----|
|Numero di utenti nella sala di attesa  <br/> |Il 5% degli utenti che si connettono tramite chiamate in ingresso passa dalla sala di attesa, come il 25% degli altri utenti  <br/> |
|Ammissione dalla sala di attesa  <br/> |Nelle simulazioni tutti gli utenti sono stati ammessi dal relatore prima del timeout del client.  <br/> |
   
Nella tabella riportata di seguito viene descritto il modello utente per altre sessioni peer-to-peer.
  
**Modello utente per altre sessioni peer-to-peer**

|**Categoria**|**Descrizione**|
|:-----|:-----|
|Condivisione applicazioni  <br/> |Ogni utente partecipa a cinque sessioni di condivisione applicazioni peer-to-peer al mese, per una media di 0,25 sessioni al giorno.  <br/> |
|Trasferimento di file  <br/> |Ogni utente partecipa a 1 sessione di trasferimento file peer-to-peer al mese (nell'ambito di una sessione di messaggistica istantanea), per una media di 0,05 sessioni al giorno. Le dimensioni medie dei file trasferiti durante la sessione sono di 1 MB.  <br/> |
   
Nella tabella seguente viene descritto il modello utente per i criteri.
  
**Modello utente per i criteri**

|**Categoria**|**Descrizione**|
|:-----|:-----|
|Criteri di conferenza, presenza e archiviazione  <br/> |Si presuppone che siano configurati un criterio globale, 10 criteri tag di conferenza, quattro criteri di archiviazione e 10 criteri tag di presenza.  <br/> |
|Criteri vocali  <br/> |Presuppongiamo che siano presenti un criterio globale e due criteri tag per sito. Al 100% dei siti è assegnato un criterio sito e al 30% degli utenti è assegnato un criterio per utente. Si presuppone che un dial plan per sito e due route per sito.  <br/> |
   
## <a name="busy-hour"></a>Ora di punta

Per le sessioni peer-to-peer, il carico di picco viene calcolato tramite l'indicatore dei tentativi di chiamata durante l'ora di punta, noto anche come BHCA (Busy Hour Call Attempt). Questo indicatore del settore presuppone che il 50% di tutte le chiamate in un giorno venga effettuato nel 20% del tempo. Per il calcolo viene utilizzata la formula seguente:
  
 `BHCA=(total calls * 0.5) / 1.6`
  
Per i test delle prestazioni l'ora di punta è stata simulata eseguendo sessioni VoIP e altre sessioni peer-to-peer con un carico di picco per almeno 1,6 ore al giorno.
  
Nel carico di picco per le conferenze si presuppone che il 75% di tutte le conferenze per un giorno di otto ore venga effettuato in 4 ore di punta. In tali ore di punta si concentra 1,5 volte il carico medio delle conferenze.
  
## <a name="enterprise-voice-to-pstn-calls"></a>VoIP aziendale chiamate PSTN

I presupposti seguenti si applicano VoIP aziendale chiamate:
  
- Il 60% degli utenti è abilitato per VoIP aziendale e il 60% di questi utenti è abilitato per le chiamate PSTN.
    
- Ognuno di questi utenti abilitati per le chiamate PSTN esegue quattro chiamate PSTN durante l'orario lavorativo. Ogni chiamata dura tre minuti.
    
- Nel 65% di queste chiamate vocali PSTN viene utilizzato il bypass multimediale.
    
## <a name="mobility"></a>Mobilità

Si presuppone che il 40% degli utenti registrati sia abilitato per i dispositivi mobili. Per ogni utente abilitato per i dispositivi mobili, si presuppone che l'attività del client mobile si aggiunga a quella delle altre istanze MPOP dell'utente, ad eccezione delle interazioni con i servizi di conferenza, per cui il client per servizi mobili rappresenta solo un altro tipo di client che può essere utilizzato per partecipare alle conferenze.
  
## <a name="persistent-chat"></a>Persistent Chat

Si presuppone che il 25% degli utenti registrati parteciperà a sessioni di Persistent Chat, con le caratteristiche seguenti:
  
- Una media di 1,5 chat room per utente
    
- Ogni chat room comporta 12 richieste di polling all'ora, con una media di 10 utenti per ognuna
    
## <a name="response-group-and-call-park"></a>Response Group e parcheggio di chiamata

Si presuppone che lo 0,15% degli utenti registrati appartenga a Response Group e che lo 0,02% degli utenti registrati utilizzi la funzionalità di parcheggio di chiamata in un determinato momento.
  

