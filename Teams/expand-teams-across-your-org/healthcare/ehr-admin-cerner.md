---
title: Visite virtuali con Teams - Integrazione in Cerner EHR
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
description: Informazioni su come integrare il connettore Teams EHR per consentire agli operatori sanitari dell'organizzazione di condurre visite virtuali con pazienti o altri provider in Teams direttamente dal sistema Cerner EHR.
ms.openlocfilehash: b5a5a860036b3b561d5a6e18a13b71e072998aa4
ms.sourcegitcommit: 1e8cff687b12348d4ecc538084ab57bbba23b523
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2022
ms.locfileid: "64703692"
---
# <a name="virtual-visits-with-teams---integration-into-cerner-ehr"></a>Visite virtuali con Teams - Integrazione in Cerner EHR

Il connettore EHR (Electronic Health Record) Microsoft Teams consente al clinico di avviare una visita virtuale o di consultare un altro fornitore in Microsoft Teams direttamente dal sistema EHR cerner. Basato sul cloud Microsoft 365, Teams consente una collaborazione e una comunicazione semplici e sicure con strumenti di chat, video, voce e assistenza sanitaria in un unico hub che supporta la conformità con HIPAA, la certificazione HITECH e altro ancora.

La piattaforma di comunicazione e collaborazione di Teams consente ai medici di sgombrare facilmente il disordine di sistemi frammentati in modo che possano concentrarsi sulla fornitura della migliore assistenza possibile. Con il connettore Teams EHR è possibile:

- Condurre Teams visite virtuali dal sistema Cerner EHR con un flusso di lavoro clinico integrato.
- Consente ai pazienti di partecipare a visite virtuali Teams dalle notifiche tramite posta elettronica o SMS.
- Visualizzare report sui dati di consumo e informazioni personalizzabili sulla qualità delle chiamate per le visite connesse con EHR.

Questo articolo descrive come configurare il connettore Teams EHR per l'integrazione con la piattaforma Cerner. Offre anche una panoramica dell'esperienza delle visite virtuali Teams dal sistema EHR di Cerner.

## <a name="before-you-begin"></a>Prima di iniziare

> [!NOTE]
> Assicurati di parlare con il tuo rappresentante Cerner e rivedi la guida all'integrazione di Cerner prima di abilitare l'integrazione.

### <a name="prerequisites"></a>Prerequisiti

Prima di integrare il connettore Teams EHR nell'organizzazione sanitaria, è necessario disporre di quanto segue:

- Un abbonamento attivo a Microsoft Teams'offerta autonoma del connettore EHR (applicata solo durante il test in un ambiente EHR di produzione).
- Gli utenti hanno una licenza appropriata per Microsoft 365 o Office 365 che include Teams riunioni.
- Teams è adottato e usato nell'organizzazione sanitaria.
- I sistemi soddisfano tutti i [requisiti software e del browser](../../hardware-requirements-for-the-teams-app.md) per Teams.
- Cerner versione novembre 2018 o successiva

## <a name="set-up-the-teams-ehr-connector"></a>Configurare il connettore Teams EHR

Per la configurazione del connettore è necessario:

- [Avviare il portale di configurazione del connettore EHR](#launch-the-ehr-connector-configuration-portal)
- [Immettere le informazioni di configurazione](#enter-configuration-information)
- [Abilitare le notifiche SMS (facoltativo)](#enable-sms-notifications-optional)
- [Rivedere e completare la configurazione](ehr-admin-cerner.md#review-and-finish-the-configuration)

> [!IMPORTANT]
> Questi passaggi devono essere completati dall'amministratore globale Microsoft 365 dell'organizzazione.  

### <a name="launch-the-ehr-connector-configuration-portal"></a>Avviare il portale di configurazione del connettore EHR

Per iniziare, l'amministratore Microsoft 365 avvia il portale di configurazione del [connettore EHR](https://ehrconnector.teams.microsoft.com) ed esegue l'accesso con le credenziali Microsoft.

L'amministratore Microsoft 365 può configurare un singolo reparto o più reparti per testare l'integrazione. Configurare l'URL di test e produzione nel portale di configurazione. Assicurarsi di testare l'integrazione dall'ambiente di test cerner prima di passare alla produzione.

### <a name="enter-configuration-information"></a>Immettere le informazioni di configurazione

Quindi, per configurare l'integrazione, l'amministratore Microsoft 365 aggiunge un URL di base Fast Health Interoperability Resources (FHIR) da Cerner e specifica l'ambiente. Configurare tutti gli URL di base FHIR necessari, a seconda delle esigenze dell'organizzazione e degli ambienti da testare.

:::image type="content" source="media/ehr-admin-cerner-configuration.png" alt-text="Screenshot della pagina Informazioni di configurazione del portale di configurazione del connettore Teams EHR." lightbox="media/ehr-admin-cerner-configuration.png":::

- L'URL di base FHIR è un indirizzo statico che corrisponde all'endpoint dell'API FHIR del server. Un URL di esempio è `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.

- È possibile configurare l'integrazione per gli ambienti di test e produzione. Per la configurazione iniziale, è consigliabile configurare il connettore da un ambiente di test prima di passare alla produzione.

Dopo aver convalidato l'URL di base FHIR e aver selezionato l'ambiente, scegliere **Fatto**. Quindi, aggiungere altri URL di base FHIR per altri ambienti, in base alle esigenze.

Selezionare **Avanti** per passare al passaggio successivo.

### <a name="enable-sms-notifications-optional"></a>Abilitare le notifiche SMS (facoltativo)

Completare questo passaggio se l'organizzazione vuole che Microsoft gestisse le notifiche SMS per i pazienti. Quando si abilitano le notifiche SMS, i pazienti riceveranno messaggi di conferma e promemoria per le visite pianificate.

Per abilitare le notifiche SMS, l'amministratore Microsoft 365 esegue le operazioni seguenti:

1. Nella pagina Notifiche SMS seleziona entrambe le caselle di controllo per il consenso per:

    - Consenti a Microsoft di inviare notifiche SMS ai pazienti per conto della tua organizzazione.
    - Confermare che i partecipanti avranno acconsentito a inviare e ricevere messaggi SMS.

    :::image type="content" source="media/ehr-admin-cerner-sms-notifications.png" alt-text="Screenshot della pagina delle notifiche SMS, che mostra le caselle di controllo per il consenso e l'opzione per generare un numero di telefono." lightbox="media/ehr-admin-cerner-sms-notifications.png":::

1. In **I tuoi numeri di telefono** seleziona **Genera un nuovo numero di telefono** per generare un numero di telefono per la tua organizzazione. In questo modo viene avviato il processo per richiedere e generare un nuovo numero di telefono. Il completamento di questo processo potrebbe richiedere fino a 2 minuti.

    Dopo che il numero di telefono è stato generato, viene visualizzato sullo schermo. Questo numero verrà utilizzato per inviare ai pazienti conferme e promemoria tramite SMS. Il provisioning del numero è stato eseguito, ma non è ancora collegato all'URL di base FHIR. Esegui questa operazione nel passaggio successivo.

    :::image type="content" source="media/ehr-admin-cerner-phone-number.png" alt-text="Screenshot che mostra un esempio del numero di telefono generato." lightbox="media/ehr-admin-cerner-phone-number.png":::

    Scegliere **Fine** e quindi **Avanti**.

1. Per collegare il numero di telefono a un URL di base FHIR, selezionare il **numero in Telefono numero** nella sezione **configurazione SMS**. Eseguire questa operazione per ogni URL di base FHIR per cui si desidera abilitare le notifiche SMS.

    :::image type="content" source="media/ehr-admin-cerner-link-phone-number.png" alt-text="Screenshot che mostra come collegare un numero di telefono a un URL di base FHIR." lightbox="media/ehr-admin-cerner-link-phone-number.png":::

    Se è la prima volta che si configura il connettore, viene visualizzato l'URL di base FHIR immesso nel passaggio precedente. Lo stesso numero di telefono può essere collegato a più URL di base FHIR, il che significa che i pazienti riceveranno notifiche SMS dallo stesso numero di telefono per diverse organizzazioni e/o reparti.

     Selezionare **Avanti**.

### <a name="review-and-finish-the-configuration"></a>Rivedere e completare la configurazione

Verranno visualizzati i record di integrazione per il lancio di pazienti e fornitori. Questi record sono necessari per completare la configurazione delle visite virtuali a Cerner. Per ulteriori informazioni, vedi la guida Cerner-Microsoft Teams Telehealth Integration.

> [!NOTE]
> In qualsiasi momento, l'amministratore Microsoft 365 può accedere al portale di configurazione per visualizzare i record di integrazione e modificare le impostazioni di configurazione, se necessario.

## <a name="launch-teams-virtual-visits"></a>Avviare Teams visite virtuali

Dopo aver completato i passaggi del connettore EHR e i passaggi di configurazione di Cerner, l'organizzazione è pronta a supportare le visite video con Teams.

### <a name="virtual-visits-prerequisites"></a>Prerequisiti delle visite virtuali

- I sistemi devono soddisfare tutti i [requisiti software e del browser](../../hardware-requirements-for-the-teams-app.md) per Teams.
- È stata completata la configurazione dell'integrazione tra l'organizzazione Cerner e l'organizzazione Microsoft 365.

### <a name="provider-experience"></a>Esperienza del provider

Gli operatori sanitari dell'organizzazione possono partecipare alle visite usando Teams dal portale di PowerChart. Il fornitore deve accedere alla scheda del paziente, dove è disponibile l'opzione Teams.

Da qui, il provider può visualizzare le informazioni sulla visita, partecipare alle visite e inviare il collegamento alla riunione. Dopo l'accesso una tantum, il provider viene indirizzato direttamente all'appuntamento virtuale in Teams.

Caratteristiche principali dell'esperienza del provider:

- I provider possono partecipare alle visite usando i browser supportati o l'app Teams.
- I provider possono usare tutte le funzionalità supportate per le riunioni Teams, tra cui la condivisione dello schermo, lo sfondo personalizzato e la registrazione.
- I provider possono vedere gli aggiornamenti in tempo reale dei pazienti che si connettono a una visita per un determinato appuntamento in PowerChart.
- Le informazioni sul provider non sono visibili ai pazienti durante la visita.

> [!NOTE]
> Tutte le informazioni immesse nella chat della riunione necessarie per garantire la continuità o la conservazione delle cartelle cliniche devono essere scaricate, copiate e annoate dal provider del servizio sanitario. La chat non costituisce una cartella clinica legale o un record designato. I messaggi della chat vengono archiviati in base alle impostazioni create dall'amministratore Microsoft Teams.

### <a name="patient-experience"></a>Esperienza del paziente

Il connettore supporta i pazienti che si uniscono alle visite tramite un collegamento nel messaggio di testo SMS. Al momento dell'appuntamento, i pazienti possono iniziare una visita toccando il collegamento nell'SMS.

Caratteristiche principali dell'esperienza del paziente

- I pazienti possono partecipare alle visite dai [web browser moderni su desktop e dispositivi mobili senza dover installare l'app Teams](../browser-join.md).
- I pazienti possono partecipare alle visite con un solo clic e non sono necessari altri account o accessi.
- I pazienti non sono tenuti a creare un account Microsoft o ad accedere per avviare una visita.
- I pazienti sono messi in una sala d'attesa finché il fornitore non li aggiunge e li ammette.
- I pazienti possono testare il video e il microfono nella sala di attesa prima di partecipare alla visita.

## <a name="get-insight-into-virtual-visits-usage"></a>Ottenere informazioni dettagliate sull'utilizzo delle visite virtuali

Il [report Utilizzo delle visite virtuali](../../teams-analytics-and-reports/virtual-visits-usage-report.md) nell'interfaccia di amministrazione di Microsoft Teams offre agli amministratori una panoramica di Teams'attività Visite virtuali nell'organizzazione. Il report mostra analisi dettagliate per gli appuntamenti virtuali, tra cui Teams riunioni integrate con EHR eseguite dal sistema EHR.

È possibile visualizzare le metriche principali, ad esempio il tempo di attesa della sala di attesa e la durata della visita. Usare queste informazioni per ottenere informazioni approfondite sulle tendenze di utilizzo e ottimizzare le visite virtuali per ottenere risultati aziendali migliori.

## <a name="privacy-and-location-of-data"></a>Privacy e posizione dei dati

Teams l'integrazione nei sistemi EHR ottimizza la quantità di dati usati e archiviati durante l'integrazione e i flussi delle visite virtuali. La soluzione segue i principi generali della privacy e della gestione dei dati di Teams e le linee guida descritte nell’informativa sulla privacy di Teams.

Il connettore Teams EHR non archivia né trasferisce dati personali identificabili o record sanitari di pazienti o operatori sanitari dal sistema EHR. Gli unici dati archiviati dal connettore EHR sono l'ID univoco dell'utente EHR, usato durante Teams configurazione della riunione.

L'ID univoco dell'utente CCE viene archiviato in una delle tre aree geografiche descritte in [Dove sono archiviati i dati dei clienti di Microsoft 365](/microsoft-365/enterprise/o365-data-locations). Tutte le chat, le registrazioni e altri dati condivisi in Teams dai partecipanti alla riunione vengono archiviati in base ai criteri di archiviazione esistenti. Per altre informazioni sulla posizione dei dati in Teams, vedere [Posizione dei dati in Teams](../../location-of-data-in-teams.md).

## <a name="related-articles"></a>Articoli correlati

- [report sull'utilizzo delle visite virtuali Teams](../../teams-analytics-and-reports/virtual-visits-usage-report.md)
- [report di amministrazione del connettore Teams EHR](ehr-admin-reports.md)
- [Attività iniziali con Teams per le organizzazioni sanitarie](teams-in-hc.md)
