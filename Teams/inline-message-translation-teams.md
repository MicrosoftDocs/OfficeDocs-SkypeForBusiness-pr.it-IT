---
title: Attivare la traduzione dei messaggi in linea con il testo
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
description: Informazioni su come attivare la traduzione in linea in Microsoft Teams tramite l'interfaccia di amministrazione di Microsoft Teams o PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 012f2431ec7fb249a2f2e3b963c41166c4649a5c
ms.sourcegitcommit: 2e6b0930645cd97dbd597e9346a6fe1788c6facf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2020
ms.locfileid: "47395385"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Disattivare la traduzione dei messaggi in linea in Microsoft Teams
=================================================

La traduzione dei messaggi all'interno del testo è una funzionalità di Microsoft Teams che consente agli utenti di tradurre i messaggi di Teams nella lingua [specificata](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) dalle impostazioni personali della lingua.

Per impostazione predefinita, la traduzione dei messaggi all'interno del testo viene implementazione per l'organizzazione. Non è necessario apportare modifiche se si vuole consentire agli utenti di usare questa funzionalità all'interno del client di Teams.

> [!NOTE]
>Questa implementazione è esclusa dagli abbonamenti a Office 365 negli ambienti Office 365 Government Community Cloud e Office 365 Germany.

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>Usare PowerShell per disattivare la traduzione dei messaggi in linea

È possibile usare i criteri di messaggistica per disattivare la traduzione dei messaggi in linea.

Disattivare il criterio usando il cmdlet [Set-CsTeamsMessagingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) L'applicazione del criterio richiede alcuni minuti. Gli utenti potrebbero dover disconnettersi e accedere di nuovo a Teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Usare l'interfaccia di amministrazione di Microsoft Teams per disattivare la traduzione dei messaggi in linea

Nell'interfaccia di amministrazione  di **Microsoft Teams** selezionare Criteri di messaggistica nel riquadro di spostamento  sinistro, quindi creare un nuovo criterio o modificare un criterio esistente e impostare l'opzione Traduci messaggi su **Disattivato.**

> [!NOTE]
> Il servizio esegue la traduzione e la recapita al client senza alcun effetto sul contenuto acquisito nei record di conformità. Per altre informazioni sulla traduzione, vedere [Cos'è Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)
