---
title: Attivare la traduzione del messaggio in linea in Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare la traduzione in linea in Microsoft teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24f6c6a2eca313b70640dbf61a87c6c5742ea318
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570736"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="1f33d-103">Attivare la traduzione del messaggio in linea in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1f33d-103">Turn on inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="1f33d-104">La traduzione dei messaggi in linea è una nuova caratteristica di Microsoft teams che consente agli utenti di tradurre i messaggi di teams nella [lingua](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specificata dalle impostazioni della lingua personale per Office 365.</span><span class="sxs-lookup"><span data-stu-id="1f33d-104">Inline message translation is a new Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="1f33d-105">La traduzione dei messaggi in linea viene distribuita per impostazione predefinita per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1f33d-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="1f33d-106">Se si vuole consentire agli utenti di usare questa funzionalità nel client teams, è necessario attivare questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="1f33d-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on.</span></span>

> [!NOTE]
><span data-ttu-id="1f33d-107">Questa implementazione è esclusa dagli abbonamenti a Office 365 nei nostri ambienti Office 365 Government community Cloud e Office 365 Germany.</span><span class="sxs-lookup"><span data-stu-id="1f33d-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-on-inline-message-translation"></a><span data-ttu-id="1f33d-108">Usare PowerShell per attivare la traduzione in linea del messaggio</span><span class="sxs-lookup"><span data-stu-id="1f33d-108">Use PowerShell to turn on inline message translation</span></span>

<span data-ttu-id="1f33d-109">È possibile usare i criteri di messaggistica per attivare la traduzione del messaggio inline.</span><span class="sxs-lookup"><span data-stu-id="1f33d-109">You can use the messaging policy to turn on the inline message translation.</span></span>

<span data-ttu-id="1f33d-110">Attivare i criteri usando il cmdlet [set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="1f33d-110">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="1f33d-111">I criteri richiedono alcuni minuti per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1f33d-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="1f33d-112">Gli utenti potrebbero dover disconnettersi e accedere di nuovo a teams.</span><span class="sxs-lookup"><span data-stu-id="1f33d-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a><span data-ttu-id="1f33d-113">Usare l'interfaccia di amministrazione di Microsoft teams per attivare la traduzione dei messaggi in linea</span><span class="sxs-lookup"><span data-stu-id="1f33d-113">Use the Microsoft Teams admin center to turn on inline message translation</span></span>

<span data-ttu-id="1f33d-114">Nell'interfaccia di **amministrazione di Microsoft teams**selezionare **criteri di messaggistica** dalla barra di spostamento sinistra, quindi creare un nuovo criterio o modificare un criterio esistente e impostare l'opzione **Consenti agli utenti di tradurre i messaggi** **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="1f33d-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Allow users to translate messages** option to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="1f33d-115">Il servizio esegue la traduzione e lo recapita al client senza alcun effetto sul contenuto acquisito nei record di conformità.</span><span class="sxs-lookup"><span data-stu-id="1f33d-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="1f33d-116">Per ulteriori informazioni sulla traduzione, vedere [che cos'è Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="1f33d-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>