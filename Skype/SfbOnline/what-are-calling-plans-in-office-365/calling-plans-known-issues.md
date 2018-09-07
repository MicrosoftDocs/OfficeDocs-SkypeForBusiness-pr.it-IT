---
title: Problemi noti nei Piani per chiamate
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Informazioni su problemi noti di piano di chiamata per Office 365 (tramite la chiamata PSTN) e operazioni su di essi. '
ms.openlocfilehash: e43aecea6bd19c6b346de68577f471214818d43f
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854158"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="fb0e5-103">Problemi noti nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="fb0e5-103">Calling Plans known issues</span></span>

<span data-ttu-id="fb0e5-104">Piani di chiamata in Office 365 sono una nuova funzionalità disponibili in Skype Business online.</span><span class="sxs-lookup"><span data-stu-id="fb0e5-104">Calling Plans in Office 365 are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="fb0e5-105">Di seguito sono riportati i problemi correnti che vengono registrati e analizzare attivamente.</span><span class="sxs-lookup"><span data-stu-id="fb0e5-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="fb0e5-106">Verrà risolto potenzialmente quando la caratteristica viene aggiornata in futuro build in Office 365 e Skype Business online.</span><span class="sxs-lookup"><span data-stu-id="fb0e5-106">They will be potentially resolved when the feature is updated in future builds in Office 365 and Skype for Business Online.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="fb0e5-107">Problemi noti nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="fb0e5-107">Calling Plans known issues</span></span>

|<span data-ttu-id="fb0e5-108">**Problemi noti**</span><span class="sxs-lookup"><span data-stu-id="fb0e5-108">**Known issue**</span></span>|<span data-ttu-id="fb0e5-109">**Commenti**</span><span class="sxs-lookup"><span data-stu-id="fb0e5-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fb0e5-110">Transizione da Tech Preview licenze per le licenze di produzione per piani di chiamata non vengono aggiornati automaticamente la licenza.</span><span class="sxs-lookup"><span data-stu-id="fb0e5-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="fb0e5-111">Acquistare le licenze nuove innanzitutto in modo che siano pronti per essere assegnati agli utenti.</span><span class="sxs-lookup"><span data-stu-id="fb0e5-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="fb0e5-112">Rimuovere la licenza promozione (Tech Preview) da un utente e quindi assegnare **immediatamente** le nuove licenze **Chiamata pianificare interne** e/o **nazionali e internazionali chiamata pianificare** all'utente.</span><span class="sxs-lookup"><span data-stu-id="fb0e5-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="fb0e5-113">Se si ha la rimozione e aggiungendo le licenze per più utenti, è estremamente importante per rimuovere tutti gli utenti utilizzando Windows PowerShell le licenze e assegnarle **immediatamente** le licenze per tutti gli utenti anche tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fb0e5-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="fb0e5-114">In questo modo verrà assicurarsi che non vi sia alcuna interruzione del servizio quando si gestiscono volumi elevati di assegnazione di licenze utente.</span><span class="sxs-lookup"><span data-stu-id="fb0e5-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="fb0e5-115">Per gli script di PowerShell di esempio, vedere [Assegnare Skype per le licenze aziendali e team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="fb0e5-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="fb0e5-116">**Nota:** Se si utilizza una connettività PSTN locale per gli utenti ibrida, è *solo* necessario assegnare una licenza di **Sistema telefonico** .</span><span class="sxs-lookup"><span data-stu-id="fb0e5-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you  *only*  need to assign a **Phone System** license.</span></span> <span data-ttu-id="fb0e5-117">**Non** deve inoltre assegnare una voce pianificare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fb0e5-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="fb0e5-118">Tuttavia, se si abilita la chiamata dei piani di Office 365 per gli utenti presenti in Office 365, è necessario assegnare ancora un **Interno pianificare la chiamata** o una licenza **nazionali e internazionali la chiamata a pianificare** per tali utenti.</span><span class="sxs-lookup"><span data-stu-id="fb0e5-118">However, if you are enabling Calling Plans in Office 365 for users that are in Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="fb0e5-119">Vedi [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="fb0e5-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fb0e5-120">Se si desidera ottenere altri numeri di telefono rispetto a quella, [contattare il supporto per i prodotti di business - della Guida di amministrazione](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="fb0e5-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="fb0e5-121">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="fb0e5-121">Related topics</span></span>
[<span data-ttu-id="fb0e5-122">Domande comuni sul trasferimento dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="fb0e5-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="fb0e5-123">Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="fb0e5-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="fb0e5-124">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="fb0e5-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="fb0e5-125">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="fb0e5-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="fb0e5-126">[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="fb0e5-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 