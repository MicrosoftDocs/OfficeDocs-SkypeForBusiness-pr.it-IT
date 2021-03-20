---
title: Pianificare un evento live in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
f1.keywords:
- NOCSH
localization_priority: Priority
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
search.appverid: MET150
description: Questo articolo offre informazioni sui fattori da prendere in considerazione prima di configurare eventi live in Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 26192da2b9d11a94f9d37adb7e1a170cb81d3170
ms.sourcegitcommit: 0fddd05334e37b0086ccc0aebe17a26f8e6e8e6c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50884580"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Pianificare un evento live in Microsoft Teams

Quando si pianificano eventi live di Teams per organizzare riunioni con numerosi partecipanti nell'organizzazione, è necessario considerare diversi fattori prima di procedere alla configurazione.

> [!Note]
> Per informazioni dettagliate sugli eventi live di Teams su piattaforme diverse, vedere [Funzionalità di Teams per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3). Per informazioni sui requisiti di larghezza di banda per gli eventi live di Teams, vedere [Preparare l'organizzazione](../prepare-network.md).

## <a name="who-can-attend-create-and-schedule-live-events"></a>Chi può partecipare, creare e pianificare eventi live

Chiunque può partecipare a un evento live senza licenza. Leggere [Guida introduttiva per l'amministratore - Riunioni ed eventi live](../quick-start-meetings-live-events.md).

Per la pianificazione di un evento live di Teams, sono necessari i prerequisiti seguenti.

Ecco le licenze che devono essere assegnate per organizzare, produrre o presentare un evento live di Teams:  

- **Per organizzare:** una licenza di Microsoft o Office 365 Enterprise E1, E3 o E5 **[oppure]** una licenza di Microsoft o Office 365 Education A3 o A5. 
- **Per produrre o presentare:** una licenza di Microsoft o Office 365 Enterprise E1, E3 o E5 **[oppure]** una licenza di Microsoft o Office 365 Education A1, A3 o A5. L'eccezione a questo requisito è che gli utenti guest possono presentare senza licenza se vengono soddisfatti gli altri criteri per gli [utenti guest](plan-for-teams-live-events.md#guest-to-present).
- Una licenza di Microsoft Teams - questa licenza è inclusa nelle licenze indicate al primo e al secondo punto dell'elenco.
- Una licenza di Microsoft Stream, necessaria se si prevede di condividere il contenuto in un'app o un dispositivo esterno. Vedere l'articolo sulla [gestione delle licenze di Microsoft Stream](https://docs.microsoft.com/stream/license-overview).

  Gli utenti non avranno bisogno di una licenza di Microsoft Stream assegnata se si vuole consentire loro solo di registrare e scaricare le registrazioni. Ciò significa che le registrazioni non verranno archiviate in Microsoft Stream ma in Azure Media Services (AMS) con un limite di 180 giorni prima di essere eliminate. Non è qualcosa a questo punto che gli amministratori possono controllare o gestire per includere la possibilità di eliminarle.

>[!Note]
> Il passaggio dall’uso di Microsoft Stream all’uso di [OneDrive for Business e SharePoint per le registrazioni delle riunioni](../tmr-meeting-recording-change.md) avverrà in modo graduale. Al momento del lancio sarà possibile acconsentire esplicitamente all’esperienza. A novembre sarà necessario rifiutarla esplicitamente se si vuole continuare a usare Stream e all'inizio del 2021, sarà chiesto a tutti i clienti di usare OneDrive for Business e SharePoint per le registrazioni delle riunioni.

> [!NOTE]
> Attualmente non ci sono piani di Microsoft 365 Small Business che possono essere usati per creare e organizzare eventi live di Teams.

È importante tenere presente che è necessaria una licenza di Microsoft 365 o Office 365 per partecipare a un evento live come utente autenticato, ma questo requisito dipende dal metodo di produzione usato:

- **Per gli eventi prodotti in Teams,** all'utente deve essere assegnata una licenza di Teams.
- **Per gli eventi prodotti in un'app o un dispositivo esterno,** all'utente deve essere assegnata una licenza di Stream.

> [!NOTE]
> Gli eventi live di Teams sono ora disponibili per le organizzazioni GCC (Government Cloud Community) degli Stati Uniti.

Per altre informazioni sulle licenze, vedere [Licenze per i componenti aggiuntivi di Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).

L'utente deve disporre di:

- Pianificazione delle riunioni private in Teams abilitata (*parametro TeamsMeetingPolicy -AllowPrivateMeetingScheduling = True*).
- Condivisione video abilitata nelle riunioni di Teams (*parametro TeamsMeetingPolicy -AllowIPVideo = True*).
- Condivisione schermo abilitata nelle riunioni di Teams (*parametro TeamsMeetingPolicy -ScreenSharingMode = EntireScreen*).
- Pianificazione degli eventi live in Teams abilitata (*parametro TeamsMeetingBroadcastPolicy -AllowBroadcastScheduling = True*).
- Autorizzazioni per la creazione di eventi live in Stream (per la produzione in app o dispositivi esterni).
- La modalità di coesistenza viene configurata per riuscire a pianificare le riunioni di Teams (*Isole, riunioni al primo posto o solo Teams*).

> [!IMPORTANT]
> Gli utenti anonimi non autenticati non possono essere invitati come produttori o relatori negli eventi live di Teams.

### <a name="guest-to-present"></a>[Utenti guest da presentare](#guest-to-present)

Per rendere un utente guest relatore in un evento live, eseguire le seguenti attività:

1. [Aggiungere l'utente come guest a un team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. Chiedere all'utente di accettare l'invito di guest e accedere al team.
3. [Pianificare l'evento live e aggiungere l'utente guest al gruppo di eventi](https://support.microsoft.com/article/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).

Come procedura consigliata, creare un canale per i produttori e i relatori dell'evento live in modo che possano chattare e condividere informazioni prima dell'evento. Gli utenti che non hanno credenziali di Microsoft 365 non vedranno il calendario in Teams. Per rendere più semplice l'accesso all'evento, i produttori possono pubblicare il collegamento all'evento nel canale. I relatori possono quindi aprire Teams, accedere al canale e infine selezionare sul collegamento per partecipare all'evento.

## <a name="who-can-watch-live-events"></a>Chi può assistere agli eventi live

| Visibilità dei partecipanti | Produzione Teams | Produzione in app o dispositivi esterni |
|------------------------------|-----------------|----------------------|
|Pubblica (utenti anonimi)      |  Sì            |  No                  |
|Utenti guest                   |  Sì<sup>1</sup>            |  No                  |
|Tutti gli utenti dell'organizzazione con accesso esterno (federazione) |  Sì<sup>1</sup>|  No                  |
|Tutti gli utenti della società           |  Sì            |  Sì                 |
|Gruppi/utenti specifici      |  Sì            |  Sì                 |

<sup>1</sup> Possono essere invitati solo tramite l'opzione Utenti e gruppi <br>

## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Eventi live di Teams e Skype Meeting Broadcast

La tabella seguente illustra le funzionalità principali disponibili negli eventi live e le differenze con Skype Meeting Broadcast.

> [!IMPORTANT]
> **Aumento del limite degli eventi live di Microsoft 365**
>
> **Per continuare a supportare le esigenze dei nostri clienti, dal 30 giugno 2021 estenderemo gli incrementi del limite temporaneo per gli eventi live, inclusi**:
>
>- Supporto agli eventi fino a 20.000 partecipanti
>- 50 eventi possono avere luogo contemporaneamente in uno stesso tenant
>- Durata degli eventi fino a 16 ore per trasmissione
>
> Inoltre, tramite il programma di assistenza per gli eventi live di Microsoft 365 è possibile pianificare eventi live con un totale di 100.000 partecipanti. Il team valuterà ogni richiesta e collaborerà con l'utente per determinare le opzioni che potrebbero essere disponibili. [Altre informazioni](https://aka.ms/Stream/Blog/LiveEventOptions). 

| Funzionalità | Skype Meeting Broadcast | Eventi prodotti in Teams | Eventi prodotti in app o dispositivi esterni |
|---------|---------|---------|---------|
|Numero massimo di partecipanti |10.000 partecipanti |10.000 partecipanti<sup>1</sup> |10.000 partecipanti<sup>1</sup> |
|Durata massima dell'evento live |4 ore |4 ore |4 ore |
|Numero massimo di relatori e produttori in un evento live |10 <sup>2</sup> |10 <sup>2</sup> |10 <sup>2</sup> |
|Numero massimo di eventi live concomitanti per l'organizzazione di Microsoft 365 o Office 365 |15  | 15  | 15  |
|Creazione eventi live |   Portale di Skype Meeting Broadcast |Teams, Yammer tramite Teams | Teams, Yammer tramite Teams, Stream |
|Coinvolgimento partecipanti - Yammer |&#x2714; |&#x2714; (esperienza integrata) |&#x2714; (esperienza integrata) |
|Coinvolgimento partecipanti - Domande e risposte con moderatore |&#x2714;  |&#x2714; |&#x2714; |
|Client del produttore in Windows |&#x2714; (Skype for Business) |&#x2714; (Teams) |&#x2714; (Stream, Teams tramite Stream incorporato) |
|Client del produttore su Mac |&#x274C;  | &#x2714; (Teams) |&#x2714; (Stream, Teams tramite Stream incorporato) |
|Numero di partecipanti nell'interfaccia utente del produttore |&#x274C;  |&#x2714; (Teams) |&#x2714; (Stream, Teams tramite Stream incorporato) |
|Consente più relatori |&#x2714; (Skype for Business) |&#x2714; (Teams) |N/D  |
|Invitare un relatore durante la riunione |&#x2714; (Skype for Business) |&#x274C; |N/D |
|Partecipazione del relatore su Web e dispositivi mobili |&#x2714; (Skype for Business)  |&#x274C; |N/D |
|Relatori/Partecipanti con accesso esterno (federazione) |&#x2714; (Skype for Business)  |  &#x2714; (Teams) |N/D |
|Relatore - Accesso PSTN |&#x274C; |&#x2714; (Teams) |N/D |
|Presentare una schermata |&#x274C; |&#x2714; (Teams) |N/D |
|Condividere l'audio di sistema in Windows (disponibile solo in caso di condivisione dello schermo)|&#x274C; |&#x2714; (Teams) |&#x2714; |
|Presentare una presentazione di PowerPoint (condivisione PPT) |&#x2714; |&#x274C; (attenuato tramite condivisione dello schermo) |N/D |
|Registrazione delle riunioni basate sul cloud |&#x2714; |&#x2714; |&#x2714; |
|Pubblicazione automatica delle registrazioni su Stream  |&#x274C; |&#x274C; |&#x2714; |
|Didascalie e sottotitoli in tempo reale |&#x2714; |&#x2714; |&#x274C; |
|Didascalie nelle registrazioni degli eventi live |&#x2714; |&#x2714; |&#x2714; |
|Controlli DVR dei partecipanti (pausa, riavvolgimento) |&#x2714; |&#x2714; |&#x2714; |
|Supporto eCDN per partner |&#x2714; (Kollective, Hive, Riverbed) |&#x2714; (Kollective, Hive, Riverbed) |&#x2714; (Hive, Kollective, Ramp, Riverbed) |
|Report presenze per i produttori dopo la trasmissione |&#x2714; |&#x2714; |&#x274C; |
|Analisi delle valutazioni dei partecipanti - Votazioni e sondaggi in tempo reale |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> I limiti impostati potrebbero essere modificati. Consultare [Limiti e specifiche per Teams](../limits-specifications-teams.md).<br/>
<sup>2</sup> È possibile avere fino a 100 relatori e produttori in un evento live, ma solo gli ultimi 10 che sono intervenuti vengono visualizzati nell'elenco.

## <a name="regional-availability"></a>Disponibilità a livello di area geografica

È possibile usare la funzione degli eventi live di Teams in più aree geografiche del mondo. Le informazioni seguenti mostrano la disponibilità per i partecipanti e i membri del team dell'evento.

> [!IMPORTANT]
> L'area geografica dell'evento viene selezionata automaticamente in base all'organizzatore e alla posizione del tenant di Microsoft 365.

**Disponibile in questi data center regionali**

- Nord America
- America centrale
- Sud America
- Asia Pacifico
- Europa/Africa

**Posizione dei dati per questi paesi/aree geografiche (supportate)**

- Australia
- Brasile
- Canada
- Francia
- Germania
- India
- Giappone
- Sudafrica
- Sud Corea
- Svizzera
- Emirati Arabi Uniti
- Regno Unito

**Questi paesi/aree geografiche e cloud non sono supportati**

- Norvegia
- Government Community Cloud (GCC)-H
- Department of Defense (DOD)

**Esclusioni e considerazioni**

- **Posizione dei dati:** le posizioni dei dati di Teams, ad eccezione di quelle elencate sopra, non sono supportate al momento.
- **Cina:** i partecipanti e i membri del team dell'evento non potranno usare gli eventi live di Teams perché la rete CDN di Azure non è accessibile in Cina. In alternativa, è possibile usare una connessione VPN aziendale che ottiene il client connesso alla rete CDN tramite la rete aziendale del cliente.

## <a name="next-steps"></a>Passaggi successivi

Passare a [Configurare gli eventi live di Teams](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Argomenti correlati

- [Cosa sono gli eventi live di Teams?](what-are-teams-live-events.md)
- [Configurare gli eventi live di Teams](set-up-for-teams-live-events.md)
- [Configurare le impostazioni degli eventi live in Teams](configure-teams-live-events.md)
