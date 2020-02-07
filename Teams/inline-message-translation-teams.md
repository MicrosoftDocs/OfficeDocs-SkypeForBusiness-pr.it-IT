---
title: Attivare la traduzione del messaggio in linea in Microsoft Teams
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
description: Informazioni su come usare la traduzione in linea in Microsoft teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1926f574977f65181f12ddbb9f0239ad1547d1e5
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836636"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a>Attivare la traduzione del messaggio in linea in Microsoft Teams 
=================================================

La traduzione dei messaggi in linea è una nuova caratteristica di Microsoft teams che consente agli utenti di tradurre i messaggi di teams nella [lingua](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specificata dalle impostazioni della lingua personale per Office 365.

La traduzione dei messaggi in linea viene distribuita per impostazione predefinita per l'organizzazione. Se si vuole consentire agli utenti di usare questa funzionalità nel client teams, è necessario attivare questa impostazione.

> [!NOTE]
>Questa implementazione è esclusa dagli abbonamenti a Office 365 nei nostri ambienti Office 365 Government community Cloud e Office 365 Germany.

## <a name="use-powershell-to-turn-on-inline-message-translation"></a>Usare PowerShell per attivare la traduzione in linea del messaggio

È possibile usare i criteri di messaggistica per attivare la traduzione del messaggio inline.

Attivare i criteri usando il cmdlet [set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) . I criteri richiedono alcuni minuti per l'applicazione. Gli utenti potrebbero dover disconnettersi e accedere di nuovo a teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a>Usare l'interfaccia di amministrazione di Microsoft teams per attivare la traduzione dei messaggi in linea

Nell'interfaccia di **amministrazione di Microsoft teams**selezionare **criteri di messaggistica** dalla barra di spostamento sinistra, quindi creare un nuovo criterio o modificare un criterio esistente e impostare l'opzione **Consenti agli utenti di tradurre i messaggi** **su**attivato.

> [!NOTE]
> Il servizio esegue la traduzione e lo recapita al client senza alcun effetto sul contenuto acquisito nei record di conformità. Per ulteriori informazioni sulla traduzione, vedere [che cos'è Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).