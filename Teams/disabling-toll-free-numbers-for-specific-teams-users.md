---
title: Disabilitazione dei numeri verdi per gli utenti di team specifici
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Gli amministratori possono controllare come gli organizzatori utilizzano i numeri gratuiti per le riunioni.
ms.openlocfilehash: e2dddd04f376de69dbbc9579525966bac6351a0a
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572103"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="9e6a6-103">Disabilitazione dei numeri verdi per gli utenti di team specifici</span><span class="sxs-lookup"><span data-stu-id="9e6a6-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="9e6a6-104">Se la tua organizzazione dispone di numeri gratuiti nel relativo ponte per audioconferenze Microsoft, puoi consentire o impedire il loro utilizzo in riunioni di organizzatori specifici.</span><span class="sxs-lookup"><span data-stu-id="9e6a6-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="9e6a6-105">Per impostazione predefinita, tutti gli utenti nell'organizzazione sono abilitati per l'utilizzo di numeri gratuiti, ovvero questi numeri, se disponibili, possono essere utilizzati dai partecipanti per partecipare alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="9e6a6-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="9e6a6-106">Se desideri che alcuni utenti all'interno dell'organizzazione siano esclusi, puoi limitare l'uso di tali numeri relativi alle riunioni per utenti specifici tramite un controllo di attivazione dei numeri gratuiti.</span><span class="sxs-lookup"><span data-stu-id="9e6a6-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="9e6a6-107">Quando i numeri gratuiti sono disabilitati per un determinato organizzatore:</span><span class="sxs-lookup"><span data-stu-id="9e6a6-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="9e6a6-108">Un numero gratuito non verrà più incluso nel suo invito alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="9e6a6-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="9e6a6-109">I numeri gratuiti non verranno più elencati nella pagina "Trova un numero locale" a cui viene fatto riferimento nei suoi inviti alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="9e6a6-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="9e6a6-110">I partecipanti saranno in grado di partecipare alla riunione di un determinato organizzatore se compongono qualsiasi numero gratuito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9e6a6-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="9e6a6-111">Tutte le riunioni dell'organizzatore verranno ripianificate automaticamente e verrà rimosso il numero gratuito.</span><span class="sxs-lookup"><span data-stu-id="9e6a6-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="9e6a6-112">Quindi verranno inviati nuovamente tutti gli inviti di posta elettronica dell'organizzatore ai partecipanti di quelle riunioni.</span><span class="sxs-lookup"><span data-stu-id="9e6a6-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="9e6a6-113">I partecipanti possono continuare a partecipare alle riunioni dell'organizzatore tramite numeri a pagamento.</span><span class="sxs-lookup"><span data-stu-id="9e6a6-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="9e6a6-114">Disattivazione dei numeri verdi per utenti specifici</span><span class="sxs-lookup"><span data-stu-id="9e6a6-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="9e6a6-115">Dall'interfaccia di **amministrazione di Microsoft teams**:</span><span class="sxs-lookup"><span data-stu-id="9e6a6-115">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="9e6a6-116">Nella barra di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente nell'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="9e6a6-116">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="9e6a6-117">Accanto a servizi di **audioconferenza**fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="9e6a6-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="9e6a6-118">Imposta **Includi numeri verdi nelle convocazioni di riunione da questo utente** su **disattivato**.</span><span class="sxs-lookup"><span data-stu-id="9e6a6-118">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="9e6a6-119">Fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="9e6a6-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="9e6a6-120">**Utilizzo di PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9e6a6-120">**Using PowerShell**</span></span>  

<span data-ttu-id="9e6a6-121">Per altre informazioni, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .</span><span class="sxs-lookup"><span data-stu-id="9e6a6-121">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
