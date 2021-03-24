---
title: Interoperabilità di Teams e Skype
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
description: Scopri le funzionalità di interoperabilità tra gli utenti di Teams nella tua organizzazione e gli utenti Skype (consumer).
localization_priority: Normal
ms.openlocfilehash: e3203c03043dbcdb04370cf3aa26b435fad4a728
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093956"
---
# <a name="teams-and-skype-interoperability"></a>Interoperabilità di Teams e Skype

Questo articolo offre una panoramica delle funzionalità di interoperabilità tra Microsoft Teams e Skype (Consumer). Scopri in che modo gli utenti di Teams e Skype possono comunicare tramite chat e chiamate e i controlli di amministrazione applicabili.

Gli utenti di Teams nella tua organizzazione possono chattare e chiamare gli utenti Skype usando il loro indirizzo e-mail e viceversa.

- Gli utenti di Teams possono cercare e avviare una conversazione di testo uno-a-uno o una chiamata audio/video con un utente Skype.
- Gli utenti Skype possono cercare e avviare una conversazione di testo uno-a-uno o una chiamata audio/video con un utente di Teams.

Queste funzionalità sono disponibili nei client desktop, Web e mobili (Android e iOS) sia per Teams che per Skype. Per un'esperienza ottimale, consigliamo Skype versione 8.58 e successive.

> [!NOTE]
> Le funzionalità di interoperabilità di Teams e Skype descritte in questo articolo non sono disponibili nelle distribuzioni GCC, GCC High o DOD o in ambienti cloud privati.

## <a name="chat-and-calling-experience"></a>Esperienza di chat e chiamate

Ecco una panoramica dell'esperienza di chat e chiamate.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>L'utente di Teams avvia una chat o una chiamata con un utente Skype

Gli utenti di Teams possono cercare un utente Skype digitando il proprio indirizzo e-mail in una nuova chat o nella barra di ricerca.  L'utente di Teams può quindi selezionare l'utente Skype nei risultati della ricerca per avviare una chat o una chiamata con loro.

Un utente Skype può scegliere di non comparire nei risultati della ricerca. In questo caso, non verranno visualizzati nei risultati della ricerca in Teams e gli utenti di Teams non saranno in grado di trovarli.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>L'utente Skype avvia una chat o una chiamata con un utente di Teams

Gli utenti Skype possono cercare e avviare una chat con un utente di Teams usando il loro indirizzo e-mail. L'utente di Teams viene avvisato di avere un nuovo messaggio da un utente Skype e deve prima accettare il messaggio prima di poter rispondere.

- Se l'utente di Teams seleziona **Accetta**, la conversazione viene accettata ed entrambi gli utenti possono chattare e chiamarsi.
- Se l'utente di Teams seleziona **Blocca**, la conversazione viene bloccata e i messaggi e le chiamate successive di quell'utente Skype vengono bloccati.
- Se l'utente di Teams **seleziona** Visualizza messaggi , il messaggio viene visualizzato in Teams, che consente all'utente di decidere se accettare o bloccare la conversazione.

> [!NOTE]
> Se hai eseguito l'aggiornamento da Skype for Business a Teams e i tuoi utenti sono in modalità Solo Teams, le chat e le chiamate dagli utenti Skype agli utenti di Teams vengono recapitate a Teams. Se gli utenti sono in modalità Isole, le chat e le chiamate dagli utenti Skype agli utenti di Teams vengono recapitate in Skype for Business.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Gli utenti di Teams bloccano o sbloccano un utente Skype

Dopo che un utente di Teams accetta o blocca la richiesta di conversazione iniziale da un utente Skype, può scegliere di bloccare o sbloccare la persona in qualsiasi momento. Possono farlo nella conversazione o nelle impostazioni di privacy in Teams. Gli utenti Skype non sapranno che sono stati bloccati.

Gli utenti Skype bloccati, insieme ad altre persone e ai numeri di telefono PSTN (Public Switched Telephone Network) bloccati da un utente di Teams, sono elencati nell'elenco dei contatti bloccati dell'utente in Teams.

## <a name="limitations"></a>Limitazioni

- Le conversazioni sono solo testo. Questo significa che non esiste una formattazione completa, @mentions, emoji o altre funzionalità di chat disponibili in un'esperienza di chat nativa di [Teams.](native-chat-for-external-users.md)
- Le conversazioni sono solo uno-a-uno. Le chat di gruppo non sono supportate.
- Gli utenti di Teams e gli utenti Skype non possono vedere la presenza reciproca.
- La ricerca di utenti Skype usando il proprio ID Skype o il numero di telefono non è supportata.
- Gli utenti Skype non possono chiamare gli utenti di Teams che configurano l'inoltro di chiamata al numero di un altro utente, al numero di un delegato o a un numero PSTN (Public Switched Telephone Network).  È supportata solo la segreteria telefonica.
- L'escalation di interoperabilità, le chiamate di gruppo e le riunioni non sono supportate.
- La possibilità per un delegato di chiamare un utente Skype per conto di un utente di Teams non è supportata.
- La condivisione dello schermo con la chat non è supportata.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Specificare se gli utenti di Teams possono comunicare con gli utenti Skype

L'amministratore usa l'interfaccia di amministrazione di Microsoft Teams o PowerShell per impostare le impostazioni di accesso esterno per controllare se gli utenti di Teams dell'organizzazione possono comunicare con gli utenti Skype. Per impostazione predefinita, questa funzionalità è attivata per i nuovi tenant. Tuttavia, esiste un prerequisito che il record SRV DNS seguente deve essere configurato dall'amministratore IT se non è già disponibile per il dominio, ad esempio _sipfederationtls.contoso.com.  

**Servizio**: sipfederationtls<br/>
**Protocollo**: TCP<br/>
**Priorità**: 100<br/>
**Peso**: 1<br/>
**Porta**: 5061<br/>
**Destinazione**: sipfed.online.lync.com

Se è stato eseguito l'aggiornamento da Skype for Business a Teams, le impostazioni di comunicazione esterna configurate nell'interfaccia di amministrazione di Skype for Business vengono migrate in Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>Nell'interfaccia di amministrazione di Microsoft Teams

Nell'interfaccia di amministrazione di Microsoft Teams passare **a** Impostazioni a livello di organizzazione Accesso esterno e quindi attivare Gli  >  utenti possono comunicare con gli **utenti Skype.** Per istruzioni dettagliate su come configurare questa e altre impostazioni di accesso esterno, vedere [Gestire l'accesso esterno in Teams.](./manage-external-access.md#allow-or-block-domains)

### <a name="using-powershell"></a>Utilizzo di PowerShell

Eseguire le operazioni seguenti: 
1. Usare il cmdlet [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) insieme al parametro per controllare se gli utenti di ```EnablePublicCloudAccess``` Teams possono comunicare con gli utenti Skype. L'impostazione del parametro ```true``` su consente agli utenti di Teams di comunicare con gli utenti Skype. È possibile usare il ```EnablePublicCloudAudioVideoAccess``` parametro per abilitare/disabilitare le chiamate audio/video.

2. Usare il cmdlet [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) insieme al parametro impostato su in modo che gli utenti di Teams possano ```Provider``` comunicare con gli utenti ```"WindowsLive"``` Skype.

## <a name="related-topics"></a>Argomenti correlati

- [Gestire l'accesso esterno in Teams](manage-external-access.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)