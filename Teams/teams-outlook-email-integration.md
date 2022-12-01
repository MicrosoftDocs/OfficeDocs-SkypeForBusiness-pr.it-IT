---
title: Gestire i messaggi di posta elettronica delle attività su cui è possibile eseguire azioni
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come abilitare e disabilitare le e-mail di attività su cui è possibile eseguire azioni delle conversazioni di Microsoft Teams
ms.collection:
- M365-collaboration
ms.custom: chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: de1bd12a0f079154a37156e3a01c3e5791bef10c
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198508"
---
# <a name="manage-actionable-activity-emails"></a>Gestire i messaggi di posta elettronica delle attività su cui è possibile eseguire azioni

I messaggi di posta elettronica sulle attività su cui è possibile eseguire azioni sono abilitati per impostazione predefinita e notificano agli utenti dell'organizzazione le conversazioni perse su Microsoft Teams.

Un messaggio e-mail di attività persa mostra le risposte più recenti a una conversazione, inclusi i messaggi inviati dopo il messaggio perso. Questa caratteristica consente agli utenti di rispondere direttamente da Outlook selezionando **Rispondi**.

## <a name="disable-actionability-in-missed-activity-emails"></a>Disabilitare l'azionebilità nei messaggi di posta elettronica per le attività perse

Anche se questa funzionalità è impostata per l'abilitazione per impostazione predefinita, è possibile disattivare l'azionebilità nei messaggi di posta elettronica delle attività all'interno dell'organizzazione eseguendo il comando seguente:

```Powershell
Set-OrganizationConfig -SmtpActionableMessagesEnabled $false
```

Una volta disabilitata la funzionalità, l'opzione **Rispondi** viene sostituita da **Rispondi in Teams** , rendendo i messaggi di posta elettronica delle attività perse non più considerati interattivi. Gli utenti non potranno più rispondere direttamente da Outlook e vengono indirizzati per continuare la conversazione su Teams.

> [!NOTE]
> Questa funzionalità non è supportata in Outlook per Mac o in alcune versioni precedenti di Outlook per Windows. Per altre informazioni, vedere [Messaggi interattivi in Outlook e gruppi di Office 365](/outlook/actionable-messages/).

## <a name="related-topics"></a>Argomenti correlati

[Rispondere ai messaggi di posta elettronica sulle attività perse da Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381).

[Messaggi interattivi in Outlook e gruppi di Office 365](/outlook/actionable-messages/).
