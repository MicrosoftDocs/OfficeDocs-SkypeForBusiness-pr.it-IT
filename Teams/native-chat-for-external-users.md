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
description: Informazioni sull'esperienza Teams chat nativa per gli utenti con accesso esterno (federato) in Microsoft Teams in cui entrambi gli utenti sono in modalità di aggiornamento TeamsOnly.
ms.openlocfilehash: 3d94c55dc184d80edbc22be53f1df18c256423c5aa04b7e342b8964463db1aa7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54350598"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Esperienza di chat nativa per utenti esterni (federati) in Microsoft Teams

Quando un Microsoft Teams chatta con un utente esterno (federato), l'esperienza di chat è limitata al testo. Tuttavia, se sia l'utente di Teams che la persona di un'altra organizzazione sono in modalità di aggiornamento TeamsOnly, è possibile avere un'esperienza di chat nativa di Teams, che include formattazione avanzata, @mentions e altre funzionalità di chat. Le Teams chat native con persone di altre organizzazioni sono limitate a 1:1 chat.

L'esperienza di chat nativa per le persone di altre organizzazioni è attivata per tutti Teams tenant, ma non tutte le persone sono idonee. Per offrire un'esperienza di chat nativa, sia il mittente che il destinatario devono essere configurati per la modalità di aggiornamento TeamsOnly. Per altre informazioni sui criteri di aggiornamento, vedere [Impostazione delle impostazioni di coesistenza e aggiornamento.](setting-your-coexistence-and-upgrade-settings.md)

Per visualizzare un elenco delle funzionalità per gli utenti con accesso esterno in Teams, vedere Confronto tra accesso esterno [e accesso guest.](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>Come si fa a sapere se si è in una chat nativa?

Se è possibile scambiare testo nella chat solo con persone di altre organizzazioni, si è in una chat standard di accesso esterno (federato). Se hai altre funzionalità di chat, tra cui formattazione, @mentions, emoji e così via, sei in una chat Teams nativa. 

Teams controlla periodicamente la modalità di aggiornamento per le persone di altre organizzazioni e, quando trova un Teams che esegue Teams in modalità di aggiornamento TeamsOnly, ti verrà richiesto di passare a una chat Teams nativa e bloccare la chat originale.

Quando si passa a una chat Teams nativa, Teams le due conversazioni non vengono unite. Al contrario, vedrai entrambe le chat nel feed chat. La nuova chat nativa Teams è attiva, ma la vecchia chat di solo testo è bloccata.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>Cosa succede se un utente non è più in Teams modalità Solo utenti?

Se si aveva una chat Teams nativa con persone di altre organizzazioni e quindi una di queste viene passata dalla modalità di aggiornamento TeamsOnly, Teams blocca la chat nativa di Teams e fornisce un collegamento per una chat limitata di solo testo. Non sarà possibile continuare nella chat Teams nativa. È comunque possibile leggere la chat Teams nativa, ma non è possibile continuare la conversazione.

Se Teams trova una vecchia chat di solo testo con questa persona, la rivitalierà. In caso contrario, Teams crea una nuova chat di solo testo.


## <a name="related-topics"></a>Argomenti correlati

[Gestire l'accesso esterno in Teams](manage-external-access.md)
