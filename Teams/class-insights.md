---
title: Insights di Microsoft Teams per l’istruzione per amministratori IT
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Guida a Insights di Microsoft Teams per l’istruzione per amministratori IT.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75d9396bf5f537f965493bb0db317a1286b2f950
ms.sourcegitcommit: b14ad0a6c454b20f34fccbd1d312de24379faef0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2020
ms.locfileid: "46572371"
---
# <a name="insights-in-teams-for-education-for-it-admins"></a>Insights di Teams per l’istruzione per amministratori IT

Con Insights in Microsoft Teams per l’istruzione, i docenti e i dirigenti possono accedere ai dati analitici relativi all’impegno digitale, alle attività assegnate, ai voti, alle comunicazioni e altro ancora.

La funzionalità Insights è attiva in Office 365 Education, SKU A1, A3 e A5.

> [!NOTE]
> I docenti possono imparare ad usare Insights [qui](https://support.microsoft.com/office/actionable-analytics-with-class-insights-in-teams-163add4f-997d-4a01-91de-2846fe4e99bc).

## <a name="permissions"></a>Autorizzazioni

- Gli studenti vengono identificati in base all’istituto e **non hanno accesso alla scheda Dati analitici** anche se sono proprietari del team.
- I docenti sono definiti secondo gli istituti di istruzione. I docenti devono appartenere a un istituto di istruzione e essere proprietari del team di classe per aggiungere e visualizzare la scheda Insights. La scheda riflette le attività dei membri del team di classe che non sono proprietari (inclusi i docenti che non sono proprietari del team).
- I dirigenti sono definiti secondo gli istituti di istruzione. L'amministratore globale IT è identificato dal suo ruolo. I dirigenti devono appartenere a un istituto di istruzione e ottenere autorizzazioni esplicite dall’amministratore globale IT per visualizzare i report nell’app Insights.

Insights è disponibile in due moduli:
- Schede: i docenti possono aggiungere Insights a un canale pubblico all'interno di un team di classe passando a App nella barra delle applicazioni di Teams e cercando Insights.
- App personale: i dirigenti possono aggiungere l'app Insights come app personale (disponibile nel menu a sinistra di Teams) passando a App nella barra delle applicazioni di Teams e cercando Insights.

## <a name="compliance"></a>Conformità

La funzionalità Insights ha impegni di conformità all’avanguardia ed è classificata come servizio di Livello C nel framework di conformità di Office 365.

> [!NOTE]
> Visitare il [Centro protezione Microsoft](https://www.microsoft.com/trust-center) per altre informazioni su come Microsoft protegge i dati dell’utente.

## <a name="privacy"></a>Privacy

Le informazioni raccolte e visualizzate tramite Insights soddisfano oltre 90 standard normativi e di settore, tra cui GDPR e FERPA (Family Education Rights and Privacy Act) per la sicurezza degli studenti e dei bambini e altre normative simili orientate alla privacy. È importante che gli amministratori IT sappiano che le informazioni raccolte per ogni singolo studente devono essere usate solo in un contesto di classe, per consentire ai docenti e ai dirigenti di determinare l’andamento della classe. Le informazioni vengono raccolte per le attività di apprendimento significative, ad esempio la presenza alle riunioni di classe, la pubblicazione di messaggi, le risposte ai post di altri studenti, l’impegno sulle attività, la modifica di file e altro ancora. Ad esempio, non vengono visualizzate informazioni sulle chat private o sull'accesso a Teams.

Il nostro obiettivo consiste nell’aiutare i docenti a comprendere l’impegno degli studenti e a evidenziare l'apprendimento. Anche se queste attività di classe sono concentrate sulle azioni a livello di studente, Microsoft Teams non assegna valori positivi o negativi a tali azioni e gli studenti non vengono identificati in base a un giudizio sulla base di criteri. Le informazioni contenute in Insights informano i docenti, ad esempio, sull’attività di uno studente all’interno dello strumento durante un determinato periodo di tempo o se ha completato in tempo tutte le assegnazioni della settimana passata. Il docente rimane responsabile dell’interazione con lo studente e la relativa famiglia, o i relativi tutori, per determinare il motivo per cui è stata o non è stata rilevata una determinata attività.

## <a name="data-collection"></a>Raccolta dei dati

Microsoft raccoglie i dati di Insights quando Education Analytics è attivato per il tenant. I dati vengono raccolti dall'attività di Teams per evidenziare le informazioni dettagliate per l'insegnamento e l'apprendimento.

Per impostazione predefinita, Education Analytics è impostato su **Attivato**.

Al momento, i dati vengono recuperati dalle aree seguenti di attività degli studenti e dei docenti nei team di classe:

|Componenti dei team  |Dati raccolti  |
|-----------------|------------------------|------------------------|
|Attività assegnate |Apertura, consegna e assegnazione dei voti alle attività. |
|Impegno nel canale |Visita di un canale, creazione di post, risposta e gradimento di un post, escluso il contenuto della chat. |
|File |Carico, download, accesso, modifica, commento e condivisione dei file, escluso il contenuto del file. |
|Riunioni |Frequenza, escluso il contenuto della riunione. |

## <a name="data-location"></a>Posizione dei dati

I dati di Insights per i tenant basati in Europa sono archiviati in server europei. I dati di Insights per i tenant basati negli Stati Uniti sono archiviati in server statunitensi. Se si usa Insights e il tenant di Office 365 si trova in un'area geografica all'esterno di Europa o Stati Uniti, i dati verranno archiviati nell'area geografica appropriata.

## <a name="performance-and-reliability"></a>Prestazioni e affidabilità

Insights è studiato per gestire un volume elevato di dati raccolti dall’attività di Teams con prestazioni e affidabilità ottimali.

Il processo di raccolta dei dati avviene in server distinti, indipendentemente dall'installazione della scheda Insights in Teams. La scheda o l’app personale Insights non influisce sulle prestazioni delle applicazioni o sulla larghezza di banda di rete dei docenti e degli studenti che usano altre funzionalità di Teams.

> [!TIP]
> Leggere [qui](edu-remote-low-bandwidth.md) per informazioni sull'uso di Teams per l'istruzione quando la larghezza di banda è bassa.

## <a name="how-to-delete-your-data"></a>Come eliminare i dati

I servizi per l’istruzione archiviano le azioni che i docenti e gli studenti compiono nel contesto di un team di classe. Questo tipo di dati è considerato un set di dati mescolati e pertanto non viene eliminato automaticamente una volta che gli account utente di studenti o docenti vengono eliminati dall'organizzazione.

> [!NOTE]
> L'eliminazione dei dati ha un impatto negativo sulla possibilità di Insights di analizzare l’impegno del team di classe nel corso del tempo.

- Aprire un ticket di supporto [qui](https://edusupport.microsoft.com/support). Il ticket di supporto deve indicare chiaramente la richiesta di eliminazione DSR ai sensi del GDPR e contenere l'ID dell’oggetto utente da eliminare. Non c'è alcuna possibilità di limitare il set di dati o la finestra temporale per l’eliminazione.
- Una volta archiviato, il ticket di supporto attende in coda per una settimana per rispettare i criteri di conservazione minimi per la conformità. È possibile annullare l'operazione durante questo periodo.
- Dopo una settimana, il team di Education Analytics interviene per assicurare che tutti i dati relativi all'ID utente vengano eliminati dal servizio. Il supporto Microsoft monitora il ticket ICM e informerà l’utente quando il processo è stato completato, entro 28 giorni.

## <a name="turn-insights-off-and-on-using-school-data-sync-sds"></a>Attivare e disattivare Dati analitici tramite School Data Sync (SDS)

School Data Sync (SDS) consente di automatizzare il processo di importazione e sincronizzazione dei dati di Student Information System (SIS) con Office 365.

L'uso di Insights non richiede l'uso di SDS. Tuttavia, è possibile scegliere di rifiutare esplicitamente Education Analytics in qualsiasi momento disattivando l'interruttore nell'interfaccia di amministrazione di SDS in **Impostazioni** > **Gestisci Education Analytics**.

:::image type="content" source="media/class-insights-on-off.png" alt-text="Attivazione o disattivazione di Insights.":::

Per impostazione predefinita Education Analytics, e di conseguenza Insights, è attivato. Quando l’utente rifiuta esplicitamente Education Analytics, Microsoft elimina tutti i dati raccolti per la scheda Insights. Education Analytics viene riattivato e inizia la raccolta dei dati dal momento in cui viene attivato di nuovo.

Altre informazioni: [Insights per docenti](https://support.microsoft.com/office/actionable-analytics-with-class-insights-in-teams-163add4f-997d-4a01-91de-2846fe4e99bc)
