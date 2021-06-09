---
title: Teams comportamento delle app per gli utenti non standard
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni sul comportamento delle app Microsoft Teams per gli utenti non standard.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: d7b79371cdc8ff5109bf67b1c78639106a83a95e
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796649"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a>Microsoft Teams delle app per gli utenti non standard

Questo articolo descrive il comportamento delle app in Teams quando gli utenti guest, esterni (federati) e anonimi sono presenti in un Teams locale.

- Un **utente guest** è una persona che non è un dipendente, uno studente o un membro dell'organizzazione. e che non ha un account aziendale o dell'istituto di istruzione presso l'organizzazione.

- Un **utente esterno (federato)** appartiene a un altro dominio e non ha accesso ai team o alle risorse del team dell'organizzazione.

  > [!Note]
  > Per un confronto più dettagliato tra utenti guest e utenti esterni, vedere Comunicare [con utenti di altre organizzazioni.](./communicate-with-users-from-other-organizations.md)

- Un **utente anonimo** è un concetto in Teams riunioni in cui l'utente ha partecipato alla riunione tramite un collegamento. L'utente non ha eseguito l'accesso con l'account Microsoft o dell'organizzazione.

## <a name="guest-users"></a>Utenti guest

### <a name="install-update-and-delete-for-guest-users"></a>Installare, aggiornare ed eliminare per gli utenti guest

Gli utenti guest non possono installare, aggiornare o eliminare app in un contesto condiviso, ad esempio una chat, un canale o una riunione, ma possono accedere all'ambito personale usando le estensioni dei messaggi e i collegamenti diretti. Gli utenti guest non hanno accesso all'app store Teams dall'applicazione desktop Teams, ma possono accedervi con un collegamento diretto.

### <a name="usage-behavior-and-policy-for-guest-users"></a>Comportamento di utilizzo e criteri per gli utenti guest 

Gli utenti guest possono usare un'app se l'app è stata installata da un utente nativo.

#### <a name="bots-installed-to-a-channel"></a>Bot installati in un canale

I bot possono inviare messaggi proattivi agli utenti guest, ma gli utenti guest non possono interagire con il bot. Gli utenti guest non possono inviare messaggi uno a uno al bot, menzionare il bot o interagire con schede adattive che comunicano con il bot.

#### <a name="personal-bots-installed-with-policies"></a>Bot personali installati con i criteri

- Gli utenti guest aderiscono ai criteri di autorizzazione globali e a livello di organizzazione impostati per il tenant host per qualsiasi app. Se un'app è bloccata per l'intera organizzazione host, gli utenti guest non possono usare l'app.
- Tutti i bot inclusi nei criteri di configurazione delle app predefinite globali verranno installati anche per gli guest.
- Dopo l'installazione di un bot, i bot possono comunicare in modo proattivo con gli utenti guest e gli utenti guest possono comunicare di nuovo con i bot.
- Non è possibile rimuovere un guest dai criteri di configurazione dell'app predefiniti globali.
- Per evitare che i guest possano accedere ai bot, è possibile creare altri criteri di configurazione delle app, assegnarli agli utenti interni e installare i bot con i criteri personalizzati.

## <a name="external-federated-users"></a>Utenti esterni (federati)

### <a name="install-update-and-delete-for-external-users"></a>Installare, aggiornare ed eliminare utenti esterni

Gli utenti esterni non possono installare, aggiornare o eliminare app in qualsiasi contesto, ad esempio una riunione, una chat, un canale o una chat personale. Non hanno accesso all'app store Teams dell'organizzazione di hosting.

### <a name="usage-behavior-and-policy-for-external-users"></a>Comportamento di utilizzo e criteri per gli utenti esterni

- Gli utenti di altre organizzazioni aderiscono ai criteri globali dell'organizzazione ospitata (impostazione predefinita a livello di organizzazione)
- Gli utenti dell'organizzazione di hosting possono aggiungere app nelle chat delle riunioni con persone di altre organizzazioni. Le persone di altre organizzazioni non possono aggiungere app nelle chat delle riunioni, ma possono interagire con bot, schede ed estensioni dei messaggi una volta aggiunte alla chat.
- Dopo aver installato un bot in una chat di riunione, può comunicare in modo proattivo con persone di altre organizzazioni nella chat e queste persone possono comunicare con il bot.
- Vengono applicati i criteri dati dell'organizzazione di hosting, nonché le procedure di condivisione dei dati di qualsiasi app di terze parti condivise dall'organizzazione dell'utente.

## <a name="anonymous-users"></a>Utenti anonimi

### <a name="install-update-and-delete-for-anonymous-users"></a>Installare, aggiornare ed eliminare utenti anonimi

Gli utenti anonimi non possono installare, aggiornare o eliminare app nelle riunioni.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Comportamento di utilizzo e criteri per gli utenti anonimi

Gli utenti anonimi non possono usare direttamente le app nelle riunioni. Gli utenti nativi possono continuare a usare le app riunioni se sono presenti utenti anonimi. Se un'app invia una scheda adattiva nella chat, gli utenti anonimi possono interagire con la scheda. Per altre informazioni, vedere [Consentire agli utenti anonimi di partecipare alle riunioni.](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)

Gli utenti anonimi erediteranno i criteri di autorizzazione predefiniti globali a livello di utente. Possono interagire con le app nelle riunioni Teams se i criteri di autorizzazione a livello di utente hanno abilitato l'app. Gli utenti anonimi possono interagire solo con app già disponibili in una riunione e che non possono acquisire e/o gestire queste app.
