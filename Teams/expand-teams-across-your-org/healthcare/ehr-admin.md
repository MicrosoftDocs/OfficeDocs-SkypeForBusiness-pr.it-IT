---
title: Visite virtuali con Teams - Integrazione in Epic EHR
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
  - Microsoft Teams
  - Microsoft Cloud for Healthcare
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - M365-collaboration
  - Teams_ITAdmin_Healthcare
  - microsoftcloud-healthcare
  - m365solution-healthcare
  - m365solution-scenario
appliesto:
  - Microsoft Teams
ms.reviewer: ansantam
description: Informazioni su come integrare il connettore Teams EHR per consentire agli operatori sanitari dell'organizzazione di effettuare visite virtuali con pazienti o altri provider in Teams direttamente dal sistema Epic EHR.
---

# <a name="virtual-visits-with-teams---integration-into-epic-ehr"></a>Visite virtuali con Teams - Integrazione in Epic EHR

Il connettore Microsoft Teams Electronic Health Record (EHR) consente ai medici di avviare facilmente una visita virtuale del paziente o una consultazione con un altro provider in Microsoft Teams direttamente dal sistema Epic EHR. Basato sul cloud Microsoft 365, Teams consente una collaborazione e una comunicazione semplici e sicure con strumenti di chat, video, voce e assistenza sanitaria in un unico hub che supporta la conformità con HIPAA, la certificazione HITECH e altro ancora.

La piattaforma di comunicazione e collaborazione di Teams consente ai medici di ridurre facilmente l'ingombro dei sistemi frammentati, in modo che possano concentrarsi sulla fornitura delle migliori cure possibili. Con il Teams EHR è possibile:

- Avvia Teams visite virtuali dal sistema Epic EHR con un flusso di lavoro clinico integrato.
- Consenti ai pazienti di partecipare Teams visite virtuali dal portale dei pazienti o tramite SMS.
- Supportare altri scenari di visite virtuali, tra cui più partecipanti, visite di gruppo e servizi di interprete.
- Scrivere di nuovo i metadati nel sistema EHR Teams le visite virtuali da registrare quando i partecipanti si connettono, si disconnettino e abilitano il controllo automatico e la conservazione dei record.
- Visualizza report sui dati di consumo e informazioni personalizzabili sulla qualità delle chiamate per le visite connesse a EHR.

Guarda questo video per una panoramica su come gestire le visite virtuali dal portale EHR.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

Questo articolo descrive come configurare e configurare il connettore Teams EHR per l'integrazione con la piattaforma Epic nell'organizzazione sanitaria. Offre anche una panoramica dell'esperienza Teams delle visite virtuali dal sistema Epic EHR.

## <a name="before-you-begin"></a>Prima di iniziare

Prima di iniziare, è necessario eseguire alcune operazioni per preparare l'integrazione.

### <a name="get-familiar-with-the-integration-process"></a>Acquisire familiarità con il processo di integrazione

Esaminare le informazioni seguenti per comprendere il processo di integrazione generale.

:::image type="content" source="media/ehr-connector-epic-flow.png" alt-text="Immagine che riepiloga i passaggi del processo di integrazione generale.":::

||||||
|---------|---------|---------|---------|---------|
|**Azione**: richiedi [l'accesso all'app Teams app](#request-access-to-the-teams-app). <br> **Risultato**: autorizziamo l'organizzazione per i test.|**Azione**: creiamo un certificato di chiave pubblica e privata e li carichiamo in Epic. <br> **Risultato**: Epic sincronizza il certificato della chiave pubblica.|**Azione**: completare i passaggi di configurazione nel portale di configurazione del connettore EHR. <br> **Risultato**: si ricevono i record FDI per la configurazione Epic.| **Azione**: si lavora con lo specialista tecnico Epic per configurare i record FDI in Epic.<br> **Risultato**: configurazione completata. Pronto per il test.|**Azione**: È possibile completare i test nell'ambiente di test.<br> **Risultato**: convalida completa dei flussi e decisione di passare alla produzione.|

### <a name="request-access-to-the-teams-app"></a>Richiedere l'accesso all Teams app

Dovrai richiedere l'accesso all'app Teams app.

1. Richiedi di scaricare l'app Teams app [nel marketplace Epic App Orchard](https://apporchard.epic.com/Gallery?id=6153). In questo modo viene attivata una richiesta da Epic al team di connettori Microsoft EHR.
1. Dopo aver inviato la richiesta, inviare un messaggio di posta elettronica [a TeamsForHealthcare@microsoft.com](mailto:TeamsForHealthcare@microsoft.com) con il nome dell'organizzazione, l'ID tenant e l'indirizzo di posta elettronica del contatto tecnico Epic.
1. Il team del connettore Microsoft EHR risponderà al messaggio di posta elettronica con la conferma dell'abilitazione.

### <a name="review-the-epic-microsoft-teams-telehealth-integration-guide"></a>Leggere la guida Epic-Microsoft Teams'integrazione telehealth

Rivedere la [Guida all'integrazione della telemedicina di Epic-Microsoft Teams](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) con uno specialista tecnico Epic. Assicurarsi che tutti i prerequisiti siano soddisfatti.

## <a name="prerequisites"></a>Prerequisiti

- Un abbonamento attivo a Microsoft Cloud per il settore sanitario o un abbonamento a un'offerta autonoma del connettore EHR Microsoft Teams (applicata solo quando si esegue il test in un ambiente EHR di produzione).
- Versione epica di novembre 2018 o successiva.
- Gli utenti hanno una licenza Microsoft 365 o Office 365 che include Teams riunioni.
- Teams viene adottato e usato nell'organizzazione sanitaria.
- I sistemi soddisfano tutti [i requisiti software e del browser](../../hardware-requirements-for-the-teams-app.md) per Teams.

> [!IMPORTANT]
> Assicurarsi di completare i passaggi di pre-integrazione e che tutti i prerequisiti siano soddisfatti prima di procedere con l'integrazione.

I passaggi di integrazione vengono eseguiti dalle persone seguenti dell'organizzazione:

- **Microsoft 365 amministratore globale**: la persona principale responsabile dell'integrazione. L'amministratore configura il connettore, abilita SMS (se necessario) e aggiunge l'analista del cliente Epic che approverà la configurazione.
- **Analista cliente epico**: una persona dell'organizzazione che ha le credenziali di accesso a Epic. Approvano le impostazioni di configurazione immesse dall'amministratore e forniscono i record di configurazione a Epic.

L Microsoft 365 e l'analista dei clienti Epic possono essere la stessa persona.

## <a name="set-up-the-teams-ehr-connector"></a>Configurare il connettore Teams EHR

Per la configurazione del connettore è necessario:

- [Avviare il portale di configurazione del connettore EHR](#launch-the-ehr-connector-configuration-portal)
- [Immettere le informazioni di configurazione](#enter-configuration-information)
- [Abilitare le notifiche SMS (facoltativo)](#enable-sms-notifications-optional)
- [Approvare o visualizzare la configurazione](#approve-or-view-the-configuration)
- [Rivedere e completare la configurazione](#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>Avviare il portale di configurazione del connettore EHR

Per iniziare, l'amministratore Microsoft 365 avvia il portale di configurazione del connettore [EHR](https://ehrconnector.teams.microsoft.com) e accede usando le Microsoft 365 credenziali.

L Microsoft 365 amministratore può configurare una o più organizzazioni per testare l'integrazione. Configurare l'URL di test e produzione nel portale di configurazione. Assicurarsi di testare l'integrazione dall'ambiente di test Epic prima di passare alla produzione.

> [!NOTE]
> L Microsoft 365 e l'analista del cliente Epic devono completare i passaggi di integrazione nel portale di configurazione. Per la procedura di configurazione epica, contattare lo specialista tecnico Epic assegnato all'organizzazione.

### <a name="enter-configuration-information"></a>Immettere le informazioni di configurazione

Quindi, per configurare l'integrazione, l'Microsoft 365 amministratore esegue le operazioni seguenti:

1. Aggiunge un URL di base FHIR (Fast Health Interoperability Resources) dallo specialista tecnico Epic e specifica l'ambiente. Configurare il numero di URL di base FHIR necessario, a seconda delle esigenze dell'organizzazione e degli ambienti da testare.

    - L'URL di base FHIR è un indirizzo statico che corrisponde all'endpoint API FHIR del server. Un URL di esempio è `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.

    - È possibile configurare l'integrazione per gli ambienti di test e produzione. Per la configurazione iniziale, è necessario configurare il connettore da un ambiente di prova prima di passare all'ambiente di produzione.

1. Aggiunge il nome utente dell'analista del cliente Epic che approverà la configurazione in un passaggio successivo.

    :::image type="content" source="media/ehr-connector-epic-configure.png" alt-text="Screenshot della pagina Configurazione che mostra il responsabile approvazione aggiunto." lightbox="media/ehr-connector-epic-configure.png":::

### <a name="enable-sms-notifications-optional"></a>Abilitare le notifiche SMS (facoltativo)

> [!NOTE]
> Le notifiche TRAMITE SMS sono attualmente disponibili solo negli Stati Uniti. Stiamo lavorando per rendere questa funzionalità disponibile in altre aree geografiche nelle versioni future Teams e questo articolo verrà aggiornato quando disponibile. 

Completare questo passaggio se l'organizzazione vuole che Microsoft gesti le notifiche SMS per i pazienti. Quando si abilitano le notifiche TRAMITE SMS, i pazienti riceveranno messaggi di conferma e promemoria per le visite virtuali pianificate.

Per abilitare le notifiche TRAMITE SMS, l Microsoft 365 amministratore esegue le operazioni seguenti:

1. Nella pagina Notifiche SMS selezionare entrambe le caselle di controllo di consenso per:

    - Consenti a Microsoft di inviare notifiche SMS ai pazienti per conto dell'organizzazione.
    - Conferma che i partecipanti hanno acconsentito a inviare e ricevere SMS.
    
    :::image type="content" source="media/ehr-connector-epic-sms-notifications.png" alt-text="Screenshot della pagina delle notifiche TRAMITE SMS, con le caselle di controllo relative al consenso e l'opzione per generare un numero di telefono." lightbox="media/ehr-connector-epic-sms-notifications.png":::

1. In **Numeri di telefono selezionare** **Genera un nuovo numero di telefono** per generare un numero di telefono per l'organizzazione. In questo modo viene avviato il processo per richiedere e generare un nuovo numero di telefono. Il completamento di questo processo potrebbe richiedere fino a 2 minuti.

    Dopo la generazione, il numero di telefono viene visualizzato sullo schermo. Questo numero verrà usato per inviare sms di conferma e promemoria ai pazienti. Il provisioning del numero è stato eseguito ma non è ancora collegato all'URL di base FHIR. Eseguire questa operazione nel passaggio successivo.

    :::image type="content" source="media/ehr-connector-epic-phone-number.png" alt-text="Screenshot che mostra un esempio del numero di telefono generato." lightbox="media/ehr-connector-epic-phone-number.png":::

    Scegliere **Fine** e quindi **avanti**.

1. Per collegare il numero di telefono a un URL di base FHIR, **in Telefono numero nella** sezione configurazione **SMS** selezionare il numero. Eseguire questa operazione per ogni URL di base FHIR per cui si vogliono abilitare le notifiche SMS.

    :::image type="content" source="media/ehr-connector-epic-link-phone-number.png" alt-text="Screenshot che mostra come collegare un numero di telefono a un URL di base FHIR." lightbox="media/ehr-connector-epic-link-phone-number.png":::

    Se è la prima volta che si configura il connettore, verrà visualizzato l'URL di base FHIR immesso nel passaggio precedente. Lo stesso numero di telefono può essere collegato a più URL di base FHIR, il che significa che i pazienti riceveranno notifiche TRAMITE SMS dallo stesso numero di telefono per organizzazioni e/o reparti diversi.

1. Selezionare **Configurazione SMS** accanto a ogni URL di base FHIR per configurare i tipi di notifiche SMS da inviare ai pazienti.

    :::image type="content" source="media/ehr-connector-epic-sms-setup.png" alt-text="Screenshot che mostra le impostazioni di configurazione di SMS." lightbox="media/ehr-connector-epic-sms-setup.png":::

    - **SMS di** conferma: le notifiche vengono inviate ai pazienti quando una visita virtuale viene pianificata, aggiornata o annullata nel sistema EHR.
    - **SMS promemoria**: le notifiche vengono inviate ai pazienti in base all'intervallo di tempo specificato e all'ora pianificata della visita virtuale.

    Scegliere **Save**.

1. Selezionare **Upload certificato per** caricare un certificato con chiave pubblica. È necessario caricare un certificato cer con codifica Base64 (solo chiave pubblica) per ogni ambiente.

    Per ricevere le informazioni sugli appuntamenti per l'invio di notifiche TRAMITE SMS è necessario un certificato di chiave pubblica. Il certificato è necessario per verificare che le informazioni in arrivo siano provenienti da un'origine valida.

    Quando il connettore viene usato per inviare promemoria SMS, il numero di telefono del paziente viene inviato da Epic in un payload HL7v2 quando gli appuntamenti vengono creati in Epic. Questi numeri vengono archiviati per ogni appuntamento nell'area geografica dell'organizzazione e vengono mantenuti fino a quando l'appuntamento non ha luogo. Per altre informazioni su come configurare i messaggi HL7v2, vedere la Guida all'integrazione [di Microsoft Teams Telehealth](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357).

    Scegliere **Avanti**.

> [!NOTE]
> In qualsiasi momento, l Microsoft 365 amministratore può aggiornare qualsiasi impostazione di SMS. Tenere presente che la modifica delle impostazioni potrebbe comportare l'interruzione del servizio SMS. Per altre informazioni su come visualizzare i report SMS, vedere Teams di amministrazione [del connettore EHR](ehr-admin-reports.md).

### <a name="approve-or-view-the-configuration"></a>Approvare o visualizzare la configurazione

L'analista cliente epico dell'organizzazione che è stato aggiunto come responsabile approvazione avvia il portale di configurazione del connettore [EHR](https://ehrconnector.teams.microsoft.com) e accede usando le Microsoft 365 credenziali. Dopo la convalida, al responsabile approvazione viene chiesto di accedere usando le credenziali Epic per convalidare l'organizzazione Epic.

> [!Note]
> Se l'Microsoft 365 e l'analista del cliente Epic sono la stessa persona, sarà comunque necessario accedere a Epic per convalidare l'accesso. L'accesso epico viene usato solo per convalidare l'URL di base FHIR. Microsoft non archivia le credenziali né accede ai dati EHR con questo accesso.

:::image type="content" source="media/ehr-connector-epic-login-approve.png" alt-text="Screenshot della pagina Approva o Visualizza configurazione, con l'opzione Accedi e approva." lightbox="media/ehr-connector-epic-login-approve.png":::

Dopo aver eseguito l'accesso a Epic, l'analista del cliente Epic **deve** approvare la configurazione. Se la configurazione non è corretta, l'Microsoft 365 amministratore può accedere al portale di configurazione e modificare le impostazioni.

:::image type="content" source="media/ehr-connector-epic-approve.png" alt-text="Screenshot della pagina Approva o Visualizza configurazione con l'opzione Approva." lightbox="media/ehr-connector-epic-approve.png":::

### <a name="review-and-finish-the-configuration"></a>Rivedere e completare la configurazione

Quando l’amministratore di Epic avrà approvato le informazioni di configurazione, verranno visualizzati i record di integrazione per l’avvio di visite virtuali tra pazienti e provider. I record di integrazione includono:

- Record di pazienti e provider
- Record SMS diretto
- Record di configurazione SMS
- Record di configurazione del test del dispositivo

L'analista del cliente Epic deve fornire questi record a Epic per completare la configurazione della visita virtuale in Epic. Per altre informazioni, vedere la [Guida all'integrazione di Microsoft Teams Telehealth.](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357)

> [!Note]  
> In qualsiasi momento il Microsoft 365 o l'analista cliente Epic può accedere al portale di configurazione per visualizzare i record di integrazione e modificare la configurazione dell'organizzazione, in base alle esigenze.

:::image type="content" source="media/ehr-connector-epic-finish.png" alt-text="Screenshot della pagina Revisione e fine, con le informazioni sull'integrazione." lightbox="media/ehr-connector-epic-finish.png":::

> [!Note]
> L'analista del cliente Epic deve completare il processo di approvazione per ogni URL di base FHIR configurato dall'Microsoft 365 aziendale.

## <a name="launch-teams-virtual-visits"></a>Avviare visite virtuali di Teams

Dopo aver completato i passaggi del connettore EHR e la configurazione epica, l'organizzazione è pronta a supportare le videochiamate con Teams.

### <a name="virtual-visit-prerequisites"></a>Prerequisiti per la visita virtuale

- I sistemi devono soddisfare tutti i [requisiti software e del browser](../../hardware-requirements-for-the-teams-app.md) per Teams.

- È stata completata la configurazione dell'integrazione tra l'organizzazione Epic e l'Microsoft 365 organizzazione.

### <a name="provider-experience"></a>Esperienza del provider

I provider di servizi sanitari dell'organizzazione possono partecipare a visite virtuali usando Teams dalle loro app di provider Epic (Hyperspace, Haiku, Canto). Il pulsante **Begin virtual visit** (Avvia visita virtuale) è incorporato nel flusso del provider.

Caratteristiche principali dell'esperienza del provider:

- I provider possono partecipare a visite virtuali usando i browser supportati o l Teams app.

- I provider devono eseguire l'accesso singolo con il proprio account Microsoft 365 quando partecipano a una visita virtuale per la prima volta.

- Dopo l'accesso una sola volta, il provider viene portato direttamente all'appuntamento virtuale in Teams. Il provider deve essere connesso a Teams.

- I provider possono visualizzare gli aggiornamenti in tempo reale dei partecipanti che si connettono e si disconnettino per un determinato appuntamento. I provider possono vedere quando il paziente è connesso a una visita virtuale.

  ![Esperienza del provider di una visita virtuale con il paziente.](media/ehc-provider-experience-6.png)

> [!NOTE]
> Tutte le informazioni immesse nella chat della riunione necessarie per la continuità o la conservazione delle cartelle cliniche devono essere scaricate, copiate e notate dal provider sanitario. La chat non costituisce una cartella medica legale o un set di record designato. I messaggi della chat vengono archiviati in base alle impostazioni create dall'Microsoft Teams amministratore.

### <a name="patient-experience"></a>Esperienza del paziente

Il connettore supporta la partecipazione di pazienti alle visite virtuali attraverso le versioni Web e per dispositivo mobile di MyChart. All’ora dell'appuntamento, i pazienti possono iniziare una visita virtuale da MyChart usando il pulsante **Begin virtual visit** (Inizia visita virtuale).

Caratteristiche principali dell'esperienza del paziente:

- I pazienti possono partecipare a visite virtuali da web browser moderni su desktop e [dispositivi mobili](../mobile-browser-join.md) senza dover installare l Teams app.

- I pazienti possono partecipare a visite virtuali con un solo clic e non è necessario alcun altro account o accesso.

- I pazienti non sono tenuti a creare un account Microsoft o ad accedere con le credenziali per avviare una visita virtuale.

- I pazienti vengono inseriti in una sala d'attesa finché il provider non partecipa all'appuntamento e li ammette alla visita virtuale.

- I pazienti possono testare il video e il microfono nella sala d'attesa prima di partecipare alla visita virtuale.

  ![Esperienza paziente della visita virtuale.](media/ehc-virtual-visit-5.png)

> [!Note]
> Epic, MyChart, Haiku e Canto sono marchi registrati di Epic Systems Corporation.

### <a name="privacy-and-location-of-data"></a>Privacy e posizione dei dati

Teams'integrazione nei sistemi EHR ottimizza la quantità di dati usati e archiviati durante l'integrazione e i flussi delle visite virtuali. La soluzione segue i principi generali della privacy e della gestione dei dati di Teams e le linee guida descritte nell’informativa sulla privacy di Teams.

Il Teams EHR non archivia né trasferisce dati personali identificabili o registri sanitari di pazienti o operatori sanitari dal sistema EHR. Gli unici dati archiviati dal connettore CCE sono l'ID univoco dell'utente CCE, che viene usato durante la configurazione della riunione di Teams.

L'ID univoco dell'utente CCE viene archiviato in una delle tre aree geografiche descritte in [Dove sono archiviati i dati dei clienti di Microsoft 365](/microsoft-365/enterprise/o365-data-locations). Tutte le chat, le registrazioni e altri dati condivisi in Teams dai partecipanti alla riunione vengono archiviati in base ai criteri di archiviazione esistenti. Per altre informazioni sulla posizione dei dati in Teams, vedere Posizione [dei dati in Teams](../../location-of-data-in-teams.md).

## <a name="related-articles"></a>Articoli correlati

- [Teams di amministrazione del connettore EHR](ehr-admin-reports.md)
- [Introduzione a Teams per le organizzazioni sanitarie](teams-in-hc.md)
