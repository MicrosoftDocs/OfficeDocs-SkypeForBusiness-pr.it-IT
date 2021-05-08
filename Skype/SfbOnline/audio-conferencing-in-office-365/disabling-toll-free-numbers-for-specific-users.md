---
title: Disattivazione di numeri gratuiti per utenti specifici su Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Gli amministratori possono controllare come gli organizzatori utilizzano i numeri gratuiti per le riunioni.
ms.openlocfilehash: 4fae54e3ed140ab876e6fadef10907e40f59057e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238511"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="409bb-103">Disattivazione di numeri gratuiti per utenti specifici su Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="409bb-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
 
> [!Note]
> <span data-ttu-id="409bb-104">Per informazioni sulla disattivazione dei numeri telefonici gratuiti per gli utenti di Teams, consulta [Disabilitazione numeri gratuiti per utenti specifici su Teams](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span><span class="sxs-lookup"><span data-stu-id="409bb-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="409bb-105">Se la tua organizzazione dispone di numeri gratuiti nel relativo ponte per audioconferenze Microsoft, puoi consentire o impedire il loro utilizzo in riunioni di organizzatori specifici.</span><span class="sxs-lookup"><span data-stu-id="409bb-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="409bb-106">Per impostazione predefinita, tutti gli utenti nell'organizzazione sono abilitati per l'utilizzo di numeri gratuiti, ovvero questi numeri, se disponibili, possono essere utilizzati dai partecipanti per partecipare alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="409bb-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="409bb-107">Se desideri che alcuni utenti all'interno dell'organizzazione siano esclusi, puoi limitare l'uso di tali numeri relativi alle riunioni per utenti specifici tramite un controllo di attivazione dei numeri gratuiti.</span><span class="sxs-lookup"><span data-stu-id="409bb-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="409bb-108">Quando i numeri gratuiti sono disabilitati per un determinato organizzatore:</span><span class="sxs-lookup"><span data-stu-id="409bb-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="409bb-109">Un numero gratuito non verrà più incluso nel suo invito alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="409bb-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="409bb-110">I numeri gratuiti non verranno più elencati nella pagina "Trova un numero locale" a cui viene fatto riferimento nei suoi inviti alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="409bb-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="409bb-111">I partecipanti saranno in grado di partecipare alla riunione di un determinato organizzatore se compongono qualsiasi numero gratuito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="409bb-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="409bb-112">Tutte le riunioni dell'organizzatore verranno ripianificate automaticamente e verrà rimosso il numero gratuito.</span><span class="sxs-lookup"><span data-stu-id="409bb-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="409bb-113">Quindi verranno inviati nuovamente tutti gli inviti di posta elettronica dell'organizzatore ai partecipanti di quelle riunioni.</span><span class="sxs-lookup"><span data-stu-id="409bb-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="409bb-114">I partecipanti possono continuare a partecipare alle riunioni dell'organizzatore tramite numeri a pagamento.</span><span class="sxs-lookup"><span data-stu-id="409bb-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="409bb-115">Disattivazione dei numeri verdi per utenti specifici</span><span class="sxs-lookup"><span data-stu-id="409bb-115">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="409bb-116">**Nell'Microsoft Teams di amministrazione:**</span><span class="sxs-lookup"><span data-stu-id="409bb-116">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="409bb-117">Nel riquadro di spostamento sinistro fare clic **su Utenti** e quindi selezionare l'utente nell'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="409bb-117">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="409bb-118">Accanto a **Audioconferenza** fare clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="409bb-118">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="409bb-119">Impostare **Includi numeri verde nelle convocazioni di riunione di questo utente su** **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="409bb-119">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="409bb-120">Fare clic **su Salva.**</span><span class="sxs-lookup"><span data-stu-id="409bb-120">Click **Save.**</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="409bb-121">**Utilizzo di PowerShell**</span><span class="sxs-lookup"><span data-stu-id="409bb-121">**Using PowerShell**</span></span>  

<span data-ttu-id="409bb-122">Puoi utilizzare il parametro AllowTollFreeDialIn del cmdlet Set-CsOnlineDialInConferencingUser per abilitare o disabilitare questo controllo.</span><span class="sxs-lookup"><span data-stu-id="409bb-122">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="409bb-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="409bb-123">For example:</span></span> 

- <span data-ttu-id="409bb-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="409bb-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
