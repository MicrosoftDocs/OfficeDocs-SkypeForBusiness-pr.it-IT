---
title: Esperienza di chat nativa per utenti esterni (federati) in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
description: Informazioni sull'esperienza di chat di Team native per utenti di Access esterni (federati) in Microsoft teams, disponibile tra utenti esterni in cui entrambi gli utenti si trovano nella modalità di aggiornamento di TeamsOnly.
ms.openlocfilehash: d3ff414420f8d1d68965307e9303aed4b5cf00ff
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030602"
---
<a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Esperienza di chat nativa per utenti esterni (federati) in Microsoft Teams
======================================

Quando un utente di Microsoft teams sta chattando con un utente esterno (federato), l'esperienza della chat è limitata al testo. Tuttavia, se sia l'utente del team che l'utente esterno si trova nella modalità di aggiornamento di TeamsOnly, è possibile avere un'"esperienza di chat con Team nativi", che include la formattazione RTF, la @mentions e altre funzionalità di chat. In altre parole, puoi avere la stessa esperienza di chat di Microsoft teams Rich 1:1 con utenti esterni idonei, come hai fatto con gli utenti dell'organizzazione. Le chat di teams native con utenti esterni sono ancora limitate solo alle chat di 1:1 (gli utenti esterni non possono eseguire chat di gruppo).

L'esperienza di chat nativa per gli utenti esterni è attivata per tutti i tenant di teams, ma non tutti gli utenti sono idonei. Per offrire un'esperienza di chat nativa, sia il mittente che il destinatario devono essere configurati per la modalità di aggiornamento di TeamsOnly. Per ulteriori informazioni sui criteri di aggiornamento, vedere [impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md).

Per visualizzare un elenco delle funzionalità per gli utenti di Access esterni in teams, vedere [confrontare l'accesso esterno e Guest](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>Come si può verificare se si è in una chat nativa?

Se è possibile scambiare solo testo in una chat con un utente esterno, si è in una chat di accesso esterno standard (federati). Se hai tutte le altre funzionalità di chat, inclusi la formattazione, la @mentions, i emoji e così via, sei in una chat di Team nativi con l'utente esterno. 

Teams controlla periodicamente la modalità di aggiornamento per gli utenti esterni e, quando trova un utente esterno che esegue teams nella modalità di aggiornamento di TeamsOnly, verrà chiesto di passare a una chat di Team nativi e bloccare la chat originale.

Quando si passa a una chat nativa in teams, i team non uniscono le due conversazioni. Verranno invece visualizzate entrambe le chat nel feed della chat. La nuova chat a squadre native è attiva, ma la vecchia chat di solo testo è bloccata.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>Cosa succede se un utente non è più in modalità solo Teams?

Se si sta usando una chat di Team nativi con un utente esterno e uno di essi viene disattivato dalla modalità di aggiornamento di TeamsOnly, i team bloccano la chat dei team nativi e forniscono un collegamento per una chat limitata di solo testo. Non potrai continuare nella chat di Team nativi. È ancora possibile leggere la chat di Team nativi, ma non è possibile continuare la conversazione.

Se teams trova una vecchia chat di solo testo con questo utente esterno, la chat verrà riattivata. In caso contrario, teams crea una nuova chat di solo testo.


## <a name="related-topics"></a>Argomenti correlati

[Gestire l'accesso esterno in teams](manage-external-access.md)
