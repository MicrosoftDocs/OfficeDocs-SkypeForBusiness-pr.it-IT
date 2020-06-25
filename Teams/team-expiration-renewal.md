---
title: Scadenza e rinnovo del team in Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni sulla scadenza e il rinnovo del team e su come usare i criteri di scadenza del gruppo Microsoft 365 per pulire automaticamente i team inutilizzati in Microsoft teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 697e36085169e0666e6a821a66c763be39cf9425
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868523"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a><span data-ttu-id="5025d-103">Scadenza e rinnovo del team in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5025d-103">Team expiration and renewal in Microsoft Teams</span></span>

<span data-ttu-id="5025d-104">Le organizzazioni con un numero elevato di team hanno spesso team che non vengono mai effettivamente usati.</span><span class="sxs-lookup"><span data-stu-id="5025d-104">Organizations with a large number of teams often have teams that are never actually used.</span></span> <span data-ttu-id="5025d-105">Questo problema può verificarsi a causa di diversi motivi, tra cui la sperimentazione del prodotto, la collaborazione a breve termine del team o i proprietari del team che lasciano l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5025d-105">This can happen because of several reasons including product experimentation, short-term team collaboration, or team owners leaving the organization.</span></span> <span data-ttu-id="5025d-106">Nel tempo, questi team possono accumularsi e creare un onere per le risorse del tenant.</span><span class="sxs-lookup"><span data-stu-id="5025d-106">Over time, such teams can accumulate and create a burden on tenant resources.</span></span>  

<span data-ttu-id="5025d-107">Per limitare il numero di Team inutilizzati, come amministratore, è possibile usare i [criteri di scadenza del gruppo Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) per pulire automaticamente i team inutilizzati.</span><span class="sxs-lookup"><span data-stu-id="5025d-107">To curb the number of unused teams, as an admin, you can use [Microsoft 365 group expiration policy](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) to automatically clean up unused teams.</span></span> <span data-ttu-id="5025d-108">Poiché i team sono supportate da gruppi, i criteri di scadenza del gruppo si applicano automaticamente anche ai team.</span><span class="sxs-lookup"><span data-stu-id="5025d-108">Because teams are backed by groups, group expiration policies automatically apply to teams as well.</span></span>

<span data-ttu-id="5025d-109">Quando si applicano criteri di scadenza a un team, un proprietario del team riceve una notifica per il rinnovo del team di 30 giorni, 15 giorni e 1 giorno prima della data di scadenza del team.</span><span class="sxs-lookup"><span data-stu-id="5025d-109">When you apply an expiration policy to a team, a team owner receives a notification for team renewal 30 days, 15 days and 1 day before the team's expiration date.</span></span> <span data-ttu-id="5025d-110">Quando il proprietario del team riceve la notifica, può fare clic su **rinnova ora** nelle impostazioni del team per rinnovare il team.</span><span class="sxs-lookup"><span data-stu-id="5025d-110">When the team owner receives the notification, they can click **Renew now** in team settings to renew the team.</span></span>

<span data-ttu-id="5025d-111">![Screenshot del pulsante Rinnova ora per rinnovare un team nelle impostazioni del team](media/team-expiration.png "Screenshot del pulsante Rinnova ora per rinnovare un team nelle impostazioni del team")</span><span class="sxs-lookup"><span data-stu-id="5025d-111">![Screenshot of the Renew Now button to renew a team in team settings](media/team-expiration.png "Screenshot of the Renew Now button to renew a team in team settings")</span></span>

<span data-ttu-id="5025d-112">Se il proprietario del team non rinnova il team, il team viene inserito in uno stato "Soft-deleted", il che significa che può essere ripristinato entro i prossimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="5025d-112">If the team owner doesn't renew the team, the team is put in a "soft-deleted" state, which means it can be restored within the next 30 days.</span></span>

## <a name="team-auto-renewal"></a><span data-ttu-id="5025d-113">Rinnovo automatico del team</span><span class="sxs-lookup"><span data-stu-id="5025d-113">Team auto-renewal</span></span>

<span data-ttu-id="5025d-114">Non è possibile che un proprietario del team possa rinnovare il team, perché si è dimenticato di rinnovare o non è più disponibile al momento del rinnovo.</span><span class="sxs-lookup"><span data-stu-id="5025d-114">There can be times when a team owner is unable to renew the team perhaps because they forgot to renew or were away when renewal was due.</span></span> <span data-ttu-id="5025d-115">In questi scenari, un team in uso attivo può essere eliminato a causa di criteri di scadenza che si applicano al team.</span><span class="sxs-lookup"><span data-stu-id="5025d-115">In these scenarios, a team in active use can get deleted because of expiration policies that apply to the team.</span></span>  

<span data-ttu-id="5025d-116">Per evitare l'eliminazione accidentale, il rinnovo automatico viene abilitato automaticamente per un team nei criteri di scadenza del gruppo.</span><span class="sxs-lookup"><span data-stu-id="5025d-116">To prevent accidental deletion, auto-renewal is automatically enabled for a team in the group expiration policy.</span></span> <span data-ttu-id="5025d-117">Quando viene configurato il criterio di scadenza del gruppo, qualsiasi team che abbia almeno una visita di un canale da qualsiasi membro del team prima della data di scadenza viene rinnovato automaticamente senza alcun intervento manuale da parte del proprietario del team.</span><span class="sxs-lookup"><span data-stu-id="5025d-117">When the group expiration policy is set up, any team that has at least one channel visit from any team member before its expiration date is automatically renewed without any manual intervention from the team owner.</span></span>

## <a name="known-issues"></a><span data-ttu-id="5025d-118">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="5025d-118">Known issues</span></span>

<span data-ttu-id="5025d-119">**La data di scadenza del team e il gruppo sottostante non corrispondono**</span><span class="sxs-lookup"><span data-stu-id="5025d-119">**Expiration date of team and underlying group don't match**</span></span>

<span data-ttu-id="5025d-120">Prima che un team venga rinnovato, il gruppo che appoggia il team viene rinnovato per primo.</span><span class="sxs-lookup"><span data-stu-id="5025d-120">Before a team is renewed, the group that backs the team is renewed first.</span></span> <span data-ttu-id="5025d-121">Come parte del rinnovo, una nuova data di scadenza viene impostata sul gruppo per una data futura.</span><span class="sxs-lookup"><span data-stu-id="5025d-121">As part of renewal, a new expiry date is set on the group for a future date.</span></span> <span data-ttu-id="5025d-122">Questa nuova data potrebbe non essere immediatamente visibile in teams.</span><span class="sxs-lookup"><span data-stu-id="5025d-122">This new date may not be immediately visible in Teams.</span></span> <span data-ttu-id="5025d-123">La sincronizzazione può richiedere fino a 24 ore. Se viene visualizzata una discrepanza tra la data di scadenza per un team e il relativo gruppo sottostante, attendere 24 ore prima di richiedere ulteriore supporto.</span><span class="sxs-lookup"><span data-stu-id="5025d-123">It can take up to 24 hours to sync. If you see a discrepancy between the expiry date for a team and its underlying group, wait 24 hours before seeking further support.</span></span>
