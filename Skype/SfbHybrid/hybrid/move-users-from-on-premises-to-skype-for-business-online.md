---
title: Spostare utenti da ambiente locale a Skype for Business Online
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
description: Informazioni su come spostare gli utenti in Skype for Business Online.
ms.openlocfilehash: 883db98a424c254e6792fd651594b02201a311f9
ms.sourcegitcommit: 2591c96d8613660220c5af71fc945e27b31175d7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "52863197"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="ff253-103">Spostare utenti da ambiente locale a Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ff253-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="ff253-104">Dopo aver spostato un utente da locale a Skype for Business Online, l'utente interagisce con Skype for Business Online per le sue funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ff253-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="ff253-105">Tutti i contatti esistenti in locale saranno disponibili in Skype for Business Online e tutte le riunioni esistenti organizzate dall'utente per il futuro verranno aggiornate in modo che i collegamenti puntino a Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="ff253-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="ff253-106">Se l'utente è abilitato per l'audioconferenza, le riunioni includeranno anche le coordinate di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="ff253-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="ff253-107">Per spostare gli utenti da un ambiente locale a Skype for Business Online, utilizzare il cmdlet Move-CsUser o il Pannello di controllo di Skype for Business Server, entrambi strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="ff253-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="ff253-108">Prima di spostare gli utenti, verificare i [prerequisiti](move-users-between-on-premises-and-cloud.md#prerequisites) per spostare gli utenti nel cloud.</span><span class="sxs-lookup"><span data-stu-id="ff253-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="ff253-109">In preparazione del prossimo ritiro di Skype for Business Online, Microsoft ha semplificato il modo in cui le organizzazioni passano a Teams.</span><span class="sxs-lookup"><span data-stu-id="ff253-109">In preparation for the upcoming retirement of Skype for Business Online, Microsoft has simplified how organizations move to Teams.</span></span> <span data-ttu-id="ff253-110">Quando si spostano gli utenti dall'ambiente locale al cloud, agli utenti viene automaticamente assegnata la modalità TeamsOnly e le riunioni dall'ambiente locale vengono convertite automaticamente in riunioni Teams, come se fosse stato specificato il commutatore, indipendentemente dal fatto che il commutatore sia stato effettivamente `-MoveToTeams` specificato.</span><span class="sxs-lookup"><span data-stu-id="ff253-110">When moving users from on-premises to the cloud, users are now automatically assigned TeamsOnly mode and their meetings from on-premises are automtically converted to Teams meetings, just as if the `-MoveToTeams` switch had been specified, regardless of whether the switch was actually specified.</span></span>  <span data-ttu-id="ff253-111">Prima del ritiro di Skype for Business Online, le organizzazioni che richiedono lo spostamento degli utenti da locale a Skype for Business Online possono ottenere questo risultato in due passaggi aggiornando la modalità dell'utente dopo che l'utente è stato spostato in *TeamsOnly.*</span><span class="sxs-lookup"><span data-stu-id="ff253-111">Prior to retirement of Skype for Business Online, organizations that require moving users from on-premises to Skype for Business Online can achieve this in two steps by updating the user's mode *after the user is moved to TeamsOnly*.</span></span> <span data-ttu-id="ff253-112">Tuttavia, nel prossimo futuro, non sarà più possibile assegnare una modalità diversa da TeamsOnly agli utenti ospitati nel cloud.</span><span class="sxs-lookup"><span data-stu-id="ff253-112">However in the near future, it will no longer be possible to assign a mode other than TeamsOnly to users homed in the cloud.</span></span>  
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="ff253-113">Spostare gli utenti con Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="ff253-113">Move users with Move-CsUser</span></span> 

<span data-ttu-id="ff253-114">Move-CsUser è disponibile da una finestra di PowerShell Skype for Business Management Shell locale.</span><span class="sxs-lookup"><span data-stu-id="ff253-114">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="ff253-115">È necessario disporre di privilegi sufficienti sia nell'ambiente locale che nell'organizzazione Microsoft 365, come descritto in [Credenziali amministrative necessarie.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="ff253-115">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="ff253-116">È possibile utilizzare un singolo account con privilegi in entrambi gli ambienti oppure avviare una finestra di Skype for Business Server Management Shell locale con credenziali locali e utilizzare il parametro per specificare le credenziali per un account Microsoft 365 con il ruolo amministrativo `-Credential` necessario.</span><span class="sxs-lookup"><span data-stu-id="ff253-116">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="ff253-117">Per spostare un utente online tramite Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="ff253-117">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="ff253-118">Specificare l'utente da spostare utilizzando il parametro Identity.</span><span class="sxs-lookup"><span data-stu-id="ff253-118">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="ff253-119">Specificare il parametro -Target con il valore "sipfed.online.lync. <span> com".</span><span class="sxs-lookup"><span data-stu-id="ff253-119">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="ff253-120">Se non si dispone di un account con autorizzazioni sufficienti sia in locale che in Microsoft 365, utilizzare il parametro -credential per fornire a un account autorizzazioni sufficienti in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ff253-120">If you do not have one account with sufficient permissions in both on premises and Microsoft 365, use the -credential parameter to supply an account with sufficient permissions in Microsoft 365.</span></span>
- <span data-ttu-id="ff253-121">Se l'account con autorizzazioni in Microsoft 365 non termina con ".onmicrosoft. <span> com", è quindi necessario specificare il parametro -HostedMigrationOverrideUrl, con il valore corretto come descritto in [Credenziali amministrative obbligatorie.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="ff253-121">If the account with permissions in Microsoft 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="ff253-122">La sequenza di cmdlet seguente può essere utilizzata per spostare un utente in Skype for Business Online e assegnare la modalità predefinita tenant all'utente.</span><span class="sxs-lookup"><span data-stu-id="ff253-122">The following cmdlet sequence can be used to move a user to Skype for Business Online and assigns the tenant default mode to the user.</span></span> <span data-ttu-id="ff253-123">Presuppone che la credenziale Microsoft 365 sia un account separato e fornita come input per il prompt Get-Credential richiesta.</span><span class="sxs-lookup"><span data-stu-id="ff253-123">It assumes the Microsoft 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
# From an on-premises Skype for Business Server or Lync Server 2013 management shell window, run:
 
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
 
# And then from a Teams PowerShell window, remove TeamsOnly mode by running: 
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName $null
```

<span data-ttu-id="ff253-124">Se l'account amministratore è abilitato per L'autenticazione a più fattori( Multi-Factor Authentication), non specificare il parametro -Credential.</span><span class="sxs-lookup"><span data-stu-id="ff253-124">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="ff253-125">All'amministratore verranno richieste le credenziali.</span><span class="sxs-lookup"><span data-stu-id="ff253-125">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel-and-teams-admin-center"></a><span data-ttu-id="ff253-126">Spostare gli utenti con Skype for Business Server pannello di controllo e Teams di amministrazione</span><span class="sxs-lookup"><span data-stu-id="ff253-126">Move users with Skype for Business Server Control Panel and Teams Admin Center</span></span>

1. <span data-ttu-id="ff253-127">Apri l'Skype for Business Server del Pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="ff253-127">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="ff253-128">Nel riquadro di spostamento sinistro scegliere **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="ff253-128">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="ff253-129">Usa **Trova** per individuare gli utenti che vuoi spostare in Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="ff253-129">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="ff253-130">Selezionare gli utenti e quindi nell'elenco a discesa Azione sopra l'elenco scegliere Sposta gli utenti selezionati **in Skype for Business Online** o Sposta gli utenti selezionati in **Teams**. </span><span class="sxs-lookup"><span data-stu-id="ff253-130">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online** or **Move selected users to Teams**.</span></span> <span data-ttu-id="ff253-131">Entrambe le opzioni inizialmente spostano l'utente in modalità TeamsOnly, ma dopo lo spostamento puoi assegnare un'altra modalità.</span><span class="sxs-lookup"><span data-stu-id="ff253-131">Either option will initially move the user to TeamsOnly mode but after the move you can assign another mode.</span></span> 
5. <span data-ttu-id="ff253-132">Nella procedura guidata fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ff253-132">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="ff253-133">Se richiesto, accedere a Microsoft 365 con un account che termina con .onmicrosoft.com e dispone di autorizzazioni sufficienti.</span><span class="sxs-lookup"><span data-stu-id="ff253-133">If prompted, sign in to Microsoft 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="ff253-134">Fare **clic su** Avanti e **quindi** su Avanti ancora una volta per spostare l'utente.</span><span class="sxs-lookup"><span data-stu-id="ff253-134">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="ff253-135">Tieni presente che i messaggi di stato relativi all'esito positivo o negativo vengono forniti nella parte superiore dell'app principale del Pannello di controllo, non nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="ff253-135">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>
9. <span data-ttu-id="ff253-136">Apri l Teams'interfaccia di amministrazione e seleziona "Utenti" nel riquadro di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="ff253-136">Open the Teams Admin Center and select "Users" in the left hand navigation.</span></span> 
10. <span data-ttu-id="ff253-137">Fai clic sull'utente desiderato nella visualizzazione elenco.</span><span class="sxs-lookup"><span data-stu-id="ff253-137">Click on the desired user in the listview.</span></span> 
11. <span data-ttu-id="ff253-138">Fare clic **su** Modifica nella sezione che indica **Teams aggiornamento**.</span><span class="sxs-lookup"><span data-stu-id="ff253-138">Click the **Edit** in the section that says **Teams upgrade**.</span></span>
12. <span data-ttu-id="ff253-139">Nel riquadro a comparsa a destra selezionare la modalità di coesistenza desiderata e fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="ff253-139">In the right-hand flyout, select the desired coexistence mode and click **Apply**.</span></span>
 

## <a name="see-also"></a><span data-ttu-id="ff253-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff253-140">See also</span></span>

[<span data-ttu-id="ff253-141">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="ff253-141">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)
