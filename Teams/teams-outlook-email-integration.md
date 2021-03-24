---
title: Integrazione di Teams e posta elettronica di Outlook
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Informazioni sulle funzionalità di integrazione della posta elettronica di Teams e Outlook, incluse le funzionalità che consentono agli utenti di condividere informazioni tra la posta elettronica in Outlook e le conversazioni di chat o canali in Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3bfab6643d478537b3f9d2b7e4fa990b75511582
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104052"
---
# <a name="teams-and-outlook-email-integration"></a>Integrazione di Teams e posta elettronica di Outlook

Microsoft Teams include funzionalità che consentono agli utenti dell'organizzazione di condividere facilmente informazioni tra posta elettronica in Outlook e conversazioni in chat o canali in Teams e di rimanere sempre al corrente delle conversazioni perse. Questo articolo offre una panoramica di queste caratteristiche e dei controlli di amministrazione applicabili.

## <a name="share-to-outlook"></a>Condividere con Outlook

**Condividi con Outlook consente** agli utenti di condividere una copia di una conversazione di Teams con un messaggio di posta elettronica in Outlook, senza dover uscire da Teams. Questa funzionalità è utile se gli utenti devono condividere conversazioni o aggiornamenti di stato con utenti esterni al team o persino all'organizzazione. Passare all'inizio della conversazione in Teams, selezionare ̇ ̇ ̇ **Altre** opzioni e quindi **selezionare Condividi in Outlook.**  Per altre informazioni, vedere [Condividere con Outlook da Teams](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d).

![Screenshot che mostra la caratteristica Condividi in Outlook in Teams](media/share-to-outlook.png)

Per usare questa caratteristica, è necessario che Outlook sul Web sia attivato per l'utente. Se Outlook sul Web è disattivato, l'opzione Condividi in **Outlook** non viene visualizzata in Teams per l'utente. Per informazioni su come attivare e disattivare Outlook sul Web, vedere Abilitare o disabilitare [Outlook sul Web per una cassetta postale.](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)

## <a name="actionable-activity-emails"></a>Messaggi di posta elettronica di attività utilizzabili

Gli utenti ottengono automaticamente messaggi di posta elettronica di attività perse che li aiutano a recuperare le conversazioni perse in Teams. I messaggi di posta elettronica delle attività perse mostrano le risposte più recenti di  una conversazione, inclusi i messaggi inviati dopo il messaggio perso, e gli utenti possono fare clic su Rispondi per rispondere direttamente da Outlook. Per altre informazioni, vedere Rispondere ai messaggi di posta elettronica [delle attività perse da Outlook.](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381) 

> [!NOTE]
> Questa caratteristica non è supportata in Outlook per Mac o in alcune versioni precedenti di Outlook per Windows. Per altre informazioni, vedere Messaggi utilizzabili in Outlook e gruppi di [Office 365.](/outlook/actionable-messages/)

![Screenshot che mostra un messaggio di posta elettronica di un'attività persa](media/missed-activity-email.png)

![Screenshot che mostra come rispondere a un messaggio di posta elettronica di un'attività persa](media/missed-activity-email-reply.png)

È possibile usare il cmdlet [Set-OrganizationConfig](/powershell/module/exchange/organization/set-organizationconfig) insieme al parametro **SmtpActionableMessagesEnabled** per disattivare i messaggi di posta elettronica utilizzabili. Per impostazione predefinita, il **parametro SmtpActionableMessagesEnabled** è impostato su **true.** L'impostazione del parametro **su false disattiva** i messaggi di posta elettronica utilizzabili in Office 365. Per gli utenti di  Teams, questo significa che l'opzione Rispondi per rispondere direttamente in Outlook non è disponibile nei messaggi di posta elettronica delle attività perse. I messaggi di posta elettronica delle attività perse includono invece un'opzione Rispondi **in Teams** per consentire agli utenti di rispondere in Teams.