---
title: Interoperabilità tra Teams e Skype
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
description: Informazioni sulle funzionalità di interoperabilità tra gli utenti di Teams nell'organizzazione e gli utenti Skype (Consumer).
localization_priority: Normal
ms.openlocfilehash: 8bb6a83eddc60ff680d1a08c7266e082dd8b0188
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055648"
---
# <a name="teams-and-skype-interoperability"></a>Interoperabilità tra Teams e Skype

In questo articolo viene fornita una panoramica delle funzionalità di interoperabilità tra Microsoft Teams e Skype (Consumer). Informazioni su come gli utenti di Teams e Skype possono comunicare tramite chat, chiamate e i controlli di amministrazione applicabili.

Gli utenti di Teams nella tua organizzazione possono chattare con gli utenti Skype e chiamarli utilizzando il loro indirizzo e-mail e viceversa.

- Gli utenti di Teams possono cercare e avviare una conversazione tra due persone o una chiamata audio/video con un utente Skype.
- Gli utenti Skype possono cercare e avviare una conversazione tra due persone o una chiamata audio/video con un utente di Teams.

Queste funzionalità sono disponibili nei client desktop, Web e per dispositivi mobili (Android e iOS) sia per Teams che per Skype. Per un'esperienza ottimale, consigliamo Skype 8.58 e versioni successive.

> [!NOTE]
> Le funzionalità di interoperabilità di Teams e Skype ci illustrate in questo articolo non sono disponibili nelle distribuzioni GCC, GCC High o DOD o negli ambienti cloud privati.

## <a name="chat-and-calling-experience"></a>Esperienza di chat e chiamate

Ecco una panoramica dell'esperienza di chat e chiamate.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Un utente di Teams avvia una chat o una chiamata con un utente Skype

Gli utenti di Teams possono cercare un utente Skype digitando il proprio indirizzo e-mail in una nuova chat o nella barra di ricerca.  L'utente di Teams può quindi selezionare l'utente Skype nei risultati della ricerca per avviare una chat o chiamare con l'utente.

Un utente Skype può scegliere di non comparire nei risultati della ricerca. In questo caso, non verranno visualizzati nei risultati della ricerca in Teams e gli utenti di Teams non saranno in grado di trovarli.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Un utente Skype avvia una chat o una chiamata con un utente di Teams

Gli utenti Skype possono cercare e avviare una chat con un utente di Teams usando il proprio indirizzo di posta elettronica. All'utente di Teams viene notificato di avere un nuovo messaggio da parte di un utente Skype e deve prima accettare il messaggio prima di poter rispondere.

- Se l'utente di Teams seleziona **Accetta,** la conversazione viene accettata ed entrambi gli utenti possono chattare e chiamarsi tra loro.
- Se l'utente di Teams seleziona **Blocca,** la conversazione viene bloccata e i messaggi e le chiamate successive di quell'utente Skype vengono bloccati.
- Se l'utente di Teams **seleziona** Visualizza messaggi, il messaggio viene visualizzato in Teams, che aiuta l'utente a decidere se accettare o bloccare la conversazione.

> [!NOTE]
> Se hai effettuato l'aggiornamento da Skype for Business a Teams e i tuoi utenti sono in modalità Solo Teams, le chat e le chiamate dagli utenti Skype agli utenti di Teams vengono recapitate a Teams. Se gli utenti sono in modalità Isole, le chat e le chiamate dagli utenti Skype agli utenti di Teams vengono recapitate a Skype for Business.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Gli utenti di Teams bloccano o sbloccano un utente Skype

Dopo che un utente di Teams accetta o blocca la richiesta di conversazione iniziale da parte di un utente Skype, può scegliere di bloccare o sbloccare quella persona in qualsiasi momento. Possono farlo sia nella conversazione che nelle impostazioni di privacy in Teams. Gli utenti Skype non sapranno che sono stati bloccati.

Gli utenti Skype bloccati, insieme ad altre persone e ai numeri di telefono PSTN (Public Switched Telephone Network) bloccati da un utente di Teams, sono elencati nell'elenco dei contatti bloccati dell'utente in Teams.

## <a name="limitations"></a>Limitazioni

- Le conversazioni sono solo testuali. Questo significa che non esiste formattazione rtf, @mentions, emoji o altre funzionalità di chat disponibili in un'esperienza di chat nativa di [Teams.](native-chat-for-external-users.md)
- Le conversazioni sono una sola volta. Le chat di gruppo non sono supportate.
- Gli utenti di Teams e gli utenti Skype non possono vedere la presenza degli altri utenti.
- La ricerca di utenti Skype utilizzando il proprio ID Skype o il numero di telefono non è supportata.
- Gli utenti Skype non possono chiamare gli utenti di Teams che configurano l'inoltro di chiamata al numero di un altro utente, a un numero di delegato o a un numero PSTN (Public Switched Telephone Network).  È supportata solo la segreteria telefonica.
- Le escalation di interoperabilità, le chiamate di gruppo e le riunioni non sono supportate.
- La possibilità per un delegato di chiamare un utente Skype per conto di un utente di Teams non è supportata.
- La condivisione dello schermo con la chat non è supportata.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Stabilire se gli utenti di Teams possono comunicare con gli utenti Skype

Come amministratore, puoi usare l'interfaccia di amministrazione di Microsoft Teams o PowerShell per configurare le impostazioni di accesso esterno per controllare se gli utenti di Teams nella tua organizzazione possono comunicare con gli utenti Skype. Per impostazione predefinita, questa funzionalità è attivata per i nuovi tenant. Esiste tuttavia un prerequisito che il record SRV DNS seguente deve essere configurato dall'amministratore IT se non è già disponibile per il dominio, ad esempio _sipfederationtls.contoso.com.  

**Servizio**: sipfederationtls<br/>
**Protocollo:** TCP<br/>
**Priorità**: 100<br/>
**Peso**: 1<br/>
**Porta:** 5061<br/>
**Destinazione:** sipfed.online.lync.com

Se è stato eseguito l'aggiornamento da Skype for Business a Teams, le impostazioni per le comunicazioni esterne configurate nell'interfaccia di amministrazione di Skype for Business vengono migrate a Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>Nell'interfaccia di amministrazione di Microsoft Teams

Nell'interfaccia di amministrazione di Microsoft Teams, vai a Impostazioni **a** livello di organizzazione Accesso esterno, quindi attiva l'accesso esterno per consentire agli utenti di  >  comunicare con gli utenti **Skype.** Per istruzioni dettagliate su come configurare questa e altre impostazioni di accesso esterno, vedere [Gestire l'accesso esterno in Teams.](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains)

### <a name="using-powershell"></a>Utilizzo di PowerShell

Eseguire le operazioni seguenti: 
1. Usa il cmdlet [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) insieme al parametro per controllare se gli utenti ```EnablePublicCloudAccess``` di Teams possono comunicare con gli utenti Skype. L'impostazione del parametro ```true``` su consente agli utenti di Teams di comunicare con gli utenti Skype. È possibile usare il ```EnablePublicCloudAudioVideoAccess``` parametro per abilitare/disabilitare le chiamate audio/video.

2. Usare il cmdlet [Set-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) insieme al parametro impostato per consentire agli utenti di Teams di ```Provider``` comunicare con gli utenti ```"WindowsLive"``` Skype.

## <a name="related-topics"></a>Argomenti correlati

- [Gestire l'accesso esterno in Teams](manage-external-access.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
