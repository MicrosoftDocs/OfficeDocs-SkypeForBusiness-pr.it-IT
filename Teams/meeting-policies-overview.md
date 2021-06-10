---
title: Gestire i criteri di riunione
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- seo-marvel-apr2020
description: Informazioni su come gestire le impostazioni dei criteri di riunione in Teams e usarle per controllare le funzionalità disponibili per i partecipanti alle riunioni programmate dagli utenti.
ms.openlocfilehash: d9f403625225711cb21245ca01262d3c0140063f
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598732"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="2dc87-103">Gestire i criteri di riunione in Teams</span><span class="sxs-lookup"><span data-stu-id="2dc87-103">Manage meeting policies in Teams</span></span>

<span data-ttu-id="2dc87-104"><a name="bkautomatically-admit-people"> </a></span><span class="sxs-lookup"><span data-stu-id="2dc87-104"><a name="bkautomatically-admit-people"> </a></span></span>

<span data-ttu-id="2dc87-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span><span class="sxs-lookup"><span data-stu-id="2dc87-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span></span>

<span data-ttu-id="2dc87-106"><a name="bkallow-transcription"> </a></span><span class="sxs-lookup"><span data-stu-id="2dc87-106"><a name="bkallow-transcription"> </a></span></span>

<span data-ttu-id="2dc87-107">I criteri riunione vengono usati per controllare le funzionalità disponibili per i partecipanti alle riunioni programmate dagli utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2dc87-107">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="2dc87-108">È possibile usare il criterio globale (predefinito a livello di organizzazione) creato automaticamente oppure creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="2dc87-108">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="2dc87-109">Si possono gestire i criteri di riunione nell'interfaccia di amministrazione di Microsoft Teams o tramite [PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2dc87-109">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2dc87-110">Per informazioni sull'utilizzo dei ruoli per gestire le autorizzazioni dei relatori e dei partecipanti delle riunioni, vedere [Ruoli in una riunione di Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span><span class="sxs-lookup"><span data-stu-id="2dc87-110">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="2dc87-111">È possibile implementare i criteri nei modi descritti di seguito. La scelta influisce sull'esperienza di riunione per gli utenti prima, durante o dopo una riunione.</span><span class="sxs-lookup"><span data-stu-id="2dc87-111">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="2dc87-112">Tipo di implementazione</span><span class="sxs-lookup"><span data-stu-id="2dc87-112">Implementation type</span></span>  |<span data-ttu-id="2dc87-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2dc87-113">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="2dc87-114">Per organizzatore</span><span class="sxs-lookup"><span data-stu-id="2dc87-114">Per-organizer</span></span>    |<span data-ttu-id="2dc87-115">Quando si implementa un criterio per organizzatore, tutti i partecipanti alla riunione ereditano il criterio dell'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="2dc87-115">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="2dc87-116">Ad esempio, **Ammetti automaticamente le persone** è un criterio per organizzatore e controlla se gli utenti accedono direttamente alla riunione oppure attendono nella sala di attesa per le riunioni pianificate dall'utente a cui è assegnato il criterio.</span><span class="sxs-lookup"><span data-stu-id="2dc87-116">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="2dc87-117">Per utente</span><span class="sxs-lookup"><span data-stu-id="2dc87-117">Per-user</span></span>    |<span data-ttu-id="2dc87-118">Quando si implementano criteri per utente, viene applicato solo il criterio per utente per limitare l'uso di determinate funzionalità da parte dell'organizzatore e/o dei partecipanti alla riunione.</span><span class="sxs-lookup"><span data-stu-id="2dc87-118">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="2dc87-119">Ad esempio, **Consenti l'uso di Riunione immediata nei canali** è un criterio per utente.</span><span class="sxs-lookup"><span data-stu-id="2dc87-119">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="2dc87-120">Per organizzatore e per utente</span><span class="sxs-lookup"><span data-stu-id="2dc87-120">Per-organizer and per-user</span></span>     |<span data-ttu-id="2dc87-121">Quando si implementa una combinazione di criteri per organizzatore e per utente, l'uso di alcune funzionalità da parte dei partecipanti alla riunione è limitato, in base ai criteri applicati al singolo utente e ai criteri dell'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="2dc87-121">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="2dc87-122">Ad esempio, **Consenti registrazione cloud** è un criterio per organizzazione e per utente.</span><span class="sxs-lookup"><span data-stu-id="2dc87-122">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="2dc87-123">Attivare questa impostazione per consentire all'organizzatore della riunione e ai partecipanti di avviare o interrompere una registrazione.</span><span class="sxs-lookup"><span data-stu-id="2dc87-123">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="2dc87-124">È possibile modificare le impostazioni nel criterio globale o creare e assegnare uno o più criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="2dc87-124">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="2dc87-125">Se non si creano e assegnano criteri personalizzati, gli utenti riceveranno il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="2dc87-125">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="2dc87-126">Il pulsante Dettagli riunione sarà disponibile se un utente ha le licenze di audioconferenza abilitate o se l'utente è autorizzato a partecipare alle audioconferenze; in caso contrario, i dettagli della riunione non saranno disponibili.</span><span class="sxs-lookup"><span data-stu-id="2dc87-126">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="2dc87-127">Creare un criterio di riunione personalizzato</span><span class="sxs-lookup"><span data-stu-id="2dc87-127">Create a custom meeting policy</span></span>

1. <span data-ttu-id="2dc87-128">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Riunioni** > **Criteri riunione**.</span><span class="sxs-lookup"><span data-stu-id="2dc87-128">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="2dc87-129">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="2dc87-129">Click **Add**.</span></span>
3. <span data-ttu-id="2dc87-130">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="2dc87-130">Enter a name and description for the policy.</span></span> <span data-ttu-id="2dc87-131">Il nome non può contenere caratteri speciali o più di 64 caratteri.</span><span class="sxs-lookup"><span data-stu-id="2dc87-131">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="2dc87-132">Scegliere le impostazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="2dc87-132">Choose the settings that you want.</span></span>
5. <span data-ttu-id="2dc87-133">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2dc87-133">Click **Save**.</span></span>

<span data-ttu-id="2dc87-134">Ad esempio, si supponga di avere un gruppo di utenti e di voler limitare la larghezza di banda necessaria per la riunione.</span><span class="sxs-lookup"><span data-stu-id="2dc87-134">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="2dc87-135">È possibile creare un nuovo criterio personalizzato denominato "Larghezza di banda limitata" e disabilitare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2dc87-135">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="2dc87-136">In **Audio e video**:</span><span class="sxs-lookup"><span data-stu-id="2dc87-136">Under **Audio & video**:</span></span>

- <span data-ttu-id="2dc87-137">Disattivare Consenti registrazione cloud.</span><span class="sxs-lookup"><span data-stu-id="2dc87-137">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="2dc87-138">Disattivare Consenti video IP.</span><span class="sxs-lookup"><span data-stu-id="2dc87-138">Turn off Allow IP video.</span></span>

<span data-ttu-id="2dc87-139">In **Condivisione di contenuti**:</span><span class="sxs-lookup"><span data-stu-id="2dc87-139">Under **Content sharing**:</span></span>

- <span data-ttu-id="2dc87-140">Disabilitare la modalità di condivisione dello schermo.</span><span class="sxs-lookup"><span data-stu-id="2dc87-140">Disable screen sharing mode.</span></span>
- <span data-ttu-id="2dc87-141">Disattivare Consenti la lavagna.</span><span class="sxs-lookup"><span data-stu-id="2dc87-141">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="2dc87-142">Disattivare Consenti note condivise.</span><span class="sxs-lookup"><span data-stu-id="2dc87-142">Turn off Allow shared notes.</span></span>

<span data-ttu-id="2dc87-143">Assegnare poi il criterio agli utenti.</span><span class="sxs-lookup"><span data-stu-id="2dc87-143">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="2dc87-144">Modificare un criterio di riunione</span><span class="sxs-lookup"><span data-stu-id="2dc87-144">Edit a meeting policy</span></span>

<span data-ttu-id="2dc87-145">È possibile modificare il criterio globale e i criteri personalizzati creati.</span><span class="sxs-lookup"><span data-stu-id="2dc87-145">You can edit the global policy and any custom policies that you create.</span></span>

1. <span data-ttu-id="2dc87-146">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Riunioni** > **Criteri riunione**.</span><span class="sxs-lookup"><span data-stu-id="2dc87-146">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="2dc87-147">Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="2dc87-147">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="2dc87-148">Da lì, apportare le modifiche desiderate.</span><span class="sxs-lookup"><span data-stu-id="2dc87-148">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="2dc87-149">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2dc87-149">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="2dc87-150">A ogni utente può essere assegnato un solo criterio di riunione per volta.</span><span class="sxs-lookup"><span data-stu-id="2dc87-150">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="2dc87-151">Assegnare un criterio riunione agli utenti</span><span class="sxs-lookup"><span data-stu-id="2dc87-151">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="2dc87-152">Non è possibile eliminare un criterio a cui sono utenti.</span><span class="sxs-lookup"><span data-stu-id="2dc87-152">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="2dc87-153">È prima di tutto necessario assegnare un criterio diverso a tutti gli utenti interessati, quindi sarà possibile eliminare il criterio originale.</span><span class="sxs-lookup"><span data-stu-id="2dc87-153">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="2dc87-154">Impostazioni dei criteri di riunione</span><span class="sxs-lookup"><span data-stu-id="2dc87-154">Meeting policy settings</span></span>

<span data-ttu-id="2dc87-155">Quando si seleziona un criterio esistente nella pagina **Criteri riunione** o si seleziona **Aggiungi** per aggiungere un nuovo criterio, è possibile configurare le impostazioni per gli elementi seguenti.</span><span class="sxs-lookup"><span data-stu-id="2dc87-155">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="2dc87-156">Generale</span><span class="sxs-lookup"><span data-stu-id="2dc87-156">General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="2dc87-157">Audio e video</span><span class="sxs-lookup"><span data-stu-id="2dc87-157">Audio & video</span></span>](meeting-policies-audio-and-video.md)
- [<span data-ttu-id="2dc87-158">Condivisione di contenuti</span><span class="sxs-lookup"><span data-stu-id="2dc87-158">Content sharing</span></span>](meeting-policies-content-sharing.md)
- [<span data-ttu-id="2dc87-159">Partecipanti e ospiti</span><span class="sxs-lookup"><span data-stu-id="2dc87-159">Participants & guests</span></span>](meeting-policies-participants-and-guests.md)


## <a name="related-topics"></a><span data-ttu-id="2dc87-160">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2dc87-160">Related topics</span></span>

- [<span data-ttu-id="2dc87-161">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="2dc87-161">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="2dc87-162">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="2dc87-162">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="2dc87-163">Rimuovere dagli utenti il criterio RestrictedAnonymousAccess per le riunioni di Teams</span><span class="sxs-lookup"><span data-stu-id="2dc87-163">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)