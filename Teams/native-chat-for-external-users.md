---
title: Esperienza di chat nativa per utenti esterni (federati) in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni sull'esperienza di chat nativa di Teams per gli utenti di accesso esterno (federato) in Microsoft Teams, in cui entrambi gli utenti sono in modalità di aggiornamento TeamsOnly.
ms.openlocfilehash: df9e1e41992e105937deacf898833995cdfb7714
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055658"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Esperienza di chat nativa per utenti esterni (federati) in Microsoft Teams

Quando un utente di Microsoft Teams chatta con un utente esterno (federato), l'esperienza di chat è limitata al testo. Tuttavia, se sia l'utente di Teams che la persona in un'altra organizzazione si trova nella modalità di aggiornamento di TeamsOnly, è possibile avere un'esperienza di chat nativa di Teams, che include formattazione avanzata, @mentions e altre funzionalità di chat. In altre parole, puoi avere la stessa ricca esperienza di chat 1:1 Teams con persone idonee in altre organizzazioni come faresti con gli utenti dell'organizzazione. Le chat native di Teams con persone in altre organizzazioni sono limitate a chat 1:1.

L'esperienza di chat nativa per le persone in altre organizzazioni è attivata per tutti i tenant di Teams, ma non tutte le persone sono idonee. Per offrire un'esperienza di chat nativa, è necessario configurare sia il mittente che il destinatario per la modalità di aggiornamento TeamsOnly. Per altre informazioni sui criteri di aggiornamento, vedere [Impostazione delle impostazioni di coesistenza e aggiornamento.](setting-your-coexistence-and-upgrade-settings.md)

Per visualizzare un elenco di funzionalità per gli utenti con accesso esterno in Teams, vedere [Confrontare l'accesso esterno e guest.](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>Come faccio a sapere se sono in una chat nativa?

Se è possibile scambiare testo solo nella chat con persone di altre organizzazioni, si è in una chat di accesso esterno (federato) standard. Se hai tutte le altre funzionalità di chat, tra cui la formattazione, @mentions, emoji e così via, sei in una chat nativa di Teams. 

Teams controlla periodicamente la modalità di aggiornamento per le persone in altre organizzazioni e, quando trova un team che esegue Teams in modalità di aggiornamento TeamsOnly, ti chiederà di passare a una chat nativa di Teams e bloccare la chat originale.

Quando si passa a una chat nativa di Teams, Teams non unisce le due conversazioni. Verranno invece visualizzati entrambe le chat nel feed chat. La nuova chat nativa di Teams è attiva, ma la vecchia chat di solo testo è bloccata.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>Cosa succede se un utente non è più in modalità Solo teams?

Se si aveva una chat nativa di Teams con persone di altre organizzazioni e quindi una di queste viene passata dalla modalità di aggiornamento TeamsOnly, Teams blocca la chat nativa di Teams e fornisce un collegamento per una chat limitata di solo testo. Non sarà possibile continuare nella chat nativa di Teams. È comunque possibile leggere la chat nativa di Teams, ma non è possibile continuare la conversazione.

Se Teams trova una vecchia chat solo testuale con questa persona, la chat verrà ripristinata. In caso contrario, Teams crea una nuova chat solo testuale.


## <a name="related-topics"></a>Argomenti correlati

[Gestire l'accesso esterno in Teams](manage-external-access.md)
