---
title: Visite virtuali con Microsoft Teams e l'app Bookings
author: msdmaguire
ms.author: dmaguire
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Microsoft Teams e visite virtuali con l'app Bookings
ms.openlocfilehash: 582c59b4c389d687c529a7db9d9f1825d488f9f3
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125749"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Visite virtuali con Microsoft Teams e l'app Bookings

L'app Bookings in Microsoft Teams offre un modo semplice per pianificare appuntamenti di persona e virtuali, come visite mediche, consulenze finanziarie, colloqui, supporto clienti, orari di ufficio per l'istruzione e molto altro ancora.

Gli utilità di pianificazione possono gestire più calendari di reparto e del personale, nonché le comunicazioni con partecipanti interni ed esterni, da un'unica esperienza. Gli appuntamenti virtuali si svolgono tramite riunioni di Microsoft Teams, che offrono efficaci funzionalità di videoconferenza.

> [!NOTE]
> Solo gli utilità di pianificazione devono avere l'app Bookings installata in Teams. Il personale che partecipa ad appuntamenti virtuali non ha bisogno dell'app. Possono semplicemente partecipare agli appuntamenti dal calendario di Outlook o Teams o da un collegamento nel messaggio e-mail di conferma della prenotazione.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Prerequisiti per l'uso dell'app Bookings in Teams

- La cassetta postale di Exchange deve essere in Exchange Online. Le cassette postali Exchange Server locali non sono supportate.

- Microsoft Bookings deve essere attivato per l'organizzazione.

- Gli utenti devono avere una licenza appropriata. Sono supportati Office 365 A3, A5, E3 ed E5, oltre a Microsoft 365 Business Standard, A3, A5, E3 ed E5.

- Tutti gli utenti dell'app Bookings e tutto il personale che partecipano alle riunioni devono avere una licenza che supporta la pianificazione delle riunioni di Teams.

- I sistemi devono soddisfare tutti [i prerequisiti software e del browser.](hardware-requirements-for-the-teams-app.md)

## <a name="availability-of-bookings-in-teams"></a>Disponibilità di Bookings in Teams

L'app Microsoft Bookings per Teams è disponibile sul desktop e sul Web. È disponibile in App [all'interno di Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) e in **Gestisci app nell'interfaccia** di amministrazione di Teams.

### <a name="control-access-to-bookings-within-your-organization"></a>Controllare l'accesso a Bookings all'interno dell'organizzazione

Esistono diversi modi per controllare chi ha accesso all'app Bookings e a caratteristiche specifiche dell'app. Per informazioni su come attivare o disattivare Microsoft Bookings nell'interfaccia di amministrazione di Microsoft 365 e su come creare criteri dell'app Bookings per consentire a utenti selezionati di creare calendari di Bookings, vedere Ottenere l'accesso a [Microsoft Bookings.](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce) È anche possibile imparare a creare [criteri dell'app Teams per aggiungere l'app Bookings a utenti selezionati.](teams-app-setup-policies.md)

## <a name="recommended-meeting-policy-settings"></a>Impostazioni dei criteri riunione consigliate

Per consentire un'esperienza ottimale per Bookings, creare un criterio per le riunioni del personale in modo da ammettere automaticamente tutti **gli utenti dell'organizzazione.** In questo modo il personale può partecipare automaticamente all'appuntamento e consentire l'esperienza di attesa per i partecipanti esterni. Altre informazioni sull'ammissione automatica di persone alle riunioni sono [più dettagliate.](meeting-policies-in-teams.md#automatically-admit-people)

### <a name="optional-staff-approvals-setting"></a>Impostazione approvazione del personale facoltativa

Come impostazione di privacy aggiuntiva, è possibile scegliere di richiedere al personale di acconsentire esplicitamente prima che le informazioni sulla disponibilità della pianificazione siano condivise tramite Bookings e prima che possano essere prenotate per un appuntamento.  

Per abilitare questa impostazione, passare a Impostazioni dell'interfaccia di amministrazione di **Microsoft 365** \>  \> e quindi selezionare **Bookings.**

Quando questa impostazione è attivata, i membri del personale riceveranno un messaggio di posta elettronica in cui gli viene chiesto di approvare l'appartenenza a un calendario delle prenotazioni.  

Questa funzionalità verrà gradualmente implementazione in tutto il mondo ai clienti di Microsoft 365 e Office 365. Se tutte le opzioni non sono ancora disponibili nel proprio ambiente, tornare presto alla pagina.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Modifica del dominio predefinito quando si configurano cassette postali di Bookings

Quando si configura una cassetta postale di Bookings, viene usato il dominio di posta elettronica predefinito dell'organizzazione di Microsoft 365 o Office 365. Tuttavia, questo può causare problemi durante l'invio di inviti alle riunioni a destinatari esterni; l'invito potrebbe essere contrassegnato come posta indesiderata e spostato nella cartella Posta indesiderata del destinatario, in modo che il destinatario non veda mai l'invito.

È consigliabile modificare il dominio predefinito prima di creare la cassetta postale di Bookings. Per informazioni su come eseguire questa operazione, vedere le domande [frequenti sui domini.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)

Se è necessario cambiare il dominio predefinito dopo aver già creato la cassetta postale di Bookings, è possibile farlo con PowerShell:

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Per altre informazioni, vedere la documentazione di PowerShell per il cmdlet [Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)

> [!NOTE]
> Se si usa una configurazione ibrida di Exchange, è consigliabile testare approfonditamente il flusso di posta tra Exchange locale ed Exchange Online quando si modifica il dominio predefinito.

## <a name="sending-feedback"></a>Invio di feedback

Il feedback degli utenti è positivo per:

  - Esperienza utente o facilità d'uso
  - Lacune di funzionalità o funzionalità mancanti
  - Bug o problemi
  
Per inviare commenti  e suggerimenti, fare clic sul pulsante ? nella parte inferiore della barra di spostamento **sinistra** di Teams, quindi fare clic su Segnala un problema per **TUTTI i** problemi. Tenere presente all'inizio del report sul feedback che si sta inviando feedback su "Bookings" per poter identificare facilmente i problemi di Bookings.

## <a name="related-topics"></a>Argomenti correlati

[Documentazione di Bookings per gli utenti finali](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
