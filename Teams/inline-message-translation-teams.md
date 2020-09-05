---
title: Attivare la traduzione in linea del messaggio
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
description: Informazioni su come attivare la traduzione in linea in Microsoft teams usando l'interfaccia di amministrazione di Microsoft teams o PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 012f2431ec7fb249a2f2e3b963c41166c4649a5c
ms.sourcegitcommit: 2e6b0930645cd97dbd597e9346a6fe1788c6facf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2020
ms.locfileid: "47395385"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="517cd-103">Disattivare la traduzione del messaggio in linea in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="517cd-103">Turn off inline message translation in Microsoft Teams</span></span>
=================================================

<span data-ttu-id="517cd-104">La traduzione in linea dei messaggi è una caratteristica di Microsoft teams che consente agli utenti di tradurre i messaggi di teams nella [lingua](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specificata dalle impostazioni della lingua personale.</span><span class="sxs-lookup"><span data-stu-id="517cd-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="517cd-105">La traduzione dei messaggi in linea viene distribuita per impostazione predefinita per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="517cd-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="517cd-106">Non è necessario apportare modifiche se si vuole consentire agli utenti di usare questa funzionalità nel client teams.</span><span class="sxs-lookup"><span data-stu-id="517cd-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="517cd-107">Questa implementazione è esclusa dagli abbonamenti a Office 365 nei nostri ambienti Office 365 Government community Cloud e Office 365 Germany.</span><span class="sxs-lookup"><span data-stu-id="517cd-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="517cd-108">Usare PowerShell per disattivare la traduzione in linea del messaggio</span><span class="sxs-lookup"><span data-stu-id="517cd-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="517cd-109">È possibile usare i criteri di messaggistica per disattivare la traduzione del messaggio inline.</span><span class="sxs-lookup"><span data-stu-id="517cd-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="517cd-110">Disattivare il criterio usando il cmdlet [set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="517cd-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="517cd-111">I criteri richiedono alcuni minuti per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="517cd-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="517cd-112">Gli utenti potrebbero dover disconnettersi e accedere di nuovo a teams.</span><span class="sxs-lookup"><span data-stu-id="517cd-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="517cd-113">Usare l'interfaccia di amministrazione di Microsoft teams per disattivare la traduzione dei messaggi in linea</span><span class="sxs-lookup"><span data-stu-id="517cd-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="517cd-114">Nell'interfaccia di **amministrazione di Microsoft teams**selezionare **criteri di messaggistica** dalla barra di spostamento sinistra, quindi creare un nuovo criterio o modificare un criterio esistente e impostare l'opzione **Traduci messaggi** su **disattivato**.</span><span class="sxs-lookup"><span data-stu-id="517cd-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="517cd-115">Il servizio esegue la traduzione e lo recapita al client senza alcun effetto sul contenuto acquisito nei record di conformità.</span><span class="sxs-lookup"><span data-stu-id="517cd-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="517cd-116">Per ulteriori informazioni sulla traduzione, vedere [che cos'è Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)</span><span class="sxs-lookup"><span data-stu-id="517cd-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)</span></span>
