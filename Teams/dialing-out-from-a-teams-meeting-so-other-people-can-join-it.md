---
title: Chiamata in uscita da una riunione in modo che altre persone possano partecipare
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
description: Gli organizzatori delle riunioni possono imparare a usare l'app Teams per consentire ad altri utenti di partecipare alla stessa riunione usando i loro telefoni.
ms.openlocfilehash: 55cbd5ccc9e9c364bcb829d9a392f61cbdd2f7f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119285"
---
# <a name="dialing-out-from-a-microsoft-teams-meeting-so-other-people-can-join-it"></a><span data-ttu-id="0cd93-103">Chiamata in uscita da una riunione di Microsoft Teams in modo che altri utenti possano parteciparvi</span><span class="sxs-lookup"><span data-stu-id="0cd93-103">Dialing out from a Microsoft Teams meeting so other people can join it</span></span>

<span data-ttu-id="0cd93-104">L'organizzatore della riunione può effettuare chiamate in uscita usando l'app Teams per consentire ad altre persone di partecipare alla stessa riunione usando i loro telefoni.</span><span class="sxs-lookup"><span data-stu-id="0cd93-104">As the meeting organizer, you can dial out using the Teams app to let other people join the same meeting using their phones.</span></span>

<span data-ttu-id="0cd93-105">Quando si chiama un utente, è consigliabile farlo usando i numeri di telefono completi (incluso il codice paese/area geografica - formato E.164).</span><span class="sxs-lookup"><span data-stu-id="0cd93-105">When you dial out to someone, we recommend that you do so using their full phone numbers (including the country/region code - E.164 format).</span></span>
  
  <span data-ttu-id="0cd93-106">Tenere presente che:</span><span class="sxs-lookup"><span data-stu-id="0cd93-106">Please note that:</span></span>

- <span data-ttu-id="0cd93-107">È possibile effettuare chiamate in uscita solo se si partecipa a una riunione con Teams.</span><span class="sxs-lookup"><span data-stu-id="0cd93-107">You can dial out only if you join a meeting using Teams.</span></span>
- <span data-ttu-id="0cd93-108">L'organizzatore della riunione, è stato abilitato per le audioconferenze oppure, nel caso in cui non sia assegnata alcuna licenza per i servizi di audioconferenza, è autorizzato a effettuare chiamate alla rete telefonica a commutazione pubblica tramite piani di chiamata online o routing diretto.</span><span class="sxs-lookup"><span data-stu-id="0cd93-108">The meeting organizer, has been enabled for audio conferencing, OR, in the case no audio conferencing license is assigned, is allowed to make calls to the public switched telephone network via online calling plans or direct routing.</span></span>
- <span data-ttu-id="0cd93-109">All'organizzatore della riunione [è concesso un criterio di chiamata in uscita online che abilita la chiamata in uscita dalle conferenze telefoniche abilitate](/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="0cd93-109">The meeting organizer is [Granted an online dial out policy that enables dial out from conferencing enabled](/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="0cd93-110">Ecco come usare la chiamata in uscita:</span><span class="sxs-lookup"><span data-stu-id="0cd93-110">Here's how to get dial out to work:</span></span>

 <span data-ttu-id="0cd93-111">**Passaggio 1:** Nella riunione usare lo screenshot **Aggiungi persone** del pulsante Aggiungi persone per effettuare chiamate in uscita a un numero ![ di ](media/add-people-button.png) telefono.</span><span class="sxs-lookup"><span data-stu-id="0cd93-111">**Step 1:** In the meeting, use the **Add people** ![Screenshot of the Add people button](media/add-people-button.png) option to dial out to a phone number.</span></span>
 <span data-ttu-id="0cd93-112">**Passaggio 2:** Immetti il numero di telefono completo, incluso il codice paese/area geografica nella casella **Invita qualcuno o componi un numero.**</span><span class="sxs-lookup"><span data-stu-id="0cd93-112">**Step 2:** Enter the full phone number, including the country/region code in the **Invite someone or dial a number** box.</span></span>
  
![Screenshot della casella Invita qualcuno o componi un numero](media/invite-someone-box.png)
    
## <a name="supported-countries-and-regions"></a><span data-ttu-id="0cd93-114">Paesi e aree geografiche supportati</span><span class="sxs-lookup"><span data-stu-id="0cd93-114">Supported countries and regions</span></span>

<span data-ttu-id="0cd93-115">Dial-out is only available to some countries/regions.</span><span class="sxs-lookup"><span data-stu-id="0cd93-115">Dial-out is only available to some countries/regions.</span></span> <span data-ttu-id="0cd93-116">Per l'elenco completo, vedere [Disponibilità di paesi e aree geografica per audioconferenze e piani per chiamate.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="0cd93-116">For complete list, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>

## <a name="allow-users-to-dial-in"></a><span data-ttu-id="0cd93-117">Consenti agli utenti di effettuare l'accesso</span><span class="sxs-lookup"><span data-stu-id="0cd93-117">Allow users to dial in</span></span>

<span data-ttu-id="0cd93-118">Per istruzioni su come consentire agli utenti di accedere a una riunione di Teams, vedere Numeri di telefono per [le audioconferenze in Microsoft Teams.](phone-numbers-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="0cd93-118">If you are looking for instructions on how to let your users dial in to a Teams meeting, please see [Phone numbers for Audio Conferencing in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md).</span></span>

## <a name="want-to-know-more-about-audio-conferencing"></a><span data-ttu-id="0cd93-119">Per saperne di più sui servizi di conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="0cd93-119">Want to know more about audio conferencing?</span></span>

[<span data-ttu-id="0cd93-120">Provare o acquistare audioconferenze</span><span class="sxs-lookup"><span data-stu-id="0cd93-120">Try or purchase Audio Conferencing</span></span>](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
[<span data-ttu-id="0cd93-121">Licenze per i componenti aggiuntivi di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0cd93-121">Microsoft Teams add-on licensing</span></span>](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)