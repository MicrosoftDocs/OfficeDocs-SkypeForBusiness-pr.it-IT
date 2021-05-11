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
ms.openlocfilehash: e4536b13b6a9c05757bfcbf629fcc8301f94ed86
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305980"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="44e48-103">Spostare utenti da ambiente locale a Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="44e48-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="44e48-104">Dopo aver spostato un utente da locale a Skype for Business Online, l'utente interagisce con Skype for Business Online per le sue funzionalità.</span><span class="sxs-lookup"><span data-stu-id="44e48-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="44e48-105">Tutti i contatti esistenti in locale saranno disponibili in Skype for Business Online e tutte le riunioni esistenti organizzate dall'utente per il futuro verranno aggiornate in modo che i collegamenti puntino a Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="44e48-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="44e48-106">Se l'utente è abilitato per l'audioconferenza, le riunioni includeranno anche le coordinate di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="44e48-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="44e48-107">Per spostare gli utenti da un ambiente locale a Skype for Business Online, utilizzare il cmdlet Move-CsUser o il Pannello di controllo di Skype for Business Server, entrambi strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="44e48-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="44e48-108">Prima di spostare gli utenti, verificare i [prerequisiti](move-users-between-on-premises-and-cloud.md#prerequisites) per spostare gli utenti nel cloud.</span><span class="sxs-lookup"><span data-stu-id="44e48-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="44e48-109">In preparazione del prossimo ritiro di Skype for Business Online, Microsoft semplificherà il passaggio delle organizzazioni a Teams nel prossimo futuro e non sarà più possibile passare a Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="44e48-109">In preparation for the upcoming retirement of Skype for Business Online, Microsoft will be simplifying how organizations move to Teams in the near future and it will no longer be possible to move to Skype for Business Online.</span></span>  <span data-ttu-id="44e48-110">Una volta rese disponibili queste modifiche, quando si sposta un utente dall'ambiente locale al cloud, agli utenti verrà automaticamente assegnata la modalità TeamsOnly e le riunioni dall'ambiente locale verranno convertite automaticamente in riunioni Teams, come se fosse stato specificato il commutatore, indipendentemente dal fatto che il commutatore sia effettivamente `-MoveToTeams` specificato.</span><span class="sxs-lookup"><span data-stu-id="44e48-110">Once these changes are made available, when moving a user from on-premises to the cloud, users will automatically be assigned TeamsOnly mode and their meetings from on-premises will be automtically converted to Teams meetings, just as if the `-MoveToTeams` switch had been specified, regardless of whether the switch is actually specified.</span></span> <span data-ttu-id="44e48-111">Si prevede di rilasciare questa funzionalità prima del ritiro effettivo del 31 luglio 2021.</span><span class="sxs-lookup"><span data-stu-id="44e48-111">We expect to release this functionality before the actual retirement of July 31, 2021.</span></span>   <span data-ttu-id="44e48-112">Attualmente, se questa opzione non è specificata, gli utenti passano da Skype for Business Server locale a Skype for Business Online e la relativa modalità rimane invariata, ovvero la funzionalità documentata in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="44e48-112">Currently if this switch is not specified, users transition from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remains unchanged, which is the functionality documented in this article.</span></span>

 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="44e48-113">Spostare gli utenti con Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="44e48-113">Move users with Move-CsUser</span></span> 

<span data-ttu-id="44e48-114">Move-CsUser è disponibile da una finestra di PowerShell Skype for Business Management Shell locale.</span><span class="sxs-lookup"><span data-stu-id="44e48-114">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="44e48-115">È necessario disporre di privilegi sufficienti sia nell'ambiente locale che nell'organizzazione Microsoft 365, come descritto in [Credenziali amministrative necessarie.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="44e48-115">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="44e48-116">È possibile utilizzare un singolo account con privilegi in entrambi gli ambienti oppure avviare una finestra di Skype for Business Server Management Shell locale con credenziali locali e utilizzare il parametro per specificare le credenziali per un account Microsoft 365 con il ruolo amministrativo `-Credential` necessario.</span><span class="sxs-lookup"><span data-stu-id="44e48-116">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="44e48-117">Per spostare un utente online tramite Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="44e48-117">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="44e48-118">Specificare l'utente da spostare utilizzando il parametro Identity.</span><span class="sxs-lookup"><span data-stu-id="44e48-118">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="44e48-119">Specificare il parametro -Target con il valore "sipfed.online.lync. <span> com".</span><span class="sxs-lookup"><span data-stu-id="44e48-119">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="44e48-120">Se non si dispone di un account con autorizzazioni sufficienti sia in locale che in Microsoft 365, utilizzare il parametro -credential per fornire a un account autorizzazioni sufficienti in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="44e48-120">If you do not have one account with sufficient permissions in both on premises and Microsoft 365, use the -credential parameter to supply an account with sufficient permissions in Microsoft 365.</span></span>
- <span data-ttu-id="44e48-121">Se l'account con autorizzazioni in Microsoft 365 non termina con ".onmicrosoft. <span> com", è quindi necessario specificare il parametro -HostedMigrationOverrideUrl, con il valore corretto come descritto in [Credenziali amministrative obbligatorie.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="44e48-121">If the account with permissions in Microsoft 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="44e48-122">La sequenza di cmdlet seguente può essere utilizzata per spostare un utente in Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="44e48-122">The following cmdlet sequence can be used to move a user to Skype for Business Online.</span></span> <span data-ttu-id="44e48-123">Presuppone che la credenziale Microsoft 365 sia un account separato e fornita come input per il prompt Get-Credential richiesta.</span><span class="sxs-lookup"><span data-stu-id="44e48-123">It assumes the Microsoft 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="44e48-124">Se l'account amministratore è abilitato per L'autenticazione a più fattori( Multi-Factor Authentication), non specificare il parametro -Credential.</span><span class="sxs-lookup"><span data-stu-id="44e48-124">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="44e48-125">All'amministratore verranno richieste le credenziali.</span><span class="sxs-lookup"><span data-stu-id="44e48-125">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="44e48-126">Spostare gli utenti con Skype for Business Server Pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="44e48-126">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="44e48-127">Apri l'Skype for Business Server del Pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="44e48-127">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="44e48-128">Nel riquadro di spostamento sinistro scegliere **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="44e48-128">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="44e48-129">Usa **Trova** per individuare gli utenti che vuoi spostare in Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="44e48-129">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="44e48-130">Selezionare gli utenti e quindi scegliere  Sposta gli utenti selezionati in **Skype for Business Online nell'elenco a discesa Azione sopra l'elenco.**</span><span class="sxs-lookup"><span data-stu-id="44e48-130">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="44e48-131">Nella procedura guidata fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="44e48-131">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="44e48-132">Se richiesto, accedere a Microsoft 365 con un account che termina con .onmicrosoft.com e dispone di autorizzazioni sufficienti.</span><span class="sxs-lookup"><span data-stu-id="44e48-132">If prompted, sign in to Microsoft 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="44e48-133">Fare **clic su** Avanti e **quindi** su Avanti ancora una volta per spostare l'utente.</span><span class="sxs-lookup"><span data-stu-id="44e48-133">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="44e48-134">Tieni presente che i messaggi di stato relativi all'esito positivo o negativo vengono forniti nella parte superiore dell'app principale del Pannello di controllo, non nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="44e48-134">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="44e48-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44e48-135">See also</span></span>

[<span data-ttu-id="44e48-136">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="44e48-136">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)
