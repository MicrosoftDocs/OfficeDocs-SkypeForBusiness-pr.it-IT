---
title: Problemi noti di piani di chiamata
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Calling Plans
description: 'Informazioni su problemi noti di piano di chiamata per Office 365 (tramite la chiamata PSTN) e operazioni su di essi. '
ms.openlocfilehash: 42b282bce7ba65dc4e053020970a02e71c98b5bd
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="4434f-103">Problemi noti di piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="4434f-103">Calling Plans known issues</span></span>

<span data-ttu-id="4434f-104">Piani di chiamata in Office 365 sono una nuova funzionalità disponibili in Skype Business online.</span><span class="sxs-lookup"><span data-stu-id="4434f-104">Calling Plans in Office 365 are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="4434f-105">Di seguito sono riportati i problemi correnti che vengono registrati e analizzare attivamente.</span><span class="sxs-lookup"><span data-stu-id="4434f-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="4434f-106">Verrà risolto potenzialmente quando la caratteristica viene aggiornata in futuro build in Office 365 e Skype Business online.</span><span class="sxs-lookup"><span data-stu-id="4434f-106">They will be potentially resolved when the feature is updated in future builds in Office 365 and Skype for Business Online.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="4434f-107">Problemi noti di piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="4434f-107">Calling Plans known issues</span></span>

|<span data-ttu-id="4434f-108">**Problemi noti**</span><span class="sxs-lookup"><span data-stu-id="4434f-108">**Known issue**</span></span>|<span data-ttu-id="4434f-109">**Commenti**</span><span class="sxs-lookup"><span data-stu-id="4434f-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4434f-110">Transizione da Tech Preview licenze per le licenze di produzione per piani di chiamata non vengono aggiornati automaticamente la licenza.</span><span class="sxs-lookup"><span data-stu-id="4434f-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="4434f-111">Acquistare le licenze nuove innanzitutto in modo che siano pronti per essere assegnati agli utenti.</span><span class="sxs-lookup"><span data-stu-id="4434f-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="4434f-112">Rimuovere la licenza promozione (Tech Preview) da un utente e quindi assegnare **immediatamente** le nuove licenze **Chiamata pianificare interne** e/o **nazionali e internazionali chiamata pianificare** all'utente.</span><span class="sxs-lookup"><span data-stu-id="4434f-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="4434f-113">Se si ha la rimozione e aggiungendo le licenze per più utenti, è estremamente importante per rimuovere tutti gli utenti utilizzando Windows PowerShell le licenze e assegnarle **immediatamente** le licenze per tutti gli utenti anche tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4434f-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="4434f-114">In questo modo verrà assicurarsi che non vi sia alcuna interruzione del servizio quando si gestiscono volumi elevati di assegnazione di licenze utente.</span><span class="sxs-lookup"><span data-stu-id="4434f-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="4434f-115">Per gli script di PowerShell di esempio, vedere [Assegnare Skype per le licenze aziendali e team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="4434f-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="4434f-116">**Nota:** Se si utilizza una connettività PSTN locale per gli utenti ibrida, è *solo* necessario assegnare una licenza di **Sistema telefonico** .</span><span class="sxs-lookup"><span data-stu-id="4434f-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you  *only*  need to assign a **Phone System** license.</span></span> <span data-ttu-id="4434f-117">**Non** deve inoltre assegnare una voce pianificare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4434f-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="4434f-118">Tuttavia, se si abilita la chiamata dei piani di Office 365 per gli utenti presenti in Office 365, è necessario assegnare ancora un **Interno pianificare la chiamata** o una licenza **nazionali e internazionali la chiamata a pianificare** per tali utenti.</span><span class="sxs-lookup"><span data-stu-id="4434f-118">However, if you are enabling Calling Plans in Office 365 for users that are in Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="4434f-119">Vedere [Assegnare Skype per le licenze aziendali e team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="4434f-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4434f-120">Se si desidera ottenere altri numeri di telefono rispetto a quella, [contattare il supporto per i prodotti di business - della Guida di amministrazione](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="4434f-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="4434f-121">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4434f-121">Related topics</span></span>
[<span data-ttu-id="4434f-122">Trasferimento di domande comuni numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="4434f-122">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="4434f-123">Diversi tipi di numeri di telefono utilizzati per la chiamata dei piani</span><span class="sxs-lookup"><span data-stu-id="4434f-123">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="4434f-124">Gestire i numeri di telefono per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="4434f-124">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="4434f-125">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="4434f-125">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="4434f-126">Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="4434f-126">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)
