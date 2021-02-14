---
title: 'Auditing Patients app for Teams IT and compliance admins '
author: dstrome
ms.author: dstrome
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
ms.reviewer: anach
description: Informazioni sul controllo dell'app Pazienti per gli amministratori di Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: ce1851b6d424203f6a4aed8a871209e3a65ce5f8
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803514"
---
# <a name="audit-logs-for-patients-app"></a>Log di controllo per l'app Pazienti

> [!NOTE]
> A partire dal 30 ottobre 2020, l'app Pazienti è stata ritirata e sostituita [dall'app Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams. I dati dell'app Pazienti vengono archiviati nella cassetta postale del gruppo di Office 365 che backup il team. Tutti i dati associati all'app Pazienti vengono conservati in questo gruppo, ma non sono più accessibili tramite l'interfaccia utente. Gli utenti possono creare di nuovo i propri elenchi usando [l'app Elenchi.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>Con Elenchi, i team di assistenza all'interno dell'organizzazione sanitaria possono creare elenchi di pazienti per scenari che vanno da turni e riunioni interdisciplinari del team al monitoraggio generale dei pazienti. Per iniziare, vedere il modello Pazienti in Elenchi. Per altre informazioni su come gestire l'app Elenchi nell'organizzazione, vedere [Gestire l'app Elenchi.](../../manage-lists-app.md)

Un log di controllo per l'attività dell'app Pazienti consente ai team di risposta dopo un incidente di esaminare le modifiche apportate alle cartelle cliniche elettroniche (EMR) o alle informazioni sanitarie dei pazienti e determinare se è necessario apportare modifiche o miglioramenti ai criteri o alle procedure per l'accesso phI agli strumenti per la produttività. Gli eventi del log di controllo riguardano le azioni eseguite tramite l'interfaccia utente dell'app Pazienti.

## <a name="meet-hipaa-requirements"></a>Soddisfare i requisiti HIPAA

In base alle linee guida HIPAA, gli operatori sanitari sono tenuti a tenere traccia di tutto l'accesso al phI, in modo che sia possibile che le modifiche siano verificate. Microsoft si impegna a rispettare i propri clienti aziendali che usano Microsoft Teams e a aiutarli a soddisfare i requisiti e i controlli HIPAA. L'accesso al servizio phi tramite l'app Pazienti è completamente monitorato e i log vengono resi disponibili nel Centro conformità di Microsoft 365, come descritto nell'articolo sulla funzionalità di ricerca [nel log di](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) controllo.

> [!IMPORTANT]
> Il carico di gestione della privacy dei pazienti è posto per legge al provider sanitario. La legge dà diritto alla privacy dei pazienti e richiede che un amministratore IT o un controller HIPAA possa determinare facilmente quale infermiera, medico o assistente sociale ha eseguito l'accesso o modificato i record dei pazienti. Uno degli esempi più comuni di violazione di accesso phi è l'accesso ai pazienti VIP. La funzionalità del log di controllo è necessaria per condurre indagini su eventuali violazioni di accesso PHI e per soddisfare i requisiti HIPAA.

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>Abilitare i log di controllo per l'app Pazienti

Un controllo dipende da diverse configurazioni precedenti:

1. L'amministratore deve collaborare con il proprio provider di servizi FHIR per ottenere un emr in un formato utilizzato dall'app Pazienti. Vedere [l'integrazione di record sanitari elettronici in Microsoft Teams.](patients-app.md)
2. Un amministratore del provider sanitario dovrebbe abilitare l'app pazienti nell'interfaccia di amministrazione di Teams. Per [altre informazioni, vedere](../../teams-app-setup-policies.md) Gestire i criteri di configurazione delle app in Microsoft Teams e gli articoli correlati.
3. L'amministratore deve abilitare i controlli attività, nello stesso modo [in](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin) cui abilita qualsiasi controllo del log attività, come descritto in Prima di iniziare e attivare o disattivare la ricerca nel log [di controllo.](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search) Se la registrazione di controllo è già attivata, non sono necessarie informazioni speciali per l'app Pazienti. Ogni volta che un provider sanitario installa ed esegue l'app in un team, i log di controllo registrano l'attività di PHI.
4. L'amministratore dovrà quindi annunciare la disponibilità dell'app Pazienti e gli operatori sanitari dovranno iniziare a generare attività da includere in un controllo.

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>Eseguire un controllo

Per istruzioni su come eseguire una ricerca nel log attività, vedere [Eseguire ricerche nel log di controllo.](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log)

## <a name="logged-activities-for-patients-app"></a>Attività registrate per l'app Pazienti

L'app Pazienti ha le proprie attività registrate, elencate nella tabella seguente:

|Nome descrittivo |Operazione|Descrizione|
|:---|:---|:---|
| Elenco dei pazienti visualizzato | PatientListView | Un utente ha visualizzato un elenco di pazienti.|
| Elenco di pazienti eliminato | PatientListDelete | Un utente ha eliminato un elenco di pazienti.|
| Paziente aggiunto all'elenco | PatientListAddPatient | Un paziente è stato aggiunto a un elenco di pazienti. |
| Aggiunta una nota per il paziente | PatientNoteAdd | È stata aggiunta una nota a un record del paziente. |
| Data creazione dello schema del paziente | PatientSchemaCreate | È stato creato un set di colonne usate nel record del paziente. |
| Un utente ha avviato un'esportazione | ExportInitiation | I dati dei pazienti sono stati esportati dall'app Pazienti in un file di Excel. Il file verrà salvato nel sito di SharePoint del team. |
| Elenco di pazienti creato | PatientListCreate | Un utente ha creato un elenco di pazienti.|
| Impostare l'elenco dei pazienti predefinito| PatientListDefaultSet| Un utente imposta un elenco specifico come elenco predefinito.|
| Paziente rimosso dall'elenco| PatientListRemovePatient | Un paziente è stato rimosso da un elenco di pazienti. |
| Paziente cercato | PatientSearch | Ha cercato il record di un paziente nel servizio EHR. |
| Schema dei pazienti aggiornato | PatientSchemaUpdate  | È stato aggiornato un set di colonne esistente usato nel record del paziente. |<!-- | Paziente spostato in un altro elenco| PatientMoved | Il record del paziente è stato spostato da un elenco a un altro. |-->
| Elenco di pazienti rinominato | PatientListRename | È stato rinominato un elenco di pazienti. |
| Colonne modificate nell'elenco dei pazienti | PatientListEditColumns | Una colonna in un elenco di pazienti è stata modificata (aggiunta o rimossa). |
| Visualizza i dettagli del paziente | PatientView | Un utente ha visualizzato il record di un paziente.|
| Dettagli del paziente modificati | PatientDetailsEdit | È stato modificato un dettaglio sul record di un paziente. |
| Impostare la connessione EHR | EHRConnectionSet | Impostare l'URL usato per connettersi alla connessione al servizio FHIR di EHR. Esempio: https://<span>api-v8-dstu2.hspconsortium.org/ContosoHospital/open</span>  |
||||

È possibile personalizzare il controllo in base alle esigenze per cercare o filtrare in base a una di queste attività registrate.

Le attività registrate per Microsoft Teams in generale sono descritte nelle [attività di Microsoft Teams.](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities)

## <a name="related-topics"></a>Argomenti correlati

[Eseguire ricerche nel log di controllo](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

[Integrare cartelle cliniche elettroniche in Microsoft Teams](patients-app.md)
