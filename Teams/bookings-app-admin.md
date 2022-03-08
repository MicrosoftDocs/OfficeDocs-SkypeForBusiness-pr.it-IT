---
title: Gestire l'app Bookings in Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
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
ms.openlocfilehash: 3032704fe935f1d4d316741400e8a4b5841f8685
ms.sourcegitcommit: de6eb0478a79e178c5d02cdab8cca44a88beb853
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/07/2022
ms.locfileid: "63070585"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Gestire l'app Bookings in Microsoft Teams

L'app Bookings in Microsoft Teams offre un modo semplice per pianificare appuntamenti di persona e virtuali. Ad esempio, visite sanitarie, consulenze finanziarie, colloqui, assistenza clienti e ore di ufficio per l'istruzione. Per altre informazioni, vedere [Visite virtuali con Teams e l'app Bookings](expand-teams-across-your-org/bookings-virtual-visits.md).

Gli utilità di pianificazione possono gestire più calendari del reparto e del personale e le comunicazioni con i partecipanti interni ed esterni, da un'unica esperienza. Gli appuntamenti virtuali si svolgono tramite riunioni Microsoft Teams che offrono solide funzionalità di videoconferenza.

> [!NOTE]
> Solo le utilità di pianificazione devono avere l'app Bookings installata in Teams. Il personale che conduce o partecipa a appuntamenti virtuali non ha bisogno dell'app. Possono semplicemente partecipare agli appuntamenti dal calendario Outlook o Teams o dal collegamento Teams riunione nel messaggio di posta elettronica di conferma della prenotazione.

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>Prerequisiti per l'uso dell'app Bookings in Teams

* La Exchange cassetta postale è in Exchange Online. Le cassette postali Exchange Server locali non sono supportate.
* Microsoft Bookings è disponibile per l'organizzazione.
* Gli utenti hanno una licenza appropriata. Office 365 A3, A5, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 e Business Standard sono supportati.
* Tutti gli utenti dell'app Bookings e tutto il personale che partecipa alle riunioni hanno una licenza che supporta Teams pianificazione delle riunioni.
* [Prerequisiti software e del browser](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilità di Bookings in Teams

L'app Microsoft Bookings per Teams è disponibile sul desktop e sul Web. È disponibile in [App in Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) e in **Gestisci app** nell'Teams di amministrazione.

### <a name="control-access-to-bookings-within-your-organization"></a>Controllare l'accesso a Bookings all'interno dell'organizzazione

Esistono diversi modi per controllare chi ha accesso all'app Bookings e a specifiche funzionalità dell'app. È possibile rendere disponibile l'app Microsoft Bookings o disabilitarla interfaccia di amministrazione di Microsoft 365. In alternativa, è possibile creare un criterio dell'app Bookings per consentire a utenti selezionati di creare calendari di Bookings. Vedere [Ottenere l'accesso a Microsoft Bookings](/microsoft-365/bookings/get-access).

È anche possibile [creare un criterio Teams di configurazione dell'app per aggiungere l'app Bookings per utenti selezionati](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Impostazioni dei criteri per le riunioni consigliate

Per abilitare l'esperienza migliore per Bookings, creare un criterio Teams riunione per ammettere automaticamente tutti  gli utenti dell'organizzazione e assegnare il criterio al personale. Il criterio consente al personale di partecipare automaticamente all'appuntamento e di abilitare l'esperienza di attesa per i partecipanti esterni. Scopri [come ammettere automaticamente le persone alle riunioni](meeting-policies-participants-and-guests.md#automatically-admit-people).

## <a name="optional-staff-approvals-setting"></a>Impostazione facoltativa delle approvazioni del personale

È possibile richiedere al personale di acconsentire esplicitamente prima che Bookings condiva le informazioni sulla disponibilità della pianificazione e prima che altri utenti possano pianificare un appuntamento con loro.

Per abilitare questa impostazione, passare a **interfaccia di amministrazione di Microsoft 365** \> **Impostazioni** \> **Impostazioni** e quindi selezionare **Prenotazioni**.

Con questa impostazione attivata, il personale riceve un messaggio di posta elettronica in cui viene richiesto di approvare l'appartenenza a un calendario di prenotazione.  

Questa funzionalità verrà distribuita gradualmente in tutto il mondo per i clienti di Microsoft 365 e Office 365. Se tutte le opzioni non sono ancora disponibili nell'ambiente, tornare presto.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>Modifica del dominio predefinito durante la configurazione della cassetta postale di Bookings

Quando si configura una cassetta postale di Bookings, viene usato il dominio di posta elettronica predefinito dell'organizzazione di Microsoft 365 o Office 365. Tuttavia, il dominio predefinito può causare problemi durante l'invio di inviti a riunioni a destinatari esterni. Ad esempio, l'invito potrebbe essere contrassegnato come posta indesiderata e spostato nella cartella Posta indesiderata del destinatario, quindi il destinatario potrebbe non vedere mai l'invito.

È consigliabile modificare il dominio predefinito prima di creare la cassetta postale di Bookings. Vedere le [domande frequenti sui domini](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Se è necessario modificare il dominio predefinito dopo aver creato la cassetta postale di Bookings, usare PowerShell.

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Vedere la documentazione di PowerShell per [il cmdlet Set Mailbox](/powershell/module/exchange/mailboxes/set-mailbox) .

> [!NOTE]
> Se si usa una configurazione ibrida Exchange, è consigliabile testare a fondo il flusso di posta tra Exchange e Exchange Online locale quando si modifica il dominio predefinito.

## <a name="send-feedback"></a>Inviare feedback

Invitiamo gli utenti a inviarci un feedback sugli argomenti seguenti:

* Esperienza utente o facilità d'uso
* Lacune delle funzionalità o funzionalità mancanti
* Bug o problemi
  
Per inviare commenti e suggerimenti,  selezionare l'opzione Guida nella parte inferiore Teams barra di spostamento sinistra e **quindi selezionare Segnala** un problema per **TUTTI i** problemi. Indicare all'inizio del report di feedback che si sta inviando un feedback su "Bookings" in modo da poter identificare facilmente i problemi relativi a Bookings.

## <a name="related-articles"></a>Articoli correlati

[Gestire l'esperienza di partecipazione Teams visite virtuali nei browser per dispositivi mobili](expand-teams-across-your-org/mobile-browser-join.md)


  [Documentazione di Bookings per gli utenti finali](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
