---
title: Comportamento delle app di Teams per utenti non standard
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni sul comportamento delle app in Microsoft Teams per gli utenti non standard.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fc4f4f53262127355afa573b0fc2abec6b05e64
ms.sourcegitcommit: 3861d661d32f507bd8479509ed09b1cfcf0b214f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2021
ms.locfileid: "51607518"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a>Comportamento delle app di Microsoft Teams per utenti non standard

Questo articolo descrive il comportamento delle app in Teams quando gli utenti guest, esterni (federati) e anonimi sono presenti in un contesto di Teams.

- Un **utente guest** è una persona che non è un dipendente, uno studente o un membro dell'organizzazione. e che non ha un account aziendale o dell'istituto di istruzione presso l'organizzazione.

- Un **utente esterno (federato)** appartiene a un altro dominio e non ha accesso ai team o alle risorse del team dell'organizzazione.

>[!Note]
> Per un confronto più dettagliato tra utenti guest e utenti esterni, vedere Comunicare [con utenti di altre organizzazioni.](./communicate-with-users-from-other-organizations.md)

- Un **utente anonimo è** un concetto nelle riunioni di Teams in cui l'utente ha partecipato alla riunione tramite un collegamento. L'utente non ha eseguito l'accesso con l'account Microsoft o dell'organizzazione.

## <a name="guest-user-access"></a>Accesso degli utenti guest

### <a name="install-update-and-delete-for-guest-users"></a>Installare, aggiornare ed eliminare per gli utenti guest

Gli utenti guest non possono installare, aggiornare o eliminare app in un contesto condiviso, ad esempio una chat, un canale o una riunione. Possono installare, aggiornare o eliminare le app nell'ambito personale usando le estensioni dei messaggi e i collegamenti diretti. Gli utenti guest non hanno accesso all'App Store di Teams.

### <a name="usage-behavior-and-policy-for-guest-users"></a>Comportamento di utilizzo e criteri per gli utenti guest

Gli utenti guest possono usare un'app se l'app è stata installata da un utente nativo.

I bot possono inviare messaggi proattivi agli utenti guest, ma gli utenti guest non possono interagire con il bot. Gli utenti guest non possono inviare messaggi al bot 1:1, @ menzionare il bot o interagire con schede adattive che comunicano con il bot.

Gli utenti guest aderiscono ai criteri di autorizzazione globali e a livello di organizzazione impostati per il tenant host per qualsiasi app. In altre parole, se un'app è bloccata per l'intera organizzazione host, gli utenti guest non possono usare l'app.

I criteri di configurazione non si applicano agli utenti guest. Questo significa che l'app aggiunta dall'amministratore dai criteri predefiniti non influisce sugli utenti guest.

## <a name="external-federated-user-access"></a>Accesso utente esterno (federato)

### <a name="install-update-and-delete-for-external-users"></a>Installare, aggiornare ed eliminare utenti esterni

Gli utenti esterni non possono installare, aggiornare o eliminare app in qualsiasi contesto, ad esempio una riunione, una chat, un canale o una chat personale. Non hanno accesso all'app store di Teams.

### <a name="usage-behavior-and-policy-for-external-users"></a>Comportamento di utilizzo e criteri per gli utenti esterni

Gli utenti esterni non possono usare le app di Teams e quando un utente esterno viene aggiunto a un contesto con utenti nativi, tutti gli utenti, nativi ed esterni, non possono più usare le app.

Gli utenti esterni non sono influenzati dai criteri delle app, perché non possono usare le app di Teams.

## <a name="anonymous-user-in-meetings-access"></a>Accesso a utenti anonimi nelle riunioni

### <a name="install-update-and-delete-for-anonymous-users"></a>Installare, aggiornare ed eliminare utenti anonimi

Gli utenti anonimi non possono installare, aggiornare o eliminare app nelle riunioni.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Comportamento di utilizzo e criteri per gli utenti anonimi

Gli utenti anonimi non possono usare direttamente le app nelle riunioni. Gli utenti nativi possono continuare a usare le app riunioni se sono presenti utenti anonimi. Se un'app invia una scheda adattiva nella chat, gli utenti anonimi possono interagire con la scheda Per altre informazioni, vedere Consentire agli utenti anonimi di [partecipare alle riunioni.](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)

Gli utenti anonimi erediteranno i criteri di autorizzazione predefiniti globali a livello di utente. Possono interagire con le app nelle riunioni di Teams se i criteri di autorizzazione a livello di utente hanno abilitato l'app. Gli utenti anonimi possono interagire solo con app già disponibili in una riunione e che non possono acquisire e/o gestire queste app.
