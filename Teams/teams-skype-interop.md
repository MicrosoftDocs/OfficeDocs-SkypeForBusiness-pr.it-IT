---
title: Interoperabilità teams e Skype
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Informazioni sulle funzionalità di interoperabilità tra gli utenti di team nell'organizzazione e gli utenti Skype (consumer).
localization_priority: Normal
ms.openlocfilehash: 18031f9d1f4ae9a4e42525f8c722259590349c24
ms.sourcegitcommit: e95519cbcc4078810b251c6725863e4610323319
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2020
ms.locfileid: "48925428"
---
# <a name="teams-and-skype-interoperability"></a>Interoperabilità teams e Skype

Questo articolo offre una panoramica delle funzionalità di interoperabilità tra Microsoft teams e Skype (consumer). Informazioni su come gli utenti del team e gli utenti Skype possono comunicare tramite chat e chiamate e i controlli di amministratore applicabili.

Gli utenti dei team dell'organizzazione possono chattare e chiamare gli utenti Skype usando l'indirizzo di posta elettronica e viceversa.

- Gli utenti del team possono cercare e avviare una conversazione uno-a-uno solo testo o una chiamata audio/video con un utente Skype.
- Gli utenti di Skype possono cercare e avviare una conversazione uno-a-uno solo testo o una chiamata audio/video con un utente di teams.

Queste funzionalità sono disponibili nei client desktop, Web e mobile (Android e iOS) per entrambi i team e Skype. Per un'esperienza ottimale, è consigliabile Skype versione 8,58 e versioni successive.

> [!NOTE]
> Le funzionalità di interoperabilità teams e Skype descritte in questo articolo non sono disponibili nelle distribuzioni GCC, GCC High o DOD o in ambienti cloud privati.

## <a name="chat-and-calling-experience"></a>Esperienza di chat e chiamate

Ecco una panoramica dell'esperienza di chat e chiamate.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>L'utente di teams avvia una chat o una chiamata con un utente Skype

Gli utenti di teams possono cercare un utente Skype digitando l'indirizzo di posta elettronica in una nuova chat o nella barra di ricerca.  L'utente teams può quindi selezionare l'utente Skype nei risultati della ricerca per avviare una chat o una chiamata.

Un utente Skype può scegliere di non comparire nei risultati della ricerca. In questo caso, non verranno visualizzati nei risultati della ricerca in teams e gli utenti di teams non saranno in grado di trovarli.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>L'utente Skype avvia una chat o una chiamata con un utente di Teams

Gli utenti di Skype possono cercare e avviare una chat con un utente di teams usando l'indirizzo di posta elettronica. L'utente di Teams riceve una notifica di avere un nuovo messaggio da un utente Skype e deve prima accettare il messaggio prima che possa rispondere.

- Se l'utente teams seleziona **accetta** , la conversazione viene accettata e entrambi gli utenti possono chattare e chiamarsi a vicenda.
- Se l'utente teams seleziona il **blocco** , la conversazione viene bloccata e i messaggi e le chiamate successivi dell'utente Skype sono bloccati.
- Se l'utente teams seleziona **Visualizza messaggi** , il messaggio viene visualizzato in teams, che consente all'utente di decidere se accettare o bloccare la conversazione.

> [!NOTE]
> Se l'aggiornamento è stato effettuato da Skype for business a teams e gli utenti sono solo in modalità teams, le chat e le chiamate dagli utenti Skype agli utenti del team vengono recapitate ai team. Se gli utenti sono in modalità isole, le chat e le chiamate dagli utenti Skype agli utenti del team vengono recapitate a Skype for business.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>L'utente di teams blocca o sblocca un utente Skype

Dopo che un utente di teams accetta o blocca la richiesta di conversazione iniziale di un utente Skype, può scegliere di bloccare o sbloccare la persona in qualsiasi momento. Possono eseguire questa operazione sia nella conversazione che nelle impostazioni di privacy in teams. Gli utenti di Skype non sapranno che sono stati bloccati.

Gli utenti di Skype bloccati, insieme ad altre persone e ai numeri di telefono PSTN (Public Switched Telephone Network) che un utente di Teams ha bloccato, sono elencati nell'elenco contatti bloccati dell'utente in teams.

## <a name="limitations"></a>Limitazioni

- Le conversazioni sono di solo testo. Questo significa che non ci sono formattazione RTF, @mentions, emoji o altre caratteristiche di chat disponibili in un' [esperienza di chat di Team nativi](native-chat-for-external-users.md).
- Le conversazioni sono solo uno-a-uno. Le chat di gruppo non sono supportate.
- Gli utenti di teams e gli utenti Skype non possono vedere la presenza dell'altro.
- La ricerca di utenti Skype tramite l'ID Skype o il numero di telefono non è supportata.
- Gli utenti di Skype non possono chiamare gli utenti del team che hanno configurato l'inoltro di chiamata al numero di un altro utente, un numero di delegato o un numero PSTN (Public Switched Telephone Network).  È supportata solo la segreteria telefonica.
- L'escalation di interoperabilità, i gruppi e le riunioni non sono supportati.
- La possibilità per un delegato di chiamare un utente Skype per conto di un utente di teams non è supportata.
- La condivisione dello schermo con la chat non è supportata.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Impostare se gli utenti del team possono comunicare con utenti Skype

Come amministratore, puoi usare l'interfaccia di amministrazione di Microsoft teams o PowerShell per impostare le impostazioni di accesso esterno per controllare se gli utenti dei team dell'organizzazione possono comunicare con gli utenti Skype. Per impostazione predefinita, questa funzionalità è attivata per i nuovi tenant. Tuttavia, c'è un prerequisito che il record SRV DNS seguente debba essere configurato dall'amministratore IT, se non è già disponibile per il dominio, ad esempio _sipfederationtls. contoso. com.  

**Servizio** : sipfederationtls<br/>
**Protocollo** : TCP<br/>
**Priorità** : 100<br/>
**Peso** : 1<br/>
**Porta** : 5061<br/>
**Destinazione** : sipfed.online.Lync.com

Se l'aggiornamento è stato effettuato da Skype for business a teams, le impostazioni di comunicazione esterna configurate nell'interfaccia di amministrazione di Skype for business vengono migrate in teams.

### <a name="in-the-microsoft-teams-admin-center"></a>Nell'interfaccia di amministrazione di Microsoft Teams

Nell'interfaccia di amministrazione di Microsoft teams accedere a **impostazioni a livello di organizzazione** per  >  **l'accesso esterno** e quindi attivare **gli utenti in grado di comunicare con gli utenti Skype**. Per istruzioni dettagliate su come configurare questa e altre impostazioni di accesso esterno, vedere [gestire l'accesso esterno in teams](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains).

### <a name="using-powershell"></a>Utilizzo di PowerShell

Eseguire le operazioni seguenti: 
1. Usa il cmdlet [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) insieme al ```EnablePublicCloudAccess``` parametro per controllare se gli utenti del team possono comunicare con gli utenti Skype. Impostando il parametro per ```true``` consentire agli utenti di comunicare con utenti Skype. Puoi usare il ```EnablePublicCloudAudioVideoAccess``` parametro per abilitare/disabilitare le chiamate audio/video.

2. Usa il cmdlet [set-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) insieme al ```Provider``` parametro impostato in ```"WindowsLive"``` modo che gli utenti dei team possano comunicare con gli utenti Skype.

## <a name="related-topics"></a>Argomenti correlati

- [Gestire l'accesso esterno in teams](manage-external-access.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
