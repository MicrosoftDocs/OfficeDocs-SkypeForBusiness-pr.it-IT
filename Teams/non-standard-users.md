---
title: Teams il comportamento delle app in base ai tipi di utenti
author: guptaashish
ms.author: guptaashish
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Scopri come si comportano le app in Microsoft Teams per diversi tipi di utenti.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: a407564986d5e4c758d39e2684e5c068539bb9dc
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922467"
---
# <a name="microsoft-teams-apps-behavior-based-on-types-of-users"></a>Microsoft Teams il comportamento delle app in base ai tipi di utenti

Teams le app si comportano quando gli utenti guest, esterni (federati) e anonimi sono presenti in un contesto Teams.

* Un **utente guest** è una persona che non è un dipendente, uno studente o un membro dell'organizzazione. e che non ha un account aziendale o dell'istituto di istruzione presso l'organizzazione.

* Un **utente esterno (federato)** appartiene a un altro dominio e non ha accesso alle risorse del team o dei team dell'organizzazione.

  > [!Note]
  > Per un confronto più dettagliato tra utenti guest ed esterni, [vedere Comunicare con gli utenti di altre organizzazioni](./communicate-with-users-from-other-organizations.md).

* Un **utente anonimo** è un concetto nelle riunioni Teams in cui l'utente ha aderito alla riunione tramite un collegamento. L'utente non ha eseguito l'accesso con l'account Microsoft o dell'organizzazione.

## <a name="guest-users"></a>Utenti guest

### <a name="install-update-and-delete-for-guest-users"></a>Installare, aggiornare ed eliminare per gli utenti guest

I guest non possono installare, aggiornare o eliminare app in un contesto condiviso, ad esempio una chat, un canale o una riunione, ma possono accedere all'ambito personale usando le estensioni dei messaggi e i collegamenti diretti. Gli utenti guest non hanno accesso all'app store Teams dall'applicazione desktop Teams, ma possono accedervi con un collegamento diretto.

### <a name="usage-behavior-and-policy-for-guest-users"></a>Comportamento e criteri di utilizzo per gli utenti guest

Gli utenti guest possono usare un'app se l'app è stata installata da un utente nativo.

#### <a name="bots-installed-to-a-channel"></a>Bot installati in un canale

Gli utenti guest possono menzionare il bot e interagire con le schede adattive.

#### <a name="personal-bots-installed-with-policies"></a>Bot personali installati con criteri

* I guest aderiscono ai criteri di autorizzazione globali e a livello di organizzazione impostati per il tenant host per qualsiasi app. Se un'app è bloccata per l'intera organizzazione host, neanche gli utenti guest possono usare l'app.
* Tutti i bot inclusi nei criteri di configurazione delle app predefiniti globali verranno installati anche per gli utenti guest.
* Dopo l'installazione di un bot, i bot possono comunicare in modo proattivo con i guest e gli ospiti possono comunicare con i bot.
* Non è possibile rimuovere un guest dai criteri di configurazione delle app predefinite globali.
* Per evitare che gli utenti guest accingano ad accedere ai bot, è possibile creare altri criteri di configurazione delle app, assegnarli agli utenti interni e installare bot con i criteri personalizzati.

## <a name="external-federated-users"></a>Utenti esterni (federati)

### <a name="install-update-and-delete-for-external-users"></a>Installare, aggiornare ed eliminare gli utenti esterni

Gli utenti esterni non possono installare, aggiornare o eliminare app in alcun contesto, ad esempio una riunione, una chat, un canale o una riunione personale. Non hanno accesso all'app store Teams dell'organizzazione di hosting.

### <a name="usage-behavior-and-policy-for-external-users"></a>Comportamento e criteri di utilizzo per gli utenti esterni

* Le persone di altre organizzazioni aderiscono ai criteri globali (impostazione predefinita a livello di organizzazione) dell'organizzazione ospitante
* Gli utenti dell'organizzazione di hosting possono aggiungere app nelle chat delle riunioni con persone di altre organizzazioni. Le persone di altre organizzazioni non possono aggiungere app nelle chat delle riunioni, ma possono interagire con bot, schede ed estensioni di messaggi una volta aggiunte alla chat.
* Dopo aver installato un bot in una chat di riunione, può comunicare in modo proattivo con persone di altre organizzazioni in quella chat e queste persone possono comunicare con bot.
* Vengono applicati i criteri dei dati dell'organizzazione di hosting e le procedure di condivisione dei dati di qualsiasi app di terze parti condivisa dall'organizzazione dell'utente.

## <a name="anonymous-users"></a>Utenti anonimi

### <a name="install-update-and-delete-for-anonymous-users"></a>Installare, aggiornare ed eliminare utenti anonimi

Gli utenti anonimi non possono installare, aggiornare o eliminare app nelle riunioni.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Comportamento e criteri di utilizzo per utenti anonimi

Gli utenti anonimi non possono usare direttamente le app nelle riunioni. Gli utenti anonimi ereditano il criterio di autorizzazione predefinito globale a livello utente. Se un'app invia una scheda adattiva nella chat, gli utenti anonimi possono interagire con la scheda. Tali utenti possono interagire con le app nelle riunioni Teams se i criteri di autorizzazione a livello utente abilitano l'app.

Gli utenti anonimi possono interagire solo con le app già disponibili in una riunione e non possono acquisire e gestire tali app. Gli utenti nativi possono continuare a usare le app per le riunioni anche quando gli utenti anonimi partecipano a una riunione.

## <a name="see-also"></a>Vedere anche

* [Consentire agli utenti anonimi di partecipare alle riunioni](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).
* [Gestire i criteri di configurazione delle app in Microsoft Teams](teams-app-setup-policies.md).
