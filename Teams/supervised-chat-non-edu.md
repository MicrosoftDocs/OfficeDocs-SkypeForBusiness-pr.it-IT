---
title: Usare le chat supervisionate per i tenant non didattici
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Informazioni sulle chat supervisionate per tenant non didattici nelle riunioni di Microsoft Teams.
ms.collection:
- M365-collaboration
ms.openlocfilehash: 8b587dbc7537c612d2b48f5b202cd94e55e4d8f6
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270461"
---
# <a name="supervised-chats-for-non-educational-tenants"></a>Chat supervisionate per tenant non didattici

La chat supervisionata consente ai supervisori designati di avviare chat con chiunque nell'organizzazione e impedisce agli utenti con restrizioni di avviare nuove chat a meno che non sia presente un supervisore appropriato. Quando la supervisione della chat è abilitata, i supervisori non sono autorizzati a lasciare le chat e gli altri partecipanti non sono autorizzati a rimuoverli, assicurando che le chat che coinvolgono utenti con restrizioni siano correttamente supervisionate.

Queste limitazioni vengono applicate solo alle nuove chat private create dopo che la chat supervisionata è stata completamente abilitata. Non si applicano alle chat private, alle chat di riunione o ai canali esistenti.

La chat supervisionata è personalizzata per le esigenze degli istituti di istruzione, ma è disponibile anche per gli inquilini non didattici.

> [!NOTE]
> La chat supervisionata protegge le nuove chat create dopo l'applicazione della funzionalità. Non protegge le chat esistenti.

## <a name="enable-supervised-chat"></a>Abilitare la chat supervisionata

> [!NOTE]
> Assicurarsi di configurare i ruoli di autorizzazione della chat e i criteri di autorizzazione della chat basati sui ruoli prima di abilitare la chat per l'istituto per evitare l'accesso indesiderato da parte degli utenti con restrizioni alle chat non supervisionate.

**Definire i ruoli di autorizzazione chat per ogni utente dell'ambiente**:

Affinché la chat supervisionata funzioni come previsto, a ogni utente all'interno dell'ambiente deve essere assegnato il ruolo di autorizzazione chat corretto. A un utente possono essere assegnati tre ruoli:

- Autorizzazioni complete: questo ruolo deve essere assegnato ai supervisori della chat nell'ambiente. Possono avviare chat con qualsiasi utente all'interno dell'ambiente. Gli utenti con autorizzazioni complete sono tenuti a supervisionare le chat a cui partecipano. Non possono uscire o essere rimossi dalle chat che avviano o dalle chat che stanno supervisionando nei tenant federati.

- Autorizzazioni limitate: questo ruolo è ideale per i membri del personale che devono avere accesso supervisionato solo agli utenti con restrizioni. Possono avviare chat con utenti completi o limitati, ma non possono avviare chat con utenti con restrizioni. Se un utente con autorizzazioni complete inizia una chat con un utente con restrizioni, nella conversazione possono essere aggiunti utenti limitati. Questo accesso si verifica perché un utente con autorizzazioni complete è presente per supervisionare la collaborazione tra utenti limitati e con restrizioni.

- Autorizzazioni limitate: questo ruolo è ideale per gli utenti che devono essere supervisionati. Possono avviare chat solo con utenti con autorizzazioni complete. Può partecipare a qualsiasi conversazione a cui l'utente con autorizzazioni complete lo invita. Nei casi di chat federate, gli utenti con restrizioni possono essere aggiunti alle chat solo da un utente con autorizzazioni complete provenienti dal tenant dell'utente con restrizioni.

Per impostare il ruolo di autorizzazione chat degli utenti, usare i criteri del **ruolo Autorizzazioni chat** disponibili nelle opzioni dei criteri di messaggistica nel portale di amministrazione di Teams. È possibile usare PowerShell per definire i ruoli usando il criterio ChatPermissionRole con i valori Completi, Limitati o Con restrizioni. Questo criterio è in [CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy).

I ruoli non possono essere assegnati a guest nel tenant. Ai guest viene assegnato il ruolo limitato.

## <a name="allow-supervised-chat"></a>Consentire la chat supervisionata

La chat supervisionata è disabilitata per impostazione predefinita per il tenant. Dopo aver impostato i ruoli di autorizzazione chat per gli utenti, è possibile abilitare la chat supervisionata all'interno del tenant accedendo alle **impostazioni** \> di **Teams** a livello di organizzazione e impostando il criterio **delle autorizzazioni chat basate sui ruoli su** **Attivato**. È anche possibile usare PowerShell per abilitare la chat supervisionata impostando AllowRoleBasedChatPermissions su True. Questo cmdlet si trova in [CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration).

La chat supervisionata deve essere abilitata per tutti gli utenti nel tenant e non può essere abilitata solo per una parte degli utenti.

**Abilitare la chat**:

Abilitare la chat per tutti gli utenti usando i criteri chat esistenti disponibili nell'interfaccia di amministrazione di Teams.

**Gestire chat supervisionate**:

Dopo aver inizialmente abilitato la chat supervisionata, è necessario eseguire alcune operazioni per assicurarsi che le chat nell'ambiente rimangano supervisionate:

- Assegnare ruoli appropriati a tutti i nuovi utenti che si aggiungono al tenant. Per impostazione predefinita, agli utenti viene assegnato un ruolo con restrizioni.

- Se un utente con autorizzazioni complete lascia o viene rimosso da un tenant, le chat che stava supervisionando verranno lasciate incustodito. Prima di rimuovere l'utente originale, assicurarsi che un altro utente con autorizzazioni complete venga aggiunto a queste conversazioni in modo che la chat possa rimanere supervisionata. Una volta rimosso il supervisore originale, i nuovi partecipanti non possono essere aggiunti alla conversazione, ma i partecipanti correnti possono continuare a comunicare.
