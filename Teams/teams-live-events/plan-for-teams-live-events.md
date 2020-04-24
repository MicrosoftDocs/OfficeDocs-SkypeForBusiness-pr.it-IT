---
title: Pianificare un evento live in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/19/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
f1.keywords:
- NOCSH
localization_priority: Priority
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Informazioni sui fattori da prendere in considerazione prima di configurare eventi live in Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: aabd94e8a5c4904f0343e2c8ccb647d632f3fa21
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779965"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Pianificare un evento live in Microsoft Teams

Quando si pianificano eventi live di Teams per organizzare riunioni con numerosi partecipanti nell'organizzazione, è necessario considerare diversi fattori prima di procedere alla configurazione.

## <a name="who-can-attend-create-and-schedule-live-events"></a>Chi può partecipare, creare e pianificare eventi live

Chiunque può partecipare a un evento live senza licenza. Leggere [Guida introduttiva per l'amministratore - Riunioni ed eventi live](../quick-start-meetings-live-events.md).

Per la pianificazione di un evento live di Teams, sono necessari i prerequisiti seguenti.

Ecco le licenze che devono essere assegnate:  

- Una licenza di Office 365 Enterprise E1, E3 o E5 o una licenza di Office 365 A3 o A5
- Una licenza di Microsoft Teams
- Una licenza di Microsoft Stream

> [!IMPORTANT]
> Gli utenti che creano e pianificano un evento live devono disporre di una cassetta postale di Exchange Online.

È importante tenere presente che è necessaria una licenza di Office 365 per partecipare a un evento live come utente autenticato, ma questo requisito dipende dal metodo di produzione utilizzato:

- **Per gli eventi prodotti in Teams,** all'utente deve essere assegnata una licenza di Teams.
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

## <a name="who-can-watch-live-events"></a>Chi può assistere agli eventi live

|**Visibilità dei partecipanti**       |**Produzione in Teams**  |**Produzione in app o dispositivi esterni**  |
|------------------------------|-----------------|----------------------|
|Pubblica (utenti anonimi)      |  Sì            |  No                  |
|Utenti guest                   |  Sì            |  No                  |
|Tutti gli utenti dell'organizzazione con accesso esterno (federazione) |  Sì<sup>1</sup>|  No                  |
|Tutti gli utenti della società           |  Sì            |  Sì                 |
|Gruppi/utenti specifici      |  Sì            |  Sì                 |

<sup>1</sup> I partecipanti con accesso esterno (federazione) possono essere invitati solo tramite l'opzione Utenti e gruppi <br>

## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Eventi live di Teams e Skype Meeting Broadcast

La tabella seguente illustra le funzionalità principali disponibili negli eventi live e le differenze con Skype Meeting Broadcast.

|**Funzionalità**   |**Skype Meeting Broadcast** |**Eventi prodotti in Teams** |**Eventi prodotti in app o dispositivi esterni** |
|---------|---------|---------|---------|
|Numero massimo di partecipanti |10.000 partecipanti |10.000 partecipanti<sup>1</sup> |10.000 partecipanti<sup>1</sup> |
|Durata massima dell'evento live |4 ore |4 ore |4 ore |
|Numero massimo di relatori e produttori in un evento live |10 <sup>2</sup> |10 <sup>2</sup> |10 <sup>2</sup> |
|Numero massimo di eventi live concomitanti per l'organizzazione di Office 365 |15  | 15  | 15  |
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
|Presentare una presentazione di PowerPoint (condivisione PPT) |&#x2714; |&#x274C; (attenuato tramite condivisione dello schermo) |N/D |
|Registrazione delle riunioni basate sul cloud |&#x2714; |&#x2714; |&#x2714; |
|Pubblicazione automatica delle registrazioni su Stream  |&#x274C; |&#x274C; |&#x2714; |
|Didascalie e sottotitoli in tempo reale |&#x2714; |&#x2714; |&#x274C; |
|Didascalie nelle registrazioni degli eventi live |&#x2714; |&#x2714; |&#x2714; |
|Controlli DVR dei partecipanti (pausa, riavvolgimento) |&#x2714; |&#x2714; |&#x2714; |
|Supporto eCDN per partner |&#x2714; (Hive, Kollective, Ramp) |&#x2714; (Hive, Kollective, Ramp) |&#x2714; (Hive, Kollective, Ramp) |
|Report presenze per i produttori dopo la trasmissione |&#x2714; |&#x2714; |&#x274C; |
|Analisi delle valutazioni dei partecipanti - Votazioni e sondaggi in tempo reale |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> I limiti impostati potrebbero essere modificati. Consultare [Limiti e specifiche per Teams](../limits-specifications-teams.md).<br/>
<sup>2</sup> È possibile avere fino a 250 relatori e produttori in un evento live, ma solo gli ultimi 10 che sono intervenuti vengono visualizzati nell'elenco.

## <a name="regional-availability"></a>Disponibilità a livello di area geografica

È possibile usare la funzione degli eventi live di Teams in più aree geografiche del mondo. Le informazioni seguenti mostrano la disponibilità per i partecipanti e i membri del team dell'evento.

> [!IMPORTANT]
> L'area geografica dell'evento viene selezionata automaticamente in base all'organizzatore e a Microsoft 365 o Office 365.

**Disponibile nelle aree geografiche seguenti**

- Americhe
- Europa/Africa
- Asia Pacifico
- Posizione dei dati per Canada, India, Australia, Giappone e Regno Unito

**Esclusioni e considerazioni**

- **Posizione dei dati:** le posizioni dei dati di Teams, ad eccezione di quelle elencate sopra, non sono supportate al momento.
- **Cina:** i partecipanti e i membri del team dell'evento non potranno usare gli eventi live di Teams perché la rete CDN di Azure non è accessibile in Cina. In alternativa, è possibile usare una connessione VPN aziendale che ottiene il client connesso alla rete CDN tramite la rete aziendale del cliente.

## <a name="next-steps"></a>Passaggi successivi

Passare a [Configurare gli eventi live di Teams](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Argomenti correlati

- [Cosa sono gli eventi live di Teams?](what-are-teams-live-events.md)
- [Configurare gli eventi live di Teams](set-up-for-teams-live-events.md)
- [Configurare le impostazioni degli eventi live in Teams](configure-teams-live-events.md)
