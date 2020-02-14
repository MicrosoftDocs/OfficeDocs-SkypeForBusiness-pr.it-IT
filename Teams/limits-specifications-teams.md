---
title: Limiti e specifiche per Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Informazioni sui limiti, le specifiche e gli altri requisiti applicabili a Microsoft Teams.
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- SPO_Content
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fd871f36c2261dd5ec243dbd8dbdd52a3a8e694
ms.sourcegitcommit: 93a8bd330c9a8ced81cd3eafb7b7236e9ed2066f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2020
ms.locfileid: "41962085"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Limiti e specifiche per Microsoft Teams

Questo articolo descrive alcuni dei limiti, le specifiche e altri requisiti applicabili a Teams.

## <a name="teams-and-channels"></a>Team e canali

|Funzionalità    | Limite massimo |
|-----------|---------------|
|Numero di team che un utente può creare | Soggetto a un limite di 250 oggetti&sup1;         |
|Numero di team di cui un utente può essere membro|1.000|
|Numero di membri in un team | 5,000       |
|Numero di proprietari per Ttam | 100   |
|Numero di team di tutta l'organizzazione consentiti in un tenant | 5     |
|Numero di membri in un [team di tutta l'organizzazione](create-an-org-wide-team.md) | 5.000       |
|Numero di team che possono essere creati da un amministratore globale        |  500.000   |
|Numero di team che un tenant di Office 365 può avere    | 500.000&sup2;     |
|Numero di canali per team    | 200 (include i canali eliminati)&sup3;         |
|Numero di canali privati per team    |30|
|Dimensione post di conversazione sul canale | Circa 28 KB per post<sup>4</sup> |

&sup1; Qualsiasi oggetto di directory di Azure Active Directory conta rispetto a questo limite. Gli amministratori globali sono esentati da questo limite, così come le app che chiamano Microsoft Graph usando le [autorizzazioni dell'applicazione](https://docs.microsoft.com/graph/permissions-reference).

&sup2; Questo limite include i team archiviati.

&sup3; I canali eliminati possono essere ripristinati entro 30 giorni. In questi 30 giorni, un canale eliminato continua a essere considerato rispetto al limite di 200 canali per team. Dopo 30 giorni, un canale eliminato e il relativo contenuto vengono eliminati definitivamente e il canale non viene più calcolato per il limite di 200 canali.

<sup>4</sup> 28 KB è un limite approssimativo perché include il messaggio stesso (testo, collegamenti a immagini e così via), menzioni con @, numero di connettori e reazioni.

## <a name="messaging"></a>Messaggistica

### <a name="chat"></a>Chat

Gli utenti che partecipano a conversazioni che fanno parte dell'elenco chat in Teams devono avere una cassetta postale di Exchange Online (basata su cloud) perché un amministratore possa eseguire ricerche nelle conversazioni via chat. Il motivo è che le conversazioni che fanno parte dell'elenco chat vengono archiviate nelle cassette postali basate su cloud dei partecipanti. Se un partecipante della chat non ha una cassetta postale di Exchange Online, l'amministratore non potrà eseguire una ricerca né applicare un blocco alle conversazioni in chat. In una distribuzione ibrida di Exchange, ad esempio, gli utenti con una cassetta postale locale potrebbero essere in grado di partecipare a conversazioni che fanno parte dell'elenco chat in Teams. In questo caso, tuttavia, il contenuto delle conversazioni non sarebbe disponibile per la ricerca e non potrebbe essere bloccato perché gli utenti non hanno cassette postali basate su cloud. Per altre informazioni, vedere [Interazione tra Exchange e Microsoft Teams](exchange-teams-interact.md).

La chat di Teams opera in un back-end di Microsoft Exchange, quindi per la funzione di chat in Teams si applicano i limiti della messaggistica di Exchange.

|Funzionalità  | Limite massimo  |
|---------|---------|
|Numero di persone in una chat privata<sup>1</sup>  | 100    |
|Numero di file allegati<sup>2</sup>  |10     |
|Dimensione chat | Circa 28 KB per post<sup>3</sup> |

<sup>1</sup> Se si hanno più di 1 persone in una chat, le funzionalità di chat seguenti vengono disattivate: risposte automatiche di Outlook, messaggi di stato di Teams, indicatore di scrittura in corso, chiamate audio e video, condivisione e conferme di lettura.

<sup>2</sup> Se il numero di allegati supera questo limite, viene visualizzato un messaggio di errore.

<sup>3</sup> 28 KB è un limite approssimativo perché include il messaggio stesso (testo, collegamenti a immagini e così via), menzioni con @ e reazioni.

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

Per altre informazioni, vedere [Limiti di Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

> [!NOTE]
> I limiti relativi a dimensioni del messaggio, file allegati e immagini incorporate sono gli stessi per tutte le licenze di Office 365.

## <a name="channel-names"></a>Nomi dei canali

I nomi dei canali non possono contenere i caratteri o le parole seguenti.

|||
|---------|---------|
|Caratteri     | ~ # % & * { } + / \ : < > ? &#124; ' " ..        |
|Caratteri in questi intervalli    | Da 0 a 1F<br>Da 80 a 9F        |
|Parole     | forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, da COM1 a COM9, da LPT1 a LPT9, desktop.ini,  &#95;vti&#95;|

Inoltre, i nomi di canale non possono iniziare con un carattere di sottolineatura (_) o un punto (.), né terminare con un punto (.).

## <a name="meetings-and-calls"></a>Riunioni e chiamate

|Funzionalità     | Limite massimo |
|------------|---------------|
|Numero di persone in una riunione  | 250    |
|Dimensione massima file di PowerPoint | 2 GB|

### <a name="meeting-expiration"></a>Scadenza della riunione

|Tipo di riunione  |La riunione scade dopo un certo intervallo di tempo  |Ogni volta che si avvia o si aggiorna una riunione, la scadenza viene estesa di un certo intervallo di tempo  |
|---------|---------|---------|
|Riunione immediata     |Ora di inizio + 8 ore         |N/D         |
|Regolare senza ora di fine     |Ora di inizio + 60 giorni         | 60 giorni        |
|Regolare con ora di fine     |Ora di fine + 60 giorni         |60 giorni         |
|Ricorrente senza ora di fine     |Ora di inizio + 60 giorni         |60 giorni         |
|Ricorrente con ora di fine     |Ora di fine dell'ultima occorrenza + 60 giorni         |60 giorni         |



## <a name="teams-live-events"></a>Eventi live in Teams

|Funzionalità     | Limite massimo |
|------------|---------------|
|Dimensioni del gruppo di destinatari | 10.000 partecipanti |
|Durata dell'evento | 4 ore |
|Eventi live simultanei in un tenant di Office 365 | 15 |

Per altre informazioni sugli eventi live e per un confronto tra gli eventi live di Teams e Skype Meeting Broadcast, passare a [Eventi live di Teams e Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).

## <a name="presence-in-outlook"></a>Presenza in Outlook

La presenza di Teams in Outlook è supportata nell'app desktop Outlook 2013 e versioni successive. Per altre informazioni sulla presenza in Teams, vedere [Presenza utente in Teams](presence-admins.md).

## <a name="storage"></a>Archiviazione

Ogni team di Microsoft Teams ha un sito del team in SharePoint Online e ogni canale in un team ottiene una cartella all'interno della raccolta documenti predefinita del sito del team. I file condivisi in una conversazione vengono aggiunti automaticamente alla raccolta documenti e le autorizzazioni e opzioni di sicurezza per i file impostate in SharePoint vengono applicate automaticamente all'interno di Teams.

Se SharePoint Online non è abilitato nel tenant, non sempre gli utenti di Microsoft Teams potranno condividere file nei team. Anche per gli utenti in chat private non è possibile condividere file, perché per questa funzionalità è necessario usare OneDrive for Business, che è associato alla licenza di SharePoint.

Archiviando i file nella raccolta documenti di SharePoint Online e in OneDrive for Business, verranno rispettate tutte le regole di conformità configurate a livello di tenant. Per altre informazioni, vedere [Modalità di interazione di SharePoint Online e OneDrive for Business con Microsoft Teams](sharepoint-onedrive-interact.md).

Poiché Teams viene eseguito in un back-end di SharePoint Online per la condivisione dei file, alla sezione File all'interno di un team si applicano le limitazioni di SharePoint. Ecco i limiti di archiviazione applicabili per SharePoint Online.

|Funzionalità                 |Office 365 Business Essentials  |Office 365 Business Premium   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Archiviazione                 |1 TB per ogni organizzazione e 10 GB per ogni licenza acquistata  |1 TB per ogni organizzazione e 10 GB per ogni licenza acquistata  |1 TB per ogni organizzazione e 10 GB per ogni licenza acquistata   |1 TB per ogni organizzazione e 10 GB per ogni licenza acquistata |1 TB per ogni organizzazione e 10 GB per ogni licenza acquistata  |1 TB per ogni organizzazione           |
|Spazio di archiviazione per i file di Teams |Fino a 25 TB per raccolta siti o gruppo |Fino a 25 TB per raccolta siti o gruppo |Fino a 25 TB per raccolta siti o gruppo |Fino a 25 TB per raccolta siti o gruppo |Fino a 25 TB per raccolta siti o gruppo |Fino a 25 TB per raccolta siti o gruppo |
|Limite di caricamento file (per file)    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

I canali sono supportati da cartelle all'interno della raccolta siti di SharePoint Online creata per il team, quindi le schede dei file all'interno dei canali condividono i limiti di archiviazione del team a cui appartengono.

Per altre informazioni, vedere [Limiti di SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

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
