---
title: Disattivazione di numeri verdi per utenti specifici
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Gli amministratori possono controllare gli organizzatori utilizzo numeri verdi per le riunioni.
ms.openlocfilehash: a63078256ac9ac52b3d405bd3cf1b63120fb77ce
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="2f905-103">Disattivazione di numeri verdi per utenti specifici</span><span class="sxs-lookup"><span data-stu-id="2f905-103">Disabling toll-free numbers for specific users</span></span>

<span data-ttu-id="2f905-104">Se l'organizzazione dispone di numeri verdi nel relativo Audio Conferencing Bridge Microsoft, è possibile consentire o impedire loro utilizzo in riunioni degli organizzatori specifici.</span><span class="sxs-lookup"><span data-stu-id="2f905-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="2f905-105">Per impostazione predefinita, tutti gli utenti nell'organizzazione sono abilitati per l'utilizzo di numeri verdi, ovvero i numeri, se disponibile, possono essere utilizzati dai partecipanti per partecipare alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="2f905-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="2f905-106">Se non è il comportamento desiderato per alcuni utenti all'interno dell'organizzazione, è possibile limitare gli utenti specifici di utilizzare tali numeri relativi alle riunioni tramite un controllo di attivazione dei numerico verdi.</span><span class="sxs-lookup"><span data-stu-id="2f905-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="2f905-107">Numeri verdi quando sono disabilitati per organizzare una determinata:</span><span class="sxs-lookup"><span data-stu-id="2f905-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="2f905-108">Un numero verde non verrà non è più incluso nel suo o verrà invita.</span><span class="sxs-lookup"><span data-stu-id="2f905-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="2f905-109">Non è più numeri verdi verranno elencati nella pagina "Trova un numero locale" viene fatto riferimento nel suo o verrà invita.</span><span class="sxs-lookup"><span data-stu-id="2f905-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="2f905-110">I partecipanti saranno in grado di partecipare alla riunione dell'organizzatore determinato se è comporre un numero verde dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2f905-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="2f905-111">Tutte le riunioni dell'organizzatore ripianificate automaticamente e verrà rimossa il numero verde.</span><span class="sxs-lookup"><span data-stu-id="2f905-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="2f905-112">Si verrà nuovamente tutti gli inviti di posta elettronica dell'organizzatore inviato a tutti i partecipanti delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="2f905-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="2f905-113">I partecipanti possono continuare a partecipare alle riunioni dell'organizzatore tramite numeri a tariffa.</span><span class="sxs-lookup"><span data-stu-id="2f905-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="2f905-114">Disattivazione di numeri verdi per utenti specifici</span><span class="sxs-lookup"><span data-stu-id="2f905-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="2f905-115">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="2f905-115">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="2f905-116">Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="2f905-116">In the left navigation, click **Users**, and then select the user from teh list of available users.</span></span>

2. <span data-ttu-id="2f905-117">Nella parte superiore della pagina, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="2f905-117">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="2f905-118">Fare clic sul menu accanto a **Ponti di conferenza**e quindi fare clic su **Modifica** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="2f905-118">Click the menu next to **Conference Bridges**, and then click **Edit** in the drop-down list.</span></span>

4. <span data-ttu-id="2f905-119">Nel riquadro dei **provider di ponte conferenza** , disattiva **Consenti utilizzo di numeri verdi di ponte per conferenze della propria organizzazione di partecipare alle riunioni di questo utente**.</span><span class="sxs-lookup"><span data-stu-id="2f905-119">In the **Conference bridge provider** pane, turn off **Allow using toll-free numbers in the Conferencing bridge of your organization to join the meetings of this user**.</span></span> 

5. <span data-ttu-id="2f905-120">Fare clic su **si applicano.**</span><span class="sxs-lookup"><span data-stu-id="2f905-120">Click **Apply.**</span></span> 

<span data-ttu-id="2f905-121">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="2f905-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="2f905-122">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="2f905-122">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span> 

2. <span data-ttu-id="2f905-123">In the Action pane, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="2f905-123">In the Action pane, click **Edit**.</span></span> 

3. <span data-ttu-id="2f905-124">Deselezionare **Consenti utilizzo di numeri verdi per partecipare alle riunioni di questo utente**.</span><span class="sxs-lookup"><span data-stu-id="2f905-124">Clear **Allow using toll-free numbers to join the meetings of this user**.</span></span> 
 
4. <span data-ttu-id="2f905-125">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2f905-125">Click **Save**.</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="2f905-126">**Utilizzo di PowerShell**</span><span class="sxs-lookup"><span data-stu-id="2f905-126">**Using PowerShell**</span></span>  

<span data-ttu-id="2f905-127">È possibile utilizzare il parametro AllowTollFreeDialIn del cmdlet Set-CsOnlineDialInConferencingUser per abilitare o disabilitare questo controllo.</span><span class="sxs-lookup"><span data-stu-id="2f905-127">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="2f905-128">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2f905-128">For example:</span></span> 

 - <span data-ttu-id="2f905-129">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="2f905-129">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
