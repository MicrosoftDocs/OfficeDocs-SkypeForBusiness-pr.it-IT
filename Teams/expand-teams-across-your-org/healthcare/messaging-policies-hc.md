---
title: Introduzione alla messaggistica sicura per le organizzazioni sanitarie
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Introduzione alla messaggistica sicura per le organizzazioni sanitarie
ms.openlocfilehash: d53a445cd7c13001fee8f365bc5d897a065de398
ms.sourcegitcommit: f735495849f02e0ea23c7d6f250e9c0656daeea1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2019
ms.locfileid: "36184102"
---
# <a name="get-started-with-secure-messaging-for-healthcare-organizations"></a>Introduzione alla messaggistica sicura per le organizzazioni sanitarie

I criteri di messaggistica vengono usati per controllare quali funzionalità di messaggistica chat e canale sono disponibili per gli utenti di Microsoft teams e fanno parte della distribuzione complessiva di messaggistica sicura per organizzazioni sanitarie come ospedali, cliniche o uffici medici, dove è fondamentale avere un messaggio prelevato e agito in modo tempestivo, così come si sa quando vengono letti messaggi cruciali.

È possibile usare i criteri predefiniti o creare uno o più criteri di messaggistica personalizzati per gli utenti dell'organizzazione. Dopo aver creato un criterio, verrà assegnato a un utente o a un gruppo di utenti dell'organizzazione. Ad esempio, puoi scegliere di consentire solo a determinati ruoli di lavoro di usare queste funzionalità (solo medici e infermieri) e altri lavoratori (come gli addetti alle pulizie o il personale della cucina) per ottenere un set di caratteristiche più limitato. Per decidere autonomamente ciò che serve alla propria organizzazione, le indicazioni sono al massimo un suggerimento.

I criteri possono essere facilmente gestiti nell'interfaccia di [amministrazione di Microsoft teams](http://admin.teams.microsoft.com) accedendo con le credenziali di amministratore e scegliendo i **criteri di messaggistica** nel riquadro di spostamento sinistro.

 ![Screenshot della pagina Criteri di messaggistica](../../media/messaging-policies-image1.png)

Per modificare i criteri di messaggistica predefiniti esistenti per l'organizzazione, fare clic sulla riga **globale (org-Wide default)** e quindi apportare le modifiche desiderate. Per creare nuovi criteri di messaggistica personalizzati, fare clic su **nuovo criterio** e selezionare le impostazioni. Al termine, scegliere **Salva** .

![Screenshot delle impostazioni dei criteri di messaggistica](../../media/hc-message-policy.png)

Le impostazioni seguenti sono di particolare interesse per le applicazioni sanitarie e devono essere considerate quando si progettano criteri personalizzati usati nel campo dell'assistenza sanitaria:

## <a name="read-receipts"></a>Conferme di lettura

- ![Icona del numero 1, facendo riferimento a un callout nello screenshot](../../media/sfbcallout1.png) precedente **leggere** le conferme di lettura consente al mittente di un messaggio di chat di sapere quando il messaggio è stato letto dal destinatario in 1:1 e raggruppare le chat di 20 persone o meno. Usare questa impostazione per specificare se le conferme di lettura sono controllate dall'utente, attivate per tutti o disattivate per tutti. Le conferme di lettura dei messaggi sono importanti per le organizzazioni sanitarie perché eliminano in maniera non sicura se un messaggio è stato letto.

  Per le applicazioni sanitarie, scegliere **utente controllato** o attivato **per tutti**. Tenere presente che quando si usa l'impostazione **attiva per tutti** , l'unico modo per impostare le conferme per l'intero tenant è quello di avere un solo criterio di messaggistica per l'intero tenant (il criterio predefinito denominato "globale (impostazione predefinita per l'intera organizzazione)") o per avere tutti i criteri di messaggistica in il tenant usa le stesse impostazioni per i conferme. La caratteristica delle conferme di lettura è più efficace quando la funzionalità è abilitata per **tutti**.

    *Esempio di utilizzo senza conferme di lettura:* Jakob Roth, un paziente ad alto rischio, è ammesso in ospedale.Sofia Krause è un'infermiera che lavora come parte del team interdisciplinare (IDT) di operatori sanitari, inclusi diversi specialisti, viene assegnato come coordinatore di assistenza primaria responsabile di questo paziente.  Sofia invia posta elettronica e altri messaggi istantanei a gruppi di infermieri e medici che usano diversi client e app di messaggistica e spesso non riceve alcuna risposta o indica se un messaggio è stato letto dai membri del team. A causa di processi di comunicazione aggrovigliati, il farmaco di Jakob viene applicato in stato di malessere e il suo soggiorno in ospedale viene esteso.

    *Esempio di utilizzo con le conferme di lettura:* Jakob Roth, un paziente ad alto rischio, è ammesso in ospedale.Sofia Krause è un'infermiera che lavora come parte del team interdisciplinare (IDT) di operatori sanitari, inclusi diversi specialisti, viene assegnato come coordinatore di assistenza primaria responsabile di questo paziente.  Sofia avvia una chat di gruppo con un set di medici e altri infermieri che lavoreranno con il paziente per coordinare le cure e avviare un triage di emergenza.Gli infermieri e i medici comunicano e collaborano al piano di assistenza del paziente durante il processo di coordinamento delle cure.  I messaggi importanti e urgenti vengono inviati tramite 1:1 e conversazioni di chat di gruppo. Sofia usa la funzionalità di lettura ricevute per determinare se i messaggi inviati che richiedono il supporto vengono recapitati e letti dai medici o infermieri mirati. I risultati del paziente di Jakob sono quasi ottimali e torna a casa prima perché il suo team di assistenza comunica senza intoppi.

## <a name="priority-notifications"></a>Notifiche prioritarie

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

[!INCLUDE [pri-message-offer](../../includes/pri-message-offer.md)]

- ![Icona del numero 2, facendo riferimento a un callout nella schermata](../../media/sfbcallout2.png) precedente **gli utenti possono inviare notifiche prioritarie** un utente può contrassegnare un messaggio come "urgente" quando si inviano messaggi di chat ad altri utenti. Questa caratteristica aiuta il personale ospedaliero ad avvisarsi l'un l'altro quando un incidente critico richiede la sua attenzione. A differenza dei normali messaggi "importanti", le notifiche prioritarie avvisano gli utenti ogni due minuti per un massimo di 20 minuti o finché il messaggio non viene prelevato e letto dal destinatario, massimizzando la probabilità che il messaggio venga agito in modo tempestivo.

  Un amministratore può abilitare o disabilitare la possibilità per gli utenti assegnati a questo criterio di inviare notifiche prioritarie. Questa caratteristica è attivata per impostazione predefinita. Il destinatario del messaggio di priorità potrebbe non avere lo stesso criterio di messaggistica e non avrà l'opzione di disabilitare la ricezione dei messaggi prioritari. Per le applicazioni sanitarie, è consigliabile abilitare la funzionalità per almeno alcuni utenti, ma è necessario determinare quali.

  *Esempio di utilizzo:* Sofia Krause sta riammettendo un paziente ad alto rischio, Jakob Roth. Manuela Carstens, un medico, è il medico di primo interesse per questo paziente.  Sofia Invia un messaggio a Manuela con una notifica prioritaria che chiede assistenza immediata per la valutazione di Jakob.  Il telefono di Manuela riceve il messaggio ma Manuela non sente la vibrazione del telefono e non risponde. I team notificano nuovamente Manuela e continueranno a essere ripetutamente avvisati finché non legge il messaggio. Se sono abilitate anche le conferme di lettura, Sofia può tenere presente che il messaggio è stato letto da Manuela, anche prima che Manuela decida come rispondere.

## <a name="related-topics"></a>Argomenti correlati

- [Gestire i criteri di messaggistica in teams](../../messaging-policies-in-teams.md)
- [Iniziare a usare team per organizzazioni sanitarie](teams-in-hc.md)
