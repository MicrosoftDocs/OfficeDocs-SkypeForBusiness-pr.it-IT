---
title: Gestire i criteri di messaggistica in Teams
ms.author: serdars
author: SerdarSoysal
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
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.messagingpolicies.overview
- seo-marvel-apr2020
description: In questo articolo si apprenderanno i criteri di messaggistica e come possono essere usati per controllare la messaggistica della chat in Teams.
ms.openlocfilehash: 050f072a2148be909dbaabd4ac8ab53c1e5bb298
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611660"
---
# <a name="manage-messaging-policies-in-teams"></a>Gestire i criteri di messaggistica in Teams

<!--- Add zone marker here--->

I criteri di messaggistica vengono utilizzati per controllare quali funzionalità di messaggistica chat e canale sono disponibili [per gli utenti (proprietari](assign-roles-permissions.md) e membri) in Microsoft Teams. È possibile usare il criterio globale (impostazione predefinita a livello di organizzazione) creato automaticamente oppure creare e assegnare criteri di messaggistica personalizzati.

Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato. È possibile modificare le impostazioni nei criteri globali oppure creare e assegnare uno o più criteri personalizzati per attivare o disattivare le caratteristiche desiderate.

## <a name="create-a-custom-messaging-policy"></a>Creare criteri di messaggistica personalizzati

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Criteri di messaggistica.**
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per il criterio.
4. Scegliere le impostazioni desiderate.
5. Fare clic su **Salva**.

Si supponga ad esempio di voler assicurarsi che i messaggi inviati non siano eliminati o modificati. Creare un nuovo criterio personalizzato denominato "Conserva messaggi inviati" e disattivare le impostazioni seguenti:

- I proprietari possono eliminare i messaggi inviati
- Gli utenti possono eliminare i messaggi inviati
- Gli utenti possono modificare i messaggi inviati

Quindi assegnare il criterio agli utenti.

## <a name="edit-a-messaging-policy"></a>Modificare un criterio di messaggistica

È possibile modificare il criterio globale e i criteri personalizzati creati. 

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Criteri di messaggistica.**
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.
3. Da lì, apportare le modifiche desiderate.
4. Fare clic su **Salva**.

## <a name="assign-a-custom-messaging-policy-to-users"></a>Assegnare criteri di messaggistica personalizzati agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

A un utente può essere assegnato un solo criterio di messaggistica alla volta.

> [!NOTE]
> Non è possibile eliminare un criterio a cui sono utenti. È prima di tutto necessario assegnare un criterio diverso a tutti gli utenti interessati, quindi sarà possibile eliminare il criterio originale.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Impostazioni dei criteri di messaggistica

Ecco le impostazioni dei criteri di messaggistica che è possibile configurare.

- **I proprietari possono eliminare i messaggi inviati**  Usare questa impostazione per consentire ai proprietari di eliminare i messaggi inviati dagli utenti in chat.
- **Gli utenti possono eliminare i messaggi inviati** Usare questa impostazione per consentire agli utenti di eliminare i messaggi inviati in chat.
- **Gli utenti possono modificare i messaggi inviati** Usare questa impostazione per consentire agli utenti di modificare i messaggi inviati in chat.
- **Conferme di lettura** Le conferme di lettura consentono al mittente di un messaggio di chat di essere avvisato quando il messaggio è stato letto dal destinatario in 1:1 e le chat di gruppo 20 persone o meno. Le conferme di lettura dei messaggi determinano in modo incerto se un messaggio è stato letto e migliorano la comunicazione del team. Tenere presente che le conferme di lettura non vengono acquisite nei report di eDiscovery.  
    - **Utente controllato** Questo significa che gli utenti devono decidere se le conferme di lettura devono essere disattivate o meno. L'impostazione predefinita all'interno dell'app è attivata. Gli utenti possono quindi disattivarla.
    - **Per tutti** Questo significa che tutti gli utenti del tenant avranno la funzionalità attivata, senza possibilità di disattivarla. Tenere presente che  quando si usa l'impostazione Attivata per tutti gli utenti, l'unico modo per impostare le ricevute per l'intero tenant è impostare un solo criterio di messaggistica per l'intero tenant (il criterio predefinito denominato "Globale (impostazione predefinita a livello di organizzazione)") o fare in modo che tutti i criteri di messaggistica nel tenant usino le stesse impostazioni per le ricevute. La funzionalità conferme di lettura è più efficace se è abilitata per **tutti gli utenti.**
    - **Disattivato per tutti** Questo significa che la funzionalità è disabilitata e nessuno nel tenant ha conferme di lettura né può attivarla.
<a name="bkchat"> </a>

- **Chat**  Attivare questa impostazione se si vuole consentire agli utenti dell'organizzazione di usare l'app Teams per chattare con altre persone.
- **Usare Giphy nelle conversazioni**  Se si attiva questa opzione, gli utenti possono includere Giphy nelle conversazioni in chat con altre persone. Giphy è un database online e un motore di ricerca che consente agli utenti di cercare e condividere file GIF animati. A ogni Giphy viene assegnata una classificazione dei contenuti. Oltre ad attivare questa impostazione, è necessario abilitare [](https://docs.microsoft.com/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) anche le esperienze connesse facoltative per consentire Giphy nelle conversazioni.
- **Classificazione del contenuto Giphy**
    - **Nessuna restrizione** Questo significa che gli utenti potranno inserire qualsiasi Giphy nelle chat indipendentemente dalla classificazione del contenuto.
    - **Moderato**  Questo significa che gli utenti potranno inserire Giphy nelle chat, ma saranno moderatamente limitati dal contenuto per adulti.
    - **Restrittiva**  Questo significa che gli utenti potranno inserire Giphy nelle chat, ma saranno rigorosamente limitati ai contenuti per adulti.
- **Usare i Meme nelle conversazioni** Se attivi questa opzione, gli utenti possono includere Meme nelle conversazioni in chat con altre persone.
- **Usare gli sticker nelle conversazioni** Se attivi questa opzione, gli utenti possono includere sticker nelle conversazioni in chat con altre persone.
- **Consenti anteprime degli URL** Usare questa impostazione per attivare o disattivare l'anteprima automatica degli URL nei messaggi.
- **Consentire agli utenti di tradurre i messaggi** Attivare questa impostazione per consentire agli utenti di tradurre automaticamente i messaggi di Teams nella lingua specificata dalle impostazioni personali della lingua per Microsoft 365 o Office 365.
- **Consentire lo strumento di lettura immersiva per la visualizzazione dei messaggi** Attivare questa impostazione per consentire agli utenti di visualizzare i messaggi nello strumento di lettura immersiva. Lo strumento di lettura immersiva è uno strumento di apprendimento che offre un'esperienza di lettura a schermo intero per migliorare la leggibilità del testo.
- **Inviare messaggi urgenti usando le notifiche di priorità** Se si attiva questa opzione, gli utenti possono inviare messaggi usando le [notifiche di priorità.](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462) Le notifiche di priorità informano gli utenti ogni 2 minuti per  un periodo di 20 minuti o finché i messaggi contrassegnati come urgenti non vengono ritirati e letti dal destinatario, massimizzando la probabilità che il messaggio si aggravi in modo efficace.
- **Creazione di messaggi audio** 
  > [!Important]
  > I messaggi audio non vengono acquisiti nei report di eDiscovery.
    - **Consentito in chat e canali** Questo significa che gli utenti possono lasciare i messaggi audio sia nelle chat che nei canali.
    - **Consentito solo nelle chat** Questo significa che gli utenti possono lasciare i messaggi audio nelle chat, ma non nei canali.
    - **Disabilitato** Questo significa che gli utenti non possono creare messaggi audio in chat o canali.  
- **Su dispositivi mobili, visualizza i canali preferiti sopra le chat recenti** Abilitare questa impostazione per spostare i canali preferiti nella parte superiore della schermata del dispositivo mobile in modo che l'utente non deve scorrere per trovarli.
- **Consentire a un utente di rimuovere utenti da una chat di gruppo** Attiva questa impostazione per consentire a un utente di rimuovere altri utenti da una chat di gruppo. Questa funzione ti consente di continuare una chat con un gruppo più ridotto di persone senza perdere la cronologia della chat.
- **Abilitare le risposte suggerite**  Attivare questa impostazione per abilitare le risposte suggerite per i messaggi di chat.

> [!NOTE]
> Alcune di queste impostazioni, ad esempio l'uso di Giphy, possono anche essere configurate a livello di team dai proprietari del team e a livello di canale privato dai proprietari di canali privati.

### <a name="related-topics"></a>Argomenti correlati

- [Assegnare i criteri agli utenti in Teams](assign-policies.md)
- [Assegnare proprietari e membri dei team in Microsoft Teams](assign-roles-permissions.md)
