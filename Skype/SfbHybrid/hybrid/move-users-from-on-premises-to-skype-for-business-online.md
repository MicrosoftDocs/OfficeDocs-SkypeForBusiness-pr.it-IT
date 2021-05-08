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
ms.openlocfilehash: 8c028044fe8c4b808a419503091f9ecf767cfe4d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237962"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="cf5a0-103">Spostare utenti da ambiente locale a Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cf5a0-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="cf5a0-104">Dopo aver spostato un utente da locale a Skype for Business Online, l'utente interagisce con Skype for Business Online per le sue funzionalità.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="cf5a0-105">Tutti i contatti esistenti in locale saranno disponibili in Skype for Business Online e tutte le riunioni esistenti organizzate dall'utente per il futuro verranno aggiornate in modo che i collegamenti puntino a Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="cf5a0-106">Se l'utente è abilitato per l'audioconferenza, le riunioni includeranno anche le coordinate di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="cf5a0-107">Per spostare gli utenti da un ambiente locale a Skype for Business Online, utilizzare il cmdlet Move-CsUser o il Pannello di controllo di Skype for Business Server, entrambi strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="cf5a0-108">Prima di spostare gli utenti, verificare i [prerequisiti](move-users-between-on-premises-and-cloud.md#prerequisites) per spostare gli utenti nel cloud.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="cf5a0-109">Spostare gli utenti con Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="cf5a0-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="cf5a0-110">Move-CsUser è disponibile da una finestra di PowerShell Skype for Business Management Shell locale.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="cf5a0-111">È necessario disporre di privilegi sufficienti sia nell'ambiente locale che nell'organizzazione Microsoft 365/Office 365, come descritto in [Credenziali amministrative necessarie.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="cf5a0-111">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365/Office 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="cf5a0-112">È possibile utilizzare un singolo account con privilegi in entrambi gli ambienti oppure avviare una finestra di Skype for Business Server Management Shell locale con credenziali locali e utilizzare il parametro per specificare le credenziali per un account Microsoft 365 o Office 365 con il ruolo amministrativo `-Credential` necessario.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-112">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="cf5a0-113">Per spostare un utente online tramite Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="cf5a0-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="cf5a0-114">Specificare l'utente da spostare utilizzando il parametro Identity.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="cf5a0-115">Specificare il parametro -Target con il valore "sipfed.online.lync. <span> com".</span><span class="sxs-lookup"><span data-stu-id="cf5a0-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="cf5a0-116">Se non si dispone di un account con autorizzazioni sufficienti sia in locale che in Office 365, utilizzare il parametro -credential per fornire a un account autorizzazioni sufficienti in Office 365.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="cf5a0-117">Se l'account con autorizzazioni in Office 365 non termina con ".onmicrosoft. <span> com", è quindi necessario specificare il parametro -HostedMigrationOverrideUrl, con il valore corretto come descritto in [Credenziali amministrative obbligatorie.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="cf5a0-117">If the account with permissions in Office 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="cf5a0-118">La sequenza di cmdlet seguente può essere utilizzata per spostare un utente in Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-118">The following cmdlet sequence can be used to move a user to Skype for Business Online.</span></span> <span data-ttu-id="cf5a0-119">Presuppone che la Microsoft 365 o Office 365 sia un account separato e fornita come input per il prompt Get-Credential richiesta.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-119">It assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="cf5a0-120">Se l'account amministratore è abilitato per L'autenticazione a più fattori( Multi-Factor Authentication), non specificare il parametro -Credential.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-120">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="cf5a0-121">All'amministratore verranno richieste le credenziali.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-121">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="cf5a0-122">Spostare gli utenti con Skype for Business Server Pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="cf5a0-122">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="cf5a0-123">Apri l'Skype for Business Server del Pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-123">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="cf5a0-124">Nel riquadro di spostamento sinistro scegliere **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-124">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="cf5a0-125">Usa **Trova** per individuare gli utenti che vuoi spostare in Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-125">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="cf5a0-126">Selezionare gli utenti e quindi scegliere  Sposta gli utenti selezionati in **Skype for Business Online nell'elenco a discesa Azione sopra l'elenco.**</span><span class="sxs-lookup"><span data-stu-id="cf5a0-126">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="cf5a0-127">Nella procedura guidata fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-127">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="cf5a0-128">Se richiesto, accedere a Microsoft 365 o Office 365 con un account che termina con .onmicrosoft.com e dispone di autorizzazioni sufficienti.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-128">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="cf5a0-129">Fare **clic su** Avanti e **quindi** su Avanti ancora una volta per spostare l'utente.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-129">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="cf5a0-130">Tieni presente che i messaggi di stato relativi all'esito positivo o negativo vengono forniti nella parte superiore dell'app principale del Pannello di controllo, non nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="cf5a0-130">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf5a0-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf5a0-131">See also</span></span>

[<span data-ttu-id="cf5a0-132">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="cf5a0-132">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)