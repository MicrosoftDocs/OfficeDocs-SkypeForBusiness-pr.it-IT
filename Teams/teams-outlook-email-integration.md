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
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43435c436685c53e0ad077887a9fe9d991cf2d61
ms.sourcegitcommit: f5480d0ca34b3160980a4b46b5afa34271293a26
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/09/2022
ms.locfileid: "68899690"
---
# <a name="manage-actionable-activity-emails"></a>Gestire i messaggi di posta elettronica delle attività su cui è possibile eseguire azioni

I messaggi di posta elettronica sulle attività su cui è possibile intervenire sono abilitati per impostazione predefinita e notificano agli utenti dell'organizzazione le conversazioni perse in Microsoft Teams.

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
