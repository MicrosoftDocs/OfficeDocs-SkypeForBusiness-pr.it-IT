---
title: Conformità delle comunicazioni per Microsoft Teams
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
ms.openlocfilehash: 01d9906044fe0ea8472cd8bb2ba8ccf247cdbeb9
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121696"
---
# <a name="communication-compliance-for-microsoft-teams"></a><span data-ttu-id="ebf87-103">Conformità delle comunicazioni per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ebf87-103">Communication compliance for Microsoft Teams</span></span>

<span data-ttu-id="ebf87-104">La conformità delle comunicazioni fa parte della nuova soluzione Insider Risk impostata in Microsoft 365 che consente di ridurre al minimo i rischi per la comunicazione aiutandoli a rilevare, acquisire e adottare azioni correttive per i messaggi non appropriati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ebf87-104">Communication compliance is part of the new insider risk solution set in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and take remediation actions for inappropriate messages in your organization.</span></span> <span data-ttu-id="ebf87-105">Aiuta ad identificare il linguaggio offensivo e l'anti-molestia nei canali del team o in 1:1 e chat di gruppo.</span><span class="sxs-lookup"><span data-stu-id="ebf87-105">It helps in identifying Offensive language and anti-harassment in Team Channels or 1:1 and Group chats.</span></span> <span data-ttu-id="ebf87-106">È anche possibile impostare i criteri per verificare se le informazioni riservate vengono condivise come parte dei canali del team o di 1:1 e chat di gruppo.</span><span class="sxs-lookup"><span data-stu-id="ebf87-106">You can also set policies to see if any Sensitive information is being shared as part of Team channels or 1:1 and Group chats.</span></span> <span data-ttu-id="ebf87-107">Per altre informazioni sui diversi tipi di criteri e su come configurarlo, vedere l' [articolo di M365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span><span class="sxs-lookup"><span data-stu-id="ebf87-107">For more information on different types of policies and how to set up refer to the [M365 article](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-teams"></a><span data-ttu-id="ebf87-108">Come usare la conformità delle comunicazioni in teams</span><span class="sxs-lookup"><span data-stu-id="ebf87-108">How to use communication compliance in Teams</span></span>

### <a name="identify-inappropriate-messages"></a><span data-ttu-id="ebf87-109">Identificare i messaggi non appropriati</span><span class="sxs-lookup"><span data-stu-id="ebf87-109">Identify inappropriate messages</span></span>

<span data-ttu-id="ebf87-110">Per identificare i messaggi inviati in Microsoft Teams (1:1, chat di gruppo o conversazioni di canale) che contengono un linguaggio offensivo o anti-molestie, è possibile abilitare i criteri per identificare il problema e il revisore può esaminare i messaggi e eseguire le operazioni necessarie, ad esempio l'invio di materiale didattico o l'escalation alle autorità di destra.</span><span class="sxs-lookup"><span data-stu-id="ebf87-110">If you want to identify any messages that are sent in Microsoft Teams (1:1, Group Chats or Channel conversations) contain Offensive Language or anti-harassment, you can enable policies to identify this and the reviewer can look into the messages and take necessary steps like sending training material or escalate to the right authorities.</span></span>

### <a name="identify-sensitive-or-regulatory-information"></a><span data-ttu-id="ebf87-111">Identificare informazioni riservate o normative</span><span class="sxs-lookup"><span data-stu-id="ebf87-111">Identify sensitive or Regulatory information</span></span>

<span data-ttu-id="ebf87-112">Per analizzare i messaggi inviati in Microsoft Teams (1:1, chat di gruppo o conversazioni di canale) per informazioni riservate o tipi di regolamentazione, è possibile scegliere i criteri che supportano i tipi di normative o sensibili predefiniti.</span><span class="sxs-lookup"><span data-stu-id="ebf87-112">If you want to scan messages sent in Microsoft Teams (1:1, Group Chats or Channel conversations) for sensitive information or regulatory types, you can choose policies that support predefined sensitive or regulatory types.</span></span>

> [!NOTE]
> <span data-ttu-id="ebf87-113">I canali privati non sono supportati dalla conformità delle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="ebf87-113">Private channels are not supported by communication compliance.</span></span>

### <a name="custom-policy"></a><span data-ttu-id="ebf87-114">Criteri personalizzati</span><span class="sxs-lookup"><span data-stu-id="ebf87-114">Custom Policy</span></span>

<span data-ttu-id="ebf87-115">Usare questo modello per configurare specifici canali di comunicazione, singole condizioni di rilevamento e la quantità di contenuto da monitorare e rivedere nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ebf87-115">Use this template to configure specific communication channels, individual detection conditions, and the amount of content to monitor and review in your organization.</span></span>

### <a name="custom-trainable-classifier"></a><span data-ttu-id="ebf87-116">Classificatore addestrabile personalizzato</span><span class="sxs-lookup"><span data-stu-id="ebf87-116">Custom Trainable classifier</span></span>

<span data-ttu-id="ebf87-117">Usare i classificatori trainable quando uno dei classificatori fuori sede non soddisfa le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="ebf87-117">Use trainable classifiers when one of the out of the box classifiers won't meet your needs.</span></span> <span data-ttu-id="ebf87-118">Un classificatore Microsoft 365 è uno strumento che puoi addestrare per riconoscere vari tipi di contenuto dandogli esempi da esaminare.</span><span class="sxs-lookup"><span data-stu-id="ebf87-118">A Microsoft 365 classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="ebf87-119">Formazione il classificatore include prima di tutto gli esempi che sono scelti in modo umano e corrispondono positivamente alla categoria.</span><span class="sxs-lookup"><span data-stu-id="ebf87-119">Training the classifier involves first giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="ebf87-120">Dopo aver elaborato questi esempi, è quindi possibile testare le stime assegnando una combinazione di esempi positivi e negativi.</span><span class="sxs-lookup"><span data-stu-id="ebf87-120">Then, after it has processed those samples, you test the predictions by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="ebf87-121">Per altre informazioni su questo argomento, vedere l' [articolo di M365](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier) .</span><span class="sxs-lookup"><span data-stu-id="ebf87-121">To Lean more about this refer to the [M365 article](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier) for more on this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="ebf87-122">La conformità delle comunicazioni ora supporta le distribuzioni ibride di Exchange.</span><span class="sxs-lookup"><span data-stu-id="ebf87-122">Communication compliance now supports Exchange hybrid deployments.</span></span>

<span data-ttu-id="ebf87-123">La conformità delle comunicazioni supporta la cronologia delle conversazioni per tutti i messaggi corrispondenti alle forze di polizia.</span><span class="sxs-lookup"><span data-stu-id="ebf87-123">Communication compliance supports conversation history for any messages that match the polices.</span></span> <span data-ttu-id="ebf87-124">Questo fornisce il contesto all'amministratore delle indagini.</span><span class="sxs-lookup"><span data-stu-id="ebf87-124">This provides context to the investigating admin.</span></span>

:::image type="content" source="media/communication-compliance-1.png" alt-text="Uno schermo per la conformità delle comunicazioni in Microsoft teams.":::

## <a name="where-communication-policies-can-be-applied-in-teams"></a><span data-ttu-id="ebf87-126">Dove i criteri di comunicazione possono essere applicati in teams</span><span class="sxs-lookup"><span data-stu-id="ebf87-126">Where communication policies can be applied in Teams</span></span>

<span data-ttu-id="ebf87-127">I criteri di conformità delle comunicazioni possono essere impostati per i messaggi inviati in teams ai livelli seguenti:</span><span class="sxs-lookup"><span data-stu-id="ebf87-127">Communication compliance policies can be setup for messages sent in Teams at the following levels:</span></span>

- <span data-ttu-id="ebf87-128">Livello utente: un amministratore può configurare i criteri a livello di singolo utente o applicarlo a tutti gli utenti del tenant.</span><span class="sxs-lookup"><span data-stu-id="ebf87-128">User level : An admin can set up policies at an individual user level or apply it to all the users on the tenant.</span></span> <span data-ttu-id="ebf87-129">Verranno illustrati solo i messaggi inviati da un utente in 1:1 o chat di gruppo.</span><span class="sxs-lookup"><span data-stu-id="ebf87-129">This will only covers messages that a user sent in 1:1 or Group chats.</span></span>
- <span data-ttu-id="ebf87-130">Livello di Team: un amministratore può anche configurare i criteri in un team.</span><span class="sxs-lookup"><span data-stu-id="ebf87-130">Team Level: An admin can also set up policies on a team.</span></span> <span data-ttu-id="ebf87-131">In questo articolo vengono illustrati tutti i messaggi inviati nel canale del team (i messaggi di canale privato non sono supportati).</span><span class="sxs-lookup"><span data-stu-id="ebf87-131">This covers all the messages sent in the channel in that team (Private channel messages are not supported).</span></span>
