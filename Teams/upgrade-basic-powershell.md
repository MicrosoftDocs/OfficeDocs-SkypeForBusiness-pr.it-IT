---
title: PowerShell di aggiornamento di base | Microsoft Teams | Concedere i criteri di interoperabilità di aggiornamento
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Tappabuchi per l'aggiornamento a teams se l'interfaccia di amministrazione non è stata illuminata nel tenant.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 84ecfb8b9286b749e5b1bf6d34cdf0c8c8fd4113
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139675"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="4f141-103">Aggiornamento degli utenti da Skype for business online a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f141-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="4f141-104">I comandi descritti in questo articolo sono progettati per essere usati come parte dell'elenco di controllo di base per l' [aggiornamento](https://aka.ms/UpgradeBasic) .</span><span class="sxs-lookup"><span data-stu-id="4f141-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="4f141-105">Gli aspetti relativi alla migrazione tecnica dell'aggiornamento comportano la notifica agli utenti che Skype for business aggiornerà i team e li sposterà in modalità **solo teams** .</span><span class="sxs-lookup"><span data-stu-id="4f141-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="4f141-106">Questa procedura può essere eseguita tramite una sessione remota di Windows PowerShell di Skype for business o tramite l'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="4f141-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="4f141-107">Stiamo attivamente implementando gli strumenti di aggiornamento nell'interfaccia di [amministrazione di Microsoft teams](manage-teams-skypeforbusiness-admin-center.md), che dovrebbe essere presto disponibile nel tenant.</span><span class="sxs-lookup"><span data-stu-id="4f141-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="4f141-108">Non appena è disponibile, è possibile trovare informazioni sulla migrazione degli utenti nell' [impostazione delle impostazioni di coesistenza e aggiornamento](https://aka.ms/SkypeToTeams-SetCoexistence).</span><span class="sxs-lookup"><span data-stu-id="4f141-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="4f141-109">Se si è pronti per l'aggiornamento oggi, è possibile usare i comandi di [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="4f141-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="4f141-110">Passaggio di base per l'aggiornamento #</span><span class="sxs-lookup"><span data-stu-id="4f141-110">Upgrade Basic step #</span></span> | <span data-ttu-id="4f141-111">Modalità</span><span class="sxs-lookup"><span data-stu-id="4f141-111">Mode</span></span> | <span data-ttu-id="4f141-112">Comando di PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f141-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="4f141-113">5</span><span class="sxs-lookup"><span data-stu-id="4f141-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="4f141-114">Isole + notifica all'utente Skype for business</span><span class="sxs-lookup"><span data-stu-id="4f141-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="4f141-115">(Usare questo comando se gli utenti sono attualmente in modalità **isole** (impostazione predefinita))</span><span class="sxs-lookup"><span data-stu-id="4f141-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="4f141-116">*ad esempio, $SipAddress =' TestUser@contoso.com ')*</span><span class="sxs-lookup"><span data-stu-id="4f141-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="4f141-117">5</span><span class="sxs-lookup"><span data-stu-id="4f141-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="4f141-118">Skype for business solo + avvisa l'utente di Skype for business</span><span class="sxs-lookup"><span data-stu-id="4f141-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="4f141-119">(Usare questo comando se gli utenti sono attualmente in modalità **solo Skype for business** )</span><span class="sxs-lookup"><span data-stu-id="4f141-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="4f141-120">7</span><span class="sxs-lookup"><span data-stu-id="4f141-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="4f141-121">Solo Teams</span><span class="sxs-lookup"><span data-stu-id="4f141-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
