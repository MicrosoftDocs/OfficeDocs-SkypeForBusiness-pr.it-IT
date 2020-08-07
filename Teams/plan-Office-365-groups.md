---
title: Pianificare i gruppi di Microsoft 365 durante la creazione di team
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/29/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Informazioni sulla pianificazione dei gruppi di Microsoft 365 in teams, incluse le differenze tra i gruppi & le conversazioni dei team e il modo in cui i team rispettano i criteri di denominazione del gruppo
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 4e714d530e391ad0e5888607df2fb38dfd862581
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581077"
---
<a name="plan-for-microsoft-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="ff222-103">Pianificare i gruppi Microsoft 365 durante la creazione di team in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ff222-103">Plan for Microsoft 365 Groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="ff222-104">Quando si considera l'uso dei gruppi di Microsoft 365 o quando si creano team, valutare il tipo di utilizzo del team, chi deve avere accesso e il risultato che il team si aspetta di ottenere.</span><span class="sxs-lookup"><span data-stu-id="ff222-104">When considering the use of Microsoft 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve.</span></span> <span data-ttu-id="ff222-105">Prestare particolare attenzione al numero di canali creati in quanto gli utenti possono diventare rapidamente invasi da contenuti distribuiti troppo sottili (in troppi canali).</span><span class="sxs-lookup"><span data-stu-id="ff222-105">Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="ff222-106">Esistono due scenari che giustificano una discussione intorno alla pianificazione dei gruppi di Microsoft 365 e al loro impatto su (o tramite) Microsoft teams:</span><span class="sxs-lookup"><span data-stu-id="ff222-106">There are two scenarios that warrant some discussion around planning of Microsoft 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="ff222-107">Prima di tutto, dato che i clienti possono avere investimenti esistenti in gruppi, attualmente Supportiamo gruppi pubblici e privati di meno di 5000 membri.</span><span class="sxs-lookup"><span data-stu-id="ff222-107">First, since customers could have existing investments in Groups, we currently support both Public and Private groups of less than 5000 members.</span></span> <span data-ttu-id="ff222-108">Come accennato in precedenza, si vuole gestire l'appartenenza delle persone a un team usando il client teams anziché l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ff222-108">As mentioned previously, you want to manage the membership of people to a team using the Teams client rather than the Microsoft 365 admin center.</span></span> <span data-ttu-id="ff222-109">Dato questo scenario, se le persone vengono usate per le conversazioni in thread in Microsoft 365 groups, è interessante notare che una conversazione di gruppo è essenzialmente posta elettronica e non la stessa di un messaggio di chat in un canale di teams.</span><span class="sxs-lookup"><span data-stu-id="ff222-109">Given this scenario, if people are used to threaded conversations in Microsoft 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Teams channel.</span></span> <span data-ttu-id="ff222-110">Educare gli utenti a questa differenza e suggerire di adottare il formato di messaggio di chat più flessibile in teams versus inviare tramite posta elettronica il gruppo usando Outlook o OWA.</span><span class="sxs-lookup"><span data-stu-id="ff222-110">Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="ff222-111">In secondo luogo, per i clienti che non hanno gruppi esistenti definiti in Microsoft 365, è possibile crearli usando l'interfaccia di amministrazione di Microsoft 365, il Web teams o i client desktop.</span><span class="sxs-lookup"><span data-stu-id="ff222-111">Second, for customers who don't have existing Groups defined in Microsoft 365, you can either create them using the Microsoft 365 admin center, the Teams web, or desktop clients.</span></span> <span data-ttu-id="ff222-112">Come accennato in precedenza, è possibile gestire tutti i futuri membri del gruppo Microsoft 365 usando il client teams.</span><span class="sxs-lookup"><span data-stu-id="ff222-112">As mentioned previously, manage all future membership to the Microsoft 365 group using the Teams client.</span></span> <span data-ttu-id="ff222-113">Poiché l'appartenenza a un team definisce anche l'appartenenza a gruppi Microsoft 365, è consigliabile preparare le persone per questa modifica.</span><span class="sxs-lookup"><span data-stu-id="ff222-113">Since membership to a team is also defining membership to Microsoft 365 Groups, you should prepare people for this change.</span></span>

## <a name="teams-respects-microsoft-365-groups-naming-policy-in-private-preview"></a><span data-ttu-id="ff222-114">Teams rispetta i criteri di denominazione dei gruppi Microsoft 365 (in anteprima privata)</span><span class="sxs-lookup"><span data-stu-id="ff222-114">Teams respects Microsoft 365 Groups naming policy (in private preview)</span></span>

<span data-ttu-id="ff222-115">Tutti i criteri di denominazione dei gruppi Microsoft 365 impostati dall'amministratore verranno applicati in teams quando gli utenti creano o modificano i nomi del team.</span><span class="sxs-lookup"><span data-stu-id="ff222-115">Any Microsoft 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names.</span></span> <span data-ttu-id="ff222-116">Ciò include elementi come i prefissi o i suffissi obbligatori ed escludendo le parole vietate.</span><span class="sxs-lookup"><span data-stu-id="ff222-116">This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

> [!NOTE]
> <span data-ttu-id="ff222-117">Questa caratteristica è in anteprima privata, il che significa che se non si fa parte di questa anteprima, i team non aderiscono ancora ai criteri di denominazione dei gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ff222-117">This feature is in private preview, which means that if you're not part of this preview, Teams doesn't yet adhere to this Microsoft 365 Groups naming policy.</span></span>

<span data-ttu-id="ff222-118">Per altre informazioni, leggere i [criteri di denominazione dei gruppi di Microsoft 365 in teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span><span class="sxs-lookup"><span data-stu-id="ff222-118">To learn more, read [Microsoft 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="ff222-119">Gli articoli seguenti sono una buona posizione per trovare il contenuto di preparazione e adozione per i gruppi di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="ff222-119">The following articles are a good place to find readiness and adoption content for your Microsoft 365 Groups:</span></span>

-   [<span data-ttu-id="ff222-120">Ottenere di più con i gruppi in Outlook</span><span class="sxs-lookup"><span data-stu-id="ff222-120">Get more with groups in Outlook</span></span>](https://support.office.com/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

-   [<span data-ttu-id="ff222-121">Aggiungere o rimuovere membri dai gruppi di Microsoft 365 tramite l'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ff222-121">Add or remove members from Microsoft 365 Groups using the Microsoft 365 admin center</span></span>](https://support.office.com/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)

-   [<span data-ttu-id="ff222-122">Ripristinare un gruppo eliminato</span><span class="sxs-lookup"><span data-stu-id="ff222-122">Restore a deleted group</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)