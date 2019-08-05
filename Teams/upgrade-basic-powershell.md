---
title: PowerShell di aggiornamento di base | Microsoft Teams | Concedere i criteri di interoperabilità di aggiornamento
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Tappabuchi per l'aggiornamento a teams se l'interfaccia di amministrazione non è stata illuminata nel tenant
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 281938456c4fca695b2254e7cf6e50078bb32c80
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "36182125"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Aggiornamento degli utenti da Skype for business online a Microsoft Teams

> [!Note]
> I comandi descritti in questo articolo sono progettati per essere usati come parte dell'elenco di controllo di base per l' [aggiornamento](https://aka.ms/UpgradeBasic) .

Gli aspetti relativi alla migrazione tecnica dell'aggiornamento comportano la notifica agli utenti che Skype for business aggiornerà i team e li sposterà in modalità **solo teams** . Questa procedura può essere eseguita tramite una sessione remota di Windows PowerShell di Skype for business o tramite l'interfaccia di amministrazione di Microsoft teams.

Stiamo attivamente implementando gli strumenti di aggiornamento nell'interfaccia di [amministrazione di Microsoft teams](manage-teams-skypeforbusiness-admin-center.md), che dovrebbe essere presto disponibile nel tenant. Non appena è disponibile, è possibile trovare informazioni sulla migrazione degli utenti nell' [impostazione delle impostazioni di coesistenza e aggiornamento](https://aka.ms/SkypeToTeams-SetCoexistence).

Se si è pronti per l'aggiornamento oggi, è possibile usare i comandi di [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) elencati nella tabella seguente.

| Passaggio di base per l'aggiornamento # | Modalità | Comando di PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Isole + notifica all'utente Skype for business<br>(Usare questo comando se gli utenti sono attualmente in modalità **isole** (impostazione predefinita)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*ad esempio, $SipAddress =' TestUser@contoso.com ')*<br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [5](upgrade-basic.md#step-5) | Skype for business solo + avvisa l'utente di Skype for business <br>(Usare questo comando se gli utenti sono attualmente in modalità **solo Skype for business** ) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [7](upgrade-basic.md#step-7) | Solo Teams | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |
