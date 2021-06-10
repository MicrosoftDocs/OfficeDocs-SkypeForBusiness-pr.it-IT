---
title: Attivare la traduzione dei messaggi in linea
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
description: Informazioni su come attivare la traduzione in linea in Microsoft Teams l'Microsoft Teams di amministrazione o PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78282b464dd1d9cb25c5d4d2b338c74a2c91d374
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855925"
---
# <a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Disattivare la traduzione dei messaggi in linea in Microsoft Teams

La traduzione dei messaggi in linea è una Microsoft Teams che [](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) consente agli utenti di tradurre Teams messaggi nella lingua specificata dalle impostazioni della lingua personale.

La traduzione dei messaggi in linea viene implementazione per impostazione predefinita per l'organizzazione. Non è necessario apportare modifiche se si vuole consentire agli utenti di usare questa caratteristica all'interno del client Teams client.

> [!NOTE]
>Questa implementazione è esclusa dagli abbonamenti Office 365 negli ambienti Office 365 Government Community Cloud e Office 365 Germania.

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>Usare PowerShell per disattivare la traduzione dei messaggi in linea

È possibile usare i criteri di messaggistica per disattivare la traduzione dei messaggi in linea.

Disattivare i criteri usando il cmdlet [Set-CsTeamsMessagingPolicy.](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) L'applicazione del criterio richiede alcuni minuti. Gli utenti potrebbero dover disconnettersi e accedere di nuovo a Teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Usare l'Microsoft Teams di amministrazione per disattivare la traduzione dei messaggi in linea

Nell'interfaccia di amministrazione di  **Microsoft Teams** selezionare Criteri di messaggistica nel riquadro di spostamento sinistro,  quindi creare un nuovo criterio o modificare un criterio esistente e impostare l'opzione Traduci messaggi su **Disattivato.**

> [!NOTE]
> Il servizio esegue la traduzione e la consegna al client senza alcun effetto sul contenuto acquisito nei record di conformità. Per altre informazioni sulla traduzione, vedere [Che cos'è Microsoft Translator?](/azure/cognitive-services/translator/translator-info-overview)