---
title: Disponibilità e uso delle app Teams da parte di diversi tipi di utenti
author: ashishguptaiitb
ms.author: guptaashish
ms.reviewer: kojika
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: teams-apps
search.appverid: MET150
description: Informazioni sul funzionamento delle app in Microsoft Teams per guest, utenti federati e utenti anonimi.
ms.localizationpriority: high
ms.date: 09/28/2022
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
ms.openlocfilehash: c618552a574a567a91ddab0e2303fd5f99a2373a
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912605"
---
# <a name="use-of-teams-apps-for-external-attendees-or-guest-from-outside-an-organization"></a>Uso delle app Teams per partecipanti esterni o guest dall'esterno di un'organizzazione

Le app di Teams consentono la collaborazione con persone esterne all'organizzazione. Gli amministratori possono controllare chi può accedere alle chat, alle riunioni e al canale di Teams per collaborare con gli utenti dell'organizzazione. Per informazioni dettagliate, vedere [come consentire la collaborazione con i partecipanti esterni](manage-external-access.md) e [cosa possono fare i guest in Teams](guest-access.md). Questo articolo è incentrato sull'uso delle app da parte di persone esterne all'organizzazione.

I tipi di utenti seguenti possono essere presenti in una chat o una riunione di Teams e, se lo si consente, possono usare le app in Teams.

* Un **utente guest** è una persona che non è un dipendente, uno studente o un membro dell'organizzazione. e che non ha un account aziendale o dell'istituto di istruzione presso l'organizzazione.

* Un **utente esterno (federato)** proviene da un altro dominio e non ha accesso alle risorse di Teams dell'organizzazione.

* Un **utente anonimo** è un utente che partecipa a una riunione tramite un collegamento. L'utente non ha eseguito l'accesso con l'account Microsoft o con l'account dell'organizzazione.

Per un confronto più dettagliato tra utenti guest ed esterni, vedere [Comunicare con gli utenti di altre organizzazioni](communicate-with-users-from-other-organizations.md).

## <a name="guests"></a>Utenti guest

### <a name="install-update-and-delete-apps-for-guests"></a>Installare, aggiornare ed eliminare app per i guest

I guest non possono installare, aggiornare o eliminare app in un contesto condiviso, ad esempio una chat, un canale o una riunione. I guest possono farlo nell'ambito personale usando le estensioni dei messaggi e i collegamenti diretti. I guest non possono accedere all'app store di Teams dall'app desktop Teams, ma possono accedere allo Store con un collegamento diretto.

### <a name="usage-behavior-and-policy-for-guests"></a>Comportamento e criteri di utilizzo per i guest

Gli utenti guest possono usare un'app se l'app è stata installata dall'utente di un'organizzazione.

#### <a name="bots-installed-to-a-channel"></a>Bot installati in un canale

Gli ospiti possono menzionare il bot e interagire con le schede adattive.

#### <a name="personal-bots-installed-with-policies"></a>Bot personali installati con criteri

* Per qualsiasi app, gli utenti guest aderiscono ai criteri di autorizzazione globali e a livello di organizzazione impostati per l'organizzazione host. Se un'app è bloccata per l'intera organizzazione host, neanche gli utenti guest possono usare l'app.
* Tutti i bot inclusi nei criteri di configurazione delle app predefiniti globali verranno installati anche per gli utenti guest.
* Dopo aver installato un bot, bot e guest possono comunicare proattivamente tra loro.
* Non è possibile rimuovere un guest dai criteri di configurazione delle app predefinite globali.
* Per evitare che gli utenti guest accingano ad accedere ai bot, è possibile creare altri criteri di configurazione delle app, assegnarli agli utenti interni e installare bot con i criteri personalizzati.

## <a name="federated-users"></a>Utenti federati

### <a name="install-update-and-delete-apps-for-federated-users"></a>Installare, aggiornare ed eliminare app per gli utenti federati

Gli utenti federati non possono installare, aggiornare o eliminare app in alcun contesto, ad esempio una riunione personale, chat, canale o canale. Non hanno accesso all'app store di Teams dell'organizzazione che ospita.

### <a name="usage-behavior-and-policy-for-federated-users"></a>Comportamento e criteri di utilizzo per gli utenti federati

* Persone da altre organizzazioni aderiscono ai criteri globali (predefiniti) dell'organizzazione ospitante
* Gli utenti dell'organizzazione di hosting possono aggiungere app nelle chat delle riunioni con persone di altre organizzazioni. Persone di altre organizzazioni non possono aggiungere app nelle chat delle riunioni, ma possono interagire con bot, schede ed estensioni di messaggi una volta aggiunti alla chat.
* Dopo aver installato un bot in una chat di riunione, può comunicare in modo proattivo con persone di altre organizzazioni in quella chat e queste persone possono comunicare con bot.
* Vengono applicati i criteri dei dati dell'organizzazione di hosting.
* Vengono applicate le procedure di condivisione dei dati di qualsiasi app di terze parti condivisa dall'organizzazione dell'utente.

## <a name="anonymous-users"></a>Utenti anonimi

### <a name="install-update-and-delete-apps-for-anonymous-users"></a>Installare, aggiornare ed eliminare app per utenti anonimi

Gli utenti anonimi non possono installare, aggiornare o eliminare app nelle riunioni.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Comportamento e criteri di utilizzo per utenti anonimi

Gli utenti anonimi non possono usare direttamente le app nelle riunioni. Se un'app invia una scheda adattiva nella chat, gli utenti anonimi possono interagire con la scheda. Tali utenti possono interagire con le app nelle riunioni di Teams se i criteri di autorizzazione a livello utente abilitano l'app. Gli utenti anonimi ereditano il criterio di autorizzazione predefinito globale a livello utente.

Gli utenti anonimi possono interagire solo con le app già disponibili in una riunione, ma che non possono acquisire e gestire tali app. Gli utenti nativi possono continuare a usare le app per le riunioni anche quando gli utenti anonimi partecipano a una riunione.

### <a name="disallow-anonymous-users-to-use-apps-in-meetings"></a>Impedire agli utenti anonimi di usare le app nelle riunioni

Per impostazione predefinita, gli utenti anonimi possono interagire con le app esistenti in una riunione. È possibile impedire agli utenti anonimi di interagire con le app.

1. Accedere all'interfaccia di amministrazione di Teams e accedere alle **[impostazioni delle riunioni](https://admin.teams.microsoft.com/meetings/settings)** > .

1. In **Partecipanti** impostare l'interruttore su **Disattivato** per **Gli utenti anonimi possono interagire con le app nelle riunioni**.

1. Selezionare **Salva**.

## <a name="related-articles"></a>Articoli correlati

* [Consentire agli utenti anonimi di partecipare alle riunioni](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).
* [Gestire i criteri di configurazione delle app in Microsoft Teams](teams-app-setup-policies.md).
* [Come consentire la collaborazione con guest e partecipanti esterni](manage-external-access.md).
* [Cosa possono fare i guest in Teams](guest-access.md)
