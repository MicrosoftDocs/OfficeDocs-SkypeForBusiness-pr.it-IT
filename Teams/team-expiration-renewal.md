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
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a><span data-ttu-id="3c7f1-103">Scadenza e rinnovo del team in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3c7f1-103">Team expiration and renewal in Microsoft Teams</span></span>

<span data-ttu-id="3c7f1-104">Le organizzazioni con un numero elevato di team spesso hanno team che non vengono mai effettivamente usati.</span><span class="sxs-lookup"><span data-stu-id="3c7f1-104">Organizations with a large number of teams often have teams that are never actually used.</span></span> <span data-ttu-id="3c7f1-105">Questo problema può verificarsi per diversi motivi, tra cui la sperimentazione del prodotto, la collaborazione in team a breve termine o l'uscita dei proprietari dei team dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3c7f1-105">This can happen because of several reasons including product experimentation, short-term team collaboration, or team owners leaving the organization.</span></span> <span data-ttu-id="3c7f1-106">Nel corso del tempo, questi team possono accumularsi e far gravare di più sulle risorse del tenant.</span><span class="sxs-lookup"><span data-stu-id="3c7f1-106">Over time, such teams can accumulate and create a burden on tenant resources.</span></span>  

<span data-ttu-id="3c7f1-107">Per limitare il numero di team inutilizzati, come amministratore, è possibile usare i criteri di scadenza dei gruppi di [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) per pulire automaticamente i team inutilizzati.</span><span class="sxs-lookup"><span data-stu-id="3c7f1-107">To curb the number of unused teams, as an admin, you can use [Microsoft 365 group expiration policy](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) to automatically clean up unused teams.</span></span> <span data-ttu-id="3c7f1-108">Poiché i team sono supportati da gruppi, i criteri di scadenza dei gruppi vengono applicati automaticamente anche ai team.</span><span class="sxs-lookup"><span data-stu-id="3c7f1-108">Because teams are backed by groups, group expiration policies automatically apply to teams as well.</span></span>

<span data-ttu-id="3c7f1-109">Quando si applicano criteri di scadenza a un team, il proprietario del team riceve una notifica per il rinnovo del team 30, 15 giorni e 1 giorno prima della data di scadenza del team.</span><span class="sxs-lookup"><span data-stu-id="3c7f1-109">When you apply an expiration policy to a team, a team owner receives a notification for team renewal 30 days, 15 days and 1 day before the team's expiration date.</span></span> <span data-ttu-id="3c7f1-110">Quando il proprietario del team riceve la notifica, può fare clic su Rinnova **ora** nelle impostazioni del team per rinnovare il team.</span><span class="sxs-lookup"><span data-stu-id="3c7f1-110">When the team owner receives the notification, they can click **Renew now** in team settings to renew the team.</span></span>

<span data-ttu-id="3c7f1-111">![Screenshot del pulsante Rinnova ora per rinnovare un team nelle impostazioni del team](media/team-expiration.png "Screenshot del pulsante Rinnova ora per rinnovare un team nelle impostazioni del team")</span><span class="sxs-lookup"><span data-stu-id="3c7f1-111">![Screenshot of the Renew Now button to renew a team in team settings](media/team-expiration.png "Screenshot of the Renew Now button to renew a team in team settings")</span></span>

<span data-ttu-id="3c7f1-112">Se il proprietario del team non rinnova il team e non ci sono altre attività nel team fino alla fine dei criteri di scadenza, il team viene messo in stato di "eliminazione reverscita", ovvero può essere ripristinato entro i successivi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="3c7f1-112">If the team owner doesn't renew the team and there is no further activity on the team until the end of the expiration policy, the team is put in a "soft-deleted" state, which means it can be restored within the next 30 days.</span></span>

## <a name="team-auto-renewal"></a><span data-ttu-id="3c7f1-113">Rinnovo automatico del team</span><span class="sxs-lookup"><span data-stu-id="3c7f1-113">Team auto-renewal</span></span>

<span data-ttu-id="3c7f1-114">In alcuni casi il proprietario di un team non riesce a rinnovare il team, ad esempio perché ha dimenticato il rinnovo o non era al momento del rinnovo.</span><span class="sxs-lookup"><span data-stu-id="3c7f1-114">There can be times when a team owner is unable to renew the team perhaps because they forgot to renew or were away when renewal was due.</span></span> <span data-ttu-id="3c7f1-115">In questi scenari, un team in uso può essere eliminato a causa dei criteri di scadenza applicabili al team.</span><span class="sxs-lookup"><span data-stu-id="3c7f1-115">In these scenarios, a team in active use can get deleted because of expiration policies that apply to the team.</span></span>  

<span data-ttu-id="3c7f1-116">Per evitare l'eliminazione accidentale, il rinnovo automatico viene abilitato automaticamente per un team nei criteri di scadenza del gruppo.</span><span class="sxs-lookup"><span data-stu-id="3c7f1-116">To prevent accidental deletion, auto-renewal is automatically enabled for a team in the group expiration policy.</span></span> <span data-ttu-id="3c7f1-117">Dopo aver configurato i criteri di scadenza del gruppo, tutti i team che hanno almeno un canale visitato da qualsiasi membro del team prima della data di scadenza vengono automaticamente rinnovati senza alcun intervento manuale da parte del proprietario del team.</span><span class="sxs-lookup"><span data-stu-id="3c7f1-117">When the group expiration policy is set up, any team that has at least one channel visit from any team member before its expiration date is automatically renewed without any manual intervention from the team owner.</span></span>

## <a name="known-issues"></a><span data-ttu-id="3c7f1-118">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="3c7f1-118">Known issues</span></span>

<span data-ttu-id="3c7f1-119">**La data di scadenza del team e del gruppo sottostante non corrispondono**</span><span class="sxs-lookup"><span data-stu-id="3c7f1-119">**Expiration date of team and underlying group don't match**</span></span>

<span data-ttu-id="3c7f1-120">Prima del rinnovo di un team, viene rinnovato prima il gruppo che lo rappresenta.</span><span class="sxs-lookup"><span data-stu-id="3c7f1-120">Before a team is renewed, the group that backs the team is renewed first.</span></span> <span data-ttu-id="3c7f1-121">Durante il rinnovo, nel gruppo viene impostata una nuova data di scadenza per una data futura.</span><span class="sxs-lookup"><span data-stu-id="3c7f1-121">As part of renewal, a new expiry date is set on the group for a future date.</span></span> <span data-ttu-id="3c7f1-122">Questa nuova data potrebbe non essere immediatamente visibile in Teams.</span><span class="sxs-lookup"><span data-stu-id="3c7f1-122">This new date may not be immediately visible in Teams.</span></span> <span data-ttu-id="3c7f1-123">La sincronizzazione può richiedere fino a 24 ore. Se si verifica una discrepanza tra la data di scadenza di un team e il gruppo sottostante, attendere 24 ore prima di richiedere ulteriore supporto.</span><span class="sxs-lookup"><span data-stu-id="3c7f1-123">It can take up to 24 hours to sync. If you see a discrepancy between the expiry date for a team and its underlying group, wait 24 hours before seeking further support.</span></span>
