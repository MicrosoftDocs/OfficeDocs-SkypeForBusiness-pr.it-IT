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
description: Informazioni su come usare le impostazioni dei criteri di riunione per controllare la scadenza delle riunioni in Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e1efb8ac21cbe669bcea3569a5e231469685a249
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827526"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Criteri delle riunioni e scadenza delle riunioni in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Panoramica

[I criteri di](meeting-policies-in-teams.md) riunione in Microsoft Teams vengono utilizzati per controllare se gli utenti dell'organizzazione possono avviare e pianificare riunioni e le funzionalità disponibili per i partecipanti alle riunioni pianificate dagli utenti. È possibile usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati. È possibile gestire i criteri di riunione nell'interfaccia di amministrazione di Microsoft Teams oppure tramite i cmdlet [di](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingpolicy)PowerShell Get, [New,](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) [Set,](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) [Remove,](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmeetingpolicy) [Grant](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy.

Le impostazioni dei criteri per le riunioni che controllano se gli utenti possono avviare e pianificare riunioni controllano anche la scadenza delle riunioni pianificate dagli utenti. Quando un collegamento per partecipare a una riunione e l'ID conferenza per una riunione scadono, nessuno può partecipare alla riunione. Le seguenti impostazioni dei criteri per le riunioni determinano se gli utenti possono avviare e pianificare riunioni in Teams, a cui si fa riferimento in questo articolo.

- [Consenti riunione adesso nei canali:](meeting-policies-in-teams.md#allow-meet-now-in-channels)controlla se un utente può avviare una riunione es improvvisata in un canale.
- [Consenti pianificazione di riunioni di canale:](meeting-policies-in-teams.md#allow-channel-meeting-scheduling)controlla se un utente può pianificare una riunione in un canale.
- [Consentire la pianificazione di riunioni private:](meeting-policies-in-teams.md#allow-scheduling-private-meetings)controlla se un utente può pianificare una riunione privata in Teams. Una riunione è privata quando non viene pubblicata in un canale in un team.
- [Consenti il componente aggiuntivo di Outlook:](meeting-policies-in-teams.md#allow-the-outlook-add-in)controlla se un utente può pianificare una riunione privata da Outlook. Una riunione è privata quando non viene pubblicata in un canale in un team.
- [Consenti riunione in corso in riunioni private:](meeting-policies-in-teams.md#allow-meet-now-in-private-meetings)controlla se un utente può avviare una riunione privata es improvvisata.

Per impostazione predefinita, queste impostazioni sono disponibili. Quando una di queste impostazioni è disattivata, gli utenti a cui è assegnato il criterio non possono avviare o pianificare nuove riunioni di questo tipo. Allo stesso tempo, i collegamenti per partecipare alla riunione e gli ID conferenza di tutte le riunioni esistenti del tipo che l'utente ha iniziato o pianificato in precedenza scadono.

Ad esempio, se a un utente è assegnato un criterio per le riunioni in  cui queste impostazioni dei criteri per le riunioni sono impostate su Attivata e quindi si disattiva l'impostazione Consenti riunione adesso nei canali, l'utente non può più avviare riunioni improvvisate nei canali e il canale Riunione ora partecipa ai collegamenti creati in precedenza dall'utente è scaduto. L'utente può comunque avviare e pianificare altri tipi di riunione e partecipare alle riunioni organizzate da altre persone.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>Cosa succede quando il collegamento per partecipare alla riunione e l'ID conferenza scadono?

Quando il collegamento per partecipare alla riunione e l'ID conferenza per una riunione scadono, nessuno può partecipare alla riunione. Quando un utente prova a partecipare alla riunione tramite collegamento o telefono, viene visualizzato un messaggio che indica che la riunione non è più disponibile. Le conversazioni, i file, le lavagne, le registrazioni, le trascrizioni e altri contenuti relativi alla riunione vengono conservati e gli utenti possono comunque accedervi.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>Cosa succede quando si attiva e disattiva un'impostazione dei criteri per le riunioni?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Attivare o disattivare un'impostazione dei criteri per le riunioni

Quando un'impostazione dei criteri per le riunioni è impostata su **Attivata,** gli utenti a cui è assegnato il criterio possono avviare o pianificare riunioni di quel tipo e tutti possono partecipare. Quando si imposta il criterio riunione su **Disattivato,** gli utenti a cui è assegnato il criterio non possono avviare o pianificare nuove riunioni di questo tipo e i collegamenti per la partecipazione alla riunione e gli ID conferenza delle riunioni esistenti pianificate dall'utente in precedenza sono scaduti.

Tenere presente che l'utente può comunque partecipare a riunioni organizzate da altre persone.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Attivare o disattivare un'impostazione dei criteri per le riunioni

Quando si imposta un  criterio di riunione da Disattivato a **Attivata,** gli utenti a cui è assegnato il criterio possono avviare o pianificare riunioni di quel tipo. Se un'impostazione dei criteri riunione è disattivata e quindi ri attivata per un utente, tutte le riunioni pianificate in precedenza (e scadute) organizzate dall'utente diventano attive e le persone possono parteciparvi utilizzando il collegamento per partecipare alla riunione o tramite telefono.  

## <a name="meeting-expiration-scenarios"></a>Scenari di scadenza delle riunioni

Ecco un riepilogo del funzionamento della scadenza della riunione per ognuna delle impostazioni dei criteri di riunione illustrate in questo articolo. 

|Per: |Operazione da eseguire  |Comportamento di partecipazione a una riunione  |
|---------|---------|---------|
|Expire channel Meet now meetings started by a user  |Disattiva **Consenti la meet now nei canali.**|Nessuno può partecipare al canale Riunione in corso delle riunioni avviate dall'utente.         |
|Scadere le riunioni del canale pianificate da un utente   |Disattivare **Consenti pianificazione riunioni di canale.**         |Nessuno può partecipare alle riunioni del canale pianificate dall'utente. In questo modo si impedisce agli utenti di partecipare alle operazioni seguenti:<ul><li>Riunioni del canale che hanno fatto in passato.</li> <li>Riunioni del canale pianificate per il futuro e non ancora avvenute.</li><li>Istanze future di riunioni di canale ricorrenti.</li></ul>       |
|Scadere le riunioni private pianificate da un utente    |Disattivare **Consenti pianificazione riunioni private** *e* Consenti il componente aggiuntivo **di Outlook.**          |Nessuno può partecipare a riunioni private pianificate dall'utente. In questo modo si impedisce agli utenti di partecipare alle operazioni seguenti: <ul><li>Riunioni private che hanno luogo in passato.</li> <li>Riunioni private pianificate per il futuro e non ancora avvenute.</li><li>Istanze future di riunioni private ricorrenti.</li></ul> Sia **Consenti pianificazione riunioni private** che Consenti al componente aggiuntivo **Outlook** devono essere disattivate per le riunioni private pianificate da un utente. Se un'impostazione è disattivata e l'altra è attivata, i collegamenti per partecipare alle riunioni e gli ID conferenza delle riunioni esistenti rimangono attivi e non scadranno.      |
|Scadenza delle riunioni private iniziate da un utente  |Disattivare **Consenti riunione in corso nelle riunioni private.**          |Nessuno può partecipare alle riunioni private Iniziate dall'utente.         |

Se si vuole che le persone accertasino delle riunioni precedentemente pianificate o iniziate da un particolare utente, è possibile:

- Attivare l'impostazione dei criteri per la riunione per l'utente.
- Disattivare l'impostazione dei criteri per la riunione per l'utente e fare in modo che un altro utente a cui è abilitata l'impostazione del criterio crei una nuova riunione per sostituire la riunione scaduta.

> [!NOTE]
> Se la riunione è stata inviata da un delegato a cui sono state concesse le autorizzazioni per inviare inviti alle riunioni per conto di un'altra persona, ad esempio un manager, l'impostazione del criterio di riunione viene applicata alla persona che ha concesso l'autorizzazione (il responsabile).

## <a name="related-topics"></a>Argomenti correlati

[Gestire i criteri di riunione in Teams](meeting-policies-in-teams.md)

[Assegnare i criteri agli utenti in Teams](assign-policies.md)

[Panoramica di PowerShell per Teams](teams-powershell-overview.md)