---
title: Configurare il join di riunioni senza PIN in Skype for Business Server
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
ms.openlocfilehash: 794bf13d92857a18254f903a1c5dcca98d0a1ec0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827986"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="ba448-103">Configurare il join di riunioni senza PIN in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ba448-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="ba448-104">**Riepilogo:** Informazioni su come configurare l'opzione di partecipazione alle riunioni senza PIN in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ba448-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="ba448-105">Quando un chiamante di accesso esterno tenta di partecipare a una riunione, il servizio operatore automatico di conferenza inserisce il chiamante in una penna che è diversa dalla lobby &#x2014; se un relatore non è già su una chiamata e il chiamante di accesso esterno non è stato immesso in un PIN della direttrice.</span><span class="sxs-lookup"><span data-stu-id="ba448-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="ba448-106">L'opzione di partecipazione alle riunioni con PIN meno consente ai chiamanti di accesso esterno di partecipare a una riunione senza immettere un PIN della direttrice anche se è la prima persona di una chiamata.</span><span class="sxs-lookup"><span data-stu-id="ba448-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="ba448-107">Quando si configura questa funzionalità, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ba448-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="ba448-108">Si applica solo alle riunioni private.</span><span class="sxs-lookup"><span data-stu-id="ba448-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="ba448-109">Consente ai chiamanti PSTN di rimanere in riunioni private senza la presenza di utenti autenticati.</span><span class="sxs-lookup"><span data-stu-id="ba448-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="ba448-110">Dopo la modifica dell'impostazione, si applica a tutte le riunioni private esistenti e nuove.</span><span class="sxs-lookup"><span data-stu-id="ba448-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="ba448-111">Può essere abilitato sia nel sito dell'organizzatore sia a livello globale.</span><span class="sxs-lookup"><span data-stu-id="ba448-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="ba448-112">Le opzioni per gli utenti che possono ignorare la lobby possono essere impostate per una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="ba448-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="ba448-113">**Tutti gli utenti dell'organizzazione con i chiamanti si rifanno direttamente**</span><span class="sxs-lookup"><span data-stu-id="ba448-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="ba448-114">**Tutti gli utenti (nessuna restrizione) con i chiamanti ottengono direttamente** (questa è l'impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="ba448-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="ba448-115">Quando viene configurato per abilitare l'aggiunta senza PIN, il servizio CAA richiede ancora un PIN di direttrice.</span><span class="sxs-lookup"><span data-stu-id="ba448-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="ba448-116">Gli utenti possono partecipare alla riunione indipendentemente dal fatto che un PIN venga immesso.</span><span class="sxs-lookup"><span data-stu-id="ba448-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="ba448-117">Tuttavia, mantenere la possibilità di immettere un PIN di direttrice consente a un chiamante di effettuare l'autenticazione come leader e di gestire la riunione, se necessario.</span><span class="sxs-lookup"><span data-stu-id="ba448-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="ba448-118">Configurare l'aggiunta di riunioni senza PIN</span><span class="sxs-lookup"><span data-stu-id="ba448-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="ba448-119">Per abilitare la partecipazione alle riunioni senza PIN per gli utenti, utilizzare il cmdlet [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) con il parametro AllowAnonymousPstnActivation, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ba448-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="ba448-120">Ad esempio, il comando seguente consente di abilitare l'aggiunta di riunioni senza PIN per il sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="ba448-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="ba448-121">Per motivi di sicurezza, quando il PIN-less meeting join è attivato, è possibile che si desideri limitare l'accesso degli utenti anonimi assicurando che il ConferencingPolicy sia impostato come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ba448-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="ba448-122">Per ulteriori informazioni, vedere [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="ba448-122">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

