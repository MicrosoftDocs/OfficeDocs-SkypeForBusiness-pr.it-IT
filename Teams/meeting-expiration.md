---
title: Criteri delle riunioni e scadenza delle riunioni in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Informazioni su come usare le impostazioni dei criteri riunione per controllare la scadenza della riunione in Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 1685da93c90d8d12cc4e8b8f2a92fd4f93391c87
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115564"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Criteri delle riunioni e scadenza delle riunioni in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Panoramica

[I criteri riunione](meeting-policies-in-teams.md) in Microsoft Teams vengono usati per controllare se gli utenti dell'organizzazione possono avviare e pianificare riunioni e le funzionalità disponibili per i partecipanti alle riunioni pianificate dagli utenti. È possibile usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati. È possibile gestire i criteri riunione nell'interfaccia di amministrazione di Microsoft Teams o usando i cmdlet di PowerShell [Get](/powershell/module/skype/get-csteamsmeetingpolicy), [New](/powershell/module/skype/new-csteamsmeetingpolicy), [Set](/powershell/module/skype/set-csteamsmeetingpolicy), [Remove](/powershell/module/skype/remove-csteamsmeetingpolicy), [Grant](/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy.

Le impostazioni dei criteri di riunione che controllano se gli utenti possono avviare e pianificare riunioni controllano anche la scadenza delle riunioni pianificate dagli utenti. Quando un collegamento di partecipazione alla riunione e l'ID conferenza per una riunione scadono, nessuno può partecipare alla riunione. Le impostazioni dei criteri per le riunioni seguenti determinano se gli utenti possono avviare e pianificare riunioni in Teams, a cui si fa riferimento in questo articolo.

- [Consenti riunione ora nei canali:](meeting-policies-in-teams.md#allow-meet-now-in-channels)controlla se un utente può avviare una riunione improvvisata in un canale.
- [Consenti pianificazione riunione canale:](meeting-policies-in-teams.md#allow-channel-meeting-scheduling)controlla se un utente può pianificare una riunione in un canale.
- [Consenti pianificazione riunioni private:](meeting-policies-in-teams.md#allow-scheduling-private-meetings)controlla se un utente può pianificare una riunione privata in Teams. Una riunione è privata quando non viene pubblicata in un canale in un team.
- [Consenti l'aggiunta di Outlook:](meeting-policies-in-teams.md#allow-the-outlook-add-in)controlla se un utente può pianificare una riunione privata da Outlook. Una riunione è privata quando non viene pubblicata in un canale in un team.
- [Consenti riunione ora in riunioni private:](meeting-policies-in-teams.md#allow-meet-now-in-private-meetings)controlla se un utente può avviare una riunione privata esemptuosa.

Per impostazione predefinita, queste impostazioni sono disponibili. Quando una di queste impostazioni è disattivata, qualsiasi utente a cui è assegnato il criterio non può avviare o pianificare nuove riunioni di questo tipo. Allo stesso tempo, i collegamenti di partecipazione alla riunione e gli ID conferenza di tutte le riunioni esistenti di quel tipo che l'utente ha avviato o pianificato in precedenza scadono.

Ad esempio, se a un utente è assegnato un criterio di riunione in cui queste impostazioni dei criteri riunione sono impostate su **Attivata** e quindi si disattiva l'impostazione Consenti riunione ora **nei** canali, l'utente non può più avviare riunioni esromptu nei canali e il canale Riunione ora partecipa ai collegamenti creati dall'utente in precedenza è scaduto. L'utente può comunque avviare e pianificare altri tipi di riunione e partecipare a riunioni organizzate da altre persone.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>Cosa succede alla scadenza del collegamento di partecipazione alla riunione e dell'ID conferenza?

Quando il collegamento per partecipare alla riunione e l'ID conferenza per una riunione scadono, nessuno può partecipare alla riunione. Quando un utente prova a partecipare alla riunione tramite il collegamento o tramite telefono, viene visualizzato un messaggio che indica che la riunione non è più disponibile. Le conversazioni, i file, le lavagne, le registrazioni, le trascrizioni e altri contenuti correlati alla riunione vengono mantenuti e gli utenti possono comunque accedervi.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>Cosa succede quando si attiva e si disattiva un'impostazione dei criteri riunione?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Attivare o disattivare un'impostazione dei criteri per le riunioni

Quando un'impostazione dei criteri per le riunioni è impostata su **Attivata,** gli utenti a cui è assegnato il criterio possono avviare o pianificare riunioni di quel tipo e tutti possono partecipare. Quando si imposta il criterio riunione su **Disattivato,** gli utenti a cui è assegnato il criterio non possono avviare o pianificare nuove riunioni di questo tipo e i collegamenti per la partecipazione alla riunione e gli ID conferenza delle riunioni esistenti pianificate in precedenza dall'utente sono scaduti.

Tenere presente che l'utente può comunque partecipare a riunioni organizzate da altre persone.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Attivare o disattivare un'impostazione dei criteri per le riunioni

Quando si cambia l'impostazione di un criterio riunione da Disattivato a **Attivata,** gli utenti a cui è assegnato il criterio possono avviare o pianificare riunioni di quel tipo.  Se un'impostazione dei criteri riunione è disattivata e quindi nuovamente attivata per un utente, tutte le riunioni pianificate (e scadute) in precedenza organizzate dall'utente diventano attive e le persone possono partecipare usando il collegamento di partecipazione alla riunione o tramite telefono.  

## <a name="meeting-expiration-scenarios"></a>Scenari di scadenza delle riunioni

Ecco un riepilogo del funzionamento della scadenza della riunione per ognuna delle impostazioni dei criteri di riunione descritte in questo articolo. 

|Per: |Eseguire questa operazione  |Comportamento di partecipazione alla riunione  |
|---------|---------|---------|
|Scadenza del canale Riunione ora riunioni avviate da un utente  |Disattivare **Consenti ora di incontrarsi nei canali.**|Nessuno può partecipare al canale Riunione ora le riunioni avviate dall'utente.         |
|Scadere le riunioni del canale pianificate da un utente   |Disattivare **Consenti pianificazione delle riunioni del canale**.         |Nessuno può partecipare alle riunioni del canale pianificate dall'utente. In questo modo si impedisce agli utenti di partecipare a quanto segue:<ul><li>Riunioni del canale avvenute in passato.</li> <li>Riunioni del canale pianificate per il futuro e non ancora avvenute.</li><li>Istanze future di riunioni di canale ricorrenti.</li></ul>       |
|Scadere le riunioni private pianificate da un utente    |Disattivare **Consenti pianificazione riunioni private** *e* Consenti il componente **aggiuntivo outlook.**          |Nessuno può partecipare a riunioni private pianificate dall'utente. In questo modo si impedisce agli utenti di partecipare a quanto segue: <ul><li>Riunioni private avvenute in passato.</li> <li>Riunioni private pianificate per il futuro e non ancora avvenute.</li><li>Istanze future di riunioni private ricorrenti.</li></ul> Sia **Consenti pianificazione riunioni private** che Consenti il componente aggiuntivo **outlook** devono essere disattivati per la scadenza delle riunioni private pianificate da un utente. Se un'impostazione è disattivata e l'altra è attivata, i collegamenti e gli ID conferenza delle riunioni esistenti rimangono attivi e non saranno scaduti.      |
|Scadenza riunione privata ora riunioni avviate da un utente  |Disattivare **Consenti riunione ora nelle riunioni private.**          |Nessuno può partecipare a riunioni private di Meet now avviate dall'utente.         |

Se si vuole che gli utenti accertano le riunioni pianificate o avviate in precedenza da un determinato utente, è possibile:

- Attivare l'impostazione dei criteri riunione per l'utente.
- Disattivare l'impostazione dei criteri riunione per l'utente e impostare un altro utente con l'impostazione dei criteri abilitata per creare una nuova riunione per sostituire la riunione scaduta.

> [!NOTE]
> Se la riunione è stata inviata da un delegato, a cui sono state concesse le autorizzazioni per inviare inviti alle riunioni per conto di un'altra persona, ad esempio un responsabile, l'impostazione dei criteri di riunione viene applicata alla persona che ha concesso l'autorizzazione (il responsabile).

## <a name="related-topics"></a>Argomenti correlati

[Gestire i criteri di riunione in Teams](meeting-policies-in-teams.md)

[Assegnare i criteri agli utenti in Teams](assign-policies.md)

[Panoramica di PowerShell per Teams](teams-powershell-overview.md)