---
title: Visite virtuali con Microsoft Teams e l’app Bookings
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Informazioni su come pianificare, gestire e condurre appuntamenti virtuali con l'app Bookings in Teams.
ms.openlocfilehash: a89eaa242cd62238d4e5c6c9d7a88f3a2e9ac62c
ms.sourcegitcommit: 39fc58109da6b4628ffb658f2c6b94099e0ab604
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "66103383"
---
# <a name="virtual-appointments-with-microsoft-teams-and-the-bookings-app"></a>Visite virtuali con Microsoft Teams e l’app Bookings

## <a name="overview"></a>Panoramica

[L'app Bookings](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5) in Microsoft Teams offre alle organizzazioni un modo semplice per pianificare e gestire appuntamenti virtuali per personale e partecipanti. Usarlo per pianificare appuntamenti come visite mediche, consulenze finanziarie, interviste, supporto clienti, accessori virtuali e consulenze, orari di ufficio per l'istruzione e altro ancora.

L'app Bookings consente di gestire facilmente richieste di pianificazione complesse di qualsiasi organizzazione. Le utilità di pianificazione possono gestire più calendari di reparto e del personale, oltre a comunicazioni con partecipanti interni ed esterni, da un'unica esperienza.

Gli appuntamenti virtuali si svolgono attraverso riunioni Microsoft Teams, che offrono solide funzionalità di videoconferenza. Ad esempio, un medico può condividere lo schermo e rivedere i risultati dei test con un paziente. In alternativa, un consulente bancario può richiedere firme elettroniche sui documenti, consentendogli di chiudere le transazioni in remoto.

Ogni appuntamento virtuale include un collegamento Teams riunione che viene inviato ai partecipanti tramite posta elettronica, dove possono partecipare facilmente da un Web browser o in Teams su qualsiasi dispositivo. I promemoria automatici tramite posta elettronica consentono di ridurre la non-mostra e di migliorare il coinvolgimento dei clienti e dei clienti.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4TQop]

Con Bookings si ottiene un'esperienza personalizzata per il proprio settore. Ecco alcuni esempi di come usarlo nell'organizzazione:

|Industria | Esempi |
|---------|---------|
|Servizi finanziari    |  Appuntamenti virtuali per vendite e servizi remoti<br/>Pianificare e gestire appuntamenti per responsabili delle relazioni bancarie, consulenti finanziari e rettificatori di crediti, solo per citarne alcuni, per servire i clienti con maggiore efficienza e praticità.  |
|Commercio al dettaglio   | Accessori virtuali e consulenze <br/>Pianifica e gestisci appuntamenti per i tuoi addetti alle vendite, gli esperti di prodotti e i consulenti di progettazione per condurre raccordi virtuali e consulenze con i clienti.   |
|Sanità   |  Appuntamenti virtuali per la cura dei pazienti <br/>Pianificare e gestire appuntamenti per i membri del team di assistenza per incontrare pazienti o altri operatori sanitari per discutere dell'assistenza medica.   |

Questo articolo offre una panoramica su come pianificare, gestire e condurre appuntamenti virtuali usando l'app Bookings in Teams.

## <a name="before-you-get-started"></a>Nozioni preliminari

Gli amministratori possono vedere [Gestire l'app Bookings in Teams](../bookings-app-admin.md) per informazioni sui prerequisiti per l'uso dell'app Bookings in Teams, su come controllare l'accesso a Bookings nell'organizzazione e sulle impostazioni consigliate per i criteri e gli amministratori.

Tenere presente che solo gli utilità di pianificazione dell'organizzazione devono avere l'app Bookings installata in Teams. Il personale che conduce o partecipa agli appuntamenti virtuali non ha bisogno dell'app. Partecipa agli appuntamenti dal calendario Teams o Outlook o usando il collegamento alla riunione nel messaggio e-mail di conferma della prenotazione.

## <a name="set-up-a-new-booking-calendar"></a>Configurare un nuovo calendario delle prenotazioni

### <a name="create-the-booking-calendar"></a>Creare il calendario delle prenotazioni

In Teams passare a **Bookings** >  **Attività iniziali** e quindi selezionare **Nuovo calendario delle prenotazioni**. Completare il modulo e assicurarsi di scegliere il tipo di azienda appropriato per l'organizzazione.

:::image type="content" source="../media/bookings-virtual-visits-new-booking-calendar.png" alt-text="Screenshot della schermata del nuovo calendario delle prenotazioni che mostra i tipi di attività":::

Se si è un'organizzazione di grandi dimensioni, è consigliabile creare più di un calendario delle prenotazioni se si vuole che i partecipanti ricevano un messaggio di prenotazione da un reparto specifico anziché dall'organizzazione complessiva.
Per altre informazioni, vedere [Creare un calendario di Bookings](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148).

> [!NOTE]
> Se non è la prima volta che si usa l'app Bookings o se si vuole usare un calendario delle prenotazioni esistente, in Bookings selezionare la freccia a discesa accanto al nome dell'organizzazione e quindi scegliere **Calendario delle prenotazioni esistente**. Da qui è possibile cercare quello desiderato.

### <a name="add-staff"></a>Aggiungere personale

Nel calendario delle prenotazioni passare ad **Altre opzioni** (...) > **Impostazioni** e quindi selezionare **Personale**. Aggiungere membri del personale e assegnare un ruolo a ogni persona aggiunta. È possibile aggiungere fino a 100 membri del personale a un calendario delle prenotazioni.

L'app Bookings si integra con Outlook. Dopo aver aggiunto il personale, sarà possibile visualizzare la disponibilità del calendario di quella persona e pianificare le prenotazioni. Per altre informazioni, vedere [Aggiungere personale e visualizzare un calendario di Bookings](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0).  

### <a name="create-appointment-types"></a>Creare tipi di appuntamento

Creare tipi di appuntamento specifici per rappresentare i servizi offerti dall'organizzazione e personalizzare l'esperienza di prenotazione. Gli scheduler possono quindi usare il tipo di appuntamento per pianificare un appuntamento.

Nel calendario delle prenotazioni passare ad **Altre opzioni** (...) > **Impostazioni**, selezionare **Tipi di appuntamento** e quindi Selezionare **Aggiungi tipo di appuntamento**. Immettere un nome&mdash;, ad esempio apertura conto, rinnovo di prescrizione, consulenza per il prestito, preparazione&mdash;fiscale e altre informazioni e impostazioni desiderate.

Le informazioni aggiunte vengono incluse nel messaggio di conferma inviato ai partecipanti ogni volta che viene prenotato questo tipo di appuntamento. È possibile impostare promemoria tramite posta elettronica e altre opzioni, ad esempio se i partecipanti possono [partecipare da un browser desktop o per dispositivi mobili](browser-join.md) senza dover scaricare Teams.

Gli amministratori di Bookings possono collegare fino a quattro moduli che i partecipanti possono compilare ogni volta che viene prenotato questo tipo di appuntamento. Ad esempio, è possibile richiedere ai partecipanti di completare un modulo di registrazione prima che partecipino a un appuntamento. Per collegare un modulo, scegliere **Collega un modulo**. Immettere l'URL del modulo e quindi scegliere **Collegamento**. Se è la prima volta che si collega una maschera, viene chiesto di creare un gruppo di Microsoft 365 per archiviare le maschere. Scegliere **Crea gruppo** per creare il gruppo. Questa operazione deve essere eseguita una sola volta per il calendario delle prenotazioni.

Quando si usano i moduli, tenere presente che:

- Per apportare modifiche a un modulo già collegato a un tipo di appuntamento, selezionare il modulo nel tipo di appuntamento o nel gruppo di Microsoft 365 in [https://forms.office.com](https://forms.office.com).
- Il caricamento di file in moduli che contengono una [domanda di caricamento di file](https://support.microsoft.com/office/add-questions-that-allow-for-file-uploads-6a75a658-c02b-450e-b119-d068f3cba4cf) è supportato quando tutti i partecipanti provengono dalla stessa organizzazione.

Quando un'utilità di pianificazione usa il tipo di appuntamento per pianificare un appuntamento, può quindi scegliere di includere il modulo, rimuoverlo o aggiungere altri moduli collegati al tipo di appuntamento. I partecipanti devono compilare il modulo prima di partecipare all'appuntamento.

> [!NOTE]
> Le informazioni fornite dai pazienti in Forms nell'ambito dei servizi di prenotazione o appuntamenti virtuali necessari per la continuità o la conservazione delle cartelle cliniche devono essere scaricate, copiate e/o annoate direttamente in tali record. Tale servizio non costituisce né una cartella clinica legale né un registro designato.

Per altre informazioni, vedere [Creare un tipo di appuntamento](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887).

## <a name="schedule-an-appointment"></a>Pianificare un appuntamento

Nel calendario delle prenotazioni selezionare **Nuova prenotazione**. Selezionare un tipo di appuntamento e quindi inserire le informazioni pertinenti.

Sono incluse le informazioni di contatto dei partecipanti, il membro del personale che fornirà il servizio, le note interne che possono essere visualizzate solo dal personale, i promemoria tramite posta elettronica e se il partecipante può partecipare da un browser per dispositivi mobili. Se un modulo è collegato al tipo di appuntamento, è possibile scegliere di includerlo, rimuoverlo o aggiungere altri moduli collegati.

La conferma inviata al partecipante include il collegamento alla riunione e un allegato in modo che possa aggiungere l'appuntamento virtuale al proprio calendario. Il personale riceve anche un messaggio e-mail di conferma e un invito alla riunione. Se nell'appuntamento è stato incluso un modulo, gli amministratori e gli programmatori di Bookings possono verificare se il modulo è stato completato dal partecipante prima dell'appuntamento e possono visualizzare la risposta del partecipante.

Per altre informazioni, vedere [Pianificare una prenotazione nell'app Teams Bookings](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f).

## <a name="conduct-an-appointment"></a>Condurre un appuntamento

Nel calendario Teams o Outlook passare alla prenotazione e quindi selezionare **Partecipa** o il collegamento Teams riunione. Controlla le impostazioni audio e video e quindi seleziona **Partecipa ora**. Per altre informazioni, vedere [Condurre un appuntamento di Bookings](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd).

## <a name="monitor-appointments-and-get-real-time-status-updates"></a>Monitorare gli appuntamenti e ottenere aggiornamenti di stato in tempo reale

La [visualizzazione coda](https://support.microsoft.com/office/queue-view-in-bookings-3eea2840-a1e0-4bcd-8e09-d3cf51c184d6) in Bookings offre al personale una dashboard per monitorare tutti gli appuntamenti virtuali della giornata, con aggiornamenti in tempo reale. Per visualizzare la coda, vai alla scheda **Coda** in Bookings.

:::image type="content" source="../media/bookings-virtual-visits-queue.png" alt-text="Screenshot della visualizzazione coda nell'app Bookings in Teams" lightbox="../media/bookings-virtual-visits-queue.png":::

Dalla coda, gli scheduler possono aggiungere una nuova prenotazione, visualizzare i dettagli relativi agli appuntamenti e vedere gli stati degli appuntamenti durante la giornata. Quando un paziente entra nella sala d'attesa, lo stato cambia e viene visualizzato e monitorato il tempo di attesa. La visualizzazione viene aggiornata automaticamente con aggiornamenti contraddistinti dal colore, in modo da identificare facilmente le modifiche.

Il personale può anche partecipare e gestire gli appuntamenti direttamente dalla coda.

> [!NOTE]
> Attualmente, l'app Bookings supporta l'aggiunta di un massimo di 100 membri del personale per ogni calendario di prenotazione. Se sono stati usati Graph API per configurare e aggiungere personale a un calendario delle prenotazioni, questo limite potrebbe non essere applicato. In questo scenario, la scheda **Coda** non sarà in grado di eseguire il rendering del contenuto per i calendari con più di 100 membri del personale. Per un'esperienza ottimale, è consigliabile aggiungere non più di 100 membri del personale a un calendario delle prenotazioni. Stiamo lavorando per risolvere questa limitazione nelle versioni future.

## <a name="additional-capabilities-with-the-bookings-web-app"></a>Funzionalità aggiuntive con l'app Web Bookings

L'app Web Bookings offre funzionalità aggiuntive. Ad esempio, è possibile pubblicare una pagina di prenotazione self-service online in cui gli utenti possono pianificare appuntamenti con il personale. Per accedere all'app Web Bookings, passare ad **Altre opzioni** (...) **>'app Web Apri Bookings**.

Per altre informazioni, vedi [Microsoft Bookings](/microsoft-365/bookings/bookings-overview).

## <a name="get-insight-into-virtual-appointments-usage"></a>Ottenere informazioni dettagliate sull'utilizzo degli appuntamenti virtuali

Il [report Sull'utilizzo delle visite virtuali](../teams-analytics-and-reports/virtual-visits-usage-report.md) nell'interfaccia di amministrazione di Microsoft Teams offre agli amministratori una panoramica di Teams attività degli appuntamenti virtuali nell'organizzazione. Il report mostra analisi dettagliate per gli appuntamenti virtuali, inclusi gli appuntamenti di Bookings.

È possibile visualizzare metriche chiave come il tempo di attesa della sala di attesa e la durata dell'appuntamento. Usare queste informazioni per ottenere informazioni approfondite sulle tendenze di utilizzo e ottimizzare gli appuntamenti virtuali per ottenere risultati aziendali migliori.

## <a name="related-articles"></a>Articoli correlati

- [Gestire l'esperienza di partecipazione per Teams appuntamenti virtuali nei browser per dispositivi mobili](browser-join.md)

- [report sull'utilizzo delle visite virtuali Teams](../teams-analytics-and-reports/virtual-visits-usage-report.md)

- [Attività iniziali con Teams per le organizzazioni sanitarie](healthcare/teams-in-hc.md)

- [App Bookings nella documentazione della Guida di Teams](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Bookings)
