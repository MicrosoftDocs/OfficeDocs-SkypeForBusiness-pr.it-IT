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
ms.openlocfilehash: bd4c3cab1795ffcffe1cfd3ed1229f19e3ec80a243497ab13790e009878f9f35
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300752"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Aggiornamento degli utenti da Skype for Business Online a Microsoft Teams

> [!Note]
> I comandi descritti in questo articolo sono progettati per essere usati nell'elenco [di controllo Aggiornamento di base.](./upgrade-start-here.md)

Gli aspetti tecnici della migrazione dell'aggiornamento implicano la notifica agli utenti che Skype for Business verrà eseguito l'aggiornamento a Teams e quindi spostarli in una modalità **Teams solo** versione. Questa procedura può essere eseguita tramite una sessione Skype for Business remota Windows PowerShell o tramite l'Microsoft Teams di amministrazione.

Stiamo attivamente implementazione degli strumenti [](manage-teams-skypeforbusiness-admin-center.md)di aggiornamento nell'interfaccia di amministrazione Microsoft Teams e dovrebbe essere disponibile a breve nel tenant. Non appena sarà disponibile, è possibile trovare informazioni sulla migrazione degli utenti in Impostazione [delle impostazioni di coesistenza e aggiornamento.](./setting-your-coexistence-and-upgrade-settings.md)

Se si è pronti per l'aggiornamento, è possibile usare i [comandi di PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) elencati nella tabella seguente.

| Passaggio di base dell'aggiornamento # | Modalità | Comando di PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Isole + Notifica all'Skype for Business utente<br>Usare questo comando se gli utenti sono attualmente in **modalità** Isole (impostazione predefinita)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(ad esempio, $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Skype for Business Solo + Notifica all'Skype for Business utente <br>Usare questo comando se gli utenti sono attualmente in **Skype for Business modalità Solo** utenti) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Teams Solo | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |