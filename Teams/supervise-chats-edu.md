---
title: Usare chat supervisionate
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: Informazioni sulle chat supervisionate nelle riunioni di Microsoft Teams.
ms.openlocfilehash: e705120eb2f8b92ea437c78be67c139018f786fc
ms.sourcegitcommit: 50111653f72f6758a3491a4dc3e91160ab75022c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51506679"
---
# <a name="supervised-chats-in-microsoft-teams"></a>Chat supervisionate in Microsoft Teams

Gli istituti di istruzione offrono uno spazio digitale sicuro e sano per gli studenti. Lo spazio digitale include messaggi di posta elettronica, riunioni e chiamate online e messaggistica in Teams. Per evitare comportamenti di messaggistica inappropriati, molte scuole disabilitano la chat privata in Teams. Purtroppo, la disabilitazione della chat blocca anche l'opportunità per gli insegnanti di contattare gli studenti privatamente per l'apprendimento personalizzato. Con la chat disabilitata, gli studenti non possono contattare gli insegnanti quando preferiscono non pubblicare i messaggi nei team di classe.

La chat supervisionata consente ai docenti designati di avviare chat con gli studenti e impedisce agli studenti di avviare nuove chat a meno che non sia presente un docente appropriato. Quando la supervisione della chat è abilitata, i supervisori non possono uscire dalla chat e gli altri partecipanti non sono autorizzati a rimuoverli, assicurando che le chat che coinvolgono studenti siano correttamente supervisionate.

Queste limitazioni vengono applicate solo alle nuove chat private create dopo che la chat supervisionata è stata completamente abilitata. Non si applicano a chat private, chat di riunioni o canali esistenti. Per altre informazioni sulle procedure consigliate per la chat delle riunioni, la sicurezza dei canali e la sicurezza degli studenti, vedere Tenere gli studenti al [sicuro durante l'uso di Teams.](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators)

> [!Note]
> La chat con supervisione protegge le nuove chat create dopo l'applicazione della funzionalità.  Non protegge le chat esistenti.

## <a name="review-use-cases-for-supervised-chats"></a>Esaminare i casi d'uso per le chat con supervisione

Gli esempi seguenti illustrano quando è necessaria una chat supervisionata.

- Un follow-up 1.1 con un docente quando gli studenti non sono a proprio agio a condividere o porre domande pubblicamente.

- Docenti che raggiungono 1,1 a uno studente su un'attività, l'interazione recente in classe (o la mancanza di) o un altro argomento.

- Discussioni di gruppo degli studenti monitorate da un docente.

- Consenti al personale non docente di chattare con gli studenti in un ambiente supervisionato.

## <a name="enable-supervised-chat"></a>Abilitare la chat con supervisione

> [!Note]
> Assicurarsi di configurare i ruoli di autorizzazione della chat e i criteri di autorizzazione chat basati sui ruoli prima di abilitare la chat per l'istituto per evitare l'accesso indesiderato degli studenti alle chat senza supervisione.

### <a name="define-chat-permission-roles-for-each-user-in-your-environment"></a>Definire i ruoli di autorizzazione chat per ogni utente dell'ambiente

Perché la chat supervisionata funzioni come previsto, a ogni utente all'interno dell'ambiente deve essere assegnato il ruolo di autorizzazione della chat corretto. Un utente può assegnare tre ruoli:

- *Autorizzazioni complete:* questo ruolo è ideale per i docenti che devono avere accesso completo agli studenti e ad altri membri del personale. Possono avviare chat con qualsiasi utente all'interno dell'ambiente. È previsto che gli utenti con autorizzazioni complete supervisionino le chat a cui partecipano. Non possono uscire o essere rimossi dalle chat che avviano o dalle chat che stanno supervisionando nei tenant federati.

- *Autorizzazioni limitate:* questo ruolo è ideale per i membri del personale che devono avere accesso supervisionato solo agli studenti e avere accesso completo ad altri membri del personale e docenti. Possono avviare chat con utenti completi o limitati, ma non possono avviare chat con utenti con restrizioni. Se un utente con autorizzazioni complete inizia una chat con un utente con restrizioni, gli utenti limitati possono essere associati alla conversazione. Questo accesso si verifica perché un utente con autorizzazioni complete è presente per supervisionare la collaborazione tra utenti limitati e con restrizioni.

- *Autorizzazioni limitate:* questo ruolo è ideale per gli studenti che devono essere supervisionati. Possono avviare chat solo con utenti con autorizzazioni complete. Possono partecipare a qualsiasi conversazione a cui un utente con autorizzazioni complete lo invita. Nei casi di chat federate, gli utenti con restrizioni possono essere aggiunti alle chat solo da un utente con autorizzazioni complete provenienti dal tenant dell'utente con restrizioni.

Per impostare il ruolo di autorizzazione chat degli utenti, usare il criterio di ruolo **Autorizzazioni chat**  disponibile nelle opzioni dei criteri di messaggistica nel portale di amministrazione di Teams. È possibile usare PowerShell per definire i ruoli usando il criterio ChatPermissionRole con i valori Full, Limited o Restricted. Questo criterio si trova in CsTeamsMessagingPolicy.

Per altre informazioni sull'impostazione. Per i criteri di Teams, vedere Guide ai criteri e ai pacchetti di criteri di Teams per Education e Assegnare criteri a set di utenti di grandi dimensioni.

I ruoli non possono essere assegnati ai guest nel tenant. Ai guest viene assegnato il ruolo limitato.

### <a name="allow-supervised-chat"></a>Consenti chat con supervisione

La chat con supervisione è disabilitata per impostazione predefinita per il tenant. Dopo aver impostato i ruoli per le autorizzazioni di chat per gli utenti, è possibile abilitare la chat supervisionata all'interno del tenant selezionando Impostazioni  di Teams a livello di organizzazione e impostando criteri di autorizzazione chat basati sui ruoli su &gt;  *Attivato.*  È anche possibile usare PowerShell per abilitare la chat supervisionata impostando AllowRoleBasedChatPermissions su True. Questo cmdlet si trova in CsTeamsClientConfiguration.

La chat supervisionata deve essere abilitata per tutti gli utenti del tenant e non può essere abilitata solo per una parte degli utenti.

### <a name="enable-chat"></a>Abilitare la chat

Abilitare la chat per tutti gli utenti usando i criteri chat esistenti disponibili nell'interfaccia di amministrazione di Teams.

## <a name="maintain-supervised-chats"></a>Gestire le chat supervisionate

Dopo aver inizialmente abilitato la chat supervisionata, è necessario eseguire alcune operazioni per assicurarsi che le chat nell'ambiente rimangano supervisionate:

- Assegnare i ruoli appropriati a tutti i nuovi utenti che aderiscono al tenant. Per impostazione predefinita, agli utenti verrà assegnato un ruolo con restrizioni.

- Se un utente con autorizzazioni complete lascia o viene rimosso da un tenant, le chat a cui supervisionavano verranno lasciati incustoditi. Prima di rimuovere l'utente originale, assicurarsi che a queste conversazioni sia aggiunto un altro utente con autorizzazioni complete, in modo che la chat possa rimanere sotto controllo. Dopo la rimozione del supervisore originale, i nuovi partecipanti non possono essere aggiunti alla conversazione, ma i partecipanti correnti possono continuare a comunicare.

## <a name="related-topics"></a>Argomenti correlati

[Chat supervisionate per Teams per l'istruzione](https://support.microsoft.com/topic/supervised-chats-in-microsoft-teams-for-education-ad3aaafc-c85a-416f-95f9-d691f419cbb8?storagetype=live)
