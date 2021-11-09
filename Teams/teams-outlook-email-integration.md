---
title: Teams e Outlook di posta elettronica
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni sulle funzionalità Teams e Outlook di integrazione della posta elettronica, incluse le funzionalità che consentono agli utenti di condividere informazioni tra la posta elettronica in Outlook e le conversazioni di chat o canali in Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6f41d26a2d87d1c95b99534a866f64cd9f30eb8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837458"
---
# <a name="teams-and-outlook-email-integration"></a>Teams e Outlook di posta elettronica

Microsoft Teams include funzionalità che consentono agli utenti dell'organizzazione di condividere facilmente informazioni tra posta elettronica in Outlook e conversazioni di chat o canali in Teams e di rimanere sempre al corrente delle conversazioni perse. Questo articolo offre una panoramica di queste caratteristiche e dei controlli di amministrazione applicabili.

## <a name="share-to-outlook"></a>Condividere con Outlook

**Condividi con Outlook** consente agli utenti di condividere una copia di una conversazione Teams a un messaggio di posta elettronica in Outlook, senza dover uscire Teams. Questa funzionalità è utile se gli utenti devono condividere conversazioni o aggiornamenti di stato con utenti esterni al team o persino all'organizzazione. Passare all'inizio della conversazione in Teams, selezionare ̇ ̇ ̇ **Altre** opzioni e quindi selezionare **Condividi per** Outlook .  Per altre informazioni, vedere [Condividere Outlook da Teams](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d).

![Screenshot che mostra la caratteristica Condividi in Outlook in Teams.](media/share-to-outlook.png)

Per usare questa funzionalità, Outlook sul web deve essere attivato per l'utente. Se Outlook sul web è disattivata,  l'opzione Condividi in Outlook non viene visualizzata in Teams per l'utente. Per la procedura per attivare e disattivare le Outlook sul web, vedere Abilitare o disabilitare Outlook sul web [per una cassetta postale.](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)

## <a name="actionable-activity-emails"></a>Messaggi di posta elettronica di attività utilizzabili

Gli utenti ottengono automaticamente messaggi di posta elettronica di attività perse che li aiutano a recuperare le conversazioni perse in Teams. I messaggi di posta elettronica delle attività perse mostrano le risposte più recenti di  una conversazione, inclusi i messaggi inviati dopo il messaggio perso, e gli utenti possono fare clic su Rispondi per rispondere direttamente dall'interno Outlook. Per altre informazioni, vedere [Rispondere ai messaggi di posta](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381)elettronica delle attività perse Outlook . 

> [!NOTE]
> Questa caratteristica non è supportata in Outlook per Mac o in alcune versioni precedenti di Outlook per Windows. Per altre informazioni, vedere [Messaggi utilizzabili in](/outlook/actionable-messages/)Outlook e Office 365 gruppi .

![Screenshot che mostra un messaggio di posta elettronica di un'attività persa.](media/missed-activity-email.png)

![Screenshot che mostra come rispondere a un messaggio di posta elettronica di un'attività persa.](media/missed-activity-email-reply.png)

È possibile usare il cmdlet [Set-OrganizationConfig](/powershell/module/exchange/organization/set-organizationconfig) insieme al parametro **SmtpActionableMessagesEnabled** per disattivare i messaggi di posta elettronica utilizzabili. Per impostazione predefinita, il **parametro SmtpActionableMessagesEnabled** è impostato su **true.** L'impostazione del parametro **su false disattiva** i messaggi di posta elettronica utilizzabili Office 365. Per Teams utenti, questo significa  che l'opzione Rispondi per rispondere direttamente Outlook non è disponibile nei messaggi di posta elettronica delle attività perse. I messaggi di posta elettronica delle attività perse includono invece un'opzione Rispondi **in** Teams per consentire agli utenti di rispondere in Teams.

Vedere anche [Messaggi utilizzabili in Outlook e Office 365 gruppi](/outlook/actionable-messages/).
