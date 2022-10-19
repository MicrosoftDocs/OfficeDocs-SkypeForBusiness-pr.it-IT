---
title: Pianificare un evento live in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
search.appverid: MET150
description: Questo articolo offre informazioni sui fattori da prendere in considerazione prima di configurare eventi live in Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 086a8bda521827ac048b8ea9928bd3a0c5e3b81f
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584387"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Pianificare un evento live in Microsoft Teams

Quando si pianificano eventi live di Teams per organizzare riunioni con numerosi partecipanti nell'organizzazione, è necessario considerare diversi fattori prima di procedere alla configurazione.

> [!Note]
> For details about Teams live events on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3). See [prepare your organization](../prepare-network.md) to learn about bandwidth requirements for Teams live events.

## <a name="who-can-attend-create-and-schedule-live-events"></a>Chi può partecipare, creare e pianificare eventi live

Anyone can attend a live event without a license. Read [Admin quick start - Meetings and live events](../quick-start-meetings-live-events.md).

Per la pianificazione di un evento live di Teams, sono necessari i prerequisiti seguenti.

Ecco le licenze che devono essere assegnate per organizzare, produrre o presentare un evento live di Teams:  

- **Per organizzare:** una licenza di Microsoft o Office 365 Enterprise E1, E3 o E5 **[oppure]** una licenza di Microsoft o Office 365 Education A3 o A5. 
- **To produce or present:** A Microsoft or Office 365 Enterprise E1, E3 or E5 license, **[or]** a Microsoft or Office 365 Education A1, A3 or A5 license. The exception to this requirement is guest users can present without a license if the other criteria for [guest users](plan-for-teams-live-events.md#guest-to-present) is met.
- Una licenza di Microsoft Teams - questa licenza è inclusa nelle licenze indicate al primo e al secondo punto dell'elenco.
- Una licenza di Microsoft Stream, necessaria se si prevede di condividere il contenuto in un'app o un dispositivo esterno. Vedere l'articolo sulla [gestione delle licenze di Microsoft Stream](/stream/license-overview). Non è necessaria una licenza di Stream se si utilizzano i servizi codificatori di Teams più recenti per produrre l'evento. 

  Users won't need a Microsoft Stream license assigned if you want users to only record and download the recordings. This will mean that the recordings aren't stored in Microsoft Stream but are instead stored in Azure Media Services (AMS) with a 180-day limit before it's deleted. It's not something at this point that an admin can control or manage to include the ability to delete it.

>[!Note]
> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to OneDrive for Business and SharePoint for meeting recordings.

> [!NOTE]
> Attualmente non ci sono piani di Microsoft 365 Small Business che possono essere usati per creare e organizzare eventi live di Teams.

È importante tenere presente che è necessaria una licenza di Microsoft 365 o Office 365 per partecipare a un evento live come utente autenticato, ma questo requisito dipende dal metodo di produzione usato:

- **Per gli eventi prodotti in Teams o utilizzando un codificatore basato su Teams**  All'utente deve essere assegnata una licenza di Teams.
- **Per gli eventi prodotti in un'app o un dispositivo esterno,** all'utente deve essere assegnata una licenza di Stream.

> [!NOTE]
> Gli eventi live di Teams sono ora disponibili per le organizzazioni GCC (Government Cloud Community) degli Stati Uniti.

Per altre informazioni sulle licenze, vedere [Licenze per i componenti aggiuntivi di Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

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

As a best practice, we recommend that you create a channel for producers and presenters of the live event so they can chat and share information before the event. Guests who don't have Microsoft 365 credentials won't see the Calendar in Teams. To make it easy for them to join the event, producers can post the event link to the channel. Presenters can then open Teams, go to the channel, and then select the link to join the event.

## <a name="who-can-watch-live-events"></a>Chi può assistere agli eventi live

| Visibilità dei partecipanti | Produzione Teams | Produzione in app o dispositivi esterni | Codificatore con tecnologia Teams
|------------------------------|-----------------|----------------------|----------------|
|Pubblica (utenti anonimi)      |  Sì            |  No                  | Sì
|Utenti guest                   |  Sì<sup>1</sup>            |  No                  |  Sì            |
|Tutti gli utenti dell'organizzazione con accesso esterno (federazione) |  Sì<sup>1</sup>|  No                  | Sì            |
|Tutti gli utenti della società           |  Sì            |  Sì                 | Sì                |
|Gruppi/utenti specifici      |  Sì            |  Sì                 | Sì                |

<sup>1</sup> Possono essere invitati solo tramite l'opzione Utenti e gruppi <br>

## <a name="teams-live-events"></a>Eventi live in Teams

La tabella seguente evidenzia le funzionalità e le funzionalità di base offerte negli eventi live

> [!IMPORTANT]
> **Aumento del limite degli eventi live di Microsoft 365**
>
> **Per continuare a soddisfare le esigenze dei nostri clienti, estenderemo gli incrementi del limite temporaneo per gli eventi live, inclusi fino al 31 dicembre 2022, tra cui**:
>
>- Supporto agli eventi fino a 20.000 partecipanti
>- 50 eventi possono avere luogo contemporaneamente in uno stesso tenant
>- Durata degli eventi fino a 16 ore per trasmissione
>
> Additionally, live events with up to 100,000 attendees can be planned through the Microsoft 365 live events assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions). 

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
|Supporto eCDN per partner |&#x2714; (Kollective, Hive, Riverbed) |&#x2714; (Kollective, Hive, Ramp, Riverbed) |&#x2714; (Hive, Kollective, Ramp, Riverbed) |
|Report presenze per i produttori dopo la trasmissione |&#x2714; |&#x2714; |&#x274C; |
|Analisi delle valutazioni dei partecipanti - Votazioni e sondaggi in tempo reale |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> The limits that are set might be changed. Check [Limits and specifications for Teams](../limits-specifications-teams.md).<br/>
<sup>2</sup> È possibile avere fino a 100 relatori e produttori in un evento live, ma solo gli ultimi 10 che sono intervenuti vengono visualizzati nell'elenco.

## <a name="regional-availability"></a>Disponibilità a livello di area geografica

You can use Teams live events in multiple regions across the world. The following information shows availability for event team members and attendees.

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
- Norvegia
- Singapore
- Sudafrica
- Sud Corea
- Svizzera
- Emirati Arabi Uniti
- Regno Unito

**Esclusioni e considerazioni**

- **Posizione dei dati:** le posizioni dei dati di Teams, ad eccezione di quelle elencate sopra, non sono supportate al momento.

## <a name="next-steps"></a>Passaggi successivi

Passare a [Configurare gli eventi live di Teams](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Argomenti correlati

- [Cosa sono gli eventi live di Teams?](what-are-teams-live-events.md)
- [Configurare gli eventi live di Teams](set-up-for-teams-live-events.md)
- [Configurare le impostazioni degli eventi live in Teams](configure-teams-live-events.md)
