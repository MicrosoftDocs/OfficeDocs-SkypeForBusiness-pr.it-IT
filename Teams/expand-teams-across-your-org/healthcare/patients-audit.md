---
title: 'App per il controllo dei pazienti per team IT e amministratori di conformità '
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
description: App pazienti per amministratori Teams
ms.openlocfilehash: fbbb3361968ae928638fedca09fbd8d4c2ff33b6
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780405"
---
# <a name="audit-logs-for-patients-app"></a>Log di controllo per l'app Pazienti

Un log di controllo per l'attività dell'app pazienti consente ai team di risposta dopo l'incidente di esaminare le modifiche apportate ai record medici elettronici (EMR) o alle informazioni sanitarie del paziente (PHI) e determinare se sono necessarie modifiche o miglioramenti di criteri o procedure per l'accesso a PHI in strumenti di produttività. Gli eventi del log di controllo coprono le azioni eseguite tramite l'interfaccia utente dell'app patients.

## <a name="meet-hipaa-requirements"></a>Soddisfare i requisiti HIPAA

In base alle linee guida HIPAA, i provider di servizi sanitari sono tenuti a conservare i record di tutti gli accessi a PHI, in modo che sia possibile verificare le modifiche. Microsoft si impegna a raggiungere i clienti aziendali con Microsoft teams e ad aiutarli a soddisfare i requisiti e i controlli HIPAA. L'accesso a PHI tramite l'app pazienti è completamente registrato e i registri vengono resi disponibili nel centro sicurezza e conformità di M365, come descritto nell'articolo della [funzionalità Ricerca log di controllo](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) .

> [!IMPORTANT]
> L'onere di mantenere la privacy del paziente viene posto sul provider di servizi sanitari per legge. La legge dà diritto ai pazienti alla privacy e richiede che un amministratore IT o un controller HIPAA possa facilmente determinare quale infermiera, clinico o assistente sociale abbia acceduto o alterato i record del paziente. Uno degli esempi più comuni di violazione di accesso di PHI è l'accesso ai pazienti VIP. La funzionalità del log di controllo è necessaria per eseguire indagini su eventuali violazioni di Access PHI e per soddisfare i requisiti HIPAA.

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>Abilitare i log di controllo per l'app patients

Un controllo è dipendente da diverse configurazioni precedenti:

1. L'amministratore dovrebbe collaborare con il proprio provider di servizi di FHIR per avere EMR in un formato usato dall'app patients. Vedere [integrazione di record sanitari elettronici in Microsoft teams](patients-app.md).
2. Un amministratore del provider di servizi sanitari deve abilitare l'app patients nell'interfaccia di amministrazione di teams. Per altre informazioni, Vedi [gestire i criteri di configurazione delle app in Microsoft teams](../../teams-app-setup-policies.md) e articoli correlati.
3. L'amministratore deve abilitare gli audit delle attività in Office 365, allo stesso modo in cui abilitano qualsiasi controllo del log attività in Office 365, come descritto [prima di iniziare](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin) e [attivare o disattivare la ricerca nel log di controllo](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search). Se la registrazione di controllo è già attiva, non è necessario nulla di speciale per l'app pazienti. Ogni volta che un provider di servizi sanitari installa e gestisce l'app all'interno di un team, i log di controllo registrano la loro attività PHI.
4. L'amministratore dovrà quindi annunciare la disponibilità dell'app patients e gli operatori sanitari dovrebbero iniziare a generare attività da includere in un controllo.

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>Eseguire un controllo

Per istruzioni su come eseguire una ricerca nel log attività, vedere [eseguire una ricerca nel log di controllo](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log).

## <a name="logged-activities-for-patients-app"></a>Attività registrate per l'app pazienti

L'app patients ha le proprie attività registrate, elencate nella tabella seguente:

|Nome descrittivo |Operazione|Descrizione|
|:---|:---|:---|
| Elenco dei pazienti in visualizzazione | PatientListView | Un utente ha visualizzato un elenco di pazienti.|
| Elenco dei pazienti eliminati | PatientListDelete | Un utente ha eliminato un elenco di pazienti.|
| Aggiunta di un paziente all'elenco | PatientListAddPatient | Un paziente è stato aggiunto a un elenco di pazienti. |
| Nota aggiunta per il paziente | PatientNoteAdd | È stata aggiunta una nota a un record paziente. |
| Schema del paziente creato | PatientSchemaCreate | È stato creato un set di colonne usato nel record del paziente. |
| L'utente ha avviato un'esportazione | ExportInitiation | I dati del paziente sono stati esportati dall'app pazienti in un file di Excel. Il file verrà salvato nel sito del team di SharePoint. |
| Elenco dei pazienti creato | PatientListCreate | Un utente ha creato un elenco di pazienti.|
| Impostare l'elenco dei pazienti predefinito| PatientListDefaultSet| Un utente imposta un determinato elenco come elenco predefinito.|
| Rimozione di un paziente dall'elenco| PatientListRemovePatient | Un paziente è stato rimosso da un elenco di pazienti. |
| Paziente cercato | PatientSearch | Ha cercato un record paziente nel servizio EHR. |
| Schema paziente aggiornato | PatientSchemaUpdate  | Aggiornamento di un set di colonne esistente usato nel record del paziente. |<!-- | Spostamento di un paziente in un altro elenco| PatientMoved | Il record del paziente è stato spostato da un elenco a un altro. |-->
| Elenco dei pazienti rinominato | PatientListRename | È stato rinominato un elenco di pazienti. |
| Colonne modificate nell'elenco dei pazienti | PatientListEditColumns | È stata modificata una colonna in un elenco di pazienti (aggiunti o rimossi). |
| Dettagli del paziente visualizzati | PatientView | Un utente ha visualizzato un record paziente.|
| Dettagli del paziente modificati | PatientDetailsEdit | È stato modificato un dettaglio di un record paziente. |
| Impostare la connessione EHR | EHRConnectionSet | Imposta l'URL usato per connettersi alla connessione al servizio EHR FHIR. Esempio: https://<span>API-V8-dstu2.hspconsortium.org/ContosoHospital/Open</span>  |
||||

È possibile personalizzare il controllo in base alle esigenze per cercare o filtrare le attività registrate.

Le attività registrate per Microsoft teams in generale sono descritte nelle [attività di Microsoft teams](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities).

## <a name="related-topics"></a>Argomenti correlati

[Eseguire una ricerca nel log di controllo](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

[Integrare cartelle cliniche elettroniche in Microsoft Teams](patients-app.md)
