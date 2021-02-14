---
title: Chiamata in uscita da una riunione per far partecipare altri utenti
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 3c2db9a5-3a19-4e19-b59e-8e5587f25d31
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
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Gli organizzatori delle riunioni possono imparare a effettuare chiamate in uscita usando l'app Teams per consentire ad altre persone di partecipare alla stessa riunione usando i loro telefoni.
ms.openlocfilehash: 575ed18bd3dbd404dba947c0c4556d52e0653200
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788760"
---
# <a name="dialing-out-from-a-microsoft-teams-meeting-so-other-people-can-join-it"></a><span data-ttu-id="8895c-103">Chiamata in uscita da una riunione di Microsoft Teams in modo che altre persone possano parteciparvi</span><span class="sxs-lookup"><span data-stu-id="8895c-103">Dialing out from a Microsoft Teams meeting so other people can join it</span></span>

<span data-ttu-id="8895c-104">L'organizzatore della riunione può effettuare chiamate in uscita usando l'app Teams per consentire ad altre persone di partecipare alla stessa riunione usando i loro telefoni.</span><span class="sxs-lookup"><span data-stu-id="8895c-104">As the meeting organizer, you can dial out using the Teams app to let other people join the same meeting using their phones.</span></span>

<span data-ttu-id="8895c-105">Quando si chiama un utente, è consigliabile farlo utilizzando i numeri di telefono completi (incluso il codice paese/area geografica - formato E.164).</span><span class="sxs-lookup"><span data-stu-id="8895c-105">When you dial out to someone, we recommend that you do so using their full phone numbers (including the country/region code - E.164 format).</span></span>
  
  <span data-ttu-id="8895c-106">Tenere presente che:</span><span class="sxs-lookup"><span data-stu-id="8895c-106">Please note that:</span></span>

- <span data-ttu-id="8895c-107">È possibile effettuare chiamate in uscita solo se si partecipa a una riunione con Teams.</span><span class="sxs-lookup"><span data-stu-id="8895c-107">You can dial out only if you join a meeting using Teams.</span></span>
- <span data-ttu-id="8895c-108">L'organizzatore della riunione, è stato abilitato per i servizi di audioconferenza oppure, nel caso in cui non sia assegnata alcuna licenza per i servizi di audioconferenza, è autorizzato a effettuare chiamate alla rete telefonica pubblica passata tramite piani di chiamata online o instradamento diretto.</span><span class="sxs-lookup"><span data-stu-id="8895c-108">The meeting organizer, has been enabled for audio conferencing, OR, in the case no audio conferencing license is assigned, is allowed to make calls to the public switched telephone network via online calling plans or direct routing.</span></span>
- <span data-ttu-id="8895c-109">All'organizzatore della riunione [è stato concesso un criterio di chiamata in uscita online che abilita](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps) la chiamata in uscita dalle conferenze</span><span class="sxs-lookup"><span data-stu-id="8895c-109">The meeting organizer is [Granted an online dial out policy that enables dial out from conferencing enabled](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="8895c-110">Ecco come usare le chiamate in uscita:</span><span class="sxs-lookup"><span data-stu-id="8895c-110">Here's how to get dial out to work:</span></span>

 <span data-ttu-id="8895c-111">**Passaggio 1:** Nella riunione, usare lo screenshot **Aggiungi persone** dell'opzione del pulsante Aggiungi persone per effettuare una chiamata in uscita a un numero ![ di ](media/add-people-button.png) telefono.</span><span class="sxs-lookup"><span data-stu-id="8895c-111">**Step 1:** In the meeting, use the **Add people** ![Screenshot of the Add people button](media/add-people-button.png) option to dial out to a phone number.</span></span>
 <span data-ttu-id="8895c-112">**Passaggio 2:** Immettere il numero di telefono completo, comprensiva del codice paese/area geografica nella casella Invita qualcuno o **componi un numero.**</span><span class="sxs-lookup"><span data-stu-id="8895c-112">**Step 2:** Enter the full phone number, including the country/region code in the **Invite someone or dial a number** box.</span></span>
  
![Screenshot della casella Invita qualcuno o componi un numero](media/invite-someone-box.png)
    
## <a name="supported-countries-and-regions"></a><span data-ttu-id="8895c-114">Paesi e aree geografiche supportati</span><span class="sxs-lookup"><span data-stu-id="8895c-114">Supported countries and regions</span></span>

<span data-ttu-id="8895c-115">Dial-out is only available to some countries/regions.</span><span class="sxs-lookup"><span data-stu-id="8895c-115">Dial-out is only available to some countries/regions.</span></span> <span data-ttu-id="8895c-116">Per l'elenco completo, consulta la [disponibilità del Paese e dell'area geografica per audioconferenze e piani per chiamate.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="8895c-116">For complete list, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>

## <a name="allow-users-to-dial-in"></a><span data-ttu-id="8895c-117">Consenti agli utenti di chiamare tramite telefono</span><span class="sxs-lookup"><span data-stu-id="8895c-117">Allow users to dial in</span></span>

<span data-ttu-id="8895c-118">Per istruzioni su come consentire agli utenti di accedere a una riunione di Teams, vedere Numeri di telefono per le audioconferenze [in Microsoft Teams.](phone-numbers-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="8895c-118">If you are looking for instructions on how to let your users dial in to a Teams meeting, please see [Phone numbers for Audio Conferencing in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md).</span></span>

## <a name="want-to-know-more-about-audio-conferencing"></a><span data-ttu-id="8895c-119">Per saperne di più sui servizi di conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="8895c-119">Want to know more about audio conferencing?</span></span>

[<span data-ttu-id="8895c-120">Provare o acquistare audioconferenze</span><span class="sxs-lookup"><span data-stu-id="8895c-120">Try or purchase Audio Conferencing</span></span>](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
[<span data-ttu-id="8895c-121">Licenze per i componenti aggiuntivi di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8895c-121">Microsoft Teams add-on licensing</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
