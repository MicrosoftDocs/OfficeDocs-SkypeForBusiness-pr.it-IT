---
title: Attivare la traduzione dei messaggi in linea
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
description: Informazioni su come attivare la traduzione in linea in Microsoft Teams usando l'interfaccia di amministrazione di Microsoft Teams o PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5c9e34c5e539d32b25259098973e9bfe6795ad7c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120627"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="c924a-103">Disattivare la traduzione dei messaggi in linea in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c924a-103">Turn off inline message translation in Microsoft Teams</span></span>
=================================================

<span data-ttu-id="c924a-104">La traduzione dei messaggi in linea è una funzionalità di Microsoft Teams che consente agli utenti di tradurre i messaggi di Teams [nella](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) lingua specificata dalle impostazioni della lingua personale.</span><span class="sxs-lookup"><span data-stu-id="c924a-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="c924a-105">La traduzione dei messaggi in linea viene implementazione per impostazione predefinita per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c924a-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="c924a-106">Non è necessario apportare modifiche se si vuole consentire agli utenti di usare questa funzionalità all'interno del client Teams.</span><span class="sxs-lookup"><span data-stu-id="c924a-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="c924a-107">Questa implementazione è esclusa dagli abbonamenti a Office 365 negli ambienti Office 365 Government Community Cloud e Office 365 Germany.</span><span class="sxs-lookup"><span data-stu-id="c924a-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="c924a-108">Usare PowerShell per disattivare la traduzione dei messaggi in linea</span><span class="sxs-lookup"><span data-stu-id="c924a-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="c924a-109">È possibile usare i criteri di messaggistica per disattivare la traduzione dei messaggi in linea.</span><span class="sxs-lookup"><span data-stu-id="c924a-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="c924a-110">Disattivare i criteri usando il cmdlet [Set-CsTeamsMessagingPolicy.](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c924a-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="c924a-111">L'applicazione del criterio richiede alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="c924a-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="c924a-112">Gli utenti potrebbero dover disconnettersi e accedere di nuovo a Teams.</span><span class="sxs-lookup"><span data-stu-id="c924a-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="c924a-113">Usare l'interfaccia di amministrazione di Microsoft Teams per disattivare la traduzione dei messaggi in linea</span><span class="sxs-lookup"><span data-stu-id="c924a-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="c924a-114">Nell'interfaccia **di amministrazione di Microsoft Teams** selezionare Criteri di messaggistica nel riquadro di spostamento  sinistro, quindi creare un nuovo criterio o modificare un criterio esistente e impostare l'opzione Traduci messaggi su **Disattivato.** </span><span class="sxs-lookup"><span data-stu-id="c924a-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="c924a-115">Il servizio esegue la traduzione e la consegna al client senza alcun effetto sul contenuto acquisito nei record di conformità.</span><span class="sxs-lookup"><span data-stu-id="c924a-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="c924a-116">Per altre informazioni sulla traduzione, vedere [Che cos'è Microsoft Translator?](/azure/cognitive-services/translator/translator-info-overview)</span><span class="sxs-lookup"><span data-stu-id="c924a-116">To learn more about translation, see [What is Microsoft Translator?](/azure/cognitive-services/translator/translator-info-overview)</span></span>