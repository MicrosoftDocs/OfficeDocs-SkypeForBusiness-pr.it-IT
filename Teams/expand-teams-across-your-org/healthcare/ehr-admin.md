---
title: Teams per Visite virtuali
author: cichur
ms.author: v-mahoffman
manager: serdars
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
description: Usare Microsoft Teams per configurare il sistema di visite virtuali
ms.openlocfilehash: 40772326d2767e7815a73ad9feca2e4853c762fc
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743042"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a>Visite virtuali con Teams - Integrazione in CCE

Microsoft Teams Il connettore EHR (Electronic Health Record) consente ai medici di avviare facilmente una visita virtuale del paziente o una consultazione con un altro provider Teams direttamente dal sistema EHR. Basato sul cloud di Microsoft 365, Microsoft Teams semplifica e assicura la collaborazione e la comunicazione con strumenti di chat, video, voce e assistenza sanitaria in un unico hub che supporta la conformità con HIPAA, la certificazione HITECH e altro ancora.
Con la piattaforma di comunicazione e collaborazione di Teams, il personale medico può facilmente superare la complessità e la confusione di sistemi frammentati per dedicare il proprio tempo a fornire la migliore assistenza possibile. Microsoft Teams Il connettore EHR (Electronic Health Record) può:

- Avvia Teams visite virtuali dal sistema provider EHR con un flusso di lavoro clinico integrato.
- Consentire ai pazienti di partecipare Teams visite virtuali dall'interno del portale dei pazienti.
- Scrivere di nuovo i metadati nel sistema EHR Teams le visite virtuali da registrare quando i partecipanti si connettono e si disconnettino e abilitano il controllo automatico e la conservazione dei record.

  Guardare il video su come gestire le visite virtuali dal portale CCE.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a>Prima di iniziare

Prima di integrare il connettore CCE, è necessario verificare di avere i prerequisiti seguenti:

- Accesso all'app Microsoft Teams nel [marketplace App Orchard di Epic](https://apporchard.epic.com/Gallery?id=6153).

- Abbonamento attivo a Microsoft Cloud per il settore sanitario o abbonamento a un'offerta autonoma Microsoft Teams connettore EHR (applicata solo durante i test di produzione).

- Gli utenti devono avere una licenza Microsoft 365 o Office 365 appropriata che includa le riunioni di Microsoft Teams.

- Microsoft Teams dovrà essere adottato e usato all'interno dell'organizzazione.

- Le organizzazioni devono avere la versione Epic di novembre 2018 o successiva.

- I sistemi devono soddisfare tutti i [prerequisiti per software e browser](../../hardware-requirements-for-the-teams-app.md).

All'interno dell'organizzazione saranno necessarie anche le informazioni seguenti:

- Amministratore di Microsoft 365

- Customer Analyst di Epic

> [!Note]
> Rivedere la [Guida all'integrazione della telemedicina di Epic-Microsoft Teams](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) con uno specialista tecnico Epic. Assicurarsi che tutti i prerequisiti siano soddisfatti. 

## <a name="connector-setup"></a>Configurazione dei connettori

Per la configurazione del connettore è necessario:

- [Avviare il portale di configurazione del connettore EHR](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [Informazioni sulla configurazione](ehr-admin.md#configuration-information)
- [Approvare o visualizzare la configurazione](ehr-admin.md#approve-or-view-configuration)
- [Rivedere e completare la configurazione](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[Avviare il portale di configurazione del connettore EHR](#launch-the-ehr-connector-configuration-portal)

La configurazione dell'organizzazione sanitaria per l'avvio di visite virtuali Microsoft Teams parte dall'avvio del portale di configurazione del connettore EHR. Configurare una o più organizzazioni per testare l'integrazione. Configurare l'URL di test e produzione nel portale di configurazione. Testare l'integrazione dall'ambiente di test di Epic prima di passare alla produzione.
  
- URL di configurazione del connettore CCE: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)

L'amministratore di Microsoft 365 e il Customer Analyst di Epic della propria organizzazione devono completare le informazioni e i passaggi di integrazione nel portale di configurazione. Per la procedura di configurazione di Epic, contattare l’esperto tecnico di Epic assegnato all'organizzazione.

### <a name="configuration-information"></a>[Informazioni sulla configurazione](#configuration-information)

Questo passaggio deve essere completato dall'**amministratore di Microsoft 365**. Per avviare il processo di configurazione, l'amministratore di Microsoft 365 deve avviare il portale di configurazione del connettore e accedere con le credenziali Microsoft.

Per completare questo passaggio, l'amministratore di Microsoft 365 deve ricevere un valido URL di base FHIR (Fast Health Interoperability Resources) dal proprio esperto tecnico di Epic e il nome utente del Customer Analyst di Epic che approverà la configurazione. Per avviare il processo di configurazione, l'amministratore di Microsoft 365 deve avviare la pagina di configurazione del connettore e accedere con le credenziali Microsoft.

- L'URL di base FHIR è un indirizzo statico corrispondente all'endpoint dell'API FHIR del server. Un URL di esempio è `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.

- Il nome del responsabile approvazione della configurazione è il nome del Customer Analyst di Epic che sarà incaricato di approvare la configurazione nel passaggio successivo. Il Customer Analyst di Epic è una persona all’interno dell'organizzazione con accesso autorizzato a Epic.

  ![Il nome del responsabile approvazione della configurazione viene selezionato da un elenco nel connettore CCE.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[Approvare o visualizzare la configurazione](#approve-or-view-configuration)

L'analista del cliente Epic per l'organizzazione sanitaria che è stata aggiunta come responsabile approvazione deve ora usare lo stesso URL del connettore EHR del passaggio precedente per accedere usando le credenziali Microsoft 365 servizio. Dopo aver completato la convalida, al responsabile approvazione verrà chiesto di accedere con le credenziali di Epic per convalidare l'organizzazione Epic.

> [!Note]
> L'amministratore di Microsoft 365 e il Customer Analyst di Epic nell'organizzazione possono essere la stessa persona. In questo caso, aggiungere il proprio nome utente come responsabile approvazione. Sarà comunque necessario accedere a Epic per convalidare l'accesso. Le informazioni di accesso di Epic vengono usate solo per convalidare l'URL di base FHIR. Con questo accesso, Microsoft non archivia le credenziali o accede ai dati CCE.

  ![Verificare e approvare la configurazione delle credenziali.](../../media/approve-view-configuration.png)

Dopo aver completato l'accesso a Epic, il Customer Analyst **deve** approvare la configurazione. Se la configurazione non è corretta, l'amministratore di Microsoft 365 avrà la possibilità di modificare le configurazioni originali accedendo di nuovo al portale del connettore CCE di Microsoft. 

![Verificare che il connettore CCE sia configurato e l'opzione per modificare la configurazione.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[Rivedere e completare la configurazione](#review-and-finish-the-configuration)

Quando l’amministratore di Epic avrà approvato le informazioni di configurazione, verranno visualizzati i record di integrazione per l’avvio di visite virtuali tra pazienti e provider. Questi record sono necessari per completare la configurazione della visita virtuale in Epic. Per altre informazioni, vedere la guida all'integrazione della telemedicina di Microsoft Teams.

> [!Note]  
> In qualsiasi momento il Customer Analyst di Microsoft 365 o Epic potrà accedere al portale di configurazione per visualizzare i record di integrazione e modificare la configurazione dell'organizzazione, se necessario.

![Vengono visualizzate le informazioni di integrazione.](../../media/finish-configuration.png)

> [!Note]
> Il Customer Analyst di Epic dovrà completare il processo di approvazione per ogni URL FHIR configurato prima dall’amministratore Microsoft.

![Le informazioni di configurazione vengono approvate.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a>Avviare visite virtuali di Teams

Dopo aver completato i passaggi del connettore EHR e la configurazione epica, l'organizzazione è pronta a supportare le video visite con Microsoft Teams.

### <a name="virtual-visit-prerequisites"></a>Prerequisiti per la visita virtuale

- I sistemi devono soddisfare tutti i [prerequisiti per software e browser](../../hardware-requirements-for-the-teams-app.md).

- L'organizzazione del settore sanitario deve aver completato la configurazione tra l'organizzazione Epic e l'organizzazione Microsoft 365.

### <a name="provider-experience"></a>Esperienza del provider

I provider di servizi sanitari dell'organizzazione possono partecipare alle visite virtuali con Microsoft Teams anche dalle applicazioni del provider Epic (Hyperspace, Haiku, Canto). Il pulsante **Begin virtual visit** (Avvia visita virtuale) è incorporato nel flusso del provider.

Caratteristiche principali dell'esperienza del provider:

- I provider possono partecipare alle visite virtuali usando i browser supportati o l'applicazione Microsoft Teams.

- I provider devono eseguire l'accesso singolo con il proprio account Microsoft 365 quando partecipano a una visita virtuale per la prima volta.

- Dopo aver eseguito l'accesso singolo, il provider verrà trasferito direttamente all'appuntamento virtuale in Microsoft Teams. (Il provider dovrà aver eseguito l'accesso a Microsoft Teams).

- Il provider può vedere gli aggiornamenti in tempo reale dei partecipanti che si connettono e disconnettono per un appuntamento specifico. Il provider può vedere quando il paziente è connesso a una visita virtuale.

  ![Esperienza del provider di una visita virtuale con il paziente.](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a>Esperienza del paziente

Il connettore supporta la partecipazione di pazienti alle visite virtuali attraverso le versioni Web e per dispositivo mobile di MyChart. All’ora dell'appuntamento, i pazienti possono iniziare una visita virtuale da MyChart usando il pulsante **Begin virtual visit** (Inizia visita virtuale).

Caratteristiche principali dell'esperienza del paziente:

- I pazienti possono partecipare a visite virtuali da web browser moderni su desktop [e dispositivi mobili senza l'installazione di app.](../mobile-browser-join.md)

- I pazienti possono partecipare a visite virtuali con un solo clic e non è necessario alcun altro account o accesso.

- I pazienti non sono tenuti a creare un account Microsoft o ad accedere con le credenziali per avviare una visita virtuale.

- I pazienti verranno inseriti in una sala di attesa finché il provider di servizi sanitari non parteciperà all'appuntamento e darà loro accesso alla visita virtuale.

- Il test del video e del microfono è disponibile nella sala di attesa prima di partecipare alla visita virtuale.

  ![Esperienza paziente della visita virtuale.](../../media/ehc-virtual-visit-5.png)

> [!Note]
> Epic, MyChart, Haiku e Canto sono marchi registrati di Epic Systems Corporation.

### <a name="privacy-and-location-of-data"></a>Privacy e posizione dei dati

L'integrazione di Teams nei sistemi CCE ottimizza la quantità di dati usati e archiviati durante l'integrazione e i flussi di visita virtuale. La soluzione segue i principi generali della privacy e della gestione dei dati di Teams e le linee guida descritte nell’informativa sulla privacy di Teams.

Il connettore CCE di Microsoft Teams non archivia né trasferisce dati personali identificabili né cartelle sanitarie di pazienti o provider di servizi sanitari dal sistema CCE. Gli unici dati archiviati dal connettore CCE sono l'ID univoco dell'utente CCE, che viene usato durante la configurazione della riunione di Teams. L'ID univoco dell'utente CCE viene archiviato in una delle tre aree geografiche descritte in [Dove sono archiviati i dati dei clienti di Microsoft 365](/microsoft-365/enterprise/o365-data-locations). Tutti i dati di chat, registrazioni e altre fonti immessi in Teams dai partecipanti alla riunione vengono archiviati in base ai criteri di archiviazione esistenti. Per altre informazioni sulla posizione dei dati in Microsoft Teams, visitare [Posizione dei dati in Teams](../../location-of-data-in-teams.md).

## <a name="related-topics"></a>Argomenti correlati

[Teams visite virtuali](ehr-admin-reports.md)