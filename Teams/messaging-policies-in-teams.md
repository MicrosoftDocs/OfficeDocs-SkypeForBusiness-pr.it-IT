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
description: In questo articolo verranno informazioni sui criteri di messaggistica e su come possono essere usati per controllare la messaggistica chat in Teams.
ms.openlocfilehash: f760fdf196bdeecf14e432445e619c968f66c081
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096120"
---
# <a name="manage-messaging-policies-in-teams"></a>Gestire i criteri di messaggistica in Teams

<!--- Add zone marker here--->

I criteri di messaggistica vengono usati per controllare quali funzionalità di messaggistica di chat e canale sono disponibili per gli utenti [(proprietari e membri)](assign-roles-permissions.md) in Microsoft Teams. È possibile usare i criteri globali (impostazione predefinita a livello di organizzazione) creati automaticamente oppure creare e assegnare criteri di messaggistica personalizzati.

Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato. È possibile modificare le impostazioni nei criteri globali oppure creare e assegnare uno o più criteri personalizzati per attivare o disattivare le caratteristiche desiderate.

## <a name="create-a-custom-messaging-policy"></a>Creare criteri di messaggistica personalizzati

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Criteri di messaggistica.**
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per il criterio.
4. Scegliere le impostazioni desiderate.
5. Fare clic su **Salva**.

Ad esempio, si supponga di voler assicurarsi che i messaggi inviati non siano eliminati o modificati. Creare un nuovo criterio personalizzato denominato "Mantieni messaggi inviati" e disattivare le impostazioni seguenti:

- I proprietari possono eliminare i messaggi inviati
- Gli utenti possono eliminare i messaggi inviati
- Gli utenti possono modificare i messaggi inviati

Assegnare quindi il criterio agli utenti.

## <a name="edit-a-messaging-policy"></a>Modificare un criterio di messaggistica

È possibile modificare il criterio globale e i criteri personalizzati creati. 

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Criteri di messaggistica.**
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
- **Conferme di lettura** Le conferme di lettura consentono al mittente di un messaggio di chat di ricevere una notifica quando il messaggio è stato letto dal destinatario in 1:1 e le chat di gruppo 20 persone o meno. Le conferme di lettura dei messaggi eliminano incertezze sulla lettura di un messaggio e migliorano la comunicazione del team. Tenere presente che le conferme di lettura non vengono acquisite nei report di eDiscovery.  
    - **Controllato dall'utente** Questo significa che gli utenti possono decidere se vogliono che le conferme di lettura siano ON o OFF. L'impostazione predefinita all'interno dell'app è ATTIVAta. Gli utenti possono quindi disattivarla.
    - **Su per tutti** Questo significa che tutti gli utenti del tenant avranno la funzionalità ATTIVAta senza alcuna opzione per disattivarla. Tenere presente che  quando si usa l'impostazione Attivata per tutti, l'unico modo per impostare le conferme per l'intero tenant è disporre di un solo criterio di messaggistica per l'intero tenant (il criterio predefinito denominato "Globale (impostazione predefinita a livello di organizzazione)") o che tutti i criteri di messaggistica nel tenant usino le stesse impostazioni per le ricevute. La caratteristica conferme di lettura è più efficace se è **abilitata per tutti**.
    - **Disattivato per tutti** Questo significa che la caratteristica è disabilitata e nessuno nel tenant ha conferme di lettura né può attivarla.
<a name="bkchat"> </a>

- **Chat**  Attivare questa impostazione se si vuole che gli utenti dell'organizzazione possano usare l'app Teams per chattare con altre persone.
- **Usare Giphys nelle conversazioni**  Se attivi questa opzione, gli utenti possono includere Giphys nelle conversazioni in chat con altre persone. Giphy è un database online e un motore di ricerca che consente agli utenti di cercare e condividere file GIF animati. A ogni Giphy viene assegnata una classificazione dei contenuti. Oltre a attivare questa impostazione, è necessario abilitare [](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) esperienze connesse facoltative per consentire a Giphys di accedere alle conversazioni.
- **Classificazione del contenuto Giphy**
    - **Nessuna restrizione** Questo significa che gli utenti saranno in grado di inserire qualsiasi Giphy nelle chat, indipendentemente dalla classificazione del contenuto.
    - **Moderato**  Questo significa che gli utenti saranno in grado di inserire Giphys nelle chat, ma saranno moderatamente limitati dai contenuti per adulti.
    - **Strict**  Questo significa che gli utenti saranno in grado di inserire Giphys nelle chat, ma saranno strettamente limitati dai contenuti per adulti.
- **Usare Memes nelle conversazioni** Se si attiva questa opzione, gli utenti possono includere Meme nelle conversazioni in chat con altre persone.
- **Usare gli adesivi nelle conversazioni** Se si attiva questa opzione, gli utenti possono includere adesivi nelle conversazioni in chat con altre persone.
- **Consenti anteprime URL** Usare questa impostazione per attivare o disattivare l'anteprima automatica degli URL nei messaggi.
- **Consentire agli utenti di tradurre i messaggi** Attivare questa impostazione per consentire agli utenti di tradurre automaticamente i messaggi di Teams nella lingua specificata dalle impostazioni della lingua personale per Microsoft 365 o Office 365.
- **Consentire lo strumento di lettura immersiva per la visualizzazione dei messaggi** Attivare questa impostazione per consentire agli utenti di visualizzare i messaggi in Microsoft Immersive Reader. Lo strumento di lettura immersiva è uno strumento di apprendimento che offre un'esperienza di lettura a schermo intero per aumentare la leggibilità del testo.
- **Inviare messaggi urgenti usando le notifiche di priorità** Se si attiva questa opzione, gli utenti possono inviare messaggi usando le [notifiche di priorità.](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462) Le notifiche di priorità notificano agli utenti ogni 2 minuti per  un periodo di 20 minuti o finché i messaggi contrassegnati come urgenti non vengono ricevuti e letti dal destinatario, massimizzando la probabilità che il messaggio si agiti in modo appropriato.
- **Creazione di messaggi audio** 
  > [!Important]
  > I messaggi audio non vengono acquisiti nei report di eDiscovery.
    - **Consentito nelle chat e nei canali** Questo significa che gli utenti possono lasciare i messaggi audio sia nelle chat che nei canali.
    - **Consentito solo nelle chat** Questo significa che gli utenti possono lasciare i messaggi audio nelle chat, ma non nei canali.
    - **Disabilitato** Questo significa che gli utenti non possono creare messaggi audio nelle chat o nei canali.  
- **Nei dispositivi mobili, visualizza i canali preferiti sopra le chat recenti** Abilitare questa impostazione per spostare i canali preferiti nella parte superiore dello schermo del dispositivo mobile in modo che un utente non sia necessario scorrere per trovarli.
- **Consentire a un utente di rimuovere utenti da una chat di gruppo** Attivare questa impostazione per consentire a un utente di rimuovere altri utenti da una chat di gruppo. Questa caratteristica consente di continuare una chat con un gruppo di persone più piccolo senza perdere la cronologia della chat.
- **Abilitare le risposte suggerite**  Attivare questa impostazione per abilitare le risposte suggerite per i messaggi di chat.

> [!NOTE]
> Alcune di queste impostazioni, ad esempio Giphys, possono essere configurate anche a livello di team dai proprietari del team e a livello di canale privato dai proprietari dei canali privati.

### <a name="related-topics"></a>Argomenti correlati

- [Assegnare i criteri agli utenti in Teams](assign-policies.md)
- [Assegnare proprietari e membri del team in Microsoft Teams](assign-roles-permissions.md)