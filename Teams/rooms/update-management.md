---
title: Microsoft Teams Rooms gestione degli aggiornamenti
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: monitoraggio proattivo delle sale riunioni.
f1keywords: ''
ms.openlocfilehash: 6f422359044e7dad8f93223bd83b17146025c257
ms.sourcegitcommit: 268660f101609852f02f3f9d1a8436f2a99dade7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2022
ms.locfileid: "62071076"
---
# <a name="update-management"></a>Gestione degli aggiornamenti 
Una sala riunioni moderna è dotata di un dispositivo Microsoft Teams Rooms e di altre periferiche, ad esempio una fotocamera, un microfono o un altoparlante, e potenzialmente più dispositivi per creare un'esperienza di riunione inclusiva ed efficace. Le apparecchiature di diversi tipi di OEM forniscono l'esperienza organizzativa desiderata; tuttavia, devono essere mantenuti con software e firmware su base continuativa.  

Managed Services for Microsoft Teams Rooms garantisce che ogni chat room dell'organizzazione verrà mantenuta ai livelli consigliati per offrire una sala sempre pronta e che funzioni correttamente. L'obiettivo di Microsoft è ridurre la complessità e il lavoro a gambe per il personale operativo con intelligenza e automazione. La risoluzione dei problemi o la diagnostica viene eseguita il più rapidamente possibile. 

## <a name="transitioning-a-device-to-managed-services"></a>Transizione di un dispositivo ai servizi gestiti 
L'onboarding dei dispositivi delle chat room nei servizi gestiti ha in genere una cronologia e una pratica di gestione delle modifiche diverse dalle indicazioni fornite.  

- Per trarre vantaggio dai servizi gestiti, è necessario gestire le modifiche di transizione per tutti gli aggiornamenti del portfolio servizi gestiti.
- Più origini dei contratti di servizio per gli eventi imprevisti di gestione delle modifiche, in quanto esiste un'individuazione e una correzione che verranno riavviate di nuovo se si verifica un incidente nella chat room.
- Microsoft ha implementato controlli e controlli per implementare criteri che possono differire da un'organizzazione all'altra e la possibilità di intervenire in situazioni eccezionali.
- Alla fine, i dispositivi della sala verranno aggiornati agli standard comuni, ad eccezione delle eccezioni a causa di problemi con una specifica installazione hardware.  

## <a name="transitioning-devices-basic-readiness-checks"></a>Dispositivi di transizione: controlli di conformità di base 
La maggior parte degli errori imprevisti deriva da modifiche nell'immagine di base con una cronologia incerta della gestione delle modifiche. 

È consigliabile seguire semplici controlli di conformità:  

- **Immagine di base:** l'immagine di base deve essere dell'OEM specifico. Se il dispositivo è stato ricompilato in passato e mostra errori o comportamenti imprevisti nelle attività comuni, è necessario ripristinare l'immagine di base. Siamo in grado di fornire assistenza, ma non possiamo ricostruire in remoto il dispositivo della sala, quindi è necessario un tecnico del sito locale.  
- **Sistema operativo di base, edizione:** Il sistema operativo di base e l'edizione devono corrispondere ai requisiti Microsoft Teams Rooms dispositivi. In caso contrario, è necessario correggerlo nell'ambito dell'onboarding. Microsoft Teams Rooms richiede le SKU Windows 10 IoT Enterprise o Windows 10 Enterprise in Semi-Annual di manutenzione del Canale. Per altre informazioni, [consultare le indicazioni ufficiali sul MTR.](rooms-lifecycle-support.md#windows-10-release-support)

## <a name="readiness-checks"></a>Controlli di conformità

Esistono alcuni prerequisiti per la ricezione degli aggiornamenti dei servizi gestiti: 

|Software |Linee guida |
| :- | :- |
|Servizi di sincronizzazione logitech  |Deve essere installato e in esecuzione nei dispositivi della sala riunioni Logitech. I servizi di sincronizzazione necessari verranno installati automaticamente Windows aggiornamenti, a meno che non siano bloccati. È anche possibile installare il pacchetto di sincronizzazione completo. |
|Windows del sistema operativo |Devono essere mantenuti abilitati e non reindirizzati a WSUS, né bloccati dal punto di vista della rete. Per gestire gli aggiornamenti del sistema operativo, non devono essere usati né criteri DI GRUPPO né criteri MDM. |
|Microsoft Store aggiornamenti   |Dovrebbe essere disattivata. I servizi gestiti disattivano gli aggiornamenti dello Store, se vengono trovati. |
|Software antivirus |Se si esegue il software AV in questi dispositivi, assicurarsi che av abbia esclusioni per le dll Teams e Skype. Per altre informazioni, vedere qui. |
|Software aggiuntivo |Per escludere gli effetti collaterali, è consigliabile rivedere altri software, ad esempio la visualizzazione desktop remoto di terze parti e così via, con Servizi gestiti. |
|Gestione delle modifiche aggiuntiva|Può interferire con gli aggiornamenti coperti e non deve essere introdotto. |

## <a name="managed-updates--how-it-works"></a>Aggiornamenti gestiti - Funzionamento 
Esistono due modi principali per gestire gli aggiornamenti:  

- **Gestito automaticamente:** gli aggiornamenti vengono installati nel dispositivo della sala in base alla valutazione di Servizi gestiti. Non è necessario alcun intervento per gli aggiornamenti gestiti nel nostro portfolio.
- **Anello convalidato:** configurare un sistema ad anello per visualizzare in anteprima gli aggiornamenti su dispositivi specifici in modo da poterli monitorare senza il lavoro a gambe associato. La configurazione dell'anello offre un ulteriore livello di due diligence prima delle implementazioni generali.  

### <a name="automatically-managed"></a>Gestito automaticamente

Se si sceglie di essere gestiti automaticamente, non è necessaria alcuna azione per gli aggiornamenti da parte dell'utente. Tuttavia, è consigliabile esaminare l'attuale portfolio di aggiornamenti supportati da Servizi gestiti. Il portfolio riceve costantemente nuove aggiunte ed è nostra priorità coprire gli aggiornamenti più frequenti e di impatto per garantire la stabilità della stanza. Controllare l'elenco corrente (nella sezione "Gestione aggiornamenti" di questo documento) per pianificare eventuali altre operazioni di gestione delle modifiche necessarie per l'organizzazione.  

**Suggerimento:** Non installare gli aggiornamenti coperti da Servizi gestiti in qualsiasi dispositivo gestito. In caso di problemi, segnalare un evento imprevisto nel portale.

### <a name="ring-validation"></a>Convalida dell'anello

Quando si sceglie la convalida dell'anello, vedere le sezioni seguenti sul funzionamento degli anelli in Servizi gestiti e sulle opzioni disponibili per personalizzarlo per l'organizzazione. Anche con la convalida dell'anello, i servizi gestiti provano a verificare che le chat room non siano scadute in base agli aggiornamenti consigliati. A seconda della situazione, una chat room potrebbe ricevere aggiornamenti di tipo "catch up" per assicurarsi che sia conforme ai suggerimenti per i servizi gestiti.  

 Verificare la presenza di annunci nella home page del portale e nella documentazione di Servizi gestiti man appena nuovi tipi di software e firmware diventano disponibili nel portfolio. Poiché gli esperti di Servizi gestiti rivedranno quotidianamente le versioni degli aggiornamenti in tutto il nostro portfolio di dispositivi, affrontano problemi specifici e indirizzano gli aggiornamenti in base alle esigenze.  

### <a name="scheduling"></a>Pianificazione 
Gli aggiornamenti gestiti sono pianificati per le sale in base all'attrezzatura nella sala e se non sono in linea con gli standard di Servizi gestiti per il software e il firmware applicabili.  

- Per aiutare i clienti a soddisfare i requisiti di gestione delle modifiche, aggiornare l'avvio della distribuzione il **mercoledì nell'anello** di gestione temporanea. Se è necessario un aggiornamento critico, questa pianificazione verrà ignorata e rilasciata non appena sarà disponibile. 

- Gli aggiornamenti vengono sequenziati in base alle esigenze di una determinata chat room. 
- Se sono disponibili anelli di configurazione per convalidare gli aggiornamenti, l'aggiornamento procederà nell'ordine degli anelli. 
- Un nuovo aggiornamento può essere sostituito da un aggiornamento che viene accodato se si determina che la stabilità delle chat room è migliorata in base alla situazione.  
- Gli aggiornamenti vengono in genere applicati durante la finestra di manutenzione notturna, che è l'ora locale **delle 12:00 alle 5:00** per evitare qualsiasi tipo di interruzione. 

## <a name="microsoft-teams-room-app-update-lifecycle-policy"></a>Microsoft Teams del ciclo di vita dell'app Room 
I criteri di supporto del team di progettazione MTR affermano che tutto il supporto termina dopo la scadenza del ciclo di vita di dodici (12) mesi per una versione o se da allora sono stati rilasciati più di due aggiornamenti. I clienti devono quindi eseguire l'aggiornamento a una versione supportata. Fare riferimento [al Microsoft Teams Rooms della versione dell'app - Microsoft Teams | Documenti Microsoft per una ](rooms-lifecycle-support.md)descrizione dettagliata del servizio.

Per mantenere uno standard uniforme in tutte le chat room gestite e per consentirci di identificare in modo efficiente i problemi di tendenza, supporteremo e distribuiremo le due versioni principali o secondarie più recenti (N, N-1) del software dell'app MTR in base alle condizioni dei servizi di supporto e abbonamento. Le sale non conformi verranno aggiornate automaticamente, ignorando gli anelli di aggiornamento in base alle esigenze. 

Il criterio N-1 si applica anche al software di terze parti.  

## <a name="update-management-experience-walk-through"></a>Walk-through dell'esperienza di gestione degli aggiornamenti  
Per visualizzare gli aggiornamenti, accedere al portale dei servizi gestiti e passare alla pagina Aggiornamenti.

![Screenshot degli aggiornamenti dei servizi gestiti](../media/update-management-001.jpg)

Il riquadro Aggiornamenti mostra una panoramica generale della gestione degli aggiornamenti per le chat room con le schede seguenti:

- **Aggiornamenti:** aggiornamenti del software o del firmware che Managed Services sta orchestrando nell'organizzazione.  
- **Sale:** la scheda Sale offre una vista delle chat room e degli anelli a cui appartengono.
- **Anelli:** la scheda Anelli mostra gli anelli delle chat room per l'organizzazione.

### <a name="updates"></a>Aggiornamenti  

Questa visualizzazione mostra gli aggiornamenti pertinenti per il tenant e il rispettivo stato. Per visualizzare gli aggiornamenti passati che non sono più attivi, selezionare l'interruttore Includi **aggiornamenti passati** su ATTIVATO.  

Qualsiasi aggiornamento può essere in uno degli stati seguenti:

| Stato | Descrizione |
| :- | :- |
| Programmato | È pianificato un aggiornamento per le chat room in un determinato anello. Tieni presente che un aggiornamento mostrerà Programmato solo dopo che la progressione raggiunge l'anello in cui si trova la stanza. Ad esempio, se un nuovo aggiornamento si trova nell'anello Gestione temporanea, verrà visualizzato solo Pianificato per le chat room nell'anello Gestione temporanea. <p> Gli altri anelli avranno lo stato "Non obbligatorio" finché l'aggiornamento non viene aggiornato.</p> |
| In corso | È in corso un aggiornamento e i singoli anelli mostrano lo stato. Questo stato mostra lo stato complessivo dell'anello e quindi, se si applica un aggiornamento a una singola chat room nell'anello di gestione temporanea nel tenant, l'aggiornamento avrà lo stato "In corso" finché non viene raggiunto l'anello executive. |
| Operazione completata con errori | Un aggiornamento ha completato la progressione di tutti gli anelli configurati e non è riuscito in almeno una chat room. |
| Completato | Un aggiornamento ha completato la progressione attraverso tutti gli anelli configurati e installato correttamente in tutte le chat room applicabili.|
| Deprecato | Un aggiornamento è stato disattivato. L'ulteriore distribuzione viene interrotta. Questo è tipico perché l'aggiornamento è stato sostituito da una nuova versione. |
| In pausa | Un aggiornamento è in stato di pausa. |
| Non obbligatorio | L'aggiornamento non è ancora stato valutato per la chat room o non è applicabile alla chat room. |

### <a name="rooms"></a>Sale  

La scheda Sale mostra tutte le chat room del tenant e l'anello a cui appartengono.  

![Screenshot di tutti gli anelli del tenant e delle relative chat room](../media/update-management-002.jpg)

Per configurare l'anello a cui deve appartenere una chat room:  

1. Fare clic sulla sala per visualizzare la visualizzazione dettagliata.  
1. In **Anello** fare clic su **Cambia.**  
1. Selezionare l'anello a cui deve appartenere la chat room.  
1. Fare clic **su Assegna**.  

La visualizzazione dettagliata della chat room mostra gli aggiornamenti pertinenti e il relativo stato nel **nodo** Aggiornamenti.  

![Screenshot degli aggiornamenti e delle modifiche pertinenti](../media/update-management-003.jpg)

### <a name="rings"></a>Anelli  

Gli anelli vengono usati per ridurre il rischio di problemi derivanti dalla distribuzione degli aggiornamenti delle funzionalità. Questa operazione viene eseguita distribuendo gradualmente l'aggiornamento all'intero sito. Ogni anello deve avere un elenco di Microsoft Teams room e una pianificazione di implementazione corrispondente. La definizione degli anelli è in genere un evento una sola volta (o almeno poco frequenti), ma l'IT dovrebbe rivedere questi gruppi di tanto in tanto per assicurarsi che la sequenza sia ancora corretta.  

La **scheda Anelli** elenca tutti gli anelli del tenant. Sono disponibili tre anelli preconfigurati:  

**Gestione temporanea**

Assegnare chat room all'anello Gestione temporanea, che è il test. Tutti i nuovi aggiornamenti verranno prima eseminati qui. In generale, è consigliabile assicurarsi che l'anello di gestione temporanea rappresenti le sale con la varietà dei tipi di dispositivi nell'ambiente. Se ci sono determinati tipi di chat room con una configurazione non comune o una cronologia di visualizzazione dei problemi, è consigliabile rappresentarle in Gestione temporanea.

**Generale**

Per impostazione predefinita, tutte le chat room sono posizionate in questo anello. La maggior parte dei dispositivi della sala usati nell'organizzazione rientra in questa categoria. 

**Dirigenti**

Questo gruppo deve includere le chat room più di alto profilo in cui si vuole ridurre al minimo le interruzioni in modo proattivo. Un buon esempio è una sala riunioni di grandi dimensioni usata per le riunioni dei dirigenti o per le riunioni del team di grandi dimensioni. 

### <a name="specifying-rollout-timeline"></a>Specifica della sequenza temporale di implementazione

Gli aggiornamenti non possono superare i 60 giorni per essere completati in tutti gli anelli.  

|**Parametro** |**Spiegazione** |
| :- | :- |
|<p> </p><p>Periodo di rinvio </p>|<p>Quando un aggiornamento inizia con il primo anello, il periodo di rinvio è il ritardo in giorni prima dell'avvio dell'aggiornamento su questo anello.  </p><p> </p>|
|<p> </p><p>Durata dell'implementazione  </p><p> </p>|<p>Una volta avviato l'aggiornamento su questo anello, è il momento di eseguire la distribuzione in questo anello. Ad esempio, se la durata è di 5 giorni, verrà distribuita per più di 5 giorni nelle sale di questo anello una volta avviato l'aggiornamento su questo anello. </p><p> </p>|
|<p> </p><p>Periodo di test </p>|<p><p>Numero di giorni per testare/convalidare l'aggiornamento in un anello una volta applicato all'anello. Il periodo di test inizia dopo il completamento dell'implementazione e, una volta completato, l'aggiornamento passa all'anello successivo. </p><p> </p>|
|<p> </p><p>Ora di completamento </p>|<p> </p><p>La colonna "Tempo di completamento" indica il numero totale di giorni (durata dell'implementazione + periodo di test) per il completamento dell'anello.  </p><p> </p>|
|<p> </p><p>Tempo totale </p>|<p> </p><p>In fondo c'è la riga "Totale", che indica il tempo necessario per completare un aggiornamento dal primo all'ultimo anello. </p><p> </p><p> </p>|

### <a name="creating-custom-rings"></a>Creazione di anelli personalizzati


1. Passare alla **scheda** Anelli.  
1. Fare clic **su Aggiungi anello**.  
1. Specificare l'ordine in cui l'anello riceverà l'aggiornamento, dove 1 è il primo e 9 è l'ultimo.  
1. Assegnare un nome all'anello.  
1. Fornire una descrizione, se necessario.  
1. Specificare il numero di giorni di implementazione dell'aggiornamento in questo anello.  
1. Specificare il periodo di test.  
1. Fare clic **su Invia**.  

> [!NOTE]
> "Giorni impostati da altri anelli" è il numero totale di giorni che un aggiornamento dovrà completare su tutti gli anelli. "Giorni rimanenti" indica il numero massimo di giorni *per* il completamento dell'anello. La somma di "Durata implementazione in giorni" e "Periodo di test in giorni" non può superare questo importo.  

**Modificare un anello**

1. Passare alla **scheda** Anelli.
1. Fare clic sull'anello per eliminarlo.  
1. Fare clic **su Modifica anello**.  
1. Modificare il numero di giorni di implementazione e test, se necessario.

**Eliminare un anello**

1. Passare alla **scheda** Anelli.  
1. Fare clic sull'anello per eliminarlo.  
1. Fare clic **su Elimina anello**.  

> [!NOTE]
> Gli anelli predefiniti non possono essere eliminati.  

**Spostare le chat room**

Lo spostamento di sale da un anello a un altro è possibile in due modi:

1. Passare alla **scheda** Anelli.  
1. Fare clic sull'anello da cui si vogliono spostare le chat room  
1. Fare clic **su Sposta sale**.  
1. Selezionare le chat room da spostare **nell'elenco Delle chat room.**  
1. Scegliere l'anello di destinazione in cui verranno spostate le chat room selezionate nell'elenco a discesa.  
1. Fare clic **su Sposta sale**.  

**Oppure**

1. Apri i dettagli della chat room per la chat room che vuoi spostare (tramite Eventi imprevisti, Sale o Aggiornamenti -> sale).
1. Fare clic **sulla scheda** Aggiornamenti.  
1. In **Anello assegnato** fare clic su **Cambia.**
1. Nell'elenco a discesa selezionare il nuovo anello.  
1. Fare clic **su Assegna**.

## <a name="managed-updates-visibility-and-control"></a>Aggiornamenti gestiti: visibilità e controllo

I servizi gestiti coordinano gli aggiornamenti in tutta l'organizzazione. Tuttavia, si ha la visibilità e il controllo per intervenire, se necessario. Ecco i modi: 

- In caso di errore di aggiornamento, viene generato automaticamente un ticket con il team Microsoft Managed Service Operations. Il team operativo prenderà le misure necessarie per correggere l'errore e coinvolgere l'utente, se necessario.  
- Se viene visualizzato un aggiornamento che causa problemi, è possibile sospendere l'aggiornamento con il **pulsante Sospendi.** Premendo il pulsante Sospendi verrà creato un ticket per l'analisi da parte del centro operativo. Assicurarsi di fornire i dettagli durante la sospensione di un aggiornamento per accelerare la risposta agli eventi imprevisti.  
- Se un aggiornamento non è riuscito in una chat room ed è stato corretto un motivo plausibile, ad esempio la disconnessione dalla rete, è possibile riprovare l'aggiornamento con il pulsante Riprova **tutti** gli errori.  
- Possono verificarsi situazioni urgenti in cui si può decidere di rendere disponibile un aggiornamento in precedenza. In questo caso, è possibile usare il **pulsante Forza aggiornamenti.** Quando si usa l'opzione Forza aggiornamento, è possibile forzare l'aggiornamento immediatamente o alla successiva disponibilità della chat room.  

> [!NOTE]
> **Non è consigliabile usare "Forza aggiornamenti"** come strategia generale di gestione degli aggiornamenti. Se si inserisce un aggiornamento ancora in un passaggio di convalida, è possibile che si verifichino problemi già noti. In questi casi, la risoluzione degli incidenti per tali sale sarà ottimale.  

- Inoltre, per garantire buone procedure di gestione delle modifiche, ogni aggiornamento della forza verrà logato internamente nel servizio. In futuro, ci aspettiamo di renderlo visibile anche all'utente.