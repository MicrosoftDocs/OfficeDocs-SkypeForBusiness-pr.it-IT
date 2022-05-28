---
title: Appuntamenti virtuali con Teams - Integrazione in Epic EHR
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
description: Informazioni su come integrare il connettore Teams EHR per consentire agli operatori sanitari dell'organizzazione di condurre appuntamenti virtuali con pazienti o altri provider in Teams direttamente dal sistema Epic EHR.
ms.openlocfilehash: c34c8fbb32d78c1380267ce6876e947b877ce383
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2022
ms.locfileid: "65760948"
---
# <a name="virtual-appointments-with-teams---integration-into-epic-ehr"></a>Appuntamenti virtuali con Teams - Integrazione in Epic EHR

Il connettore EHR (Electronic Health Record) Microsoft Teams consente al clinico di lanciare un appuntamento virtuale con un paziente o di consultare un altro fornitore di Microsoft Teams direttamente dal sistema Epic EHR. Basato sul cloud Microsoft 365, Teams consente una collaborazione e una comunicazione semplici e sicure con strumenti di chat, video, voce e assistenza sanitaria in un unico hub che supporta la conformità con HIPAA, la certificazione HITECH e altro ancora.

La piattaforma di comunicazione e collaborazione di Teams consente ai medici di sgombrare facilmente il disordine di sistemi frammentati in modo che possano concentrarsi sulla fornitura della migliore assistenza possibile. Con il connettore Teams EHR è possibile:

- Avvia Teams appuntamenti virtuali dal sistema Epic EHR con un flusso di lavoro clinico integrato.
- Consente ai pazienti di partecipare Teams appuntamenti virtuali dall'interno del portale dei pazienti o tramite SMS.
- Supporta altri scenari, tra cui più partecipanti, visite di gruppo e servizi di interprete.
- Scrivi i metadati nel sistema EHR su Teams appuntamenti virtuali da registrare quando i partecipanti si connettono, si disconnettono e abilitano il controllo automatico e la conservazione dei record.
- Visualizzare report sui dati di consumo e informazioni personalizzabili sulla qualità delle chiamate per gli appuntamenti connessi a EHR.

Questo articolo descrive come configurare il connettore Teams EHR per l'integrazione con la piattaforma Epic nell'organizzazione sanitaria. Offre anche una panoramica dell'esperienza di appuntamenti virtuali Teams dal sistema Epic EHR.

## <a name="before-you-begin"></a>Prima di iniziare

Prima di iniziare, è necessario prepararsi per l'integrazione.

### <a name="get-familiar-with-the-integration-process"></a>Acquisire familiarità con il processo di integrazione

Esaminare le informazioni seguenti per comprendere il processo di integrazione generale.

:::image type="content" source="media/ehr-connector-epic-flow.png" alt-text="Immagine che riepiloga i passaggi del processo di integrazione generale.":::

||||||
|---------|---------|---------|---------|---------|
|**Azione**: [viene richiesto l'accesso all'app Teams](#request-access-to-the-teams-app). <br> **Risultato**: autorizziamo la tua organizzazione per i test.|**Azione**: creiamo un certificato chiave pubblico e privato e li carichiamo in Epic. <br> **Risultato**: Epic sincronizza il certificato di chiave pubblica.|**Azione**: completare i passaggi di configurazione nel portale di configurazione del connettore EHR. <br> **Risultato**: si ricevono record FDI per la configurazione epica.| **Azione**: collabora con il tuo specialista tecnico epico per configurare i record FDI in Epic.<br> **Risultato**: configurazione completata. Pronto per il test.|**Azione**: completa i test nell'ambiente di test.<br> **Risultato**: Convalida completa dei flussi e decisione di passare alla produzione.|

### <a name="request-access-to-the-teams-app"></a>Richiedere l'accesso all'app Teams

Dovrai richiedere l'accesso all'app Teams.

1. Richiesta di scaricare l'app Teams nel [marketplace di Epic App Orchard](https://apporchard.epic.com/Gallery?id=16793). In questo modo viene attivata una richiesta da Epic al team di connettori Microsoft EHR.
1. Dopo aver effettuato la richiesta, inviare un messaggio di posta elettronica a [TeamsForHealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) con il nome dell'organizzazione, l'ID tenant e l'indirizzo di posta elettronica del contatto tecnico epico.
1. Il team del connettore Microsoft EHR risponderà all'e-mail con la conferma dell'abilitazione.

### <a name="review-the-epic-microsoft-teams-telehealth-integration-guide"></a>Esamina la guida Epic-Microsoft Teams Integrazione di Telehealth

Rivedere la [Guida all'integrazione della telemedicina di Epic-Microsoft Teams](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) con uno specialista tecnico Epic. Verificare che tutti i prerequisiti siano soddisfatti.

## <a name="prerequisites"></a>Prerequisiti

- Un abbonamento attivo a Microsoft Cloud for Healthcare o un abbonamento a Microsoft Teams'offerta autonoma del connettore EHR (applicata solo durante i test in un ambiente EHR di produzione).
- Versione epica di novembre 2018 o successiva.
- Gli utenti hanno una licenza appropriata per Microsoft 365 o Office 365 che include Teams riunioni.
- Teams è adottato e usato nell'organizzazione sanitaria.
- I sistemi soddisfano tutti i [requisiti software e del browser](../../hardware-requirements-for-the-teams-app.md) per Teams.

> [!IMPORTANT]
> Assicurarsi di completare la procedura di pre-integrazione e che tutti i prerequisiti siano soddisfatti prima di procedere con l'integrazione.

I passaggi di integrazione vengono eseguiti dalle persone seguenti nell'organizzazione:

- **Microsoft 365 amministratore globale**: la persona principale responsabile dell'integrazione. L'amministratore configura il connettore, abilita SMS (se necessario) e aggiunge l'analista dei clienti Epic che approverà la configurazione.
- **Epic customer analyst**: una persona dell'organizzazione che ha le credenziali di accesso a Epic. Approvano le impostazioni di configurazione immesse dall'amministratore e forniscono i record di configurazione a Epic.

L'amministratore Microsoft 365 e l'analista dei clienti Epic possono essere la stessa persona.

## <a name="set-up-the-teams-ehr-connector"></a>Configurare il connettore Teams EHR

Per la configurazione del connettore è necessario:

- [Avviare il portale di configurazione del connettore EHR](#launch-the-ehr-connector-configuration-portal)
- [Immettere le informazioni di configurazione](#enter-configuration-information)
- [Abilitare le notifiche di SMS (facoltativo)](#enable-sms-notifications-optional)
- [Approvare o visualizzare la configurazione](#approve-or-view-the-configuration)
- [Rivedere e completare la configurazione](#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>Avviare il portale di configurazione del connettore EHR

Per iniziare, l'amministratore Microsoft 365 avvia il portale di configurazione del [connettore EHR](https://ehrconnector.teams.microsoft.com) ed esegue l'accesso con le credenziali di Microsoft 365.

L'amministratore Microsoft 365 può configurare una o più organizzazioni per testare l'integrazione. Configurare l'URL di test e produzione nel portale di configurazione. Assicurarsi di testare l'integrazione dall'ambiente di test Epic prima di passare alla produzione.

> [!NOTE]
> L'amministratore Microsoft 365 e l'analista dei clienti Epic devono completare i passaggi di integrazione nel portale di configurazione. Per i passaggi di configurazione epici, contattare lo specialista tecnico epico assegnato all'organizzazione.

### <a name="enter-configuration-information"></a>Immettere le informazioni di configurazione

Quindi, per configurare l'integrazione, l'amministratore Microsoft 365 esegue le operazioni seguenti:

1. Aggiunge un URL di base Fast Health Interoperability Resources (FHIR) dal tuo specialista tecnico epico e specifica l'ambiente. Configurare tutti gli URL di base FHIR necessari, a seconda delle esigenze dell'organizzazione e degli ambienti da testare.

    - L'URL di base FHIR è un indirizzo statico che corrisponde all'endpoint dell'API FHIR del server. Un URL di esempio è `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.

    - È possibile configurare l'integrazione per gli ambienti di test e produzione. Per la configurazione iniziale, è consigliabile configurare il connettore da un ambiente di test prima di passare alla produzione.

1. Aggiunge il nome utente dell'analista del cliente Epic che approverà la configurazione in un passaggio successivo.

    :::image type="content" source="media/ehr-connector-epic-configure.png" alt-text="Screenshot della pagina Configurazione, che mostra il responsabile approvazione aggiunto." lightbox="media/ehr-connector-epic-configure.png":::

### <a name="enable-sms-notifications-optional"></a>Abilitare le notifiche di SMS (facoltativo)

> [!NOTE]
> SMS notifiche sono attualmente disponibili solo nel Stati Uniti. Stiamo lavorando per rendere questa funzionalità disponibile in altre aree geografiche nelle versioni future di Teams e aggiorneremo questo articolo quando disponibile.

Completare questo passaggio se l'organizzazione vuole che Microsoft gestisse le notifiche di SMS per i pazienti. Quando si abilitano le notifiche di SMS, i pazienti riceveranno messaggi di conferma e promemoria per gli appuntamenti pianificati.

Per abilitare le notifiche di SMS, l'amministratore Microsoft 365 esegue le operazioni seguenti:

1. Nella pagina delle notifiche SMS seleziona entrambe le caselle di controllo per il consenso per:

    - Consenti a Microsoft di inviare notifiche di SMS ai pazienti per conto dell'organizzazione.
    - Confermare che i partecipanti avranno acconsentito a inviare e ricevere SMS messaggi.
    
    :::image type="content" source="media/ehr-connector-epic-sms-notifications.png" alt-text="Screenshot della pagina delle notifiche di SMS, con le caselle di controllo per il consenso e l'opzione per generare un numero di telefono." lightbox="media/ehr-connector-epic-sms-notifications.png":::

1. In **I tuoi numeri di telefono** seleziona **Genera un nuovo numero di telefono** per generare un numero di telefono per la tua organizzazione. In questo modo viene avviato il processo per richiedere e generare un nuovo numero di telefono. Il completamento di questo processo potrebbe richiedere fino a 2 minuti.

    Dopo che il numero di telefono è stato generato, viene visualizzato sullo schermo. Questo numero verrà utilizzato per inviare SMS conferme e promemoria ai pazienti. Il provisioning del numero è stato eseguito, ma non è ancora collegato all'URL di base FHIR. Esegui questa operazione nel passaggio successivo.

    :::image type="content" source="media/ehr-connector-epic-phone-number.png" alt-text="Screenshot che mostra un esempio del numero di telefono generato." lightbox="media/ehr-connector-epic-phone-number.png":::

    Scegliere **Fine** e quindi **Avanti**.

1. Per collegare il numero di telefono a un URL di base FHIR, selezionare il **numero in Telefono numero** nella sezione **di configurazione SMS**. Eseguire questa operazione per ogni URL di base FHIR per cui si desidera abilitare le notifiche di SMS.

    :::image type="content" source="media/ehr-connector-epic-link-phone-number.png" alt-text="Screenshot che mostra come collegare un numero di telefono a un URL di base FHIR." lightbox="media/ehr-connector-epic-link-phone-number.png":::

    Se è la prima volta che si configura il connettore, viene visualizzato l'URL di base FHIR immesso nel passaggio precedente. Lo stesso numero di telefono può essere collegato a più URL di base FHIR, il che significa che i pazienti riceveranno notifiche di SMS dallo stesso numero di telefono per organizzazioni e/o reparti diversi.

1. Selezionare **SMS configurazione** accanto a ogni URL di base FHIR per impostare i tipi di notifiche di SMS da inviare ai pazienti.

    :::image type="content" source="media/ehr-connector-epic-sms-setup.png" alt-text="Screenshot che mostra le impostazioni di configurazione di SMS." lightbox="media/ehr-connector-epic-sms-setup.png":::

    - **Conferma SMS**: le notifiche vengono inviate ai pazienti quando un appuntamento è pianificato, aggiornato o annullato nel sistema EHR.
    - **Promemoria SMS**: le notifiche vengono inviate ai pazienti in base all'intervallo di tempo specificato e all'ora pianificata dell'appuntamento.

    Scegliere **Save**.

1. Selezionare **Upload certificato** per caricare un certificato con chiave pubblica. È necessario caricare un certificato cer con codifica Base64 (solo chiave pubblica) per ogni ambiente.

    Per ricevere informazioni sugli appuntamenti per l'invio di notifiche di SMS, è necessario un certificato di chiave pubblica. Il certificato è necessario per verificare che le informazioni in arrivo proveni siano provenienti da una fonte valida.

    Quando il connettore viene utilizzato per inviare promemoria SMS, il numero di telefono del paziente viene inviato da Epic in un payload HL7v2 quando gli appuntamenti vengono creati in Epic. Questi numeri vengono archiviati per ogni appuntamento nell'area geografica dell'organizzazione e vengono conservati fino a quando non viene effettuato l'appuntamento. Per ulteriori informazioni su come configurare i messaggi HL7v2, vedi la [Guida all'integrazione di Epic-Microsoft Teams Telehealth](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357).

    Scegliere **Avanti**.

> [!NOTE]
> L'amministratore Microsoft 365 può aggiornare le impostazioni di SMS in qualsiasi momento. Tenere presente che la modifica delle impostazioni potrebbe causare un arresto di SMS servizio. Per altre informazioni su come visualizzare i report SMS, vedere [report di amministrazione di Teams connettore EHR](ehr-admin-reports.md).

### <a name="approve-or-view-the-configuration"></a>Approvare o visualizzare la configurazione

L'analista dei clienti Epic nell'organizzazione che è stato aggiunto come responsabile approvazione avvia il [portale di configurazione del connettore EHR](https://ehrconnector.teams.microsoft.com) e accede usando le credenziali di Microsoft 365. Dopo la convalida, al responsabile approvazione viene chiesto di accedere con le credenziali epiche per convalidare l'organizzazione Epic.

> [!Note]
> Se l'amministratore Microsoft 365 e l'analista dei clienti Epic sono la stessa persona, sarà comunque necessario accedere a Epic per convalidare l'accesso. L'accesso Epic viene usato solo per convalidare l'URL di base FHIR. Microsoft non archivierà le credenziali o non accederà ai dati EHR con questo accesso.

:::image type="content" source="media/ehr-connector-epic-login-approve.png" alt-text="Screenshot della pagina Approva o Visualizza configurazione, con l'opzione Accedi e approva." lightbox="media/ehr-connector-epic-login-approve.png":::

Dopo aver eseguito correttamente l'accesso a Epic, l'analista dei clienti di Epic **deve** approvare la configurazione. Se la configurazione non è corretta, l'amministratore Microsoft 365 può accedere al portale di configurazione e modificare le impostazioni.

:::image type="content" source="media/ehr-connector-epic-approve.png" alt-text="Screenshot della pagina Approva o Visualizza configurazione con l'opzione Approva." lightbox="media/ehr-connector-epic-approve.png":::

### <a name="review-and-finish-the-configuration"></a>Rivedere e completare la configurazione

Quando l’amministratore di Epic avrà approvato le informazioni di configurazione, verranno visualizzati i record di integrazione per l’avvio di visite virtuali tra pazienti e provider. I record di integrazione includono:

- Record di pazienti e fornitori
- Direct SMS record
- record di configurazione SMS
- Record di configurazione del test del dispositivo

Il token di contesto per il test del dispositivo è disponibile nel record di integrazione del paziente. L'analista dei clienti Epic deve fornire questi record a Epic per completare la configurazione degli appuntamenti virtuali in Epic. Per ulteriori informazioni, vedi la [Guida all'integrazione di Epic-Microsoft Teams Telehealth](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357).

> [!Note]  
> In qualsiasi momento l'analista del cliente Microsoft 365 o Epic può accedere al portale di configurazione per visualizzare i record di integrazione e modificare la configurazione dell'organizzazione, se necessario.

:::image type="content" source="media/ehr-connector-epic-finish.png" alt-text="Screenshot della pagina Revisione e fine, con informazioni sull'integrazione." lightbox="media/ehr-connector-epic-finish.png":::

> [!Note]
> L'analista del cliente epico deve completare il processo di approvazione per ogni URL di base FHIR configurato dall'amministratore di Microsoft 365.

## <a name="launch-teams-virtual-appointments"></a>Avviare Teams appuntamenti virtuali

Dopo aver completato i passaggi del connettore EHR e la configurazione epica, l'organizzazione è pronta a supportare gli appuntamenti video con Teams.

### <a name="virtual-appointments-prerequisites"></a>Prerequisiti per appuntamenti virtuali

- I sistemi devono soddisfare tutti i [requisiti software e del browser](../../hardware-requirements-for-the-teams-app.md) per Teams.

- È stata completata la configurazione dell'integrazione tra l'organizzazione Epic e l'organizzazione Microsoft 365.

### <a name="provider-experience"></a>Esperienza del provider

Gli operatori sanitari della tua organizzazione possono partecipare agli appuntamenti usando Teams dalle loro app epiche (Hyperspace, Haiku, Canto). Il pulsante **Begin virtual visit** (Avvia visita virtuale) è incorporato nel flusso del provider.

  ![Esperienza del fornitore di un appuntamento virtuale con il paziente.](media/ehc-provider-experience-6.png)

Caratteristiche principali dell'esperienza del provider:

- I provider possono partecipare agli appuntamenti usando i browser supportati o l'app Teams.

- I provider devono eseguire un accesso una tantum con il proprio account di Microsoft 365 quando si partecipa a un appuntamento per la prima volta.

- Dopo l'accesso una tantum, il provider viene indirizzato direttamente all'appuntamento virtuale in Teams. (Il provider deve essere connesso a Teams).

- I provider possono vedere gli aggiornamenti in tempo reale dei partecipanti che si connettono e si disconnettono per un determinato appuntamento. I fornitori possono vedere quando il paziente è connesso a un appuntamento.

> [!NOTE]
> Tutte le informazioni immesse nella chat della riunione necessarie per garantire la continuità o la conservazione delle cartelle cliniche devono essere scaricate, copiate e annoate dal provider del servizio sanitario. La chat non costituisce una cartella clinica legale o un record designato. I messaggi della chat vengono archiviati in base alle impostazioni create dall'amministratore Microsoft Teams.

### <a name="patient-experience"></a>Esperienza del paziente

Il connettore supporta i pazienti che partecipano agli appuntamenti tramite un collegamento nell'SMS di SMS, nel Web Grafico personale e nel dispositivo mobile. Al momento dell'appuntamento, i pazienti possono iniziare l'appuntamento da Grafico personale usando il pulsante **Inizia visita virtuale** o toccando il collegamento nell'SMS di SMS.

  ![Esperienza paziente di un appuntamento virtuale.](media/ehc-virtual-visit-5.png)

Caratteristiche principali dell'esperienza del paziente:

- I pazienti possono partecipare agli [appuntamenti dai web browser moderni su desktop e dispositivi mobili senza dover installare l'app Teams](../browser-join.md).
- I pazienti possono testare l'hardware e la connessione del dispositivo prima di partecipare a un appuntamento.

    :::image type="content" source="media/ehr-admin-epic-device-test.png" alt-text="Immagini di un dispositivo mobile che mostra le funzionalità di test del dispositivo." lightbox="media/ehr-admin-epic-device-test.png":::
  
    Funzionalità di test del dispositivo:

  - I pazienti possono testare l'altoparlante, il microfono, la fotocamera e la connessione.
  - I pazienti possono completare una chiamata di test per convalidare completamente la loro configurazione.
  - I risultati del test del dispositivo possono essere inviati al sistema EHR.

- I pazienti possono partecipare agli appuntamenti con un solo clic e non sono necessari altri account o accessi.

- I pazienti non devono creare un account Microsoft o accedere per avviare un appuntamento.

- I pazienti sono messi in una sala d'attesa finché il fornitore non li aggiunge e li ammette.

- I pazienti possono testare il video e il microfono nella sala di attesa prima di partecipare all'appuntamento.

> [!Note]
> Epic, MyChart, Haiku e Canto sono marchi registrati di Epic Systems Corporation.

## <a name="get-insight-into-virtual-appointments-usage"></a>Ottenere informazioni dettagliate sull'utilizzo degli appuntamenti virtuali

Il [report Sull'utilizzo delle visite virtuali](../../teams-analytics-and-reports/virtual-visits-usage-report.md) nell'interfaccia di amministrazione di Microsoft Teams offre agli amministratori una panoramica delle attività Teams appuntamenti virtuali nell'organizzazione. Il report mostra analisi dettagliate per gli appuntamenti virtuali, tra cui Teams riunioni integrate con EHR eseguite dal sistema EHR.

È possibile visualizzare metriche chiave come il tempo di attesa della sala di attesa e la durata dell'appuntamento. Usare queste informazioni per ottenere informazioni approfondite sulle tendenze di utilizzo e ottimizzare gli appuntamenti virtuali per ottenere risultati aziendali migliori.

### <a name="privacy-and-location-of-data"></a>Privacy e posizione dei dati

Teams l'integrazione nei sistemi EHR ottimizza la quantità di dati usati e archiviati durante l'integrazione e i flussi di appuntamenti virtuali. La soluzione segue i principi generali della privacy e della gestione dei dati di Teams e le linee guida descritte nell’informativa sulla privacy di Teams.

Il connettore Teams EHR non archivia né trasferisce dati personali identificabili o record sanitari di pazienti o operatori sanitari dal sistema EHR. Gli unici dati archiviati dal connettore CCE sono l'ID univoco dell'utente CCE, che viene usato durante la configurazione della riunione di Teams.

L'ID univoco dell'utente CCE viene archiviato in una delle tre aree geografiche descritte in [Dove sono archiviati i dati dei clienti di Microsoft 365](/microsoft-365/enterprise/o365-data-locations). Tutte le chat, le registrazioni e altri dati condivisi in Teams dai partecipanti alla riunione vengono archiviati in base ai criteri di archiviazione esistenti. Per altre informazioni sulla posizione dei dati in Teams, vedere [Posizione dei dati in Teams](../../location-of-data-in-teams.md).

## <a name="related-articles"></a>Articoli correlati

- [report sull'utilizzo delle visite virtuali Teams](../../teams-analytics-and-reports/virtual-visits-usage-report.md)
- [report di amministrazione del connettore Teams EHR](ehr-admin-reports.md)
- [Attività iniziali con Teams per le organizzazioni sanitarie](teams-in-hc.md)
