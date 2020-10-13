---
title: App bookings e visite virtuali in Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
ms.reviewer: ''
description: Microsoft teams e visite virtuali con l'app bookings
ms.openlocfilehash: c60993b57233c0c526e1770c1d3d414a73fcc42a
ms.sourcegitcommit: a043bde507a9f6747fdd2063dd085edb3c1d6c3c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2020
ms.locfileid: "48427681"
---
# <a name="bookings-app-and-virtual-visits-in-microsoft-teams"></a>App bookings e visite virtuali in Microsoft Teams

L'app bookings in Microsoft teams offre un modo semplice per pianificare appuntamenti personali e virtuali, ad esempio visite sanitarie, consulenze finanziarie, interviste, assistenza clienti, ore di ufficio per l'istruzione e molto altro.

Le utilità di pianificazione possono gestire più calendari di reparto e personale, nonché le comunicazioni con i partecipanti interni ed esterni, da una singola esperienza. Gli appuntamenti virtuali si svolgono tramite riunioni di Microsoft teams, che offrono funzionalità di videoconferenza affidabili.

> [!NOTE]
> Solo gli utilità di pianificazione devono avere l'app bookings installata in teams. I membri del personale che effettuano o partecipano a appuntamenti virtuali non richiedono l'app. Possono semplicemente partecipare agli appuntamenti dal calendario di Outlook o di teams o da un collegamento nel messaggio di conferma della prenotazione.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Prerequisiti per l'uso dell'app bookings in teams

- La cassetta postale di Exchange deve essere in Exchange Online. Le cassette postali di Exchange Server locali non sono supportate.

- Le prenotazioni Microsoft devono essere attivate per l'organizzazione.

- Gli utenti devono avere una licenza appropriata. Sono supportati Office 365 a3, a5, E3 e E5, oltre a Microsoft 365 business standard, a3, a5, E3 e E5.

- Tutti gli utenti dell'app bookings e tutti i membri del personale che partecipano alle riunioni devono avere una licenza che supporti la pianificazione della riunione di teams.

- I sistemi devono soddisfare tutti i [prerequisiti del software e del browser](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilità delle prenotazioni in teams

L'app Microsoft bookings per Teams è disponibile sul desktop e sul Web. Può essere trovato in [app in Microsoft teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) e in **Manage Apps** in teams Admin Center.

### <a name="control-access-to-bookings-within-your-organization"></a>Controllare l'accesso alle prenotazioni all'interno dell'organizzazione

Esistono diversi modi per controllare chi ha accesso all'app bookings e a specifiche caratteristiche dell'app. Per informazioni su come attivare o disattivare le prenotazioni Microsoft nell'interfaccia di amministrazione di Microsoft 365, nonché su come creare un criterio per l'app bookings per consentire agli utenti selezionati di creare calendari delle prenotazioni, vedere [accedere alle prenotazioni Microsoft](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce). Puoi anche scoprire come [creare criteri per l'app teams per aggiungere l'app bookings per gli utenti selezionati](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Impostazioni consigliate per i criteri riunione

Per consentire l'esperienza ottimale per le prenotazioni, creare un criterio per la riunione del personale per ammettere automaticamente **tutti gli utenti dell'organizzazione**. In questo modo, il personale potrà partecipare automaticamente all'appuntamento e abilitare l'esperienza di lobby per i partecipanti esterni. Per altre informazioni, vedere l' [ammissione automatica delle persone alle riunioni](meeting-policies-in-teams.md#automatically-admit-people).

### <a name="optional-staff-approvals-setting"></a>Impostazione facoltativa degli approvazioni del personale

Come ulteriore impostazione per la privacy, puoi scegliere di richiedere al personale l'opt-in prima che le informazioni sulla disponibilità di programmazione vengano condivise tramite le prenotazioni e prima che possano essere prenotate per un appuntamento.  

Per abilitare questa impostazione, accedere alle impostazioni dell'interfaccia di **amministrazione di Microsoft 365** \> **Settings** \> **Settings**e quindi selezionare **prenotazioni**.

Con questa impostazione attivata, il personale riceverà un messaggio di posta elettronica in cui verrà richiesto di approvare l'appartenenza a un calendario di prenotazione.  

Questa caratteristica viene gradualmente distribuita in tutto il mondo a Microsoft 365 e ai clienti di Office 365. Se tutte le opzioni non sono ancora disponibili nell'ambiente, vedere presto.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Cambiare il dominio predefinito durante la configurazione delle cassette postali di prenotazione

Quando si configura una cassetta postale di prenotazione, viene usato il dominio di posta elettronica predefinito dell'organizzazione Microsoft 365 o Office 365. Tuttavia, questo problema può causare problemi durante l'invio di inviti alle riunioni a destinatari esterni; l'invito potrebbe essere contrassegnato come posta indesiderata e spostato nella cartella posta indesiderata del destinatario, in modo che il destinatario potrebbe non vedere mai l'invito.

È consigliabile modificare il dominio predefinito prima di creare la cassetta postale di prenotazione. Per informazioni su come eseguire questa operazione, vedere le [domande frequenti sui domini](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Se è necessario modificare il dominio predefinito dopo che la cassetta postale di prenotazione è già stata creata, è possibile farlo con PowerShell:

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Per altre informazioni, vedere la documentazione di PowerShell relativa al cmdlet [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) .

> [!NOTE]
> Se si usa una configurazione ibrida di Exchange, è consigliabile testare completamente il flusso di posta tra Exchange locale ed Exchange Online quando si cambia il dominio predefinito.

## <a name="sending-feedback"></a>Invio di commenti e suggerimenti

Accogliamo favorevolmente il feedback su:

  - Esperienza utente o facilità d'uso
  - Funzionalità gap o funzionalità mancanti
  - Bug o problemi
  
Per inviare commenti e suggerimenti, fare clic sul pulsante della **Guida** nella parte inferiore della barra di spostamento sinistra teams, quindi fare clic su **segnala un problema** per **tutti i** problemi. Tieni presente che all'inizio del tuo report di feedback stai inviando feedback su "prenotazioni" in modo da identificare facilmente i problemi di prenotazione.

## <a name="related-topics"></a>Argomenti correlati

[Documentazione delle prenotazioni per gli utenti finali](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
