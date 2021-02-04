---
title: Team per le visite virtuali
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Usare Microsoft teams per configurare il sistema di visite virtuali
ms.openlocfilehash: 4c8511939532a448d5229865618aa308494c7a42
ms.sourcegitcommit: 4bf85d91befb56566130731198518c103a53ebc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "50101334"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a>Visite virtuali con teams-integrazione in EHR

Microsoft teams Electronic Health record (EHR) Connector rende più facile per i medici avviare una visita virtuale o una consultazione con un altro provider in teams direttamente dal sistema EHR. Basato sul cloud Microsoft 365, Microsoft teams consente la collaborazione e la comunicazione semplici e sicure con strumenti di chat, video, Voice e Healthcare in un singolo hub che supporta la conformità con HIPAA, la certificazione HITECH e altro ancora.
La piattaforma di comunicazione e collaborazione dei team rende più facile per i clinici tagliare il groviglio di sistemi frammentati in modo che possano trascorrere il tempo fornendo le migliori cure possibili. Microsoft teams Electronic Health record (EHR) Connector può:
- Avviare le visite virtuali di team sia da provider che da portatori di pazienti.
- Riscrivi i metadati di EHR sugli eventi Connetti e Disconnetti per abilitare il controllo automatico e la conservazione dei record.
- Integrare i flussi di lavoro clinici e del paziente esistenti, consentendo loro di usare Microsoft teams.

  Guarda il video su come gestire le visite virtuali dal portale di EHR.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a>Prima di iniziare

Per poter integrare il connettore EHR, è necessario assicurarsi di avere i prerequisiti seguenti:

- Accesso da usare all'app Microsoft teams nell' [app Orchard Marketplace di Epic](https://apporchard.epic.com/Gallery?id=6153).

- Abbonamento attivo a Microsoft Cloud per l'assistenza sanitaria o all'abbonamento a Microsoft teams EHR Connector standalone offer (applicato solo durante i test di produzione).

- Gli utenti devono avere una licenza Microsoft 365 o Office 365 appropriata che include le riunioni di Microsoft teams.

- Microsoft Teams deve essere adottato e usato all'interno dell'organizzazione.

- Le organizzazioni devono avere con versione epica il 2018 novembre o versioni successive.

- I sistemi devono soddisfare tutti i [prerequisiti del software e del browser](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).

Saranno inoltre necessarie informazioni dalle persone seguenti dell'organizzazione:

- Amministratore di Microsoft 365

- Analista di clienti epici

> [!Note]
> Richiedi il tuo specialista tecnico epico per specificare la Guida all'integrazione di telehealth di Epic-Microsoft teams disponibile nell'Epic Marketplace.

## <a name="connector-setup"></a>Configurazione del connettore

La configurazione del connettore richiede che:

- [Avviare il portale di configurazione di EHR Connector](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [Informazioni sulla configurazione](ehr-admin.md#configuration-information)
- [Approvare o visualizzare la configurazione](ehr-admin.md#approve-or-view-configuration)
- [Rivedere e completare la configurazione](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[Avviare il portale di configurazione di EHR Connector](#launch-the-ehr-connector-configuration-portal)

La configurazione dell'organizzazione sanitaria per avviare le visite virtuali con Microsoft teams inizia con l'avvio del portale di configurazione di EHR Connector. Si configura una singola o più organizzazioni per testare l'integrazione. Configurare l'URL di test e produzione nel portale di configurazione. Testare l'integrazione dall'ambiente di test epico prima di passare alla produzione.
  
- URL di configurazione del connettore EHR: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)

L'amministratore di Microsoft 365 e l'analista di clienti epici dell'organizzazione devono completare i passaggi di informazioni e integrazione nel portale di configurazione. Per i passaggi di configurazione epici, contattare la risorsa specialistica tecnica epica assegnata all'organizzazione.

### <a name="configuration-information"></a>[Informazioni sulla configurazione](#configuration-information)

Questo passaggio deve essere completato dall'amministratore di **Microsoft 365**. L'amministratore di Microsoft 365 deve avviare il portale di configurazione del connettore ed eseguire l'accesso con le credenziali Microsoft per avviare il processo di configurazione.

Per completare questo passaggio, l'amministratore di Microsoft 365 deve ricevere un URL di base per l'interoperabilità rapida (FHIR) valido presso il proprio specialista tecnico epico e il nome utente dell'analista di clienti epici che approverà la configurazione. L'amministratore di Microsoft 365 deve avviare la pagina di configurazione del connettore ed eseguire l'accesso con le credenziali Microsoft per avviare il processo di configurazione.

- L'URL di base di FHIR è un indirizzo statico corrispondente all'endpoint dell'API FHIR del server. Un URL di esempio è `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` .

- Il nome dell'approvatore della configurazione è il nome dell'analista di clienti Epic che sarà responsabile dell'approvazione della configurazione nel passaggio successivo. L'analista di clienti epici è una persona dell'organizzazione con accesso SignIn a Epic.

  ![Il nome dell'approvatore della configurazione viene selezionato da un elenco nel connettore EHR.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[Approvare o visualizzare la configurazione](#approve-or-view-configuration)

L'analista di clienti epici per l'organizzazione sanitaria che è stato aggiunto come approvatore deve ora usare lo stesso URL del connettore EHR del passaggio precedente per accedere con le credenziali di Microsoft 365. Dopo aver eseguito correttamente la convalida, l'approvatore verrà invitato a eseguire l'accesso usando le proprie credenziali epiche per convalidare l'organizzazione epica.

> [!Note]
> L'amministratore di Microsoft 365 e l'analista di clienti epici dell'organizzazione possono essere la stessa persona. In questo caso, Aggiungi il tuo nome utente come responsabile approvazione. È comunque necessario accedere a Epic per convalidare l'accesso. L'accesso Epic viene usato solo per convalidare l'URL di base di FHIR. Microsoft non archivia le credenziali o accede ai dati di EHR con questo accesso.

  ![Verificare e approvare la configurazione delle credenziali.](../../media/approve-view-configuration.png)

Dopo un accesso epico di successo, l'analista del cliente Epic **deve** approvare la configurazione. Se la configurazione non è corretta, l'amministratore di Microsoft 365 avrà la possibilità di modificare le configurazioni originali accedendo di nuovo al portale di Microsoft EHR Connector. 

![Verificare che il connettore EHR sia configurato e che sia possibile modificare la configurazione.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[Rivedere e completare la configurazione](#review-and-finish-the-configuration)

Quando le informazioni di configurazione sono approvate dall'amministratore Epic, verranno presentati i record di integrazione per l'avvio del paziente e del provider. Questi record sono necessari per completare la configurazione della visita virtuale in Epic. Per altre informazioni, vedere la Guida all'integrazione di telehealth di Epic-Microsoft teams.

> [!Note]  
> In qualsiasi momento Microsoft 365 o Epic Customer Analyst può accedere al portale di configurazione per visualizzare i record di integrazione e modificare la configurazione dell'organizzazione, se necessario.

![Vengono visualizzate le informazioni sull'integrazione.](../../media/finish-configuration.png)

> [!Note]
> Il processo di approvazione deve essere completato dall'analista di clienti epici per ogni URL di FHIR configurato dall'amministratore Microsoft.

![Le informazioni di configurazione sono approvate.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a>Avviare visite virtuali di Teams

Dopo aver completato i passaggi del connettore EHR e la configurazione Epic, l'organizzazione è pronta per supportare le visite video con Microsoft teams.

### <a name="virtual-visit-prerequisites"></a>Prerequisiti per la visita virtuale

- I sistemi devono soddisfare tutti i [prerequisiti del software e del browser](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).

- L'organizzazione sanitaria deve aver completato la configurazione tra l'organizzazione Epic e l'organizzazione Microsoft 365.

### <a name="provider-experience"></a>Esperienza del provider

I provider di servizi sanitari dell'organizzazione possono partecipare anche alle visite virtuali con Microsoft teams dalle loro applicazioni di provider epiche (iperspazio, Haiku, canto). Il pulsante **inizia visita virtuale** è incorporato nel flusso del provider.

Caratteristiche principali dell'esperienza del provider:

- I provider possono partecipare a visite virtuali usando i browser supportati o l'applicazione Microsoft teams.

- I provider devono eseguire l'accesso una tantum con il proprio account Microsoft 365 quando si partecipa a una visita virtuale per la prima volta.

- Dopo l'accesso una tantum, il provider verrà portato direttamente all'appuntamento virtuale in Microsoft teams. Il provider deve essere connesso a Microsoft teams.

- Il provider può vedere gli aggiornamenti in tempo reale dei partecipanti connettersi e disconnettersi per un appuntamento specifico. Il provider può vedere quando il paziente è connesso a una visita virtuale.

  ![Esperienza di provider di una visita virtuale con il paziente](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a>Esperienza paziente

Il connettore supporta i pazienti che partecipano a visite virtuali tramite il grafico Web e il dispositivo mobile. Al momento dell'appuntamento, i pazienti possono iniziare una visita virtuale dal grafico con il pulsante **inizia visita virtuale** .

Caratteristiche principali dell'esperienza paziente:

- I pazienti possono partecipare a visite virtuali da Web browser moderni su desktop e dispositivi mobili senza installazione dell'app.

- I pazienti possono partecipare a visite virtuali con un solo clic e non è necessario alcun altro account o accesso.

- I pazienti non sono tenuti a creare un account Microsoft o a eseguire l'accesso per avviare una visita virtuale.

- I pazienti verranno collocati in una sala d'attesa fino a quando il provider di servizi sanitari non si unisce all'appuntamento e li ammette alla visita virtuale.

- Il test del video e del microfono è disponibile nella sala di attesa prima di partecipare alla visita virtuale.

  ![Esperienza paziente della visita virtuale](../../media/ehc-virtual-visit-5.png)

> [!Note]
> Epic, grafico, Haiku e canto sono marchi registrati di Epic Systems Corporation.

### <a name="privacy-and-location-of-data"></a>Privacy e posizione dei dati

L'integrazione dei team nei sistemi EHR ottimizza la quantità di dati che vengono usati e archiviati durante l'integrazione e i flussi di visite virtuali. La soluzione segue i principi e le linee guida generali per la privacy e la gestione dei dati di teams descritti in privacy teams.

Il connettore Microsoft teams EHR non archivia né trasferisce i dati personali identificabili o i record sanitari di pazienti o fornitori di servizi sanitari dal sistema EHR. Gli unici dati archiviati dal connettore EHR sono l'ID univoco dell'utente di EHR, usato durante la configurazione della riunione di teams. L'ID univoco dell'utente di EHR è archiviato in una delle tre aree geografiche descritte in [cui sono archiviati i dati del cliente Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies). Tutte le chat, le registrazioni e altri dati immessi in teams dai partecipanti alla riunione vengono archiviati in base ai criteri di archiviazione esistenti. Per ulteriori informazioni sulla posizione dei dati in Microsoft teams, visitare le [posizioni dei dati in teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).
