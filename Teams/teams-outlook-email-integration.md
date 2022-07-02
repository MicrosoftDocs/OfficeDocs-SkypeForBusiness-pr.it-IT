---
title: Integrazione della posta elettronica di Teams e Outlook
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni sulle funzionalità di integrazione della posta elettronica di Teams e Outlook, incluse le funzionalità che consentono agli utenti di condividere informazioni tra la posta elettronica in Outlook e le conversazioni tramite chat o canale in Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76a2ecf05a8769b51ffcb9827c0fe6ff75df7b18
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606235"
---
# <a name="teams-and-outlook-email-integration"></a>Integrazione della posta elettronica di Teams e Outlook

Microsoft Teams include funzionalità che consentono agli utenti dell'organizzazione di condividere facilmente informazioni tra la posta elettronica in Outlook e le conversazioni via chat o del canale in Teams e di tenere sotto controllo le conversazioni perse. Questo articolo offre una panoramica di queste caratteristiche e dei controlli di amministrazione applicabili.

## <a name="share-to-outlook"></a>Condividere in Outlook

**Condividi in Outlook** consente agli utenti di condividere una copia di una conversazione di Teams in un messaggio di posta elettronica in Outlook, senza dover uscire da Teams. Questa funzionalità è utile se gli utenti devono condividere conversazioni o aggiornamenti di stato con utenti esterni al team o persino all'organizzazione. Vai all'inizio della conversazione in Teams, seleziona **... Altre opzioni** e quindi selezionare **Condividi in Outlook**.  Per altre informazioni, vedere [Condividere in Outlook da Teams](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d).

![Screenshot che mostra la funzionalità Condividi in Outlook in Teams.](media/share-to-outlook.png)

Per usare questa funzionalità, Outlook sul web deve essere attivata per l'utente. Se Outlook sul web è disattivata, l'opzione **Condividi in Outlook** non viene visualizzata in Teams per l'utente. Per la procedura per attivare e disattivare Outlook sul web, vedere [Abilitare o disabilitare Outlook sul web per una cassetta postale](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app).

## <a name="actionable-activity-emails"></a>Messaggi di posta elettronica attività su cui è possibile eseguire azioni

Gli utenti ricevono automaticamente messaggi di posta elettronica sulle attività perse su cui è possibile eseguire azioni, che li aiutano a tenere sotto controllo le conversazioni perse in Teams. I messaggi di posta elettronica per le attività perse mostrano le risposte più recenti da una conversazione, inclusi i messaggi inviati dopo il messaggio perso e gli utenti possono fare clic su **Rispondi** per rispondere direttamente da Outlook. Per altre informazioni, vedere [Rispondere ai messaggi di posta elettronica per le attività perse da Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381). 

> [!NOTE]
> Questa funzionalità non è supportata in Outlook per Mac o in alcune versioni precedenti di Outlook per Windows. Per altre informazioni, vedere [Messaggi interattivi in Outlook e gruppi di Office 365](/outlook/actionable-messages/).

![Screenshot che mostra un messaggio e-mail di attività perse.](media/missed-activity-email.png)

![Screenshot che mostra come rispondere a un messaggio e-mail di attività persa.](media/missed-activity-email-reply.png)

È possibile usare il cmdlet [Set-OrganizationConfig](/powershell/module/exchange/organization/set-organizationconfig) insieme al parametro **SmtpActionableMessagesEnabled** per disattivare i messaggi di posta elettronica su cui è possibile eseguire azioni. Per impostazione predefinita, il parametro **SmtpActionableMessagesEnabled** è impostato su **true**. Se si imposta il parametro **su false**, i messaggi di posta elettronica su cui è possibile eseguire azioni vengono disattivati in Office 365. Per gli utenti di Teams, questo significa che l'opzione **Rispondi** per rispondere direttamente in Outlook non è disponibile nei messaggi di posta elettronica per le attività perse. Invece, i messaggi di posta elettronica per le attività perse includono un'opzione **Rispondi in Teams** per consentire agli utenti di rispondere in Teams.

Vedere anche [Messaggi interattivi in Outlook e gruppi di Office 365](/outlook/actionable-messages/).
