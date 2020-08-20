---
title: Gestire i criteri di messaggistica in teams
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
description: In questo articolo vengono illustrati i criteri di messaggistica e il modo in cui possono essere usati per controllare la messaggistica di chat in teams.
ms.openlocfilehash: 0a548eee32fc196157b6a363dd0427b187e52112
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814182"
---
# <a name="manage-messaging-policies-in-teams"></a>Gestire i criteri di messaggistica in teams

<!--- Add zone marker here--->

I criteri di messaggistica vengono usati per controllare quali funzionalità di messaggistica chat e canale sono disponibili per [gli utenti (proprietari e membri)](assign-roles-permissions.md) in Microsoft teams. Puoi usare il criterio globale (predefinito per l'intera organizzazione) creato automaticamente o crea e assegna criteri di messaggistica personalizzati.

Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato. È possibile modificare le impostazioni dei criteri globali oppure creare e assegnare uno o più criteri personalizzati per attivare o disattivare le caratteristiche desiderate.

## <a name="create-a-custom-messaging-policy"></a>Creare criteri di messaggistica personalizzati

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vedere **criteri di messaggistica**.
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per il criterio.
4. Scegliere le impostazioni desiderate.
5. Fare clic su **Salva**.

Ad esempio, supponiamo di voler verificare che i messaggi inviati non vengano eliminati o modificati. Creare un nuovo criterio personalizzato denominato "Mantieni messaggi inviati" e disattivare le impostazioni seguenti:

- I proprietari possono eliminare i messaggi inviati
- Gli utenti possono eliminare i messaggi inviati
- Gli utenti possono modificare i messaggi inviati

Assegna quindi il criterio agli utenti.

## <a name="edit-a-messaging-policy"></a>Modificare i criteri di messaggistica

È possibile modificare i criteri globali e i criteri personalizzati creati. 

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vedere **criteri di messaggistica**.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.
3. Da qui apportare le modifiche desiderate.
4. Fare clic su **Salva**.

## <a name="assign-a-custom-messaging-policy-to-users"></a>Assegnare criteri di messaggistica personalizzati agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

A un utente può essere assegnato solo un criterio di messaggistica alla volta.

> [!NOTE]
> Non è possibile eliminare un criterio a cui sono utenti. È prima di tutto necessario assegnare un criterio diverso a tutti gli utenti interessati, quindi sarà possibile eliminare il criterio originale.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Impostazioni dei criteri di messaggistica

Ecco le impostazioni dei criteri di messaggistica che è possibile configurare.

- **I proprietari possono eliminare i messaggi inviati**  Usare questa impostazione per consentire ai proprietari di eliminare i messaggi inviati dagli utenti in chat.
- **Gli utenti possono eliminare i messaggi inviati** Usare questa impostazione per consentire agli utenti di eliminare i messaggi inviati in chat.
- **Gli utenti possono modificare i messaggi inviati** Usare questa impostazione per consentire agli utenti di modificare i messaggi inviati in chat.
- **Conferme di lettura** Conferme di lettura consentire al mittente di un messaggio di chat di ricevere una notifica quando il messaggio è stato letto dal destinatario in 1:1 e raggruppare le chat di 20 persone o meno. Le conferme di lettura dei messaggi eliminano in maniera non sicura se un messaggio è stato letto e migliorano la comunicazione del team. Tieni presente che le conferme di lettura non vengono acquisite in eDiscovery Reporting.  
    - **Utente controllato** Ciò significa che gli utenti possono decidere se vogliono ricevere le conferme di lettura. L'impostazione predefinita all'interno dell'app è attivata. Gli utenti possono quindi disattivarli.
    - **Attiva per tutti** Questo significa che tutti gli utenti del tenant avranno la funzionalità con nessuna opzione per disattivarla. Tenere presente che quando si usa l'impostazione **per tutti gli utenti** , l'unico modo per impostare le conferme per l'intero tenant è quello di avere solo un criterio di messaggistica per l'intero tenant (il criterio predefinito denominato "globale (impostazione predefinita)") o per avere tutti i criteri di messaggistica nel tenant usano le stesse impostazioni per le conferme. La caratteristica delle conferme di lettura è più efficace quando la funzionalità è abilitata per **tutti**.
    - **Disattivato per tutti** Questo significa che la caratteristica è disabilitata e che nessuno nel tenant ha conferme di lettura né può attivarlo.
<a name="bkchat"> </a>

- **Chat**  Attivare questa impostazione se si vuole che gli utenti dell'organizzazione possano usare l'app teams per chattare con altre persone.
- **Usare giphy nelle conversazioni**  Se si attiva questa opzione, gli utenti possono includere Giphy nelle conversazioni di chat con altre persone. Giphy è un database online e un motore di ricerca che consente agli utenti di cercare e condividere file GIF animati. A ogni Giphy viene assegnata una valutazione del contenuto.
- **Valutazione del contenuto di Giphy**
    - **Nessuna restrizione** Ciò significa che gli utenti saranno in grado di inserire qualsiasi Giphy in chat indipendentemente dalla valutazione del contenuto.
    - **Moderato**  Ciò significa che gli utenti saranno in grado di inserire Giphy in chat, ma saranno limitati moderatamente dal contenuto per adulti.
    - **Strict**  Ciò significa che gli utenti saranno in grado di inserire Giphy in chat, ma saranno rigorosamente limitati da contenuti per adulti.
- **Usare memi nelle conversazioni** Se si attiva questa opzione, gli utenti possono includere memi in conversazioni di chat con altre persone.
- **Usare gli adesivi nelle conversazioni** Se si attiva questa opzione, gli utenti possono includere adesivi nelle conversazioni di chat con altre persone.
- **Consenti anteprime URL** Usare questa impostazione per attivare o disattivare l'anteprima automatica degli URL nei messaggi.
- **Consentire agli utenti di tradurre i messaggi** Attivare questa impostazione per consentire agli utenti di tradurre automaticamente i messaggi di teams nella lingua specificata dalle impostazioni della lingua personale per Microsoft 365 o Office 365.
- **Consentire all'utilità di lettura immersiva di visualizzare i messaggi** Attivare questa impostazione per consentire agli utenti di visualizzare i messaggi in Microsoft immersive Reader. Immersive Reader è uno strumento di apprendimento che offre un'esperienza di lettura a schermo intero per aumentare la leggibilità del testo.
- **Inviare messaggi urgenti con le notifiche prioritarie** Se si attiva questa opzione, gli utenti possono inviare messaggi usando le [notifiche prioritarie](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462). Le notifiche prioritarie avvisano gli utenti ogni 2 minuti per un periodo di 20 minuti o finché i messaggi contrassegnati come *urgenti* vengono prelevati e letti dal destinatario, massimizzando la probabilità che il messaggio venga agito in modo tempestivo.
- **Creazione di messaggi audio** 
  > [!Important]
  > I messaggi audio non vengono acquisiti in eDiscovery Reporting.
    - **Consentito in chat e canali** Ciò significa che gli utenti possono uscire da messaggi audio sia in chat che in canali.
    - **Consentito solo nelle chat** Ciò significa che gli utenti possono abbandonare i messaggi audio in chat, ma non nei canali.
    - **Disabilitata** Ciò significa che gli utenti non possono creare messaggi audio in chat o canali.  
- **Nei dispositivi mobili, visualizzare i canali preferiti sopra le chat recenti** Abilitare questa impostazione per spostare i canali preferiti nella parte superiore della schermata del dispositivo mobile in modo che l'utente non debba scorrere per trovarli.
- **Consentire a un utente di rimuovere utenti da una chat di gruppo** Attivare questa impostazione per consentire a un utente di rimuovere altri utenti da una chat di gruppo. Questa funzionalità consente di continuare una chat con un gruppo di persone più piccolo senza perdere la cronologia chat.
- **Abilitare le risposte suggerite**  Attivare questa impostazione per abilitare le risposte suggerite per i messaggi di chat.

> [!NOTE]
> Alcune di queste impostazioni, ad esempio l'uso di Giphy, possono essere configurate anche a livello di team dai proprietari del team e a livello di canale privato da proprietari di canali privati.

### <a name="related-topics"></a>Argomenti correlati

- [Assegnare criteri agli utenti in teams](assign-policies.md)
- [Assegnare proprietari e membri del team in Microsoft Teams](assign-roles-permissions.md)
