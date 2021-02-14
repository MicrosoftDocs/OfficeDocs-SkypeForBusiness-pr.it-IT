---
title: PowerShell di aggiornamento di base| Microsoft Teams| Criteri di interoperabilità per l'aggiornamento
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni su un programma per l'aggiornamento a Microsoft Teams se l'interfaccia di amministrazione non è stata ancora accesa nel tenant.
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
ms.openlocfilehash: adb9a0854268df25ebb8dc0337db22f792834b36
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809096"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="1ac18-103">Aggiornamento degli utenti da Skype for Business online a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1ac18-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="1ac18-104">I comandi descritti in questo articolo sono progettati per essere usati nell'elenco di controllo [di base per l'aggiornamento.](https://aka.ms/UpgradeBasic)</span><span class="sxs-lookup"><span data-stu-id="1ac18-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="1ac18-105">Gli aspetti tecnici relativi alla migrazione implicano la notifica agli utenti che Skype for Business eserciterà l'aggiornamento a Teams e quindi li sposta in modalità **solo Teams.**</span><span class="sxs-lookup"><span data-stu-id="1ac18-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="1ac18-106">Questa procedura può essere eseguita tramite una sessione di Windows PowerShell remota di Skype for Business o tramite l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1ac18-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="1ac18-107">Stiamo implementazione attiva degli strumenti di aggiornamento nell'interfaccia di amministrazione di [Microsoft Teams,](manage-teams-skypeforbusiness-admin-center.md)che dovrebbe essere disponibile a breve nel tuo tenant.</span><span class="sxs-lookup"><span data-stu-id="1ac18-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="1ac18-108">Non appena è disponibile, è possibile trovare informazioni sulla migrazione degli utenti in Impostazione delle impostazioni di [coesistenza e aggiornamento.](https://aka.ms/SkypeToTeams-SetCoexistence)</span><span class="sxs-lookup"><span data-stu-id="1ac18-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="1ac18-109">Se si è pronti per eseguire l'aggiornamento, è possibile usare i [comandi di PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1ac18-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="1ac18-110">Passaggio di base dell'aggiornamento #</span><span class="sxs-lookup"><span data-stu-id="1ac18-110">Upgrade Basic step #</span></span> | <span data-ttu-id="1ac18-111">Modalità</span><span class="sxs-lookup"><span data-stu-id="1ac18-111">Mode</span></span> | <span data-ttu-id="1ac18-112">Comando di PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ac18-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="1ac18-113">5</span><span class="sxs-lookup"><span data-stu-id="1ac18-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="1ac18-114">Isole + Notifica all'utente Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1ac18-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="1ac18-115">Usare questo comando se gli utenti sono in **modalità** Isole (impostazione predefinita))</span><span class="sxs-lookup"><span data-stu-id="1ac18-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="1ac18-116">*(ad esempio $ SipAddress='TestUser@contoso.com')*</span><span class="sxs-lookup"><span data-stu-id="1ac18-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="1ac18-117">5</span><span class="sxs-lookup"><span data-stu-id="1ac18-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="1ac18-118">Solo Skype for Business + Notifica all'utente Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1ac18-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="1ac18-119">(Utilizzare questo comando se gli utenti sono attualmente in **modalità solo Skype for Business)**</span><span class="sxs-lookup"><span data-stu-id="1ac18-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="1ac18-120">7</span><span class="sxs-lookup"><span data-stu-id="1ac18-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="1ac18-121">Solo Teams</span><span class="sxs-lookup"><span data-stu-id="1ac18-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
