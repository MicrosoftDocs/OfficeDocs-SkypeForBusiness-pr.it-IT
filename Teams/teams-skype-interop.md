---
title: Teams e Skype interoperabilità
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: Informazioni sulle funzionalità di interoperabilità tra Teams utenti dell'organizzazione e Skype utenti (consumer).
localization_priority: Normal
ms.openlocfilehash: e3203c03043dbcdb04370cf3aa26b435fad4a728
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093956"
---
# <a name="teams-and-skype-interoperability"></a>Teams e Skype interoperabilità

Questo articolo offre una panoramica delle funzionalità di interoperabilità tra Microsoft Teams e Skype (consumer). Scopri come Teams utenti e Skype utenti possono comunicare tramite chat e chiamate e i controlli di amministrazione applicabili.

Teams utenti dell'organizzazione possono chattare e chiamare Skype utenti usando l'indirizzo di posta elettronica e viceversa.

- Teams utenti possono cercare e avviare una conversazione di testo uno-a-uno o una chiamata audio/video con un Skype utente.
- Skype utenti possono cercare e avviare una conversazione di testo uno-a-uno o una chiamata audio/video con un Teams utente.

Queste funzionalità sono disponibili nei client desktop, Web e per dispositivi mobili (Android e iOS) per Teams e Skype. Per un'esperienza ottimale, è consigliabile Skype versione 8.58 e successive.

> [!NOTE]
> Le Teams e Skype di interoperabilità descritte in questo articolo non sono disponibili nelle distribuzioni GCC, GCC High o DOD o in ambienti cloud privati.

## <a name="chat-and-calling-experience"></a>Esperienza di chat e chiamate

Ecco una panoramica dell'esperienza di chat e chiamate.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teams utente avvia una chat o una chiamata con un Skype utente

Teams utenti possono cercare un Skype digitando il proprio indirizzo di posta elettronica in una nuova chat o nella barra di ricerca.  L Teams utente può quindi selezionare il Skype nei risultati della ricerca per avviare una chat o una chiamata con loro.

Un Skype può scegliere di non comparire nei risultati della ricerca. In questo caso, non verranno visualizzati nei risultati della ricerca in Teams e Teams gli utenti non saranno in grado di trovarli.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype utente avvia una chat o una chiamata con un Teams utente

Skype gli utenti possono cercare e avviare una chat con un Teams utente usando il proprio indirizzo di posta elettronica. L Teams utente viene avvisato di avere un nuovo messaggio da un utente di Skype e deve prima accettare il messaggio prima di poter rispondere.

- Se l Teams'utente seleziona **Accetta**, la conversazione viene accettata ed entrambi gli utenti possono chattare e chiamarsi.
- Se l Teams'utente seleziona Blocca **,** la conversazione viene bloccata e i messaggi e le chiamate successivi da quell'Skype utente vengono bloccati.
- Se l Teams utente seleziona Visualizza messaggi **,** il messaggio viene visualizzato in Teams, che consente all'utente di decidere se accettare o bloccare la conversazione.

> [!NOTE]
> Se è stato eseguito l'aggiornamento da Skype for Business a Teams e gli utenti sono in modalità Solo Teams, le chat e le chiamate degli utenti di Skype Teams vengono recapitate a Teams. Se gli utenti sono in modalità Isole, le chat e le chiamate da Skype utenti a Teams utenti vengono recapitate a Skype for Business.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams utente blocca o sblocca un Skype utente

Dopo che Teams un utente accetta o blocca la richiesta di conversazione iniziale da un utente di Skype, può scegliere di bloccare o sbloccare la persona in qualsiasi momento. Possono farlo nella conversazione o nelle impostazioni di privacy in Teams. Skype gli utenti non sapranno che sono stati bloccati.

Gli utenti Skype bloccati, insieme ad altre persone e ai numeri di telefono PSTN (Public Switched Telephone Network) bloccati da un utente di Teams, sono elencati nell'elenco dei contatti bloccati dell'utente in Teams.

## <a name="limitations"></a>Limitazioni

- Le conversazioni sono solo testo. Questo significa che non è disponibile una formattazione completa, @mentions, emoji o altre funzionalità di chat disponibili in un'esperienza Teams [chat nativa.](native-chat-for-external-users.md)
- Le conversazioni sono solo uno-a-uno. Le chat di gruppo non sono supportate.
- Teams utenti e Skype non possono vedere la presenza degli altri utenti.
- La ricerca Skype utenti usando l'ID Skype o il numero di telefono non è supportato.
- Skype utenti non possono chiamare Teams utenti che configurano l'inoltro di chiamata al numero di un altro utente, a un numero di delegato o a un numero PSTN (Public Switched Telephone Network).  È supportata solo la segreteria telefonica.
- L'escalation di interoperabilità, le chiamate di gruppo e le riunioni non sono supportate.
- La possibilità per un delegato di chiamare un Skype utente per conto di un Teams non è supportata.
- La condivisione dello schermo con la chat non è supportata.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Impostare se gli Teams utenti possono comunicare con Skype utenti

Gli amministratori usano l'interfaccia di amministrazione di Microsoft Teams o PowerShell per impostare le impostazioni di accesso esterno per controllare se gli utenti Teams dell'organizzazione possono comunicare con Skype utenti. Per impostazione predefinita, questa funzionalità è attivata per i nuovi tenant. Tuttavia, esiste un prerequisito che il record SRV DNS seguente deve essere configurato dall'amministratore IT se non è già disponibile per il dominio, ad esempio _sipfederationtls.contoso.com.  

**Servizio**: sipfederationtls<br/>
**Protocollo**: TCP<br/>
**Priorità**: 100<br/>
**Peso**: 1<br/>
**Porta**: 5061<br/>
**Destinazione**: sipfed.online.lync.com

Se è stato eseguito l'aggiornamento da Skype for Business a Teams, le impostazioni delle comunicazioni esterne configurate nell'interfaccia di amministrazione di Skype for Business vengono migrate in Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>Nell'interfaccia di amministrazione di Microsoft Teams

Nell'Microsoft Teams di amministrazione passare a Impostazioni a livello di organizzazione Accesso esterno e quindi attivare Gli utenti possono comunicare con Skype  >   **utenti.** Per istruzioni dettagliate su come configurare questa e altre impostazioni di accesso esterno, vedere Gestire l'accesso esterno [in Teams](./manage-external-access.md#allow-or-block-domains).

### <a name="using-powershell"></a>Utilizzo di PowerShell

Eseguire le operazioni seguenti: 
1. Usare il cmdlet [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) insieme al parametro per controllare se Teams gli utenti possono comunicare con Skype ```EnablePublicCloudAccess``` utenti. L'impostazione del parametro ```true``` su consente Teams utenti di comunicare con Skype utenti. È possibile usare il ```EnablePublicCloudAudioVideoAccess``` parametro per abilitare/disabilitare le chiamate audio/video.

2. Usare il cmdlet [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) insieme al parametro impostato su in modo che Teams gli utenti possano comunicare con Skype ```Provider``` ```"WindowsLive"``` utenti.

## <a name="related-topics"></a>Argomenti correlati

- [Gestire l'accesso esterno in Teams](manage-external-access.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)