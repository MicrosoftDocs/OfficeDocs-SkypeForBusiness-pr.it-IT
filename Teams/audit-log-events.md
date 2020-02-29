---
title: Eseguire una ricerca nel log di controllo per gli eventi in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anach
search.appverid: MET150
description: Informazioni su come recuperare i dati di Microsoft teams dal log di controllo di Office 365.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f53d1a0b5e600de9d38233b243dba3486b88bf1
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341624"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="f6a1e-103">Eseguire una ricerca nel log di controllo per gli eventi in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f6a1e-103">Search the audit log for events in Microsoft Teams</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="f6a1e-104">Il log di controllo consente di analizzare attività specifiche in tutti i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f6a1e-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="f6a1e-105">Per i team, Ecco alcune delle attività che vengono controllate:</span><span class="sxs-lookup"><span data-stu-id="f6a1e-105">For Teams, here are some of the activities that are audited:</span></span>

- <span data-ttu-id="f6a1e-106">Creazione di Team</span><span class="sxs-lookup"><span data-stu-id="f6a1e-106">Team creation</span></span>

- <span data-ttu-id="f6a1e-107">Eliminazione del team</span><span class="sxs-lookup"><span data-stu-id="f6a1e-107">Team deletion</span></span>

- <span data-ttu-id="f6a1e-108">Canale aggiunto</span><span class="sxs-lookup"><span data-stu-id="f6a1e-108">Added channel</span></span>

- <span data-ttu-id="f6a1e-109">Impostazione modificata</span><span class="sxs-lookup"><span data-stu-id="f6a1e-109">Changed setting</span></span>

> [!NOTE]
> <span data-ttu-id="f6a1e-110">Gli eventi di controllo dei canali privati vengono registrati anche per i team e i canali standard.</span><span class="sxs-lookup"><span data-stu-id="f6a1e-110">Audit events from private channels are also logged as they are for teams and standard channels.</span></span>

<span data-ttu-id="f6a1e-111">Per visualizzare l'elenco completo delle attività controllate in Office 365, vedere [cercare il log di controllo nel centro conformità & sicurezza di office 365](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="f6a1e-111">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="f6a1e-112">Attivare il controllo in teams</span><span class="sxs-lookup"><span data-stu-id="f6a1e-112">Turn on auditing in Teams</span></span>

<span data-ttu-id="f6a1e-113">Prima di poter esaminare i dati di controllo, è necessario attivare prima di tutto il controllo nel [centro conformità & sicurezza](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="f6a1e-113">Before you can look at audit data, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="f6a1e-114">Per assistenza durante l'attivazione del controllo, leggere [attivare o disattivare la ricerca nel log di controllo di Office 365](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="f6a1e-114">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6a1e-115">I dati di controllo sono disponibili solo dal momento in cui è stato attivato il controllo.</span><span class="sxs-lookup"><span data-stu-id="f6a1e-115">Audit data is only available from the point at which you turned on Auditing.</span></span>

## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="f6a1e-116">Recuperare i dati di teams dal log di controllo</span><span class="sxs-lookup"><span data-stu-id="f6a1e-116">Retrieve Teams data from the audit log</span></span>

1. <span data-ttu-id="f6a1e-117">Per recuperare i log di controllo, accedere al [centro conformità & sicurezza](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="f6a1e-117">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="f6a1e-118">In **ricerca**selezionare **Ricerca log di controllo**.</span><span class="sxs-lookup"><span data-stu-id="f6a1e-118">Under **Search**, select **Audit log search**.</span></span>
1. <span data-ttu-id="f6a1e-119">Usare la **ricerca** per filtrare in base alle attività, alle date e agli utenti che si desidera controllare.</span><span class="sxs-lookup"><span data-stu-id="f6a1e-119">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>
1. <span data-ttu-id="f6a1e-120">Esportare i risultati in Excel per un'ulteriore analisi.</span><span class="sxs-lookup"><span data-stu-id="f6a1e-120">Export your results to Excel for further analysis.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6a1e-121">I dati di controllo sono visibili solo nel log di controllo se è attivato il controllo.</span><span class="sxs-lookup"><span data-stu-id="f6a1e-121">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="external-user-scenario"></a><span data-ttu-id="f6a1e-122">Scenario utente esterno</span><span class="sxs-lookup"><span data-stu-id="f6a1e-122">External user scenario</span></span>

<span data-ttu-id="f6a1e-123">Uno scenario in cui è consigliabile tenersi d'occhio, da un punto di vista aziendale, è l'aggiunta di utenti esterni all'ambiente teams.</span><span class="sxs-lookup"><span data-stu-id="f6a1e-123">One scenario you might want to keep an eye on, from a business perspective, is the addition of external users to your Teams environment.</span></span> <span data-ttu-id="f6a1e-124">Se gli utenti esterni sono abilitati, è consigliabile monitorarne la presenza.</span><span class="sxs-lookup"><span data-stu-id="f6a1e-124">If external users are enabled, then monitoring their presence is a good idea.</span></span>

![Screenshot di un elenco di eventi attivati dalle eliminazioni di massa](media/TeamsExternalUserAddPolicy.png)

<span data-ttu-id="f6a1e-126">La schermata di questo criterio per il monitoraggio degli utenti esterni consente di assegnare un nome al criterio, impostare la gravità in base alle esigenze aziendali, impostarlo come (in questo caso) una singola attività e quindi stabilire i parametri che verranno monitorati in modo specifico solo nell'aggiunta di utenti non interni e limita questa attività a Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="f6a1e-126">The screenshot of this policy to monitor external user adds allows you to name the policy, set the severity according to your business needs, set it as (in this case) a single activity, and then establish the parameters that will specifically monitor only the addition of non-internal users, and limit this activity to Microsoft Teams.</span></span>

<span data-ttu-id="f6a1e-127">I risultati di questo criterio saranno quindi in grado di essere visualizzati nel log attività:</span><span class="sxs-lookup"><span data-stu-id="f6a1e-127">Then results from this policy will be able to be viewed in the activity log:</span></span>

![Screenshot di un elenco di eventi attivati dalle eliminazioni di massa](media/TeamsExternalUserList.png)

<span data-ttu-id="f6a1e-129">Qui puoi rivedere le corrispondenze ai criteri impostati e apportare le eventuali modifiche necessarie oppure esportare i risultati per usarli altrove.</span><span class="sxs-lookup"><span data-stu-id="f6a1e-129">Here you can review matches to the policy you've set, and make any adjustments as needed, or export the results to use elsewhere.</span></span>

## <a name="mass-delete-scenario"></a><span data-ttu-id="f6a1e-130">Scenario di eliminazione di massa</span><span class="sxs-lookup"><span data-stu-id="f6a1e-130">Mass delete scenario</span></span>

<span data-ttu-id="f6a1e-131">Come accennato in precedenza, è possibile monitorare gli scenari di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="f6a1e-131">As mentioned above, you can monitor deletion scenarios.</span></span> <span data-ttu-id="f6a1e-132">È possibile creare un criterio che monitora l'eliminazione di massa dei siti di teams:</span><span class="sxs-lookup"><span data-stu-id="f6a1e-132">It's possible to create a policy that would monitor mass deletion of Teams sites:</span></span>

![Screenshot della pagina di creazione dei criteri che mostra l'impostazione di un criterio per il rilevamento dell'eliminazione di massa del team](media/TeamsMassDeletePolicy.png)

<span data-ttu-id="f6a1e-134">Come Mostra la schermata, è possibile impostare molti parametri diversi per questo criterio per monitorare le eliminazioni dei team, tra cui gravità, azione singola o ripetuta e parametri che limitano questa operazione ai team e all'eliminazione del sito.</span><span class="sxs-lookup"><span data-stu-id="f6a1e-134">As the screenshot shows, you can set many different parameters for this policy to monitor Teams deletions, including severity, single or repeated action, and parameters limiting this to Teams and site deletion.</span></span> <span data-ttu-id="f6a1e-135">Questa operazione può essere eseguita indipendentemente da un modello oppure è possibile che sia stato creato un modello per la base dei criteri, a seconda delle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f6a1e-135">This can be done independently of a template, or you may have a template created to base this policy off, depending on your organizational needs.</span></span>

<span data-ttu-id="f6a1e-136">Dopo aver stabilito un criterio che funzionerà per l'azienda, è possibile esaminare i risultati nel log attività come vengono attivati gli eventi:</span><span class="sxs-lookup"><span data-stu-id="f6a1e-136">Once you've established a policy that will work for your business, you can then review the results in the activity log as events are triggered:</span></span>

![Screenshot di un elenco di eventi attivati dalle eliminazioni di massa](media/TeamsMassDeleteList.png)

<span data-ttu-id="f6a1e-138">È possibile filtrare i criteri impostati per visualizzare i risultati di tale criterio.</span><span class="sxs-lookup"><span data-stu-id="f6a1e-138">You can filter down to the policy you've set to see the results of that policy.</span></span> <span data-ttu-id="f6a1e-139">Se i risultati ottenuti nel registro attività non sono soddisfacenti (forse si verificano molti risultati o niente affatto), potrebbe essere utile ottimizzare la query per renderla più pertinente a ciò che è necessario.</span><span class="sxs-lookup"><span data-stu-id="f6a1e-139">If the results you're getting in the activity log are not satisfactory (maybe you're seeing a lot of results, or nothing at all), this may help you to fine-tune the query to make it more relevant to what you need it to do.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="f6a1e-140">Video: TechTip: uso della ricerca nel log di controllo in teams</span><span class="sxs-lookup"><span data-stu-id="f6a1e-140">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="f6a1e-141">Partecipare a un responsabile del programma per Teams, che illustra come eseguire la ricerca di un log di controllo per i team nel centro conformità & sicurezza di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f6a1e-141">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span>

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
