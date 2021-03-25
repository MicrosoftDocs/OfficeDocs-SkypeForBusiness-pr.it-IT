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
description: Informazioni sulla pianificazione per i gruppi di Microsoft 365 in Teams, incluse le differenze tra le conversazioni di Gruppi & Teams e il rispetto dei criteri di denominazione dei gruppi in Teams.
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
ms.openlocfilehash: 1acde038bc2df64d7cf35828bf0b08273bf1f095
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108352"
---
<a name="plan-for-microsoft-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="e98cb-103">Pianificare i gruppi di Microsoft 365 durante la creazione di team in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e98cb-103">Plan for Microsoft 365 Groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="e98cb-104">Quando si valuta l'uso dei gruppi di Microsoft 365 o quando si creano team, valutare per cosa verrà usato il team, per chi dovrebbe avere accesso e per quale risultato il team si aspetta di ottenere.</span><span class="sxs-lookup"><span data-stu-id="e98cb-104">When considering the use of Microsoft 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve.</span></span> <span data-ttu-id="e98cb-105">Prestare particolare attenzione al numero di canali creati, in quanto gli utenti possono diventare rapidamente invasi da contenuti troppo sottili (su troppi canali).</span><span class="sxs-lookup"><span data-stu-id="e98cb-105">Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="e98cb-106">Esistono due scenari che giustificano alcune discussioni sulla pianificazione dei gruppi di Microsoft 365 e sul loro impatto su (o da) Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="e98cb-106">There are two scenarios that warrant some discussion around planning of Microsoft 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="e98cb-107">Prima di tutto, poiché i clienti potrebbero avere investimenti esistenti in Gruppi, attualmente supportiamo sia i gruppi pubblici che i gruppi privati, per il numero di membri attualmente supportati, vedi Limiti e specifiche per [Microsoft Teams.](./limits-specifications-teams.md)</span><span class="sxs-lookup"><span data-stu-id="e98cb-107">First, since customers could have existing investments in Groups, we currently support both Public and Private groups, for the number of members currently supported, please see [Limits and specifications for Microsoft Teams](./limits-specifications-teams.md).</span></span> <span data-ttu-id="e98cb-108">Come accennato in precedenza, si vuole gestire l'appartenenza delle persone a un team usando il client Teams anziché l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e98cb-108">As mentioned previously, you want to manage the membership of people to a team using the Teams client rather than the Microsoft 365 admin center.</span></span> <span data-ttu-id="e98cb-109">In questo scenario, se le persone sono abituate a conversazioni in thread nei gruppi di Microsoft 365, è utile annotare che una conversazione di Gruppi è essenzialmente posta elettronica e non corrisponde a un messaggio di chat in un canale di Teams.</span><span class="sxs-lookup"><span data-stu-id="e98cb-109">Given this scenario, if people are used to threaded conversations in Microsoft 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Teams channel.</span></span> <span data-ttu-id="e98cb-110">Informa le persone su questa differenza e suggerisci loro di adottare il formato dei messaggi di chat più flessibile in Teams rispetto all'invio tramite posta elettronica al gruppo tramite Outlook o OWA.</span><span class="sxs-lookup"><span data-stu-id="e98cb-110">Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="e98cb-111">Secondo, per i clienti che non hanno gruppi esistenti definiti in Microsoft 365, è possibile crearli usando l'interfaccia di amministrazione di Microsoft 365, il Web di Teams o i client desktop.</span><span class="sxs-lookup"><span data-stu-id="e98cb-111">Second, for customers who don't have existing Groups defined in Microsoft 365, you can either create them using the Microsoft 365 admin center, the Teams web, or desktop clients.</span></span> <span data-ttu-id="e98cb-112">Come accennato in precedenza, gestire tutte le future appartenenze al gruppo di Microsoft 365 usando il client Teams.</span><span class="sxs-lookup"><span data-stu-id="e98cb-112">As mentioned previously, manage all future membership to the Microsoft 365 group using the Teams client.</span></span> <span data-ttu-id="e98cb-113">Poiché anche l'appartenenza a un team sta definendo l'appartenenza ai gruppi di Microsoft 365, è consigliabile preparare gli utenti per questa modifica.</span><span class="sxs-lookup"><span data-stu-id="e98cb-113">Since membership to a team is also defining membership to Microsoft 365 Groups, you should prepare people for this change.</span></span>

## <a name="teams-respects-microsoft-365-groups-naming-policy-in-private-preview"></a><span data-ttu-id="e98cb-114">Teams rispetta i criteri di denominazione dei gruppi di Microsoft 365 (in anteprima privata)</span><span class="sxs-lookup"><span data-stu-id="e98cb-114">Teams respects Microsoft 365 Groups naming policy (in private preview)</span></span>

<span data-ttu-id="e98cb-115">I criteri di denominazione dei gruppi di Microsoft 365 impostati dall'amministratore verranno applicati in Teams quando gli utenti creano o modificano i nomi dei team.</span><span class="sxs-lookup"><span data-stu-id="e98cb-115">Any Microsoft 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names.</span></span> <span data-ttu-id="e98cb-116">Sono inclusi elementi come prefissi o suffissi obbligatori e l'esclusione di parole escluse.</span><span class="sxs-lookup"><span data-stu-id="e98cb-116">This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

> [!NOTE]
> <span data-ttu-id="e98cb-117">Questa funzionalità è in anteprima privata, il che significa che se non si fa parte di questa anteprima, Teams non è ancora conforme a questo criterio di denominazione dei gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e98cb-117">This feature is in private preview, which means that if you're not part of this preview, Teams doesn't yet adhere to this Microsoft 365 Groups naming policy.</span></span>

<span data-ttu-id="e98cb-118">Per altre informazioni, vedere Criteri di denominazione dei gruppi di [Microsoft 365 in Teams.](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)</span><span class="sxs-lookup"><span data-stu-id="e98cb-118">To learn more, read [Microsoft 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="e98cb-119">Gli articoli seguenti sono utili per trovare contenuti di preparazione e adozione per i gruppi di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="e98cb-119">The following articles are a good place to find readiness and adoption content for your Microsoft 365 Groups:</span></span>

-   [<span data-ttu-id="e98cb-120">Ottenere di più con i gruppi in Outlook</span><span class="sxs-lookup"><span data-stu-id="e98cb-120">Get more with groups in Outlook</span></span>](https://support.office.com/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

-   [<span data-ttu-id="e98cb-121">Aggiungere o rimuovere membri dai gruppi di Microsoft 365 tramite l'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e98cb-121">Add or remove members from Microsoft 365 Groups using the Microsoft 365 admin center</span></span>](https://support.office.com/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)

-   [<span data-ttu-id="e98cb-122">Ripristinare un gruppo eliminato</span><span class="sxs-lookup"><span data-stu-id="e98cb-122">Restore a deleted group</span></span>](/microsoft-365/admin/create-groups/restore-deleted-group)