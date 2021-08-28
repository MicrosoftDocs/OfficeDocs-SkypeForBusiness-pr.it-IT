---
title: 'App Pazienti di controllo per Teams amministratori IT e conformità '
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
ms.reviewer: anach
description: Informazioni sul controllo dell'app Pazienti per Teams amministratori
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: b65dae205f7f7438482847ceb07e37a64609a534
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595060"
---
# <a name="audit-logs-for-patients-app"></a>Log di controllo per l'app Pazienti

> [!NOTE]
> A partire dal 30 ottobre 2020, l'app Pazienti è stata ritirata e sostituita dall’app [Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams. I dati dell’app Pazienti vengono archiviati nella casella postale di gruppo del gruppo di Office 365 che supporta il team. Tutti i dati associati all'app Pazienti vengono conservati in questo gruppo, ma non è più possibile accedervi tramite l'interfaccia utente. Gli utenti possono ricreare i propri elenchi utilizzando l’app [Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Con Elenchi, i team di assistenza della tua organizzazione sanitaria possono creare elenchi di pazienti per scenari che vanno da turni e riunioni di team interdisciplinari al monitoraggio generale dei pazienti. Estrai il modello Coordinamento pazienti in Elenchi per iniziare. Per ulteriori informazioni su come gestire l'app Elenchi nella tua organizzazione, vedere [Gestire l’app Elenchi](../../manage-lists-app.md).

Un log di controllo per l'attività dell'app Pazienti consente ai team di risposta dopo gli incidenti di rivedere le modifiche apportate alle cartelle cliniche elettroniche (EMR) o alle informazioni sull'assistenza sanitaria dei pazienti (PHI) di un paziente e determinare se sono necessarie modifiche o miglioramenti ai criteri o alle procedure per l'accesso al phI negli strumenti di produttività. Gli eventi del log di controllo riguardano le azioni eseguite tramite l'interfaccia utente dell'app Pazienti.

## <a name="meet-hipaa-requirements"></a>Soddisfare i requisiti HIPAA

In base alle linee guida HIPAA, i provider di servizi sanitari sono tenuti a tenere traccia di tutti gli accessi a PHI, in modo da poter controllare le modifiche. Microsoft si impegna a soddisfare i propri clienti aziendali Microsoft Teams e a aiutarli a soddisfare i requisiti e i controlli HIPAA. L'accesso a PHI tramite l'app Patients è completamente monitorato e i log vengono resi disponibili nel Centro conformità di Microsoft 365, come descritto nell'articolo sulla funzionalità di ricerca [nel log di](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) controllo.

> [!IMPORTANT]
> L'onere di mantenere la privacy dei pazienti è posto per legge al provider sanitario. La legge autorizza i pazienti alla privacy e richiede che un amministratore IT o un controller HIPAA possa determinare facilmente quale infermiera, medico o assistente sociale ha eseguito l'accesso o modificato i record dei pazienti. Uno degli esempi più comuni di violazione dell'accesso phI è l'accesso ai pazienti VIP. La funzionalità del log di controllo è necessaria per condurre indagini su eventuali violazioni di accesso phI e per soddisfare i requisiti HIPAA.

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>Abilitare i log di controllo per l'app Pazienti

Un controllo dipende da diverse configurazioni precedenti:

1. L'amministratore dovrebbe collaborare con il provider di servizi FHIR per avere EMR in un formato usato dall'app Patients. 
2. Un amministratore del provider di assistenza sanitaria dovrebbe abilitare l'app pazienti nell Teams di amministrazione. Per [altre informazioni,](../../teams-app-setup-policies.md) vedere Gestire i criteri di configurazione delle app Microsoft Teams e gli articoli correlati.
3. L'amministratore dovrebbe abilitare i controlli attività, nello stesso modo [in](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin) cui abilita qualsiasi controllo del log attività, come descritto in Prima di iniziare e Attivare o disattivare la ricerca nel log [di controllo.](/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search) Se la registrazione di controllo è già attivata, non è necessaria alcuna funzionalità speciale per l'app Pazienti. Ogni volta che un provider di servizi sanitari installa ed esegue l'app all'interno di un team, i log di controllo registrano l'attività phI.
4. L'amministratore dovrà quindi annunciare la disponibilità dell'app Pazienti e gli operatori sanitari dovranno iniziare a generare attività da includere in un controllo.

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>Eseguire un controllo

Per istruzioni sull'esecuzione di una ricerca nel log attività, vedere [Eseguire una ricerca nel log di controllo.](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log)

## <a name="logged-activities-for-patients-app"></a>Attività registrate per l'app Pazienti

L'app Pazienti ha le proprie attività registrate, elencate nella tabella seguente:

|Nome descrittivo | Operazione | Descrizione|
|:---|:---|:---|
| Elenco dei pazienti visualizzato | PatientListView | Un utente ha visualizzato un elenco di pazienti.|
| Elenco di pazienti eliminato | PatientListDelete | Un utente ha eliminato un elenco di pazienti.|
| Aggiunto paziente all'elenco | PatientListAddPatient | Un paziente è stato aggiunto a un elenco di pazienti. |
| Aggiunta di una nota per il paziente | PatientNoteAdd | È stata aggiunta una nota a un record del paziente. |
| Schema del paziente creato | PatientSchemaCreate | È stato creato un set di colonne usate nel record del paziente. |
| L'utente ha avviato un'esportazione | ExportInitiation | I dati dei pazienti sono stati esportati dall'app Pazienti in un file Excel pazienti. Il file verrà salvato nel sito SharePoint team. |
| Elenco di pazienti creato | PatientListCreate | Un utente ha creato un elenco di pazienti.|
| Impostare l'elenco dei pazienti predefinito| PatientListDefaultSet| Un utente imposta un determinato elenco come elenco predefinito.|
| Paziente rimosso dall'elenco| PatientListRemovePatient | Un paziente è stato rimosso da un elenco di pazienti. |
| Paziente cercato | PatientSearch | È stata cercata una registrazione del paziente nel servizio EHR. |
| Schema del paziente aggiornato | PatientSchemaUpdate  | È stato aggiornato un set di colonne esistente usato nel record del paziente. |<!-- | Il paziente è stato spostato in un elenco diverso| PatientMoved | Il record del paziente è stato spostato da un elenco a un altro. |-->
| Elenco di pazienti rinominato | PatientListRename | Un elenco di pazienti è stato rinominato. |
| Colonne modificate nell'elenco dei pazienti | PatientListEditColumns | Una colonna in un elenco di pazienti è stata modificata (aggiunta o rimossa). |
| Dettagli dei pazienti visualizzati | PatientView | Un utente ha visualizzato un record del paziente.|
| Dettagli dei pazienti modificati | PatientDetailsEdit | È stato modificato un dettaglio su un record del paziente. |
| Impostare la connessione EHR | EHRConnectionSet | Impostare l'URL usato per connettersi alla connessione al servizio EHR FHIR. Esempio: https://<span>api-v8-dstu2.hspconsortium.org/ContosoHospital/open</span>  |

È possibile personalizzare il controllo in base alle esigenze per cercare o filtrare in base a una di queste attività registrate.

Le attività registrate per Microsoft Teams in generale sono descritte in [Microsoft Teams attività.](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities)

## <a name="related-topics"></a>Argomenti correlati

[Eseguire una ricerca nel log di controllo](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
