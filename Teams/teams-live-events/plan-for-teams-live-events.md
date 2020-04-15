---
title: Pianificare eventi dinamici in Microsoft Teams
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
localization_priority: Normal
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Informazioni sui fattori da prendere in considerazione prima di configurare gli eventi dinamici in Microsoft teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2f70a7a2be51045f616ebb4cedc5baf46dbe101d
ms.sourcegitcommit: 56ceda54ca48d2984298d4d1f26017c0147d4431
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2020
ms.locfileid: "43505623"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Pianificare eventi dinamici in Microsoft Teams

Quando si pianificano eventi live di teams per organizzare riunioni di grandi dimensioni nell'organizzazione, è necessario prendere in considerazione diversi fattori prima di iniziare a configurare il tutto. 

## <a name="who-can-create-and-schedule-live-events"></a>Chi può creare e pianificare eventi Live? 
Per l'utente sono necessari i prerequisiti seguenti per pianificare un evento di teams Live.

Ecco le licenze che devono essere assegnate:  
- Una licenza di Office 365 Enterprise E1, E3 o E5 o una licenza di Office 365 a3 o a5
- Licenza di Microsoft Teams
- Una licenza Microsoft Stream

> [!IMPORTANT]
> L'utente che crea e pianifica un evento Live deve avere una cassetta postale di Exchange Online.

È importante sapere che è necessaria una licenza di Office 365 per partecipare a un evento dinamico come utente autenticato, ma questo requisito dipende dal metodo di produzione usato:

- **Per gli eventi prodotti in teams**  All'utente deve essere assegnata una licenza teams.
- **Per gli eventi prodotti con un'app o un dispositivo esterno** All'utente deve essere assegnata una licenza Stream.

> [!NOTE]
> Gli eventi live di teams sono ora disponibili per le organizzazioni di community Cloud (GCC) degli Stati Uniti.

Per altre informazioni sulle licenze, vedere [licenze per i componenti aggiuntivi Microsoft teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

L'utente deve avere:
- Pianificazione di riunioni private in teams Enabled (*il parametro TeamsMeetingPolicy-AllowPrivateMeetingScheduling = true*).
- Condivisione video abilitata in riunioni Teams (*il parametro TeamsMeetingPolicy-AllowIPVideo = true*).
- Condivisione dello schermo abilitata in riunioni Teams (*il parametro TeamsMeetingPolicy-ScreenSharingMode = EntireScreen*).
- Programmazione di eventi dinamici in teams Enabled (*il parametro TeamsMeetingBroadcastPolicy-AllowBroadcastScheduling = true*).
- Autorizzazioni per creare eventi dinamici in Stream (per l'app esterna o la produzione di dispositivi).
- Modalità di coesistenza configurata per poter pianificare le riunioni di Team (*isole, riunioni per primo o solo team*).

> [!IMPORTANT]
> Gli utenti anonimi non autenticati non possono essere invitati come produttori o relatori in eventi live di teams. 
 
## <a name="who-can-watch-live-events"></a>Chi può guardare gli eventi Live?

|**Visibilità partecipanti**       |**Produzione di Teams**  |**App esterna o produzione di dispositivi**  |
|------------------------------|-----------------|----------------------|
|Pubblico (utenti anonimi)      |  Sì            |  No                  |
|Utenti guest                   |  Sì            |  No                  |
|Tutti gli utenti della società federata |  Sì<sup>1</sup>|  No                  |
|Tutti gli utenti della società           |  Sì            |  Sì                 |
|Gruppi/utenti specifici      |  Sì            |  Sì                 |

<sup>1</sup> i partecipanti federati possono essere invitati solo tramite persone & gruppo <br>
 
## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Eventi live di teams e Skype meeting broadcast

La tabella seguente evidenzia le funzionalità e le funzionalità principali offerte in eventi live e il modo in cui si differenziano da Skype meeting broadcast. 

|**Capacità**   |**Trasmissione riunione Skype** |**Eventi prodotti in teams** |**Eventi prodotti in un'app o un dispositivo esterno** |
|---------|---------|---------|---------|
|Numero massimo di destinatari |10.000 partecipanti |10.000 partecipanti<sup>1</sup> |10.000 partecipanti<sup>1</sup> |
|Durata massima dell'evento Live |4 ore |4 ore |4 ore |
|Numero massimo di relatori e produttori in un evento Live |10 <sup>2</sup> |10 <sup>2</sup> |10 <sup>2</sup> |
|Numero massimo di eventi live concorrenti per Office 365 tenant |15  | 15  | 15  |
|Creazione di eventi dinamici |   Portale Skype meeting broadcast |Teams, Yammer tramite Teams | Teams, Yammer tramite teams, Stream |
|Coinvolgimento del pubblico-Yammer |&#x2714; |&#x2714; (esperienza integrata) |&#x2714; (esperienza integrata) |
|Coinvolgimento del pubblico – moderato Q & A |&#x2714;  |&#x2714; |&#x2714; |
|Client di produttori in Windows |&#x2714; (Skype for business) |&#x2714; (Teams) |&#x2714; (Stream, teams tramite l'incorporamento del flusso) |
|Client di produttori su Mac |&#x274C;  | &#x2714; (Teams) |&#x2714; (Stream, teams tramite l'incorporamento del flusso) |
|Conteggio partecipanti nell'interfaccia utente del produttore |&#x274C;  |&#x2714; (Teams) |&#x2714; (Stream, teams tramite l'incorporamento del flusso) |
|Consente più relatori |&#x2714; (Skype for business) |&#x2714; (Teams) |N/D  |
|Invitare un relatore durante la riunione |&#x2714; (Skype for business) |&#x274C; |N/D |
|Partecipare a un relatore su Web e mobile |&#x2714; (Skype for business)  |&#x274C; |N/D |
|Relatori/partecipanti federati & Guest |&#x2714; (Skype for business)  |  &#x2714; (Teams) |N/D |
|Relatore-accesso PSTN |&#x274C; |&#x2714; (Teams) |N/D |
|Presentare una schermata |&#x274C; |&#x2714; (Teams) |N/D |
|Presentare un PowerPoint (condivisione PPT) |&#x2714; |&#x274C; (attenuata tramite la condivisione dello schermo) |N/D |
|Registrazione delle riunioni basata su cloud |&#x2714; |&#x2714; |&#x2714; |
|Pubblicazione automatica della registrazione in streaming |&#x274C; |&#x274C; |&#x2714; |
|Didascalie e sottotitoli dinamici |&#x2714; |&#x2714; |&#x274C; |
|Didascalie nelle registrazioni di eventi Live |&#x2714; |&#x2714; |&#x2714; |
|Controlli DVR partecipanti (pausa, rewind) |&#x2714; |&#x2714; |&#x2714; |
|Supporto per i partner eCDN |&#x2714; (hive, Kollective, ramp) |&#x2714; (hive, Kollective, ramp) |&#x2714; (hive, Kollective, ramp) |
|Report di presenza post-broadcast per produttori |&#x2714; |&#x2714; |&#x274C; |
|Analisi del sentimento del pubblico-votazioni in tempo reale & sondaggi |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> i limiti impostati possono essere modificati. Verificare [i limiti e le specifiche per i team](../limits-specifications-teams.md).<br/>
<sup>2</sup> puoi avere fino a 250 relatori e produttori in un evento Live, ma solo gli ultimi 10 che hanno parlato sono presenti nell'elenco.


## <a name="regional-availability"></a>Disponibilità regionale
Puoi usare gli eventi teams Live in più aree geografiche in tutto il mondo. Le informazioni seguenti mostrano la disponibilità per i membri del team dell'evento e i partecipanti. 

> [!IMPORTANT]
> L'area geografica dell'evento viene selezionata automaticamente a seconda dell'organizzazione e della società di Office 365.

**Disponibile in queste aree geografiche**
- America
- Europa/Africa
- Asia Pacifico
- Go local Canada, India, Australia, Giappone, UK

**Esclusioni e considerazioni**
- **Vai ai locali:** Le squadre locali, al di fuori di quelle elencate sopra, non sono attualmente supportate.
- **Cina:** I membri del team dell'evento e i partecipanti non saranno in grado di usare gli eventi live di teams perché Azure CDN non è accessibile in Cina. Una soluzione alternativa consiste nell'usare una connessione VPN aziendale, che consente di ottenere il client connesso alla rete CDN tramite il network aziendale del cliente.

## <a name="next-steps"></a>Passaggi successivi
Andare alla [configurazione per gli eventi live di teams](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Argomenti correlati
- [Cosa sono gli eventi live di Teams?](what-are-teams-live-events.md)
- [Configurare gli eventi live di Teams](set-up-for-teams-live-events.md)
- [Configurare le impostazioni degli eventi dinamici in teams](configure-teams-live-events.md)
