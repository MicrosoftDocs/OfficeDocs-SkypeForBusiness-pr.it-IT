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
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Aggiornamento degli utenti da Skype for Business online a Microsoft Teams

> [!Note]
> I comandi descritti in questo articolo sono progettati per essere usati nell'elenco di controllo [di base per l'aggiornamento.](https://aka.ms/UpgradeBasic)

Gli aspetti tecnici relativi alla migrazione implicano la notifica agli utenti che Skype for Business eserciterà l'aggiornamento a Teams e quindi li sposta in modalità **solo Teams.** Questa procedura può essere eseguita tramite una sessione di Windows PowerShell remota di Skype for Business o tramite l'interfaccia di amministrazione di Microsoft Teams.

Stiamo implementazione attiva degli strumenti di aggiornamento nell'interfaccia di amministrazione di [Microsoft Teams,](manage-teams-skypeforbusiness-admin-center.md)che dovrebbe essere disponibile a breve nel tuo tenant. Non appena è disponibile, è possibile trovare informazioni sulla migrazione degli utenti in Impostazione delle impostazioni di [coesistenza e aggiornamento.](https://aka.ms/SkypeToTeams-SetCoexistence)

Se si è pronti per eseguire l'aggiornamento, è possibile usare i [comandi di PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) elencati nella tabella seguente.

| Passaggio di base dell'aggiornamento # | Modalità | Comando di PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Isole + Notifica all'utente Skype for Business<br>Usare questo comando se gli utenti sono in **modalità** Isole (impostazione predefinita)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(ad esempio $ SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Solo Skype for Business + Notifica all'utente Skype for Business <br>(Utilizzare questo comando se gli utenti sono attualmente in **modalità solo Skype for Business)** | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Solo Teams | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
