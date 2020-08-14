---
title: Chiamata in uscita da una riunione in modo che gli altri utenti possano partecipare
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
description: Gli organizzatori della riunione possono imparare a usare l'app teams per consentire ad altre persone di partecipare alla stessa riunione usando i loro telefoni.
ms.openlocfilehash: f84f811d89847bfdf17f123abe9c2df88536bc76
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662106"
---
# <a name="dialing-out-from-a-microsoft-teams-meeting-so-other-people-can-join-it"></a><span data-ttu-id="eac96-103">Chiamata in uscita da una riunione di Microsoft teams in modo che gli altri utenti possano accedervi</span><span class="sxs-lookup"><span data-stu-id="eac96-103">Dialing out from a Microsoft Teams meeting so other people can join it</span></span>

<span data-ttu-id="eac96-104">L'organizzatore della riunione può eseguire la chiamata usando l'app teams per consentire ad altri utenti di partecipare alla stessa riunione usando i loro telefoni.</span><span class="sxs-lookup"><span data-stu-id="eac96-104">As the meeting organizer, you can dial out using the Teams app to let other people join the same meeting using their phones.</span></span>

<span data-ttu-id="eac96-105">Quando si effettua la chiamata in uscita a un utente, è consigliabile usare i numeri di telefono completi (incluso il formato del codice paese/area geografica-E. 164).</span><span class="sxs-lookup"><span data-stu-id="eac96-105">When you dial out to someone, we recommend that you do so using their full phone numbers (including the country/region code - E.164 format).</span></span>
  
  <span data-ttu-id="eac96-106">Tieni presente che:</span><span class="sxs-lookup"><span data-stu-id="eac96-106">Please note that:</span></span>

- <span data-ttu-id="eac96-107">È possibile effettuare la chiamata solo se si partecipa a una riunione tramite teams.</span><span class="sxs-lookup"><span data-stu-id="eac96-107">You can dial out only if you join a meeting using Teams.</span></span>
- <span data-ttu-id="eac96-108">L'organizzatore della riunione è stato abilitato per i servizi di audioconferenza oppure, nel caso in cui non è stata assegnata una licenza di audioconferenza, è consentito effettuare chiamate alla rete telefonica pubblica tramite piani per chiamate online o routing diretto.</span><span class="sxs-lookup"><span data-stu-id="eac96-108">The meeting organizer, has been enabled for audio conferencing, OR, in the case no audio conferencing license is assigned, is allowed to make calls to the public switched telephone network via online calling plans or direct routing.</span></span>
- <span data-ttu-id="eac96-109">All'organizzatore della riunione viene [concesso un criterio di chiamata in linea che consente la chiamata fuori dalle conferenze abilitate](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="eac96-109">The meeting organizer is [Granted an online dial out policy that enables dial out from conferencing enabled](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="eac96-110">Ecco come ottenere la chiamata in uscita per il lavoro:</span><span class="sxs-lookup"><span data-stu-id="eac96-110">Here's how to get dial out to work:</span></span>

 <span data-ttu-id="eac96-111">**Passaggio 1:** Nella riunione usare lo screenshot **Aggiungi persone** ![ dell'opzione Aggiungi persone ](media/add-people-button.png) per chiamare un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="eac96-111">**Step 1:** In the meeting, use the **Add people** ![Screenshot of the Add people button](media/add-people-button.png) option to dial out to a phone number.</span></span>
 <span data-ttu-id="eac96-112">**Passaggio 2:** Immettere il numero di telefono completo, incluso il codice paese nella casella **invita qualcuno o componi un numero** .</span><span class="sxs-lookup"><span data-stu-id="eac96-112">**Step 2:** Enter the full phone number, including the country/region code in the **Invite someone or dial a number** box.</span></span>
  
![Screenshot della casella invita qualcuno o componi un numero](media/invite-someone-box.png)
    
## <a name="supported-countries-and-regions"></a><span data-ttu-id="eac96-114">Paesi e aree geografiche supportati</span><span class="sxs-lookup"><span data-stu-id="eac96-114">Supported countries and regions</span></span>

<span data-ttu-id="eac96-115">Dial-out is only available to some countries/regions.</span><span class="sxs-lookup"><span data-stu-id="eac96-115">Dial-out is only available to some countries/regions.</span></span> <span data-ttu-id="eac96-116">Per l'elenco completo, vedere [disponibilità di paesi e aree geografiche per i piani di audioconferenza e chiamate](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="eac96-116">For complete list, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>

## <a name="allow-users-to-dial-in"></a><span data-ttu-id="eac96-117">Consentire agli utenti di effettuare la chiamata in</span><span class="sxs-lookup"><span data-stu-id="eac96-117">Allow users to dial in</span></span>

<span data-ttu-id="eac96-118">Per istruzioni su come consentire agli utenti di accedere a una riunione di teams, vedere i [numeri di telefono per i servizi di audioconferenza in Microsoft teams](phone-numbers-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="eac96-118">If you are looking for instructions on how to let your users dial in to a Teams meeting, please see [Phone numbers for Audio Conferencing in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md).</span></span>

## <a name="want-to-know-more-about-audio-conferencing"></a><span data-ttu-id="eac96-119">Per saperne di più sui servizi di conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="eac96-119">Want to know more about audio conferencing?</span></span>

[<span data-ttu-id="eac96-120">Provare o acquistare servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="eac96-120">Try or purchase Audio Conferencing</span></span>](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
[<span data-ttu-id="eac96-121">Licenze per i componenti aggiuntivi di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="eac96-121">Microsoft Teams add-on licensing</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
