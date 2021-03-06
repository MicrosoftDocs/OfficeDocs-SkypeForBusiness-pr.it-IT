---
title: Usare i modelli di Teams nell'interfaccia di amministrazione
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: aaglick
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come usare i modelli di Teams per creare spazi di collaborazione con canali per diversi argomenti usando modelli preinstallati.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 62bee9c494cc6155a84b30d75ae71528656133be
ms.sourcegitcommit: 113f587a1c09d42b7394ba1195c32cb054bdf31c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508009"
---
# <a name="get-started-with-teams-templates-in-the-admin-center"></a>Introduzione ai modelli di Teams nell'interfaccia di amministrazione

**La possibilità di creare modelli personalizzati non è ancora supportata per i clienti del tipo EDU.**

> [!NOTE]
> I modelli di Teams attualmente non supportano la creazione di canali privati. La creazione di canali privati non è inclusa nelle definizioni dei modelli.

I modelli di Teams sono definizioni predefinite della struttura di un team progettata in base alle esigenze o ai progetti aziendali. Usare modelli predefiniti o crearne di personalizzati. I modelli di Teams consentono di creare rapidamente spazi di collaborazione con canali per diversi argomenti e preinstallare app per inserire contenuti e servizi cruciali. I modelli di Teams offrono una struttura di team predefinita che consente di creare facilmente team coerenti nell'organizzazione. Attualmente è possibile creare un team da un modello in Teams o usando [Microsoft Graph.](get-started-with-teams-templates.md)

Questo articolo descrive le proprietà che possono essere definite nei modelli, quali sono i tipi di modello di base e come è possibile usare alcuni esempi di richieste per creare un team da un modello.

Questo articolo è utile se si è responsabili della pianificazione, della distribuzione e della gestione di più team all'interno dell'organizzazione

## <a name="teams-template-capabilities"></a>Funzionalità dei modelli di Teams

La maggior parte delle proprietà di un team è inclusa e supportata dai modelli. Alcune proprietà e caratteristiche, tuttavia, non sono attualmente supportate. La tabella seguente contiene un breve riepilogo delle funzionalità incluse e di ciò che non è incluso nei modelli di Teams.

| **Proprietà del team supportate dai modelli di Teams** | **Proprietà del team non ancora supportate dai modelli di Teams** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo di modello di base | Appartenenza al team |
| Nome del team | Immagine del team |
| Descrizione del team | Impostazioni del canale |
| Visibilità del team (pubblica o privata) | Connettori |
| Impostazioni del team (ad esempio, membro, guest, @ menzioni) | File e contenuti |
| Canale Autofavorite | |
| App installata | |
| Schede bloccate | |

> [!NOTE]
> Aggiungeremo altre funzionalità di modello nelle versioni future di Microsoft Teams, quindi controlla di nuovo le informazioni più aggiornate sulle proprietà supportate.

## <a name="what-are-base-template-types"></a>Che cosa sono i tipi di modello di base

I tipi di modello di base sono modelli speciali creati da Microsoft per settori specifici. Questi modelli di base contengono spesso app proprietarie che non sono disponibili nello store delle app.

Dopo aver definito un tipo di modello di base, è possibile estendere o sostituire questi modelli speciali con altre proprietà da specificare. Alcuni tipi di modello di base contengono proprietà che non è possibile modificare.

> [!NOTE]
> I modelli di base predefiniti disponibili in Microsoft Teams possono essere duplicati ma non modificati.

| Tipo di modello di base | baseTemplateId | Proprietà disponibili con questo modello di base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adottare Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Angolo campioni</li> <li>Moduli del team</li></ul> App: <ul><li>Wiki</li>  <li>Calendario</li> |
| Gestire un progetto |`com.microsoft.teams.template.ManageAProject`| Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Risorse</li> <li>Pianificazione</li></ul> App:<ul><li>Wiki</li><li>OneNote</li><li>Programmazione</li><li>Elenchi</li>  </ul> |
| Gestire un evento|`com.microsoft.teams.template.ManageAnEvent` | Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Budget</li> <li>Contenuto</li><li>Logistica</li> <li>Pianificazione</li> <li> Marketing e PR</li></ul> App:<ul><li>Wiki</li><li>Sito Web</li> <li>YouTube</li> <li>Programmazione</li> <li>OneNote</li></ul> |
|Dipendenti a bordo|`com.microsoft.teams.template.OnboardEmployees` | Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Chat per i dipendenti</li> <li>Formazione</li></ul>App:<ul><li>Wiki</li><li>Community</li><li>Programmazione</li></ul>|
|Organizzare l'help desk| `com.microsoft.teams.template.OrganizeHelpDesk`|Canali:<ul><li>Generale</li><li>Annunci</li><li>Domande frequenti</li></ul>App:<ul><li>Wiki</li><li>OneNote</li><li>Programmazione </li><li>Complimento</li></ul> |
| Collaborare all'assistenza pazienti| `healthcareWard`| Canali:<ul><li>Generale</li><li>Annunci</li><li>Huddles</li><li>Arrotondamenti</li><li>Personale</li><li>Formazione</li></ul> App: <ul><li>Wiki</li><li>Elenchi  </li></ul>|
| Collaborare in caso di emergenza o evento globale |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Canali: <ul><li>Generale<li>Annunci</li><li>Notizie del mondo</li><li>Continuità aziendale</li><li>Lavoro remoto</li><li>Messaggi interni</li><li>Comms esterni</li><li>Richiesta di approvazione</li><li>Reclami dei clienti</li><li>Kudos</li><li>Aggiornamento della dirigenzia</li></ul>App: <ul><li>Complimento</li><li>Wiki</li><li>Sito Web</li><li>Programmazione</li></ul>|
|Collaborare all'interno di una filiale bancaria| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Canali: <ul><li>Generale<li>Annunci</li><li>Huddles</li><li>Riunioni con i clienti</li><li>Richiesta di approvazione </li><li>Snodato</li><li>Sviluppo di competenze</li><li>Elaborazione dei prestito</li><li>Reclami dei clienti</li><li>Kudos</li><li>Cose divertenti</li><li>Conformità</li></ul>App:<ul><li>Complimento </li></ul>|
|Coordinare la risposta a un incidente| `com.microsoft.teams.template.CoordinateIncidentResponse`|Canali: <ul><li>Generale<li>Annunci</li><li>Logistica</li><li>Pianificazione</li><li>Ripristino</li><li>Urgente</li></ul> App: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Programmazione</li></ul>|
|Ospedale| `healthcareHospital` |Canali: <ul><li>Generale</li><li>Annunci</li><li>Conformità</li><li>Responsabile</li><li>Risorse umane</li><li>Farmacia</li></ul> App: <ul><li>Wiki</li><li>Elenchi  </li></ul>|
|Organizzare uno store| `retailStore` |Canali: <ul><li>Generale<li>Maiusc handoff</li><li>Apprendimento</li></ul> App: <ul><li>Wiki</li><li>Programmazione</li></ul>|
|Qualità e sicurezza |`com.microsoft.teams.template.QualitySafety`|Canali: <ul><li>Generale<li>Annunci</li><li>Riga 1</li><li>Riga 2</li><li>Riga 3</li><li>Sicurezza</li><li>Formazione</li><li>Manutenzione</li><li>Cose divertenti</li></ul> App: <ul><li>Wiki</li><li>Programmazione</li></ul>|
|Vendita al dettaglio - collaborazione con i manager| `retailManagerCollaboration` |Canali: <ul><li>Generale<li>Operazioni</li><li>Apprendimento</li></ul> App: <ul><li>Wiki</li><li>Programmazione</li></ul>|
||||

Per altre informazioni sulle categorie di modelli, vedere le categorie seguenti:

- [Modelli finanziari](financial-teams-templates-in-the-admin-console.md)
- [Modelli generali](general-teams-templates-in-the-admin-console.md)
- [Modelli per enti pubblici](government-teams-templates-in-the-admin-console.md)
- [Modelli sanitari](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Modelli di produzione](manufacturing-teams-templates-in-the-admin-console.md)
- [Modelli di vendita al dettaglio](retail-teams-templates-in-the-admin-console.md)

## <a name="template-size-limits"></a>Limiti di dimensioni dei modelli

I modelli sono limitati a un numero specifico di canali, schede e app.

 > [!Note]
 > È possibile aggiungere altri canali, schede e app al team dopo che è stato creato da un modello.

|Funzionalità | Limite|
|-|-|
|Canali per modello | 15 |
|Schede per canale in un modello | 20 |
|App per modello | 50|
|||

Per [altre informazioni, vedere Limiti](limits-specifications-teams.md) e specifiche di Teams.

## <a name="related-topics"></a>Argomenti correlati

- [Creare un modello di team personalizzato](create-a-team-template.md)
- [Creare un modello di team da un modello di team esistente](create-template-from-existing-template.md)
- [Creare un modello da un team esistente](create-template-from-existing-team.md)
