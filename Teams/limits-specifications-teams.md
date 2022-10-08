---
title: Limiti e specifiche per Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: siunies
description: Questo articolo descrive i limiti, le specifiche e altri requisiti applicabili a Microsoft Teams.
ms.localizationpriority: high
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b34f22d5ef038eff44b5488588902d1a99af8676
ms.sourcegitcommit: fcedb958bf555d870215ae84fb83752304944716
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2022
ms.locfileid: "68486616"
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
|Dimensioni massime della lista di distribuzione, del gruppo di sicurezza o del gruppo di Microsoft 365 che è possibile importare in un team    |3.500|
|Numero massimo di membri in un gruppo di Microsoft 365 che possono essere trasformati in un team    |10.000<sup>6</sup>     |
|Dimensione post di conversazione sul canale | Circa 28 KB per post<sup>5</sup> |

<sup>1</sup> Any directory object in Azure Active Directory counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](/graph/permissions-reference).

<sup>2</sup> Questo limite include i team archiviati. 

<sup>3</sup> To further increase the number of teams, you must contact Microsoft support and request further increase to the number of Azure Active Directory objects in your tenant. Increase is only made for real-life production scenarios.

<sup>4</sup> Deleted channels can be restored within 30 days. During these 30 days, a deleted channel continues to be counted towards the 200 channel or 30 private channel per team limit. After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the per team limit.

<sup>5</sup> 28 KB è un limite approssimativo perché include il messaggio stesso (testo, collegamenti a immagini e così via), menzioni con @, numero di connettori e reazioni.

<sup>6</sup> I membri dei canali condivisi esterni al team vengono conteggiati in base a questo limite. Si noti inoltre che le menzioni dei team/canali sono bloccate nei team con più di 10.000 membri.

> [!NOTE]
> Per i limiti dei canali condivisi, vedere [Limiti per i canali condivisi](/MicrosoftTeams/shared-channels#limits-for-shared-channels).

## <a name="messaging"></a>Messaggistica

### <a name="chat"></a>Chat

Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)


|Funzionalità  | Limite massimo  |
|---------|---------|
|Numero di persone in una chat privata<sup>1</sup>  | 250<sup>2</sup> |
|Numero di persone in un video o una chiamata audio dalla chat | 20 |
|Numero di file allegati<sup>3</sup>  |10     |
|Dimensione chat | Circa 28 KB per post<sup>4</sup> |

<sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.

<sup>2</sup> Only 200 members at a time can be added to a group chat. [See this article for more information](/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat).

<sup>3</sup> Se il numero di allegati supera questo limite, viene visualizzato un messaggio di errore.

<sup>4</sup> 28 KB è un limite approssimativo perché include il messaggio stesso (testo, collegamenti a immagini e così via), menzioni con @ e reazioni.

### <a name="emailing-a-channel"></a>Invio di messaggi di posta elettronica a un canale

 If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.

|Funzionalità  | Limite massimo  |
|---------|---------|
|Dimensioni messaggio<sup>1<sup> | 24 KB |
|Numero di file allegati<sup>2</sup>  |20     |
|Dimensioni di ogni file allegato | Meno di 10 MB |
|Numero di immagini incorporate<sup>2</sup> |50   |

> [!NOTE]
> Esiste un limite di limitazione per il numero di messaggi di posta elettronica che è possibile inviare a un canale. Il limite è di sei messaggi di posta elettronica per dieci secondi per canale per utente e otto messaggi di posta elettronica per dieci secondi per tenant per ogni utente.
<sup>1</sup> Se il messaggio supera questo limite viene generato un messaggio di anteprima e all'utente viene chiesto di scaricare e visualizzare il messaggio di posta elettronica originale dal collegamento fornito.

<sup>2</sup> Se il numero di allegati o immagini supera questo limite, viene visualizzato un messaggio di errore.

Per altre informazioni, vedere [Limiti di Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

> [!NOTE]
> Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.

## <a name="channel-names"></a>Nomi dei canali

I nomi dei canali non possono contenere i caratteri o le parole seguenti:

|Tipo|Esempio|
|---------|---------|
|Caratteri     | ~ # % & * { } + / \ : < > ? &#124; ' " , ..        |
|Caratteri in questi intervalli    | Da 0 a 1F<br>Da 80 a 9F        |
|Parole     | forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, da COM1 a COM9, da LPT1 a LPT9, desktop.ini,  &#95;vti&#95;|

Inoltre, i nomi di canale non possono iniziare con un carattere di sottolineatura (_) o un punto (.), né terminare con un punto (.).

## <a name="meetings-and-calls"></a>Riunioni e chiamate

|Funzionalità     | Limite massimo |
|------------|---------------|
|Numero di persone in una riunione (che possono chattare e partecipare tramite telefono)  | 1000, include GCC, GCCH e DoD, ma non A1 (300). **Solo visualizzazione** consente a un massimo di 20.000 persone di partecipare in solo ascolto a una riunione in cui l'organizzatore ha una licenza per lo SKU E3/E5/A3/A5, oltre al Governo (GCC, GCC High, DoD). L'esperienza di sola visualizzazione sarà disponibile prossimamente anche per i webinar. Altre informazioni sull'[esperienza di sola visualizzazione](view-only-meeting-experience.md).<sup>1,2</sup>|
|Numero di persone in un video o una chiamata audio dalla chat | 20 |
|Dimensione massima file di PowerPoint | 2 GB|
|Teams conserva le [registrazioni delle riunioni](cloud-recording.md) che non vengono caricate in Microsoft Stream, disponibili per il download locale | 20 giorni |
| Lunghezza massima registrazione riunione | 4 ore o 1,5 GB. Quando viene raggiunto questo limite, la registrazione terminerà e verrà riavviato automaticamente.
  
<sup>1</sup> Per un'esperienza ottimale nei webinar, negli eventi live e nelle riunioni di grandi dimensioni, Microsoft consiglia di usare l'ultima versione del client desktop di Teams o dei client per dispositivi mobili di Teams.

<sup>2</sup> Nelle riunioni di grandi dimensioni, nei webinar e negli eventi live, i relatori dovrebbero usare il client desktop di Teams. Per altri suggerimenti su come ospitare riunioni di grandi dimensioni, vedere [Procedure consigliate per le riunioni di grandi dimensioni in Teams](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16).

> [!NOTE]
> I gruppi di lavoro possono essere creati esclusivamente nelle riunioni con meno di 300 partecipanti. Inoltre, la creazione di gruppi di lavoro in una riunione limita automaticamente il numero di partecipanti alla riunione a 300. Consigliare agli utenti finali di non avviare gruppi di lavoro in riunioni in cui si prevede la partecipazione di oltre 300 partecipanti. Per altre informazioni sulle riunioni di grandi dimensioni in Teams, condividere le linee guida [Best practice per riunioni di grandi dimensioni in Teams](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16) con gli utenti finali.

### <a name="meeting-expiration"></a>Scadenza della riunione

> [!NOTE]
> A meeting URL will never stop working. The expiry only relates to any PSTN dial-in numbers, CVI coordinates, and/or underlying meeting policies and settings.

|Tipo di riunione  |La riunione scade dopo un certo intervallo di tempo  |Ogni volta che si avvia o si aggiorna una riunione, la scadenza viene estesa di un certo intervallo di tempo  |
|---------|---------|---------|
|Riunione immediata     |Ora di inizio + 8 ore         |N/D         |
|Regolare senza ora di fine     |Ora di inizio + 60 giorni         | 60 giorni        |
|Regolare con ora di fine     |Ora di fine + 60 giorni         |60 giorni         |
|Ricorrente senza ora di fine     |Ora di inizio + 60 giorni         |60 giorni         |
|Ricorrente con ora di fine     |Ora di fine dell'ultima occorrenza + 60 giorni         |60 giorni         |

> [!NOTE]
> Le riunioni di Microsoft Teams hanno un limite di tempo di 30 ore.

## <a name="teams-live-events"></a>Eventi live in Teams

|Funzionalità     | Limite massimo |
|------------|---------------|
|Dimensioni del gruppo di destinatari | 10.000 partecipanti |
|Durata dell'evento | 4 ore |
|Eventi live simultanei eseguiti in un'organizzazione di Microsoft 365 o Office 365<sup>1</sup> | 15 |

<sup>1</sup> You can schedule as many Live Events as you want, but you can only run 15 at a time. As soon as the producer joins a live event, it's considered to be running. The producer who attempts to join the 16th live event gets an error.

Per altre informazioni sugli eventi live, vedere [Eventi live di Teams](teams-live-events/plan-for-teams-live-events.md#teams-live-events). Vedere anche [Pianificare un evento live di Teams](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).

> [!IMPORTANT]
> **Aumento del limite degli eventi live di Microsoft 365**
>
> **Per continuare a soddisfare le esigenze dei nostri clienti, estenderemo gli incrementi del limite temporaneo per gli eventi live, inclusi fino al 31 dicembre 2022, tra cui**:
>
>- Supporto agli eventi fino a 20.000 partecipanti
>- 50 eventi possono avere luogo contemporaneamente in uno stesso tenant
>- Durata degli eventi fino a 16 ore per trasmissione
>
> Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).

## <a name="presence-in-outlook"></a>Presenza in Outlook

Teams presence in Outlook is supported on the Outlook 2013 desktop app and later. To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).

## <a name="storage"></a>Archiviazione

Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.

> [!NOTE]
> Ogni [canale privato](./private-channels.md) include un proprio sito di SharePoint, in precedenza denominato “raccolta siti”.

If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams. Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.

By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed. (For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)

Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team. Here are the applicable storage limits for SharePoint Online.

|Funzionalità                 |Microsoft 365 Business Basic  |Microsoft 365 Business Standard   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Archiviazione                 |1 TB per ogni organizzazione e 10 GB per ogni licenza acquistata  |1 TB per ogni organizzazione e 10 GB per ogni licenza acquistata  |1 TB per ogni organizzazione e 10 GB per ogni licenza acquistata   |1 TB per ogni organizzazione e 10 GB per ogni licenza acquistata |1 TB per ogni organizzazione e 10 GB per ogni licenza acquistata  |1 TB per ogni organizzazione           |
|Spazio di archiviazione per i file di Teams |Fino a 25 TB per sito o gruppo |Fino a 25 TB per sito o gruppo |Fino a 25 TB per sito o gruppo |Fino a 25 TB per sito o gruppo |Fino a 25 TB per sito o gruppo |Fino a 25 TB per sito o gruppo |
|Limite di caricamento file (per file)    |250 GB    |250 GB    |250 GB    |250 GB    |250 GB    |250 GB    |

I canali sono supportati da cartelle all'interno del sito di SharePoint Online, in precedenza denominato “raccolta siti”, creato per il team, quindi le schede dei file all'interno dei canali condividono i limiti di archiviazione del team a cui appartengono.

Per altre informazioni, vedere [Limiti di SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## <a name="class-teams"></a>Team di classe

Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching. More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).

Un team di classe è un tipo di modello con altre app incluse e con limiti distinti per il numero di membri del team.

> [!NOTE]
> Per usare i team di classe è necessaria una [licenza Microsoft Office 365 per l'istruzione](https://www.microsoft.com/education/products/office).

Nella tabella seguente sono elencati i limiti per i team di classe:

|Funzionalità  |Limite massimo  |
|---------|---------|
|Numero di membri in un team    | Vedere la sezione di questo articolo [team e canali](#teams-and-channels)        |
|Numero di membri che possono utilizzare le attività in un team di classe    | 300        |
|Numero di membri che usano un blocco appunti di OneNote per la classe in un team di classe     |300         |

A class team can support more than 300 members. However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.

## <a name="tags"></a>Tag

|Funzionalità  |Limite massimo  |
|---------|---------|
|Numero di tag per team    | 100        |
|Numero di tag predefiniti consigliati per ogni team    | 25        |
|Numero di membri del team assegnati a un tag    |200         |
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
