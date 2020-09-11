---
title: Integrazione della posta elettronica in teams e Outlook
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Informazioni sui team e sulle caratteristiche di integrazione della posta elettronica di Outlook, incluse le caratteristiche che consentono agli utenti di condividere le comunicazioni tra i messaggi di posta elettronica in Outlook e chat o canali in teams
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 675834cd36c4e86d34d179e91fe66905e3860b32
ms.sourcegitcommit: 0ad2fb145496210b728034d291a456b4caabdbf9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429442"
---
# <a name="teams-and-outlook-email-integration"></a>Integrazione della posta elettronica in teams e Outlook

Microsoft teams include caratteristiche che consentono agli utenti dell'organizzazione di condividere informazioni tra i messaggi di posta elettronica in Outlook e le conversazioni tramite chat o canali in teams e di rimanere in primo piano sulle conversazioni perse. Questo articolo offre una panoramica di queste funzionalità e dei controlli di amministratore applicabili.

## <a name="share-to-outlook"></a>Condivisione in Outlook

**Condivisione in Outlook** consente agli utenti di condividere una copia di una conversazione di teams in un messaggio di posta elettronica in Outlook senza dover abbandonare teams. Questa funzionalità è utile se gli utenti devono condividere le conversazioni o gli aggiornamenti di stato con utenti esterni al team immediato o anche all'organizzazione. Spostarsi all'inizio della conversazione in teams, selezionare **˙ ˙ ˙ altre opzioni**e quindi scegliere **Condividi in Outlook**.  Per altre informazioni, vedere [condividere in Outlook da teams](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d).

![Schermata che mostra la funzionalità Condividi in Outlook in teams](media/share-to-outlook.png)

Per usare questa caratteristica, Outlook sul Web deve essere attivato per l'utente. Se Outlook sul Web è disattivato, l'opzione **Condividi in Outlook** non viene visualizzata in teams per l'utente. Per istruzioni su come attivare e disattivare Outlook sul Web, vedere [abilitare o disabilitare Outlook sul Web per una cassetta postale](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app).

## <a name="actionable-activity-emails"></a>Messaggi di posta elettronica attivi

Gli utenti ottengono automaticamente i messaggi di posta elettronica che possono essere manomessi, aiutandoli a raggiungere conversazioni perse in teams. I messaggi di posta elettronica per le attività perse mostrano le risposte più recenti da una conversazione, inclusi quelli inviati dopo il messaggio mancante e gli utenti possono fare clic su **Rispondi** per rispondere direttamente da Outlook. Per altre informazioni, vedere [rispondere ai messaggi di posta elettronica di attività perse da Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381). 

> [!NOTE]
> Questa funzionalità non è supportata in Outlook per Mac o in alcune versioni precedenti di Outlook per Windows. Per altre informazioni, vedere [messaggi con azione in Outlook e gruppi di Office 365](https://docs.microsoft.com/outlook/actionable-messages/).

![Screenshot che mostra un messaggio di posta elettronica con attività perse](media/missed-activity-email.png)

![Screenshot che Mostra come rispondere a un messaggio di posta elettronica con attività perse](media/missed-activity-email-reply.png)

Puoi usare il cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) insieme al parametro **SmtpActionableMessagesEnabled** per disattivare i messaggi di posta elettronica con azione. Per impostazione predefinita, il parametro **SmtpActionableMessagesEnabled** è impostato su **true**. Se si imposta il parametro su **false** , i messaggi di posta elettronica di Office 365 vengono disattivati. Per gli utenti di teams, ciò significa che l'opzione **Rispondi** per rispondere direttamente in Outlook non è disponibile nei messaggi di posta elettronica di attività perse. I messaggi di posta elettronica attività mancanti includono invece un'opzione **Rispondi in teams** per consentire agli utenti di rispondere in teams.
