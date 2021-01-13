---
title: Configurare la chiamata in uscita della riunione per gli utenti in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come configurare i team per richiedere una conferma di chiamata in uscita per evitare che i sistemi di segreteria telefonica si connettano alle riunioni quando la persona chiamata non è in grado di rispondere alla chiamata.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37d68eb90e42b57ff76d352ea2c856e6904a9308
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806146"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a><span data-ttu-id="94eb3-103">Configurare la conferma della chiamata in uscita della riunione per gli utenti in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="94eb3-103">Set up meeting dial-out confirmation for your users in Microsoft Teams</span></span>

<span data-ttu-id="94eb3-104">I partecipanti alla riunione e le chiamate chiamami sono modi molto utili per invitare gli utenti a partecipare a una riunione e per partecipare a una riunione con un telefono tradizionale o cellulare.</span><span class="sxs-lookup"><span data-stu-id="94eb3-104">Meeting dial outs and Call me calls are very useful ways to invite participants to join a meeting and for existing participants to join a meeting using a traditional or mobile phone.</span></span> <span data-ttu-id="94eb3-105">Tuttavia, quando la persona chiamata non è in grado di rispondere alla chiamata e la chiamata viene risolta da un sistema di segreteria telefonica, il sistema di segreteria telefonica è connesso alla riunione e i partecipanti potranno ascoltarlo finché non viene rimosso dalla riunione.</span><span class="sxs-lookup"><span data-stu-id="94eb3-105">However, when the called person is unable to answer the call and the call is answered by a voicemail system, the voicemail system is connected to the meeting and participants will be able to listen to it until it’s removed from the meeting.</span></span>

<span data-ttu-id="94eb3-106">Per evitare che i sistemi di segreteria telefonica si connettano alle riunioni quando viene inviata una chiamata in uscita a un numero di telefono e la persona chiamata non è in grado di rispondere, è possibile configurare i team per richiedere una conferma da parte della persona chiamata per partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="94eb3-106">To prevent voicemail systems from connecting to meetings when a meeting dial out is sent to a phone number and the called person is unable to answer the call, you can set up Teams to request a confirmation from the called person for them to join the meeting.</span></span> <span data-ttu-id="94eb3-107">Se la persona chiamata non riesce a rispondere alla chiamata e la chiamata viene risolta da un sistema di segreteria telefonica, il sistema di segreteria telefonica non verrà connesso alla riunione perché non offre una conferma per partecipare.</span><span class="sxs-lookup"><span data-stu-id="94eb3-107">If the called person can’t answer the call and the call is answered by a voicemail system, the voicemail system won‘t be connected to the meeting because it won’t provide a confirmation to join it.</span></span>

<span data-ttu-id="94eb3-108">Quando questa funzionalità è abilitata, le persone che ricevono una chiamata in uscita o chiamata telefonica devono confermare di voler partecipare alla riunione premendo 1 sul telefono tradizionale o mobile.</span><span class="sxs-lookup"><span data-stu-id="94eb3-108">When this capability is enabled, people that receive a dial out or Call me call must confirm that they want to join the meeting by pressing 1 on their traditional or mobile phone.</span></span>

<span data-ttu-id="94eb3-109">Per abilitare questa funzionalità per tutte le riunioni dell'organizzazione, imposta il ```EnableDialOutJoinConfirmation``` parametro del cmdlet [set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) su ```true``` .</span><span class="sxs-lookup"><span data-stu-id="94eb3-109">To enable this capability for all meetings in your organization, set the ```EnableDialOutJoinConfirmation``` parameter of the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to ```true```.</span></span> <span data-ttu-id="94eb3-110">Per farlo, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="94eb3-110">To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a><span data-ttu-id="94eb3-111">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="94eb3-111">Related topics</span></span>

- [<span data-ttu-id="94eb3-112">Configurare la funzionalità Chiamami per gli utenti</span><span class="sxs-lookup"><span data-stu-id="94eb3-112">Set up the Call me feature for your users</span></span>](set-up-the-call-me-feature-for-your-users.md)
- [<span data-ttu-id="94eb3-113">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="94eb3-113">Teams PowerShell overview</span></span>](teams-powershell-overview.md)