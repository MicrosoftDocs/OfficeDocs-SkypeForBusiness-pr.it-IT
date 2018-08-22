---
title: Disattivazione di numeri verdi per specifico Skype per gli utenti aziendali Online
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
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Gli amministratori possono controllare gli organizzatori utilizzo numeri verdi per le riunioni.
ms.openlocfilehash: 1cd144af4f57b3c4ecb19de6c4aeea36f5d2baed
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490546"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="a3335-103">Disattivazione di numeri verdi per specifico Skype per gli utenti aziendali Online</span><span class="sxs-lookup"><span data-stu-id="a3335-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>

> [!Note]
> <span data-ttu-id="a3335-104">Per informazioni sulla disattivazione numeri strumento gratuito per gli utenti di team, vedere [Disabilitazione numeri verdi per utenti specifici in team](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span><span class="sxs-lookup"><span data-stu-id="a3335-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="a3335-105">Se l'organizzazione dispone di numeri verdi nel relativo Audio Conferencing Bridge Microsoft, è possibile consentire o impedire loro utilizzo in riunioni degli organizzatori specifici.</span><span class="sxs-lookup"><span data-stu-id="a3335-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="a3335-106">Per impostazione predefinita, tutti gli utenti nell'organizzazione sono abilitati per l'utilizzo di numeri verdi, ovvero i numeri, se disponibile, possono essere utilizzati dai partecipanti per partecipare alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="a3335-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="a3335-107">Se non è il comportamento desiderato per alcuni utenti all'interno dell'organizzazione, è possibile limitare gli utenti specifici di utilizzare tali numeri relativi alle riunioni tramite un controllo di attivazione dei numerico verdi.</span><span class="sxs-lookup"><span data-stu-id="a3335-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="a3335-108">Numeri verdi quando sono disabilitati per organizzare una determinata:</span><span class="sxs-lookup"><span data-stu-id="a3335-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="a3335-109">Un numero verde non verrà non è più incluso nel suo o verrà invita.</span><span class="sxs-lookup"><span data-stu-id="a3335-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="a3335-110">Non è più numeri verdi verranno elencati nella pagina "Trova un numero locale" viene fatto riferimento nel suo o verrà invita.</span><span class="sxs-lookup"><span data-stu-id="a3335-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="a3335-111">I partecipanti saranno in grado di partecipare alla riunione dell'organizzatore determinato se è comporre un numero verde dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a3335-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="a3335-112">Tutte le riunioni dell'organizzatore ripianificate automaticamente e verrà rimossa il numero verde.</span><span class="sxs-lookup"><span data-stu-id="a3335-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="a3335-113">Si verrà nuovamente tutti gli inviti di posta elettronica dell'organizzatore inviato a tutti i partecipanti delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="a3335-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="a3335-114">I partecipanti possono continuare a partecipare alle riunioni dell'organizzatore tramite numeri a tariffa.</span><span class="sxs-lookup"><span data-stu-id="a3335-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="a3335-115">Disattivazione dei numeri verdi per utenti specifici</span><span class="sxs-lookup"><span data-stu-id="a3335-115">Disabling toll-free numbers for specific users</span></span> 


1. <span data-ttu-id="a3335-116">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="a3335-116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span> 

2. <span data-ttu-id="a3335-117">In the Action pane, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="a3335-117">In the Action pane, click **Edit**.</span></span> 

3. <span data-ttu-id="a3335-118">Deselezionare **Consenti utilizzo di numeri verdi per partecipare alle riunioni di questo utente**.</span><span class="sxs-lookup"><span data-stu-id="a3335-118">Clear **Allow using toll-free numbers to join the meetings of this user**.</span></span> 
 
4. <span data-ttu-id="a3335-119">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a3335-119">Click **Save**.</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="a3335-120">**Utilizzo di PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a3335-120">**Using PowerShell**</span></span>  

<span data-ttu-id="a3335-121">È possibile utilizzare il parametro AllowTollFreeDialIn del cmdlet Set-CsOnlineDialInConferencingUser per abilitare o disabilitare questo controllo.</span><span class="sxs-lookup"><span data-stu-id="a3335-121">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="a3335-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a3335-122">For example:</span></span> 

 - <span data-ttu-id="a3335-123">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="a3335-123">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
