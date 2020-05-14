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
description: Informazioni su come spostare gli utenti in Skype for business online.
ms.openlocfilehash: a9fb80046195580daca6dfc7f810b2e0c1877f1c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221116"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="460d7-103">Spostare utenti da ambiente locale a Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="460d7-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="460d7-104">Dopo aver spostato un utente da locale a Skype for business online, l'utente interagisce con Skype for business online per la sua funzionalità.</span><span class="sxs-lookup"><span data-stu-id="460d7-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="460d7-105">Tutti i contatti che esistevano in locale saranno disponibili in Skype for business online e tutte le riunioni esistenti che l'utente organizzerà per il futuro verranno aggiornate in modo che i collegamenti puntino a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="460d7-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="460d7-106">Se l'utente è abilitato per l'audioconferenza, le riunioni includeranno anche le coordinate di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="460d7-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="460d7-107">Per spostare gli utenti da un ambiente locale a Skype for business online, utilizzare il cmdlet Move-CsUser o il pannello di controllo di Skype for Business Server, entrambi strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="460d7-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="460d7-108">Prima di spostare gli utenti, assicurarsi di esaminare i [prerequisiti](move-users-between-on-premises-and-cloud.md#prerequisites) per spostare gli utenti nel cloud.</span><span class="sxs-lookup"><span data-stu-id="460d7-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="460d7-109">Spostare gli utenti con Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="460d7-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="460d7-110">Move-CsUser è disponibile da una finestra di PowerShell della shell di gestione di Skype for business locale.</span><span class="sxs-lookup"><span data-stu-id="460d7-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="460d7-111">È necessario disporre di privilegi sufficienti sia nell'ambiente locale sia nell'organizzazione di Microsoft 365/Office 365, come descritto in [credenziali amministrative obbligatorie](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="460d7-111">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365/Office 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="460d7-112">È possibile utilizzare un singolo account che disponga di privilegi in entrambi gli ambienti oppure è possibile avviare una finestra della shell di gestione di Skype for Business Server locale con le credenziali locali e utilizzare il `-Credential` parametro per specificare le credenziali di un account di Microsoft 365 o di Office 365 con il ruolo amministrativo necessario.</span><span class="sxs-lookup"><span data-stu-id="460d7-112">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="460d7-113">Per spostare un utente in online tramite Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="460d7-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="460d7-114">Specificare l'utente da spostare utilizzando il parametro Identity.</span><span class="sxs-lookup"><span data-stu-id="460d7-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="460d7-115">Specificare il parametro-target con il valore "sipfed. online. Lync. <span> com ".</span><span class="sxs-lookup"><span data-stu-id="460d7-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="460d7-116">Se non si dispone di un account con autorizzazioni sufficienti sia in locale che in Office 365, utilizzare il parametro-Credential per fornire un account con autorizzazioni sufficienti in Office 365.</span><span class="sxs-lookup"><span data-stu-id="460d7-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="460d7-117">Se l'account con le autorizzazioni in Office 365 non termina in ". onmicrosoft. <span> com ", è necessario specificare il parametro-HostedMigrationOverrideUrl, con il valore corretto come descritto in [credenziali amministrative obbligatorie](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="460d7-117">If the account with permissions in Office 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="460d7-118">Per spostare un utente in Skype for business online, è possibile utilizzare la sequenza di cmdlet seguente.</span><span class="sxs-lookup"><span data-stu-id="460d7-118">The following cmdlet sequence can be used to move a user to Skype for Business Online.</span></span> <span data-ttu-id="460d7-119">Si presuppone che la credenziale Microsoft 365 o Office 365 sia un account separato e fornito come input per il prompt di Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="460d7-119">It assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="460d7-120">Se l'account Administrator è Mae (multi-factor authentication) abilitato, non specificare il parametro-Credential.</span><span class="sxs-lookup"><span data-stu-id="460d7-120">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="460d7-121">All'amministratore verranno richieste le credenziali.</span><span class="sxs-lookup"><span data-stu-id="460d7-121">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="460d7-122">Spostare gli utenti con il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="460d7-122">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="460d7-123">Aprire l'app del pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="460d7-123">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="460d7-124">Nella barra di spostamento a sinistra, scegliere **utenti**.</span><span class="sxs-lookup"><span data-stu-id="460d7-124">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="460d7-125">Utilizzare **trova** per individuare gli utenti che si desidera spostare in Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="460d7-125">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="460d7-126">Selezionare l'utente o gli utenti e quindi, nell'elenco a discesa **azione** sopra la lista, scegliere **Move users selected to Skype for business online**.</span><span class="sxs-lookup"><span data-stu-id="460d7-126">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="460d7-127">Nella procedura guidata fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="460d7-127">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="460d7-128">Se richiesto, accedere a Microsoft 365 o Office 365 con un account che termina con. onmicrosoft.com e dispone di autorizzazioni sufficienti.</span><span class="sxs-lookup"><span data-stu-id="460d7-128">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="460d7-129">Fare clic su **Avanti**e **quindi su Avanti per** spostare l'utente.</span><span class="sxs-lookup"><span data-stu-id="460d7-129">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="460d7-130">Si noti che i messaggi di stato relativi a esito positivo o negativo sono forniti nella parte superiore dell'app del pannello di controllo principale, non nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="460d7-130">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="460d7-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="460d7-131">See also</span></span>

[<span data-ttu-id="460d7-132">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="460d7-132">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)
