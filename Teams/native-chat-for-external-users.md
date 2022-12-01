---
title: Esperienza di chat nativa per utenti esterni (federati) in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni sull'esperienza di chat nativa di Teams per gli utenti con accesso esterno (federato) in Microsoft Teams, in cui entrambi gli utenti si trovano nella modalità di aggiornamento di TeamsOnly.
ms.openlocfilehash: 134216364fdd7397d8a7d72a2ae6684cfa9f90b4
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198878"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Esperienza di chat nativa per utenti esterni (federati) in Microsoft Teams

Quando un utente di Microsoft Teams chatta con un utente esterno (federato), l'esperienza di chat è limitata al testo. Tuttavia, se sia l'utente di Teams che la persona in un'altra organizzazione sono nella modalità di aggiornamento di TeamsOnly, è possibile avere un'"esperienza di chat nativa di Teams", che include formattazione avanzata, @mentions e altre funzionalità di chat.

L'esperienza di chat nativa per le persone di altre organizzazioni è attivata per tutti i tenant di Teams, ma non tutte le persone sono idonee. Per offrire un'esperienza di chat nativa, il mittente e il ricevitore devono essere configurati per la modalità di aggiornamento di TeamsOnly. Per altre informazioni sui criteri di aggiornamento, vedere [Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md).

Per visualizzare un elenco di funzionalità per gli utenti con accesso esterno in Teams, vedere [Confrontare l'accesso esterno e guest](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>Ricerca per categorie sapere se è in una chat nativa?

Se è possibile scambiare testo nella chat solo con persone di altre organizzazioni, è attiva una chat standard di accesso esterno (federato). Se hai altre funzionalità di chat, tra cui formattazione, @mentions, emoji e così via, allora sei in una chat nativa di Teams. 

Teams controlla periodicamente la modalità di aggiornamento per gli utenti di altre organizzazioni e, quando trova un team che esegue Teams nella modalità di aggiornamento di TeamsOnly, ti chiederà di passare a una chat nativa di Teams e bloccare la chat originale.

Quando si passa a una chat nativa di Teams, Teams non unisce le due conversazioni. Verranno invece visualizzate entrambe le chat nel feed chat. La nuova chat nativa di Teams è attiva, ma la vecchia chat di sola lettura è bloccata.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>Cosa succede se un utente non è più in modalità Solo Teams?

Se si stava avendo una chat nativa di Teams con persone di altre organizzazioni e poi uno di voi viene disattivato dalla modalità di aggiornamento TeamsOnly, Teams blocca la chat nativa di Teams e offre un collegamento per una chat limitata di sola testo. Non sarà possibile continuare nella chat nativa di Teams. È comunque possibile leggere la chat nativa di Teams, ma non è possibile continuare la conversazione.

Se Teams trova una vecchia chat di sola lettura con questa persona, la chat sarà di nuovo disponibile. In caso contrario, Teams crea una nuova chat di sola lettura.


## <a name="related-topics"></a>Argomenti correlati

[Gestire l'accesso esterno in Teams](manage-external-access.md)
