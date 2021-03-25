---
title: Limiti e specifiche per Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: siunies
description: Questo articolo descrive i limiti, le specifiche e altri requisiti applicabili a Microsoft Teams.
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- SPO_Content
- m365initiative-deployteams
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 98f462044fba566ecea491bc55bf8df055973701
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112292"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Limiti e specifiche per Microsoft Teams

Questo articolo descrive alcuni dei limiti, le specifiche e altri requisiti applicabili a Teams.

## <a name="teams-and-channels"></a>Team e canali

|Funzionalità    | Limite massimo |
|-----------|---------------|
|Numero di team che un utente può creare | Soggetto a un limite di 250 oggetti&sup1;         |
|Numero di team di cui un utente può essere membro|1,000&sup2;|
|Numero di membri in un team | 25.000<sup>6</sup>     |
|Numero di proprietari per Ttam | 100   |
|Numero di team di tutta l'organizzazione consentiti in un tenant | 5&sup2;     |
|Numero di membri in un [team di tutta l'organizzazione](create-an-org-wide-team.md) | 10.000       |
|Numero di team che possono essere creati da un amministratore globale        |  500.000   |
|Numero di team che un'organizzazione di Microsoft 365 o Office 365 può avere    | 500.000&sup3;     |
|Numero di canali per team    | 200 (include i canali eliminati)<sup>4</sup>        |
|Numero di canali privati per team    |30 (include i canali eliminati)<sup>4</sup>        |
|Numero di membri in un canale privato    |250|
|Dimensioni massime della lista di distribuzione, del gruppo di sicurezza o del gruppo di Office 365 che è possibile importare in un team    |3.500|
|Numero massimo di membri in un gruppo di Office 365 che possono essere trasformati in un team    |10.000<sup>6</sup>     |
|Dimensione post di conversazione sul canale | Circa 28 KB per post<sup>5</sup> |

<sup>1</sup> Qualsiasi oggetto di directory di Azure Active Directory conta rispetto a questo limite. Gli amministratori globali sono esentati da questo limite, così come le app che chiamano Microsoft Graph usando le [autorizzazioni dell'applicazione](/graph/permissions-reference).

<sup>2</sup> Questo limite include i team archiviati. 

<sup>3</sup> Per aumentare ulteriormente il numero di team, è necessario contattare il supporto Microsoft e richiedere un aumento ulteriore del numero di oggetti di Azure Active Directory nel tenant. L'aumento viene eseguito solo per scenari di produzione reali.

<sup>4</sup> I canali eliminati possono essere ripristinati entro 30 giorni. In questi 30 giorni, un canale eliminato continua a essere considerato rispetto al limite di 200 canali o 30 canali privati per team. Dopo 30 giorni, un canale eliminato e il relativo contenuto vengono eliminati definitivamente e il canale non viene più calcolato per il limite per team.

<sup>5</sup> 28 KB è un limite approssimativo perché include il messaggio stesso (testo, collegamenti a immagini e così via), menzioni con @, numero di connettori e reazioni.

<sup>6</sup> I team di GCC possono ospitare solo 25.000 membri mentre i team di GCCH/DoD solo 2.500 membri. Si noti inoltre che le menzioni dei team/canali sono bloccate nei team con più di 10.000 membri.

## <a name="messaging"></a>Messaggistica

### <a name="chat"></a>Chat

Gli utenti che partecipano a conversazioni che fanno parte dell'elenco chat in Teams devono avere una cassetta postale di Exchange Online (basata sul cloud) perché un amministratore possa eseguire ricerche nelle conversazioni in chat. Il motivo è che le conversazioni che fanno parte dell'elenco chat vengono archiviate nelle cassette postali basate su cloud dei partecipanti. Se un partecipante della chat non ha una cassetta postale di Exchange Online, l'amministratore non potrà eseguire una ricerca né applicare un blocco alle conversazioni in chat. In una distribuzione ibrida di Exchange, ad esempio, gli utenti con una cassetta postale locale potrebbero essere in grado di partecipare a conversazioni che fanno parte dell'elenco chat in Teams. In questo caso, tuttavia, il contenuto delle conversazioni non è disponibile per la ricerca e non può essere bloccato perché gli utenti non hanno cassette postali basate sul cloud. Per ulteriori informazioni, vedere [Come interagiscono Exchange e Microsoft Teams](exchange-teams-interact.md).

La chat di Teams funziona su un back-end di Microsoft Exchange, quindi i limiti di messaggistica di Exchange si applicano alla funzione di chat in Teams.

|Funzionalità  | Limite massimo  |
|---------|---------|
|Numero di persone in una chat privata<sup>1</sup>  | 250<sup>2</sup> |
|Numero di persone in un video o una chiamata audio dalla chat | 20 |
|Numero di file allegati<sup>3</sup>  |10     |
|Dimensione chat | Circa 28 KB per post<sup>4</sup> |

<sup>1</sup>Se si hanno più di 20 persone in una chat, le funzionalità di chat seguenti sono disattivate: risposte automatiche di Outlook, messaggi di stato di Teams, indicatore di scrittura in corso, chiamate audio e video, condivisione e conferme di lettura. Il pulsante "Imposta opzioni di recapito" (!) viene rimosso anche quando le chat di gruppo privato contengono più di 20 membri.

<sup>2</sup> È possibile aggiungere solo 200 membri alla volta a una chat di gruppo. [Per altre informazioni, vedere questo articolo](/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat).

<sup>3</sup> Se il numero di allegati supera questo limite, viene visualizzato un messaggio di errore.

<sup>4</sup> 28 KB è un limite approssimativo perché include il messaggio stesso (testo, collegamenti a immagini e così via), menzioni con @ e reazioni.

### <a name="emailing-a-channel"></a>Invio di messaggi di posta elettronica a un canale

 Se gli utenti vogliono inviare un messaggio di posta elettronica a un canale in Teams, usano l'indirizzo di posta elettronica del canale. Quando un messaggio di posta elettronica fa parte di un canale, chiunque può rispondere per avviare una conversazione. Ecco alcuni dei limiti applicabili all'invio di messaggi di posta elettronica a un canale.

|Funzionalità  | Limite massimo  |
|---------|---------|
|Dimensioni messaggio<sup>1<sup> | 24 KB |
|Numero di file allegati<sup>2</sup>  |20     |
|Dimensioni di ogni file allegato | Meno di 10 MB |
|Numero di immagini incorporate<sup>2</sup> |50   |

<sup>1</sup> Se il messaggio supera questo limite viene generato un messaggio di anteprima e all'utente viene chiesto di scaricare e visualizzare il messaggio di posta elettronica originale dal collegamento fornito.

<sup>2</sup> Se il numero di allegati o immagini supera questo limite, viene visualizzato un messaggio di errore.

Per altre informazioni, vedere [Limiti di Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

> [!NOTE]
> I limiti relativi a dimensioni del messaggio, file allegati e immagini incorporate sono gli stessi per tutte le licenze di Microsoft 365 o Office 365. L'invio di messaggi di posta elettronica a un canale non è disponibile in Teams per le organizzazioni di Office GCC/GCCH/DOD.

## <a name="channel-names"></a>Nomi dei canali

I nomi dei canali non possono contenere i caratteri o le parole seguenti:

|Tipo|Esempio|
|---------|---------|
|Caratteri     | ~ # % & * { } + / \ : < > ? &#124; ' " , ..        |
|Caratteri in questi intervalli    | Da 0 a 1F<br>Da 80 a 9F        |
|Parole     | forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, da COM1 a COM9, da LPT1 a LPT9, desktop.ini,  &#95;vti&#95;|

Inoltre, i nomi di canale non possono iniziare con un carattere di sottolineatura (_) o un punto (.), né terminare con un punto (.).

## <a name="meetings-and-calls"></a>Riunioni e chiamate

> [!IMPORTANT]
> **Aumento del limite degli eventi live di Microsoft 365**
>
> **Per continuare a supportare le esigenze dei nostri clienti, dal 30 giugno 2021 estenderemo gli incrementi del limite temporaneo per gli eventi live, inclusi**:
>
>- Supporto agli eventi fino a 20.000 partecipanti
>- 50 eventi possono avere luogo contemporaneamente in uno stesso tenant
>- Durata degli eventi fino a 16 ore per trasmissione
>
> Inoltre, tramite il programma di assistenza di Microsoft 365 è possibile pianificare eventi live con un massimo di 100.000 partecipanti. Il team valuterà ogni richiesta e collaborerà con l'utente per determinare le opzioni che potrebbero essere disponibili. [Ulteriori informazioni](https://aka.ms/Stream/Blog/LiveEventOptions).

|Funzionalità     | Limite massimo |
|------------|---------------|
|Numero di persone in una riunione (che possono chattare e partecipare tramite telefono)  | 300. **Solo visualizzazione** consente a un massimo di 10.000 persone di partecipare in solo ascolto a una riunione in cui l'organizzatore ha una licenza per lo SKU E3/E5/A3/A5.<br>**Nota:** per Teams per enti pubblici (GCC, GCC High, DoD), il limite è ancora 250. Questo articolo verrà aggiornato appena il limite del cloud per enti pubblici passerà da 250 a 300 e supporterà l'overflow delle riunioni. Altre informazioni sull'[esperienza di sola visualizzazione](view-only-meeting-experience.md).|
|Numero di persone in un video o una chiamata audio dalla chat | 20 |
|Dimensione massima file di PowerPoint | 2 GB|
|Teams conserva le [registrazioni delle riunioni](cloud-recording.md) che non vengono caricate in Microsoft Stream, disponibili per il download locale | 20 giorni |

### <a name="meeting-expiration"></a>Scadenza della riunione

|Tipo di riunione  |La riunione scade dopo un certo intervallo di tempo  |Ogni volta che si avvia o si aggiorna una riunione, la scadenza viene estesa di un certo intervallo di tempo  |
|---------|---------|---------|
|Riunione immediata     |Ora di inizio + 8 ore         |N/D         |
|Regolare senza ora di fine     |Ora di inizio + 60 giorni         | 60 giorni        |
|Regolare con ora di fine     |Ora di fine + 60 giorni         |60 giorni         |
|Ricorrente senza ora di fine     |Ora di inizio + 60 giorni         |60 giorni         |
|Ricorrente con ora di fine     |Ora di fine dell'ultima occorrenza + 60 giorni         |60 giorni         |

> [!NOTE]
> Le riunioni di Microsoft Teams hanno un limite di tempo di 24 ore.

## <a name="teams-live-events"></a>Eventi live in Teams

|Funzionalità     | Limite massimo |
|------------|---------------|
|Dimensioni del gruppo di destinatari | 10.000 partecipanti |
|Durata dell'evento | 4 ore |
|Eventi live simultanei eseguiti in un'organizzazione di Microsoft 365 o Office 365<sup>1</sup> | 15 |

<sup>1</sup> È possibile pianificare un numero illimitato di eventi, ma se ne possono eseguire solo 15 alla volta. Non appena il produttore partecipa a un evento live, questo è considerato in esecuzione. Il produttore che prova a partecipare al sedicesimo evento live riceve un messaggio di errore.

Per altre informazioni sugli eventi live e per un confronto tra gli eventi live di Teams e Skype Meeting Broadcast, passare a [Eventi live di Teams e Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast). Vedere anche [Pianificare un evento live di Teams](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).

> [!IMPORTANT]
> **Aumento del limite degli eventi live di Microsoft 365**
>
> **Per continuare a supportare le esigenze dei nostri clienti, dal 30 giugno 2021 estenderemo gli incrementi del limite temporaneo per gli eventi live, inclusi**:
>
>- Supporto agli eventi fino a 20.000 partecipanti
>- 50 eventi possono avere luogo contemporaneamente in uno stesso tenant
>- Durata degli eventi fino a 16 ore per trasmissione
>
> Inoltre, tramite il programma di assistenza di Microsoft 365 è possibile pianificare eventi live con un massimo di 100.000 partecipanti. Il team valuterà ogni richiesta e collaborerà con l'utente per determinare le opzioni che potrebbero essere disponibili. [Ulteriori informazioni](https://aka.ms/Stream/Blog/LiveEventOptions). 

## <a name="presence-in-outlook"></a>Presenza in Outlook

La presenza di Teams in Outlook è supportata nell'app desktop Outlook 2013 e versioni successive. Per altre informazioni sulla presenza in Teams, vedere [Presenza utente in Teams](presence-admins.md).

## <a name="storage"></a>Archiviazione

Ogni team di Microsoft Teams ha un sito del team in SharePoint Online e ogni canale in un team ottiene una cartella all'interno della raccolta documenti predefinita del sito del team. I file condivisi in una conversazione vengono aggiunti automaticamente alla raccolta documenti e le autorizzazioni e opzioni di sicurezza per i file impostate in SharePoint vengono applicate automaticamente all'interno di Teams.

> [!NOTE]
> Ogni [canale privato](./private-channels.md) include un proprio sito di SharePoint, in precedenza denominato “raccolta siti”.

Se SharePoint Online non è abilitato nel tenant, non sempre gli utenti di Microsoft Teams potranno condividere file nei team. Anche per gli utenti in chat private non è possibile condividere file, perché per questa funzionalità è necessario usare OneDrive for Business, che è associato alla licenza di SharePoint.

Archiviando i file nella raccolta documenti di SharePoint Online e in OneDrive for Business, verranno rispettate tutte le regole di conformità configurate a livello di tenant. Per altre informazioni, vedere [Modalità di interazione di SharePoint Online e OneDrive for Business con Microsoft Teams](sharepoint-onedrive-interact.md).

Poiché Teams viene eseguito su un back-end di SharePoint Online per la condivisione di file, le limitazioni di SharePoint si applicano alla sezione File all'interno di un team. Di seguito sono riportati i limiti di archiviazione applicabili per SharePoint Online.

|Funzionalità                 |Microsoft 365 Business Basic  |Microsoft 365 Business Standard   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Archiviazione                 |1 TB per ogni organizzazione e 10 GB per ogni licenza acquistata  |1 TB per ogni organizzazione e 10 GB per ogni licenza acquistata  |1 TB per ogni organizzazione e 10 GB per ogni licenza acquistata   |1 TB per ogni organizzazione e 10 GB per ogni licenza acquistata |1 TB per ogni organizzazione e 10 GB per ogni licenza acquistata  |1 TB per ogni organizzazione           |
|Spazio di archiviazione per i file di Teams |Fino a 25 TB per sito o gruppo |Fino a 25 TB per sito o gruppo |Fino a 25 TB per sito o gruppo |Fino a 25 TB per sito o gruppo |Fino a 25 TB per sito o gruppo |Fino a 25 TB per sito o gruppo |
|Limite di caricamento file (per file)    |100 GB    |100 GB    |100 GB    |100 GB    |100 GB    |100 GB    |

I canali sono supportati da cartelle all'interno del sito di SharePoint Online, in precedenza denominato “raccolta siti”, creato per il team, quindi le schede dei file all'interno dei canali condividono i limiti di archiviazione del team a cui appartengono.

Per altre informazioni, vedere [Limiti di SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## <a name="class-teams"></a>Team di classe

Microsoft Teams per l’istruzione fornisce modelli ideati per scenari di istruzione univoci, ad esempio per l’insegnamento in classe. Altre informazioni sui tipi di team, tra cui i team di classe, sono disponibili in [Scegliere un tipo di team per collaborare in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).

Un team di classe è un tipo di modello con altre app incluse e con limiti distinti per il numero di membri del team.

> [!NOTE]
> Per usare i team di classe è necessaria una [licenza Microsoft Office 365 per l'istruzione](https://www.microsoft.com/education/products/office).

Nella tabella seguente sono elencati i limiti per i team di classe:

|Funzionalità  |Limite massimo  |
|---------|---------|
|Numero di membri in un team    | Vedere la sezione di questo articolo [team e canali](#teams-and-channels)        |
|Numero di membri che possono utilizzare le attività in un team di classe    | 200        |
|Numero di membri che usano un blocco appunti di OneNote per la classe in un team di classe     |200         |

Un team di classe può supportare più di 200 membri. Se si prevede di usare l'app Attività o Blocco appunti per la classe all'interno del team, è necessario mantenere il numero di membri al di sotto dei limiti massimi elencati in precedenza.

## <a name="tags"></a>Tag

|Funzionalità  |Limite massimo  |
|---------|---------|
|Numero di tag per team    | 100        |
|Numero di tag predefiniti consigliati per ogni team    | 25        |
|Numero di membri del team assegnati a un tag    |100         |
|Numero di tag assegnati a un utente per team    |25         |

## <a name="contacts"></a>Contatti

Teams usa questi contatti:

- Contatti nell'ambiente Active Directory dell'organizzazione
- Contatti aggiunti alla cartella predefinita di Outlook dell'utente

Gli utenti di Teams possono comunicare con chiunque all'interno dell'organizzazione e aggiungere chiunque nell'ambiente Active Directory dell'organizzazione come contatto e al proprio elenco di contatti, passando a **Chat** > **Contatti** o **Chiamate** > **Contatti**.

Gli utenti di Teams possono anche aggiungere come contatto una persona non presente in Active Directory dell'organizzazione, passando a **Chiamate** > **Contatti**.

## <a name="browsers"></a>Browser

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>Sistemi operativi

Per informazioni sui requisiti per il sistema operativo, vedere [Ottenere client per Microsoft Teams](get-clients.md).