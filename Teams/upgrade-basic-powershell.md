---
title: PowerShell per l'aggiornamento di base| Microsoft Teams| Concedi criteri di interoperabilità per l'aggiornamento
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni su un stopgap per l'aggiornamento a Microsoft Teams se il Centro Amministrazione non si è acceso nel tenant.
ms.localizationpriority: medium
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
ms.openlocfilehash: 02ba32e5b498639e93bc10757c51429871f5683a
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606035"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Aggiornamento degli utenti da Skype for Business Online a Microsoft Teams

> [!Note]
> I comandi descritti in questo articolo sono progettati per essere usati come parte dell'elenco di controllo [Di base per l'aggiornamento](./upgrade-start-here.md) .

Gli aspetti tecnici della migrazione dell'aggiornamento implicano la notifica agli utenti che Skype for Business verrà aggiornato a Teams e quindi li sposterà in una modalità **solo teams**. Questi passaggi possono essere eseguiti tramite una sessione di Windows PowerShell remota Skype for Business o tramite l'interfaccia di amministrazione di Microsoft Teams.

Stiamo distribuendo attivamente gli strumenti di aggiornamento [nell'interfaccia di amministrazione di Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md) e dovrebbero essere disponibili a breve nel tuo tenant. Non appena è disponibile, è possibile trovare informazioni sulla migrazione degli utenti in [Impostazione delle impostazioni di coesistenza e aggiornamento](./setting-your-coexistence-and-upgrade-settings.md).

Se si è pronti per l'aggiornamento oggi stesso, è possibile usare i comandi di [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) elencati nella tabella seguente.

| Passaggio di base sull'aggiornamento # | Modalità | Comando di PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islands + Notify the Skype for Business User<br>Usare questo comando se gli utenti sono attualmente in modalità **Isole** (impostazione predefinita)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(ad esempio$ SipAddress='TestUser@contoso.com)* |
| [5](upgrade-basic.md#step-5) | Skype for Business Only + Notify the Skype for Business User <br>Usare questo comando se gli utenti sono attualmente in modalità **solo Skype for Business**. | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Solo teams | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |