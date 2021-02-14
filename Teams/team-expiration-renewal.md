---
title: Scadenza e rinnovo del team in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni sulla scadenza e il rinnovo del team e su come usare i criteri di scadenza dei gruppi di Microsoft 365 per eliminare automaticamente i team inutilizzati in Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b111ddd6b874fef22a7d221f6eb932c4c14c7b70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809406"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Scadenza e rinnovo del team in Microsoft Teams

Le organizzazioni con un numero elevato di team spesso hanno team che non vengono mai effettivamente usati. Questo problema può verificarsi per diversi motivi, tra cui la sperimentazione del prodotto, la collaborazione in team a breve termine o l'uscita dei proprietari dei team dall'organizzazione. Nel corso del tempo, questi team possono accumularsi e far gravare di più sulle risorse del tenant.  

Per limitare il numero di team inutilizzati, come amministratore, è possibile usare i criteri di scadenza dei gruppi di [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) per pulire automaticamente i team inutilizzati. Poiché i team sono supportati da gruppi, i criteri di scadenza dei gruppi vengono applicati automaticamente anche ai team.

Quando si applicano criteri di scadenza a un team, il proprietario del team riceve una notifica per il rinnovo del team 30, 15 giorni e 1 giorno prima della data di scadenza del team. Quando il proprietario del team riceve la notifica, può fare clic su Rinnova **ora** nelle impostazioni del team per rinnovare il team.

![Screenshot del pulsante Rinnova ora per rinnovare un team nelle impostazioni del team](media/team-expiration.png "Screenshot del pulsante Rinnova ora per rinnovare un team nelle impostazioni del team")

Se il proprietario del team non rinnova il team e non ci sono altre attività nel team fino alla fine dei criteri di scadenza, il team viene messo in stato di "eliminazione reverscita", ovvero può essere ripristinato entro i successivi 30 giorni.

## <a name="team-auto-renewal"></a>Rinnovo automatico del team

In alcuni casi il proprietario di un team non riesce a rinnovare il team, ad esempio perché ha dimenticato il rinnovo o non era al momento del rinnovo. In questi scenari, un team in uso può essere eliminato a causa dei criteri di scadenza applicabili al team.  

Per evitare l'eliminazione accidentale, il rinnovo automatico viene abilitato automaticamente per un team nei criteri di scadenza del gruppo. Dopo aver configurato i criteri di scadenza del gruppo, tutti i team che hanno almeno un canale visitato da qualsiasi membro del team prima della data di scadenza vengono automaticamente rinnovati senza alcun intervento manuale da parte del proprietario del team.

## <a name="known-issues"></a>Problemi noti

**La data di scadenza del team e del gruppo sottostante non corrispondono**

Prima del rinnovo di un team, viene rinnovato prima il gruppo che lo rappresenta. Durante il rinnovo, nel gruppo viene impostata una nuova data di scadenza per una data futura. Questa nuova data potrebbe non essere immediatamente visibile in Teams. La sincronizzazione può richiedere fino a 24 ore. Se si verifica una discrepanza tra la data di scadenza di un team e il gruppo sottostante, attendere 24 ore prima di richiedere ulteriore supporto.
