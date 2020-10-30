---
title: Guida a Insights dt Teams per l’istruzione per amministratori IT
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Una guida a Insights di Microsoft Teams per l’istruzione per amministratori IT.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b63ea1a1a09a55d9a51fb2a110c024960f23f6f4
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803524"
---
# <a name="it-admin-guide-to-insights-in-teams-for-education"></a>Guida a Insights dt Teams per l’istruzione per amministratori IT

Con Insights di Microsoft Teams per l’istruzione, i docenti e i dirigenti possono accedere ai dati analitici relativi all’impegno digitale, alle attività assegnate, ai voti, alle comunicazioni e altro ancora. Insights è guidato da principi etici che mettono al primo posto insegnanti e studenti, soddisfano gli standard di privacy e garantiscono la conformità continua per l’istituto.

La funzionalità Insights è attiva in Microsoft Office 365 per l'istruzione, SKU A1, A3 e A5.

> [!NOTE]
> I docenti possono apprendere come usare Insights da qui: [Guida per docenti su Insights in Microsoft Teams](https://support.microsoft.com/article/27b56255-90c0-47aa-bac3-1c9f50157181).

## <a name="use-insights"></a>Usare Insights

### <a name="user-types"></a>Tipi di utente
- **Gli studenti** sono identificati in base all’istituto e  _non hanno accesso_ alla scheda Dati analitici (anche se sono i proprietari del team). 
- **Educators** sono identificati in base agli istituti educativi. I docenti devono appartenere a un istituto di istruzione e essere proprietari del team di classe per aggiungere e visualizzare i dati presentati nella scheda Dati analitici. 
- **I dirigenti** vengono anche identificati da un istituto di istruzione, ma necessitano inoltre di autorizzazioni esplicite dall’amministratore globale IT per visualizzare i report nell’app Dati analitici.
- Gli account guest _non possono accedere_ a Dati analitici.

### <a name="entry-points"></a>Punti di ingresso
I docenti e i leader hanno diversi punti di ingresso in cui possono scoprire e utilizzare Insights.

I **docenti** possono usare questi due punti di ingresso:
- [Schede](https://support.microsoft.com/article/27b56255-90c0-47aa-bac3-1c9f50157181): sono disponibili approfondimenti per ogni classe in una scheda aggiunta dal menu di navigazione in alto. Insights mostrerà i dati sulle attività da tutti i canali in un team di classe, ma può essere aggiunto solo come scheda ai canali pubblici. La scheda riflette le attività dei membri del team di classe che non sono proprietari, inclusi i docenti che non sono proprietari del team.
- [App personale](https://support.microsoft.com/article/747fd8d9-00b0-43e6-bacc-a1bf030b1867): è disponibile una panoramica di tutte le classi attive dalla barra dell'app Teams a sinistra.

I **leader** possono Insights come [app personale](https://support.microsoft.com/article/8738d1b1-4e1c-49bd-9e8d-b5292474c347).

### <a name="manage-setup-policy"></a>Gestire i criteri di configurazione
L'amministratore può usare i [criteri di configurazione dell'app](https://docs.microsoft.com/microsoftteams/teams-app-setup-policies) per installare Insights per impostazione predefinita, per i docenti e i leader all’avvio di Teams.
Con tale criterio, è possibile personalizzare Teams per evidenziare Insights, e ancorarlo alla barra delle app.

> [!TIP]
> Leggere [Criteri per Teams e pacchetti di criteri per l'istruzione](https://docs.microsoft.com/microsoftteams/policy-packages-edu) sui criteri di Teams e i pacchetti di criteri per l'istruzione.



## <a name="compliance"></a>Conformità

La funzionalità Insights ha impegni di conformità all’avanguardia ed è classificata come servizio di Livello C nel framework di conformità di Office 365.

> [!NOTE]
> Visitare il [Centro protezione Microsoft](https://www.microsoft.com/trust-center) per altre informazioni su come Microsoft protegge i dati dell’utente.

## <a name="privacy"></a>Privacy

Le informazioni raccolte e visualizzate tramite Insights soddisfano oltre 90 standard normativi e di settore, tra cui GDPR e FERPA (Family Education Rights and Privacy Act) per la sicurezza degli studenti e dei bambini e altre normative simili orientate alla privacy. È importante che gli amministratori IT sappiano che le informazioni raccolte per ogni singolo studente devono essere usate solo in un contesto di classe, per consentire ai docenti e ai dirigenti di determinare l’andamento degli studenti. Le informazioni vengono raccolte per le attività di apprendimento significative, ad esempio la presenza alle riunioni di classe, la pubblicazione di messaggi, le risposte ai post di altri studenti, l’impegno sulle attività, la modifica di file e altro ancora. Ad esempio, non vengono visualizzate informazioni sulle chat private o sull'accesso a Teams.

Il nostro obiettivo consiste nell’aiutare i docenti a comprendere l’impegno degli studenti e a evidenziare l'apprendimento. Anche se queste attività di classe sono concentrate sulle azioni a livello di studente, Microsoft Teams non assegna valori positivi o negativi a tali azioni e gli studenti non vengono identificati in base a un giudizio sulla base di criteri. Le informazioni contenute in Insights informano i docenti, ad esempio, sull’attività di uno studente all’interno dello strumento durante un determinato periodo di tempo o se ha completato in tempo tutte le assegnazioni della settimana passata. Il docente rimane responsabile dell’interazione con lo studente e la relativa famiglia, o i relativi tutori, per determinare il motivo per cui è stata o non è stata rilevata una determinata attività.

## <a name="data-collection"></a>Raccolta dei dati

- Microsoft raccoglie i dati di Insights quando Education Analytics è attivato per il tenant. I dati vengono raccolti dall'attività di Teams per evidenziare le informazioni dettagliate per l'insegnamento e l'apprendimento.
- I dati degli utenti guest _non sono raccolti_ da Dati analitici.
- Per impostazione predefinita, Education Analytics è impostato su **Attivato** .

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
> Leggere [Indicazioni per le situazioni di larghezza di banda ridotta per Teams per l'istruzione](edu-remote-low-bandwidth.md) sull'uso di Teams per l'istruzione quando la larghezza di banda è bassa.

## <a name="how-to-delete-your-data"></a>Come eliminare i dati

I servizi per l’istruzione archiviano le azioni che i docenti e gli studenti compiono nel contesto di un team di classe. Questo tipo di dati è considerato un set di dati mescolati e pertanto non viene eliminato automaticamente una volta che gli account utente di studenti o docenti vengono eliminati dall'organizzazione.

> [!NOTE]
> L'eliminazione dei dati ha un impatto negativo sulla possibilità di Insights di analizzare l’impegno del team di classe nel corso del tempo.

- Aprire un ticket di supporto su [https://edusupport.microsoft.com/support](https://edusupport.microsoft.com/support). Il ticket di supporto deve indicare chiaramente la richiesta di eliminazione DSR ai sensi del GDPR e contenere l'ID dell’oggetto utente da eliminare. Non c'è alcuna possibilità di limitare il set di dati o la finestra temporale per l’eliminazione.
- Una volta archiviato, il ticket di supporto attende in coda per una settimana per rispettare i criteri di conservazione minimi per la conformità. È possibile annullare l'operazione durante questo periodo.
- Dopo una settimana, il team di Education Analytics interviene per assicurare che tutti i dati relativi all'ID utente vengano eliminati dal servizio. Il supporto Microsoft monitora il ticket ICM e informerà l’utente quando il processo è stato completato, entro 28 giorni.

## <a name="turn-insights-off-and-on-using-school-data-sync-sds"></a>Attivare e disattivare Dati analitici tramite School Data Sync (SDS)

School Data Sync (SDS) consente di automatizzare il processo di importazione e sincronizzazione dei dati di Student Information System (SIS) con Office 365.

L'uso di Insights non richiede l'uso di SDS. Tuttavia, è possibile scegliere di rifiutare esplicitamente Education Analytics in qualsiasi momento disattivando l'interruttore nell'interfaccia di amministrazione di SDS in **Impostazioni** > **Gestisci Education Analytics** .

:::image type="content" source="media/class-insights-on-off.png" alt-text="Attivazione o disattivazione di Insights.":::

Per impostazione predefinita Education Analytics, e di conseguenza Insights, è attivato. Quando l’utente rifiuta esplicitamente Education Analytics, Microsoft elimina tutti i dati raccolti per la scheda Insights. Education Analytics viene riattivato e inizia la raccolta dei dati dal momento in cui viene attivato di nuovo.

## <a name="additional-resources"></a>Risorse aggiuntive
- [Guida a Insights per i docenti](https://support.microsoft.com/office/27b56255-90c0-47aa-bac3-1c9f50157181)
