---
title: Scadenza e rinnovo del team in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
  - M365-collaboration
description: Informazioni sulla scadenza e il rinnovo del team e su come usare i criteri di scadenza Microsoft 365 gruppo per pulire automaticamente i team inutilizzati nelle Microsoft Teams.
f1.keywords:
  - NOCSH
appliesto:
  - Microsoft Teams
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Scadenza e rinnovo del team in Microsoft Teams

Le organizzazioni con un numero elevato di team hanno spesso team che non vengono mai effettivamente usati. Questo problema può verificarsi a causa di diversi motivi, tra cui la sperimentazione del prodotto, la collaborazione in team a breve termine o l'uscita dall'organizzazione da parte dei proprietari del team. Nel corso del tempo, questi team possono accumularsi e creare un onere sulle risorse del tenant.  

Per limitare il numero di team inutilizzati, come amministratore, è possibile usare i criteri [](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) di scadenza Microsoft 365 di gruppo per pulire automaticamente i team inutilizzati. Poiché i team sono supportati da gruppi, i criteri di scadenza dei gruppi vengono applicati automaticamente anche ai team.

Quando si applicano criteri di scadenza a un team, il proprietario del team riceve una notifica per il rinnovo del team 30 giorni, 15 giorni e 1 giorno prima della data di scadenza del team. Quando il proprietario del team riceve la notifica, può fare clic su Rinnova **ora** nelle impostazioni del team per rinnovare il team.

![Screenshot del pulsante Rinnova ora per rinnovare un team nelle impostazioni del team.](media/team-expiration.png "Screenshot del pulsante Rinnova ora per rinnovare un team nelle impostazioni del team")

Se il proprietario del team non rinnova il team e non ci sono altre attività nel team fino alla fine dei criteri di scadenza, il team viene inserito in uno stato "soft-deleted", ovvero può essere ripristinato entro i prossimi 30 giorni.

## <a name="team-auto-renewal"></a>Rinnovo automatico del team

In alcuni casi, il proprietario del team potrebbe non essere in grado di rinnovare il team perché si è dimenticato di rinnovarlo o non era disponibile quando era in scadenza il rinnovo. In questi scenari, un team in uso attivo può essere eliminato a causa dei criteri di scadenza applicabili al team.  

Per impedire l'eliminazione accidentale, il rinnovo automatico viene abilitato automaticamente per un team nei criteri di scadenza del gruppo. Quando sono impostati i criteri di scadenza del gruppo, qualsiasi team che ha almeno una visita al canale da qualsiasi membro del team prima della data di scadenza viene rinnovato automaticamente senza alcun intervento manuale da parte del proprietario del team.

## <a name="known-issues"></a>Problemi noti

**La data di scadenza del team e del gruppo sottostante non corrispondono**

Prima che un team venga rinnovato, il gruppo che lo contiene viene rinnovato per primo. Durante il rinnovo, nel gruppo viene impostata una nuova data di scadenza per una data futura. Questa nuova data potrebbe non essere immediatamente visibile in Teams. La sincronizzazione può richiedere fino a 24 ore. Se viene visualizzata una discrepanza tra la data di scadenza di un team e il gruppo sottostante, attendere 24 ore prima di richiedere ulteriore supporto.