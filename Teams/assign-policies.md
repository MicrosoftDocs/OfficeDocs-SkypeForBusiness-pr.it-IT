---
title: Assegnare i criteri agli utenti in Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Scopri i diversi modi per assegnare i criteri agli utenti in Microsoft teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: ada58a9abf07e606f91d48b7ac71ba06d4c1496a
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085700"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="25caa-103">Assegnare i criteri agli utenti in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="25caa-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="25caa-104">Come amministratore, puoi usare i criteri per controllare le caratteristiche dei team disponibili per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="25caa-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="25caa-105">Ad esempio, esistono criteri per la chiamata, criteri per le riunioni e criteri di messaggistica, per citarne solo alcuni.</span><span class="sxs-lookup"><span data-stu-id="25caa-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="25caa-106">Le organizzazioni hanno diversi tipi di utenti con esigenze esclusive e criteri personalizzati creati e assegnati consentono di adattare le impostazioni dei criteri a diversi set di utenti in base a tali esigenze.</span><span class="sxs-lookup"><span data-stu-id="25caa-106">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="25caa-107">Per semplificare la gestione dei criteri nell'organizzazione, teams offre diversi modi per assegnare i criteri agli utenti.</span><span class="sxs-lookup"><span data-stu-id="25caa-107">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="25caa-108">È possibile assegnare un criterio direttamente agli utenti, singolarmente o in scala, tramite un'assegnazione batch o a un gruppo di cui fanno parte gli utenti.</span><span class="sxs-lookup"><span data-stu-id="25caa-108">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="25caa-109">Puoi anche usare i pacchetti di criteri per assegnare una raccolta preimpostata di criteri agli utenti dell'organizzazione che hanno ruoli simili.</span><span class="sxs-lookup"><span data-stu-id="25caa-109">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="25caa-110">L'opzione scelta dipende dal numero di criteri che si stanno gestendo e dal numero di utenti a cui si sta assegnando.</span><span class="sxs-lookup"><span data-stu-id="25caa-110">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="25caa-111">Impostando i criteri globali (a livello di organizzazione) in modo che vengano applicati al numero maggiore di utenti dell'organizzazione, è necessario assegnare i criteri solo agli utenti che richiedono criteri specializzati.</span><span class="sxs-lookup"><span data-stu-id="25caa-111">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="25caa-112">In questo articolo vengono illustrati i diversi modi in cui è possibile assegnare i criteri agli utenti e gli scenari consigliati per quando usare cosa.</span><span class="sxs-lookup"><span data-stu-id="25caa-112">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="25caa-113">Quali criteri hanno la precedenza?</span><span class="sxs-lookup"><span data-stu-id="25caa-113">Which policy takes precedence?</span></span>

<span data-ttu-id="25caa-114">Un utente ha un criterio effettivo per ogni tipo di criterio.</span><span class="sxs-lookup"><span data-stu-id="25caa-114">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="25caa-115">È possibile o anche probabile che a un utente venga assegnato direttamente un criterio ed è anche membro di uno o più gruppi a cui è assegnato un criterio dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="25caa-115">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="25caa-116">In questi tipi di scenari, quali criteri hanno la precedenza?</span><span class="sxs-lookup"><span data-stu-id="25caa-116">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="25caa-117">I criteri effettivi di un utente vengono determinati in base alle regole di precedenza, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="25caa-117">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="25caa-118">Se a un utente viene assegnato direttamente un criterio (individualmente o tramite un'assegnazione batch), tale criterio avrà la precedenza.</span><span class="sxs-lookup"><span data-stu-id="25caa-118">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="25caa-119">Nell'esempio seguente, il criterio effettivo dell'utente è il criterio riunione di Lincoln Square, che viene direttamente assegnato all'utente.</span><span class="sxs-lookup"><span data-stu-id="25caa-119">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagramma che mostra il modo in cui un criterio assegnato direttamente ha la precedenza](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="25caa-121">Se un utente non viene assegnato direttamente a un criterio di un tipo specificato, il criterio assegnato a un gruppo di cui l'utente è membro ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="25caa-121">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="25caa-122">Se un utente è un membro di più gruppi, il criterio con la classificazione delle [assegnazioni di gruppo](#group-assignment-ranking) più alta per il tipo di criteri specifico ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="25caa-122">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="25caa-123">In questo esempio, i criteri effettivi dell'utente sono i team Exec e i criteri HD, che hanno il ranking di assegnazione più alto rispetto ad altri gruppi a cui l'utente fa parte e a cui sono assegnati anche i criteri dello stesso tipo di criteri.</span><span class="sxs-lookup"><span data-stu-id="25caa-123">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagramma che mostra il modo in cui un criterio ereditato dal gruppo ha la precedenza](media/assign-policies-example-group.png)

<span data-ttu-id="25caa-125">Se a un utente non viene assegnato un criterio o non è un membro di un gruppo a cui è assegnato un criterio, l'utente otterrà il criterio globale (a livello di organizzazione) per il tipo di criteri.</span><span class="sxs-lookup"><span data-stu-id="25caa-125">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="25caa-126">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="25caa-126">Here's an example.</span></span>

![Diagramma che mostra il modo in cui prevale un criterio globale](media/assign-policies-example-global.png)

<span data-ttu-id="25caa-128">Per altre informazioni, Vedi [regole di precedenza](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="25caa-128">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="25caa-129">Modalità di assegnazione di criteri</span><span class="sxs-lookup"><span data-stu-id="25caa-129">Ways to assign policies</span></span>

<span data-ttu-id="25caa-130">Ecco una panoramica dei modi in cui è possibile assegnare i criteri agli utenti e gli scenari consigliati per ognuno.</span><span class="sxs-lookup"><span data-stu-id="25caa-130">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="25caa-131">Fare clic sui collegamenti per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="25caa-131">Click the links to learn more.</span></span>

<span data-ttu-id="25caa-132">Prima di assegnare criteri a singoli utenti o gruppi, iniziare [impostando i criteri globali (org-Wide default)](#set-the-global-policies) in modo che vengano applicati al numero maggiore di utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="25caa-132">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="25caa-133">Una volta impostati i criteri globali, sarà necessario assegnare i criteri solo agli utenti che richiedono criteri specializzati.</span><span class="sxs-lookup"><span data-stu-id="25caa-133">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="25caa-134">Operazione da eseguire</span><span class="sxs-lookup"><span data-stu-id="25caa-134">Do this</span></span>  |<span data-ttu-id="25caa-135">Se...</span><span class="sxs-lookup"><span data-stu-id="25caa-135">If...</span></span>  | <span data-ttu-id="25caa-136">Uso di...</span><span class="sxs-lookup"><span data-stu-id="25caa-136">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="25caa-137">Assegnare un criterio a singoli utenti</span><span class="sxs-lookup"><span data-stu-id="25caa-137">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="25caa-138">Si è nuovi team e si è appena iniziato o si deve solo assegnare uno o due criteri a un numero limitato di utenti.</span><span class="sxs-lookup"><span data-stu-id="25caa-138">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="25caa-139">L'interfaccia di amministrazione di Microsoft teams o i cmdlet di PowerShell nel modulo di PowerShell Skype for business online</span><span class="sxs-lookup"><span data-stu-id="25caa-139">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
|[<span data-ttu-id="25caa-140">Assegnare un criterio a un gruppo</span><span class="sxs-lookup"><span data-stu-id="25caa-140">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="25caa-141">È necessario assegnare criteri in base all'appartenenza al gruppo di un utente.</span><span class="sxs-lookup"><span data-stu-id="25caa-141">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="25caa-142">Ad esempio, si vuole assegnare un criterio a tutti gli utenti in un gruppo di sicurezza o in una lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="25caa-142">For example, you want to assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="25caa-143">Interfaccia di amministrazione di Microsoft teams o cmdlet di PowerShell nel modulo di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="25caa-143">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="25caa-144">Assegnare un criterio a un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="25caa-144">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="25caa-145">È necessario assegnare criteri a set di utenti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="25caa-145">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="25caa-146">Ad esempio, si vuole assegnare un criterio a centinaia o migliaia di utenti dell'organizzazione alla volta.</span><span class="sxs-lookup"><span data-stu-id="25caa-146">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="25caa-147">Interfaccia di amministrazione di Microsoft teams o cmdlet di PowerShell nel modulo di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="25caa-147">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="25caa-148">Assegnare un pacchetto di criteri agli utenti</span><span class="sxs-lookup"><span data-stu-id="25caa-148">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  | <span data-ttu-id="25caa-149">È necessario assegnare più criteri a specifici set di utenti dell'organizzazione che hanno ruoli uguali o simili.</span><span class="sxs-lookup"><span data-stu-id="25caa-149">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="25caa-150">Ad esempio, assegnare il pacchetto di criteri Education (Teacher) agli insegnanti della scuola per consentire loro l'accesso completo alle chat, alle chiamate e alle riunioni e al pacchetto di criteri per l'istruzione (studente della scuola secondaria) agli studenti secondari per limitare alcune funzionalità come le chiamate private.</span><span class="sxs-lookup"><span data-stu-id="25caa-150">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="25caa-151">Interfaccia di amministrazione di Microsoft teams o cmdlet di PowerShell nel modulo di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="25caa-151">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="25caa-152">[Assegnare un pacchetto di criteri a un gruppo](#assign-a-policy-package-to-a-group) (in anteprima privata)</span><span class="sxs-lookup"><span data-stu-id="25caa-152">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="25caa-153">È necessario assegnare più criteri a un gruppo di utenti dell'organizzazione che hanno ruoli uguali o simili.</span><span class="sxs-lookup"><span data-stu-id="25caa-153">You need to assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="25caa-154">Ad esempio, si vuole assegnare un pacchetto di criteri a tutti gli utenti in un gruppo di sicurezza o in una lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="25caa-154">For example, you want to assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="25caa-155">L'interfaccia di amministrazione di Microsoft Teams (disponibile a breve) o i cmdlet di PowerShell nel modulo di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="25caa-155">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="25caa-156">Assegnare un pacchetto di criteri a un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="25caa-156">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="25caa-157">È necessario assegnare più criteri a un gruppo di utenti dell'organizzazione che hanno ruoli uguali o simili.</span><span class="sxs-lookup"><span data-stu-id="25caa-157">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="25caa-158">Ad esempio, assegna il pacchetto di criteri Education (Teacher) a tutti gli insegnanti dell'Istituto di istruzione usando l'assegnazione batch per consentire loro l'accesso completo alle chat, alle chiamate e alle riunioni e assegnare il pacchetto di criteri per l'istruzione (studente di scuola secondaria) a un gruppo di studenti secondari per limitare alcune funzionalità come le chiamate private.</span><span class="sxs-lookup"><span data-stu-id="25caa-158">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="25caa-159">Cmdlet di PowerShell nel modulo di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="25caa-159">PowerShell cmdlets in the Teams PowerShell module</span></span>|


## <a name="set-the-global-policies"></a><span data-ttu-id="25caa-160">Impostare i criteri globali</span><span class="sxs-lookup"><span data-stu-id="25caa-160">Set the global policies</span></span>

<span data-ttu-id="25caa-161">Seguire questa procedura per impostare i criteri globali (per impostazione predefinita a livello di organizzazione) per ogni tipo di criterio.</span><span class="sxs-lookup"><span data-stu-id="25caa-161">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="25caa-162">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="25caa-162">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="25caa-163">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa alla pagina dei criteri per il tipo di criterio che vuoi aggiornare.</span><span class="sxs-lookup"><span data-stu-id="25caa-163">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="25caa-164">Ad **esempio, criteri Team teams**  >  **Teams policies**, **Meetings**  >  **criteri riunioni** riunioni, **criteri di messaggistica** o criteri di chiamata **vocale**  >  **Calling policies**.</span><span class="sxs-lookup"><span data-stu-id="25caa-164">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="25caa-165">Selezionare il criterio **globale (predefinito per l'intera organizzazione)** per visualizzare le impostazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="25caa-165">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="25caa-166">Aggiornare i criteri in base alle esigenze e quindi selezionare **applica**.</span><span class="sxs-lookup"><span data-stu-id="25caa-166">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="25caa-167">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="25caa-167">Using PowerShell</span></span>

<span data-ttu-id="25caa-168">Per impostare i criteri globali tramite PowerShell, usare l'identificatore globale.</span><span class="sxs-lookup"><span data-stu-id="25caa-168">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="25caa-169">Iniziare rivedendo il criterio globale corrente per determinare l'impostazione che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="25caa-169">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="25caa-170">Aggiornare quindi il criterio globale in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="25caa-170">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="25caa-171">È necessario specificare solo i valori per le impostazioni che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="25caa-171">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="25caa-172">Assegnare un criterio a singoli utenti</span><span class="sxs-lookup"><span data-stu-id="25caa-172">Assign a policy to individual users</span></span>

<span data-ttu-id="25caa-173">Seguire questa procedura per assegnare un criterio a un singolo utente o a un numero limitato di utenti alla volta.</span><span class="sxs-lookup"><span data-stu-id="25caa-173">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="25caa-174">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="25caa-174">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="25caa-175">Per assegnare un criterio a un utente:</span><span class="sxs-lookup"><span data-stu-id="25caa-175">To assign a policy to a user:</span></span>

1. <span data-ttu-id="25caa-176">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.</span><span class="sxs-lookup"><span data-stu-id="25caa-176">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="25caa-177">Per selezionare l'utente facendo clic a sinistra del nome utente e poi fare clic su **Impostazioni di modifica**.</span><span class="sxs-lookup"><span data-stu-id="25caa-177">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="25caa-178">Selezionare il criterio che si vuole assegnare e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="25caa-178">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="25caa-179">Si può anche procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="25caa-179">Or, you can also do the following:</span></span>

1. <span data-ttu-id="25caa-180">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa alla pagina dei criteri.</span><span class="sxs-lookup"><span data-stu-id="25caa-180">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="25caa-181">Selezionare il criterio che si vuole assegnare facendo clic a sinistra del nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="25caa-181">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="25caa-182">Scegliere **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="25caa-182">Select **Manage users**.</span></span>
4. <span data-ttu-id="25caa-183">Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="25caa-183">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="25caa-184">Ripetere questa operazione per ogni utente da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="25caa-184">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="25caa-185">Al termine dell'aggiunta di utenti, selezionare **applica**.</span><span class="sxs-lookup"><span data-stu-id="25caa-185">When you're finished adding users, select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="25caa-186">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="25caa-186">Using PowerShell</span></span>

<span data-ttu-id="25caa-187">Ogni tipo di criterio ha un proprio set di cmdlet per la gestione.</span><span class="sxs-lookup"><span data-stu-id="25caa-187">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="25caa-188">Usa il ```Grant-``` cmdlet per un tipo di criteri specifico per assegnare i criteri.</span><span class="sxs-lookup"><span data-stu-id="25caa-188">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="25caa-189">Ad esempio, usa il ```Grant-CsTeamsMeetingPolicy``` cmdlet per assegnare un criterio di riunione teams agli utenti.</span><span class="sxs-lookup"><span data-stu-id="25caa-189">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="25caa-190">Questi cmdlet sono inclusi nel modulo di PowerShell per Skype for business online e sono documentati nella Guida di [riferimento ai cmdlet di Skype for business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="25caa-190">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="25caa-191">Scaricare e installare il [modulo di PowerShell per Skype for business online](https://www.microsoft.com/download/details.aspx?id=39366) (se non è già stato fatto), quindi eseguire le operazioni seguenti per connettersi a Skype for business online e avviare una sessione.</span><span class="sxs-lookup"><span data-stu-id="25caa-191">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

> [!NOTE]
> <span data-ttu-id="25caa-192">Skype for Business Online Connector fa attualmente parte del modulo di PowerShell più recente di teams.</span><span class="sxs-lookup"><span data-stu-id="25caa-192">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="25caa-193">Se si usa l'ultima [versione pubblica di PowerShell per Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/), non è necessario installare il connettore Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="25caa-193">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="25caa-194">In questo esempio, assegniamo un criterio riunione teams denominato criteri riunione studenti a un utente di nome Reda.</span><span class="sxs-lookup"><span data-stu-id="25caa-194">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="25caa-195">Per altre informazioni, leggere [gestire i criteri tramite PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="25caa-195">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="25caa-196">Assegnare un criterio a un gruppo</span><span class="sxs-lookup"><span data-stu-id="25caa-196">Assign a policy to a group</span></span>

<span data-ttu-id="25caa-197">L'assegnazione dei criteri a gruppi consente di assegnare un criterio a un gruppo di utenti, ad esempio un gruppo di sicurezza o una lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="25caa-197">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="25caa-198">L'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza.</span><span class="sxs-lookup"><span data-stu-id="25caa-198">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="25caa-199">Quando vengono aggiunti o rimossi membri da un gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="25caa-199">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="25caa-200">L'assegnazione dei criteri ai gruppi è consigliata per i gruppi di utenti fino a 50.000, ma funziona anche con i gruppi più grandi.</span><span class="sxs-lookup"><span data-stu-id="25caa-200">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="25caa-201">Quando si assegna il criterio, viene immediatamente assegnato al gruppo.</span><span class="sxs-lookup"><span data-stu-id="25caa-201">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="25caa-202">Si noti tuttavia che la propagazione dell'assegnazione dei criteri ai membri del gruppo viene eseguita come operazione in background e può richiedere del tempo, a seconda delle dimensioni del gruppo.</span><span class="sxs-lookup"><span data-stu-id="25caa-202">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="25caa-203">Lo stesso vale quando un criterio non viene assegnato da un gruppo o quando i membri vengono aggiunti o rimossi da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="25caa-203">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="25caa-204">Le assegnazioni dei criteri di gruppo vengono propagate solo agli utenti che sono membri diretti del gruppo.</span><span class="sxs-lookup"><span data-stu-id="25caa-204">Group policy assignments are only propagated to users that are direct members of the group.</span></span> <span data-ttu-id="25caa-205">Le assegnazioni non vengono propagate ai membri dei gruppi annidati.</span><span class="sxs-lookup"><span data-stu-id="25caa-205">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="25caa-206">Informazioni utili sull'assegnazione dei criteri ai gruppi</span><span class="sxs-lookup"><span data-stu-id="25caa-206">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="25caa-207">Prima di iniziare, è importante comprendere le regole di precedenza e la classificazione delle assegnazioni di gruppo.</span><span class="sxs-lookup"><span data-stu-id="25caa-207">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="25caa-208">Regole di precedenza</span><span class="sxs-lookup"><span data-stu-id="25caa-208">Precedence rules</span></span>

<span data-ttu-id="25caa-209">Per un determinato tipo di criteri, il criterio effettivo di un utente viene determinato in base alle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="25caa-209">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="25caa-210">Un criterio assegnato direttamente a un utente ha la precedenza su qualsiasi altro criterio dello stesso tipo assegnato a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="25caa-210">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="25caa-211">In altre parole, se a un utente viene assegnato direttamente un criterio di un tipo specifico, l'utente non erediterà un criterio dello stesso tipo da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="25caa-211">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="25caa-212">Ciò significa anche che, se un utente ha un criterio di un tipo specifico a cui è stato assegnato direttamente, è necessario rimuovere i criteri dall'utente prima che possano ereditare un criterio dello stesso tipo da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="25caa-212">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="25caa-213">Se un utente non ha un criterio direttamente assegnato ed è un membro di due o più gruppi e ogni gruppo ha un criterio dello stesso tipo assegnato, l'utente eredita i criteri dell'assegnazione del gruppo con la classificazione più alta.</span><span class="sxs-lookup"><span data-stu-id="25caa-213">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="25caa-214">Se un utente non è un membro di tutti i gruppi a cui è assegnato un criterio, il criterio globale (a livello di organizzazione predefinita) per tale tipo di criteri si applica all'utente.</span><span class="sxs-lookup"><span data-stu-id="25caa-214">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="25caa-215">I criteri effettivi di un utente vengono aggiornati in base a queste regole quando un utente viene aggiunto o rimosso da un gruppo a cui è assegnato un criterio, un criterio non è assegnato da un gruppo o viene rimosso un criterio direttamente assegnato all'utente.</span><span class="sxs-lookup"><span data-stu-id="25caa-215">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="25caa-216">Classificazione delle assegnazioni di gruppo</span><span class="sxs-lookup"><span data-stu-id="25caa-216">Group assignment ranking</span></span>
 
<span data-ttu-id="25caa-217">Quando si assegna un criterio a un gruppo, è necessario specificare una classificazione per l'assegnazione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="25caa-217">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="25caa-218">Viene usato per determinare i criteri che un utente deve ereditare come criterio effettivo se l'utente è un membro di due o più gruppi e a ogni gruppo viene assegnato un criterio dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="25caa-218">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="25caa-219">La classificazione delle assegnazioni di gruppo è relativa ad altre assegnazioni di gruppo dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="25caa-219">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="25caa-220">Ad esempio, se si sta assegnando un criterio di chiamata a due gruppi, impostare la classificazione di un'assegnazione su 1 e l'altra su 2, con 1 che è la classificazione più alta.</span><span class="sxs-lookup"><span data-stu-id="25caa-220">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="25caa-221">La classificazione delle assegnazioni di gruppo indica l'appartenenza a un gruppo più importante o più pertinente rispetto alle altre appartenenze ai gruppi per quanto riguarda l'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="25caa-221">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="25caa-222">Supponiamo, ad esempio, di avere due gruppi, i dipendenti dello Store e i responsabili dello Store.</span><span class="sxs-lookup"><span data-stu-id="25caa-222">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="25caa-223">A entrambi i gruppi viene assegnato un criterio di chiamata per i team, rispettivamente i criteri di chiamata dei dipendenti e i responsabili dello Store.</span><span class="sxs-lookup"><span data-stu-id="25caa-223">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="25caa-224">Per un responsabile dello Store che si trova in entrambi i gruppi, il loro ruolo di Manager è più pertinente del loro ruolo di dipendente, quindi il criterio di chiamata assegnato al gruppo responsabili dello Store dovrebbe avere una classificazione più alta.</span><span class="sxs-lookup"><span data-stu-id="25caa-224">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="25caa-225">Gruppo</span><span class="sxs-lookup"><span data-stu-id="25caa-225">Group</span></span> |<span data-ttu-id="25caa-226">Nome dei criteri di chiamata dei team</span><span class="sxs-lookup"><span data-stu-id="25caa-226">Teams calling policy name</span></span>  |<span data-ttu-id="25caa-227">Rango</span><span class="sxs-lookup"><span data-stu-id="25caa-227">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="25caa-228">Responsabili dello Store</span><span class="sxs-lookup"><span data-stu-id="25caa-228">Store Managers</span></span>   |<span data-ttu-id="25caa-229">Criteri di chiamata per i responsabili dello Store</span><span class="sxs-lookup"><span data-stu-id="25caa-229">Store Managers Calling Policy</span></span>         |<span data-ttu-id="25caa-230">1</span><span class="sxs-lookup"><span data-stu-id="25caa-230">1</span></span>|
|<span data-ttu-id="25caa-231">Archiviare i dipendenti</span><span class="sxs-lookup"><span data-stu-id="25caa-231">Store Employees</span></span>    |<span data-ttu-id="25caa-232">Criteri di chiamata dei dipendenti dello Store</span><span class="sxs-lookup"><span data-stu-id="25caa-232">Store Employees Calling Policy</span></span>      |<span data-ttu-id="25caa-233">2</span><span class="sxs-lookup"><span data-stu-id="25caa-233">2</span></span>|

<span data-ttu-id="25caa-234">Se non specifichi una classificazione, all'assegnazione dei criteri viene assegnata la classificazione più bassa.</span><span class="sxs-lookup"><span data-stu-id="25caa-234">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span> 

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="25caa-235">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="25caa-235">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="25caa-236">Attualmente, l'assegnazione dei criteri ai gruppi che usano l'interfaccia di amministrazione di Microsoft teams è disponibile solo per i criteri di chiamata dei team, i criteri di parcheggio per i team, i criteri per i team, i criteri per le riunioni dei team e i criteri di messaggistica di team.</span><span class="sxs-lookup"><span data-stu-id="25caa-236">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="25caa-237">Per altri tipi di criteri, usare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25caa-237">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="25caa-238">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams passa alla pagina tipo di criteri.</span><span class="sxs-lookup"><span data-stu-id="25caa-238">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="25caa-239">Ad esempio, vai a **Meetings**  >  **criteri riunione** riunioni.</span><span class="sxs-lookup"><span data-stu-id="25caa-239">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="25caa-240">Selezionare la scheda **assegnazione criteri di gruppo** .</span><span class="sxs-lookup"><span data-stu-id="25caa-240">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="25caa-241">Selezionare **Aggiungi gruppo** e quindi nel riquadro **Assegna criteri a gruppo** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="25caa-241">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="25caa-242">Cercare e aggiungere il gruppo a cui si vuole assegnare il criterio.</span><span class="sxs-lookup"><span data-stu-id="25caa-242">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="25caa-243">Impostare la classificazione per l'assegnazione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="25caa-243">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="25caa-244">Selezionare il criterio che si vuole assegnare.</span><span class="sxs-lookup"><span data-stu-id="25caa-244">Select the policy that you want to assign.</span></span> 
    4. <span data-ttu-id="25caa-245">Selezionare **applica**.</span><span class="sxs-lookup"><span data-stu-id="25caa-245">Select **Apply**.</span></span>

<span data-ttu-id="25caa-246">Per rimuovere un'assegnazione di criteri di gruppo, nella scheda assegnazione criteri di **gruppo** della pagina Criteri selezionare l'assegnazione del gruppo e quindi scegliere **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="25caa-246">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="25caa-247">Per modificare la classificazione di un'assegnazione di gruppo, è necessario rimuovere prima di tutto l'assegnazione dei criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="25caa-247">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="25caa-248">Seguire quindi la procedura descritta in precedenza per assegnare i criteri a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="25caa-248">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="25caa-249">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="25caa-249">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="25caa-250">Attualmente, l'assegnazione dei criteri ai gruppi che usano PowerShell non è disponibile per tutti i tipi di criteri teams.</span><span class="sxs-lookup"><span data-stu-id="25caa-250">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="25caa-251">Vedere [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) per l'elenco dei tipi di criteri supportati.</span><span class="sxs-lookup"><span data-stu-id="25caa-251">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="25caa-252">Installare e connettersi al modulo di PowerShell di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="25caa-252">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="25caa-253">Per informazioni dettagliate, vedere [installare teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="25caa-253">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="25caa-254">Assegnare un criterio a un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="25caa-254">Assign a policy to a group of users</span></span>

<span data-ttu-id="25caa-255">Puoi usare il cmdlet [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) per assegnare un criterio a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="25caa-255">You use the [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="25caa-256">Puoi specificare un gruppo usando l'ID oggetto, l'indirizzo SIP o l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="25caa-256">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="25caa-257">In questo esempio, assegniamo un criterio riunione teams denominato criteri di riunione per i responsabili delle riunioni a un gruppo con una classificazione di assegnazione di 1.</span><span class="sxs-lookup"><span data-stu-id="25caa-257">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="25caa-258">Ottenere le assegnazioni dei criteri per un gruppo</span><span class="sxs-lookup"><span data-stu-id="25caa-258">Get policy assignments for a group</span></span>

<span data-ttu-id="25caa-259">Usa il cmdlet [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) per ottenere tutti i criteri assegnati a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="25caa-259">Use the [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="25caa-260">Tieni presente che i gruppi sono sempre elencati dall'ID del gruppo, anche se l'indirizzo SIP o l'indirizzo di posta elettronica è stato usato per assegnare il criterio.</span><span class="sxs-lookup"><span data-stu-id="25caa-260">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="25caa-261">In questo esempio recuperiamo tutti i criteri assegnati a un gruppo specifico.</span><span class="sxs-lookup"><span data-stu-id="25caa-261">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="25caa-262">In questo esempio vengono restituiti tutti i gruppi a cui è stato assegnato un criterio di riunione teams.</span><span class="sxs-lookup"><span data-stu-id="25caa-262">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="25caa-263">Rimuovere un criterio da un gruppo</span><span class="sxs-lookup"><span data-stu-id="25caa-263">Remove a policy from a group</span></span>

<span data-ttu-id="25caa-264">Utilizzare il cmdlet [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) per rimuovere un criterio da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="25caa-264">Use the [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="25caa-265">Quando si rimuove un criterio da un gruppo, vengono aggiornate le priorità di altri criteri dello stesso tipo assegnati al gruppo e con una classificazione inferiore.</span><span class="sxs-lookup"><span data-stu-id="25caa-265">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="25caa-266">Se ad esempio si rimuove un criterio con una classificazione 2, i criteri che hanno una classificazione 3 e 4 vengono aggiornati per riflettere la nuova classificazione.</span><span class="sxs-lookup"><span data-stu-id="25caa-266">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="25caa-267">Le due tabelle seguenti mostrano questo esempio.</span><span class="sxs-lookup"><span data-stu-id="25caa-267">The following two tables show this example.</span></span>

<span data-ttu-id="25caa-268">Ecco un elenco delle assegnazioni dei criteri e delle priorità per i criteri di riunione di teams.</span><span class="sxs-lookup"><span data-stu-id="25caa-268">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="25caa-269">Nome gruppo</span><span class="sxs-lookup"><span data-stu-id="25caa-269">Group name</span></span>  |<span data-ttu-id="25caa-270">Nome del criterio</span><span class="sxs-lookup"><span data-stu-id="25caa-270">Policy name</span></span>  |<span data-ttu-id="25caa-271">Rango</span><span class="sxs-lookup"><span data-stu-id="25caa-271">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="25caa-272">Vendite</span><span class="sxs-lookup"><span data-stu-id="25caa-272">Sales</span></span>    |<span data-ttu-id="25caa-273">Criteri di vendita</span><span class="sxs-lookup"><span data-stu-id="25caa-273">Sales policy</span></span>       | <span data-ttu-id="25caa-274">1</span><span class="sxs-lookup"><span data-stu-id="25caa-274">1</span></span>        |
|<span data-ttu-id="25caa-275">Regione occidentale</span><span class="sxs-lookup"><span data-stu-id="25caa-275">West Region</span></span>     |<span data-ttu-id="25caa-276">Criteri per la regione occidentale</span><span class="sxs-lookup"><span data-stu-id="25caa-276">West Region policy</span></span>         |<span data-ttu-id="25caa-277">2</span><span class="sxs-lookup"><span data-stu-id="25caa-277">2</span></span>         |
|<span data-ttu-id="25caa-278">Divisione</span><span class="sxs-lookup"><span data-stu-id="25caa-278">Division</span></span>    |<span data-ttu-id="25caa-279">Criteri di divisione</span><span class="sxs-lookup"><span data-stu-id="25caa-279">Division policy</span></span>         |<span data-ttu-id="25caa-280">3</span><span class="sxs-lookup"><span data-stu-id="25caa-280">3</span></span>         |
|<span data-ttu-id="25caa-281">Filiale nel</span><span class="sxs-lookup"><span data-stu-id="25caa-281">Subsidiary</span></span>   |<span data-ttu-id="25caa-282">Criteri sussidiari</span><span class="sxs-lookup"><span data-stu-id="25caa-282">Subsidiary policy</span></span>        |<span data-ttu-id="25caa-283">4</span><span class="sxs-lookup"><span data-stu-id="25caa-283">4</span></span>         |

<span data-ttu-id="25caa-284">Se rimuoviamo i criteri per l'area ovest dal gruppo area occidentale, le assegnazioni dei criteri e le priorità vengono aggiornate come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="25caa-284">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="25caa-285">Nome gruppo</span><span class="sxs-lookup"><span data-stu-id="25caa-285">Group name</span></span>  |<span data-ttu-id="25caa-286">Nome del criterio</span><span class="sxs-lookup"><span data-stu-id="25caa-286">Policy name</span></span>  |<span data-ttu-id="25caa-287">Rango</span><span class="sxs-lookup"><span data-stu-id="25caa-287">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="25caa-288">Vendite</span><span class="sxs-lookup"><span data-stu-id="25caa-288">Sales</span></span>    |<span data-ttu-id="25caa-289">Criteri di vendita</span><span class="sxs-lookup"><span data-stu-id="25caa-289">Sales policy</span></span>       | <span data-ttu-id="25caa-290">1</span><span class="sxs-lookup"><span data-stu-id="25caa-290">1</span></span>        |
|<span data-ttu-id="25caa-291">Divisione</span><span class="sxs-lookup"><span data-stu-id="25caa-291">Division</span></span>    |<span data-ttu-id="25caa-292">Criteri di divisione</span><span class="sxs-lookup"><span data-stu-id="25caa-292">Division policy</span></span>         |<span data-ttu-id="25caa-293">2</span><span class="sxs-lookup"><span data-stu-id="25caa-293">2</span></span>         |
|<span data-ttu-id="25caa-294">Filiale nel</span><span class="sxs-lookup"><span data-stu-id="25caa-294">Subsidiary</span></span>   |<span data-ttu-id="25caa-295">Criteri sussidiari</span><span class="sxs-lookup"><span data-stu-id="25caa-295">Subsidiary policy</span></span>        |<span data-ttu-id="25caa-296">3</span><span class="sxs-lookup"><span data-stu-id="25caa-296">3</span></span>        |

<span data-ttu-id="25caa-297">In questo esempio rimuoviamo i criteri riunione Teams da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="25caa-297">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="25caa-298">Modificare un'assegnazione di criteri per un gruppo</span><span class="sxs-lookup"><span data-stu-id="25caa-298">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="25caa-299">Il cmdlet [set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) sarà disponibile a breve.</span><span class="sxs-lookup"><span data-stu-id="25caa-299">The [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="25caa-300">Nel frattempo, per modificare un'assegnazione di criteri di gruppo, è possibile rimuovere l'assegnazione di criteri corrente dal gruppo e quindi aggiungere una nuova assegnazione di criteri.</span><span class="sxs-lookup"><span data-stu-id="25caa-300">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="25caa-301">Dopo aver assegnato un criterio a un gruppo, è possibile usare il cmdlet [set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) per modificare l'assegnazione dei criteri del gruppo come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="25caa-301">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="25caa-302">Modificare la classificazione</span><span class="sxs-lookup"><span data-stu-id="25caa-302">Change the ranking</span></span>
- <span data-ttu-id="25caa-303">Modificare i criteri di un tipo di criterio specifico</span><span class="sxs-lookup"><span data-stu-id="25caa-303">Change the policy of a given policy type</span></span>
- <span data-ttu-id="25caa-304">Modificare i criteri di un tipo di criteri specifico e la classificazione</span><span class="sxs-lookup"><span data-stu-id="25caa-304">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="25caa-305">In questo esempio modifichiamo i criteri di parcheggio per le chiamate di team di un gruppo in un criterio denominato SupportCallPark e la classificazione delle assegnazioni su 3.</span><span class="sxs-lookup"><span data-stu-id="25caa-305">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="25caa-306">Modificare i criteri effettivi per un utente</span><span class="sxs-lookup"><span data-stu-id="25caa-306">Change the effective policy for a user</span></span>

<span data-ttu-id="25caa-307">Ecco un esempio di come modificare i criteri effettivi per un utente a cui è assegnato direttamente un criterio.</span><span class="sxs-lookup"><span data-stu-id="25caa-307">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="25caa-308">Prima di tutto, usiamo il cmdlet [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) insieme al ```PolicySource``` parametro per ottenere informazioni dettagliate sui criteri di trasmissione delle riunioni dei team associati all'utente.</span><span class="sxs-lookup"><span data-stu-id="25caa-308">First, we use the [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> 

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="25caa-309">Nell'output viene indicato che all'utente sono stati assegnati direttamente i criteri di riunione per le riunioni di teams denominati eventi dei dipendenti, che hanno la precedenza sui criteri denominati fornitori di eventi live assegnati a un gruppo a cui appartiene l'utente.</span><span class="sxs-lookup"><span data-stu-id="25caa-309">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="25caa-310">Ora rimuoviamo i criteri degli eventi dei dipendenti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="25caa-310">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="25caa-311">Ciò significa che l'utente non ha più un criterio di riunione delle riunioni di teams direttamente assegnato e erediterà i criteri degli eventi live del fornitore assegnati al gruppo a cui appartiene l'utente.</span><span class="sxs-lookup"><span data-stu-id="25caa-311">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="25caa-312">Per eseguire questa operazione, usare il cmdlet seguente nel modulo di PowerShell per Skype for business.</span><span class="sxs-lookup"><span data-stu-id="25caa-312">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="25caa-313">È possibile usare i cmdlet seguenti nel modulo di PowerShell teams per eseguire questa operazione in scala anche se un'assegnazione di criteri batch, dove $users è un elenco di utenti specificati.</span><span class="sxs-lookup"><span data-stu-id="25caa-313">You can use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="25caa-314">Assegnare un criterio a un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="25caa-314">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="25caa-315">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="25caa-315">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="25caa-316">Per assegnare un criterio agli utenti in blocco:</span><span class="sxs-lookup"><span data-stu-id="25caa-316">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="25caa-317">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare **utenti**.</span><span class="sxs-lookup"><span data-stu-id="25caa-317">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="25caa-318">Cercare gli utenti a cui assegnare il criterio o filtrare la visualizzazione per mostrare gli utenti desiderati.</span><span class="sxs-lookup"><span data-stu-id="25caa-318">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="25caa-319">Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="25caa-319">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="25caa-320">Per selezionare tutti gli utenti, fare clic sul &#x2713; (segno di spunta) nella parte superiore della tabella.</span><span class="sxs-lookup"><span data-stu-id="25caa-320">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="25caa-321">Fare clic su **Modifica impostazioni**, apportare le modifiche desiderate e quindi fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="25caa-321">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="25caa-322">Per visualizzare lo stato dell'assegnazione dei criteri, nell'intestazione visualizzata nella parte superiore della pagina **utenti** dopo aver fatto clic su **applica** per inviare l'assegnazione di criteri, fare clic su **Registro attività**.</span><span class="sxs-lookup"><span data-stu-id="25caa-322">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="25caa-323">Oppure, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **Dashboard** e quindi in **Registro attività** fare clic su **Visualizza dettagli**.</span><span class="sxs-lookup"><span data-stu-id="25caa-323">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="25caa-324">Il registro attività Mostra le assegnazioni dei criteri ai batch di più di 20 utenti tramite l'interfaccia di amministrazione di Microsoft teams degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="25caa-324">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="25caa-325">Per altre informazioni, vedere [visualizzare le assegnazioni dei criteri nel registro attività](activity-log.md).</span><span class="sxs-lookup"><span data-stu-id="25caa-325">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="25caa-326">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="25caa-326">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="25caa-327">Attualmente, l'assegnazione di criteri batch con PowerShell non è disponibile per tutti i tipi di criteri teams.</span><span class="sxs-lookup"><span data-stu-id="25caa-327">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="25caa-328">Vedere [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) per l'elenco dei tipi di criteri supportati.</span><span class="sxs-lookup"><span data-stu-id="25caa-328">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>
 
<span data-ttu-id="25caa-329">Con l'assegnazione di criteri batch è possibile assegnare un criterio a set di utenti di grandi dimensioni alla volta senza dover usare uno script.</span><span class="sxs-lookup"><span data-stu-id="25caa-329">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="25caa-330">Puoi usare il cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) per inviare un batch di utenti e i criteri che vuoi assegnare.</span><span class="sxs-lookup"><span data-stu-id="25caa-330">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="25caa-331">Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch.</span><span class="sxs-lookup"><span data-stu-id="25caa-331">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="25caa-332">Puoi quindi usare il cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) per tenere traccia dello stato di avanzamento e dello stato delle assegnazioni in un batch.</span><span class="sxs-lookup"><span data-stu-id="25caa-332">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="25caa-333">Puoi specificare gli utenti in base al loro ID oggetto o all'indirizzo SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="25caa-333">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="25caa-334">Tieni presente che l'indirizzo SIP di un utente ha spesso lo stesso valore del nome dell'entità utente (UPN) o dell'indirizzo di posta elettronica, ma non è necessario.</span><span class="sxs-lookup"><span data-stu-id="25caa-334">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="25caa-335">Se un utente viene specificato con il proprio UPN o tramite posta elettronica, ma ha un valore diverso rispetto all'indirizzo SIP, l'assegnazione dei criteri non riesce per l'utente.</span><span class="sxs-lookup"><span data-stu-id="25caa-335">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="25caa-336">Se un batch include utenti duplicati, i duplicati verranno rimossi dal batch prima che l'elaborazione e lo stato vengano forniti solo per gli utenti univoci rimasti nel batch.</span><span class="sxs-lookup"><span data-stu-id="25caa-336">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="25caa-337">Un batch può contenere fino a 5.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="25caa-337">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="25caa-338">Per ottenere risultati ottimali, non inviare più di alcuni batch alla volta.</span><span class="sxs-lookup"><span data-stu-id="25caa-338">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="25caa-339">Consentire ai batch di completare l'elaborazione prima di inviare più batch.</span><span class="sxs-lookup"><span data-stu-id="25caa-339">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="25caa-340">Installare e connettersi al modulo di PowerShell di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="25caa-340">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="25caa-341">Eseguire la procedura seguente per installare il [modulo di PowerShell per Microsoft teams](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="25caa-341">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="25caa-342">Assicurarsi di installare la versione 1.0.5 o successiva.</span><span class="sxs-lookup"><span data-stu-id="25caa-342">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="25caa-343">Eseguire le operazioni seguenti per connettersi ai team e avviare una sessione.</span><span class="sxs-lookup"><span data-stu-id="25caa-343">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="25caa-344">Quando viene richiesto, accedere con le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="25caa-344">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="25caa-345">Installare e connettersi a Azure AD PowerShell per modulo grafico (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="25caa-345">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="25caa-346">Puoi anche [scaricare e installare Azure ad PowerShell per il modulo grafico](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (se non lo hai già fatto) e connetterti AD Azure ad in modo da poter recuperare un elenco di utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="25caa-346">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="25caa-347">Eseguire la procedura seguente per connettersi ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="25caa-347">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="25caa-348">Quando viene richiesto, accedere con le stesse credenziali di amministratore usate per connettersi ai team.</span><span class="sxs-lookup"><span data-stu-id="25caa-348">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="25caa-349">Assegnare un criterio a un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="25caa-349">Assign a policy to a batch of users</span></span>

<span data-ttu-id="25caa-350">In questo esempio usiamo il cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) per assegnare un criterio di configurazione dell'app denominato criteri di configurazione dell'app HR a un batch di utenti elencati nel file Users_ids. Text.</span><span class="sxs-lookup"><span data-stu-id="25caa-350">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="25caa-351">In questo esempio, ci connettiamo ad Azure AD per recuperare una raccolta di utenti e quindi assegnare un criterio di messaggistica denominato nuovi criteri di messaggistica di noleggio a un batch di utenti specificato tramite l'indirizzo SIP.</span><span class="sxs-lookup"><span data-stu-id="25caa-351">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="25caa-352">Ottenere lo stato di un'assegnazione batch</span><span class="sxs-lookup"><span data-stu-id="25caa-352">Get the status of a batch assignment</span></span>

<span data-ttu-id="25caa-353">Eseguire la procedura seguente per ottenere lo stato di un'assegnazione batch, dove OperationId è l'ID operazione restituito dal ```New-CsBatchPolicyAssignmentOperation``` cmdlet per un batch specifico.</span><span class="sxs-lookup"><span data-stu-id="25caa-353">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="25caa-354">Se l'output indica che si è verificato un errore, eseguire la procedura seguente per ottenere altre informazioni sugli errori, che si trovano nella ```UserState``` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="25caa-354">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="25caa-355">Per altre informazioni, vedere [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="25caa-355">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="25caa-356">Assegnare un pacchetto di criteri agli utenti</span><span class="sxs-lookup"><span data-stu-id="25caa-356">Assign a policy package to users</span></span>

<span data-ttu-id="25caa-357">Un pacchetto di criteri in teams è una raccolta di criteri predefiniti e di impostazioni dei criteri che è possibile assegnare agli utenti che hanno ruoli uguali o simili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="25caa-357">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="25caa-358">Ogni pacchetto di criteri è progettato intorno a un ruolo utente e include criteri predefiniti e impostazioni dei criteri che supportano le attività tipiche di tale ruolo.</span><span class="sxs-lookup"><span data-stu-id="25caa-358">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="25caa-359">Alcuni esempi di pacchetti di criteri sono il pacchetto Education (Teacher) e il pacchetto Healthcare (Worker clinico).</span><span class="sxs-lookup"><span data-stu-id="25caa-359">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="25caa-360">Per altre informazioni, vedere [gestire i pacchetti di criteri in teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="25caa-360">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="25caa-361">Assegnare un pacchetto di criteri a un utente</span><span class="sxs-lookup"><span data-stu-id="25caa-361">Assign a policy package to one user</span></span>

1. <span data-ttu-id="25caa-362">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.</span><span class="sxs-lookup"><span data-stu-id="25caa-362">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="25caa-363">Nella pagina dell'utente fare clic su **criteri** e quindi fare clic su **modifica** accanto a **pacchetto criteri**.</span><span class="sxs-lookup"><span data-stu-id="25caa-363">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="25caa-364">Nel riquadro **Assegna criteri del pacchetto** selezionare il pacchetto da assegnare e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="25caa-364">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="25caa-365">Assegnare un pacchetto di criteri a più utenti</span><span class="sxs-lookup"><span data-stu-id="25caa-365">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="25caa-366">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **pacchetti di criteri** e quindi seleziona il pacchetto di criteri da assegnare facendo clic a sinistra del nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="25caa-366">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="25caa-367">Fare clic su **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="25caa-367">Click **Manage users**.</span></span>
3. <span data-ttu-id="25caa-368">Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="25caa-368">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="25caa-369">Ripetere questa operazione per ogni utente da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="25caa-369">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="25caa-370">Al termine dell'aggiunta di utenti, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="25caa-370">When you're finished adding users, click **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="25caa-371">Assegnare un pacchetto di criteri a un gruppo</span><span class="sxs-lookup"><span data-stu-id="25caa-371">Assign a policy package to a group</span></span>

<span data-ttu-id="25caa-372">**Questa funzionalità è in anteprima privata**</span><span class="sxs-lookup"><span data-stu-id="25caa-372">**This feature is in private preview**</span></span>

<span data-ttu-id="25caa-373">L'assegnazione di pacchetti di criteri ai gruppi consente di assegnare più criteri a un gruppo di utenti, ad esempio un gruppo di sicurezza o una lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="25caa-373">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="25caa-374">L'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza.</span><span class="sxs-lookup"><span data-stu-id="25caa-374">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="25caa-375">Quando vengono aggiunti o rimossi membri da un gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="25caa-375">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="25caa-376">L'assegnazione dei pacchetti di criteri ai gruppi è consigliata per i gruppi di utenti fino a 50.000, ma funziona anche con i gruppi più grandi.</span><span class="sxs-lookup"><span data-stu-id="25caa-376">Policy package assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span> 

<span data-ttu-id="25caa-377">Quando si assegna il pacchetto di criteri, viene immediatamente assegnato al gruppo.</span><span class="sxs-lookup"><span data-stu-id="25caa-377">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="25caa-378">Si noti tuttavia che la propagazione dell'assegnazione dei criteri ai membri del gruppo viene eseguita come operazione in background e può richiedere del tempo, a seconda delle dimensioni del gruppo.</span><span class="sxs-lookup"><span data-stu-id="25caa-378">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="25caa-379">Lo stesso vale quando un criterio non viene assegnato da un gruppo o quando i membri vengono aggiunti o rimossi da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="25caa-379">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="25caa-380">Prima di iniziare, è importante comprendere [le regole di precedenza](#precedence-rules) e la [classificazione delle assegnazioni di gruppo](#group-assignment-ranking).</span><span class="sxs-lookup"><span data-stu-id="25caa-380">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="25caa-381">Verificare di aver letto e compreso i concetti [che occorre sapere sull'assegnazione dei criteri ai gruppi](#what-you-need-to-know-about-policy-assignment-to-groups) precedenti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="25caa-381">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="using-the-microsoft-teams-admin-center-coming-soon"></a><span data-ttu-id="25caa-382">Uso dell'interfaccia di amministrazione di Microsoft Teams (disponibile a breve)</span><span class="sxs-lookup"><span data-stu-id="25caa-382">Using the Microsoft Teams admin center (coming soon)</span></span>

<span data-ttu-id="25caa-383">L'assegnazione dei pacchetti di criteri ai gruppi nell'interfaccia di amministrazione di Microsoft teams sarà disponibile a breve.</span><span class="sxs-lookup"><span data-stu-id="25caa-383">Policy package assignment to groups in the Microsoft Teams admin center is coming soon.</span></span> <span data-ttu-id="25caa-384">Verificare di nuovo gli aggiornamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="25caa-384">Check back here for the latest updates.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="25caa-385">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="25caa-385">Using PowerShell</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="25caa-386">Installare e connettersi al modulo di PowerShell di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="25caa-386">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="25caa-387">Per informazioni dettagliate, vedere [installare teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="25caa-387">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="25caa-388">Assegnare un pacchetto di criteri a un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="25caa-388">Assign a policy package to a group of users</span></span>

<span data-ttu-id="25caa-389">Puoi usare il cmdlet [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) per assegnare un pacchetto di criteri a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="25caa-389">You use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="25caa-390">Puoi specificare un gruppo usando l'ID oggetto, l'indirizzo SIP o l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="25caa-390">You can specify a group by using the object Id, SIP address, or email address.</span></span> <span data-ttu-id="25caa-391">Quando si assegna il pacchetto di criteri, specificare una [classificazione delle assegnazioni di gruppo](#group-assignment-ranking) per ogni tipo di criterio nel pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="25caa-391">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span> 

<span data-ttu-id="25caa-392">In questo esempio assegniamo il pacchetto di criteri di Education_Teacher a un gruppo con una classificazione delle assegnazioni di 1 per TeamsAppSetupPolicy e TeamsMeetingBroadcastPolicy e una classificazione di 2 per TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="25caa-392">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="25caa-393">Assegnare un pacchetto di criteri a un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="25caa-393">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="25caa-394">Con l'assegnazione di un pacchetto di criteri batch, puoi assegnare un pacchetto di criteri a set di grandi dimensioni di utenti alla volta senza dover usare uno script.</span><span class="sxs-lookup"><span data-stu-id="25caa-394">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="25caa-395">Si usa il cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) per inviare un batch di utenti e il pacchetto di criteri che si vuole assegnare.</span><span class="sxs-lookup"><span data-stu-id="25caa-395">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="25caa-396">Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch.</span><span class="sxs-lookup"><span data-stu-id="25caa-396">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="25caa-397">Puoi quindi usare il cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) per tenere traccia dello stato di avanzamento e dello stato delle assegnazioni in un batch.</span><span class="sxs-lookup"><span data-stu-id="25caa-397">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="25caa-398">Puoi specificare gli utenti in base al loro ID oggetto o all'indirizzo SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="25caa-398">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="25caa-399">Tieni presente che l'indirizzo SIP di un utente ha spesso lo stesso valore del nome dell'entità utente (UPN) o dell'indirizzo di posta elettronica, ma non è necessario.</span><span class="sxs-lookup"><span data-stu-id="25caa-399">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="25caa-400">Se un utente viene specificato con il proprio UPN o tramite posta elettronica, ma ha un valore diverso rispetto all'indirizzo SIP, l'assegnazione dei criteri non riesce per l'utente.</span><span class="sxs-lookup"><span data-stu-id="25caa-400">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="25caa-401">Se un batch include utenti duplicati, i duplicati verranno rimossi dal batch prima che l'elaborazione e lo stato vengano forniti solo per gli utenti univoci rimasti nel batch.</span><span class="sxs-lookup"><span data-stu-id="25caa-401">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="25caa-402">Un batch può contenere fino a 5.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="25caa-402">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="25caa-403">Per ottenere risultati ottimali, non inviare più di alcuni batch alla volta.</span><span class="sxs-lookup"><span data-stu-id="25caa-403">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="25caa-404">Consentire ai batch di completare l'elaborazione prima di inviare più batch.</span><span class="sxs-lookup"><span data-stu-id="25caa-404">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="25caa-405">Installare e connettersi al modulo di PowerShell di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="25caa-405">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="25caa-406">Eseguire la procedura seguente per installare il [modulo di PowerShell di Microsoft teams](https://www.powershellgallery.com/packages/MicrosoftTeams) (se non è già stato fatto).</span><span class="sxs-lookup"><span data-stu-id="25caa-406">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="25caa-407">Assicurarsi di installare la versione 1.0.5 o successiva.</span><span class="sxs-lookup"><span data-stu-id="25caa-407">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="25caa-408">Eseguire le operazioni seguenti per connettersi ai team e avviare una sessione.</span><span class="sxs-lookup"><span data-stu-id="25caa-408">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="25caa-409">Quando viene richiesto, accedere con le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="25caa-409">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="25caa-410">Assegnare un pacchetto di criteri a un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="25caa-410">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="25caa-411">In questo esempio usiamo il cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) per assegnare il pacchetto di criteri Education_PrimaryStudent a un batch di utenti.</span><span class="sxs-lookup"><span data-stu-id="25caa-411">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="25caa-412">Ottenere lo stato di un'assegnazione batch</span><span class="sxs-lookup"><span data-stu-id="25caa-412">Get the status of a batch assignment</span></span>

<span data-ttu-id="25caa-413">Eseguire la procedura seguente per ottenere lo stato di un'assegnazione batch, dove OperationId è l'ID operazione restituito dal ```New-CsBatchPolicyAssignmentOperation``` cmdlet per un batch specifico.</span><span class="sxs-lookup"><span data-stu-id="25caa-413">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="25caa-414">Se l'output indica che si è verificato un errore, eseguire la procedura seguente per ottenere altre informazioni sugli errori, che si trovano nella ```UserState``` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="25caa-414">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="25caa-415">Per altre informazioni, vedere [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="25caa-415">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="25caa-416">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="25caa-416">Related topics</span></span>

[<span data-ttu-id="25caa-417">Panoramica di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="25caa-417">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
