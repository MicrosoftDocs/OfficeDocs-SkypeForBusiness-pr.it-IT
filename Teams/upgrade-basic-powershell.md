---
title: PowerShell di aggiornamento di base| Microsoft Teams| Concedere i criteri di interoperabilità per l'aggiornamento
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni su un'interruzione dell'aggiornamento a Microsoft Teams se l'interfaccia di amministrazione non è stata accesa nel tenant.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef164ee5d93cb5491923ef3b319ae51134924cc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120542"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="008df-103">Aggiornamento degli utenti da Skype for Business Online a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="008df-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="008df-104">I comandi descritti in questo articolo sono progettati per essere usati nell'elenco [di controllo Aggiornamento di base.](./upgrade-start-here.md)</span><span class="sxs-lookup"><span data-stu-id="008df-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](./upgrade-start-here.md) checklist.</span></span>

<span data-ttu-id="008df-105">Gli aspetti tecnici della migrazione dell'aggiornamento implicano la notifica agli utenti che Skype for Business verrà eseguito l'aggiornamento a Teams e quindi spostarli in una modalità **Teams solo** versione.</span><span class="sxs-lookup"><span data-stu-id="008df-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="008df-106">Questa procedura può essere eseguita tramite una sessione Skype for Business remota Windows PowerShell o tramite l'Microsoft Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="008df-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="008df-107">Stiamo attivamente implementazione degli strumenti [](manage-teams-skypeforbusiness-admin-center.md)di aggiornamento nell'interfaccia di amministrazione Microsoft Teams e dovrebbe essere disponibile a breve nel tenant.</span><span class="sxs-lookup"><span data-stu-id="008df-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="008df-108">Non appena sarà disponibile, è possibile trovare informazioni sulla migrazione degli utenti in Impostazione [delle impostazioni di coesistenza e aggiornamento.](./setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="008df-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="008df-109">Se si è pronti per l'aggiornamento, è possibile usare i [comandi di PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="008df-109">If you're ready to upgrade today, you can use the [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="008df-110">Passaggio di base dell'aggiornamento #</span><span class="sxs-lookup"><span data-stu-id="008df-110">Upgrade Basic step #</span></span> | <span data-ttu-id="008df-111">Modalità</span><span class="sxs-lookup"><span data-stu-id="008df-111">Mode</span></span> | <span data-ttu-id="008df-112">Comando di PowerShell</span><span class="sxs-lookup"><span data-stu-id="008df-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="008df-113">5</span><span class="sxs-lookup"><span data-stu-id="008df-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="008df-114">Isole + Notifica all'Skype for Business utente</span><span class="sxs-lookup"><span data-stu-id="008df-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="008df-115">Usare questo comando se gli utenti sono attualmente in **modalità** Isole (impostazione predefinita))</span><span class="sxs-lookup"><span data-stu-id="008df-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="008df-116">*(ad esempio, $SipAddress='TestUser@contoso.com')*</span><span class="sxs-lookup"><span data-stu-id="008df-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="008df-117">5</span><span class="sxs-lookup"><span data-stu-id="008df-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="008df-118">Skype for Business Solo + Notifica all'Skype for Business utente</span><span class="sxs-lookup"><span data-stu-id="008df-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="008df-119">Usare questo comando se gli utenti sono attualmente in **Skype for Business modalità Solo** utenti)</span><span class="sxs-lookup"><span data-stu-id="008df-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="008df-120">7</span><span class="sxs-lookup"><span data-stu-id="008df-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="008df-121">Teams Solo</span><span class="sxs-lookup"><span data-stu-id="008df-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |