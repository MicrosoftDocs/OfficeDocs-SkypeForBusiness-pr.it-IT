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
ms.reviewer: vinbel
search.appverid: MET150
description: Informazioni sulle funzionalità di interoperabilità tra Teams utenti dell'organizzazione e gli utenti di Skype (consumer).
ms.localizationpriority: medium
ms.openlocfilehash: dd5bb05f1206baf94f2651899d0c49edbf6fe902
ms.sourcegitcommit: 5bb00d639828c744951a39705fefe81ed6698efe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/20/2022
ms.locfileid: "66167270"
---
# <a name="teams-and-skype-interoperability"></a>Interoperabilità di Teams e Skype

Questo articolo offre una panoramica delle funzionalità di interoperabilità tra Microsoft Teams e Skype (Consumer). Informazioni su come Teams gli utenti e Skype possono comunicare tramite chat e chiamate e i controlli di amministrazione applicabili.

Teams gli utenti dell'organizzazione possono chattare e chiamare Skype utenti usando il proprio indirizzo di posta elettronica e viceversa.

- Teams gli utenti possono cercare e avviare una conversazione testuale uno-a-uno o una chiamata audio/video con un utente Skype.
- Skype gli utenti possono cercare e avviare una conversazione testuale uno-a-uno o una chiamata audio/video con un utente Teams.

Queste funzionalità sono disponibili nei client desktop, Web e per dispositivi mobili (Android e iOS) per Teams e Skype. Per un'esperienza ottimale, è consigliabile Skype versione 8.58 e successive.

> [!NOTE]
> Le funzionalità di interoperabilità Teams e Skype illustrate in questo articolo non sono disponibili nelle distribuzioni di GCC, GCC High o DOD o in ambienti cloud privati.

## <a name="chat-and-calling-experience"></a>Esperienza di chat e chiamate

Ecco una panoramica dell'esperienza di chat e chiamate.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teams'utente avvia una chat o una chiamata con un utente Skype

Teams utenti possono cercare un utente Skype digitando il proprio indirizzo di posta elettronica in una nuova chat o nella barra di ricerca.  L'utente Teams può quindi selezionare il Skype utente nei risultati della ricerca per avviare una chat o una chiamata.

Un utente Skype può scegliere di non visualizzare nei risultati della ricerca. In questo caso, non verranno visualizzati nei risultati della ricerca in Teams e Teams utenti non saranno in grado di trovarli.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype utente avvia una chat o una chiamata con un utente Teams

Skype gli utenti possono cercare e avviare una chat con un utente Teams usando il proprio indirizzo di posta elettronica. L'utente Teams riceve una notifica che informa di avere un nuovo messaggio inviato da un utente Skype e deve prima accettare il messaggio prima di potervi rispondere.

- Se l'utente Teams seleziona **Accetta**, la conversazione viene accettata ed entrambi gli utenti possono chattare e chiamarsi.
- Se l'utente Teams seleziona **Blocca**, la conversazione viene bloccata e i messaggi e le chiamate successivi provenienti da tale Skype utente vengono bloccati.
- Se l'utente Teams seleziona **Visualizza messaggi**, il messaggio viene visualizzato in Teams, per consentire all'utente di decidere se accettare o bloccare la conversazione.

> [!NOTE]
> Se hai eseguito l'aggiornamento da Skype for Business a Teams e gli utenti sono in modalità solo Teams, le chat e le chiamate da Skype utenti a Teams utenti vengono recapitate a Teams. Se gli utenti sono in modalità Isole, le chat e le chiamate da Skype utenti a Teams gli utenti vengono recapitati a Skype for Business.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams utente blocca o sblocca un utente Skype

Dopo che un utente Teams accetta o blocca la richiesta di conversazione iniziale di un utente Skype, può scegliere di bloccare o sbloccare tale persona in qualsiasi momento. Possono farlo sia nella conversazione che nelle impostazioni di privacy in Teams. Skype utenti non sanno di essere stati bloccati.

Gli utenti bloccati Skype, insieme ad altri utenti e ai numeri di telefono PSTN (Public Switched Telephone Network) bloccati da un utente Teams, sono elencati nell'elenco contatti bloccati dell'utente in Teams.

## <a name="limitations"></a>Limitazioni

- Le conversazioni sono solo di testo. Questo significa che non esiste una formattazione avanzata, @mentions, emoji o altre funzionalità di chat disponibili in [un'esperienza di chat di Teams nativa](native-chat-for-external-users.md).
- Le conversazioni sono una-a-uno. Le chat di gruppo non sono supportate.
- Teams utenti e Skype utenti non possono vedere la presenza reciproca.
- La ricerca di Skype utenti usando l'ID Skype o il numero di telefono non è supportata.
- Skype utenti non possono chiamare Teams utenti che configurano l'inoltro di chiamata a un altro utente, al numero di un delegato o a un numero PSTN (Public Switched Telephone Network).  È supportata solo la segreteria telefonica.
- L'escalation all'interoperabilità, le chiamate di gruppo e le riunioni non sono supportate.
- La possibilità per un delegato di chiamare un utente Skype per conto di un Teams utente non è supportata.
- La condivisione dello schermo con la chat non è supportata.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Impostare se Teams gli utenti possono comunicare con Skype utenti

Gli amministratori usano l'interfaccia di amministrazione di Microsoft Teams o PowerShell per impostare le impostazioni di accesso esterno per controllare se Teams utenti dell'organizzazione possono comunicare con Skype utenti. Per impostazione predefinita, questa funzionalità è attivata per i nuovi tenant. Esiste tuttavia un prerequisito che il record SRV DNS seguente debba essere configurato dal Amministrazione IT se non è già disponibile per il dominio, ad esempio _sipfederationtls._tcp.contoso.com.  

**Servizio**: sipfederationtls<br/>
**Protocollo**: TCP<br/>
**Priorità**: 100<br/>
**Peso**: 1<br/>
**Porta**: 5061<br/>
**Destinazione**: sipfed.online.lync.com

Se è stato eseguito l'aggiornamento da Skype for Business a Teams, le impostazioni per le comunicazioni esterne configurate nell'interfaccia di amministrazione di Skype for Business vengono spostate in Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>Nell'interfaccia di amministrazione di Microsoft Teams

Nell'interfaccia di amministrazione di Microsoft Teams passare a **Accesso esterno** **utenti** >  e quindi attivare **Gli utenti possono comunicare con Skype utenti**. Per indicazioni dettagliate su come configurare queste e altre impostazioni di accesso esterno, vedere [Gestire l'accesso esterno in Teams](./manage-external-access.md#allow-or-block-domains).

### <a name="using-powershell"></a>Utilizzo di PowerShell

Eseguire le operazioni seguenti: 
1. Utilizza il cmdlet [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) insieme al ```EnablePublicCloudAccess``` parametro per controllare se Teams utenti possono comunicare con Skype utenti. L'impostazione del parametro su consente agli ```true``` utenti Teams di comunicare con Skype utenti. È possibile usare il ```EnablePublicCloudAudioVideoAccess``` parametro per abilitare/disabilitare le chiamate audio/video.

2. Utilizzare il cmdlet [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) insieme al ```Provider``` parametro impostato su ```"WindowsLive"``` in modo che Teams gli utenti possano comunicare con Skype utenti.

## <a name="related-topics"></a>Argomenti correlati

- [Gestire l'accesso esterno in Teams](manage-external-access.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
