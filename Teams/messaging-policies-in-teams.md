---
title: Gestire i criteri di messaggistica in Teams
ms.author: mabond
author: mkbond007
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.messagingpolicies.overview
- seo-marvel-apr2020
- chat-teams-channels-revamp
description: Informazioni sui criteri di messaggistica e su come possono essere usati per controllare la messaggistica chat in Teams.
ms.openlocfilehash: e3925d76c66c324337982f37e704caded77b02a5
ms.sourcegitcommit: 54c691bd34980a47a5ebf58555529a618a8cada7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2022
ms.locfileid: "69251779"
---
# <a name="manage-messaging-policies-in-teams"></a>Gestire i criteri di messaggistica in Teams

<!--- Add zone marker here--->

I criteri di messaggistica vengono usati per controllare quali funzionalità di messaggistica di chat e canali sono disponibili per [gli utenti (proprietari e membri)](assign-roles-permissions.md) in Microsoft Teams. È possibile usare il criterio globale (predefinito a livello di organizzazione) creato automaticamente oppure creare e assegnare criteri di messaggistica personalizzati.

Gli utenti dell'organizzazione riceveranno automaticamente i criteri globali, a meno che non vengano creati e assegnati criteri personalizzati. Modificare le impostazioni nel criterio globale oppure creare e assegnare uno o più criteri personalizzati per attivare o disattivare le caratteristiche desiderate.

> [!NOTE]
> Per garantire la sincronizzazione dopo una modifica dei criteri, potrebbe essere necessario un riavvio per alcune istanze. 

## <a name="create-a-custom-messaging-policy"></a>Creare criteri di messaggistica personalizzati

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Criteri di messaggistica**.
2. Selezionare **Aggiungi**.
3. Immettere un nome e una descrizione per il criterio.
4. Scegliere le impostazioni desiderate.
5. Selezionare **Salva**.

Ad esempio, si vuole assicurarsi che i messaggi inviati non vengano eliminati o modificati. Creare un nuovo criterio personalizzato denominato "Conserva messaggi inviati" e disattivare le impostazioni seguenti:

- I proprietari possono eliminare i messaggi inviati
- Gli utenti possono eliminare i messaggi inviati
- Gli utenti possono modificare i messaggi inviati

Assegnare quindi il criterio agli utenti.

## <a name="edit-a-messaging-policy"></a>Modificare i criteri di messaggistica

È possibile modificare il criterio globale e i criteri personalizzati creati.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Criteri di messaggistica**.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.
3. Da lì, apportare le modifiche desiderate.
4. Selezionare **Salva**.

## <a name="assign-a-custom-messaging-policy-to-users"></a>Assegnare criteri di messaggistica personalizzati agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

A un utente può essere assegnato un solo criterio di messaggistica alla volta.

> [!NOTE]
> Non è possibile eliminare un criterio a cui sono utenti. È prima di tutto necessario assegnare un criterio diverso a tutti gli utenti interessati, quindi sarà possibile eliminare il criterio originale.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Impostazioni dei criteri di messaggistica

Ecco le impostazioni dei criteri di messaggistica che è possibile configurare.

- **I proprietari possono eliminare i messaggi inviati**  Usare questa impostazione per consentire ai proprietari di eliminare i messaggi o i post del canale inviati dall'utente.
- **Eliminare i messaggi inviati** Usare questa impostazione per consentire agli utenti di eliminare singoli messaggi inviati in chat.
- **Eliminare una chat** Usare questa impostazione per consentire agli utenti di eliminare intere conversazioni dall'elenco chat. In questo modo verranno eliminati solo i contenuti della chat per l'utente che esegue l'azione; gli altri utenti nella chat potranno comunque vedere tutti i messaggi. L'utente che ha eliminato la chat non vedrà messaggi esistenti nel proprio feed attività o risultati della ricerca per la chat eliminata; anche questo utente verrà rimosso dalla chat eliminata. Agli utenti verrà chiesto di confermare la decisione di eliminare una chat. Questa impostazione è attivata per impostazione predefinita. Se questa impostazione è disattivata, gli utenti non vedranno più l'opzione di eliminazione per le loro chat.
- **Modificare i messaggi inviati** Usare questa impostazione per consentire agli utenti di modificare i messaggi inviati in chat.
- **Conferme di lettura** Le conferme di lettura consentono al mittente di un messaggio di chat di ricevere una notifica quando il messaggio è stato letto dal destinatario in 1:1 e in chat di gruppo almeno 20 persone. Le conferme di lettura dei messaggi eliminano l'incertezza sul fatto che un messaggio sia stato letto e migliorano le comunicazioni del team. Le conferme di lettura non vengono acquisite nei report di eDiscovery.  
  - **Controllo dell'utente** Questo significa che gli utenti possono decidere se attivare o disattivare le conferme di lettura. L'impostazione predefinita all'interno dell'app è ATTIVATA. Gli utenti possono quindi disattivarla.
  - **Attivato per tutti gli utenti** Questo significa che tutti gli utenti del tenant avranno la funzionalità attivata senza la possibilità di disattivarla. Quando si usa l'impostazione **Attivato per tutti** , l'unico modo per impostare le ricevute per l'intero tenant consiste nell'avere un solo criterio di messaggistica per l'intero tenant (il criterio predefinito denominato "Globale (impostazione predefinita a livello di organizzazione)") oppure fare in modo che tutti i criteri di messaggistica nel tenant utilizzino le stesse impostazioni per le conferme. La caratteristica conferme di lettura è più efficace se è **abilitata per tutti**.
  - **Disattivato per tutti gli utenti** Questo significa che la caratteristica è disabilitata e nessuno nel tenant ha conferme di lettura né può attivarla.
<a name="bkchat"> </a>

- **Chat**  Attivare questa impostazione se si vuole che gli utenti dell'organizzazione possano usare l'app Teams per chattare con altre persone.
- **Chattare con i gruppi** Gli utenti possono avviare una chat con gruppi di distribuzione, gruppi di sicurezza abilitati alla posta elettronica e gruppi di Microsoft 365.
- **Usare Giphy nelle conversazioni**  Se si attiva Giphys, gli utenti possono includere Giphy nelle conversazioni in chat con altre persone. Giphy è un database online e un motore di ricerca che consente agli utenti di cercare e condividere file GIF animati. A ogni Giphy viene assegnata una classificazione dei contenuti. Oltre ad attivare questa impostazione, è necessario abilitare [esperienze connesse facoltative](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) per consentire giphy nelle conversazioni.
- **Valutazione del contenuto Giphy**
  - **Nessuna restrizione** Ciò significa che gli utenti saranno in grado di inserire qualsiasi Giphy in chat indipendentemente dalla classificazione del contenuto.
  - **Moderata**  Questo significa che gli utenti saranno in grado di inserire Giphy in chat, ma sarà moderatamente limitato dal contenuto per adulti.
  - **Rigorosa**  Ciò significa che i tuoi utenti saranno in grado di inserire Giphy in chat, ma sarà strettamente limitato dal contenuto per adulti.
- **Meme nelle conversazioni** Se attivi Meme, gli utenti possono includere memi nelle conversazioni in chat con altre persone.
- **Adesivi nelle conversazioni** Se si attiva questa opzione, gli utenti possono includere gli adesivi nelle conversazioni in chat con altre persone.
- **Anteprime degli URL** Usare questa impostazione per attivare o disattivare l'anteprima automatica degli URL nei messaggi.
- **Tradurre messaggi** Attivare questa impostazione per consentire agli utenti di tradurre automaticamente i messaggi di Teams nella lingua specificata dalle impostazioni personali della lingua per Microsoft 365 o Office 365.
- **Strumento di lettura immersiva per i messaggi** Attivare questa impostazione per consentire agli utenti di visualizzare i messaggi in Microsoft Strumento di lettura immersiva. Strumento di lettura immersiva è uno strumento di apprendimento che offre un'esperienza di lettura a schermo intero per migliorare la leggibilità del testo.
- **Inviare messaggi urgenti usando le notifiche di priorità** Se si attiva questa opzione, gli utenti possono inviare messaggi usando [le notifiche di priorità](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462). Le notifiche di priorità avvisano gli utenti ogni 2 minuti per 20 minuti o fino a quando i messaggi contrassegnati come *urgenti* non vengono raccolti e letti dal destinatario. Questa caratteristica aumenta la probabilità che il messaggio venga agito in modo tempestivo. Non è possibile modificare un messaggio urgente dopo averlo inviato.
- **Creare messaggi vocali**
  > [!Important]
  > I messaggi audio non vengono acquisiti nei report di eDiscovery.
  - **Consentito nelle chat e nei canali** Questo significa che gli utenti possono lasciare messaggi audio sia in chat che in canali.
  - **Consentito solo nelle chat** Questo significa che gli utenti possono lasciare i messaggi audio nelle chat, ma non nei canali.
  - **Non abilitato** Questo significa che gli utenti non possono creare messaggi audio in chat o canali.  
- **Nei dispositivi mobili, visualizza i canali preferiti sopra le chat recenti** Abilita questa impostazione per spostare i canali preferiti nella parte superiore dello schermo del dispositivo mobile in modo che un utente non debba scorrere per trovarli.
- **Rimuovere utenti dalle chat di gruppo** Attivare questa impostazione per consentire a un utente di rimuovere altri utenti da una chat di gruppo. Questa funzionalità consente di continuare una chat con un gruppo più piccolo di persone senza perdere la cronologia della chat.
- **Completamento del testo** Attiva questa impostazione per consentire a un utente di ottenere il completamento del testo per i messaggi di chat.
- **Risposte suggerite**  Attiva questa impostazione per abilitare le risposte suggerite per i messaggi di chat.
- **Ruolo di autorizzazione chat** Usare questa impostazione per definire il ruolo di chat supervisionato dell'utente. Altre informazioni sulla [chat supervisionata](supervise-chats-edu.md).
- **Gli utenti con autorizzazioni chat complete possono eliminare qualsiasi messaggio** Usare questa impostazione per consentire agli utenti con autorizzazioni complete di eliminare qualsiasi messaggio di gruppo o chat della riunione.
- **Messaggi video** Attivare questa impostazione se si vuole che gli utenti dell'organizzazione possano usare l'app Teams per inviare messaggi video ad altre persone in Chat.

> [!NOTE]
> Alcune di queste impostazioni, ad esempio Giphy, possono anche essere configurate a livello di team dai proprietari del team e a livello di canale privato o condiviso dai proprietari del canale.

### <a name="related-topics"></a>Argomenti correlati

- [Assegnare criteri a utenti e gruppi in Teams](assign-policies-users-and-groups.md)
- [Assegnare proprietari e membri del team in Microsoft Teams](assign-roles-permissions.md)
