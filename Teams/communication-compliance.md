---
title: Conformità delle comunicazioni con Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Informazioni sulla conformità delle comunicazioni, parte del set di soluzioni di rischio Insider, dalla prospettiva Microsoft Teams (questo fa parte della funzionalità di conformità delle comunicazioni di M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a8fa1bcc7190050fd06c15717aebf8648f94b090
ms.sourcegitcommit: 8816b58e175031cb0a71e0d0e89e447a7b83a760
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597150"
---
# <a name="communication-compliance-with-microsoft-teams"></a><span data-ttu-id="a85b9-103">Conformità delle comunicazioni con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a85b9-103">Communication compliance with Microsoft Teams</span></span>

<span data-ttu-id="a85b9-104">La conformità delle comunicazioni è una soluzione di rischio insider in Microsoft 365 che consente di ridurre al minimo i rischi per la comunicazione aiutandoli a rilevare, acquisire e agire su messaggi non appropriati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a85b9-104">Communication compliance is an insider risk solution in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span>

<span data-ttu-id="a85b9-105">Per Microsoft teams, la conformità delle comunicazioni consente di identificare i [seguenti tipi](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) di contenuto non appropriato nei canali di teams o in 1:1 e chat di gruppo:</span><span class="sxs-lookup"><span data-stu-id="a85b9-105">For Microsoft Teams, communication compliance helps identify the [following types](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) of inappropriate content in Teams channels or in 1:1 and group chats:</span></span>

- <span data-ttu-id="a85b9-106">Linguaggio offensivo, profano e molesto</span><span class="sxs-lookup"><span data-stu-id="a85b9-106">Offensive, profane, and harassing language</span></span>
- <span data-ttu-id="a85b9-107">Immagini adulte, audace e cruente</span><span class="sxs-lookup"><span data-stu-id="a85b9-107">Adult, racy, and gory images</span></span>
- <span data-ttu-id="a85b9-108">Condivisione di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="a85b9-108">Sharing of sensitive information</span></span>

>[!IMPORTANT]
><span data-ttu-id="a85b9-109">I canali privati di Microsoft teams non sono supportati dalla conformità delle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="a85b9-109">Private Microsoft Teams channels are not supported by communication compliance.</span></span> <span data-ttu-id="a85b9-110">Le comunicazioni tramite chat inviate dagli utenti Guest agli utenti del team non vengono monitorate per contenuti non appropriati.</span><span class="sxs-lookup"><span data-stu-id="a85b9-110">Chat communications sent by guest users to Teams users aren't monitored for inappropriate content.</span></span>

<span data-ttu-id="a85b9-111">Per altre informazioni sulla conformità delle comunicazioni e su come configurare i criteri per l'organizzazione, vedere [conformità delle comunicazioni in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span><span class="sxs-lookup"><span data-stu-id="a85b9-111">For more information on communication compliance and how to configure policies for your organization, see [Communication compliance in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a><span data-ttu-id="a85b9-112">Come usare la conformità delle comunicazioni in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a85b9-112">How to use communication compliance in Microsoft Teams</span></span>

<span data-ttu-id="a85b9-113">Conformità delle comunicazioni e Microsoft teams sono strettamente integrati e consentono di ridurre al minimo i rischi per la comunicazione nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a85b9-113">Communication compliance and Microsoft Teams are tightly integrated and can help minimize communication risks in your organization.</span></span> <span data-ttu-id="a85b9-114">Dopo aver configurato i primi criteri di conformità delle comunicazioni, è possibile gestire attivamente i messaggi e i contenuti di Microsoft teams inappropriati che vengono contrassegnati automaticamente in avvisi.</span><span class="sxs-lookup"><span data-stu-id="a85b9-114">After you've configured your first communication compliance policies, you can actively manage inappropriate Microsoft Teams messages and content that is automatically flagged in alerts.</span></span>

### <a name="getting-started"></a><span data-ttu-id="a85b9-115">Introduzione</span><span class="sxs-lookup"><span data-stu-id="a85b9-115">Getting started</span></span>

<span data-ttu-id="a85b9-116">Per iniziare a usare la conformità delle comunicazioni in Microsoft teams, inizia con la [pianificazione](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) e la creazione di criteri predefiniti o personalizzati per identificare le attività degli utenti non appropriate nei canali dei team o in 1:1 e gruppi.</span><span class="sxs-lookup"><span data-stu-id="a85b9-116">Getting started with communication compliance in Microsoft Teams begins with [planning](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) and creating pre-defined or custom policies to identify inappropriate user activities in Teams channels or in 1:1 and groups.</span></span> <span data-ttu-id="a85b9-117">Tieni presente che è necessario [configurare](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) alcune autorizzazioni e prerequisiti di base come parte del processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a85b9-117">Keep in mind that you'll need to [configure](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) some permissions and basic prerequisites as part of the configuration process.</span></span>

<span data-ttu-id="a85b9-118">Gli amministratori dei team possono configurare i criteri di conformità delle comunicazioni ai livelli seguenti:</span><span class="sxs-lookup"><span data-stu-id="a85b9-118">Teams administrators can configure communication compliance policies at the following levels:</span></span>

- <span data-ttu-id="a85b9-119">**Livello utente**: i criteri a questo livello si applicano a un singolo utente di teams o possono essere applicati a tutti gli utenti di Teams dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a85b9-119">**User level**: Policies at this level apply to an individual Teams user or may be applied to all Teams users in your organization.</span></span> <span data-ttu-id="a85b9-120">Questi criteri includono i messaggi che possono essere inviati da questi utenti in 1:1 o in chat di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a85b9-120">These policies cover messages that these users may send in 1:1 or group chats.</span></span> <span data-ttu-id="a85b9-121">Le comunicazioni tramite chat per gli utenti vengono monitorate automaticamente in tutti i team di Microsoft in cui gli utenti sono membri.</span><span class="sxs-lookup"><span data-stu-id="a85b9-121">Chat communications for the users are automatically monitored across all Microsoft Teams where the users are a member.</span></span>
- <span data-ttu-id="a85b9-122">**Livello teams**: i criteri a questo livello si applicano a un canale di Microsoft Team.</span><span class="sxs-lookup"><span data-stu-id="a85b9-122">**Teams level**: Policies at this level apply to a Microsoft Team channel.</span></span> <span data-ttu-id="a85b9-123">Questi criteri coprono i messaggi inviati solo nel canale teams.</span><span class="sxs-lookup"><span data-stu-id="a85b9-123">These policies cover messages sent in the Teams channel only.</span></span>

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a><span data-ttu-id="a85b9-124">Agire su messaggi non appropriati in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a85b9-124">Act on inappropriate messages in Microsoft Teams</span></span>

<span data-ttu-id="a85b9-125">Dopo aver configurato i criteri e aver ricevuto avvisi per la conformità delle comunicazioni per i messaggi di Microsoft teams, è ora che i revisori di conformità dell'organizzazione intervengano in questi messaggi.</span><span class="sxs-lookup"><span data-stu-id="a85b9-125">After you have configured your policies and have received communication compliance alerts for Microsoft Teams messages, it's time for compliance reviewers in your organization to take action on these messages.</span></span> <span data-ttu-id="a85b9-126">I revisori possono aiutare a salvaguardare l'organizzazione rivedendo gli avvisi di conformità delle comunicazioni e rimuovendo i messaggi contrassegnati dalla visualizzazione in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="a85b9-126">Reviewers can help safeguard your organization by reviewing communication compliance alerts and removing flagged messages from view in Microsoft Teams.</span></span>

![Rimuovere un messaggio in teams](./media/communication-compliance-remove-teams-message.png)

<span data-ttu-id="a85b9-128">I messaggi rimossi e il contenuto vengono sostituiti con le notifiche per i visualizzatori che spiegano che il messaggio o il contenuto è stato rimosso e quali criteri sono applicabili alla rimozione.</span><span class="sxs-lookup"><span data-stu-id="a85b9-128">Removed messages and content are replaced with notifications for viewers explaining that the message or content has been removed and what policy is applicable to the removal.</span></span> <span data-ttu-id="a85b9-129">Al mittente del messaggio o del contenuto rimosso viene anche notificato lo stato di rimozione e viene fornito il contenuto originale del messaggio per il contesto relativo alla relativa rimozione.</span><span class="sxs-lookup"><span data-stu-id="a85b9-129">The sender of the removed message or content is also notified of the removal status and provided with original message content for context relating to its removal.</span></span> <span data-ttu-id="a85b9-130">Il mittente può anche visualizzare la condizione di criteri specifica che si applica alla rimozione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="a85b9-130">The sender can also view the specific policy condition that applies to the message removal.</span></span>

<span data-ttu-id="a85b9-131">Esempio di suggerimento per i criteri visualizzato dal mittente:</span><span class="sxs-lookup"><span data-stu-id="a85b9-131">Example of policy tip seen by sender:</span></span>

![Suggerimento per i criteri per il mittente](./media/communication-compliance-warning-1.png)

<span data-ttu-id="a85b9-133">Esempio di notifica della condizione dei criteri visualizzata dal mittente:</span><span class="sxs-lookup"><span data-stu-id="a85b9-133">Example of policy condition notification seen by the sender:</span></span>

![Informazioni sulle condizioni dei criteri per il mittente](./media/communication-compliance-warning-2.png)

<span data-ttu-id="a85b9-135">Esempio di suggerimento per i criteri visualizzato dal destinatario:</span><span class="sxs-lookup"><span data-stu-id="a85b9-135">Example of policy tip seen by recipient:</span></span>

![Suggerimento per i criteri per il destinatario](./media/communication-compliance-warning-3.png)