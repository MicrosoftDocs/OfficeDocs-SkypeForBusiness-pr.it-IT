---
title: Problemi noti relativi ai piani di chiamata
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: Informazioni sui problemi noti relativi al piano per le chiamate PSTN e sulle relative funzioni.
ms.openlocfilehash: 3a97057f61c154ded83b85becbfcf53dc2b4bc78
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220736"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="8a897-103">Problemi noti relativi ai piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="8a897-103">Calling Plans known issues</span></span>

<span data-ttu-id="8a897-104">I Piani per chiamate sono una nuova funzionalità disponibile in Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="8a897-104">Calling Plans are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="8a897-105">Di seguito sono riportati gli attuali problemi che vengono monitorati e esaminati attivamente.</span><span class="sxs-lookup"><span data-stu-id="8a897-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="8a897-106">Saranno potenzialmente risolti quando la caratteristica verrà aggiornata nelle build future.</span><span class="sxs-lookup"><span data-stu-id="8a897-106">They will be potentially resolved when the feature is updated in future builds.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="8a897-107">Problemi noti relativi ai piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="8a897-107">Calling Plans known issues</span></span>

|<span data-ttu-id="8a897-108">**Problema noto**</span><span class="sxs-lookup"><span data-stu-id="8a897-108">**Known issue**</span></span>|<span data-ttu-id="8a897-109">**Commenti**</span><span class="sxs-lookup"><span data-stu-id="8a897-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8a897-110">La transizione dalle licenze di Anteprima tecnica alle licenze di produzione per i Piani per chiamate non aggiorna automaticamente la licenza.</span><span class="sxs-lookup"><span data-stu-id="8a897-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="8a897-111">Acquistare prima le nuove licenze in modo che siano pronte per essere assegnate agli utenti.</span><span class="sxs-lookup"><span data-stu-id="8a897-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="8a897-112">Rimuovere la licenza promozionale (Anteprima tecnica)  da un  utente, quindi assegnare IMMEDIATAMENTE all'utente le nuove licenze per il Piano per chiamate nazionali e/o Per chiamate nazionali e internazionali. </span><span class="sxs-lookup"><span data-stu-id="8a897-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="8a897-113">Se si rimuovono e si aggiungono licenze per più utenti, è estremamente importante rimuovere le  licenze da tutti gli utenti che usano Windows PowerShell e quindi assegnare IMMEDIATAMENTE le licenze per tutti gli utenti usando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a897-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="8a897-114">In questo modo si ha la sicurezza che non si verificano interruzioni del servizio durante la gestione di volumi elevati di assegnazioni di licenze utente.</span><span class="sxs-lookup"><span data-stu-id="8a897-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="8a897-115">Per script PowerShell di esempio, vedi [Assegnare le licenze di Skype for Business e Microsoft Teams.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="8a897-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="8a897-116">**Nota:** Se si usa la connettività PSTN locale per utenti ibridi, *è* necessario assegnare solo una **licenza Sistema** telefonico.</span><span class="sxs-lookup"><span data-stu-id="8a897-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you *only* need to assign a **Phone System** license.</span></span> <span data-ttu-id="8a897-117">NON è **consigliabile** assegnare anche un piano per le chiamate vocali.</span><span class="sxs-lookup"><span data-stu-id="8a897-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="8a897-118">Tuttavia, se si abilitano i Piani per chiamate in Microsoft 365 o Office 365 per gli utenti di Microsoft 365 o Office 365, è comunque necessario assegnare **a** tali utenti una licenza per un Piano per chiamate nazionali o Internazionali. </span><span class="sxs-lookup"><span data-stu-id="8a897-118">However, if you are enabling Calling Plans in Microsoft 365 or Office 365 for users that are in Microsoft 365 or Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="8a897-119">Vedi [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="8a897-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8a897-120">Se è necessario ottenere più numeri di telefono, contattare il supporto per i prodotti per le [aziende - Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="8a897-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="8a897-121">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8a897-121">Related topics</span></span>
[<span data-ttu-id="8a897-122">Domande comuni sul trasferimento dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="8a897-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="8a897-123">Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="8a897-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="8a897-124">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="8a897-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="8a897-125">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="8a897-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="8a897-126">[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="8a897-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
