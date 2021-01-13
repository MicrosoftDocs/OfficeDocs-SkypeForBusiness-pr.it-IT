---
title: Criteri riunione e scadenza riunione in Microsoft Teams
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
description: Informazioni su come usare le impostazioni dei criteri di riunione per controllare la scadenza delle riunioni in Microsoft teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e1efb8ac21cbe669bcea3569a5e231469685a249
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827526"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Criteri riunione e scadenza riunione in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Panoramica

I [criteri di riunione](meeting-policies-in-teams.md) in Microsoft teams vengono usati per controllare se gli utenti dell'organizzazione possono avviare e pianificare le riunioni e le caratteristiche disponibili per i partecipanti alla riunione per le riunioni programmate dagli utenti. Puoi usare il criterio globale (predefinito per l'intera organizzazione) oppure creare e assegnare criteri personalizzati. Puoi gestire i criteri delle riunioni nell'interfaccia di amministrazione di Microsoft teams oppure usando i cmdlet [Get](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingpolicy), [New](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy), [set](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmeetingpolicy), [Grant](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy di PowerShell.

Le impostazioni dei criteri riunione che controllano se gli utenti possono avviare e pianificare le riunioni controllano anche la scadenza delle riunioni pianificate dagli utenti. Quando scade un collegamento a una riunione e un ID conferenza per una riunione, nessuno può partecipare alla riunione. Le impostazioni dei criteri di riunione seguenti determinano se gli utenti possono avviare e pianificare riunioni in teams e fare riferimento a questi ultimi in questo articolo.

- [Consenti riunione ora nei canali](meeting-policies-in-teams.md#allow-meet-now-in-channels): controlla se un utente può avviare un incontro estemporaneo in un canale.
- [Consenti pianificazione riunione canale](meeting-policies-in-teams.md#allow-channel-meeting-scheduling): controlla se un utente può pianificare una riunione in un canale.
- [Consenti la pianificazione di riunioni private](meeting-policies-in-teams.md#allow-scheduling-private-meetings): controlla se un utente può programmare una riunione privata in teams. Una riunione è privata quando non viene pubblicata in un canale in un team.
- [Consenti il componente aggiuntivo per Outlook](meeting-policies-in-teams.md#allow-the-outlook-add-in): controlla se un utente può pianificare una riunione privata da Outlook. Una riunione è privata quando non viene pubblicata in un canale in un team.
- [Consenti riunione ora in riunioni private](meeting-policies-in-teams.md#allow-meet-now-in-private-meetings): controlla se un utente può avviare un incontro privato estemporaneo.

Per impostazione predefinita, queste impostazioni sono attivate. Quando una di queste impostazioni è disattivata, qualsiasi utente a cui viene assegnato il criterio non può avviare o pianificare le nuove riunioni di quel tipo. Allo stesso tempo, i collegamenti alla riunione e gli ID conferenza di tutte le riunioni esistenti di quel tipo che l'utente ha già iniziato o pianificato scadono.

Ad esempio, se a un utente viene assegnato un criterio per la riunione in cui queste impostazioni dei criteri di riunione sono impostate **su** attivato e quindi si disattiva l'impostazione **Consenti riunioni in canali** , l'utente non potrà più avviare incontri improvvisati nei canali e il canale incontra ora i collegamenti che l'utente ha creato in precedenza. L'utente può comunque avviare e pianificare altri tipi di riunione e partecipare a riunioni organizzati da altri utenti.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>Cosa succede quando il collegamento a una riunione e l'ID conferenza scadono?

Quando il collegamento a una riunione e l'ID conferenza di una riunione scadono, nessuno può partecipare alla riunione. Quando un utente tenta di partecipare alla riunione tramite il collegamento o tramite telefono, riceverà un messaggio che indica che la riunione non è più disponibile. Le conversazioni, i file, le lavagne, le registrazioni, le trascrizioni e altri contenuti correlati alla riunione vengono mantenuti e gli utenti possono comunque accedervi.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>Cosa succede quando si attiva e si disattiva un'impostazione di criteri per le riunioni?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Cambiare l'impostazione di un criterio di riunione da attivato a disattivato

Quando un'impostazione per i criteri di riunione è impostata **su** attivato, gli utenti a cui viene assegnato il criterio possono avviare o pianificare riunioni del tipo e tutti possono partecipare. Quando si cambia l'impostazione del criterio riunione su **disattivato**, gli utenti a cui viene assegnato il criterio non possono avviare o pianificare nuove riunioni di questo tipo e i collegamenti alla riunione e gli ID conferenza delle riunioni esistenti che l'utente ha pianificato in precedenza.

Tieni presente che l'utente può ancora partecipare alle riunioni organizzate da altri utenti.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Cambiare l'impostazione di un criterio riunione da disattivato a attivato

Quando si cambia l'impostazione di un criterio riunione da **disattivato** a **attivato, gli utenti a cui** è stato assegnato il criterio possono avviare o pianificare le riunioni del tipo. Se un'impostazione per i criteri di riunione è disattivata e quindi riattivata per un utente, tutte le riunioni pianificate (ed esposte in precedenza) organizzate dall'utente diventano attive e le persone possono partecipare tramite il collegamento a una riunione o tramite telefono.  

## <a name="meeting-expiration-scenarios"></a>Scenari di scadenza delle riunioni

Ecco un riepilogo del funzionamento della scadenza delle riunioni per ognuna delle impostazioni dei criteri di riunione descritte in questo articolo. 

|Per: |Operazione da eseguire  |Comportamento di partecipazione alle riunioni  |
|---------|---------|---------|
|Scadenza canale riunione ora riunioni avviate da un utente  |Disattivare **Consenti riunione ora nei canali**.|Non è possibile partecipare a un canale riunione ora riunioni avviate dall'utente.         |
|Scadere le riunioni di canale pianificate da un utente   |Disattivare la **programmazione Consenti riunione canali**.         |Nessuno può partecipare a riunioni di canale pianificate dall'utente. Ciò impedisce agli utenti di partecipare alle operazioni seguenti:<ul><li>Riunioni di canale che si sono verificate nel passato.</li> <li>Riunioni di canale pianificate per il futuro e non ancora avvenute.</li><li>Istanze future delle riunioni di canali ricorrenti.</li></ul>       |
|Scadono le riunioni private programmate da un utente    |Disattivare **Consenti la pianificazione di riunioni private** *e* disattivare **Consenti il componente aggiuntivo per Outlook**.          |Nessuno può partecipare a riunioni private pianificate dall'utente. Ciò impedisce agli utenti di partecipare alle operazioni seguenti: <ul><li>Riunioni private che si sono verificate in passato.</li> <li>Riunioni private pianificate per il futuro e non ancora avvenute.</li><li>Istanze future delle riunioni private ricorrenti.</li></ul> **Consentire la pianificazione di riunioni private** e **consentire il componente aggiuntivo per Outlook** deve essere disattivato per la scadenza delle riunioni private pianificate da un utente. Se un'impostazione è disattivata e l'altra è attiva, i collegamenti alla riunione e gli ID conferenza delle riunioni esistenti rimarranno attivi e non verranno scaduti.      |
|Scadenza private meeting Now riunioni avviate da un utente  |Disattivare **Consenti riunione ora in riunioni private**.          |Nessuno può partecipare a riunioni private riunione avviate dall'utente.         |

Se si vuole che gli utenti accedano alle riunioni pianificate o avviate in precedenza da un determinato utente, è possibile:

- Attivare l'impostazione dei criteri di riunione per l'utente.
- Disattivare l'impostazione dei criteri di riunione per l'utente e avere un altro utente con l'impostazione del criterio abilitato per creare una nuova riunione per sostituire la riunione scaduta.

> [!NOTE]
> Se la riunione è stata inviata da un delegato, a cui è stata assegnata l'autorizzazione per l'invio di inviti alla riunione per conto di un'altra persona, ad esempio un responsabile, l'impostazione dei criteri di riunione viene applicata alla persona che ha concesso l'abilitazione (il responsabile).

## <a name="related-topics"></a>Argomenti correlati

[Gestire i criteri di riunione in Teams](meeting-policies-in-teams.md)

[Assegnare i criteri agli utenti in Teams](assign-policies.md)

[Panoramica di PowerShell per Teams](teams-powershell-overview.md)