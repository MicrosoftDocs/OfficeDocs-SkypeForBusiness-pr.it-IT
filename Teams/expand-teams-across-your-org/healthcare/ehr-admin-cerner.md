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
ms.openlocfilehash: fd37b32acfd2a33cde61b56c7f17191e7470923e
ms.sourcegitcommit: 5ca04ee10e3f254e1b24506de116591fdfd51d18
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2022
ms.locfileid: "62929331"
---
# <a name="virtual-visits-with-teams---integration-into-cerner-ehr"></a>Visite virtuali con Teams - Integrazione in Cerner EHR

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Il connettore Microsoft Teams Electronic Health Record (EHR) consente ai medici di avviare facilmente una visita virtuale del paziente o di consultare un altro provider in Microsoft Teams direttamente dal sistema Cerner EHR. Basato sul cloud Microsoft 365, Teams consente una collaborazione e una comunicazione semplici e sicure con strumenti di chat, video, voce e assistenza sanitaria in un unico hub che supporta la conformità con HIPAA, la certificazione HITECH e altro ancora.

La piattaforma di comunicazione e collaborazione di Teams consente ai medici di ridurre facilmente l'ingombro di sistemi frammentati, in modo che possano concentrarsi sulla fornitura delle migliori cure possibili. Con il Teams EHR è possibile:

- Condurre Teams visite virtuali dal sistema Cerner EHR con un flusso di lavoro clinico integrato.
- Consenti ai pazienti di partecipare Teams visite virtuali tramite e-mail o notifiche SMS.
- Visualizza report sui dati di consumo e informazioni personalizzabili sulla qualità delle chiamate per le visite connesse a EHR.

Questo articolo descrive come configurare e configurare il connettore Teams EHR per l'integrazione con la piattaforma Cerner. Offre anche una panoramica dell'esperienza Teams visite virtuali dal sistema Cerner EHR.

## <a name="before-you-begin"></a>Prima di iniziare

> [!NOTE]
> Prima di abilitare l'integrazione, assicurarsi di parlare con il rappresentante Cerner ed esaminare la guida all'integrazione di Cerner.

### <a name="prerequisites"></a>Prerequisiti

Prima di integrare il connettore Teams EHR nell'organizzazione sanitaria, è necessario disporre di quanto segue:

- Un abbonamento attivo all'offerta Microsoft Teams autonomo del connettore EHR (applicato solo durante i test in un ambiente EHR di produzione).
- Gli utenti hanno una licenza Microsoft 365 o Office 365 che include Teams riunioni.
- Teams viene adottato e usato nell'organizzazione sanitaria.
- I sistemi soddisfano tutti [i requisiti software e del browser](../../hardware-requirements-for-the-teams-app.md) per Teams.
- Cerner versione novembre 2018 o successiva

## <a name="set-up-the-teams-ehr-connector"></a>Configurare il connettore Teams EHR

Per la configurazione del connettore è necessario:

- [Avviare il portale di configurazione del connettore EHR](#launch-the-ehr-connector-configuration-portal)
- [Immettere le informazioni di configurazione](#enter-configuration-information)
- [Abilitare le notifiche SMS (facoltativo)](#enable-sms-notifications-optional)
- [Rivedere e completare la configurazione](ehr-admin-cerner.md#review-and-finish-the-configuration)

> [!IMPORTANT]
> Questi passaggi devono essere completati dall Microsoft 365 amministratore globale dell'organizzazione.  

### <a name="launch-the-ehr-connector-configuration-portal"></a>Avviare il portale di configurazione del connettore EHR

Per iniziare, l'amministratore Microsoft 365 avvia il portale di configurazione del connettore [EHR](https://ehrconnector.teams.microsoft.com) e accede usando le credenziali Microsoft.

L Microsoft 365 amministratore può configurare un singolo reparto o più reparti per testare l'integrazione. Configurare l'URL di test e produzione nel portale di configurazione. Assicurarsi di testare l'integrazione dall'ambiente di test Cerner prima di passare all'ambiente di produzione.

### <a name="enter-configuration-information"></a>Immettere le informazioni di configurazione

Quindi, per configurare l'integrazione, l'amministratore Microsoft 365 aggiunge un URL di base FHIR (Fast Health Interoperability Resources) da Cerner e specifica l'ambiente. Configurare il numero di URL di base FHIR necessario, a seconda delle esigenze dell'organizzazione e degli ambienti da testare.

:::image type="content" source="media/ehr-admin-cerner-configuration.png" alt-text="Screenshot della pagina Delle informazioni di configurazione del portale di configurazione Teams connettore EHR." lightbox="media/ehr-admin-cerner-configuration.png":::

- L'URL di base FHIR è un indirizzo statico che corrisponde all'endpoint API FHIR del server. Un URL di esempio è `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.

- È possibile configurare l'integrazione per gli ambienti di test e produzione. Per la configurazione iniziale, è necessario configurare il connettore da un ambiente di prova prima di passare all'ambiente di produzione.

Dopo aver convalidato l'URL di base FHIR e aver selezionato l'ambiente, scegliere **Fine**. Aggiungere quindi altri URL di base FHIR per altri ambienti, se necessario.

Selezionare **Avanti** per andare al passaggio successivo.

### <a name="enable-sms-notifications-optional"></a>Abilitare le notifiche SMS (facoltativo)

Completare questo passaggio se l'organizzazione vuole che Microsoft gesti le notifiche SMS per i pazienti. Quando si abilitano le notifiche TRAMITE SMS, i pazienti riceveranno messaggi di conferma e promemoria per le visite pianificate.

Per abilitare le notifiche SMS, l Microsoft 365 amministratore esegue le operazioni seguenti:

1. Nella pagina Notifiche SMS selezionare entrambe le caselle di controllo di consenso per:

    - Consenti a Microsoft di inviare notifiche SMS ai pazienti per conto dell'organizzazione.
    - Conferma che i partecipanti hanno acconsentito a inviare e ricevere SMS.

    :::image type="content" source="media/ehr-admin-cerner-sms-notifications.png" alt-text="Screenshot della pagina delle notifiche TRAMITE SMS, con le caselle di controllo relative al consenso e l'opzione per generare un numero di telefono." lightbox="media/ehr-admin-cerner-sms-notifications.png":::

1. In **Numeri di telefono selezionare** **Genera un nuovo numero di telefono** per generare un numero di telefono per l'organizzazione. In questo modo viene avviato il processo per richiedere e generare un nuovo numero di telefono. Il completamento di questo processo potrebbe richiedere fino a 2 minuti.

    Dopo la generazione, il numero di telefono viene visualizzato sullo schermo. Questo numero verrà usato per inviare sms di conferma e promemoria ai pazienti. Il provisioning del numero è stato eseguito ma non è ancora collegato all'URL di base FHIR. Eseguire questa operazione nel passaggio successivo.

    :::image type="content" source="media/ehr-admin-cerner-phone-number.png" alt-text="Screenshot che mostra un esempio del numero di telefono generato." lightbox="media/ehr-admin-cerner-phone-number.png":::

    Scegliere **Fine** e quindi **avanti**.

1. Per collegare il numero di telefono a un URL di base FHIR, **in Telefono numero nella** sezione configurazione **SMS** selezionare il numero. Eseguire questa operazione per ogni URL di base FHIR per cui si vogliono abilitare le notifiche SMS.

    :::image type="content" source="media/ehr-admin-cerner-link-phone-number.png" alt-text="Screenshot che mostra come collegare un numero di telefono a un URL di base FHIR." lightbox="media/ehr-admin-cerner-link-phone-number.png":::

    Se è la prima volta che si configura il connettore, verrà visualizzato l'URL di base FHIR immesso nel passaggio precedente. Lo stesso numero di telefono può essere collegato a più URL di base FHIR, il che significa che i pazienti riceveranno notifiche TRAMITE SMS dallo stesso numero di telefono per organizzazioni e/o reparti diversi.

     Selezionare **Avanti**.

### <a name="review-and-finish-the-configuration"></a>Rivedere e completare la configurazione

Verranno presentati i record di integrazione per il lancio di pazienti e provider. Questi record sono necessari per completare la configurazione delle visite virtuali in Cerner. Per altre informazioni, vedere la guida Cerner-Microsoft Teams'integrazione telehealth.

> [!NOTE]
> In qualsiasi momento, l Microsoft 365 amministratore può accedere al portale di configurazione per visualizzare i record di integrazione e modificare le impostazioni di configurazione, se necessario.

## <a name="launch-teams-virtual-visits"></a>Avviare Teams visite virtuali

Dopo aver completato i passaggi del connettore EHR e i passaggi di configurazione di Cerner, l'organizzazione è pronta a supportare le video visite con Teams.

### <a name="virtual-visits-prerequisites"></a>Prerequisiti per le visite virtuali

- I sistemi devono soddisfare tutti i [requisiti software e del browser](../../hardware-requirements-for-the-teams-app.md) per Teams.
- È stata completata la configurazione dell'integrazione tra l'organizzazione Cerner e l'Microsoft 365 organizzazione.

### <a name="provider-experience"></a>Esperienza del provider

I provider di servizi sanitari dell'organizzazione possono partecipare alle visite Teams dal portale di PowerChart. Il provider deve passare alla bacheca del paziente in cui è Teams'opzione di assistenza.

Da qui, il provider può visualizzare le informazioni sulla visita, partecipare alle visite e inviare il collegamento alla riunione. Dopo l'accesso una sola volta, il provider viene portato direttamente all'appuntamento virtuale in Teams.

Caratteristiche principali dell'esperienza del provider:

- I provider possono partecipare alle visite usando i browser supportati o l Teams app.
- I provider possono usare tutte le funzionalità Teams delle riunioni, tra cui la condivisione dello schermo, lo sfondo personalizzato e la registrazione.
- I provider possono visualizzare gli aggiornamenti in tempo reale dei pazienti che si connettono a una visita per un determinato appuntamento in PowerChart.
- Le informazioni sul provider non sono visibili ai pazienti durante la visita.

> [!NOTE]
> Tutte le informazioni immesse nella chat della riunione necessarie per la continuità o la conservazione delle cartelle cliniche devono essere scaricate, copiate e notate dal provider sanitario. La chat non costituisce una cartella medica legale o un set di record designato. I messaggi della chat vengono archiviati in base alle impostazioni create dall Microsoft Teams amministratore.

### <a name="patient-experience"></a>Esperienza del paziente

Il connettore supporta i pazienti che a uniscono le visite tramite un collegamento nel messaggio SMS. Al momento dell'appuntamento, i pazienti possono iniziare una visita toccando il collegamento nell'SMS.

Caratteristiche chiave dell'esperienza del paziente

- I pazienti possono partecipare a visite da web browser moderni su desktop e [dispositivi mobili senza dover](../mobile-browser-join.md) installare l Teams app.
- I pazienti possono partecipare alle visite con un solo clic e non è necessario alcun altro account o accesso.
- I pazienti non sono tenuti a creare un account Microsoft o ad accedere per avviare una visita.
- I pazienti vengono inseriti in una sala d'attesa finché il provider non si unisce e non li ammette.
- I pazienti possono testare il video e il microfono nella sala d'attesa prima di partecipare alla visita.

## <a name="privacy-and-location-of-data"></a>Privacy e posizione dei dati

Teams'integrazione nei sistemi EHR ottimizza la quantità di dati usati e archiviati durante l'integrazione e i flussi delle visite virtuali. La soluzione segue i principi generali della privacy e della gestione dei dati di Teams e le linee guida descritte nell’informativa sulla privacy di Teams.

Il Teams EHR non archivia né trasferisce dati personali identificabili o registri sanitari di pazienti o operatori sanitari dal sistema EHR. Gli unici dati archiviati dal connettore EHR sono l'ID univoco dell'utente EHR, che viene usato durante la configurazione Teams riunione.

L'ID univoco dell'utente CCE viene archiviato in una delle tre aree geografiche descritte in [Dove sono archiviati i dati dei clienti di Microsoft 365](/microsoft-365/enterprise/o365-data-locations). Tutte le chat, le registrazioni e altri dati condivisi in Teams dai partecipanti alla riunione vengono archiviati in base ai criteri di archiviazione esistenti. Per altre informazioni sulla posizione dei dati in Teams, vedere Posizione [dei dati in Teams](../../location-of-data-in-teams.md).

## <a name="related-articles"></a>Articoli correlati

- [Teams utilizzo delle visite virtuali](../../teams-analytics-and-reports/virtual-visits-usage-report.md)
- [Teams di amministrazione del connettore EHR](ehr-admin-reports.md)
- [Introduzione a Teams per le organizzazioni sanitarie](teams-in-hc.md)
