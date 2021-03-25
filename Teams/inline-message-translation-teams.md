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
description: Informazioni su come attivare la traduzione in linea in Microsoft Teams usando l'interfaccia di amministrazione di Microsoft Teams o PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5c9e34c5e539d32b25259098973e9bfe6795ad7c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120627"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Disattivare la traduzione dei messaggi in linea in Microsoft Teams
=================================================

La traduzione dei messaggi in linea è una funzionalità di Microsoft Teams che consente agli utenti di tradurre i messaggi di Teams [nella](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) lingua specificata dalle impostazioni della lingua personale.

La traduzione dei messaggi in linea viene implementazione per impostazione predefinita per l'organizzazione. Non è necessario apportare modifiche se si vuole consentire agli utenti di usare questa funzionalità all'interno del client Teams.

> [!NOTE]
>Questa implementazione è esclusa dagli abbonamenti a Office 365 negli ambienti Office 365 Government Community Cloud e Office 365 Germany.

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>Usare PowerShell per disattivare la traduzione dei messaggi in linea

È possibile usare i criteri di messaggistica per disattivare la traduzione dei messaggi in linea.

Disattivare i criteri usando il cmdlet [Set-CsTeamsMessagingPolicy.](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) L'applicazione del criterio richiede alcuni minuti. Gli utenti potrebbero dover disconnettersi e accedere di nuovo a Teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Usare l'interfaccia di amministrazione di Microsoft Teams per disattivare la traduzione dei messaggi in linea

Nell'interfaccia **di amministrazione di Microsoft Teams** selezionare Criteri di messaggistica nel riquadro di spostamento  sinistro, quindi creare un nuovo criterio o modificare un criterio esistente e impostare l'opzione Traduci messaggi su **Disattivato.** 

> [!NOTE]
> Il servizio esegue la traduzione e la consegna al client senza alcun effetto sul contenuto acquisito nei record di conformità. Per altre informazioni sulla traduzione, vedere [Che cos'è Microsoft Translator?](/azure/cognitive-services/translator/translator-info-overview)