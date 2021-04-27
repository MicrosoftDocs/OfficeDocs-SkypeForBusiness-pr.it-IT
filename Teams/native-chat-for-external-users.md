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
description: Informazioni sull'esperienza di chat nativa di Teams per gli utenti con accesso esterno (federato) in Microsoft Teams in cui entrambi gli utenti sono in modalità di aggiornamento TeamsOnly.
ms.openlocfilehash: a06532ab4cd1d1c5ffe3f30d2a6036b2c34c716f
ms.sourcegitcommit: 5a39061c2156531f4b7f5f69eecf81a8c8b238d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2021
ms.locfileid: "52030116"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Esperienza di chat nativa per utenti esterni (federati) in Microsoft Teams

Quando un utente di Microsoft Teams sta chattando con un utente esterno (federato), l'esperienza di chat è limitata al testo. Tuttavia, se sia l'utente di Teams che la persona in un'altra organizzazione sono in modalità di aggiornamento TeamsOnly, è possibile avere una "esperienza di chat nativa di Teams", che include formattazione avanzata, @mentions e altre funzionalità di chat. Le chat native di Teams con persone di altre organizzazioni sono limitate a 1:1 chat.

L'esperienza di chat nativa per le persone di altre organizzazioni è attivata per tutti i tenant di Teams, ma non tutte le persone sono idonee. Per offrire un'esperienza di chat nativa, sia il mittente che il destinatario devono essere configurati per la modalità di aggiornamento TeamsOnly. Per altre informazioni sui criteri di aggiornamento, vedere [Impostazione delle impostazioni di coesistenza e aggiornamento.](setting-your-coexistence-and-upgrade-settings.md)

Per visualizzare un elenco delle funzionalità per gli utenti con accesso esterno in Teams, vedere [Confrontare l'accesso esterno e quello guest.](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>Come si fa a sapere se si è in una chat nativa?

Se è possibile scambiare testo nella chat solo con persone di altre organizzazioni, si è in una chat standard di accesso esterno (federato). Se hai tutte le altre funzionalità di chat, tra cui formattazione, @mentions, emoji e così via, sei in una chat nativa di Teams. 

Teams controlla periodicamente la modalità di aggiornamento per le persone di altre organizzazioni e, quando trova un team che esegue Teams nella modalità di aggiornamento TeamsOnly, ti chiederà di passare a una chat nativa di Teams e bloccare la chat originale.

Quando si passa a una chat nativa di Teams, Teams non unisce le due conversazioni. Al contrario, vedrai entrambe le chat nel feed chat. La nuova chat nativa di Teams è attiva, ma la vecchia chat di solo testo è bloccata.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>Cosa succede se un utente non è più in modalità Solo Teams?

Se si ha una chat nativa di Teams con persone di altre organizzazioni e quindi una di queste viene passata dalla modalità di aggiornamento di TeamsOnly, Teams blocca la chat nativa di Teams e fornisce un collegamento per una chat limitata di solo testo. Non sarà possibile continuare nella chat nativa di Teams. È comunque possibile leggere la chat nativa di Teams, ma non è possibile continuare la conversazione.

Se Teams trova una vecchia chat di solo testo con questa persona, la resusciterà. In caso contrario, Teams crea una nuova chat di solo testo.


## <a name="related-topics"></a>Argomenti correlati

[Gestire l'accesso esterno in Teams](manage-external-access.md)
