---
title: Usare chat supervisionate per tenant non didattici
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.reviewer: angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni sulle chat supervisionate per i tenant non didattici nelle Microsoft Teams riunioni.
ms.openlocfilehash: d56a41e3c168aea1d5454fb38ae2aac0c033fe64
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745482"
---
# <a name="supervised-chats-for-non-educational-tenants"></a>Chat supervisionate per tenant non didattici

La chat con supervisione consente ai supervisori designati di avviare chat con chiunque nell'organizzazione e impedisce agli utenti con restrizioni di avviare nuove chat, a meno che non sia presente un supervisore appropriato. Quando la supervisione della chat è abilitata, i supervisori non possono uscire dalla chat e gli altri partecipanti non sono autorizzati a rimuoverli, assicurando che le chat che coinvolgono utenti con restrizioni siano correttamente supervisionate.

Queste limitazioni vengono applicate solo alle nuove chat private create dopo che la chat supervisionata è stata completamente abilitata. Non si applicano a chat private, chat di riunioni o canali esistenti.

La chat supervisionata è personalizzata per le esigenze degli istituti di istruzione, ma è disponibile anche per i tenant non didattici.

> [!NOTE]
> La chat con supervisione protegge le nuove chat create dopo l'applicazione della funzionalità. Non protegge le chat esistenti.

## <a name="enable-supervised-chat"></a>Abilitare la chat con supervisione

> [!NOTE]
> Assicurarsi di configurare i ruoli di autorizzazione della chat e i criteri di autorizzazione della chat basati sui ruoli prima di abilitare la chat per l'istituto per evitare l'accesso degli utenti con restrizioni indesiderate alle chat non supervisionate.

**Definire i ruoli di autorizzazione chat per ogni utente dell'ambiente**

Perché la chat supervisionata funzioni come previsto, a ogni utente all'interno dell'ambiente deve essere assegnato il ruolo di autorizzazione della chat corretto. Un utente può assegnare tre ruoli:

- Autorizzazioni complete: questo ruolo deve essere assegnato ai supervisori della chat nel proprio ambiente. Possono avviare chat con qualsiasi utente all'interno dell'ambiente. È previsto che gli utenti con autorizzazioni complete supervisionino le chat a cui partecipano. Non possono uscire o essere rimossi dalle chat che avviano o dalle chat che stanno supervisionando nei tenant federati.

- Autorizzazioni limitate: questo ruolo è ideale per i membri del personale che devono avere accesso con supervisione solo agli utenti con restrizioni. Possono avviare chat con utenti completi o limitati, ma non possono avviare chat con utenti con restrizioni. Se un utente con autorizzazioni complete inizia una chat con un utente con restrizioni, gli utenti limitati possono essere associati alla conversazione. Questo accesso si verifica perché un utente con autorizzazioni complete è presente per supervisionare la collaborazione tra utenti limitati e con restrizioni.

- Autorizzazioni limitate: questo ruolo è ideale per gli utenti che devono essere supervisionati. Possono avviare chat solo con utenti con autorizzazioni complete. Possono partecipare a qualsiasi conversazione a cui un utente con autorizzazioni complete lo invita. Nei casi di chat federate, gli utenti con restrizioni possono essere aggiunti alle chat solo da un utente con autorizzazioni complete provenienti dal tenant dell'utente con restrizioni.

Per impostare il ruolo di autorizzazione  chat degli utenti, usare il criterio del ruolo Autorizzazioni chat disponibile nelle opzioni dei criteri di messaggistica nel portale di amministrazione Teams chat. È possibile usare PowerShell per definire i ruoli usando il criterio ChatPermissionRole con i valori Full, Limited o Restricted. Questo criterio si trova in [CsTeamsMessagingPolicy.](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)

I ruoli non possono essere assegnati ai guest nel tenant. Ai guest viene assegnato il ruolo limitato.

## <a name="allow-supervised-chat"></a>Consenti chat con supervisione

La chat con supervisione è disabilitata per impostazione predefinita per il tenant. Dopo aver impostato i ruoli per le autorizzazioni di chat per gli utenti, è possibile abilitare la chat supervisionata all'interno del tenant selezionando Impostazioni a livello di organizzazione Teams Impostazioni e impostando criteri di autorizzazioni chat basate sui ruoli su  >   **Attivato**.  È anche possibile usare PowerShell per abilitare la chat supervisionata impostando AllowRoleBasedChatPermissions su True. Questo cmdlet si trova in [CsTeamsClientConfiguration.](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)

La chat supervisionata deve essere abilitata per tutti gli utenti del tenant e non può essere abilitata solo per una parte degli utenti.

**Abilitare la chat**

Abilitare la chat per tutti gli utenti usando i criteri chat esistenti disponibili nell Teams di amministrazione.

**Gestire le chat supervisionate**

Dopo aver inizialmente abilitato la chat supervisionata, è necessario eseguire alcune operazioni per assicurarsi che le chat nell'ambiente rimangano sotto controllo:

- Assegnare i ruoli appropriati a tutti i nuovi utenti che aderiscono al tenant. Per impostazione predefinita, agli utenti verrà assegnato un ruolo con restrizioni.

- Se un utente con autorizzazioni complete lascia o viene rimosso da un tenant, le chat a cui supervisionavano vengono lasciati incustoditi. Prima di rimuovere l'utente originale, assicurarsi che a queste conversazioni sia aggiunto un altro utente con autorizzazioni complete, in modo che la chat possa rimanere sotto controllo. Dopo la rimozione del supervisore originale, i nuovi partecipanti non possono essere aggiunti alla conversazione, ma i partecipanti correnti possono continuare a comunicare.
