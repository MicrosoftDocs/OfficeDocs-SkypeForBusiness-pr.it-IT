---
title: Interoperabilità di Teams e Skype
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Informazioni sulle funzionalità di interoperabilità tra gli utenti di Teams nell'organizzazione e gli utenti Skype (consumer).
ms.localizationpriority: medium
ms.openlocfilehash: 5cbb4bdf492de67131c75c97685317ef8cae866c
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242320"
---
# <a name="teams-and-skype-interoperability"></a>Interoperabilità di Teams e Skype

Questo articolo offre una panoramica delle funzionalità di interoperabilità tra Microsoft Teams e Skype (consumer). Informazioni su come gli utenti di Teams e Skype possono comunicare tramite chat e chiamate e i controlli di amministrazione applicabili.

Gli utenti di Teams nell'organizzazione possono chattare e chiamare gli utenti Skype usando il proprio indirizzo di posta elettronica e viceversa.

- Gli utenti di Teams possono cercare e avviare una conversazione testuale uno-a-uno o una chiamata audio/video con un utente Skype.
- Gli utenti Skype possono cercare e avviare una conversazione testuale uno-a-uno o una chiamata audio/video con un utente di Teams.

Queste funzionalità sono disponibili nei client desktop, Web e per dispositivi mobili (Android e iOS) sia per Teams che per Skype. Per un'esperienza ottimale, è consigliabile skype 8.58 e versioni successive.

> [!NOTE]
> Le funzionalità di interoperabilità Teams e Skype illustrate in questo articolo non sono disponibili nelle distribuzioni di GCC, GCC High o DOD o in ambienti cloud privati.

## <a name="chat-and-calling-experience"></a>Esperienza di chat e chiamate

Ecco una panoramica dell'esperienza di chat e chiamate.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>L'utente di Teams avvia una chat o una chiamata con un utente Skype

Gli utenti di Teams possono cercare un utente Skype digitando il proprio indirizzo di posta elettronica in una nuova chat o nella barra di ricerca.  L'utente di Teams può quindi selezionare l'utente Skype nei risultati della ricerca per avviare una chat o una chiamata.

Un utente Skype può scegliere di non visualizzare nei risultati della ricerca. In questo caso, non verranno visualizzati nei risultati della ricerca in Teams e gli utenti di Teams non saranno in grado di trovarli.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Un utente Skype avvia una chat o una chiamata con un utente di Teams

Gli utenti Skype possono cercare e avviare una chat con un utente di Teams usando il loro indirizzo e-mail. L'utente di Teams riceve una notifica che indica che ha un nuovo messaggio inviato da un utente Skype e deve prima accettare il messaggio prima di poter rispondere.

- Se l'utente di Teams seleziona **Accetta**, la conversazione viene accettata ed entrambi gli utenti possono chattare e chiamarsi.
- Se l'utente di Teams seleziona **Blocca**, la conversazione viene bloccata e i messaggi e le chiamate successivi provenienti da quell'utente Skype vengono bloccati.
- Se l'utente di Teams seleziona **Visualizza messaggi**, il messaggio viene visualizzato in Teams, per consentire all'utente di decidere se accettare o bloccare la conversazione.

> [!NOTE]
> Se hai eseguito l'aggiornamento da Skype for Business a Teams e gli utenti sono in modalità Solo Teams, le chat e le chiamate dagli utenti Skype agli utenti di Teams vengono recapitate a Teams. Se gli utenti sono in modalità Isole, le chat e le chiamate dagli utenti Skype agli utenti di Teams vengono recapitate a Skype for Business.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>L'utente di Teams blocca o sblocca un utente Skype

Dopo che un utente di Teams accetta o blocca la richiesta di conversazione iniziale di un utente Skype, può scegliere di bloccare o sbloccare tale persona in qualsiasi momento. Possono farlo sia nella conversazione che nelle impostazioni di privacy in Teams. Gli utenti Skype non sanno di essere stati bloccati.

Gli utenti Skype bloccati, insieme ad altre persone e numeri di telefono PSTN (Public Switched Telephone Network) bloccati da un utente di Teams, sono elencati nell'elenco contatti bloccati dell'utente in Teams.

## <a name="limitations"></a>Limitazioni

- Le conversazioni sono solo di testo. Ciò significa che non esiste una formattazione avanzata, @mentions, emoji o altre funzionalità di chat disponibili in [un'esperienza di chat nativa di Teams](native-chat-for-external-users.md).
- Le conversazioni sono una-a-uno. Le chat di gruppo non sono supportate.
- Gli utenti di Teams e gli utenti Skype non possono vedere la presenza degli altri utenti.
- La ricerca di utenti Skype con l'ID Skype o il numero di telefono non è supportata.
- Gli utenti Skype non possono chiamare gli utenti di Teams che configurano l'inoltro di chiamata al numero di un altro utente, al numero di un delegato o a un numero PSTN (Public Switched Telephone Network).  È supportata solo la segreteria telefonica.
- L'escalation all'interoperabilità, le chiamate di gruppo e le riunioni non sono supportate.
- La possibilità per un delegato di chiamare un utente Skype per conto di un utente di Teams non è supportata.
- La condivisione dello schermo con la chat non è supportata.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Impostare se gli utenti di Teams possono comunicare con gli utenti Skype

Gli amministratori usano l'interfaccia di amministrazione di Microsoft Teams o PowerShell per impostare le impostazioni di accesso esterno per controllare se gli utenti di Teams nell'organizzazione possono comunicare con gli utenti Skype. Per impostazione predefinita, questa funzionalità è attivata per i nuovi tenant. Esiste tuttavia un prerequisito che il record SRV DNS seguente debba essere configurato dal Amministrazione IT se non è già disponibile per il dominio, ad esempio _sipfederationtls._tcp.contoso.com.  

**Servizio**: sipfederationtls<br/>
**Protocollo**: TCP<br/>
**Priorità**: 100<br/>
**Peso**: 1<br/>
**Porta**: 5061<br/>
**Destinazione**: sipfed.online.lync.com

Se è stato eseguito l'aggiornamento da Skype for Business a Teams, le impostazioni per le comunicazioni esterne configurate nell'interfaccia di amministrazione Skype for Business vengono migrate in Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>Nell'interfaccia di amministrazione di Microsoft Teams

Nell'interfaccia di amministrazione di Microsoft Teams passare a **Accesso esterno** **utenti** >  e quindi attivare **Gli utenti possono comunicare con gli utenti Skype**. Per indicazioni dettagliate su come configurare queste e altre impostazioni di accesso esterno, vedere [Gestire l'accesso esterno in Teams](./manage-external-access.md).

### <a name="using-powershell"></a>Utilizzo di PowerShell

Eseguire le operazioni seguenti: 
1. Utilizza il cmdlet [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) insieme al ```EnablePublicCloudAccess``` parametro per controllare se gli utenti di Teams possono comunicare con gli utenti Skype. L'impostazione del parametro su consente agli ```true``` utenti di Teams di comunicare con gli utenti Skype. È possibile usare il ```EnablePublicCloudAudioVideoAccess``` parametro per abilitare/disabilitare le chiamate audio/video.

2. Usa il cmdlet [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) insieme al ```Provider``` parametro impostato su ```"WindowsLive"``` in modo che gli utenti di Teams possano comunicare con gli utenti Skype.

## <a name="related-topics"></a>Argomenti correlati

- [Gestire l'accesso esterno in Teams](manage-external-access.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
