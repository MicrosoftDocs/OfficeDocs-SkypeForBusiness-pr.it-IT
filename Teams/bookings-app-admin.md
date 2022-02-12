---
title: Gestire l'app Bookings in Microsoft Teams
author: dmaguire
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Informazioni su come gestire l'app Bookings in Teams per gli utenti dell'organizzazione.
ms.openlocfilehash: 147089c51ebc6d3e5eb6bf567579c9aa7fc5f2ce
ms.sourcegitcommit: 2e8daa3511cd198b3e0d43b153dd37a59cb21692
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2022
ms.locfileid: "62763730"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Gestire l'app Bookings in Microsoft Teams

L'app Bookings in Microsoft Teams offre un modo semplice per pianificare appuntamenti di persona e virtuali come visite mediche, consulenze finanziarie, colloqui, assistenza clienti, orario d’ufficio per l'istruzione e molto altro ancora. Per altre informazioni, vedere [Visite virtuali con Teams e l'app Bookings](expand-teams-across-your-org/bookings-virtual-visits.md).

Le utilità di pianificazione possono gestire più calendari di reparto e del personale, oltre a comunicazioni con partecipanti interni ed esterni, da un'unica esperienza. Gli appuntamenti virtuali stessi si svolgono tramite riunioni Microsoft Teams, che offre solide funzionalità di videoconferenza.

> [!NOTE]
> Solo le utilità di pianificazione devono avere l'app Bookings installata in Teams. Il personale che conduce o partecipa a appuntamenti virtuali non ha bisogno dell'app. Possono semplicemente partecipare agli appuntamenti dal calendario Outlook o Teams o dal collegamento Teams riunione nel messaggio di posta elettronica di conferma della prenotazione.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Prerequisiti per l'uso dell'app Bookings in Teams

- La cassetta postale di Exchange deve essere in Exchange Online. Le cassette postali Exchange Server locali non sono supportate.

- Microsoft Bookings deve essere attivato per l'organizzazione.

- Gli utenti devono avere una licenza appropriata. Office 365 A3, A5, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 e Business Standard sono supportati.

- Tutti gli utenti dell'app Bookings e tutti i membri del personale che partecipano alle riunioni devono avere una licenza che supporti Teams pianificazione delle riunioni.

- I sistemi devono soddisfare tutti i [prerequisiti per software e browser](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilità di Bookings in Teams

L'app Microsoft Bookings Teams è disponibile sul desktop e sul Web. È disponibile in App [in Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) e in **Gestisci app** nell'Teams di amministrazione.

### <a name="control-access-to-bookings-within-your-organization"></a>Controllare l'accesso a Bookings all'interno dell'organizzazione

Esistono diversi modi per controllare chi ha accesso all'app Bookings e a specifiche funzionalità dell'app.

Per informazioni su come attivare o disattivare Microsoft Bookings nel interfaccia di amministrazione di Microsoft 365 e su come creare criteri dell'app Bookings per consentire a utenti selezionati di creare calendari di Bookings, vedere Ottenere l'accesso a [Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).

È anche possibile [creare un criterio Teams di configurazione dell'app per aggiungere l'app Bookings per utenti selezionati](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Impostazioni dei criteri per le riunioni consigliate

Per abilitare l'esperienza ottimale per Bookings, creare un criterio Teams riunione per ammettere automaticamente tutti  gli utenti dell'organizzazione e assegnare il criterio al personale. In questo modo il personale può partecipare automaticamente all'appuntamento e abilitare l'esperienza di sala d'attesa per i partecipanti esterni. Altre informazioni su come ammettere [automaticamente le persone alle riunioni](meeting-policies-participants-and-guests.md#automatically-admit-people).

## <a name="optional-staff-approvals-setting"></a>Impostazione facoltativa delle approvazioni del personale

Come impostazione di privacy aggiuntiva, è possibile scegliere di richiedere al personale di acconsentire esplicitamente prima che le informazioni sulla disponibilità della pianificazione siano condivise tramite Bookings e prima che possano essere prenotati per un appuntamento.  

Per abilitare questa impostazione, passare interfaccia di amministrazione di Microsoft 365  \> **Impostazioni** \> **Impostazioni** e quindi selezionare **Prenotazioni**.

Con questa impostazione attivata, il personale riceverà un messaggio di posta elettronica in cui viene chiesto di approvare l'appartenenza a un calendario di prenotazione.  

Questa funzionalità verrà distribuita gradualmente in tutto il mondo per i clienti di Microsoft 365 e Office 365. Se tutte le opzioni non sono ancora disponibili nell'ambiente, tornare presto.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Modifica del dominio predefinito durante la configurazione delle cassette postali di Bookings

Quando si configura una cassetta postale di Bookings, viene usato il dominio di posta elettronica predefinito dell'organizzazione di Microsoft 365 o Office 365. Tuttavia, questo può causare problemi quando si inviano inviti alle riunioni a destinatari esterni; l'invito potrebbe essere contrassegnato come posta indesiderata e spostato nella cartella Posta indesiderata del destinatario, quindi il destinatario potrebbe non vederlo mai.

È consigliabile modificare il dominio predefinito prima di creare la cassetta postale di Bookings. Per informazioni su come eseguire questa operazione, vedere [Domande frequenti sui domini](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Se è necessario modificare il dominio predefinito dopo aver già creato la cassetta postale di Bookings, è possibile farlo con PowerShell:

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Per altre informazioni, vedere la documentazione di PowerShell per il cmdlet [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Se si usa una configurazione ibrida Exchange, è consigliabile testare a fondo il flusso di posta tra Exchange locale e Exchange Online quando si modifica il dominio predefinito.

## <a name="sending-feedback"></a>Invio di feedback

Invitiamo gli utenti a inviarci un feedback sugli argomenti seguenti:

  - Esperienza utente o facilità d'uso
  - Lacune delle funzionalità o funzionalità mancanti
  - Bug o problemi
  
Per inviare commenti e suggerimenti,  selezionare il pulsante ? nella parte inferiore Teams barra di spostamento sinistra e **quindi selezionare Segnala** un problema per **TUTTI i** problemi. Indicare all'inizio del report di feedback che si sta inviando un feedback su "Bookings" in modo da poter identificare facilmente i problemi relativi a Bookings.

## <a name="related-articles"></a>Articoli correlati

[Gestire l'esperienza di partecipazione Teams visite virtuali nei browser per dispositivi mobili](expand-teams-across-your-org/mobile-browser-join.md)


  [Documentazione di Bookings per gli utenti finali](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
