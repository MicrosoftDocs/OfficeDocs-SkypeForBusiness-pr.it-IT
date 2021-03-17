---
title: Spostare gli utenti da Skype for Business Server 2019 a Teams
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
description: 'Riepilogo: informazioni su come eseguire la migrazione delle impostazioni utente e spostare gli utenti in Teams.'
ms.openlocfilehash: c84cdbe5f91816ddfabd476540e47f3d1871a427
ms.sourcegitcommit: 360c78c66386fe00afe535681f51254eda886edf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/17/2021
ms.locfileid: "50836983"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="740c1-103">Spostare utenti da ambiente locale a Teams</span><span class="sxs-lookup"><span data-stu-id="740c1-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="740c1-104">Quando un utente viene spostato da locale a Solo Teams, la home page di Skype for Business dell'utente viene spostata da locale a online e all'utente viene assegnato TeamsUpgradePolicy con mode=TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="740c1-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="740c1-105">Dopo lo spostamento di un utente dalla modalità locale alla modalità TeamsOnly:</span><span class="sxs-lookup"><span data-stu-id="740c1-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="740c1-106">Tutte le chiamate in arrivo e le chat di altri utenti (inviate da Skype for Business o Teams) verranno inviate nel client Teams dell'utente.</span><span class="sxs-lookup"><span data-stu-id="740c1-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="740c1-107">L'utente sarà in grado di interagire con altri utenti che usano Skype for Business (online o in locale).</span><span class="sxs-lookup"><span data-stu-id="740c1-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span>
- <span data-ttu-id="740c1-108">L'utente sarà in grado di comunicare con gli utenti nelle organizzazioni federate.</span><span class="sxs-lookup"><span data-stu-id="740c1-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="740c1-109">Le nuove riunioni pianificate dall'utente sono riunioni di Teams.</span><span class="sxs-lookup"><span data-stu-id="740c1-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="740c1-110">L'utente può comunque partecipare a qualsiasi riunione Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="740c1-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="740c1-111">Le riunioni preesiste dell'utente pianificate per il futuro verranno migrate da locale a Teams.</span><span class="sxs-lookup"><span data-stu-id="740c1-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Teams.</span></span>
- <span data-ttu-id="740c1-112">I contatti esistenti in locale sono disponibili in Teams poco dopo l'accesso dell'utente per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="740c1-112">Contacts that existed on-premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="740c1-113">Gli utenti non possono avviare chiamate o chat da Skype for Business, né possono pianificare nuove riunioni in Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="740c1-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="740c1-114">Se tentano di aprire il client Skype for Business, verranno reindirizzati all'uso di Teams come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="740c1-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="740c1-115">Se il client Teams non è installato, verrà indirizzato alla versione Web di Teams utilizzando il browser.</span><span class="sxs-lookup"><span data-stu-id="740c1-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="740c1-116">![Messaggio che reindirizza un utente a Teams](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="740c1-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="740c1-117">Prima di spostare gli utenti, verificare i [prerequisiti](move-users-between-on-premises-and-cloud.md#prerequisites) per spostare gli utenti nel cloud.</span><span class="sxs-lookup"><span data-stu-id="740c1-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="740c1-118">Assicurati inoltre di consultare le indicazioni [sulla migrazione e l'interoperabilità](/microsoftteams/migration-interop-guidance-for-teams-with-skype)per le organizzazioni che usano Teams insieme a Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="740c1-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>


> [!NOTE]
> <span data-ttu-id="740c1-119">L'archivio contatti unificato deve essere disabilitato nell'account SfB locale per il contatto da spostare in Teams.</span><span class="sxs-lookup"><span data-stu-id="740c1-119">Unified Contact Store should be disabled on the on-prem SfB account for the contact to be moved to Teams.</span></span>


<span data-ttu-id="740c1-120">Esistono due metodi per spostare un utente da locale a Teams:</span><span class="sxs-lookup"><span data-stu-id="740c1-120">There are two methods to move a user from on premises to Teams:</span></span>

- <span data-ttu-id="740c1-121">Se si utilizza una versione precedente a Skype for Business Server 2015 CU8, lo spostamento richiede due passaggi (che possono essere scriptati insieme come singolo passaggio, se lo si desidera):</span><span class="sxs-lookup"><span data-stu-id="740c1-121">If you are using a version earlier than Skype for Business Server 2015 CU8, the move requires two steps (which can be scripted to be done together as a single step, if desired):</span></span>
  - <span data-ttu-id="740c1-122">[Spostare l'utente da Skype for Business Server (locale) a Skype for Business online.](move-users-from-on-premises-to-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="740c1-122">[Move the user from Skype for Business Server (on premises) to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>
  - <span data-ttu-id="740c1-123">Una volta che l'utente si trova in Skype for Business online, assegna all'utente TeamsUpgradePolicy con mode= TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="740c1-123">Once the user is homed in Skype for Business Online, assign the user TeamsUpgradePolicy with mode= TeamsOnly.</span></span> <span data-ttu-id="740c1-124">Per concedere la modalità TeamsOnly, eseguire il cmdlet seguente da una finestra di PowerShell di Skype for Business online: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span><span class="sxs-lookup"><span data-stu-id="740c1-124">To grant TeamsOnly mode, run the following cmdlet from a Skype for Business Online PowerShell window: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span></span>
- <span data-ttu-id="740c1-125">Se si dispone di strumenti di amministrazione da Skype for Business Server 2015 CU8 o versioni successive, è possibile utilizzare il metodo precedente oppure è possibile eseguire questo spostamento in un passaggio come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="740c1-125">If you have admin tools from Skype for Business Server 2015 CU8 or later, you can use the method above, or you can do this move in one step as described below.</span></span> <span data-ttu-id="740c1-126">Inoltre, puoi facoltativamente fornire una notifica all'interno del client Skype for Business prima di spostarli in Solo Teams, nonché facoltativamente scaricare il client Teams in modo invisibile all'utente dal client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="740c1-126">In addition, you can optionally provide a notification within the Skype for Business client prior to moving them to Teams Only as well as optionally have the Teams client silently downloaded by the Skype for Business client.</span></span>

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="740c1-127">Spostare un utente direttamente da Skype for Business locale solo a Teams</span><span class="sxs-lookup"><span data-stu-id="740c1-127">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="740c1-128">Gli strumenti di amministrazione locali in Skype for Business Server 2015 con CU8, nonché in Skype for Business Server 2019, consentono di spostare gli utenti dalla modalità locale alla modalità Solo Teams in un singolo passaggio utilizzando il cmdlet Move-CsUser in PowerShell o il Pannello di controllo di Skype for Business Server, come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="740c1-128">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to move users from on premises to Teams Only mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="740c1-129">Passare a Teams usando Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="740c1-129">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="740c1-130">Move-CsUser è disponibile da una finestra di PowerShell di Skype for Business Management Shell locale.</span><span class="sxs-lookup"><span data-stu-id="740c1-130">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="740c1-131">I passaggi seguenti e le autorizzazioni necessarie sono gli stessi dello spostamento di un utente in Skype for Business online, tranne per il fatto che è necessario specificare anche l'opzione MoveToTeams ed è necessario assicurarsi che all'utente sia stata concessa anche una licenza per Teams (oltre a Skype for Business online).</span><span class="sxs-lookup"><span data-stu-id="740c1-131">The steps below and permissions required are the same as moving a user to Skype for Business Online, except that you must also specify the MoveToTeams switch and you must ensure that the user has also been granted a license for Teams (in addition to Skype for Business Online).</span></span>

<span data-ttu-id="740c1-132">È necessario disporre di privilegi sufficienti sia nell'ambiente locale che nel servizio cloud (Microsoft 365 o Office 365), come descritto in [Credenziali amministrative necessarie.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="740c1-132">You must have sufficient privileges in both the on-premises environment and the cloud service (Microsoft 365 or Office 365), as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="740c1-133">È possibile utilizzare un singolo account con privilegi in entrambi gli ambienti oppure avviare una finestra di Skype for Business Server Management Shell locale con credenziali locali e utilizzare il parametro per specificare le credenziali per un `-Credential` account di Microsoft 365 o Office 365 con il ruolo amministrativo necessario.</span><span class="sxs-lookup"><span data-stu-id="740c1-133">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="740c1-134">Per spostare un utente in modalità Solo Teams tramite Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="740c1-134">To move a user to Teams Only mode using Move-CsUser:</span></span>

- <span data-ttu-id="740c1-135">Specificare l'utente da spostare utilizzando il `Identity` parametro .</span><span class="sxs-lookup"><span data-stu-id="740c1-135">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="740c1-136">Specificare il parametro -Target con il valore "sipfed.online.lync. <span> com".</span><span class="sxs-lookup"><span data-stu-id="740c1-136">Specify the     -Target     parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="740c1-137">Specificare `MoveToTeams` l'opzione.</span><span class="sxs-lookup"><span data-stu-id="740c1-137">Specify the `MoveToTeams` switch.</span></span>
- <span data-ttu-id="740c1-138">Se non si dispone di un account con autorizzazioni sufficienti sia in locale che nel servizio cloud (Microsoft 365 o Office 365), utilizzare il parametro per fornire a un account autorizzazioni sufficienti `-credential` in Office 365.</span><span class="sxs-lookup"><span data-stu-id="740c1-138">If you do not have one account with sufficient permissions in both on premises and the cloud service (Microsoft 365 or Office 365), use the `-credential` parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="740c1-139">Se l'account con autorizzazioni in Microsoft 365 o Office 365 non termina con "onmicrosoft. <span> com", è necessario specificare il parametro con il valore corretto come `-HostedMigrationOverrideUrl` descritto in Credenziali amministrative [obbligatorie.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="740c1-139">If the account with permissions in Microsoft 365 or Office 365 does not end in “onmicrosoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="740c1-140">La sequenza di cmdlet seguente può essere utilizzata per spostare un utente in TeamsOnly e presuppone che la credenziale di Microsoft 365 o Office 365 sia un account separato e fornita come input per il prompt di Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="740c1-140">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> <span data-ttu-id="740c1-141">Poiché esistono diverse circostanze che richiedono parametri diversi, il comando predefinito per la maggior parte dei casi è:</span><span class="sxs-lookup"><span data-stu-id="740c1-141">As there are different circumstances requiring different parameters, the default command for most cases is:</span></span>

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="740c1-142">Passare a Teams usando il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="740c1-142">Move to Teams using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="740c1-143">Apri l'app Del Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="740c1-143">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="740c1-144">Nel riquadro di spostamento sinistro scegliere **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="740c1-144">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="740c1-145">Utilizzare **Trova** per individuare gli utenti che si desidera spostare in Teams.</span><span class="sxs-lookup"><span data-stu-id="740c1-145">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4. <span data-ttu-id="740c1-146">Selezionare gli utenti e quindi scegliere  Sposta gli utenti selezionati in Teams nell'elenco a discesa **Azione sopra l'elenco.**</span><span class="sxs-lookup"><span data-stu-id="740c1-146">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams**.</span></span>
5. <span data-ttu-id="740c1-147">Nella procedura guidata fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="740c1-147">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="740c1-148">Se richiesto, accedere a Microsoft 365 o Office 365 con un account che termina con .onmicrosoft.com e dispone di autorizzazioni sufficienti.</span><span class="sxs-lookup"><span data-stu-id="740c1-148">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="740c1-149">Fare **clic su** Avanti e **quindi** su Avanti ancora una volta per spostare l'utente.</span><span class="sxs-lookup"><span data-stu-id="740c1-149">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="740c1-150">Tieni presente che i messaggi di stato relativi all'esito positivo o negativo vengono forniti nella parte superiore dell'app principale del Pannello di controllo, non nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="740c1-150">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="740c1-151">Informare gli utenti locali di Skype for Business del passaggio imminente a Teams</span><span class="sxs-lookup"><span data-stu-id="740c1-151">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="740c1-152">Gli strumenti di amministrazione locali in Skype for Business Server 2015 con CU8, nonché in Skype for Business Server 2019, consentono di informare gli utenti di Skype for Business locali del loro prossimo passaggio a Teams.</span><span class="sxs-lookup"><span data-stu-id="740c1-152">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="740c1-153">Quando abiliti queste notifiche, gli utenti visualizzano una notifica nel client Skype for Business (Win32, Mac, Web e dispositivi mobili), come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="740c1-153">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="740c1-154">Se gli utenti fa **clic sul** pulsante Prova, il client Teams verrà avviato se è installato. in caso contrario, gli utenti verranno spostati alla versione Web di Teams nel browser.</span><span class="sxs-lookup"><span data-stu-id="740c1-154">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="740c1-155">Per impostazione predefinita, quando le notifiche sono abilitate, i client Skype for Business Win32 scaricano automaticamente il client Teams in modo che il rich client sia disponibile prima di spostare l'utente in modalità Solo Teams; tuttavia, è anche possibile disabilitare questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="740c1-155">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to Teams Only mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="740c1-156">Le notifiche vengono configurate utilizzando la versione locale di e il download invisibile all'utente per i client Win32 viene controllato tramite il `TeamsUpgradePolicy` `TeamsUpgradeConfiguration` cmdlet locale.</span><span class="sxs-lookup"><span data-stu-id="740c1-156">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

> [!TIP]
> <span data-ttu-id="740c1-157">Alcuni server potrebbero dover riavviare il sistema per funzionare in Skype for Business 2015 con CU8.</span><span class="sxs-lookup"><span data-stu-id="740c1-157">Some servers may need to reboot for this to work in Skype for Business 2015 with CU8.</span></span>

![Notifica del passaggio imminente a Teams](../media/teams-upgrade-notification.png)

<span data-ttu-id="740c1-159">Per notificare agli utenti locali che saranno presto aggiornati a Teams, creare una nuova istanza di TeamsUpgradePolicy con NotifySfBUsers=true.</span><span class="sxs-lookup"><span data-stu-id="740c1-159">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="740c1-160">Assegnare quindi tale criterio agli utenti a cui si desidera inviare una notifica, assegnando il criterio direttamente all'utente o impostando il criterio a livello di sito, pool o globale.</span><span class="sxs-lookup"><span data-stu-id="740c1-160">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="740c1-161">I cmdlet seguenti creano e concedono un criterio a livello di utente:</span><span class="sxs-lookup"><span data-stu-id="740c1-161">The following cmdlets create and grant a user-level policy:</span></span>

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="740c1-162">Il download automatico di Teams tramite il client Win32 di Skype for Business viene controllato tramite il cmdlet TeamsUpgradeConfiguration locale con il parametro DownloadTeams.</span><span class="sxs-lookup"><span data-stu-id="740c1-162">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="740c1-163">Questa configurazione viene creata a livello globale, di sito e di pool.</span><span class="sxs-lookup"><span data-stu-id="740c1-163">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="740c1-164">Ad esempio, il comando seguente crea la configurazione per il sito Redmond1:</span><span class="sxs-lookup"><span data-stu-id="740c1-164">For example, the following command creates the configuration for the site Redmond1:</span></span>

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

<span data-ttu-id="740c1-165">Per impostazione predefinita, il valore di DownloadTeams è True. tuttavia, viene *rispettato* solo se NotifySfbUser = True per un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="740c1-165">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>

## <a name="see-also"></a><span data-ttu-id="740c1-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="740c1-166">See also</span></span>

[<span data-ttu-id="740c1-167">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="740c1-167">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[<span data-ttu-id="740c1-168">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="740c1-168">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="740c1-169">Linee guida per la migrazione e l'interoperabilità di organizzazioni che usano Teams insieme a Skype for Business</span><span class="sxs-lookup"><span data-stu-id="740c1-169">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="740c1-170">Coesistenza con Skype for Business</span><span class="sxs-lookup"><span data-stu-id="740c1-170">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)
