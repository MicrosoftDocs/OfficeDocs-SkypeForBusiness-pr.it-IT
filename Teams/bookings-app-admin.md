---
title: Visite virtuali con Microsoft Teams e l’app Bookings
author: cichur
ms.author: v-cichur
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
description: Microsoft Teams e visite virtuali con l’app Bookings
ms.openlocfilehash: 2ef4708cfcbdda5ba55c1aa7069e6e1e6babebc2
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "58233401"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Visite virtuali con Microsoft Teams e l’app Bookings

L'app Bookings in Microsoft Teams offre un modo semplice per pianificare appuntamenti di persona e virtuali come visite mediche, consulenze finanziarie, colloqui, assistenza clienti, orario d’ufficio per l'istruzione e molto altro ancora.

Le utilità di pianificazione possono gestire più calendari di reparto e del personale, oltre a comunicazioni con partecipanti interni ed esterni, da un'unica esperienza. Gli appuntamenti virtuali vengono tenuti tramite riunioni di Microsoft Teams, che offrono funzionalità efficaci di videoconferenza.

> [!NOTE]
> Solo le utilità di pianificazione devono avere l'app Bookings installata in Teams. Il personale che conduce o partecipa a appuntamenti virtuali non ha bisogno dell'app. Possono semplicemente partecipare agli appuntamenti dal calendario di Outlook o Teams o da un collegamento nel messaggio di conferma della prenotazione.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Prerequisiti per l'uso dell'app Bookings in Teams

- La cassetta postale di Exchange deve essere in Exchange Online. Le cassette postali di Exchange Server locale non sono supportate.

- Microsoft Bookings deve essere attivato per l'organizzazione.

- Gli utenti devono avere una licenza appropriata. Office 365 A3, A5, E3, E5, F1, F3, Microsoft 365 A3, A5, E3 ed E5, Business Standard sono supportati.

- Tutti gli utenti dell'app Bookings e tutto il personale che partecipa alle riunioni devono avere una licenza che supporti la pianificazione delle riunioni di Teams.

- I sistemi devono soddisfare tutti i [prerequisiti del software e del browser](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilità di Bookings in Teams

L'app Microsoft Bookings per Teams è disponibile sul desktop e sul Web. L'app si trova in [App all'interno di Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) e in **Gestisci app** all’interno dell'interfaccia di amministrazione di Teams.

### <a name="control-access-to-bookings-within-your-organization"></a>Controllare l'accesso a Bookings all'interno dell'organizzazione

Esistono diversi modi per controllare chi ha accesso all'app Bookings e a specifiche funzionalità dell'app. Per informazioni su come attivare o disattivare Microsoft Bookings nell'interfaccia di amministrazione di Microsoft 365 e su come creare criteri per l'app Bookings per consentire agli utenti selezionati di creare calendari di Bookings, vedere [Accedere a Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce). Vedere anche come [Creare criteri per l'app Teams per aggiungere l'app Bookings per utenti selezionati](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Impostazioni consigliate per i criteri di riunione

Per consentire l'esperienza migliore per Bookings, creare criteri di riunione del personale per ammettere automaticamente **Tutti gli utenti dell'organizzazione**. In questo modo il personale potrà partecipare automaticamente all'appuntamento e sarà possibile consentire l'esperienza di sala di attesa per i partecipanti esterni. Per altre informazioni, è possibile vedere come [ammettere automaticamente le persone alle riunioni](meeting-policies-participants-and-guests.md#automatically-admit-people).

### <a name="optional-staff-approvals-setting"></a>Impostazione facoltativa delle approvazioni del personale

Come impostazione di privacy aggiuntiva, è possibile scegliere di richiedere al personale di acconsentire esplicitamente prima che le informazioni sulla disponibilità della pianificazione siano condivise tramite Bookings e prima che possano essere prenotati per un appuntamento.  

Per abilitare questa impostazione, aprire **l'interfaccia di amministrazione di Microsoft 365** \> **Impostazioni** \> **Impostazioni**, quindi selezionare **Bookings**.

Quando questa impostazione è attivata, il personale riceverà un messaggio di posta elettronica in cui viene chiesto di approvare l'appartenenza a un calendario delle prenotazioni.  

Questa funzionalità verrà distribuita gradualmente in tutto il mondo per i clienti di Microsoft 365 e Office 365. Se nel proprio ambiente non sono ancora disponibili tutte le opzioni, ricontrollare più avanti.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Modifica del dominio predefinito durante la configurazione delle cassette postali di Bookings

Quando si configura una cassetta postale di Bookings, viene usato il dominio di posta elettronica predefinito dell'organizzazione di Microsoft 365 o Office 365. Tuttavia, questo può causare problemi quando si inviano inviti alle riunioni a destinatari esterni; l'invito potrebbe essere contrassegnato come posta indesiderata e spostato nella cartella Posta indesiderata del destinatario, quindi il destinatario potrebbe non vederlo mai.

È consigliabile modificare il dominio predefinito prima di creare la cassetta postale di Bookings. Per informazioni su come eseguire questa operazione, vedere [Domande frequenti sui domini](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Se è necessario modificare il dominio predefinito dopo aver già creato la cassetta postale di Bookings, è possibile farlo con PowerShell:

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Per altre informazioni, vedere la documentazione di PowerShell per il cmdlet [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Se si usa una configurazione ibrida di Exchange, è consigliabile testare accuratamente il flusso di posta tra Exchange locale ed Exchange Online quando si modifica il dominio predefinito.

## <a name="sending-feedback"></a>Invio di feedback

Invitiamo gli utenti a inviarci un feedback sugli argomenti seguenti:

  - Esperienza utente o facilità d'uso
  - Lacune delle funzionalità o funzionalità mancanti
  - Bug o problemi
  
Per inviare un feedback, fare clic sul pulsante **Guida** nella parte inferiore della barra di spostamento sinistra di Teams, quindi fare clic su **Segnala un problema** per **TUTTI** i problemi. Indicare all'inizio del report di feedback che si sta inviando un feedback su "Bookings" in modo da poter identificare facilmente i problemi relativi a Bookings.

## <a name="related-topics"></a>Argomenti correlati


  [Documentazione di Bookings per gli utenti finali](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)