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
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="3a98d-103">Aggiornamento degli utenti da Skype for Business Online a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3a98d-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="3a98d-104">I comandi descritti in questo articolo sono progettati per essere usati nell'elenco [di controllo Aggiornamento di base.](./upgrade-start-here.md)</span><span class="sxs-lookup"><span data-stu-id="3a98d-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](./upgrade-start-here.md) checklist.</span></span>

<span data-ttu-id="3a98d-105">Gli aspetti tecnici della migrazione dell'aggiornamento implicano la notifica agli utenti che Skype for Business esegue l'aggiornamento a Teams e quindi li sposta in modalità **Solo** Teams.</span><span class="sxs-lookup"><span data-stu-id="3a98d-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="3a98d-106">Questa procedura può essere eseguita tramite una sessione di Windows PowerShell remota di Skype for Business o tramite l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3a98d-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="3a98d-107">Stiamo attivamente implementazione degli strumenti di aggiornamento nell'interfaccia di amministrazione di [Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)e dovrebbe essere disponibile a breve nel tenant.</span><span class="sxs-lookup"><span data-stu-id="3a98d-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="3a98d-108">Non appena sarà disponibile, è possibile trovare informazioni sulla migrazione degli utenti in Impostazione [delle impostazioni di coesistenza e aggiornamento.](./setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3a98d-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="3a98d-109">Se si è pronti per l'aggiornamento, è possibile usare i [comandi di PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3a98d-109">If you're ready to upgrade today, you can use the [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="3a98d-110">Passaggio di base dell'aggiornamento #</span><span class="sxs-lookup"><span data-stu-id="3a98d-110">Upgrade Basic step #</span></span> | <span data-ttu-id="3a98d-111">Modalità</span><span class="sxs-lookup"><span data-stu-id="3a98d-111">Mode</span></span> | <span data-ttu-id="3a98d-112">Comando di PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a98d-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="3a98d-113">5</span><span class="sxs-lookup"><span data-stu-id="3a98d-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="3a98d-114">Isole + Invia una notifica all'utente skype for business</span><span class="sxs-lookup"><span data-stu-id="3a98d-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="3a98d-115">Usare questo comando se gli utenti sono attualmente in **modalità** Isole (impostazione predefinita))</span><span class="sxs-lookup"><span data-stu-id="3a98d-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="3a98d-116">*(ad esempio, $SipAddress='TestUser@contoso.com')*</span><span class="sxs-lookup"><span data-stu-id="3a98d-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="3a98d-117">5</span><span class="sxs-lookup"><span data-stu-id="3a98d-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="3a98d-118">Solo Skype for Business + Notifica all'utente Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3a98d-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="3a98d-119">(Usa questo comando se gli utenti sono attualmente in **modalità Solo Skype for Business)**</span><span class="sxs-lookup"><span data-stu-id="3a98d-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="3a98d-120">7</span><span class="sxs-lookup"><span data-stu-id="3a98d-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="3a98d-121">Solo Teams</span><span class="sxs-lookup"><span data-stu-id="3a98d-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |