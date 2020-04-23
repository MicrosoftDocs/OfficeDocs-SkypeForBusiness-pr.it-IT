---
title: Spostare gli utenti dal cloud all'ambiente locale
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Informazioni su come spostare gli utenti da Skype for business online a locale.
ms.openlocfilehash: 0add74a2480f4caed493e6e448427aa2462db714
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779672"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a><span data-ttu-id="7a9ce-103">Spostare gli utenti dal cloud all'ambiente locale</span><span class="sxs-lookup"><span data-stu-id="7a9ce-103">Move users from the cloud to on-premises</span></span> 

<span data-ttu-id="7a9ce-104">Se necessario, è possibile spostare un utente che in precedenza è stato migrato da locale al cloud (se si utilizza Skype for business online o solo Teams) di nuovo in locale.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-104">If needed, you can move a user who was previously migrated from on-premises to the cloud (whether using Skype for Business Online or Teams Only) back to on-premises.</span></span> <span data-ttu-id="7a9ce-105">Per spostare gli utenti dalla modalità Skype for business online o TeamsOnly in una distribuzione locale di Skype for Business Server, utilizzare il cmdlet Move-CsUser o il pannello di controllo di Skype for Business Server, entrambi strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-105">To move users from either Skype for Business Online or TeamsOnly mode back to an on-premises deployment of Skype for Business Server, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> <span data-ttu-id="7a9ce-106">Quando si sposta un utente in una distribuzione locale, è necessario decidere il pool in cui spostare l'utente.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-106">When you move a user back to an on-premises deployment, you must decide which pool to move the user to.</span></span>

> [!Important]
> <span data-ttu-id="7a9ce-107">Se l'utente si trovava in precedenza in modalità TeamsOnly e si utilizza una versione precedente rispetto a Skype for Business Server 2015 con CU8, è necessario rimuovere anche l'assegnazione della modalità TeamsOnly di TeamsUpgradePolicy per tale utente.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-107">If the user was previously in TeamsOnly mode, and you are using an earlier version than Skype for Business Server 2015 with CU8, then you must also remove the TeamsOnly mode assignment of TeamsUpgradePolicy for that user.</span></span> <span data-ttu-id="7a9ce-108">Gli utenti locali non devono avere la modalità = TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-108">On-premises users must not have mode= TeamsOnly.</span></span>  <span data-ttu-id="7a9ce-109">Le versioni successive di Skype for Business Server rimuovono automaticamente questa assegnazione.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-109">Subsequent versions of Skype for Business Server automatically remove this assignment.</span></span> <span data-ttu-id="7a9ce-110">Per ulteriori informazioni, vedere [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy).</span><span class="sxs-lookup"><span data-stu-id="7a9ce-110">For more details, see [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7a9ce-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7a9ce-111">Prerequisites</span></span>

- <span data-ttu-id="7a9ce-112">L'organizzazione deve disporre di Azure AD Connect configurata in modo appropriato e sincronizzare tutti gli attributi rilevanti per l'utente, come descritto in [Configure Azure ad Connect](configure-azure-ad-connect.md).</span><span class="sxs-lookup"><span data-stu-id="7a9ce-112">The organization must have Azure AD Connect properly configured and be syncing all relevant attributes for the user, as described in [Configure Azure AD Connect](configure-azure-ad-connect.md).</span></span>
- <span data-ttu-id="7a9ce-113">L'utente da spostare da online Torna a locale deve esistere già in Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-113">The user being moved from online back to on-premises must already exist in the on-premises Active Directory.</span></span>
- <span data-ttu-id="7a9ce-114">È necessario configurare l'ambiente ibrido di Skype for business, come descritto in [Configure Skype for business Hybrid](configure-federation-with-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="7a9ce-114">Skype for Business hybrid must be configured, as described in [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).</span></span>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="7a9ce-115">Spostamento degli utenti in locale</span><span class="sxs-lookup"><span data-stu-id="7a9ce-115">Moving users back to on-premises</span></span>

<span data-ttu-id="7a9ce-116">Dopo aver spostato un utente dal cloud all'ambiente locale:</span><span class="sxs-lookup"><span data-stu-id="7a9ce-116">Once you move a user from the cloud back to on-premises:</span></span>

- <span data-ttu-id="7a9ce-117">L'utente interagisce con la distribuzione di Skype for Business Server per la sua funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-117">The user interacts with your Skype for Business Server deployment for its functionality.</span></span> 
- <span data-ttu-id="7a9ce-118">Tutti i contatti esistenti in Skype for business online o in teams vengono migrati su Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-118">Any contacts that existed in either Skype for Business Online or Teams are migrated  to Skype for Business Server.</span></span> <span data-ttu-id="7a9ce-119">I due gruppi di contatti vengono Uniti e quindi trasferiti di nuovo in locale.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-119">The two sets of contacts are merged and then migrated back to on-premises.</span></span>  <span data-ttu-id="7a9ce-120">Inoltre, i contatti preesistenti nei team rimangono in teams.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-120">In addition, contacts that are pre-existing in Teams remain in Teams.</span></span>
- <span data-ttu-id="7a9ce-121">Se l'utente usa anche i team, non avrà la possibilità di interagire con gli utenti di Skype for business, né potrà comunicare con gli utenti di organizzazioni federative.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-121">If the user also uses Teams, they will not have the ability to interoperate with Skype for Business users, nor will they be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="7a9ce-122">Le riunioni in Skype for business online *non* vengono automaticamente migrate di nuovo in locale.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-122">Meetings in Skype for Business Online are *not* automatically migrated back to on-premises.</span></span> <span data-ttu-id="7a9ce-123">Gli utenti devono ripianificare le riunioni o, se lo si desidera, utilizzare lo [strumento di migrazione delle riunioni](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).</span><span class="sxs-lookup"><span data-stu-id="7a9ce-123">Users should either reschedule their meetings or, if desired, use the [Meeting Migration Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).</span></span>

### <a name="move-users-with-move-csuser"></a><span data-ttu-id="7a9ce-124">Spostare gli utenti con Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="7a9ce-124">Move users with Move-CsUser</span></span>

<span data-ttu-id="7a9ce-125">Move-CsUser è disponibile da una finestra di PowerShell della shell di gestione di Skype for business locale.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-125">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="7a9ce-126">È necessario disporre di privilegi sufficienti sia nell'ambiente locale sia nell'organizzazione di Office 365, come descritto in [credenziali amministrative obbligatorie](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="7a9ce-126">You must have sufficient privileges in both the on-premises environment as well as the Office 365 organization, as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="7a9ce-127">È possibile utilizzare un singolo account che disponga di privilegi in entrambi gli ambienti oppure è possibile avviare una finestra della shell di gestione di Skype for Business Server locale con le credenziali locali e utilizzare il `-Credential` parametro per specificare le credenziali di un account di Office 365 con il ruolo amministrativo di Office 365 necessario.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-127">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="7a9ce-128">Per spostare un utente in locale tramite Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="7a9ce-128">To move a user to on-premises using Move-CsUser:</span></span>

- <span data-ttu-id="7a9ce-129">Specificare l'utente da spostare utilizzando il parametro Identity.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-129">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="7a9ce-130">Specificare il parametro-target con il nome di dominio completo del pool locale desiderato che ospiterà l'utente.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-130">Specify the -Target parameter with the fully qualified domain name of the desired on-premises pool that will host the user.</span></span>
- <span data-ttu-id="7a9ce-131">Se non si dispone di un account con autorizzazioni sufficienti sia in locale che in Office 365, utilizzare il parametro-Credential per fornire un account con autorizzazioni sufficienti in Office 365.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-131">If you do not have one account with sufficient permissions in both on-premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="7a9ce-132">Se l'account con le autorizzazioni in Office 365 non termina con "on.microsoft.com", è necessario specificare il parametro-HostedMigrationOverrideUrl con il valore corretto descritto in [credenziali amministrative obbligatorie](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="7a9ce-132">If the account with permissions in Office 365 does not end in “on.microsoft.com”, you must specify the -HostedMigrationOverrideUrl parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="7a9ce-133">La sequenza di cmdlet seguente può essere utilizzata per spostare un utente in Skype for Business Server e presuppone che la credenziale Office 365 sia un account separato e fornito come input per il prompt di Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-133">The following cmdlet sequence can be used to move a user to Skype for Business Server, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a><span data-ttu-id="7a9ce-134">Spostare gli utenti con il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7a9ce-134">Move users with the Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="7a9ce-135">Aprire l'app del pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-135">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="7a9ce-136">Nella barra di spostamento a sinistra, scegliere **utenti**.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-136">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="7a9ce-137">Utilizzare **trova** per individuare gli utenti che si desidera spostare di nuovo in locale.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-137">Use **Find** to locate the user(s) you would like to move back to on-premises.</span></span>
4. <span data-ttu-id="7a9ce-138">Selezionare l'utente o gli utenti, quindi fare clic **su Sposta selezionati in locale**dall'elenco a discesa **azione** .</span><span class="sxs-lookup"><span data-stu-id="7a9ce-138">Select the user(s), and then from the **Action** dropdown above the list, choose **Move selected users to on-premises**.</span></span>
5. <span data-ttu-id="7a9ce-139">Nella procedura guidata, selezionare il pool di utenti che ospiterà l'utente e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-139">In the wizard, select the user pool that will host the user and click **Next**.</span></span>
6. <span data-ttu-id="7a9ce-140">Se richiesto, accedere a Office 365, con un account che termina con. onmicrosoft.com e dispone di autorizzazioni sufficienti.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-140">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="7a9ce-141">Fare clic su **Avanti**e **quindi su Avanti per** spostare l'utente.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-141">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="7a9ce-142">Si noti che i messaggi di stato relativi a esito positivo o negativo sono forniti nella parte superiore dell'app del pannello di controllo principale, non nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-142">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

### <a name="removing-teamsonly-mode"></a><span data-ttu-id="7a9ce-143">Rimozione della modalità TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="7a9ce-143">Removing TeamsOnly mode</span></span>

<span data-ttu-id="7a9ce-144">Se si utilizza una versione precedente a Skype for business 2015 con CU8 e l'utente viene spostato di nuovo in modalità locale in TeamsOnly, è necessario rimuovere l'istanza di UpgradeToTeams prima di `TeamsUpgradePolicy` spostare l'utente locale.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-144">If you are using a version earlier than Skype for Business 2015 with CU8 and the user is being moved back to on-premises in TeamsOnly mode, you must remove the UpgradeToTeams instance of `TeamsUpgradePolicy` before you move the user on-premises.</span></span> <span data-ttu-id="7a9ce-145">È possibile concedere esplicitamente un criterio con una modalità diversa oppure è sufficiente rimuovere l'assegnazione di criteri esistente per l'utente per l'utilizzo dei criteri globali (purché il criterio globale del tenant non sia UpgradeToTeams).</span><span class="sxs-lookup"><span data-stu-id="7a9ce-145">You can either explicitly grant a policy with a different mode or simply remove the existing policy assignment for that user to use the global policy (as long as your tenant’s global policy is not UpgradeToTeams).</span></span>

<span data-ttu-id="7a9ce-146">Per rimuovere l'assegnazione dell'utente di TeamsUpgradePolicy, eseguire il cmdlet seguente da una finestra di PowerShell di Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="7a9ce-146">To remove the user’s assignment of TeamsUpgradePolicy, run the following cmdlet from a Skype for Business Online PowerShell window:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

<span data-ttu-id="7a9ce-147">In alternativa, per assegnare un'altra istanza di TeamsUpgradePolicy che non disponga della modalità = TeamsOnly, è possibile specificare il nome dell'istanza desiderata come valore del parametro PolicyName nel cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-147">Alternatively, to assign another instance of TeamsUpgradePolicy that does not have mode=TeamsOnly, you can specify the name of the desired instance as the value of PolicyName parameter in the cmdlet.</span></span> <span data-ttu-id="7a9ce-148">Per visualizzare un elenco delle istanze disponibili di TeamsUpgradePolicy, eseguire Get-CsTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="7a9ce-148">To see a list of available instances of TeamsUpgradePolicy, run Get-CsTeamsUpgradePolicy.</span></span>


## <a name="see-also"></a><span data-ttu-id="7a9ce-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a9ce-149">See also</span></span>

[<span data-ttu-id="7a9ce-150">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="7a9ce-150">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)
