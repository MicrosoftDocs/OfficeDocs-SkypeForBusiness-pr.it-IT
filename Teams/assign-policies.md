---
title: Assegnare i criteri agli utenti in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni sui diversi modi per assegnare criteri agli utenti in Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 3a788ff2712c065d0273d4dfb6233f03e2272337
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196295"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="39a78-103">Assegnare i criteri agli utenti in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="39a78-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="39a78-104">Gli amministratori possono utilizzare i criteri per controllare le funzionalità di Teams disponibili per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="39a78-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="39a78-105">Ad esempio, ci sono criteri per le chiamate, criteri per le riunioni e criteri di messaggistica, solo per cita ne alcuni.</span><span class="sxs-lookup"><span data-stu-id="39a78-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="39a78-106">Le organizzazioni hanno diversi tipi di utenti con esigenze specifiche.</span><span class="sxs-lookup"><span data-stu-id="39a78-106">Organizations have different types of users with unique needs.</span></span> <span data-ttu-id="39a78-107">I criteri personalizzati creati e assegnati consentono di personalizzare le impostazioni dei criteri per diversi set di utenti in base a queste esigenze.</span><span class="sxs-lookup"><span data-stu-id="39a78-107">Custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="39a78-108">Per gestire facilmente i criteri nell'organizzazione, Teams offre diversi modi per assegnare i criteri agli utenti.</span><span class="sxs-lookup"><span data-stu-id="39a78-108">To easily manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="39a78-109">Assegnare criteri direttamente agli utenti, singolarmente o su scala nel processo di assegnazione di un batch, oppure a un gruppo di cui gli utenti sono membri.</span><span class="sxs-lookup"><span data-stu-id="39a78-109">Assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="39a78-110">È anche possibile usare pacchetti di criteri per assegnare una raccolta predefinita di criteri agli utenti dell'organizzazione con ruoli simili.</span><span class="sxs-lookup"><span data-stu-id="39a78-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="39a78-111">L'opzione scelta dipende dal numero di criteri da gestire e dal numero di utenti a cui si stanno assegnando criteri.</span><span class="sxs-lookup"><span data-stu-id="39a78-111">The option that you choose depends on the number of policies that you're managing and the number of users you're assigning policies to.</span></span> <span data-ttu-id="39a78-112">I criteri globali (impostazione predefinita a livello di organizzazione) si applicano al maggior numero di utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="39a78-112">Global (Org-wide default) policies apply to the largest number of users in your organization.</span></span> <span data-ttu-id="39a78-113">È necessario assegnare criteri solo agli utenti che richiedono criteri specifici.</span><span class="sxs-lookup"><span data-stu-id="39a78-113">You only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="39a78-114">Questo articolo descrive i diversi modi in cui è possibile assegnare criteri agli utenti e gli scenari consigliati per l'uso.</span><span class="sxs-lookup"><span data-stu-id="39a78-114">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="39a78-115">Quali criteri hanno la precedenza?</span><span class="sxs-lookup"><span data-stu-id="39a78-115">Which policy takes precedence?</span></span>

<span data-ttu-id="39a78-116">Un utente ha un criterio effettivo per ogni tipo di criterio.</span><span class="sxs-lookup"><span data-stu-id="39a78-116">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="39a78-117">È possibile, o addirittura probabile, che un utente sia assegnato direttamente a un criterio ed è anche membro di uno o più gruppi a cui è assegnato un criterio dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="39a78-117">It's possible, or even likely, that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="39a78-118">In questi tipi di scenari, quali criteri hanno la precedenza?</span><span class="sxs-lookup"><span data-stu-id="39a78-118">In these kinds of scenarios, which policy takes precedence?</span></span> <span data-ttu-id="39a78-119">I criteri effettivi di un utente vengono determinati in base alle regole di precedenza, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="39a78-119">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="39a78-120">Se a un utente viene direttamente assegnato un criterio (singolarmente o tramite un'assegnazione batch), tale criterio ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="39a78-120">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="39a78-121">Nell'esempio visivo seguente, il criterio effettivo dell'utente è il criterio di riunione Square Square, assegnato direttamente all'utente.</span><span class="sxs-lookup"><span data-stu-id="39a78-121">In the following visual example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagramma che illustra in che modo un criterio assegnato direttamente ha la precedenza](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="39a78-123">Se a un utente non viene direttamente assegnato un criterio di un determinato tipo, il criterio assegnato a un gruppo di cui l'utente è membro ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="39a78-123">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="39a78-124">Se un utente è membro di più gruppi, [](#group-assignment-ranking) il criterio con la classificazione di assegnazione di gruppi più alta per il tipo di criterio specificato ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="39a78-124">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="39a78-125">In questo esempio visivo, il criterio effettivo dell'utente è il criterio Exec Teams e HD, che ha la classificazione di assegnazione più alta rispetto agli altri gruppi di cui l'utente è membro e a cui è anche assegnato un criterio dello stesso tipo di criterio.</span><span class="sxs-lookup"><span data-stu-id="39a78-125">In this visual example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagramma che illustra in che modo un criterio ereditato dal gruppo ha la precedenza](media/assign-policies-example-group.png)

<span data-ttu-id="39a78-127">Se a un utente non viene assegnato direttamente un criterio o non è membro di alcun gruppo a cui è assegnato un criterio, l'utente ottiene il criterio globale (impostazione predefinita a livello di organizzazione) per quel tipo di criterio.</span><span class="sxs-lookup"><span data-stu-id="39a78-127">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="39a78-128">Ecco un esempio visivo.</span><span class="sxs-lookup"><span data-stu-id="39a78-128">Here's a visual example.</span></span>

![Diagramma che illustra in che modo i criteri globali hanno la precedenza](media/assign-policies-example-global.png)

<span data-ttu-id="39a78-130">Per altre informazioni, vedere [Regole di precedenza.](#precedence-rules)</span><span class="sxs-lookup"><span data-stu-id="39a78-130">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="39a78-131">Modalità di assegnazione dei criteri</span><span class="sxs-lookup"><span data-stu-id="39a78-131">Ways to assign policies</span></span>

<span data-ttu-id="39a78-132">Ecco una panoramica dei modi in cui è possibile assegnare criteri agli utenti e degli scenari consigliati per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="39a78-132">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="39a78-133">Selezionare i collegamenti per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="39a78-133">Select the links to learn more.</span></span>

<span data-ttu-id="39a78-134">Prima di assegnare criteri a singoli utenti o gruppi, iniziare impostando i criteri globali (impostazione predefinita a livello di [organizzazione)](#set-the-global-policies) in modo che siano applicati al maggior numero di utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="39a78-134">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="39a78-135">Dopo aver impostato i criteri globali, è necessario assegnarli solo agli utenti che richiedono criteri specifici.</span><span class="sxs-lookup"><span data-stu-id="39a78-135">Once the global policies are set, you'll only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="39a78-136">Operazione da eseguire</span><span class="sxs-lookup"><span data-stu-id="39a78-136">Do this</span></span>  |<span data-ttu-id="39a78-137">Se...</span><span class="sxs-lookup"><span data-stu-id="39a78-137">If...</span></span>  | <span data-ttu-id="39a78-138">Uso di...</span><span class="sxs-lookup"><span data-stu-id="39a78-138">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="39a78-139">Assegnare criteri a singoli utenti</span><span class="sxs-lookup"><span data-stu-id="39a78-139">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="39a78-140">L'utente non ha ancora iniziato a usare Teams o ha bisogno di assegnare solo uno o un paio di criteri a un numero limitato di utenti.</span><span class="sxs-lookup"><span data-stu-id="39a78-140">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="39a78-141">Interfaccia di amministrazione di Microsoft Teams o cmdlet di PowerShell nel modulo PowerShell di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="39a78-141">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
|[<span data-ttu-id="39a78-142">Assegnare un criterio a un gruppo</span><span class="sxs-lookup"><span data-stu-id="39a78-142">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="39a78-143">Assegnare criteri in base all'appartenenza ai gruppi di un utente.</span><span class="sxs-lookup"><span data-stu-id="39a78-143">Assign policies based on a user's group membership.</span></span> <span data-ttu-id="39a78-144">Ad esempio, assegnare un criterio a tutti gli utenti di un gruppo di sicurezza o una lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="39a78-144">For example, assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="39a78-145">Interfaccia di amministrazione di Microsoft Teams o cmdlet di PowerShell nel modulo PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="39a78-145">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="39a78-146">Assegnare criteri a un batch di utenti</span><span class="sxs-lookup"><span data-stu-id="39a78-146">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="39a78-147">Assegnare criteri a grandi set di utenti.</span><span class="sxs-lookup"><span data-stu-id="39a78-147">Assign policies to large sets of users.</span></span> <span data-ttu-id="39a78-148">Ad esempio, assegnare un criterio a centinaia o migliaia di utenti dell'organizzazione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="39a78-148">For example, assign a policy to hundreds or thousands of users in your organization at a time.</span></span> |<span data-ttu-id="39a78-149">Interfaccia di amministrazione di Microsoft Teams o cmdlet di PowerShell nel modulo PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="39a78-149">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="39a78-150">Assegnare un pacchetto di criteri agli utenti</span><span class="sxs-lookup"><span data-stu-id="39a78-150">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  |<span data-ttu-id="39a78-151">Assegnare più criteri a set specifici di utenti dell'organizzazione con ruoli uguali o simili.</span><span class="sxs-lookup"><span data-stu-id="39a78-151">Assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="39a78-152">Ad esempio, assegnare il pacchetto di criteri Education (docente) agli insegnanti dell'istituto di istruzione per concedere loro l'accesso completo a chat, chiamate e riunioni.</span><span class="sxs-lookup"><span data-stu-id="39a78-152">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="39a78-153">Assegnare il pacchetto di criteri Istruzione (studenti secondari) agli studenti secondari per limitare determinate funzionalità, ad esempio le chiamate private.</span><span class="sxs-lookup"><span data-stu-id="39a78-153">Assign the Education (Secondary school student) policy package to secondary students to limit certain capabilities such as private calling.</span></span>  |<span data-ttu-id="39a78-154">Interfaccia di amministrazione di Microsoft Teams o cmdlet di PowerShell nel modulo PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="39a78-154">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="39a78-155">[Assegnare un pacchetto di criteri a un gruppo](#assign-a-policy-package-to-a-group) (in anteprima privata)</span><span class="sxs-lookup"><span data-stu-id="39a78-155">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="39a78-156">Assegnare più criteri a un gruppo di utenti dell'organizzazione con ruoli uguali o simili.</span><span class="sxs-lookup"><span data-stu-id="39a78-156">Assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="39a78-157">Ad esempio, assegnare un pacchetto di criteri a tutti gli utenti in un gruppo di sicurezza o una lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="39a78-157">For example, assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="39a78-158">Interfaccia di amministrazione di Microsoft Teams (presto disponibile) o cmdlet di PowerShell nel modulo PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="39a78-158">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="39a78-159">Assegnare un pacchetto di criteri a un batch di utenti</span><span class="sxs-lookup"><span data-stu-id="39a78-159">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="39a78-160">Assegnare più criteri a un batch di utenti dell'organizzazione con ruoli uguali o simili.</span><span class="sxs-lookup"><span data-stu-id="39a78-160">Assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="39a78-161">Ad esempio, assegnare il pacchetto di criteri Education (docente) a tutti gli insegnanti dell'istituto di istruzione usando l'assegnazione batch per concedere loro l'accesso completo a chat, chiamate e riunioni.</span><span class="sxs-lookup"><span data-stu-id="39a78-161">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="39a78-162">Assegnare il pacchetto di criteri Education (studenti secondari) a un batch di studenti secondari per limitare determinate funzionalità, ad esempio le chiamate private.</span><span class="sxs-lookup"><span data-stu-id="39a78-162">Assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities such as private calling.</span></span>|<span data-ttu-id="39a78-163">Cmdlet di PowerShell nel modulo Teams di PowerShell</span><span class="sxs-lookup"><span data-stu-id="39a78-163">PowerShell cmdlets in the Teams PowerShell module</span></span>|

## <a name="set-the-global-policies"></a><span data-ttu-id="39a78-164">Impostare i criteri globali</span><span class="sxs-lookup"><span data-stu-id="39a78-164">Set the global policies</span></span>

<span data-ttu-id="39a78-165">Seguire questa procedura per impostare i criteri globali (impostazione predefinita a livello di organizzazione) per ogni tipo di criterio.</span><span class="sxs-lookup"><span data-stu-id="39a78-165">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="39a78-166">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="39a78-166">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="39a78-167">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare alla pagina dei criteri per il tipo di criterio da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="39a78-167">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="39a78-168">Ad esempio, i **criteri di Teams**  >  **Teams,** i criteri **per** le  >  **riunioni,** i criteri di **messaggistica** o **le chiamate**  >  **vocali.**</span><span class="sxs-lookup"><span data-stu-id="39a78-168">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="39a78-169">Selezionare il **criterio globale (impostazione predefinita a** livello di organizzazione) per visualizzare le impostazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="39a78-169">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="39a78-170">Aggiornare il criterio in base alle esigenze e quindi selezionare **Applica.**</span><span class="sxs-lookup"><span data-stu-id="39a78-170">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="39a78-171">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="39a78-171">Using PowerShell</span></span>

<span data-ttu-id="39a78-172">Per impostare i criteri globali con PowerShell, usare l'identificatore globale.</span><span class="sxs-lookup"><span data-stu-id="39a78-172">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="39a78-173">Per iniziare, esaminare il criterio globale corrente per determinare l'impostazione da modificare.</span><span class="sxs-lookup"><span data-stu-id="39a78-173">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

<span data-ttu-id="39a78-174">Aggiornare quindi i criteri globali in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="39a78-174">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="39a78-175">È necessario specificare solo i valori per le impostazioni da modificare.</span><span class="sxs-lookup"><span data-stu-id="39a78-175">You only need to specify values for the settings that you want to change.</span></span>

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="39a78-176">Assegnare criteri a singoli utenti</span><span class="sxs-lookup"><span data-stu-id="39a78-176">Assign a policy to individual users</span></span>

<span data-ttu-id="39a78-177">Seguire questa procedura per assegnare criteri a un singolo utente o a un numero limitato di utenti alla volta.</span><span class="sxs-lookup"><span data-stu-id="39a78-177">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="39a78-178">Usare l'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="39a78-178">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="39a78-179">Per assegnare un criterio a un utente:</span><span class="sxs-lookup"><span data-stu-id="39a78-179">To assign a policy to a user:</span></span>

1. <span data-ttu-id="39a78-180">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa **a** Utenti e quindi seleziona l'utente.</span><span class="sxs-lookup"><span data-stu-id="39a78-180">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="39a78-181">Selezionare l'utente facendo clic a sinistra del nome utente e quindi **selezionando Modifica impostazioni.**</span><span class="sxs-lookup"><span data-stu-id="39a78-181">Select the user by clicking to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="39a78-182">Selezionare il criterio da assegnare e quindi scegliere **Applica.**</span><span class="sxs-lookup"><span data-stu-id="39a78-182">Select the policy you want to assign, and then select **Apply**.</span></span>

<span data-ttu-id="39a78-183">Si può anche procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="39a78-183">Or, you can also do the following:</span></span>

1. <span data-ttu-id="39a78-184">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, vai alla pagina dei criteri.</span><span class="sxs-lookup"><span data-stu-id="39a78-184">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="39a78-185">Selezionare il criterio da assegnare facendo clic a sinistra del nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="39a78-185">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="39a78-186">Scegliere **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="39a78-186">Select **Manage users**.</span></span>
4. <span data-ttu-id="39a78-187">Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="39a78-187">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="39a78-188">Ripetere questa operazione per ogni utente da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="39a78-188">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="39a78-189">Dopo aver aggiunto gli utenti, selezionare **Applica.**</span><span class="sxs-lookup"><span data-stu-id="39a78-189">When you're finished adding users, select **Apply**.</span></span>

### <a name="use-powershell"></a><span data-ttu-id="39a78-190">Usare PowerShell</span><span class="sxs-lookup"><span data-stu-id="39a78-190">Use PowerShell</span></span>

<span data-ttu-id="39a78-191">Ogni tipo di criterio ha un proprio set di cmdlet per gestirlo.</span><span class="sxs-lookup"><span data-stu-id="39a78-191">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="39a78-192">Usare il ```Grant-``` cmdlet per un determinato tipo di criterio per assegnare il criterio.</span><span class="sxs-lookup"><span data-stu-id="39a78-192">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="39a78-193">Ad esempio, usare il ```Grant-CsTeamsMeetingPolicy``` cmdlet per assegnare criteri di riunione di Teams agli utenti.</span><span class="sxs-lookup"><span data-stu-id="39a78-193">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="39a78-194">Questi cmdlet sono inclusi nel modulo PowerShell di Skype for Business Online e sono documentati nel riferimento [ai cmdlet di Skype for Business.](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="39a78-194">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="39a78-195">Scarica e installa il modulo [PowerShell](https://www.microsoft.com/download/details.aspx?id=39366) di Skype for Business online (se non l'hai già fatto), quindi esegui questa procedura per connetterti a Skype for Business online e avviare una sessione.</span><span class="sxs-lookup"><span data-stu-id="39a78-195">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

> [!NOTE]
> <span data-ttu-id="39a78-196">Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="39a78-196">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="39a78-197">Se si usa la versione pubblica più recente di [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="39a78-197">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="39a78-198">In questo esempio viene assegnato un criterio di riunione di Teams denominato Criteri riunione studente a un utente denominato Reda.</span><span class="sxs-lookup"><span data-stu-id="39a78-198">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="39a78-199">Per altre informazioni, vedere [Gestire i criteri con PowerShell.](teams-powershell-managing-teams.md#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="39a78-199">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="39a78-200">Assegnare un criterio a un gruppo</span><span class="sxs-lookup"><span data-stu-id="39a78-200">Assign a policy to a group</span></span>

<span data-ttu-id="39a78-201">L'assegnazione dei criteri ai gruppi consente di assegnare un criterio a un gruppo di utenti, ad esempio un gruppo di sicurezza o una lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="39a78-201">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="39a78-202">L'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza.</span><span class="sxs-lookup"><span data-stu-id="39a78-202">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="39a78-203">Quando vengono aggiunti o rimossi membri da un gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="39a78-203">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="39a78-204">L'assegnazione dei criteri ai gruppi è consigliata per gruppi di un massimo di 50.000 utenti, ma funziona anche con gruppi più grandi.</span><span class="sxs-lookup"><span data-stu-id="39a78-204">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="39a78-205">Quando si assegnano i criteri, vengono immediatamente assegnati al gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-205">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="39a78-206">Tuttavia, la propagazione dell'assegnazione dei criteri ai membri del gruppo viene eseguita come operazione in background e potrebbe richiedere del tempo, a seconda delle dimensioni del gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-206">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="39a78-207">Lo stesso vale quando un criterio non è assegnato a un gruppo o quando i membri vengono aggiunti o rimossi da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-207">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="39a78-208">Le assegnazioni di Criteri di gruppo vengono propagate solo agli utenti che sono membri diretti del gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-208">Group policy assignments are only propagated to users who are direct members of the group.</span></span> <span data-ttu-id="39a78-209">Le assegnazioni non vengono propagate ai membri di gruppi annidati.</span><span class="sxs-lookup"><span data-stu-id="39a78-209">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="39a78-210">Informazioni necessarie sull'assegnazione dei criteri ai gruppi</span><span class="sxs-lookup"><span data-stu-id="39a78-210">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="39a78-211">Prima di iniziare, è importante comprendere le regole di precedenza e la classificazione delle assegnazioni dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="39a78-211">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="39a78-212">Regole di precedenza</span><span class="sxs-lookup"><span data-stu-id="39a78-212">Precedence rules</span></span>

<span data-ttu-id="39a78-213">Per un determinato tipo di criterio, il criterio effettivo di un utente viene determinato in base a quanto segue:</span><span class="sxs-lookup"><span data-stu-id="39a78-213">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="39a78-214">I criteri assegnati direttamente a un utente hanno la precedenza su qualsiasi altro criterio dello stesso tipo assegnato a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-214">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="39a78-215">In altre parole, se a un utente viene direttamente assegnato un criterio di un determinato tipo, l'utente non erediterà un criterio dello stesso tipo da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-215">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="39a78-216">Questo significa anche che se un utente ha un criterio di un determinato tipo a cui è stato assegnato direttamente, è necessario rimuoverlo dall'utente prima di ereditare un criterio dello stesso tipo da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-216">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="39a78-217">Se a un utente non sono assegnati direttamente criteri ed è membro di due o più gruppi a cui è assegnato un criterio dello stesso tipo, l'utente eredita il criterio dell'assegnazione di gruppo che ha la classificazione più alta.</span><span class="sxs-lookup"><span data-stu-id="39a78-217">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="39a78-218">Se un utente non è membro di alcun gruppo a cui è assegnato un criterio, il criterio globale (impostazione predefinita a livello di organizzazione) per quel tipo di criterio viene applicato all'utente.</span><span class="sxs-lookup"><span data-stu-id="39a78-218">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="39a78-219">I criteri effettivi di un utente vengono aggiornati in base alle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="39a78-219">A user's effective policy is updated according to these rules:</span></span>

- <span data-ttu-id="39a78-220">quando un utente viene aggiunto o rimosso da un gruppo a cui è assegnato un criterio.</span><span class="sxs-lookup"><span data-stu-id="39a78-220">when a user is added to or removed from a group that's assigned a policy.</span></span>
- <span data-ttu-id="39a78-221">Un criterio non è assegnato a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-221">a policy is unassigned from a group.</span></span>
- <span data-ttu-id="39a78-222">I criteri assegnati direttamente all'utente vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="39a78-222">a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="39a78-223">Classificazione delle assegnazioni dei gruppi</span><span class="sxs-lookup"><span data-stu-id="39a78-223">Group assignment ranking</span></span>

<span data-ttu-id="39a78-224">Quando si assegna un criterio a un gruppo, si specifica una classificazione per l'assegnazione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-224">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="39a78-225">Viene usato per determinare i criteri che un utente deve ereditare come criterio effettivo se l'utente è membro di due o più gruppi a cui è assegnato un criterio dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="39a78-225">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="39a78-226">La classificazione delle assegnazioni di gruppo è relativa ad altre assegnazioni di gruppo dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="39a78-226">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="39a78-227">Ad esempio, se si assegna un criterio di chiamata a due gruppi, impostare la classificazione di un'assegnazione su 1 e l'altra su 2, con 1 come classificazione più alta.</span><span class="sxs-lookup"><span data-stu-id="39a78-227">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="39a78-228">La classificazione delle assegnazioni di gruppo indica quale appartenenza ai gruppi è più importante o più pertinente di altre appartenenze a gruppi per quanto riguarda l'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="39a78-228">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>

<span data-ttu-id="39a78-229">Si supponga, ad esempio, di avere due gruppi, Dipendenti negozio e Responsabili negozio.</span><span class="sxs-lookup"><span data-stu-id="39a78-229">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="39a78-230">A entrambi i gruppi sono assegnati, rispettivamente, un criterio di chiamata di Teams, un criterio di chiamata dei dipendenti negozio e un criterio di chiamata per i responsabili negozio.</span><span class="sxs-lookup"><span data-stu-id="39a78-230">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="39a78-231">Per un responsabile negozio che fa parte di entrambi i gruppi, il suo ruolo di responsabile è più pertinente del suo ruolo di dipendente, quindi il criterio di chiamata assegnato al gruppo Di responsabili negozio dovrebbe avere una classificazione più alta.</span><span class="sxs-lookup"><span data-stu-id="39a78-231">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="39a78-232">Raggruppa</span><span class="sxs-lookup"><span data-stu-id="39a78-232">Group</span></span> |<span data-ttu-id="39a78-233">Nome del criterio di chiamata di Teams</span><span class="sxs-lookup"><span data-stu-id="39a78-233">Teams calling policy name</span></span>  |<span data-ttu-id="39a78-234">Rango</span><span class="sxs-lookup"><span data-stu-id="39a78-234">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="39a78-235">Responsabili negozio</span><span class="sxs-lookup"><span data-stu-id="39a78-235">Store Managers</span></span>   |<span data-ttu-id="39a78-236">Criteri per le chiamate dei responsabili negozio</span><span class="sxs-lookup"><span data-stu-id="39a78-236">Store Managers Calling Policy</span></span>         |<span data-ttu-id="39a78-237">1</span><span class="sxs-lookup"><span data-stu-id="39a78-237">1</span></span>|
|<span data-ttu-id="39a78-238">Dipendenti negozio</span><span class="sxs-lookup"><span data-stu-id="39a78-238">Store Employees</span></span>    |<span data-ttu-id="39a78-239">Criteri per le chiamate dei dipendenti negozio</span><span class="sxs-lookup"><span data-stu-id="39a78-239">Store Employees Calling Policy</span></span>      |<span data-ttu-id="39a78-240">2</span><span class="sxs-lookup"><span data-stu-id="39a78-240">2</span></span>|

<span data-ttu-id="39a78-241">Se non si specifica una classificazione, all'assegnazione dei criteri viene data la classificazione più bassa.</span><span class="sxs-lookup"><span data-stu-id="39a78-241">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="in-the-teams-admin-center"></a><span data-ttu-id="39a78-242">Nell'interfaccia di amministrazione di Teams</span><span class="sxs-lookup"><span data-stu-id="39a78-242">In the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="39a78-243">Attualmente, l'assegnazione dei criteri ai gruppi tramite l'interfaccia di amministrazione di Microsoft Teams è disponibile solo per i criteri di chiamata di Teams, i criteri del parco chiamate di Teams, i criteri di Teams, i criteri per gli eventi live di Teams, i criteri delle riunioni di Teams e i criteri di messaggistica di Teams.</span><span class="sxs-lookup"><span data-stu-id="39a78-243">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="39a78-244">Per altri tipi di criteri, usare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39a78-244">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="39a78-245">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, vai alla pagina del tipo di criterio.</span><span class="sxs-lookup"><span data-stu-id="39a78-245">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="39a78-246">Ad esempio, passare a **Criteri**  >  **riunione riunioni.**</span><span class="sxs-lookup"><span data-stu-id="39a78-246">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="39a78-247">Selezionare la scheda **di assegnazione di Criteri di** gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-247">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="39a78-248">Selezionare **Aggiungi gruppo** e quindi nel riquadro Assegna **criteri** a gruppo eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="39a78-248">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="39a78-249">Cercare e aggiungere il gruppo a cui assegnare il criterio.</span><span class="sxs-lookup"><span data-stu-id="39a78-249">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="39a78-250">Impostare la classificazione per l'assegnazione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-250">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="39a78-251">Selezionare il criterio da assegnare.</span><span class="sxs-lookup"><span data-stu-id="39a78-251">Select the policy that you want to assign.</span></span>
    4. <span data-ttu-id="39a78-252">Selezionare **Applica.**</span><span class="sxs-lookup"><span data-stu-id="39a78-252">Select **Apply**.</span></span>

<span data-ttu-id="39a78-253">Per rimuovere un'assegnazione di  Criteri di gruppo, nella scheda Assegnazione di Criteri di gruppo della pagina dei criteri selezionare l'assegnazione del gruppo e quindi **scegliere Rimuovi.**</span><span class="sxs-lookup"><span data-stu-id="39a78-253">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="39a78-254">Per modificare la classificazione di un'assegnazione di gruppo, è necessario prima rimuovere l'assegnazione di Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-254">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="39a78-255">Quindi, seguire la procedura precedente per assegnare i criteri a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-255">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="use-the-powershell-option"></a><span data-ttu-id="39a78-256">Usare l'opzione PowerShell</span><span class="sxs-lookup"><span data-stu-id="39a78-256">Use the PowerShell option</span></span>

> [!NOTE]
> <span data-ttu-id="39a78-257">Attualmente, l'assegnazione dei criteri ai gruppi con PowerShell non è disponibile per tutti i tipi di criteri di Teams.</span><span class="sxs-lookup"><span data-stu-id="39a78-257">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="39a78-258">Per [l'elenco dei tipi di criteri supportati, vedere New-CsGroupPolicyAssignment.](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="39a78-258">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="39a78-259">Installare e connettersi al modulo Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="39a78-259">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="39a78-260">Per istruzioni dettagliate, vedere Installare [PowerShell di Teams.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="39a78-260">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="39a78-261">Assegnare un criterio a un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="39a78-261">Assign a policy to a group of users</span></span>

<span data-ttu-id="39a78-262">Usare il cmdlet [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) per assegnare un criterio a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-262">Use the [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="39a78-263">È possibile specificare un gruppo usando l'ID oggetto, l'indirizzo SIP o l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="39a78-263">You can specify a group by using the object ID, SIP address, or email address.</span></span>

<span data-ttu-id="39a78-264">In questo esempio viene assegnato un criterio di riunione di Teams denominato Criterio riunione di responsabili dettaglio a un gruppo con una classificazione di assegnazione 1.</span><span class="sxs-lookup"><span data-stu-id="39a78-264">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="39a78-265">Ottenere assegnazioni dei criteri per un gruppo</span><span class="sxs-lookup"><span data-stu-id="39a78-265">Get policy assignments for a group</span></span>

<span data-ttu-id="39a78-266">Usare il [cmdlet Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) per ottenere tutti i criteri assegnati a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-266">Use the [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="39a78-267">Tenere presente che i gruppi sono sempre elencati in base all'ID gruppo anche se per assegnare i criteri è stato usato l'indirizzo SIP o l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="39a78-267">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="39a78-268">In questo esempio vengono recuperati tutti i criteri assegnati a un gruppo specifico.</span><span class="sxs-lookup"><span data-stu-id="39a78-268">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="39a78-269">In questo esempio vengono restituiti tutti i gruppi a cui è assegnato un criterio di riunione di Teams.</span><span class="sxs-lookup"><span data-stu-id="39a78-269">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="39a78-270">Rimuovere un criterio da un gruppo</span><span class="sxs-lookup"><span data-stu-id="39a78-270">Remove a policy from a group</span></span>

<span data-ttu-id="39a78-271">Usare il cmdlet [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) per rimuovere un criterio da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-271">Use the [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="39a78-272">Quando si rimuovono criteri da un gruppo, le priorità di altri criteri dello stesso tipo assegnate a quel gruppo e con una classificazione inferiore vengono aggiornate.</span><span class="sxs-lookup"><span data-stu-id="39a78-272">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group, and that have a lower ranking, are updated.</span></span> <span data-ttu-id="39a78-273">Ad esempio, se si rimuove un criterio con una classificazione 2, i criteri con una classificazione 3 e 4 vengono aggiornati in modo da riflettere la nuova classificazione.</span><span class="sxs-lookup"><span data-stu-id="39a78-273">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="39a78-274">Questo esempio è illustrato nelle due tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="39a78-274">The following two tables show this example.</span></span>

<span data-ttu-id="39a78-275">Ecco un elenco delle assegnazioni dei criteri e delle priorità per i criteri delle riunioni di Teams.</span><span class="sxs-lookup"><span data-stu-id="39a78-275">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="39a78-276">Nome gruppo</span><span class="sxs-lookup"><span data-stu-id="39a78-276">Group name</span></span>  |<span data-ttu-id="39a78-277">Nome del criterio</span><span class="sxs-lookup"><span data-stu-id="39a78-277">Policy name</span></span>  |<span data-ttu-id="39a78-278">Rango</span><span class="sxs-lookup"><span data-stu-id="39a78-278">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="39a78-279">Vendite</span><span class="sxs-lookup"><span data-stu-id="39a78-279">Sales</span></span>    |<span data-ttu-id="39a78-280">Criteri di vendita</span><span class="sxs-lookup"><span data-stu-id="39a78-280">Sales policy</span></span>       | <span data-ttu-id="39a78-281">1</span><span class="sxs-lookup"><span data-stu-id="39a78-281">1</span></span>        |
|<span data-ttu-id="39a78-282">Area ovest</span><span class="sxs-lookup"><span data-stu-id="39a78-282">West Region</span></span>     |<span data-ttu-id="39a78-283">Criteri dell'area Ovest</span><span class="sxs-lookup"><span data-stu-id="39a78-283">West Region policy</span></span>         |<span data-ttu-id="39a78-284">2</span><span class="sxs-lookup"><span data-stu-id="39a78-284">2</span></span>         |
|<span data-ttu-id="39a78-285">Divisione</span><span class="sxs-lookup"><span data-stu-id="39a78-285">Division</span></span>    |<span data-ttu-id="39a78-286">Criteri di divisione</span><span class="sxs-lookup"><span data-stu-id="39a78-286">Division policy</span></span>         |<span data-ttu-id="39a78-287">3</span><span class="sxs-lookup"><span data-stu-id="39a78-287">3</span></span>         |
|<span data-ttu-id="39a78-288">Affiliata</span><span class="sxs-lookup"><span data-stu-id="39a78-288">Subsidiary</span></span>   |<span data-ttu-id="39a78-289">Criteri affiliati</span><span class="sxs-lookup"><span data-stu-id="39a78-289">Subsidiary policy</span></span>        |<span data-ttu-id="39a78-290">4</span><span class="sxs-lookup"><span data-stu-id="39a78-290">4</span></span>         |

<span data-ttu-id="39a78-291">Se si rimuove il criterio Area Ovest dal gruppo Area Ovest, le assegnazioni e le priorità dei criteri vengono aggiornate nel modo seguente.</span><span class="sxs-lookup"><span data-stu-id="39a78-291">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="39a78-292">Nome gruppo</span><span class="sxs-lookup"><span data-stu-id="39a78-292">Group name</span></span>  |<span data-ttu-id="39a78-293">Nome del criterio</span><span class="sxs-lookup"><span data-stu-id="39a78-293">Policy name</span></span>  |<span data-ttu-id="39a78-294">Rango</span><span class="sxs-lookup"><span data-stu-id="39a78-294">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="39a78-295">Vendite</span><span class="sxs-lookup"><span data-stu-id="39a78-295">Sales</span></span>    |<span data-ttu-id="39a78-296">Criteri di vendita</span><span class="sxs-lookup"><span data-stu-id="39a78-296">Sales policy</span></span>       | <span data-ttu-id="39a78-297">1</span><span class="sxs-lookup"><span data-stu-id="39a78-297">1</span></span>        |
|<span data-ttu-id="39a78-298">Divisione</span><span class="sxs-lookup"><span data-stu-id="39a78-298">Division</span></span>    |<span data-ttu-id="39a78-299">Criteri di divisione</span><span class="sxs-lookup"><span data-stu-id="39a78-299">Division policy</span></span>         |<span data-ttu-id="39a78-300">2</span><span class="sxs-lookup"><span data-stu-id="39a78-300">2</span></span>         |
|<span data-ttu-id="39a78-301">Affiliata</span><span class="sxs-lookup"><span data-stu-id="39a78-301">Subsidiary</span></span>   |<span data-ttu-id="39a78-302">Criteri affiliati</span><span class="sxs-lookup"><span data-stu-id="39a78-302">Subsidiary policy</span></span>        |<span data-ttu-id="39a78-303">3</span><span class="sxs-lookup"><span data-stu-id="39a78-303">3</span></span>        |

<span data-ttu-id="39a78-304">In questo esempio il criterio di riunione di Teams viene rimosso da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-304">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="39a78-305">Modificare un'assegnazione di criteri per un gruppo</span><span class="sxs-lookup"><span data-stu-id="39a78-305">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="39a78-306">Il cmdlet [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) sarà disponibile a breve.</span><span class="sxs-lookup"><span data-stu-id="39a78-306">The [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="39a78-307">Nel frattempo, per modificare un'assegnazione di Criteri di gruppo, è possibile rimuovere l'assegnazione di criteri corrente dal gruppo e quindi aggiungere una nuova assegnazione di criteri.</span><span class="sxs-lookup"><span data-stu-id="39a78-307">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="39a78-308">Dopo aver assegnato un criterio a un gruppo, è possibile usare il cmdlet [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) per modificare l'assegnazione dei criteri del gruppo come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="39a78-308">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="39a78-309">Modificare la classificazione</span><span class="sxs-lookup"><span data-stu-id="39a78-309">Change the ranking</span></span>
- <span data-ttu-id="39a78-310">Modificare il criterio di un determinato tipo di criterio</span><span class="sxs-lookup"><span data-stu-id="39a78-310">Change the policy of a given policy type</span></span>
- <span data-ttu-id="39a78-311">Modificare il criterio di un determinato tipo di criterio e la classificazione</span><span class="sxs-lookup"><span data-stu-id="39a78-311">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="39a78-312">In questo esempio i criteri del call park di Teams di un gruppo vengono 3dati con un criterio denominato SupportCallPark e la classificazione delle assegnazioni viene impostata su 3.</span><span class="sxs-lookup"><span data-stu-id="39a78-312">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="39a78-313">Modificare i criteri effettivi per un utente</span><span class="sxs-lookup"><span data-stu-id="39a78-313">Change the effective policy for a user</span></span>

<span data-ttu-id="39a78-314">Ecco un esempio di come modificare il criterio effettivo per un utente a cui viene direttamente assegnato un criterio.</span><span class="sxs-lookup"><span data-stu-id="39a78-314">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="39a78-315">Prima di tutto, usiamo il cmdlet [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) insieme al parametro per ottenere i dettagli dei criteri di trasmissione delle riunioni di Teams associati ```PolicySource``` all'utente.</span><span class="sxs-lookup"><span data-stu-id="39a78-315">First, we use the [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="39a78-316">L'output mostra che all'utente è stato direttamente assegnato un criterio di trasmissione riunione di Teams denominato Eventi dipendente, che ha la precedenza sul criterio denominato Eventi live fornitore assegnato a un gruppo a cui appartiene l'utente.</span><span class="sxs-lookup"><span data-stu-id="39a78-316">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="39a78-317">A questo punto, il criterio Eventi dipendenti viene rimosso dall'utente.</span><span class="sxs-lookup"><span data-stu-id="39a78-317">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="39a78-318">Questo significa che l'utente non ha più un criterio di trasmissione riunione di Teams assegnato direttamente all'utente e erediterà il criterio Eventi live fornitore assegnato al gruppo a cui appartiene l'utente.</span><span class="sxs-lookup"><span data-stu-id="39a78-318">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span>

<span data-ttu-id="39a78-319">Utilizzare il cmdlet seguente nel modulo PowerShell di Skype for Business per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="39a78-319">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="39a78-320">Usare il cmdlet seguente nel modulo PowerShell di Teams per eseguire questa operazione su larga scala, anche se con un'assegnazione di criteri batch, in $users è un elenco di utenti specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="39a78-320">Use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="39a78-321">Assegnare criteri a un batch di utenti</span><span class="sxs-lookup"><span data-stu-id="39a78-321">Assign a policy to a batch of users</span></span>

### <a name="use-the-admin-center"></a><span data-ttu-id="39a78-322">Usare l'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="39a78-322">Use the admin center</span></span>

<span data-ttu-id="39a78-323">Per assegnare un criterio agli utenti in blocco:</span><span class="sxs-lookup"><span data-stu-id="39a78-323">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="39a78-324">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams selezionare **Utenti.**</span><span class="sxs-lookup"><span data-stu-id="39a78-324">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="39a78-325">Cercare gli utenti a cui assegnare il criterio o filtrare la visualizzazione per mostrare gli utenti desiderati.</span><span class="sxs-lookup"><span data-stu-id="39a78-325">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="39a78-326">Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="39a78-326">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="39a78-327">Per selezionare tutti gli utenti, fare clic sul &#x2713; (segno di spunta) nella parte superiore della tabella.</span><span class="sxs-lookup"><span data-stu-id="39a78-327">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="39a78-328">Selezionare **Modifica impostazioni,** apportare le modifiche desiderate e quindi scegliere **Applica.**</span><span class="sxs-lookup"><span data-stu-id="39a78-328">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="39a78-329">Per visualizzare lo stato dell'assegnazione dei criteri, nel  banner visualizzato nella  parte superiore della pagina Utenti dopo aver selezionato Applica per inviare l'assegnazione dei criteri, selezionare **Log attività.**</span><span class="sxs-lookup"><span data-stu-id="39a78-329">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you select **Apply** to submit your policy assignment, select **Activity log**.</span></span> <span data-ttu-id="39a78-330">Oppure, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Dashboard** e quindi, in **Log** attività, **seleziona Visualizza dettagli.**</span><span class="sxs-lookup"><span data-stu-id="39a78-330">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, select **View details**.</span></span> <span data-ttu-id="39a78-331">Il log attività mostra le assegnazioni dei criteri a batch di più di 20 utenti tramite l'interfaccia di amministrazione di Microsoft Teams degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="39a78-331">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="39a78-332">Per altre informazioni, vedi [Visualizzare le assegnazioni dei criteri nel log attività.](activity-log.md)</span><span class="sxs-lookup"><span data-stu-id="39a78-332">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="use-powershell-method"></a><span data-ttu-id="39a78-333">Usare il metodo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="39a78-333">Use PowerShell method</span></span>

> [!NOTE]
> <span data-ttu-id="39a78-334">Attualmente, l'assegnazione di criteri batch con PowerShell non è disponibile per tutti i tipi di criteri di Teams.</span><span class="sxs-lookup"><span data-stu-id="39a78-334">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="39a78-335">Vedere [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) per l'elenco dei tipi di criteri supportati.</span><span class="sxs-lookup"><span data-stu-id="39a78-335">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

<span data-ttu-id="39a78-336">Con l'assegnazione di criteri batch, è possibile assegnare un criterio a grandi set di utenti contemporaneamente senza dover usare uno script.</span><span class="sxs-lookup"><span data-stu-id="39a78-336">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="39a78-337">Usare il cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) per inviare un batch di utenti e il criterio da assegnare.</span><span class="sxs-lookup"><span data-stu-id="39a78-337">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="39a78-338">Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch.</span><span class="sxs-lookup"><span data-stu-id="39a78-338">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="39a78-339">È quindi possibile usare il cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) per tenere traccia dello stato delle assegnazioni in batch.</span><span class="sxs-lookup"><span data-stu-id="39a78-339">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="39a78-340">Specificare gli utenti in base all'ID oggetto o all'indirizzo SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="39a78-340">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="39a78-341">L'indirizzo SIP di un utente spesso ha lo stesso valore del nome dell'entità utente (UPN) o dell'indirizzo di posta elettronica, ma non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="39a78-341">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="39a78-342">Se un utente viene specificato usando l'UPN o l'indirizzo di posta elettronica, ma ha un valore diverso dall'indirizzo SIP, l'assegnazione dei criteri non riuscirà per l'utente.</span><span class="sxs-lookup"><span data-stu-id="39a78-342">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="39a78-343">Se un batch include utenti duplicati, i duplicati verranno rimossi dal batch prima dell'elaborazione e lo stato verrà fornito solo per gli utenti univoci che restano nel batch.</span><span class="sxs-lookup"><span data-stu-id="39a78-343">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="39a78-344">Un batch può contenere fino a 5.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="39a78-344">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="39a78-345">Per risultati ottimali, non inviare più di pochi batch alla volta.</span><span class="sxs-lookup"><span data-stu-id="39a78-345">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="39a78-346">Consentire il completamento dell'elaborazione dei batch prima di inviare altri batch.</span><span class="sxs-lookup"><span data-stu-id="39a78-346">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-teams-powershell-module"></a><span data-ttu-id="39a78-347">Installare e connettersi al modulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="39a78-347">Install and connect to the Teams PowerShell module</span></span>

<span data-ttu-id="39a78-348">Eseguire la procedura seguente per installare il modulo [Microsoft Teams PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams)</span><span class="sxs-lookup"><span data-stu-id="39a78-348">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="39a78-349">Assicurarsi di installare la versione 1.0.5 o successiva.</span><span class="sxs-lookup"><span data-stu-id="39a78-349">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="39a78-350">Esegui quanto segue per connetterti a Teams e avviare una sessione.</span><span class="sxs-lookup"><span data-stu-id="39a78-350">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="39a78-351">Quando richiesto, accedere con le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="39a78-351">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="39a78-352">Installare e connettersi al modulo Azure AD PowerShell per Graph (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="39a78-352">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="39a78-353">È anche possibile scaricare e installare il modulo [Azure AD PowerShell per Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (se non è già stato fatto) e connettersi ad Azure AD in modo da poter recuperare un elenco di utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="39a78-353">You might also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="39a78-354">Eseguire la procedura seguente per connettersi ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="39a78-354">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="39a78-355">Quando richiesto, accedere con le stesse credenziali di amministratore usate per connettersi a Teams.</span><span class="sxs-lookup"><span data-stu-id="39a78-355">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a><span data-ttu-id="39a78-356">Assegnare criteri di configurazione a un batch di utenti</span><span class="sxs-lookup"><span data-stu-id="39a78-356">Assign a setup policy to a batch of users</span></span>

<span data-ttu-id="39a78-357">In questo esempio viene utilizzato il cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) per assegnare un criterio di configurazione dell'app denominato Criteri di configurazione app risorse umane a un batch di utenti elencati nel file Users_ids.text.</span><span class="sxs-lookup"><span data-stu-id="39a78-357">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="39a78-358">In questo esempio ci connettiamo ad Azure AD per recuperare una raccolta di utenti e quindi assegniamo un criterio di messaggistica denominato Criterio di messaggistica di nuova assunzione a un batch di utenti specificato usando il loro indirizzo SIP.</span><span class="sxs-lookup"><span data-stu-id="39a78-358">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="39a78-359">Ottenere lo stato di un'assegnazione batch</span><span class="sxs-lookup"><span data-stu-id="39a78-359">Get the status of a batch assignment</span></span>

<span data-ttu-id="39a78-360">Eseguire la procedura seguente per ottenere lo stato di un'assegnazione batch, dove OperationId è l'ID operazione restituito dal ```New-CsBatchPolicyAssignmentOperation``` cmdlet per un determinato batch.</span><span class="sxs-lookup"><span data-stu-id="39a78-360">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="39a78-361">Se l'output indica che si è verificato un errore, eseguire la procedura seguente per ottenere altre informazioni sugli errori presenti nella ```UserState``` proprietà.</span><span class="sxs-lookup"><span data-stu-id="39a78-361">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="39a78-362">Per altre informazioni, vedere [Get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="39a78-362">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="39a78-363">Assegnare un pacchetto di criteri agli utenti</span><span class="sxs-lookup"><span data-stu-id="39a78-363">Assign a policy package to users</span></span>

<span data-ttu-id="39a78-364">Un pacchetto di criteri in Teams è una raccolta di criteri e impostazioni dei criteri predefiniti che è possibile assegnare agli utenti con ruoli uguali o simili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="39a78-364">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="39a78-365">Ogni pacchetto di criteri è progettato in base a un ruolo utente e include criteri e impostazioni dei criteri predefiniti che supportano le attività tipiche per quel ruolo.</span><span class="sxs-lookup"><span data-stu-id="39a78-365">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="39a78-366">Alcuni esempi di pacchetti di criteri sono il pacchetto Education (Teacher) e Il pacchetto Healthcare (operatore clinico).</span><span class="sxs-lookup"><span data-stu-id="39a78-366">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="39a78-367">Per altre informazioni, vedere [Gestire i pacchetti di criteri in Teams.](manage-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="39a78-367">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="39a78-368">Assegnare un pacchetto di criteri a un utente</span><span class="sxs-lookup"><span data-stu-id="39a78-368">Assign a policy package to one user</span></span>

1. <span data-ttu-id="39a78-369">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa **a** Utenti e quindi seleziona l'utente.</span><span class="sxs-lookup"><span data-stu-id="39a78-369">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="39a78-370">Nella pagina dell'utente selezionare **Criteri,** quindi accanto a Pacchetto **di criteri** selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="39a78-370">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>
3. <span data-ttu-id="39a78-371">Nel riquadro **Assegna pacchetto dei** criteri seleziona il pacchetto che vuoi assegnare e quindi seleziona **Salva.**</span><span class="sxs-lookup"><span data-stu-id="39a78-371">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="39a78-372">Assegnare un pacchetto di criteri a più utenti</span><span class="sxs-lookup"><span data-stu-id="39a78-372">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="39a78-373">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, vai a Pacchetti **criteri,** quindi seleziona il pacchetto di criteri da assegnare facendo clic a sinistra del nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="39a78-373">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="39a78-374">Scegliere **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="39a78-374">Select **Manage users**.</span></span>
3. <span data-ttu-id="39a78-375">Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="39a78-375">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="39a78-376">Ripetere questa operazione per ogni utente da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="39a78-376">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="39a78-377">Dopo aver aggiunto gli utenti, selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="39a78-377">When you're finished adding users, select **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="39a78-378">Assegnare un pacchetto di criteri a un gruppo</span><span class="sxs-lookup"><span data-stu-id="39a78-378">Assign a policy package to a group</span></span>

<span data-ttu-id="39a78-379">**Questa funzionalità è in anteprima privata**</span><span class="sxs-lookup"><span data-stu-id="39a78-379">**This feature is in private preview**</span></span>

<span data-ttu-id="39a78-380">L'assegnazione di pacchetti di criteri ai gruppi consente di assegnare più criteri a un gruppo di utenti, ad esempio un gruppo di sicurezza o una lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="39a78-380">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="39a78-381">L'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza.</span><span class="sxs-lookup"><span data-stu-id="39a78-381">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="39a78-382">Quando vengono aggiunti o rimossi membri da un gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="39a78-382">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="39a78-383">L'assegnazione di pacchetti di criteri ai gruppi è consigliata per gruppi di un massimo di 50.000 utenti, ma funziona anche con gruppi più grandi.</span><span class="sxs-lookup"><span data-stu-id="39a78-383">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="39a78-384">Quando si assegna il pacchetto di criteri, questo viene immediatamente assegnato al gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-384">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="39a78-385">Tuttavia, la propagazione dell'assegnazione dei criteri ai membri del gruppo viene eseguita come operazione in background e potrebbe richiedere del tempo, a seconda delle dimensioni del gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-385">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="39a78-386">Lo stesso vale quando un criterio non è assegnato a un gruppo o quando i membri vengono aggiunti o rimossi da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-386">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39a78-387">Prima di iniziare, è importante comprendere le regole di precedenza e la [classificazione](#precedence-rules) [delle assegnazioni dei gruppi.](#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="39a78-387">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="39a78-388">Leggere e comprendere i concetti che è necessario conoscere sull'assegnazione [dei](#what-you-need-to-know-about-policy-assignment-to-groups) criteri ai gruppi in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="39a78-388">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="39a78-389">Assegnare un pacchetto di criteri a un gruppo di utenti nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="39a78-389">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="39a78-390">Accedere all'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="39a78-390">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="39a78-391">Nel riquadro di spostamento sinistro passare alla pagina del pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="39a78-391">In the left navigation, go to the policy package page.</span></span>
3. <span data-ttu-id="39a78-392">Selezionare la scheda di assegnazione di Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-392">Select the Group policy assignment tab.</span></span>
4. <span data-ttu-id="39a78-393">Selezionare **Aggiungi gruppo,** quindi nel riquadro Assegna un pacchetto di criteri al gruppo eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="39a78-393">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    <span data-ttu-id="39a78-394">a.</span><span class="sxs-lookup"><span data-stu-id="39a78-394">a.</span></span> <span data-ttu-id="39a78-395">Cerca e aggiungi il gruppo a cui vuoi assegnare il pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="39a78-395">Search for and add the group you want to assign the policy package to.</span></span>

    <span data-ttu-id="39a78-396">b.</span><span class="sxs-lookup"><span data-stu-id="39a78-396">b.</span></span> <span data-ttu-id="39a78-397">Seleziona un pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="39a78-397">Select a policy package.</span></span>

    <span data-ttu-id="39a78-398">c.</span><span class="sxs-lookup"><span data-stu-id="39a78-398">c.</span></span> <span data-ttu-id="39a78-399">Impostare la classificazione per ogni tipo di criterio.</span><span class="sxs-lookup"><span data-stu-id="39a78-399">Set the ranking for each policy type.</span></span>

    <span data-ttu-id="39a78-400">d.</span><span class="sxs-lookup"><span data-stu-id="39a78-400">d.</span></span> <span data-ttu-id="39a78-401">Selezionare **Applica.**</span><span class="sxs-lookup"><span data-stu-id="39a78-401">Select **Apply**.</span></span>

    ![mostra l'assegnazione di Criteri di gruppo](media/group-pkg-assignment.png)

5. <span data-ttu-id="39a78-403">Per gestire la classificazione per un tipo di criterio specifico, passare alla pagina dei criteri specifici.</span><span class="sxs-lookup"><span data-stu-id="39a78-403">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>
6. <span data-ttu-id="39a78-404">Per riassegnare un pacchetto di criteri a un gruppo, rimuovere prima l'assegnazione di Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-404">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="39a78-405">Seguire quindi la procedura precedente per assegnare il pacchetto di criteri a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-405">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="39a78-406">Usare PowerShell</span><span class="sxs-lookup"><span data-stu-id="39a78-406">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="39a78-407">Ottenere il modulo Di PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="39a78-407">Get the Teams PowerShell module</span></span>

<span data-ttu-id="39a78-408">Per istruzioni dettagliate, vedere Installare [PowerShell di Teams.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="39a78-408">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="39a78-409">Assegnare un pacchetto di criteri a un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="39a78-409">Assign a policy package to a group of users</span></span>

<span data-ttu-id="39a78-410">Usare il cmdlet [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) per assegnare un pacchetto di criteri a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a78-410">Use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="39a78-411">È possibile specificare un gruppo usando l'ID oggetto, l'indirizzo SIP o l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="39a78-411">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="39a78-412">Quando si assegna il pacchetto di criteri, specificare una classificazione [delle assegnazioni di gruppo](#group-assignment-ranking) per ogni tipo di criterio nel pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="39a78-412">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span>

<span data-ttu-id="39a78-413">In questo esempio il pacchetto di criteri Education_Teacher viene assegnato a un gruppo con una classificazione di assegnazione 1 per TeamsAppSetupPolicy e TeamsMeetingBroadcastPolicy e una classificazione 2 per TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="39a78-413">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="39a78-414">Assegnare un pacchetto di criteri a un batch di utenti</span><span class="sxs-lookup"><span data-stu-id="39a78-414">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="39a78-415">Con l'assegnazione di pacchetti di criteri batch, è possibile assegnare un pacchetto di criteri a grandi set di utenti contemporaneamente senza dover usare uno script.</span><span class="sxs-lookup"><span data-stu-id="39a78-415">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="39a78-416">Usare il cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) per inviare un batch di utenti e il pacchetto di criteri da assegnare.</span><span class="sxs-lookup"><span data-stu-id="39a78-416">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="39a78-417">Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch.</span><span class="sxs-lookup"><span data-stu-id="39a78-417">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="39a78-418">È quindi possibile usare il cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) per tenere traccia dello stato delle assegnazioni in batch.</span><span class="sxs-lookup"><span data-stu-id="39a78-418">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="39a78-419">Specificare gli utenti in base all'ID oggetto o all'indirizzo SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="39a78-419">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="39a78-420">L'indirizzo SIP di un utente spesso ha lo stesso valore del nome dell'entità utente (UPN) o dell'indirizzo di posta elettronica, ma non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="39a78-420">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="39a78-421">Se un utente viene specificato usando l'UPN o l'indirizzo di posta elettronica, ma ha un valore diverso dall'indirizzo SIP, l'assegnazione dei criteri non riuscirà per l'utente.</span><span class="sxs-lookup"><span data-stu-id="39a78-421">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="39a78-422">Se un batch include utenti duplicati, i duplicati verranno rimossi dal batch prima dell'elaborazione e lo stato verrà fornito solo per gli utenti univoci che restano nel batch.</span><span class="sxs-lookup"><span data-stu-id="39a78-422">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="39a78-423">Un batch contiene fino a 5.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="39a78-423">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="39a78-424">Per risultati ottimali, non inviare più di pochi batch alla volta.</span><span class="sxs-lookup"><span data-stu-id="39a78-424">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="39a78-425">Consentire il completamento dell'elaborazione dei batch prima di inviare altri batch.</span><span class="sxs-lookup"><span data-stu-id="39a78-425">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="39a78-426">Usare il modulo Teams di PowerShell</span><span class="sxs-lookup"><span data-stu-id="39a78-426">Use the Teams PowerShell module</span></span>

<span data-ttu-id="39a78-427">Esegui quanto segue per installare il [modulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se non l'hai già fatto).</span><span class="sxs-lookup"><span data-stu-id="39a78-427">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="39a78-428">Assicurarsi di installare la versione 1.0.5 o successiva.</span><span class="sxs-lookup"><span data-stu-id="39a78-428">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="39a78-429">Esegui quanto segue per connetterti a Teams e avviare una sessione.</span><span class="sxs-lookup"><span data-stu-id="39a78-429">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="39a78-430">Quando richiesto, accedere con le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="39a78-430">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="39a78-431">Assegnare pacchetti di criteri a un batch di utenti</span><span class="sxs-lookup"><span data-stu-id="39a78-431">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="39a78-432">In questo esempio viene utilizzato il cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) per assegnare il pacchetto di criteri Education_PrimaryStudent a un batch di utenti.</span><span class="sxs-lookup"><span data-stu-id="39a78-432">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="39a78-433">Visualizzare lo stato di un'assegnazione batch</span><span class="sxs-lookup"><span data-stu-id="39a78-433">See the status of a batch assignment</span></span>

<span data-ttu-id="39a78-434">Eseguire la procedura seguente per ottenere lo stato di un'assegnazione batch, dove OperationId è l'ID operazione restituito dal ```New-CsBatchPolicyAssignmentOperation``` cmdlet per un determinato batch.</span><span class="sxs-lookup"><span data-stu-id="39a78-434">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="39a78-435">Se l'output indica che si è verificato un errore, eseguire la procedura seguente per ottenere altre informazioni sugli errori presenti nella ```UserState``` proprietà.</span><span class="sxs-lookup"><span data-stu-id="39a78-435">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="39a78-436">Per altre informazioni, vedere [Get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="39a78-436">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="39a78-437">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="39a78-437">Related topics</span></span>

[<span data-ttu-id="39a78-438">Panoramica di Teams su PowerShell</span><span class="sxs-lookup"><span data-stu-id="39a78-438">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
