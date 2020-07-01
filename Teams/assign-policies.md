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
ms.openlocfilehash: 403131fa3e7bd2b3fb2a128640ac49497394d669
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938545"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="861c0-103">Assegnare i criteri agli utenti in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="861c0-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="861c0-104">**Tenere presente quanto segue su una delle caratteristiche descritte in questo articolo, assegnazione dei criteri a gruppi**:</span><span class="sxs-lookup"><span data-stu-id="861c0-104">**Note the following about one of the features discussed in this article, policy assignment to groups**:</span></span> 
> - <span data-ttu-id="861c0-105">[L'assegnazione dei criteri a gruppi che usano l'interfaccia di amministrazione di Microsoft teams](#using-the-microsoft-teams-admin-center-3)non è ancora stata rilasciata.</span><span class="sxs-lookup"><span data-stu-id="861c0-105">[Policy assignment to groups using the Microsoft Teams admin center](#using-the-microsoft-teams-admin-center-3), hasn't yet been released.</span></span> <span data-ttu-id="861c0-106">È stata annunciata e arriverà presto.</span><span class="sxs-lookup"><span data-stu-id="861c0-106">It's been announced, and it's coming soon.</span></span> 
> - <span data-ttu-id="861c0-107">L' [assegnazione dei criteri ai gruppi tramite PowerShell](#using-powershell-3)è attualmente disponibile solo in anteprima privata.</span><span class="sxs-lookup"><span data-stu-id="861c0-107">[Policy assignment to groups using PowerShell](#using-powershell-3), is currently only available in private preview.</span></span> <span data-ttu-id="861c0-108">I cmdlet di PowerShell per questa funzionalità si trovano nel modulo di PowerShell per i team pre-release.</span><span class="sxs-lookup"><span data-stu-id="861c0-108">The Powershell cmdlets for this feature are in the pre-release Teams PowerShell module.</span></span>
>
> <span data-ttu-id="861c0-109">Per rimanere in primo piano sullo stato di rilascio di questa funzionalità, vedere la [Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span><span class="sxs-lookup"><span data-stu-id="861c0-109">To stay on top of the release status of this feature, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span></span>

<span data-ttu-id="861c0-110">Come amministratore, puoi usare i criteri per controllare le caratteristiche dei team disponibili per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="861c0-110">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="861c0-111">Ad esempio, esistono criteri per la chiamata, criteri per le riunioni e criteri di messaggistica, per citarne solo alcuni.</span><span class="sxs-lookup"><span data-stu-id="861c0-111">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="861c0-112">Le organizzazioni hanno diversi tipi di utenti con esigenze esclusive e criteri personalizzati creati e assegnati consentono di adattare le impostazioni dei criteri a diversi set di utenti in base a tali esigenze.</span><span class="sxs-lookup"><span data-stu-id="861c0-112">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="861c0-113">Per semplificare la gestione dei criteri nell'organizzazione, teams offre diversi modi per assegnare i criteri agli utenti.</span><span class="sxs-lookup"><span data-stu-id="861c0-113">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="861c0-114">È possibile assegnare un criterio direttamente agli utenti, singolarmente o in scala, tramite un'assegnazione batch o a un gruppo di cui fanno parte gli utenti.</span><span class="sxs-lookup"><span data-stu-id="861c0-114">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="861c0-115">Puoi anche usare i pacchetti di criteri per assegnare una raccolta preimpostata di criteri agli utenti dell'organizzazione che hanno ruoli simili.</span><span class="sxs-lookup"><span data-stu-id="861c0-115">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="861c0-116">L'opzione scelta dipende dal numero di criteri che si stanno gestendo e dal numero di utenti a cui si sta assegnando.</span><span class="sxs-lookup"><span data-stu-id="861c0-116">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="861c0-117">Impostando i criteri globali (a livello di organizzazione) in modo che vengano applicati al numero maggiore di utenti dell'organizzazione, è necessario assegnare i criteri solo agli utenti che richiedono criteri specializzati.</span><span class="sxs-lookup"><span data-stu-id="861c0-117">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="861c0-118">In questo articolo vengono illustrati i diversi modi in cui è possibile assegnare i criteri agli utenti e gli scenari consigliati per quando usare cosa.</span><span class="sxs-lookup"><span data-stu-id="861c0-118">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="861c0-119">Quali criteri hanno la precedenza?</span><span class="sxs-lookup"><span data-stu-id="861c0-119">Which policy takes precedence?</span></span>

<span data-ttu-id="861c0-120">Un utente ha un criterio effettivo per ogni tipo di criterio.</span><span class="sxs-lookup"><span data-stu-id="861c0-120">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="861c0-121">È possibile o anche probabile che a un utente venga assegnato direttamente un criterio ed è anche membro di uno o più gruppi a cui è assegnato un criterio dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="861c0-121">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="861c0-122">In questi tipi di scenari, quali criteri hanno la precedenza?</span><span class="sxs-lookup"><span data-stu-id="861c0-122">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="861c0-123">I criteri effettivi di un utente vengono determinati in base alle regole di precedenza, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="861c0-123">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="861c0-124">Se a un utente viene assegnato direttamente un criterio (individualmente o tramite un'assegnazione batch), tale criterio avrà la precedenza.</span><span class="sxs-lookup"><span data-stu-id="861c0-124">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="861c0-125">Nell'esempio seguente, il criterio effettivo dell'utente è il criterio riunione di Lincoln Square, che viene direttamente assegnato all'utente.</span><span class="sxs-lookup"><span data-stu-id="861c0-125">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagramma che mostra il modo in cui un criterio assegnato direttamente ha la precedenza](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="861c0-127">Se un utente non viene assegnato direttamente a un criterio di un tipo specificato, il criterio assegnato a un gruppo di cui l'utente è membro ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="861c0-127">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="861c0-128">Se un utente è un membro di più gruppi, il criterio con la classificazione delle [assegnazioni di gruppo](#group-assignment-ranking) più alta per il tipo di criteri specifico ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="861c0-128">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="861c0-129">In questo esempio, i criteri effettivi dell'utente sono i team Exec e i criteri HD, che hanno il ranking di assegnazione più alto rispetto ad altri gruppi a cui l'utente fa parte e a cui sono assegnati anche i criteri dello stesso tipo di criteri.</span><span class="sxs-lookup"><span data-stu-id="861c0-129">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagramma che mostra il modo in cui un criterio ereditato dal gruppo ha la precedenza](media/assign-policies-example-group.png)

<span data-ttu-id="861c0-131">Se a un utente non viene assegnato un criterio o non è un membro di un gruppo a cui è assegnato un criterio, l'utente otterrà il criterio globale (a livello di organizzazione) per il tipo di criteri.</span><span class="sxs-lookup"><span data-stu-id="861c0-131">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="861c0-132">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="861c0-132">Here's an example.</span></span>

![Diagramma che mostra il modo in cui prevale un criterio globale](media/assign-policies-example-global.png)

<span data-ttu-id="861c0-134">Per altre informazioni, Vedi [regole di precedenza](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="861c0-134">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="861c0-135">Modalità di assegnazione di criteri</span><span class="sxs-lookup"><span data-stu-id="861c0-135">Ways to assign policies</span></span>

<span data-ttu-id="861c0-136">Ecco una panoramica dei modi in cui è possibile assegnare i criteri agli utenti e gli scenari consigliati per ognuno.</span><span class="sxs-lookup"><span data-stu-id="861c0-136">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="861c0-137">Fare clic sui collegamenti per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="861c0-137">Click the links to learn more.</span></span>

<span data-ttu-id="861c0-138">Prima di assegnare criteri a singoli utenti o gruppi, iniziare [impostando i criteri globali (org-Wide default)](#set-the-global-policies) in modo che vengano applicati al numero maggiore di utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="861c0-138">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="861c0-139">Una volta impostati i criteri globali, sarà necessario assegnare i criteri solo agli utenti che richiedono criteri specializzati.</span><span class="sxs-lookup"><span data-stu-id="861c0-139">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="861c0-140">Operazione da eseguire</span><span class="sxs-lookup"><span data-stu-id="861c0-140">Do this</span></span>  |<span data-ttu-id="861c0-141">Se...</span><span class="sxs-lookup"><span data-stu-id="861c0-141">If...</span></span>  | <span data-ttu-id="861c0-142">Uso di...</span><span class="sxs-lookup"><span data-stu-id="861c0-142">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="861c0-143">Assegnare un criterio a singoli utenti</span><span class="sxs-lookup"><span data-stu-id="861c0-143">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="861c0-144">Si è nuovi team e si è appena iniziato o si deve solo assegnare uno o due criteri a un numero limitato di utenti.</span><span class="sxs-lookup"><span data-stu-id="861c0-144">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="861c0-145">L'interfaccia di amministrazione di Microsoft teams o i cmdlet di PowerShell nel modulo di PowerShell Skype for business online</span><span class="sxs-lookup"><span data-stu-id="861c0-145">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="861c0-146">Assegnare un pacchetto di criteri</span><span class="sxs-lookup"><span data-stu-id="861c0-146">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="861c0-147">È necessario assegnare più criteri a specifici set di utenti dell'organizzazione che hanno ruoli uguali o simili.</span><span class="sxs-lookup"><span data-stu-id="861c0-147">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="861c0-148">Ad esempio, assegnare il pacchetto di criteri Education (Teacher) agli insegnanti della scuola per consentire loro l'accesso completo alle chat, alle chiamate e alle riunioni e al pacchetto di criteri per l'istruzione (studente della scuola secondaria) agli studenti secondari per limitare alcune funzionalità come le chiamate private.</span><span class="sxs-lookup"><span data-stu-id="861c0-148">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="861c0-149">Interfaccia di amministrazione di Microsoft teams o cmdlet di PowerShell nel modulo di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="861c0-149">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="861c0-150">Assegnare un criterio a un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="861c0-150">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="861c0-151">È necessario assegnare criteri a set di utenti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="861c0-151">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="861c0-152">Ad esempio, si vuole assegnare un criterio a centinaia o migliaia di utenti dell'organizzazione alla volta.</span><span class="sxs-lookup"><span data-stu-id="861c0-152">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="861c0-153">Interfaccia di amministrazione di Microsoft teams o cmdlet di PowerShell nel modulo di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="861c0-153">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="861c0-154">[Assegnare un criterio a un gruppo](#assign-a-policy-to-a-group) (in anteprima/presto disponibile)</span><span class="sxs-lookup"><span data-stu-id="861c0-154">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview/coming soon)</span></span>|<span data-ttu-id="861c0-155">È necessario assegnare criteri in base all'appartenenza al gruppo di un utente.</span><span class="sxs-lookup"><span data-stu-id="861c0-155">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="861c0-156">Ad esempio, si vuole assegnare un criterio a tutti gli utenti in un gruppo di sicurezza o in un'unità organizzativa.</span><span class="sxs-lookup"><span data-stu-id="861c0-156">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="861c0-157">Interfaccia di amministrazione di Microsoft Teams (disponibile a breve) o cmdlet di PowerShell nel modulo di PowerShell Teams (in anteprima)</span><span class="sxs-lookup"><span data-stu-id="861c0-157">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module (in preview)</span></span>|
| [<span data-ttu-id="861c0-158">Assegnare un pacchetto di criteri a un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="861c0-158">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="861c0-159">È necessario assegnare più criteri a un gruppo di utenti dell'organizzazione che hanno ruoli uguali o simili.</span><span class="sxs-lookup"><span data-stu-id="861c0-159">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="861c0-160">Ad esempio, assegna il pacchetto di criteri Education (Teacher) a tutti gli insegnanti dell'Istituto di istruzione usando l'assegnazione batch per consentire loro l'accesso completo alle chat, alle chiamate e alle riunioni e assegnare il pacchetto di criteri per l'istruzione (studente di scuola secondaria) a un gruppo di studenti secondari per limitare alcune funzionalità come le chiamate private.</span><span class="sxs-lookup"><span data-stu-id="861c0-160">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="861c0-161">Cmdlet di PowerShell nel modulo di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="861c0-161">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="861c0-162">Assegnare un pacchetto di criteri a un gruppo (disponibile a breve)</span><span class="sxs-lookup"><span data-stu-id="861c0-162">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="set-the-global-policies"></a><span data-ttu-id="861c0-163">Impostare i criteri globali</span><span class="sxs-lookup"><span data-stu-id="861c0-163">Set the global policies</span></span>

<span data-ttu-id="861c0-164">Seguire questa procedura per impostare i criteri globali (per impostazione predefinita a livello di organizzazione) per ogni tipo di criterio.</span><span class="sxs-lookup"><span data-stu-id="861c0-164">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="861c0-165">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="861c0-165">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="861c0-166">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa alla pagina dei criteri per il tipo di criterio che vuoi aggiornare.</span><span class="sxs-lookup"><span data-stu-id="861c0-166">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="861c0-167">Ad **esempio, criteri Team teams**  >  **Teams policies**, **Meetings**  >  **criteri riunioni**riunioni, **criteri di messaggistica**o criteri di chiamata **vocale**  >  **Calling policies**.</span><span class="sxs-lookup"><span data-stu-id="861c0-167">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="861c0-168">Selezionare il criterio **globale (predefinito per l'intera organizzazione)** per visualizzare le impostazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="861c0-168">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="861c0-169">Aggiornare i criteri in base alle esigenze e quindi selezionare **applica**.</span><span class="sxs-lookup"><span data-stu-id="861c0-169">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="861c0-170">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="861c0-170">Using PowerShell</span></span>

<span data-ttu-id="861c0-171">Per impostare i criteri globali tramite PowerShell, usare l'identificatore globale.</span><span class="sxs-lookup"><span data-stu-id="861c0-171">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="861c0-172">Iniziare rivedendo il criterio globale corrente per determinare l'impostazione che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="861c0-172">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="861c0-173">Aggiornare quindi il criterio globale in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="861c0-173">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="861c0-174">È necessario specificare solo i valori per le impostazioni che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="861c0-174">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="861c0-175">Assegnare un criterio a singoli utenti</span><span class="sxs-lookup"><span data-stu-id="861c0-175">Assign a policy to individual users</span></span>

<span data-ttu-id="861c0-176">Seguire questa procedura per assegnare un criterio a un singolo utente o a un numero limitato di utenti alla volta.</span><span class="sxs-lookup"><span data-stu-id="861c0-176">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="861c0-177">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="861c0-177">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="861c0-178">Per assegnare un criterio a un utente:</span><span class="sxs-lookup"><span data-stu-id="861c0-178">To assign a policy to a user:</span></span>

1. <span data-ttu-id="861c0-179">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.</span><span class="sxs-lookup"><span data-stu-id="861c0-179">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="861c0-180">Per selezionare l'utente facendo clic a sinistra del nome utente e poi fare clic su **Impostazioni di modifica**.</span><span class="sxs-lookup"><span data-stu-id="861c0-180">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="861c0-181">Selezionare il criterio che si vuole assegnare e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="861c0-181">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="861c0-182">Si può anche procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="861c0-182">Or, you can also do the following:</span></span>

1. <span data-ttu-id="861c0-183">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa alla pagina dei criteri.</span><span class="sxs-lookup"><span data-stu-id="861c0-183">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="861c0-184">Selezionare il criterio che si vuole assegnare facendo clic a sinistra del nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="861c0-184">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="861c0-185">Scegliere **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="861c0-185">Select **Manage users**.</span></span>
4. <span data-ttu-id="861c0-186">Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="861c0-186">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="861c0-187">Ripetere questa operazione per ogni utente da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="861c0-187">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="861c0-188">Al termine dell'aggiunta di utenti, selezionare **applica**.</span><span class="sxs-lookup"><span data-stu-id="861c0-188">When you're finished adding users, select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="861c0-189">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="861c0-189">Using PowerShell</span></span>

<span data-ttu-id="861c0-190">Ogni tipo di criterio ha un proprio set di cmdlet per la gestione.</span><span class="sxs-lookup"><span data-stu-id="861c0-190">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="861c0-191">Usa il ```Grant-``` cmdlet per un tipo di criteri specifico per assegnare i criteri.</span><span class="sxs-lookup"><span data-stu-id="861c0-191">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="861c0-192">Ad esempio, usa il ```Grant-CsTeamsMeetingPolicy``` cmdlet per assegnare un criterio di riunione teams agli utenti.</span><span class="sxs-lookup"><span data-stu-id="861c0-192">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="861c0-193">Questi cmdlet sono inclusi nel modulo di PowerShell per Skype for business online e sono documentati nella Guida di [riferimento ai cmdlet di Skype for business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="861c0-193">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="861c0-194">Scaricare e installare il [modulo di PowerShell per Skype for business online](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (se non è già stato fatto), quindi eseguire le operazioni seguenti per connettersi a Skype for business online e avviare una sessione.</span><span class="sxs-lookup"><span data-stu-id="861c0-194">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="861c0-195">In questo esempio, assegniamo un criterio riunione teams denominato criteri riunione studenti a un utente di nome Reda.</span><span class="sxs-lookup"><span data-stu-id="861c0-195">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="861c0-196">Per altre informazioni, vedere [gestione dei criteri tramite PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="861c0-196">To learn more, see [Managing policies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="861c0-197">Assegnare un pacchetto di criteri</span><span class="sxs-lookup"><span data-stu-id="861c0-197">Assign a policy package</span></span>

<span data-ttu-id="861c0-198">Un pacchetto di criteri in teams è una raccolta di criteri predefiniti e di impostazioni dei criteri che è possibile assegnare agli utenti che hanno ruoli uguali o simili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="861c0-198">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="861c0-199">Ogni pacchetto di criteri è progettato intorno a un ruolo utente e include criteri predefiniti e impostazioni dei criteri che supportano le attività tipiche di tale ruolo.</span><span class="sxs-lookup"><span data-stu-id="861c0-199">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="861c0-200">Alcuni esempi di pacchetti di criteri sono il pacchetto Education (Teacher) e il pacchetto Healthcare (Worker clinico).</span><span class="sxs-lookup"><span data-stu-id="861c0-200">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="861c0-201">Quando si assegna un pacchetto di criteri agli utenti, i criteri del pacchetto vengono creati e quindi è possibile personalizzare le impostazioni di ogni criterio nel pacchetto per soddisfare le esigenze degli utenti.</span><span class="sxs-lookup"><span data-stu-id="861c0-201">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="861c0-202">Per altre informazioni sui pacchetti di criteri, tra cui indicazioni dettagliate su come assegnarle e gestirle, vedere gestire i [pacchetti di criteri in teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="861c0-202">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="861c0-203">Assegnare un criterio a un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="861c0-203">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="861c0-204">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="861c0-204">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="861c0-205">Per assegnare un criterio agli utenti in blocco:</span><span class="sxs-lookup"><span data-stu-id="861c0-205">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="861c0-206">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare **utenti**.</span><span class="sxs-lookup"><span data-stu-id="861c0-206">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="861c0-207">Cercare gli utenti a cui assegnare il criterio o filtrare la visualizzazione per mostrare gli utenti desiderati.</span><span class="sxs-lookup"><span data-stu-id="861c0-207">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="861c0-208">Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="861c0-208">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="861c0-209">Per selezionare tutti gli utenti, fare clic sul &#x2713; (segno di spunta) nella parte superiore della tabella.</span><span class="sxs-lookup"><span data-stu-id="861c0-209">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="861c0-210">Fare clic su **Modifica impostazioni**, apportare le modifiche desiderate e quindi fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="861c0-210">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="861c0-211">Per visualizzare lo stato dell'assegnazione dei criteri, nell'intestazione visualizzata nella parte superiore della pagina **utenti** dopo aver fatto clic su **applica** per inviare l'assegnazione di criteri, fare clic su **Registro attività**.</span><span class="sxs-lookup"><span data-stu-id="861c0-211">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="861c0-212">Oppure, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **Dashboard**e quindi in **Registro attività**fare clic su **Visualizza dettagli**.</span><span class="sxs-lookup"><span data-stu-id="861c0-212">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="861c0-213">Il registro attività Mostra le assegnazioni dei criteri ai batch di più di 20 utenti tramite l'interfaccia di amministrazione di Microsoft teams degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="861c0-213">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="861c0-214">Per altre informazioni, vedere [visualizzare le assegnazioni dei criteri nel registro attività](activity-log.md).</span><span class="sxs-lookup"><span data-stu-id="861c0-214">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="861c0-215">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="861c0-215">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="861c0-216">Attualmente, l'assegnazione di criteri batch con PowerShell non è disponibile per tutti i tipi di criteri teams.</span><span class="sxs-lookup"><span data-stu-id="861c0-216">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="861c0-217">Vedere [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) per l'elenco dei tipi di criteri supportati.</span><span class="sxs-lookup"><span data-stu-id="861c0-217">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>
 
<span data-ttu-id="861c0-218">Con l'assegnazione di criteri batch è possibile assegnare un criterio a set di utenti di grandi dimensioni alla volta senza dover usare uno script.</span><span class="sxs-lookup"><span data-stu-id="861c0-218">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="861c0-219">Puoi usare il ```New-CsBatchPolicyAssignmentOperation``` cmdlet per inviare un batch di utenti e i criteri che vuoi assegnare.</span><span class="sxs-lookup"><span data-stu-id="861c0-219">You use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="861c0-220">Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch.</span><span class="sxs-lookup"><span data-stu-id="861c0-220">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="861c0-221">Puoi quindi usare il ```Get-CsBatchPolicyAssignmentOperation``` cmdlet per tenere traccia dello stato di avanzamento e dello stato delle assegnazioni in un batch.</span><span class="sxs-lookup"><span data-stu-id="861c0-221">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="861c0-222">Puoi specificare gli utenti in base al loro ID oggetto o all'indirizzo SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="861c0-222">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="861c0-223">Tieni presente che l'indirizzo SIP di un utente ha spesso lo stesso valore del nome dell'entità utente (UPN) o dell'indirizzo di posta elettronica, ma non è necessario.</span><span class="sxs-lookup"><span data-stu-id="861c0-223">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="861c0-224">Se un utente viene specificato con il proprio UPN o tramite posta elettronica, ma ha un valore diverso rispetto all'indirizzo SIP, l'assegnazione dei criteri non riesce per l'utente.</span><span class="sxs-lookup"><span data-stu-id="861c0-224">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="861c0-225">Se un batch include utenti duplicati, i duplicati verranno rimossi dal batch prima che l'elaborazione e lo stato vengano forniti solo per gli utenti univoci rimasti nel batch.</span><span class="sxs-lookup"><span data-stu-id="861c0-225">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="861c0-226">Un batch può contenere fino a 5.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="861c0-226">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="861c0-227">Per ottenere risultati ottimali, non inviare più di alcuni batch alla volta.</span><span class="sxs-lookup"><span data-stu-id="861c0-227">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="861c0-228">Consentire ai batch di completare l'elaborazione prima di inviare più batch.</span><span class="sxs-lookup"><span data-stu-id="861c0-228">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="861c0-229">Installare e connettersi al modulo di PowerShell di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="861c0-229">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="861c0-230">Eseguire la procedura seguente per installare il [modulo di PowerShell per Microsoft teams](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="861c0-230">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="861c0-231">Assicurarsi di installare la versione 1.0.5 o successiva.</span><span class="sxs-lookup"><span data-stu-id="861c0-231">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="861c0-232">Eseguire le operazioni seguenti per connettersi ai team e avviare una sessione.</span><span class="sxs-lookup"><span data-stu-id="861c0-232">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="861c0-233">Quando viene richiesto, accedere con le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="861c0-233">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="861c0-234">Installare e connettersi a Azure AD PowerShell per modulo grafico (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="861c0-234">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="861c0-235">Puoi anche [scaricare e installare Azure ad PowerShell per il modulo grafico](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (se non lo hai già fatto) e connetterti AD Azure ad in modo da poter recuperare un elenco di utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="861c0-235">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="861c0-236">Eseguire la procedura seguente per connettersi ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="861c0-236">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="861c0-237">Quando viene richiesto, accedere con le stesse credenziali di amministratore usate per connettersi ai team.</span><span class="sxs-lookup"><span data-stu-id="861c0-237">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="861c0-238">Assegnare un criterio a un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="861c0-238">Assign a policy to a batch of users</span></span>

<span data-ttu-id="861c0-239">In questo esempio usiamo il ```New-CsBatchPolicyAssignmentOperation``` cmdlet per assegnare un criterio di configurazione dell'app denominato criteri di configurazione dell'app HR a un batch di utenti elencati nel file Users_ids. Text.</span><span class="sxs-lookup"><span data-stu-id="861c0-239">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="861c0-240">In questo esempio, ci connettiamo ad Azure AD per recuperare una raccolta di utenti e quindi assegnare un criterio di messaggistica denominato nuovi criteri di messaggistica di noleggio a un batch di utenti specificato tramite l'indirizzo SIP.</span><span class="sxs-lookup"><span data-stu-id="861c0-240">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

<span data-ttu-id="861c0-241">Per altre informazioni, vedere [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="861c0-241">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="861c0-242">Ottenere lo stato di un'assegnazione batch</span><span class="sxs-lookup"><span data-stu-id="861c0-242">Get the status of a batch assignment</span></span>

<span data-ttu-id="861c0-243">Eseguire la procedura seguente per ottenere lo stato di un'assegnazione batch, dove OperationId è l'ID operazione restituito dal ```New-CsBatchPolicyAssignmentOperation``` cmdlet per un batch specifico.</span><span class="sxs-lookup"><span data-stu-id="861c0-243">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="861c0-244">Se l'output indica che si è verificato un errore, eseguire la procedura seguente per ottenere altre informazioni sugli errori, che si trovano nella ```UserState``` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="861c0-244">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="861c0-245">Per altre informazioni, vedere [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="861c0-245">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="861c0-246">Assegnare un criterio a un gruppo</span><span class="sxs-lookup"><span data-stu-id="861c0-246">Assign a policy to a group</span></span>

<span data-ttu-id="861c0-247">L'assegnazione dei criteri a gruppi consente di assegnare un criterio a un gruppo di utenti, ad esempio un gruppo di sicurezza o un'unità organizzativa.</span><span class="sxs-lookup"><span data-stu-id="861c0-247">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="861c0-248">L'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza.</span><span class="sxs-lookup"><span data-stu-id="861c0-248">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="861c0-249">Quando i membri vengono aggiunti o rimossi da un gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="861c0-249">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="861c0-250">L'assegnazione dei criteri ai gruppi è consigliata per i gruppi di utenti fino a 50.000, ma funziona anche con i gruppi più grandi.</span><span class="sxs-lookup"><span data-stu-id="861c0-250">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="861c0-251">Quando si assegna il criterio, viene immediatamente assegnato al gruppo.</span><span class="sxs-lookup"><span data-stu-id="861c0-251">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="861c0-252">Si noti tuttavia che la propagazione dell'assegnazione dei criteri ai membri del gruppo viene eseguita come operazione in background e può richiedere del tempo, a seconda delle dimensioni del gruppo.</span><span class="sxs-lookup"><span data-stu-id="861c0-252">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="861c0-253">Lo stesso vale quando un criterio non viene assegnato da un gruppo o quando i membri vengono aggiunti o rimossi da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="861c0-253">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="861c0-254">Informazioni utili sull'assegnazione dei criteri ai gruppi</span><span class="sxs-lookup"><span data-stu-id="861c0-254">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="861c0-255">Prima di iniziare, è importante comprendere le regole di precedenza e la classificazione delle assegnazioni di gruppo.</span><span class="sxs-lookup"><span data-stu-id="861c0-255">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="861c0-256">Regole di precedenza</span><span class="sxs-lookup"><span data-stu-id="861c0-256">Precedence rules</span></span>

<span data-ttu-id="861c0-257">Per un determinato tipo di criteri, il criterio effettivo di un utente viene determinato in base alle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="861c0-257">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="861c0-258">Un criterio assegnato direttamente a un utente ha la precedenza su qualsiasi altro criterio dello stesso tipo assegnato a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="861c0-258">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="861c0-259">In altre parole, se a un utente viene assegnato direttamente un criterio di un tipo specifico, l'utente non erediterà un criterio dello stesso tipo da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="861c0-259">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="861c0-260">Ciò significa anche che, se un utente ha un criterio di un tipo specifico a cui è stato assegnato direttamente, è necessario rimuovere i criteri dall'utente prima che possano ereditare un criterio dello stesso tipo da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="861c0-260">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="861c0-261">Se un utente non ha un criterio direttamente assegnato ed è un membro di due o più gruppi e ogni gruppo ha un criterio dello stesso tipo assegnato, l'utente eredita i criteri dell'assegnazione del gruppo con la classificazione più alta.</span><span class="sxs-lookup"><span data-stu-id="861c0-261">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="861c0-262">Se un utente non è un membro di tutti i gruppi a cui è assegnato un criterio, il criterio globale (a livello di organizzazione predefinita) per tale tipo di criteri si applica all'utente.</span><span class="sxs-lookup"><span data-stu-id="861c0-262">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="861c0-263">I criteri effettivi di un utente vengono aggiornati in base a queste regole quando un utente viene aggiunto o rimosso da un gruppo a cui è assegnato un criterio, un criterio non è assegnato da un gruppo o viene rimosso un criterio direttamente assegnato all'utente.</span><span class="sxs-lookup"><span data-stu-id="861c0-263">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="861c0-264">Classificazione delle assegnazioni di gruppo</span><span class="sxs-lookup"><span data-stu-id="861c0-264">Group assignment ranking</span></span>
 
<span data-ttu-id="861c0-265">Quando si assegna un criterio a un gruppo, è necessario specificare una classificazione per l'assegnazione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="861c0-265">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="861c0-266">Viene usato per determinare i criteri che un utente deve ereditare come criterio effettivo se l'utente è un membro di due o più gruppi e a ogni gruppo viene assegnato un criterio dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="861c0-266">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="861c0-267">La classificazione delle assegnazioni di gruppo è relativa ad altre assegnazioni di gruppo dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="861c0-267">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="861c0-268">Ad esempio, se si sta assegnando un criterio di chiamata a due gruppi, impostare la classificazione di un'assegnazione su 1 e l'altra su 2, con 1 che è la classificazione più alta.</span><span class="sxs-lookup"><span data-stu-id="861c0-268">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="861c0-269">La classificazione delle assegnazioni di gruppo indica l'appartenenza a un gruppo più importante o più pertinente rispetto alle altre appartenenze ai gruppi per quanto riguarda l'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="861c0-269">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="861c0-270">Supponiamo, ad esempio, di avere due gruppi, i dipendenti dello Store e i responsabili dello Store.</span><span class="sxs-lookup"><span data-stu-id="861c0-270">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="861c0-271">A entrambi i gruppi viene assegnato un criterio di chiamata per i team, rispettivamente i criteri di chiamata dei dipendenti e i responsabili dello Store.</span><span class="sxs-lookup"><span data-stu-id="861c0-271">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="861c0-272">Per un responsabile dello Store che si trova in entrambi i gruppi, il loro ruolo di Manager è più pertinente del loro ruolo di dipendente, quindi il criterio di chiamata assegnato al gruppo responsabili dello Store dovrebbe avere una classificazione più alta.</span><span class="sxs-lookup"><span data-stu-id="861c0-272">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="861c0-273">Gruppo</span><span class="sxs-lookup"><span data-stu-id="861c0-273">Group</span></span> |<span data-ttu-id="861c0-274">Nome dei criteri di chiamata dei team</span><span class="sxs-lookup"><span data-stu-id="861c0-274">Teams calling policy name</span></span>  |<span data-ttu-id="861c0-275">Rango</span><span class="sxs-lookup"><span data-stu-id="861c0-275">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="861c0-276">Responsabili dello Store</span><span class="sxs-lookup"><span data-stu-id="861c0-276">Store Managers</span></span>   |<span data-ttu-id="861c0-277">Criteri di chiamata per i responsabili dello Store</span><span class="sxs-lookup"><span data-stu-id="861c0-277">Store Managers Calling Policy</span></span>         |<span data-ttu-id="861c0-278">1</span><span class="sxs-lookup"><span data-stu-id="861c0-278">1</span></span>|
|<span data-ttu-id="861c0-279">Archiviare i dipendenti</span><span class="sxs-lookup"><span data-stu-id="861c0-279">Store Employees</span></span>    |<span data-ttu-id="861c0-280">Criteri di chiamata dei dipendenti dello Store</span><span class="sxs-lookup"><span data-stu-id="861c0-280">Store Employees Calling Policy</span></span>      |<span data-ttu-id="861c0-281">2</span><span class="sxs-lookup"><span data-stu-id="861c0-281">2</span></span>|

<span data-ttu-id="861c0-282">Se non specifichi una classificazione, all'assegnazione dei criteri viene assegnata la classificazione più bassa.</span><span class="sxs-lookup"><span data-stu-id="861c0-282">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="861c0-283">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="861c0-283">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="861c0-284">**Questa caratteristica non è ancora stata rilasciata. È stata annunciata e arriverà presto.**</span><span class="sxs-lookup"><span data-stu-id="861c0-284">**This feature hasn't yet been released. It's been announced, and it's coming soon.**</span></span>

> [!NOTE]
> <span data-ttu-id="861c0-285">Attualmente, l'assegnazione dei criteri ai gruppi che usano l'interfaccia di amministrazione di Microsoft teams è disponibile solo per i criteri di chiamata dei team, i criteri per le riunioni di team e i criteri di messaggistica</span><span class="sxs-lookup"><span data-stu-id="861c0-285">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="861c0-286">Per altri tipi di criteri, usare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="861c0-286">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="861c0-287">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams passa alla pagina tipo di criteri.</span><span class="sxs-lookup"><span data-stu-id="861c0-287">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="861c0-288">Ad esempio, vai a **Meetings**  >  **criteri riunione**riunioni.</span><span class="sxs-lookup"><span data-stu-id="861c0-288">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="861c0-289">Selezionare la scheda **assegnazione criteri di gruppo** .</span><span class="sxs-lookup"><span data-stu-id="861c0-289">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="861c0-290">Selezionare **Aggiungi gruppo**e quindi nel riquadro **Assegna criteri a gruppo** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="861c0-290">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="861c0-291">Cercare e aggiungere il gruppo a cui si vuole assegnare il criterio.</span><span class="sxs-lookup"><span data-stu-id="861c0-291">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="861c0-292">Impostare la classificazione per l'assegnazione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="861c0-292">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="861c0-293">Selezionare il criterio che si vuole assegnare.</span><span class="sxs-lookup"><span data-stu-id="861c0-293">Select the policy that you want to assign.</span></span> 
    4. <span data-ttu-id="861c0-294">Selezionare **applica**.</span><span class="sxs-lookup"><span data-stu-id="861c0-294">Select **Apply**.</span></span>

<span data-ttu-id="861c0-295">Per rimuovere un'assegnazione di criteri di gruppo, nella scheda assegnazione criteri di **gruppo** della pagina Criteri selezionare l'assegnazione del gruppo e quindi scegliere **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="861c0-295">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="861c0-296">Per modificare la classificazione di un'assegnazione di gruppo, è necessario rimuovere prima di tutto l'assegnazione dei criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="861c0-296">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="861c0-297">Seguire quindi la procedura descritta in precedenza per assegnare i criteri a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="861c0-297">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="861c0-298">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="861c0-298">Using PowerShell</span></span>

<span data-ttu-id="861c0-299">**Questa caratteristica è attualmente disponibile solo in anteprima privata. I cmdlet per questa funzionalità si trovano nel modulo di PowerShell per i team pre-release.**</span><span class="sxs-lookup"><span data-stu-id="861c0-299">**This feature is currently only available in private preview. The cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span>

> [!NOTE]
> <span data-ttu-id="861c0-300">Attualmente, l'assegnazione dei criteri ai gruppi che usano PowerShell non è disponibile per tutti i tipi di criteri teams.</span><span class="sxs-lookup"><span data-stu-id="861c0-300">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="861c0-301">Vedere [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) per l'elenco dei tipi di criteri supportati.</span><span class="sxs-lookup"><span data-stu-id="861c0-301">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="861c0-302">Installare e connettersi al modulo di PowerShell di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="861c0-302">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="861c0-303">I cmdlet si trovano nella versione preliminare del modulo di PowerShell teams.</span><span class="sxs-lookup"><span data-stu-id="861c0-303">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="861c0-304">Seguire questa procedura per disinstallare prima di tutto la versione in genere disponibile del modulo di PowerShell Teams (se è installato) e quindi installare la versione più recente di pre-rilascio del modulo dalla raccolta di test di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="861c0-304">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="861c0-305">Se non è già stato eseguito, eseguire la procedura seguente per registrare la raccolta di test di PowerShell come origine attendibile.</span><span class="sxs-lookup"><span data-stu-id="861c0-305">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="861c0-306">Se è installata la versione in genere disponibile del modulo di PowerShell teams, eseguire la procedura seguente per disinstallarlo.</span><span class="sxs-lookup"><span data-stu-id="861c0-306">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="861c0-307">Eseguire la procedura seguente per installare il modulo di PowerShell Microsoft Teams più recente dalla raccolta di test di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="861c0-307">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="861c0-308">Eseguire le operazioni seguenti per connettersi ai team e avviare una sessione.</span><span class="sxs-lookup"><span data-stu-id="861c0-308">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="861c0-309">Quando viene richiesto, accedere con le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="861c0-309">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="861c0-310">Assegnare un criterio a un gruppo</span><span class="sxs-lookup"><span data-stu-id="861c0-310">Assign a policy to a group</span></span>

<span data-ttu-id="861c0-311">Puoi usare il ```New-CsGroupPolicyAssignment``` cmdlet per assegnare un criterio a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="861c0-311">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="861c0-312">Puoi specificare un gruppo usando l'ID oggetto, l'indirizzo SIP o l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="861c0-312">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="861c0-313">In questo esempio, usiamo il ```New-CsGroupPolicyAssignment``` cmdlet per assegnare un criterio riunione teams denominato criteri di riunione per i responsabili delle riunioni a un gruppo con una classificazione di assegnazione di 1.</span><span class="sxs-lookup"><span data-stu-id="861c0-313">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="861c0-314">Per altre informazioni, vedere [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="861c0-314">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="861c0-315">Ottenere le assegnazioni dei criteri per un gruppo</span><span class="sxs-lookup"><span data-stu-id="861c0-315">Get policy assignments for a group</span></span>

<span data-ttu-id="861c0-316">Usa il ```Get-CsGroupPolicyAssignment``` cmdlet per ottenere tutti i criteri assegnati a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="861c0-316">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="861c0-317">Tieni presente che i gruppi sono sempre elencati dall'ID del gruppo, anche se l'indirizzo SIP o l'indirizzo di posta elettronica è stato usato per assegnare il criterio.</span><span class="sxs-lookup"><span data-stu-id="861c0-317">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="861c0-318">In questo esempio recuperiamo tutti i criteri assegnati a un gruppo specifico.</span><span class="sxs-lookup"><span data-stu-id="861c0-318">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="861c0-319">In questo esempio vengono restituiti tutti i gruppi a cui è stato assegnato un criterio di riunione teams.</span><span class="sxs-lookup"><span data-stu-id="861c0-319">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="861c0-320">Per altre informazioni, vedere [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="861c0-320">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="861c0-321">Rimuovere un criterio da un gruppo</span><span class="sxs-lookup"><span data-stu-id="861c0-321">Remove a policy from a group</span></span>

<span data-ttu-id="861c0-322">Utilizzare il ```Remove-CsGroupPolicyAssignment``` cmdlet per rimuovere un criterio da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="861c0-322">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="861c0-323">Quando si rimuove un criterio da un gruppo, vengono aggiornate le priorità di altri criteri dello stesso tipo assegnati al gruppo e con una classificazione inferiore.</span><span class="sxs-lookup"><span data-stu-id="861c0-323">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="861c0-324">Se ad esempio si rimuove un criterio con una classificazione 2, i criteri che hanno una classificazione 3 e 4 vengono aggiornati per riflettere la nuova classificazione.</span><span class="sxs-lookup"><span data-stu-id="861c0-324">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="861c0-325">Le due tabelle seguenti mostrano questo esempio.</span><span class="sxs-lookup"><span data-stu-id="861c0-325">The following two tables show this example.</span></span>

<span data-ttu-id="861c0-326">Ecco un elenco delle assegnazioni dei criteri e delle priorità per i criteri di riunione di teams.</span><span class="sxs-lookup"><span data-stu-id="861c0-326">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="861c0-327">Nome gruppo</span><span class="sxs-lookup"><span data-stu-id="861c0-327">Group name</span></span>  |<span data-ttu-id="861c0-328">Nome del criterio</span><span class="sxs-lookup"><span data-stu-id="861c0-328">Policy name</span></span>  |<span data-ttu-id="861c0-329">Rango</span><span class="sxs-lookup"><span data-stu-id="861c0-329">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="861c0-330">Vendite</span><span class="sxs-lookup"><span data-stu-id="861c0-330">Sales</span></span>    |<span data-ttu-id="861c0-331">Criteri di vendita</span><span class="sxs-lookup"><span data-stu-id="861c0-331">Sales policy</span></span>       | <span data-ttu-id="861c0-332">1</span><span class="sxs-lookup"><span data-stu-id="861c0-332">1</span></span>        |
|<span data-ttu-id="861c0-333">Regione occidentale</span><span class="sxs-lookup"><span data-stu-id="861c0-333">West Region</span></span>     |<span data-ttu-id="861c0-334">Criteri per la regione occidentale</span><span class="sxs-lookup"><span data-stu-id="861c0-334">West Region policy</span></span>         |<span data-ttu-id="861c0-335">2</span><span class="sxs-lookup"><span data-stu-id="861c0-335">2</span></span>         |
|<span data-ttu-id="861c0-336">Divisione</span><span class="sxs-lookup"><span data-stu-id="861c0-336">Division</span></span>    |<span data-ttu-id="861c0-337">Criteri di divisione</span><span class="sxs-lookup"><span data-stu-id="861c0-337">Division policy</span></span>         |<span data-ttu-id="861c0-338">3</span><span class="sxs-lookup"><span data-stu-id="861c0-338">3</span></span>         |
|<span data-ttu-id="861c0-339">Filiale nel</span><span class="sxs-lookup"><span data-stu-id="861c0-339">Subsidiary</span></span>   |<span data-ttu-id="861c0-340">Criteri sussidiari</span><span class="sxs-lookup"><span data-stu-id="861c0-340">Subsidiary policy</span></span>        |<span data-ttu-id="861c0-341">4</span><span class="sxs-lookup"><span data-stu-id="861c0-341">4</span></span>         |

<span data-ttu-id="861c0-342">Se rimuoviamo i criteri per l'area ovest dal gruppo area occidentale, le assegnazioni dei criteri e le priorità vengono aggiornate come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="861c0-342">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="861c0-343">Nome gruppo</span><span class="sxs-lookup"><span data-stu-id="861c0-343">Group name</span></span>  |<span data-ttu-id="861c0-344">Nome del criterio</span><span class="sxs-lookup"><span data-stu-id="861c0-344">Policy name</span></span>  |<span data-ttu-id="861c0-345">Rango</span><span class="sxs-lookup"><span data-stu-id="861c0-345">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="861c0-346">Vendite</span><span class="sxs-lookup"><span data-stu-id="861c0-346">Sales</span></span>    |<span data-ttu-id="861c0-347">Criteri di vendita</span><span class="sxs-lookup"><span data-stu-id="861c0-347">Sales policy</span></span>       | <span data-ttu-id="861c0-348">1</span><span class="sxs-lookup"><span data-stu-id="861c0-348">1</span></span>        |
|<span data-ttu-id="861c0-349">Divisione</span><span class="sxs-lookup"><span data-stu-id="861c0-349">Division</span></span>    |<span data-ttu-id="861c0-350">Criteri di divisione</span><span class="sxs-lookup"><span data-stu-id="861c0-350">Division policy</span></span>         |<span data-ttu-id="861c0-351">2</span><span class="sxs-lookup"><span data-stu-id="861c0-351">2</span></span>         |
|<span data-ttu-id="861c0-352">Filiale nel</span><span class="sxs-lookup"><span data-stu-id="861c0-352">Subsidiary</span></span>   |<span data-ttu-id="861c0-353">Criteri sussidiari</span><span class="sxs-lookup"><span data-stu-id="861c0-353">Subsidiary policy</span></span>        |<span data-ttu-id="861c0-354">3</span><span class="sxs-lookup"><span data-stu-id="861c0-354">3</span></span>        |

<span data-ttu-id="861c0-355">In questo esempio rimuoviamo i criteri riunione Teams da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="861c0-355">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="861c0-356">Per altre informazioni, vedere [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="861c0-356">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="861c0-357">Modificare un'assegnazione di criteri per un gruppo</span><span class="sxs-lookup"><span data-stu-id="861c0-357">Change a policy assignment for a group</span></span>

<span data-ttu-id="861c0-358">Dopo aver assegnato un criterio a un gruppo, è possibile usare il ```Set-CsGroupPolicyAssignment``` cmdlet per modificare l'assegnazione dei criteri del gruppo, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="861c0-358">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignment``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="861c0-359">Modificare la classificazione</span><span class="sxs-lookup"><span data-stu-id="861c0-359">Change the ranking</span></span>
- <span data-ttu-id="861c0-360">Modificare i criteri di un tipo di criterio specifico</span><span class="sxs-lookup"><span data-stu-id="861c0-360">Change the policy of a given policy type</span></span>
- <span data-ttu-id="861c0-361">Modificare i criteri di un tipo di criteri specifico e la classificazione</span><span class="sxs-lookup"><span data-stu-id="861c0-361">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="861c0-362">In questo esempio modifichiamo i criteri di parcheggio per le chiamate di team di un gruppo in un criterio denominato SupportCallPark e la classificazione delle assegnazioni su 3.</span><span class="sxs-lookup"><span data-stu-id="861c0-362">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="861c0-363">Per altre informazioni, vedere [set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="861c0-363">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="861c0-364">Modificare i criteri effettivi per un utente</span><span class="sxs-lookup"><span data-stu-id="861c0-364">Change the effective policy for a user</span></span>

<span data-ttu-id="861c0-365">Ecco un esempio di come modificare i criteri effettivi per un utente a cui è assegnato direttamente un criterio.</span><span class="sxs-lookup"><span data-stu-id="861c0-365">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="861c0-366">Prima di tutto, usiamo il ```Get-CsUserPolicyAssignment``` cmdlet insieme al ```PolicySource``` parametro per ottenere informazioni dettagliate sui criteri di trasmissione delle riunioni dei team associati all'utente.</span><span class="sxs-lookup"><span data-stu-id="861c0-366">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="861c0-367">Per altre informazioni, vedere [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="861c0-367">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="861c0-368">Nell'output viene indicato che all'utente sono stati assegnati direttamente i criteri di riunione per le riunioni di teams denominati eventi dei dipendenti, che hanno la precedenza sui criteri denominati fornitori di eventi live assegnati a un gruppo a cui appartiene l'utente.</span><span class="sxs-lookup"><span data-stu-id="861c0-368">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="861c0-369">Ora rimuoviamo i criteri degli eventi dei dipendenti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="861c0-369">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="861c0-370">Ciò significa che l'utente non ha più un criterio di riunione delle riunioni di teams direttamente assegnato e erediterà i criteri degli eventi live del fornitore assegnati al gruppo a cui appartiene l'utente.</span><span class="sxs-lookup"><span data-stu-id="861c0-370">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="861c0-371">Per eseguire questa operazione, usare il cmdlet seguente nel modulo di PowerShell per Skype for business.</span><span class="sxs-lookup"><span data-stu-id="861c0-371">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="861c0-372">È possibile usare i cmdlet seguenti nel modulo di PowerShell teams per eseguire questa operazione in scala anche se un'assegnazione di criteri batch, dove $users è un elenco di utenti specificati.</span><span class="sxs-lookup"><span data-stu-id="861c0-372">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="861c0-373">Assegnare un pacchetto di criteri a un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="861c0-373">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="861c0-374">Con l'assegnazione di un pacchetto di criteri batch, puoi assegnare un pacchetto di criteri a set di grandi dimensioni di utenti alla volta senza dover usare uno script.</span><span class="sxs-lookup"><span data-stu-id="861c0-374">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="861c0-375">Si usa il ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet per inviare un batch di utenti e il pacchetto di criteri che si vuole assegnare.</span><span class="sxs-lookup"><span data-stu-id="861c0-375">You use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="861c0-376">Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch.</span><span class="sxs-lookup"><span data-stu-id="861c0-376">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="861c0-377">Puoi quindi usare il ```Get-CsBatchPolicyAssignmentOperation``` cmdlet per tenere traccia dello stato di avanzamento e dello stato delle assegnazioni in un batch.</span><span class="sxs-lookup"><span data-stu-id="861c0-377">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="861c0-378">Puoi specificare gli utenti in base al loro ID oggetto o all'indirizzo SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="861c0-378">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="861c0-379">Tieni presente che l'indirizzo SIP di un utente ha spesso lo stesso valore del nome dell'entità utente (UPN) o dell'indirizzo di posta elettronica, ma non è necessario.</span><span class="sxs-lookup"><span data-stu-id="861c0-379">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="861c0-380">Se un utente viene specificato con il proprio UPN o tramite posta elettronica, ma ha un valore diverso rispetto all'indirizzo SIP, l'assegnazione dei criteri non riesce per l'utente.</span><span class="sxs-lookup"><span data-stu-id="861c0-380">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="861c0-381">Se un batch include utenti duplicati, i duplicati verranno rimossi dal batch prima che l'elaborazione e lo stato vengano forniti solo per gli utenti univoci rimasti nel batch.</span><span class="sxs-lookup"><span data-stu-id="861c0-381">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="861c0-382">Un batch può contenere fino a 5.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="861c0-382">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="861c0-383">Per ottenere risultati ottimali, non inviare più di alcuni batch alla volta.</span><span class="sxs-lookup"><span data-stu-id="861c0-383">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="861c0-384">Consentire ai batch di completare l'elaborazione prima di inviare più batch.</span><span class="sxs-lookup"><span data-stu-id="861c0-384">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="861c0-385">Installare e connettersi al modulo di PowerShell di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="861c0-385">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="861c0-386">Eseguire la procedura seguente per installare il [modulo di PowerShell di Microsoft teams](https://www.powershellgallery.com/packages/MicrosoftTeams) (se non è già stato fatto).</span><span class="sxs-lookup"><span data-stu-id="861c0-386">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="861c0-387">Assicurarsi di installare la versione 1.0.5 o successiva.</span><span class="sxs-lookup"><span data-stu-id="861c0-387">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="861c0-388">Eseguire le operazioni seguenti per connettersi ai team e avviare una sessione.</span><span class="sxs-lookup"><span data-stu-id="861c0-388">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="861c0-389">Quando viene richiesto, accedere con le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="861c0-389">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="861c0-390">Assegnare un pacchetto di criteri a un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="861c0-390">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="861c0-391">In questo esempio usiamo il ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet per assegnare il pacchetto di criteri Education_PrimaryStudent a un batch di utenti.</span><span class="sxs-lookup"><span data-stu-id="861c0-391">In this example, we use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

<span data-ttu-id="861c0-392">Per altre informazioni, vedere [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="861c0-392">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="861c0-393">Ottenere lo stato di un'assegnazione batch</span><span class="sxs-lookup"><span data-stu-id="861c0-393">Get the status of a batch assignment</span></span>

<span data-ttu-id="861c0-394">Eseguire la procedura seguente per ottenere lo stato di un'assegnazione batch, dove OperationId è l'ID operazione restituito dal ```New-CsBatchPolicyAssignmentOperation``` cmdlet per un batch specifico.</span><span class="sxs-lookup"><span data-stu-id="861c0-394">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="861c0-395">Se l'output indica che si è verificato un errore, eseguire la procedura seguente per ottenere altre informazioni sugli errori, che si trovano nella ```UserState``` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="861c0-395">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="861c0-396">Per altre informazioni, vedere [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="861c0-396">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="861c0-397">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="861c0-397">Related topics</span></span>

[<span data-ttu-id="861c0-398">Panoramica di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="861c0-398">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
