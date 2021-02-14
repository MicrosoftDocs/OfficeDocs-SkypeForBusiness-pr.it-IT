---
title: Conformità alle comunicazioni con Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Informazioni sulla conformità alle comunicazioni, parte del set di soluzioni di rischio Insider, dal punto di vista di Microsoft Teams (fa parte della funzionalità di conformità alle comunicazioni M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb9400778b8e000a438343e74bc6b030087ff297
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328255"
---
# <a name="communication-compliance-with-microsoft-teams"></a><span data-ttu-id="c00ad-103">Conformità alle comunicazioni con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c00ad-103">Communication compliance with Microsoft Teams</span></span>

<span data-ttu-id="c00ad-104">La conformità alle comunicazioni è una soluzione di rischio insider in Microsoft 365 che consente di ridurre al minimo i rischi di comunicazione, consentendo di rilevare, acquisire e agire sui messaggi inappropriati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c00ad-104">Communication compliance is an insider risk solution in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span>

<span data-ttu-id="c00ad-105">Per Microsoft Teams, la conformità alle comunicazioni consente di identificare i seguenti [tipi](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) di contenuto inappropriato nei canali di Teams o nelle chat 1:1 e di gruppo:</span><span class="sxs-lookup"><span data-stu-id="c00ad-105">For Microsoft Teams, communication compliance helps identify the [following types](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) of inappropriate content in Teams channels or in 1:1 and group chats:</span></span>

- <span data-ttu-id="c00ad-106">Linguaggio offensivo, profano e molesto</span><span class="sxs-lookup"><span data-stu-id="c00ad-106">Offensive, profane, and harassing language</span></span>
- <span data-ttu-id="c00ad-107">Immagini di adulto, ghiacciato e gory</span><span class="sxs-lookup"><span data-stu-id="c00ad-107">Adult, racy, and gory images</span></span>
- <span data-ttu-id="c00ad-108">Condivisione di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="c00ad-108">Sharing of sensitive information</span></span>

<span data-ttu-id="c00ad-109">Per altre informazioni sulla conformità alle comunicazioni e su come configurare i criteri per l'organizzazione, vedere [Conformità alle comunicazioni in Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)</span><span class="sxs-lookup"><span data-stu-id="c00ad-109">For more information on communication compliance and how to configure policies for your organization, see [Communication compliance in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a><span data-ttu-id="c00ad-110">Come usare la conformità alle comunicazioni in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c00ad-110">How to use communication compliance in Microsoft Teams</span></span>

<span data-ttu-id="c00ad-111">La conformità alle comunicazioni e Microsoft Teams sono strettamente integrate e possono contribuire a ridurre al minimo i rischi di comunicazione nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c00ad-111">Communication compliance and Microsoft Teams are tightly integrated and can help minimize communication risks in your organization.</span></span> <span data-ttu-id="c00ad-112">Dopo aver configurato i primi criteri di conformità alle comunicazioni, è possibile gestire attivamente i messaggi e i contenuti inappropriati di Microsoft Teams contrassegnati automaticamente negli avvisi.</span><span class="sxs-lookup"><span data-stu-id="c00ad-112">After you've configured your first communication compliance policies, you can actively manage inappropriate Microsoft Teams messages and content that is automatically flagged in alerts.</span></span>

### <a name="getting-started"></a><span data-ttu-id="c00ad-113">Introduzione</span><span class="sxs-lookup"><span data-stu-id="c00ad-113">Getting started</span></span>

<span data-ttu-id="c00ad-114">Introduzione alla conformità alle comunicazioni [](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) in Microsoft Teams inizia con la pianificazione e la creazione di criteri predefiniti o personalizzati per identificare le attività degli utenti inappropriati nei canali di Teams o in 1:1 e gruppi.</span><span class="sxs-lookup"><span data-stu-id="c00ad-114">Getting started with communication compliance in Microsoft Teams begins with [planning](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) and creating pre-defined or custom policies to identify inappropriate user activities in Teams channels or in 1:1 and groups.</span></span> <span data-ttu-id="c00ad-115">Tenere presente che è necessario [](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) configurare alcune autorizzazioni e prerequisiti di base durante il processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c00ad-115">Keep in mind that you'll need to [configure](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) some permissions and basic prerequisites as part of the configuration process.</span></span>

<span data-ttu-id="c00ad-116">Gli amministratori di Teams possono configurare i criteri di conformità alle comunicazioni ai livelli seguenti:</span><span class="sxs-lookup"><span data-stu-id="c00ad-116">Teams administrators can configure communication compliance policies at the following levels:</span></span>

- <span data-ttu-id="c00ad-117">**Livello utente:** i criteri a questo livello si applicano a un singolo utente di Teams o possono essere applicati a tutti gli utenti di Teams nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c00ad-117">**User level**: Policies at this level apply to an individual Teams user or may be applied to all Teams users in your organization.</span></span> <span data-ttu-id="c00ad-118">Questi criteri riguardano i messaggi che questi utenti possono inviare in chat 1:1 o di gruppo.</span><span class="sxs-lookup"><span data-stu-id="c00ad-118">These policies cover messages that these users may send in 1:1 or group chats.</span></span> <span data-ttu-id="c00ad-119">Le comunicazioni in chat per gli utenti vengono monitorate automaticamente in tutti i microsoft Teams di cui gli utenti sono membri.</span><span class="sxs-lookup"><span data-stu-id="c00ad-119">Chat communications for the users are automatically monitored across all Microsoft Teams where the users are a member.</span></span>
- <span data-ttu-id="c00ad-120">**Livello team:** i criteri a questo livello si applicano a un canale di Microsoft Team.</span><span class="sxs-lookup"><span data-stu-id="c00ad-120">**Teams level**: Policies at this level apply to a Microsoft Team channel.</span></span> <span data-ttu-id="c00ad-121">Questi criteri riguardano solo i messaggi inviati nel canale di Teams.</span><span class="sxs-lookup"><span data-stu-id="c00ad-121">These policies cover messages sent in the Teams channel only.</span></span>

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a><span data-ttu-id="c00ad-122">Intervenire sui messaggi inappropriati in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c00ad-122">Act on inappropriate messages in Microsoft Teams</span></span>

<span data-ttu-id="c00ad-123">Dopo aver configurato i criteri e aver ricevuto avvisi di conformità alle comunicazioni per i messaggi di Microsoft Teams, è il momento di consentire ai revisori della conformità dell'organizzazione di intervenire su questi messaggi.</span><span class="sxs-lookup"><span data-stu-id="c00ad-123">After you have configured your policies and have received communication compliance alerts for Microsoft Teams messages, it's time for compliance reviewers in your organization to take action on these messages.</span></span> <span data-ttu-id="c00ad-124">I revisori possono proteggere l'organizzazione esaminando gli avvisi di conformità alle comunicazioni e rimuovendo i messaggi contrassegnati dalla visualizzazione in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c00ad-124">Reviewers can help safeguard your organization by reviewing communication compliance alerts and removing flagged messages from view in Microsoft Teams.</span></span>

![Rimuovere un messaggio in Teams](./media/communication-compliance-remove-teams-message.png)

<span data-ttu-id="c00ad-126">I messaggi e i contenuti rimossi vengono sostituiti con notifiche per gli utenti che spiegano che il messaggio o il contenuto è stato rimosso e quali criteri sono applicabili alla rimozione.</span><span class="sxs-lookup"><span data-stu-id="c00ad-126">Removed messages and content are replaced with notifications for viewers explaining that the message or content has been removed and what policy is applicable to the removal.</span></span> <span data-ttu-id="c00ad-127">Il mittente del messaggio o del contenuto rimosso viene inoltre informato dello stato di rimozione e viene fornito il contenuto originale del messaggio per il contesto relativo alla rimozione.</span><span class="sxs-lookup"><span data-stu-id="c00ad-127">The sender of the removed message or content is also notified of the removal status and provided with original message content for context relating to its removal.</span></span> <span data-ttu-id="c00ad-128">Il mittente può anche visualizzare la condizione del criterio specifica che si applica alla rimozione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="c00ad-128">The sender can also view the specific policy condition that applies to the message removal.</span></span>

<span data-ttu-id="c00ad-129">Esempio di suggerimento per i criteri visualizzato dal mittente:</span><span class="sxs-lookup"><span data-stu-id="c00ad-129">Example of policy tip seen by sender:</span></span>

![Suggerimento per i criteri per il mittente](./media/communication-compliance-warning-1.png)

<span data-ttu-id="c00ad-131">Esempio di notifica di condizione dei criteri visualizzata dal mittente:</span><span class="sxs-lookup"><span data-stu-id="c00ad-131">Example of policy condition notification seen by the sender:</span></span>

![Informazioni sulle condizioni dei criteri per il mittente](./media/communication-compliance-warning-2.png)

<span data-ttu-id="c00ad-133">Esempio di suggerimento per i criteri visualizzato dal destinatario:</span><span class="sxs-lookup"><span data-stu-id="c00ad-133">Example of policy tip seen by recipient:</span></span>

![Suggerimento per i criteri per il destinatario](./media/communication-compliance-warning-3.png)
