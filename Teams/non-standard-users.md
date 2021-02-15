---
title: Comportamento delle app Teams per gli utenti non standard
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
ms.openlocfilehash: 683ba9a20c51a23fa1468c07407a389c23dba507
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237499"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a>Comportamento delle app Microsoft Teams per gli utenti non standard

Questo articolo descrive il comportamento delle app in Teams quando utenti guest, esterni (federati) e anonimi sono presenti in un contesto teams.

- Un **utente guest** è una persona che non è un dipendente, uno studente o un membro dell'organizzazione. e che non ha un account aziendale o dell'istituto di istruzione presso l'organizzazione.

- Un **utente esterno (federato)** appartiene a un altro dominio e non ha accesso ai team o alle risorse del team dell'organizzazione.

>[!Note]
> Per un confronto più dettagliato tra utenti guest ed utenti esterni, vedere Comunicare [con utenti di altre organizzazioni .](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations)

- Un **utente anonimo** è un concetto nelle riunioni di Teams in cui l'utente si è unito alla riunione tramite un collegamento. L'utente non ha eseguito l'accesso con l'account Microsoft o dell'organizzazione.

## <a name="guest-user-access"></a>Accesso degli utenti guest

### <a name="install-update-and-delete-for-guest-users"></a>Installare, aggiornare ed eliminare gli utenti guest

I guest non possono installare, aggiornare o eliminare app in un contesto condiviso, ad esempio una chat, un canale o una riunione. Possono installare, aggiornare o eliminare le app nell'ambito personale usando le estensioni dei messaggi e i collegamenti diretti. I guest non hanno accesso all'app store di Teams.

### <a name="usage-behavior-and-policy-for-guest-users"></a>Comportamento e criteri di utilizzo per gli utenti guest

Gli utenti guest possono usare un'app se l'app è stata installata da un utente nativo.

I bot possono inviare messaggi proattivamente agli utenti guest, ma i guest non possono interagire con il bot. Gli ospiti non possono inviare messaggi al bot 1:1, @ menzionare il bot o interagire con le schede adattive che comunicano con il bot.

Gli utenti guest aderiscono ai criteri di autorizzazione globali e a livello di organizzazione impostati per il tenant host per qualsiasi app. In altre parole, se un'app è bloccata per l'intera organizzazione host, i guest non possono neanche usare l'app.

I criteri di configurazione non si applicano agli utenti guest. Questo significa che l'aggiunta di un'app dall'interfaccia di amministrazione ai criteri predefiniti non ha alcun effetto sugli utenti guest.

## <a name="external-federated-user-access"></a>Accesso degli utenti esterni (federati)

### <a name="install-update-and-delete-for-external-users"></a>Installare, aggiornare ed eliminare utenti esterni

Gli utenti esterni non possono installare, aggiornare o eliminare app in qualsiasi contesto, ad esempio una chat, un canale o una riunione personale. Non hanno accesso all'app store di Teams.

### <a name="usage-behavior-and-policy-for-external-users"></a>Comportamento e criteri di utilizzo per gli utenti esterni

Gli utenti esterni non possono usare alcuna app di Teams e, quando un utente esterno viene aggiunto a un contesto con utenti nativi, tutti gli utenti, sia nativi che esterni, non possono più usare le app.

Gli utenti esterni non sono influenzati dai criteri delle app perché non possono usare le app di Teams.

## <a name="anonymous-user-in-meetings-access"></a>Utente anonimo nell'accesso alle riunioni

### <a name="install-update-and-delete-for-anonymous-users"></a>Installare, aggiornare ed eliminare utenti anonimi

Gli utenti anonimi non possono installare, aggiornare o eliminare app nelle riunioni.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Comportamento di utilizzo e criteri per gli utenti anonimi

Gli utenti anonimi non possono usare direttamente le app nelle riunioni. Gli utenti nativi possono continuare a usare le app per le riunioni se sono presenti utenti anonimi. Se un'app invia una scheda adattiva nella chat, gli utenti anonimi possono interagire con la scheda.

Gli utenti anonimi erediteranno i criteri di autorizzazione predefiniti globali a livello di utente. Questo controllo consente agli utenti anonimi di interagire con le app nelle riunioni di Teams, purché il criterio di autorizzazione a livello utente abbia abilitato l'app. Gli utenti anonimi possono interagire solo con le app già disponibili in una riunione e che non possono acquisire e/o gestire queste app.
