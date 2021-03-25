---
title: Configurare la partecipazione alle riunioni senza PIN in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: "Riepilogo: informazioni su come configurare l'opzione di partecipazione alle riunioni senza PIN in Skype for Business Server."
ms.openlocfilehash: 76a2fb401c684e0eb685b733cb1b0a63ecbd9907
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119395"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="14a07-103">Configurare la partecipazione alle riunioni senza PIN in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="14a07-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="14a07-104">**Riepilogo:** Informazioni su come configurare l'opzione di partecipazione alle riunioni senza PIN in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="14a07-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="14a07-105">Quando un chiamante con accesso esterno tenta di partecipare a una riunione, il servizio Conference Operatore automatico (CAA) posiziona il chiamante in una penna di attesa diversa dal &#x2014; sala di attesa se un relatore non è già in una chiamata e il chiamante esterno non ha immesso un PIN di leader.</span><span class="sxs-lookup"><span data-stu-id="14a07-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="14a07-106">L'opzione di partecipazione alla riunione senza PIN consente ai chiamanti con accesso esterno di partecipare a una riunione senza immettere un PIN di leader anche se sono la prima persona di una chiamata.</span><span class="sxs-lookup"><span data-stu-id="14a07-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="14a07-107">Quando si configura questa funzionalità, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="14a07-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="14a07-108">Si applica solo alle riunioni private.</span><span class="sxs-lookup"><span data-stu-id="14a07-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="14a07-109">Consente ai chiamanti PSTN di rimanere in riunioni private senza la presenza di utenti autenticati.</span><span class="sxs-lookup"><span data-stu-id="14a07-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="14a07-110">Dopo la modifica, l'impostazione si applica a tutte le riunioni private esistenti e nuove.</span><span class="sxs-lookup"><span data-stu-id="14a07-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="14a07-111">Può essere abilitato sia nel sito dell'organizzatore che a livello globale.</span><span class="sxs-lookup"><span data-stu-id="14a07-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="14a07-112">Le opzioni per gli utenti che possono ignorare la sala di attesa possono essere impostate per una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="14a07-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="14a07-113">**Tutti gli utenti dell'organizzazione con chiamanti possono accedere direttamente**</span><span class="sxs-lookup"><span data-stu-id="14a07-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="14a07-114">**Chiunque (senza restrizioni) con chiamanti ottiene direttamente** (questa è l'impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="14a07-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="14a07-115">Se configurato per abilitare l'aggiunta senza PIN, il servizio CAA richiede comunque un PIN di leader.</span><span class="sxs-lookup"><span data-stu-id="14a07-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="14a07-116">Gli utenti possono partecipare alla riunione indipendentemente dal fatto che sia stato immesso o meno un PIN.</span><span class="sxs-lookup"><span data-stu-id="14a07-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="14a07-117">Tuttavia, mantenendo la possibilità di immettere un PIN di leader, un chiamante esterno può autenticarsi come leader e gestire la riunione, se necessario.</span><span class="sxs-lookup"><span data-stu-id="14a07-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="14a07-118">Configurare la partecipazione alle riunioni senza PIN</span><span class="sxs-lookup"><span data-stu-id="14a07-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="14a07-119">Per abilitare la partecipazione alle riunioni senza PIN per gli utenti, utilizzare il cmdlet [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) con il parametro AllowAnonymousPstnActivation come segue:</span><span class="sxs-lookup"><span data-stu-id="14a07-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="14a07-120">Ad esempio, il comando seguente abilita la partecipazione alle riunioni senza PIN per il sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="14a07-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="14a07-121">Per motivi di sicurezza, quando la partecipazione alle riunioni senza PIN è attivata, è consigliabile impedire agli utenti anonimi di effettuare chiamate in uscita verificando che ConferencingPolicy sia impostato come segue:</span><span class="sxs-lookup"><span data-stu-id="14a07-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="14a07-122">Per ulteriori informazioni, vedere [Set-CsConferencingPolicy.](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="14a07-122">For more information, see [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
