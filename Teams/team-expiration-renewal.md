---
title: Scadenza e rinnovo del team in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
ms.localizationpriority: medium
search.appverid: MET150
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
description: Informazioni sulla scadenza e il rinnovo del team e su come usare i criteri di scadenza dei gruppi di Microsoft 365 per pulire automaticamente i team inutilizzati in Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b4f56c8cbb2d25b05d6c87fa2862e56244d6b9c8
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198798"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Scadenza e rinnovo del team in Microsoft Teams

Le organizzazioni con un numero elevato di team spesso hanno team che non vengono mai effettivamente utilizzati. Ciò può verificarsi a causa di diversi motivi, tra cui sperimentazione del prodotto, collaborazione in team a breve termine o proprietari di team che lasciano l'organizzazione. Nel corso del tempo, tali team possono accumularsi e creare un carico sulle risorse del tenant.  

Per limitare il numero di team inutilizzati, gli amministratori possono usare [i criteri di scadenza dei gruppi di Microsoft 365](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) per pulire automaticamente i team inutilizzati. Poiché i team sono supportati dai gruppi, i criteri di scadenza dei gruppi si applicano automaticamente anche ai team.

Quando si applicano criteri di scadenza a un team, il proprietario del team riceve una notifica per il rinnovo del team 30, 15 giorni e 1 giorno prima della data di scadenza del team. Quando il proprietario del team riceve la notifica, può fare clic su **Rinnova ora** nelle impostazioni del team per rinnovare il team.

![Screenshot del pulsante Rinnova ora per rinnovare un team nelle impostazioni del team.](media/team-expiration.png "Screenshot del pulsante Rinnova ora per rinnovare un team nelle impostazioni del team")

Se il proprietario del team non rinnova il team e non ci sono altre attività nel team fino alla fine dei criteri di scadenza, il team viene messo in stato di "eliminazione temporaneamente", il che significa che può essere ripristinato entro i prossimi 30 giorni.

## <a name="team-auto-renewal"></a>Rinnovo automatico del team

In alcuni casi il proprietario del team non è in grado di rinnovare il team, ad esempio perché ha dimenticato di rinnovarlo o non era al momento del rinnovo. In questi scenari, un team in uso attivo può essere eliminato a causa dei criteri di scadenza che si applicano al team.  

Per evitare l'eliminazione accidentale, il rinnovo automatico viene abilitato automaticamente per un team nei criteri di scadenza del gruppo. Quando sono configurati i criteri di scadenza del gruppo, tutti i team che hanno almeno una visita al canale da qualsiasi membro del team prima della data di scadenza vengono rinnovati automaticamente senza alcun intervento manuale da parte del proprietario del team.

## <a name="known-issues"></a>Problemi noti

**La data di scadenza del team e del gruppo sottostante non corrispondono**

Prima del rinnovo di un team, il gruppo che ne esegue il rinnovo viene rinnovato. Nell'ambito del rinnovo, nel gruppo viene impostata una nuova data di scadenza per una data futura. Questa nuova data potrebbe non essere immediatamente visibile in Teams. La sincronizzazione può richiedere fino a 24 ore. Se si riscontra una discrepanza tra la data di scadenza di un team e il gruppo sottostante, attendere 24 ore prima di richiedere ulteriore supporto.