---
title: Pianificare i gruppi di Microsoft 365 durante la creazione di team
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/29/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Informazioni sulla pianificazione per Microsoft 365 gruppi in Teams, incluse le differenze tra le conversazioni & Teams gruppi e il modo in cui Teams criteri di denominazione dei gruppi.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 7e93b66f9a7a0abc4dfc2e3484818da28a65f36a
ms.sourcegitcommit: 5a39061c2156531f4b7f5f69eecf81a8c8b238d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2021
ms.locfileid: "52030046"
---
<a name="plan-for-microsoft-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="6ffd6-103">Pianificare i Microsoft 365 di lavoro durante la creazione di team in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6ffd6-103">Plan for Microsoft 365 Groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="6ffd6-104">Quando si valuta l'uso di Microsoft 365 Groups o quando si creano team, valutare per cosa verrà usato il team, per chi dovrebbe avere accesso e per quale risultato il team si aspetta di ottenere.</span><span class="sxs-lookup"><span data-stu-id="6ffd6-104">When considering the use of Microsoft 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve.</span></span> <span data-ttu-id="6ffd6-105">Prestare particolare attenzione al numero di canali creati, in quanto gli utenti possono diventare rapidamente invasi da contenuti troppo sottili (su troppi canali).</span><span class="sxs-lookup"><span data-stu-id="6ffd6-105">Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="6ffd6-106">Esistono due scenari che giustificano alcune discussioni sulla pianificazione Microsoft 365 gruppi di lavoro e sul loro impatto sulle Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="6ffd6-106">There are two scenarios that warrant some discussion around planning of Microsoft 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="6ffd6-107">Prima di tutto, poiché i clienti potrebbero avere investimenti esistenti in Gruppi, attualmente sono supportati sia i gruppi pubblici che i gruppi [privati,](./limits-specifications-teams.md)per il numero di membri attualmente supportati, vedere Limiti e specifiche per Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="6ffd6-107">First, since customers could have existing investments in Groups, we currently support both Public and Private groups, for the number of members currently supported, please see [Limits and specifications for Microsoft Teams](./limits-specifications-teams.md).</span></span> <span data-ttu-id="6ffd6-108">Come accennato in precedenza, si vuole gestire l'appartenenza delle persone a un team usando il client Teams anziché l'interfaccia Microsoft 365 di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="6ffd6-108">As mentioned previously, you want to manage the membership of people to a team using the Teams client rather than the Microsoft 365 admin center.</span></span> <span data-ttu-id="6ffd6-109">In questo scenario, se le persone sono abituate a conversazioni in thread in gruppi di Microsoft 365, è utile annotare che una conversazione di Gruppi è essenzialmente posta elettronica e non corrisponde a un messaggio di chat in un canale Teams.</span><span class="sxs-lookup"><span data-stu-id="6ffd6-109">Given this scenario, if people are used to threaded conversations in Microsoft 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Teams channel.</span></span> <span data-ttu-id="6ffd6-110">Informa i tuoi utenti su questa differenza e suggerisci loro di adottare il formato dei messaggi di chat più flessibile in Teams invece di inviare un messaggio di posta elettronica al gruppo usando Outlook o OWA.</span><span class="sxs-lookup"><span data-stu-id="6ffd6-110">Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="6ffd6-111">In secondo momento, per i clienti che non hanno gruppi esistenti definiti in Microsoft 365, è possibile crearli usando l'interfaccia di amministrazione di Microsoft 365, il Web Teams o i client desktop.</span><span class="sxs-lookup"><span data-stu-id="6ffd6-111">Second, for customers who don't have existing Groups defined in Microsoft 365, you can either create them using the Microsoft 365 admin center, the Teams web, or desktop clients.</span></span> <span data-ttu-id="6ffd6-112">Come accennato in precedenza, gestire tutte le future appartenenze al gruppo Microsoft 365 tramite il client Teams.</span><span class="sxs-lookup"><span data-stu-id="6ffd6-112">As mentioned previously, manage all future membership to the Microsoft 365 group using the Teams client.</span></span> <span data-ttu-id="6ffd6-113">Poiché anche l'appartenenza a un team sta definendo l'appartenenza Microsoft 365 gruppi, è consigliabile preparare le persone per questa modifica.</span><span class="sxs-lookup"><span data-stu-id="6ffd6-113">Since membership to a team is also defining membership to Microsoft 365 Groups, you should prepare people for this change.</span></span>

## <a name="teams-respects-microsoft-365-groups-naming-policy"></a><span data-ttu-id="6ffd6-114">Teams rispetta i criteri di denominazione Microsoft 365 gruppi</span><span class="sxs-lookup"><span data-stu-id="6ffd6-114">Teams respects Microsoft 365 Groups naming policy</span></span>

<span data-ttu-id="6ffd6-115">Tutti Microsoft 365 di denominazione dei gruppi di lavoro impostati dall'amministratore verranno applicati in Teams quando gli utenti creano o modificano i nomi dei team.</span><span class="sxs-lookup"><span data-stu-id="6ffd6-115">Any Microsoft 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names.</span></span> <span data-ttu-id="6ffd6-116">Sono inclusi elementi come prefissi o suffissi obbligatori e l'esclusione di parole escluse.</span><span class="sxs-lookup"><span data-stu-id="6ffd6-116">This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

<span data-ttu-id="6ffd6-117">Per altre informazioni, vedere criteri [Microsoft 365 di denominazione dei](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)gruppi in Teams .</span><span class="sxs-lookup"><span data-stu-id="6ffd6-117">To learn more, read [Microsoft 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="6ffd6-118">Gli articoli seguenti sono utili per trovare contenuti di preparazione e adozione per i Microsoft 365 gruppi:</span><span class="sxs-lookup"><span data-stu-id="6ffd6-118">The following articles are a good place to find readiness and adoption content for your Microsoft 365 Groups:</span></span>

-   [<span data-ttu-id="6ffd6-119">Ottieni di più con i gruppi in Outlook</span><span class="sxs-lookup"><span data-stu-id="6ffd6-119">Get more with groups in Outlook</span></span>](https://support.office.com/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

-   [<span data-ttu-id="6ffd6-120">Aggiungere o rimuovere membri da Microsoft 365 gruppi usando l'interfaccia Microsoft 365 di amministrazione</span><span class="sxs-lookup"><span data-stu-id="6ffd6-120">Add or remove members from Microsoft 365 Groups using the Microsoft 365 admin center</span></span>](https://support.office.com/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)

-   [<span data-ttu-id="6ffd6-121">Ripristinare un gruppo eliminato</span><span class="sxs-lookup"><span data-stu-id="6ffd6-121">Restore a deleted group</span></span>](/microsoft-365/admin/create-groups/restore-deleted-group)
