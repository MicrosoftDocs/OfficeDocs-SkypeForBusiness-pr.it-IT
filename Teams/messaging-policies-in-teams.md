---
title: Gestire i criteri di messaggistica in teams
ms.author: tonysmit
author: tonysmit
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
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
description: Informazioni sui criteri di messaggistica e sul modo in cui possono essere usati per controllare la messaggistica di chat in teams.
ms.openlocfilehash: bc69b44b47cf068bdea17ed661a873b90af44de5
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "37569277"
---
# <a name="manage-messaging-policies-in-teams"></a>Gestire i criteri di messaggistica in teams

<!--- Add zone marker here--->

I criteri di messaggistica vengono usati per controllare quali funzionalità di messaggistica chat e canale sono disponibili per gli utenti in Microsoft teams. È possibile usare i criteri predefiniti creati automaticamente o creare uno o più criteri di messaggistica personalizzati per gli utenti dell'organizzazione. Dopo aver creato un criterio, è possibile assegnarlo a un utente o a un gruppo di utenti dell'organizzazione.

Per impostazione predefinita, viene creato un criterio denominato globale (impostazione predefinita a livello di organizzazione). Per impostazione predefinita, a tutti gli utenti dell'organizzazione verrà assegnato questo criterio di messaggistica. È possibile apportare modifiche a questo criterio o creare uno o più criteri personalizzati e assegnarvi gli utenti. Quando si creano criteri personalizzati, è possibile consentire o impedire che determinate funzionalità siano disponibili per gli utenti e quindi assegnarle a uno o più utenti che avranno bisogno delle impostazioni applicate. 

## <a name="change-or-create-a-messaging-policy"></a>Modificare o creare un criterio di messaggistica

È possibile gestire facilmente i criteri di messaggistica nell'interfaccia di amministrazione dihttp://admin.teams.microsoft.com) Microsoft Teams (eseguendo l'accesso con le credenziali di amministratore e scegliendo **criteri di messaggistica** nel riquadro di spostamento sinistro. Per modificare i criteri di messaggistica predefiniti esistenti per l'organizzazione, selezionare la riga **globale (org-Wide default)** e quindi apportare le modifiche desiderate. Per creare un nuovo criterio di messaggistica personalizzato, selezionare **nuovo criterio**, assegnare un nome al nuovo criterio e quindi selezionare le impostazioni. Al termine, scegliere **Salva** .

Ad esempio, supponiamo di voler verificare che i messaggi inviati non vengano eliminati o modificati. Si creerebbe un nuovo criterio personalizzato denominato "Mantieni messaggi inviati" e si spengono le impostazioni seguenti:

- I proprietari possono eliminare i messaggi inviati
- Gli utenti possono eliminare i messaggi inviati
- Gli utenti possono modificare i messaggi inviati

Assegna quindi il criterio agli utenti.

> [!NOTE] 
> A un utente può essere assegnato solo un criterio di messaggistica alla volta.
 
## <a name="assign-a-messaging-policy-to-a-user"></a>Assegnare un criterio di messaggistica a un utente

Se crei un criterio di messaggistica personalizzato, sarà attivo solo per un utente se il criterio viene assegnato all'utente. Per assegnare un criterio personalizzato a un utente, accedere all'interfaccia di amministrazione di Microsoft teams, scegliere **utenti** nel riquadro di spostamento sinistro e selezionare l'utente a cui si vuole assegnare il criterio. Nella pagina dell'utente scegliere **modifica** accanto a **criteri assegnati**. Nel riquadro **modifica criteri utente** , quindi, in **criteri di messaggistica**Selezionare i criteri di messaggistica nell'elenco a discesa e selezionare **Salva**. È anche possibile modificare le impostazioni dall'elenco degli utenti. A questo scopo, seleziona l'utente facendo clic a sinistra del nome visualizzato dell'utente. Selezionare **Modifica impostazioni**. Nel riquadro **Modifica impostazioni** , in **criteri di messaggistica**, selezionare il criterio nell'elenco a discesa e quindi selezionare **Salva**.

Se si applica un criterio a più utenti, selezionare ognuno di essi facendo clic a sinistra del nome utente e quindi selezionare **Modifica impostazioni**. Nel riquadro **Modifica impostazioni** , in **criteri di messaggistica**, selezionare i criteri nell'elenco a discesa e quindi scegliere **Salva**.

È anche possibile assegnare un criterio di messaggistica a uno o più utenti, come indicato di seguito:

1. Accedere ai > **criteri di messaggistica**dell'interfaccia di **amministrazione di Microsoft teams**.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio.
3. Selezionare **Gestisci utenti**.
4. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o per nome utente, selezionare il nome e quindi fare clic su **Aggiungi**. Ripetere questo passaggio per ogni utente che si vuole aggiungere.
5. Al termine dell'aggiunta di utenti, selezionare **Salva**.

> [!NOTE]
> Non è possibile eliminare un criterio se gli utenti sono assegnati. Devi prima assegnare un criterio diverso a tutti gli utenti interessati, quindi puoi eliminare il criterio originale.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Impostazioni dei criteri di messaggistica

Usare le impostazioni seguenti per modificare i criteri di messaggistica globale o creare un nuovo criterio personalizzato:

- **I proprietari possono eliminare i messaggi inviati**  Usare questa impostazione per consentire ai proprietari di eliminare i messaggi inviati dagli utenti in chat.
- **Gli utenti possono eliminare i messaggi inviati** Usare questa impostazione per consentire agli utenti di eliminare i messaggi inviati in chat.
- **Gli utenti possono modificare i messaggi inviati** Usare questa impostazione per consentire agli utenti di modificare i messaggi inviati in chat.
- **Conferme di lettura** Conferme di lettura consentire al mittente di un messaggio di chat di ricevere una notifica quando il messaggio è stato letto dal destinatario in 1:1 e raggruppare le chat di 20 persone o meno. Le conferme di lettura dei messaggi eliminano in maniera non sicura se un messaggio è stato letto e migliorano la comunicazione del team.  
    - **Utente controllato** Ciò significa che gli utenti possono decidere se vogliono ricevere le conferme di lettura. L'impostazione predefinita all'interno dell'app è attivata. Gli utenti possono quindi disattivarli. 
    - **Attiva per tutti** Questo significa che tutti gli utenti del tenant avranno la funzionalità con nessuna opzione per disattivarla. Tenere presente che quando si usa l'impostazione **attiva per tutti** , l'unico modo per impostare le conferme per l'intero tenant è quello di avere un solo criterio di messaggistica per l'intero tenant (il criterio predefinito denominato "globale (impostazione predefinita per l'intera organizzazione)") o per avere tutti i criteri di messaggistica in il tenant usa le stesse impostazioni per i conferme. La caratteristica delle conferme di lettura è più efficace quando la funzionalità è abilitata per **tutti**.
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
- **Consentire agli utenti di tradurre i messaggi** Attivare questa impostazione per consentire agli utenti di tradurre automaticamente i messaggi di teams nella lingua specificata dalle impostazioni della lingua personale per Office 365.
- **Consentire all'utilità di lettura immersiva di visualizzare i messaggi** Attivare questa impostazione per consentire agli utenti di visualizzare i messaggi in Microsoft immersive Reader. Immersive Reader è uno strumento di apprendimento che offre un'esperienza di lettura a schermo intero per aumentare la leggibilità del testo.
- **Gli utenti possono inviare notifiche <a name="urgent-message">prioritarie</a> ** Se si attiva questa opzione, gli utenti possono inviare un messaggio che usa le notifiche prioritarie. Le notifiche prioritarie avvisano gli utenti ogni 2 minuti per un periodo di 20 minuti o finché i messaggi non vengono raccolti e letti dal destinatario, massimizzando la probabilità che il messaggio venga raccolto e agito in modo tempestivo.   [!INCLUDE [pri-message-offer](includes/pri-message-offer.md)]
- **Creazione di messaggi vocali** 
    - **Consentito in chat e canali** Ciò significa che gli utenti possono abbandonare i messaggi vocali sia in chat che in canali.
    - **Consentito solo nelle chat** Ciò significa che gli utenti possono abbandonare i messaggi vocali nelle chat, ma non nei canali.
    - **Disabilitata** Ciò significa che gli utenti non possono creare messaggi vocali in chat o canali.  
- **Nei dispositivi mobili, visualizzare i canali preferiti sopra le chat recenti** Abilitare questa impostazione per spostare i canali preferiti nella parte superiore della schermata del dispositivo mobile in modo che l'utente non debba scorrere per trovarli. 
- **Consentire a un utente di rimuovere utenti da una chat di gruppo** Attivare questa impostazione per consentire a un utente di rimuovere altri utenti da una chat di gruppo. Questa funzionalità consente di continuare una chat con un gruppo di persone più piccolo senza perdere la cronologia chat.

### <a name="related-topics"></a>Argomenti correlati
[Criteri di riunione in teams](meeting-policies-in-teams.md)
