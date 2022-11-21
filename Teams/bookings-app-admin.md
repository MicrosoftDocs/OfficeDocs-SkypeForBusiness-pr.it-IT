---
title: Gestire l'app Bookings in Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: how-to
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
- m365-frontline
- tier2
- highpri
ms.reviewer: ''
description: Informazioni su come gestire l'app Bookings in Teams per gli utenti dell'organizzazione.
ms.openlocfilehash: 4669b27efb351c375d5d5fd1104843e21c6f5ba9
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131305"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Gestire l'app Bookings in Microsoft Teams

L'app Bookings in Microsoft Teams offre un modo semplice per pianificare appuntamenti di persona e virtuali. Ad esempio, visite mediche, consulenze finanziarie, interviste, supporto tecnico e orari di ufficio per l'istruzione. Per altre informazioni, vedere [Appuntamenti virtuali con Teams e l'app Bookings](/microsoft-365/frontline/bookings-virtual-visits).

Gli scheduler possono gestire più calendari e comunicazioni di reparto e del personale con partecipanti interni ed esterni, da un'unica esperienza. Gli appuntamenti virtuali si svolgono tramite riunioni di Microsoft Teams che offrono solide funzionalità di videoconferenza.

> [!NOTE]
> Solo le utilità di pianificazione devono avere l'app Bookings installata in Teams. Il personale che conduce o partecipa agli appuntamenti virtuali non ha bisogno dell'app. Possono semplicemente partecipare agli appuntamenti dal calendario di Outlook o Teams o dal collegamento alla riunione di Teams nell'e-mail di conferma della prenotazione.

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>Prerequisiti per usare l'app Bookings in Teams

* La cassetta postale di Exchange si trova in Exchange Online. Le cassette postali Exchange Server locali non sono supportate.
* Microsoft Bookings è disponibile per l'organizzazione.
* Gli utenti hanno una licenza appropriata. sono supportati Office 365 A3, A5, E1, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 e Business Standard.
* Tutti gli utenti dell'app Bookings e tutto il personale che partecipa alle riunioni hanno una licenza che supporta la pianificazione delle riunioni di Teams.
* [Prerequisiti del software e del browser](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilità di Bookings in Teams

Microsoft Bookings app per Teams è disponibile sul desktop e sul Web. È disponibile in [App in Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) e in **Gestisci app** nell'interfaccia di amministrazione di Teams.

### <a name="control-access-to-bookings-within-your-organization"></a>Controllare l'accesso a Bookings all'interno dell'organizzazione

Esistono diversi modi per controllare chi ha accesso all'app Bookings e a specifiche funzionalità dell'app. Puoi rendere disponibile Microsoft Bookings'app o disabilitarla da interfaccia di amministrazione di Microsoft 365. In alternativa, è possibile creare un criterio dell'app Bookings per consentire a determinati utenti di creare calendari di Bookings. Vedere [Accedere a Microsoft Bookings](/microsoft-365/bookings/get-access).

È anche possibile [creare un criterio di configurazione dell'app Teams per aggiungere l'app Bookings per utenti selezionati](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Impostazioni dei criteri riunione consigliate

Per abilitare l'esperienza migliore per Bookings, creare un criterio riunione di Teams per ammettere automaticamente tutti gli utenti **dell'organizzazione** e assegnarlo al personale. Il criterio consente al personale di partecipare automaticamente all'appuntamento e di abilitare l'esperienza di sala di attesa per i partecipanti esterni. [Informazioni su come ammettere automaticamente le persone alle riunioni](meeting-policies-participants-and-guests.md#automatically-admit-people).

Per altre informazioni sui criteri delle riunioni, vedere [Gestire i criteri delle riunioni in Teams](meeting-policies-in-teams.md) e [Criteri di riunione e scadenza delle riunioni in Teams](meeting-expiration.md).

## <a name="optional-staff-approvals-setting"></a>Impostazione facoltativa delle approvazioni del personale

È possibile richiedere al personale di acconsentire esplicitamente prima che Bookings convida le informazioni sulla disponibilità della pianificazione e che altri utenti possano pianificare un appuntamento con loro.

Per abilitare questa impostazione,  vai a **Impostazioni interfaccia di amministrazione di Microsoft 365** \> \> e quindi seleziona **Bookings**.

Con questa impostazione attivata, il personale riceve un messaggio di posta elettronica in cui viene chiesto di approvare l'appartenenza a un calendario delle prenotazioni.  

Questa funzionalità verrà distribuita gradualmente in tutto il mondo per i clienti di Microsoft 365 e Office 365. Se tutte le opzioni non sono ancora disponibili nel tuo ambiente, ricontrollare a breve.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>Modifica del dominio predefinito durante la configurazione della cassetta postale di Bookings

Quando si configura una cassetta postale di Bookings, viene usato il dominio di posta elettronica predefinito dell'organizzazione di Microsoft 365 o Office 365. Tuttavia, il dominio predefinito può causare problemi durante l'invio di inviti alle riunioni a destinatari esterni. Ad esempio, l'invito potrebbe essere contrassegnato come posta indesiderata e spostato nella cartella Posta indesiderata del destinatario, in modo che il destinatario non veda mai l'invito.

È consigliabile modificare il dominio predefinito prima di creare la cassetta postale di Bookings. Vedere le [domande frequenti sui domini](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-microsoft-365).

Se è necessario cambiare il dominio predefinito dopo aver creato la cassetta postale di Bookings, usare PowerShell.

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Vedere la documentazione di PowerShell per impostare il cmdlet [della cassetta postale](/powershell/module/exchange/mailboxes/set-mailbox) .

> [!NOTE]
> Se si usa una configurazione ibrida di Exchange, è consigliabile testare accuratamente il flusso di posta tra Exchange locale e Exchange Online quando si modifica il dominio predefinito.

## <a name="send-feedback"></a>Invia feedback

Invitiamo gli utenti a inviarci un feedback sugli argomenti seguenti:

* Esperienza utente o facilità d'uso
* Lacune delle funzionalità o funzionalità mancanti
* Bug o problemi
  
Per inviare feedback, selezionare l'opzione **Guida** nella parte inferiore della barra di spostamento sinistra di Teams, quindi selezionare **Segnala un problema** per **TUTTI i** problemi. All'inizio del report di feedback è indicato che si sta inviando un feedback su "Bookings", in modo da poter identificare facilmente i problemi di Bookings.

## <a name="related-articles"></a>Articoli correlati

[Gestire l'esperienza di partecipazione per gli appuntamenti virtuali di Teams nei browser](/microsoft-365/frontline/browser-join)


  [Documentazione di Bookings per gli utenti finali](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
