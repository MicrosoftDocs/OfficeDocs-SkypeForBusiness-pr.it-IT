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
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Aggiornamento degli utenti da Skype for Business Online a Microsoft Teams

> [!Note]
> I comandi descritti in questo articolo sono progettati per essere usati nell'elenco [di controllo Aggiornamento di base.](./upgrade-start-here.md)

Gli aspetti tecnici della migrazione dell'aggiornamento implicano la notifica agli utenti che Skype for Business esegue l'aggiornamento a Teams e quindi li sposta in modalità **Solo** Teams. Questa procedura può essere eseguita tramite una sessione di Windows PowerShell remota di Skype for Business o tramite l'interfaccia di amministrazione di Microsoft Teams.

Stiamo attivamente implementazione degli strumenti di aggiornamento nell'interfaccia di amministrazione di [Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)e dovrebbe essere disponibile a breve nel tenant. Non appena sarà disponibile, è possibile trovare informazioni sulla migrazione degli utenti in Impostazione [delle impostazioni di coesistenza e aggiornamento.](./setting-your-coexistence-and-upgrade-settings.md)

Se si è pronti per l'aggiornamento, è possibile usare i [comandi di PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) elencati nella tabella seguente.

| Passaggio di base dell'aggiornamento # | Modalità | Comando di PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Isole + Invia una notifica all'utente skype for business<br>Usare questo comando se gli utenti sono attualmente in **modalità** Isole (impostazione predefinita)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(ad esempio, $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Solo Skype for Business + Notifica all'utente Skype for Business <br>(Usa questo comando se gli utenti sono attualmente in **modalità Solo Skype for Business)** | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Solo Teams | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |