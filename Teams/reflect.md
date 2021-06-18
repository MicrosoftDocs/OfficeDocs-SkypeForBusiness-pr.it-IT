---
title: Guida per gli amministratori a Reflect in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: "Una guida per amministratori a Reflect in Microsoft Teams per l'istruzione. "
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 981061e4892f679dac2a4e4f47fdcc929e6a02fb
ms.sourcegitcommit: 35ee6946b6f560a268d1313bf51c3cc94d8d52f1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52997705"
---
# <a name="it-admin-guide-to-reflect-in-microsoft-teams"></a><span data-ttu-id="834ac-103">Guida per gli amministratori a Reflect in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="834ac-103">IT Admin Guide to Reflect in Microsoft Teams</span></span>

<span data-ttu-id="834ac-104">Questo documento fornisce informazioni relative a [Reflect](https://aka.ms/reflect) – una componente primaria di [Education Insights in Microsoft Teams](class-insights.md).</span><span class="sxs-lookup"><span data-stu-id="834ac-104">This document provides information concerning [Reflect](https://aka.ms/reflect) – an integral part of [Education Insights in Microsoft Teams](class-insights.md).</span></span> <span data-ttu-id="834ac-105">Reflect aiuta gli studenti a riconoscere ed esplorare le proprie emozioni offrendo opportunità regolari per condividere ed essere ascoltati.</span><span class="sxs-lookup"><span data-stu-id="834ac-105">Reflect helps students recognize and navigate their emotions by providing regular opportunities to share and be heard.</span></span> <span data-ttu-id="834ac-106">Reflect può contribuire a espandere il lessico emotivo e aumentare l'empatia verso i propri compagni fornendo input utili ai docenti per creare ambienti scolastici più salutari.  </span><span class="sxs-lookup"><span data-stu-id="834ac-106">Reflect can help broaden learners' emotional vocabulary and deepen empathy for their peers while also providing valuable feedback to educators for a healthy classroom community.</span></span>

<span data-ttu-id="834ac-107">Questa app utilizza emoji e granularità emotiva basata sulla ricerca per supportare i docenti introducendo elementi di apprendimento sociale ed emotivo nella loro routine impegnativa.</span><span class="sxs-lookup"><span data-stu-id="834ac-107">This check-in app uses emojis and research-backed emotional granularity to support educators in adding social and emotional learning into their already busy routine.</span></span>


## <a name="privacy-and-security"></a><span data-ttu-id="834ac-108">Privacy e sicurezza</span><span class="sxs-lookup"><span data-stu-id="834ac-108">Privacy and Security</span></span>
<span data-ttu-id="834ac-109">Reflect applica gli stessi standard di sicurezza e riservatezza di Education Insights per proteggere i dati sensibili degli studenti.</span><span class="sxs-lookup"><span data-stu-id="834ac-109">Reflect follows the same privacy and security standards as Education Insights to protect students' sensitive information.</span></span>

<span data-ttu-id="834ac-110">Le informazioni raccolte e visualizzate tramite Reflect soddisfano [oltre 90 standard normativi e di settore](/compliance/regulatory/offering-home), tra cui [GDPR](/compliance/regulatory/gdpr) e [FERPA (Family Education Rights and Privacy Act)](/compliance/regulatory/offering-ferpa) per la sicurezza degli studenti e dei bambini e altre normative simili orientate alla privacy.</span><span class="sxs-lookup"><span data-stu-id="834ac-110">The information collected and shown through Reflect meets [more than 90 regulatory and industry standards](/compliance/regulatory/offering-home), including [GDPR](/compliance/regulatory/gdpr) and the Family [Education Rights and Privacy Act (FERPA)](/compliance/regulatory/offering-ferpa) for students and children's security and other, similar, privacy-oriented regulations.</span></span>

<span data-ttu-id="834ac-111">Gli studenti *non vedono mai* i nomi degli altri studenti, ma solo il modo in cui rispondono. </span><span class="sxs-lookup"><span data-stu-id="834ac-111">Students *never* see the names of other students, only how they responded.</span></span> <span data-ttu-id="834ac-112">Anche se possono vedere la distribuzione delle risposte, *non possono* vedere i nomi associati a ogni riflessione.</span><span class="sxs-lookup"><span data-stu-id="834ac-112">While they can see the distribution of responses, they *cannot* see names associated with each reflection.</span></span> 

> [!NOTE]
> <span data-ttu-id="834ac-113">Se rispondono meno di cinque studenti, nessun dato viene mostrato agli studenti.</span><span class="sxs-lookup"><span data-stu-id="834ac-113">If less than five students respond, no data is shown to the students.</span></span> <span data-ttu-id="834ac-114">In questo modo viene minimizzata la capacità degli studenti di identificare le risposte dei compagni.</span><span class="sxs-lookup"><span data-stu-id="834ac-114">This is to minimize the possibility of students identifying each other's responses.</span></span>

## <a name="data-collection-and-storage"></a><span data-ttu-id="834ac-115">Raccolta e archiviazione dei dati</span><span class="sxs-lookup"><span data-stu-id="834ac-115">Data collection and storage</span></span>
<span data-ttu-id="834ac-116">I dati appartengono all'istituto di istruzione, e Microsoft si limita solo a raccoglierli e ad archiviarli.</span><span class="sxs-lookup"><span data-stu-id="834ac-116">The data belongs to the educational institution, and Microsoft only collects the data and stores it.</span></span> <span data-ttu-id="834ac-117">Il personale Microsoft non può accedere ai dati o visualizzarli, se non per quanto consentito dalla conformità in modo controllato per gestire il servizio, ad esempio per il recupero dei dati.</span><span class="sxs-lookup"><span data-stu-id="834ac-117">Microsoft personnel cannot access the data or see it, except as allowed by compliance in an audited way to maintain the service, such as data recovery.</span></span>

<span data-ttu-id="834ac-118">I dati vengono archiviati in Education Insights.</span><span class="sxs-lookup"><span data-stu-id="834ac-118">The data is stored in Education Insights.</span></span> <span data-ttu-id="834ac-119">Per impostazione predefinita, Education Insights è attivato.</span><span class="sxs-lookup"><span data-stu-id="834ac-119">By default, Education Insights is turned on.</span></span> <span data-ttu-id="834ac-120">Quando si sceglie di non usare il servizio, **tutti i dati raccolti per Reflect verranno eliminati**.</span><span class="sxs-lookup"><span data-stu-id="834ac-120">When you opt-out, we **delete all the data collected for Reflect**.</span></span> <span data-ttu-id="834ac-121">Se si riattiva Education Insights, la raccolta dei dati inizierà dal momento in cui il servizio viene riattivato.</span><span class="sxs-lookup"><span data-stu-id="834ac-121">Turn Education Insights back on, and we start collecting data from the time it's re-enabled.</span></span>

<span data-ttu-id="834ac-122">Nella [Guida per gli amministratori a Education Insights](class-insights.md), puoi leggere il funzionamento di Education Insights (inclusi percorsi di archiviazione) e [come attivare o disattivare Education Insights](class-insights.md#turn-insights-on-or-off) quando vuoi cancellare i dati o abilitare il servizio.</span><span class="sxs-lookup"><span data-stu-id="834ac-122">In the [IT Admin Guide to Education Insights](class-insights.md), you can read how Education Insights works (including storage locations) and [how to turn Education Insights off or on](class-insights.md#turn-insights-on-or-off) when you want to delete the data or enable the service.</span></span>

<span data-ttu-id="834ac-123">I dati sono raccolti dagli studenti in Reflect, anche se i dati degli utenti guest non vengono raccolti.</span><span class="sxs-lookup"><span data-stu-id="834ac-123">Data is collected from student in Reflect, though guest data is not collected.</span></span> <span data-ttu-id="834ac-124">**Se uno studente viene definito come un utente guest, i dati non vengono raccolti.**</span><span class="sxs-lookup"><span data-stu-id="834ac-124">**If a student is defined as a guest, their data is not collected.**</span></span> 

## <a name="enable-reflect"></a><span data-ttu-id="834ac-125">Abilita Reflect</span><span class="sxs-lookup"><span data-stu-id="834ac-125">Enable Reflect</span></span>
<span data-ttu-id="834ac-126">Se gestisci i criteri di configurazione delle app per il tuo istituto, assicurai che Reflect sia *consentito* nel tuo tenant.</span><span class="sxs-lookup"><span data-stu-id="834ac-126">If you manage the app setup policy for your institution, ensure that Reflect is *allowed* in your tenant.</span></span> <span data-ttu-id="834ac-127">Puoi anche aggiungere Reflect ai team di classe rilevanti dall'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="834ac-127">You can also add Reflect to the relevant class teams from the Teams admin center.</span></span>

<span data-ttu-id="834ac-128">Per consentire a un utente di installare e interagire con qualsiasi app, devi autorizzazione l'app a livello di organizzazione nella pagina **Gestisci app** e nel **criterio di autorizzazione dell'app** assegnato all'utente.</span><span class="sxs-lookup"><span data-stu-id="834ac-128">To enable a user to install and interact with any app, you must allow the app at the org level on the **Manage apps** page and the **app permission policy** assigned to the user.</span></span>

<span data-ttu-id="834ac-129">Se in precedenza hai stabilito che ogni app deve essere autorizzata, passa alla pagina Gestisci app e "consenti" Reflect.</span><span class="sxs-lookup"><span data-stu-id="834ac-129">If you have previously defined that each app needs to be allowed, please go to the Manage apps page and 'allow' Reflect.</span></span> <span data-ttu-id="834ac-130">**Quando blocchi un'app, l'app non compare in Teams per tutti gli utenti dell'organizzazione.**</span><span class="sxs-lookup"><span data-stu-id="834ac-130">**When you block an app, the app doesn't appear in Teams for any users in your organization.**</span></span>

> [!NOTE]
> <span data-ttu-id="834ac-131">Per accedere all’app Reflect, è necessaria una licenza A1, A3 o A5 per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="834ac-131">To have access to the Reflect app, you will need an A1, A3, or A5 license for Microsoft 365.</span></span>

> [!TIP]
> <span data-ttu-id="834ac-132">Per altri dettagli, leggi [Come consentire un'app o aggiungerla a un team di classe](manage-apps.md#allow-and-block-apps).</span><span class="sxs-lookup"><span data-stu-id="834ac-132">For more details, read [how to allow an app or to add it to a class team](manage-apps.md#allow-and-block-apps).</span></span>

## <a name="where-do-educators-find-reflect"></a><span data-ttu-id="834ac-133">Dove possono trovare Reflect i docenti?</span><span class="sxs-lookup"><span data-stu-id="834ac-133">Where do educators find Reflect?</span></span>
<span data-ttu-id="834ac-134">Dopo aver abilitato Reflect, i docenti entrano nella classe e selezionano **Nuova conversazione**.</span><span class="sxs-lookup"><span data-stu-id="834ac-134">Once you have enabled Reflect, educators go to the class and select **New Conversation**.</span></span> <span data-ttu-id="834ac-135">Possono poi selezionare '**…**' per aprire le estensioni di messaggistica e immettere **Reflect** nella barra di ricerca.</span><span class="sxs-lookup"><span data-stu-id="834ac-135">They then select '**…**' to bring up messaging extensions and enter **Reflect** in the search bar.</span></span> <span data-ttu-id="834ac-136">La finestra di dialogo li guida nella definizione delle domanda e delle autorizzazioni di lettura degli utenti</span><span class="sxs-lookup"><span data-stu-id="834ac-136">The dialog box guides them through defining the question and who can see what.</span></span>

:::image type="content" source="media/reflect-add-app.png" alt-text="Aggiungere Reflect al team di classe":::

<span data-ttu-id="834ac-138">È possibile fare clic con il pulsante destro del mouse sull'icona Reflect e selezionare **Blocca in alto** per accedervi rapidamente.</span><span class="sxs-lookup"><span data-stu-id="834ac-138">They can right-click on the Reflect icon and select **Pin** for easy access.</span></span>

:::image type="content" source="media/reflect-pin-app.png" alt-text="Bloccare in alto l’app Reflect":::

> [!TIP]
> <span data-ttu-id="834ac-140">È anche possibile individuare l'app Insights tramite questo collegamento: [https://aka.ms/getReflect](https://aka.ms/getReflect)</span><span class="sxs-lookup"><span data-stu-id="834ac-140">You can also locate the Reflect app through this link: [https://aka.ms/getReflect](https://aka.ms/getReflect)</span></span>

> [!TIP]
> <span data-ttu-id="834ac-141">Per altri dettagli, visita la [pagina dell'assistenza di Reflect](https://support.microsoft.com/topic/e9198f62-7860-4532-821f-53ef14afa79a).</span><span class="sxs-lookup"><span data-stu-id="834ac-141">For more details, visit [Reflect support page](https://support.microsoft.com/topic/e9198f62-7860-4532-821f-53ef14afa79a).</span></span> <span data-ttu-id="834ac-142">Questa pagina fornisce istruzioni sia per i docenti che per gli studenti, e descrive come creare il primo check-in di Reflect.</span><span class="sxs-lookup"><span data-stu-id="834ac-142">This page provides guidelines for both educators and students and helps with how to create their first Reflect check-in.</span></span>
