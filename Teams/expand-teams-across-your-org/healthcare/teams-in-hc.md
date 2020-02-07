---
title: Guida introduttiva a Teams per le organizzazioni del settore sanitario
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Guida introduttiva a Teams per le organizzazioni del settore sanitario
ms.openlocfilehash: f246e0ab5abd412947ceeb871b16f464001b89bb
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827624"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Guida introduttiva a Teams per le organizzazioni del settore sanitario

Microsoft teams offre una serie di funzionalità utili per ospedali e altre organizzazioni sanitarie. Le caratteristiche dei team sono in fase di sviluppo per aiutare gli ospedali:

- Coordinamento e collaborazione per l'assistenza
- Messaggistica sicura
- Telemedicina
- Integrazione di EHR (Electronic Healthcare record) 
- Integrazione di i FIRSTLINE Worker System 

Il contenuto di questa sezione si basa sulle funzionalità fondamentali dei team, ad esempio riunioni, chiamate e messaggistica, e presuppone che siano già stati distribuiti team nell'organizzazione. Se non sono stati ancora distribuiti team, iniziare a leggere [come implementare Microsoft teams](../../How-to-roll-out-teams.md).

## <a name="care-coordination---microsoft-teams-patients-app"></a>Coordinamento delle cure-app Microsoft teams patients

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft Teams ha ora una soluzione di coordinamento delle cure specifiche per le organizzazioni sanitarie per aiutarli a fornire la migliore assistenza per i pazienti. Il nocciolo della soluzione di coordinamento delle cure, l'app Microsoft teams patients, è un'app per la scheda First party che si integra con i sistemi Electronic Health record (EHR) che usano un'interfaccia[FHIR](https://www.hl7.org/fhir/)(Fast Healthcare Resources) per fornire preziose informazioni mediche in Microsoft teams in contesto per consentire la collaborazione e la comunicazione clinica.  

La soluzione di coordinamento delle cure può interfacciarsi con fornitori di software indipendenti leader (ISV) che possono connettere l'app patients ai sistemi EHR usando standard di dati sanitari esistenti come HL7v2 e FHIR. Partner Microsoft con i seguenti leader del settore per stabilire l'integrazione elettronica dei record sanitari con i team:

- Datica (tramite l'offerta [CMI](https://datica.com/compliant-managed-integration/) )
- Infor Cloverleaf (tramite il [Bridge infor FHIR](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))
- Redox (tramite il [Server R ^ FHIR](https://www.redoxengine.com/fhir/))
- Dapasoft (tramite [corolar in FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

Un partner di integrazione e interoperabilità di EHR che prova ad implementare Microsoft teams per un'organizzazione di provider di servizi sanitari deve garantire all'app patients una connessione sicura e autenticata con i sistemi di EHR dell'organizzazione del provider di servizi sanitari. In questo modo, il flusso unidirezionale (di sola lettura) dei record paziente rilevanti viene attivato nell'app patients. L'app patients comprende il formato FHIR, in modo che il partner sia anche responsabile della trasformazione dei dati aggregati da vari altri formati come HL7v2 e così via in FHIR DSTU2 o STU3.

<br>

![Illustrazione che evidenzia il coordinamento e la collaborazione all'assistenza](../../media/ehr-1.png)

<br>

L'app patients si integra con i sistemi Electronic Health Records (EHR) e consente ai provider di assistenza di comunicare informazioni sulle cure dei pazienti in tempo reale all'interno della piattaforma sicura di teams. L'app pazienti è il primo investimento importante nell'area di coordinamento delle cure che mira ad affrontare le sfide seguenti:

- Scarsa efficienza nelle consegne e comunicazioni critiche attraverso l'esperienza del paziente
- Informazioni silos che creano oneri amministrativi
- Insoddisfazione tra i clinici con strumenti di collaborazione complessi e frammentati
- Coordinamento delle cure in-persona inefficiente che può bruciare troppo tempo clinico molto costoso

Microsoft teams consente a medici, clinici, infermieri e altri membri del personale di collaborare in modo efficiente:

- Partecipare a un singolo team virtualizzato che lavora e collabora ai documenti di Office
- Avere conversazioni persistenti su pazienti diversi che richiedono attenzione
- Usare i canali con le schede per strutturare il proprio lavoro, con ulteriori informazioni sulle schede a cui possono aggiungere le origini dati
- Uso delle riunioni di canale con la potenza dei team audio, video, condivisione dello schermo, registrazione e funzionalità di trascrizione per gestire le riunioni quotidiane
- Usando l'app pazienti per curare un elenco di pazienti ad alto rischio che devono essere controllati e i loro dettagli più recenti dal sistema EHR. L'app patients stessa aggiunge le caratteristiche seguenti a Microsoft teams:

    - Possibilità di creare più elenchi di pazienti all'interno di un singolo canale.
    - Possibilità di visualizzare e ordinare le informazioni visualizzate sui pazienti tramite colonne configurabili.
    - Possibilità di eseguire il provisioning automatico dell'app tramite un modello di team.
    - Disponibile nell'app teams per iOS e Android per i primi operatori sanitari per dispositivi mobili, oltre a Microsoft teams Web e desktop client.
    - Supporto per le versioni di FHIR DSTU2 e STU3 tramite l'analisi dell'istruzione di conformità.
    - Registri di controllo per tutte le azioni di visualizzazione e ricerca nell'interfaccia utente per salvaguardare le linee guida di PHI per HIPAA.

L'app pazienti si basa sulla piattaforma di estensibilità teams e sfrutta il framework delle schede per visualizzare il contenuto del paziente avanzato all'interno di un canale. Per altre informazioni sulle app di altri team e sulla piattaforma stessa, vedere [app per Microsoft teams](/microsoftteams/platform/concepts/apps/apps-overview).  

> [!NOTE]
> L'app patients è in anteprima privata e l'interfaccia FHIR è in versione beta. Le versioni rilasciate non dovrebbero essere compatibili con la versione precedente.

![Screenshot dell'app pazienti su dispositivi desktop e mobili](../../media/ehr-2.png)

Vedere [integrazione di record sanitari elettronici in Microsoft teams](patients-app.md) per dettagli sull'implementazione.

## <a name="templates"></a>Modelli

I nuovi modelli per la creazione di team sono stati sviluppati per applicarsi a un ambiente ospedaliero e più presto sono attesi. In questo modo è più semplice creare team che gli operatori sanitari usano per coordinare le cure per i pazienti in diversi reparti o corsi. Vedere [Introduzione ai modelli di team per le organizzazioni sanitarie](healthcare-templates.md). I team possono essere avviati per i reparti interni, ad esempio cardiologia o per i corsi di assistenza, e altri modelli sono in sviluppo.

## <a name="secure-messaging"></a>Messaggistica sicura

La messaggistica sicura supporta la collaborazione all'interno di team di assistenza, incluse diverse nuove caratteristiche:

- Un mittente del messaggio può impostare una priorità speciale per il messaggio, in modo che il destinatario venga notificato ripetutamente fino a quando non legge il messaggio.
- Un mittente del messaggio può richiedere una conferma di lettura, in modo che venga notificato quando un messaggio inviato è stato letto dal destinatario del messaggio.


Insieme, queste funzionalità permettono una maggiore attenzione ai messaggi urgenti e alla fiducia che il messaggio è stato ricevuto e letto. I nuovi team di assistenza che usano queste funzionalità possono essere creati per ogni singolo paziente. Queste caratteristiche sono basate su criteri e possono essere assegnate a singoli o a Team interi.

Per ulteriori informazioni, vedere [Introduzione ai criteri di messaggistica sicura per le organizzazioni sanitarie](messaging-policies-hc.md) .

Anche correlato alla messaggistica sicura è la possibilità di avere altri tenant federati da organizzazioni sanitarie, consentendo una comunicazione intertenant più ricca. vedere [gestire l'accesso esterno (Federazione) in Microsoft teams](../../manage-external-access.md).

## <a name="firstline-worker-integration"></a>Integrazione di i FIRSTLINE Worker

Microsoft teams si integra con I FIRSTLINE Worker, che può essere usato per coordinare le caratteristiche di personale di spostamento e altro ancora.

 Vedere gli articoli seguenti:

- [Spostare i team di Microsoft StaffHub in turni in Microsoft Teams](../shifts/move-staffhub-teams-to-shifts-in-teams.md)

- [Gestire l'app turni per l'organizzazione in Microsoft Teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
