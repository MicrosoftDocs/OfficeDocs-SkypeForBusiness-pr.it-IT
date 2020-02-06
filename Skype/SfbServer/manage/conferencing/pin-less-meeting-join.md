---
title: Configurare l'aggiunta di una riunione senza PIN in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: "Riepilogo: informazioni su come configurare l'opzione di partecipazione alla riunione senza PIN in Skype for Business Server."
ms.openlocfilehash: a52738f2ca679838ab7687cde2c017e3364542a7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818487"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="105a0-103">Configurare l'aggiunta di una riunione senza PIN in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="105a0-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="105a0-104">**Riepilogo:** Informazioni su come configurare l'opzione di partecipazione alla riunione senza PIN in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="105a0-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="105a0-105">Quando un chiamante di chiamata in ingresso tenta di partecipare a una riunione, il servizio di conferenza automatica (CAA) colloca il chiamante in una penna di attesa diversa da quella della sala di &#x2014; se un relatore non è già in una chiamata e il chiamante non ha inserito il PIN di una direttrice.</span><span class="sxs-lookup"><span data-stu-id="105a0-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="105a0-106">L'opzione di join per riunioni con PIN meno consente ai chiamanti di accesso esterno di partecipare a una riunione senza immettere un PIN di riferimento, anche se è la prima persona che effettua una chiamata.</span><span class="sxs-lookup"><span data-stu-id="105a0-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="105a0-107">Quando si configura questa funzionalità, tieni presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="105a0-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="105a0-108">Si applica solo alle riunioni private.</span><span class="sxs-lookup"><span data-stu-id="105a0-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="105a0-109">Consente ai chiamanti PSTN di rimanere in riunioni private senza la presenza di utenti autenticati.</span><span class="sxs-lookup"><span data-stu-id="105a0-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="105a0-110">Dopo aver modificato l'impostazione, viene applicata a tutte le riunioni private esistenti e nuove.</span><span class="sxs-lookup"><span data-stu-id="105a0-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="105a0-111">Può essere abilitato sia nel sito dell'organizzatore che a livello globale.</span><span class="sxs-lookup"><span data-stu-id="105a0-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="105a0-112">Le opzioni per chi può bypassare la sala d'attesa possono essere impostate per una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="105a0-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="105a0-113">**Tutti gli utenti dell'organizzazione con i chiamanti entrano direttamente**</span><span class="sxs-lookup"><span data-stu-id="105a0-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="105a0-114">**Tutti gli utenti (nessuna restrizione) con i chiamanti entrano direttamente** (questa è l'impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="105a0-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="105a0-115">Quando è configurato per abilitare l'aggiunta di PIN, il servizio CAA richiede ancora un PIN iniziale.</span><span class="sxs-lookup"><span data-stu-id="105a0-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="105a0-116">Gli utenti possono partecipare alla riunione indipendentemente dal fatto che venga immesso o meno un PIN.</span><span class="sxs-lookup"><span data-stu-id="105a0-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="105a0-117">Tuttavia, il mantenimento della possibilità di immettere un PIN di riferimento consente a un chiamante di effettuare l'autenticazione come leader e di gestire la riunione, se necessario.</span><span class="sxs-lookup"><span data-stu-id="105a0-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="105a0-118">Configurare l'aggiunta di una riunione senza PIN</span><span class="sxs-lookup"><span data-stu-id="105a0-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="105a0-119">Per abilitare l'aggiunta di una riunione senza PIN per gli utenti, usare il cmdlet [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) con il parametro AllowAnonymousPstnActivation come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="105a0-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="105a0-120">Ad esempio, con il comando seguente viene abilitato il join di riunione senza PIN per il sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="105a0-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="105a0-121">Per motivi di sicurezza, quando è attivata la partecipazione alla riunione senza PIN, è consigliabile limitare l'accesso degli utenti anonimi garantendo che ConferencingPolicy sia impostato come segue:</span><span class="sxs-lookup"><span data-stu-id="105a0-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="105a0-122">Per altre informazioni, vedere [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="105a0-122">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

