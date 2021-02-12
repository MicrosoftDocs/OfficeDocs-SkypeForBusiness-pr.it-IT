---
title: Gestire l'accesso degli utenti a Dati analitici per l'istruzione
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Informazioni su come gestire l'accesso degli utenti a Dati analitici per l'istruzione in Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32bd773975ff6b67d28ab765ffa7c932e978af7d
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145936"
---
# <a name="manage-user-access-to-education-insights"></a><span data-ttu-id="3bb09-103">Gestire l'accesso degli utenti a Dati analitici per l'istruzione</span><span class="sxs-lookup"><span data-stu-id="3bb09-103">Manage user access to Education Insights</span></span>

<span data-ttu-id="3bb09-104">Questo documento illustra la procedura necessaria per gestire l'accesso degli utenti a [Dati analitici per l'istruzione in Microsoft Teams](class-insights.md).</span><span class="sxs-lookup"><span data-stu-id="3bb09-104">This document provides the steps required to manage user access to [Education Insights in Microsoft Teams](class-insights.md).</span></span>

<span data-ttu-id="3bb09-105">È necessario fornire le autorizzazioni per i responsabili dell'istruzione, i dirigenti distrettuali, i presidi scolastici, i dirigenti scolastici, i consulenti, i responsabili delle aree di apprendimento, i direttori dei programmi, gli assistenti sociali e gli psicologi.</span><span class="sxs-lookup"><span data-stu-id="3bb09-105">You need to provide permissions for education leaders, district leaders, school principals, head teachers, counselors, heads of learning areas, program directors, social workers, and psychologists.</span></span> <span data-ttu-id="3bb09-106">Ai docenti viene *automaticamente* concessa l'autorizzazione quando sono proprietari di un team di classe.</span><span class="sxs-lookup"><span data-stu-id="3bb09-106">Educators are *automatically* given permission when they own a class team.</span></span>

<span data-ttu-id="3bb09-107">Per fornire Dati analitici a livello di organizzazione, è necessario [importare i dati dal sistema informativo degli studenti (SIS)](education-insights-sis-data-sync.md) in modo che la struttura gerarchica del sistema didattico di Dati analitici sia mappata correttamente.</span><span class="sxs-lookup"><span data-stu-id="3bb09-107">To provide organization-level Insights, you must [import data from the Student Information System (SIS)](education-insights-sis-data-sync.md) so that Insights has the hierarchical structure of the educational system mapped correctly.</span></span>

> [!NOTE]
> <span data-ttu-id="3bb09-108">Solo l'amministratore globale può gestire l'accesso degli utenti a Dati analitici.</span><span class="sxs-lookup"><span data-stu-id="3bb09-108">Only Global Administrator can manage user access to Insights.</span></span>

> [!TIP]
> <span data-ttu-id="3bb09-109">È consigliabile abilitare Dati analitici per tutti i responsabili della didattica in modo che abbiano a disposizione i dati per conoscere ogni istituto e possano identificare rapidamente i problemi, nonché fornire supporto ai docenti.</span><span class="sxs-lookup"><span data-stu-id="3bb09-109">We recommend that you enable Insights for all your education leaders so that they have the data to understand each school, and the ability to quickly identify problems and provide support to their educators.</span></span> <span data-ttu-id="3bb09-110">Anche se si esegue un progetto pilota, può comunque essere utile mantenere Dati analitici abilitato per tutti i responsabili della didattica, impostando però come destinatari delle comunicazioni solo il gruppo pilota di utenti.</span><span class="sxs-lookup"><span data-stu-id="3bb09-110">Even if you're running a pilot, it may still be helpful to keep Insights enabled for all education leaders, but only target communications to the pilot group of users.</span></span>



## <a name="grant-permissions"></a><span data-ttu-id="3bb09-111">Concedere le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3bb09-111">Grant permissions</span></span>

* <span data-ttu-id="3bb09-112">Aprire l'app Dati analitici, fare clic su **Impostazioni** e selezionare **Autorizzazioni utente**</span><span class="sxs-lookup"><span data-stu-id="3bb09-112">Open the Insights app, click **Settings**, and select **User permissions**</span></span>

:::image type="content" source="media/insights-user-permissions.png" alt-text="Impostazioni":::

* <span data-ttu-id="3bb09-114">Selezionare **Aggiungi utenti**.</span><span class="sxs-lookup"><span data-stu-id="3bb09-114">Select **Add users**.</span></span>
* <span data-ttu-id="3bb09-115">Immettere il nome utente o l'indirizzo di posta elettronica di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="3bb09-115">Enter the username or email address of each user.</span></span>
* <span data-ttu-id="3bb09-116">Selezionare il livello di autorizzazione:</span><span class="sxs-lookup"><span data-stu-id="3bb09-116">Select the permission level:</span></span>
  * <span data-ttu-id="3bb09-117">**Accesso a tutte le organizzazioni** indica che l'utente può visualizzare tutte le unità organizzative a tutti i livelli.</span><span class="sxs-lookup"><span data-stu-id="3bb09-117">**Access to all organization** means the user sees all the org units at all levels.</span></span>
  * <span data-ttu-id="3bb09-118">**Accesso a istituti specifici** indica che l'utente può visualizzare gli istituti di istruzione selezionati.</span><span class="sxs-lookup"><span data-stu-id="3bb09-118">**Access to specific schools** means the user sees the selected schools.</span></span> <span data-ttu-id="3bb09-119">Iniziare a digitare e selezionare l'istituto nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3bb09-119">Start typing and select the school from the list.</span></span> <span data-ttu-id="3bb09-120">È possibile aggiungere più istituti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="3bb09-120">You can add multiple schools together.</span></span>
* <span data-ttu-id="3bb09-121">Fare clic su **Aggiungi nuovi utenti**.</span><span class="sxs-lookup"><span data-stu-id="3bb09-121">Click **Add new users**.</span></span>

:::image type="content" source="media/insights-add-users.png" alt-text="Concedere le autorizzazioni":::

> [!NOTE]
> <span data-ttu-id="3bb09-123">Fornire l'autorizzazione solo ai responsabili della didattica che ne hanno bisogno e solo alle unità organizzative di cui sono responsabili.</span><span class="sxs-lookup"><span data-stu-id="3bb09-123">Only provide permission to those education leaders that need them and only to the organizational units they are responsible for.</span></span> <span data-ttu-id="3bb09-124">Se non si è certi che sia necessaria l'autorizzazione dell'utente per una specifica organizzazione, consultare gli esperti in materia di privacy dell'istituto, ad esempio il personale legale o delle risorse umane.</span><span class="sxs-lookup"><span data-stu-id="3bb09-124">If you are unsure whether user permission for a specific organization is required, consult your institution's privacy subject matter experts, such as legal or HR personnel.</span></span>

## <a name="edit-permissions"></a><span data-ttu-id="3bb09-125">Modificare le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3bb09-125">Edit permissions</span></span>
* <span data-ttu-id="3bb09-126">Selezionare l'utente specifico e quindi selezionare **Modifica autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="3bb09-126">Select specific user, then select **Edit permissions**.</span></span>
* <span data-ttu-id="3bb09-127">Aggiornare il livello di autorizzazione o l'elenco degli istituti e fare clic su **Aggiorna autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="3bb09-127">Update the permission level or schools list, and click **Update permissions**.</span></span>

:::image type="content" source="media/insights-edit-users.png" alt-text="Modificare le autorizzazioni":::

## <a name="remove-permissions"></a><span data-ttu-id="3bb09-129">Rimuovere le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3bb09-129">Remove permissions</span></span>
* <span data-ttu-id="3bb09-130">Selezionare gli utenti da rimuovere e quindi selezionare **Rimuovi utenti**.</span><span class="sxs-lookup"><span data-stu-id="3bb09-130">Select the users you want to remove, then select **Remove users**.</span></span>
* <span data-ttu-id="3bb09-131">Questi utenti non potranno più accedere a Dati analitici a livello di organizzazione, ma possono comunque accedervi a livello di classe se sono proprietari di un team di classe.</span><span class="sxs-lookup"><span data-stu-id="3bb09-131">These users no longer have access to organization-level Insights, but can still access class-level Insights if they own a class team.</span></span>

:::image type="content" source="media/insights-remove-users.png" alt-text="Rimuovere le autorizzazioni":::
