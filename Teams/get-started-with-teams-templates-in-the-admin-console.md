---
title: Usare i modelli di team nell'interfaccia di amministrazione
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
description: Informazioni su come usare i modelli di teams per creare spazi di collaborazione con canali per diversi argomenti usando i modelli preinstallati.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ad35b874f3f11a7e71d61c63cb90a1945c7cc85
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662651"
---
# <a name="get-started-with-teams-templates-in-the-admin-center"></a>Introduzione ai modelli di teams nell'interfaccia di amministrazione

**I modelli personalizzati non sono ancora supportati per i clienti EDU.**

> [!NOTE]
> I modelli di teams attualmente non supportano la creazione di canali privati. La creazione di canali privati non è inclusa nelle definizioni di modello.

I modelli di teams sono definizioni predefinite della struttura di un team progettate attorno a un progetto o una necessità aziendale. Usare i modelli predefiniti o creare un modello personalizzato. I modelli di team consentono di creare rapidamente spazi di collaborazione avanzati con canali per diversi argomenti e preinstallare app per il pull in contenuti e servizi mission-critical. I modelli teams offrono una struttura del team predefinita che consente di creare facilmente team coerenti nell'organizzazione. Attualmente è possibile creare un team da un modello in teams o tramite [Microsoft Graph](get-started-with-teams-templates.md).

In questo articolo vengono illustrate le proprietà che è possibile definire nei modelli, i tipi di modello di base e il modo in cui è possibile usare alcuni esempi di richieste per creare un team da un modello.

Questo articolo è per te, se sei responsabile per pianificare, distribuire e gestire più team in tutta l'organizzazione

## <a name="teams-template-capabilities"></a>Funzionalità del modello Teams

La maggior parte delle proprietà di un team è inclusa e supportata dai modelli. Tuttavia, esistono alcune proprietà e funzionalità che non sono attualmente supportate. La tabella seguente fornisce un breve riepilogo degli elementi inclusi e dei modelli di team non inclusi.

| **Proprietà del team supportate dai modelli di Teams** | **Proprietà del team non ancora supportate dai modelli di Teams** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo di modello di base | Appartenenza al team |
| Nome del team | Immagine del team |
| Descrizione del team | Impostazioni canale |
| Visibilità del team (pubblico o privato) | Connettori |
| Impostazioni del team (ad esempio, membro, Guest, @ menzioni) | File e contenuti |
| Canale preferito | |
| App installata | |
| Schede aggiunte | |

> [!NOTE]
> Aggiungeremo altre funzionalità modello nelle versioni future di Microsoft teams, quindi controlla le informazioni più aggiornate sulle proprietà supportate.

## <a name="what-are-base-template-types"></a>Informazioni sui tipi di modello di base

I tipi di modello di base sono modelli speciali creati da Microsoft per settori specifici. Questi modelli di base contengono spesso app proprietarie che non sono disponibili nell'App Store.

Una volta definito un tipo di modello di base, è possibile estendere o sostituire questi modelli speciali con altre proprietà che si desidera specificare. Alcuni tipi di modello di base contengono proprietà che non è possibile eseguire l'override.

> [!NOTE]
> I modelli di base predefiniti forniti in Microsoft teams possono essere duplicati ma non modificati.

| Tipo di modello di base | baseTemplateId | Proprietà disponibili con questo modello di base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adottare Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Canali <ul><li>Generale</li> <li>Annunci</li> <li>Champions Corner</li> <li>Moduli team</li></ul> Applicazioni <ul><li>Wiki</li>  <li>Calendario</li> |
| Gestire un progetto |`com.microsoft.teams.template.ManageAProject`| Canali <ul><li>Generale</li> <li>Annunci</li> <li>Risorse</li> <li>Pianificazione</li></ul> Applicazioni<ul><li>Wiki</li><li>OneNote</li><li>Programmazione</li><li>Elenchi</li>  </ul> |
| Gestire un evento|`com.microsoft.teams.template.ManageAnEvent` | Canali <ul><li>Generale</li> <li>Annunci</li> <li>Budget</li> <li>Contenuto</li><li>Logistica</li> <li>Pianificazione</li> <li> Marketing e PR</li></ul> Applicazioni<ul><li>Wiki</li><li>Sito Web</li> <li>YouTube</li> <li>Programmazione</li> <li>OneNote</li></ul> |
|Dipendenti a bordo|`com.microsoft.teams.template.OnboardEmployees` | Canali <ul><li>Generale</li> <li>Annunci</li> <li>Chat per dipendenti</li> <li>Formazione</li></ul>Applicazioni<ul><li>Wiki</li><li>Comunità</li><li>Programmazione</li></ul>|
|Organizzare help desk| `com.microsoft.teams.template.OrganizeHelpDesk`|Canali<ul><li>Generale</li><li>Annunci</li><li>Domande frequenti</li></ul>Applicazioni<ul><li>Wiki</li><li>OneNote</li><li>Programmazione </li><li>Lode</li></ul> |
| Collaborare alla cura del paziente| `healthcareWard`| Canali<ul><li>Generale</li><li>Annunci</li><li>Huddles</li><li>Arrotonda</li><li>Personale</li><li>Formazione</li></ul> Applicazioni <ul><li>Wiki</li><li>Elenchi  </li></ul>|
| Collaborare alla crisi o all'evento globale |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Canali <ul><li>Generale<li>Annunci</li><li>Notizie dal mondo</li><li>Continuità aziendale</li><li>Funzionamento remoto</li><li>Comunicazioni interne</li><li>Comunicazioni esterne</li><li>Richiesta di approvazione</li><li>Reclami dei clienti</li><li>Complimenti</li><li>Aggiornamento esecutivo</li></ul>Applicazioni <ul><li>Lode</li><li>Wiki</li><li>Sito Web</li><li>Programmazione</li></ul>|
|Collaborare all'interno di una filiale bancaria| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Canali <ul><li>Generale<li>Annunci</li><li>Huddles</li><li>Riunioni con i clienti</li><li>Richiesta di approvazione </li><li>Coaching</li><li>Sviluppo delle competenze</li><li>Elaborazione di prestiti</li><li>Reclami dei clienti</li><li>Complimenti</li><li>Cose divertenti</li><li>Conformità</li></ul>Applicazioni<ul><li>Lode </li></ul>|
|Coordinare le risposte agli incidenti| `com.microsoft.teams.template.CoordinateIncidentResponse`|Canali <ul><li>Generale<li>Annunci</li><li>Logistica</li><li>Pianificazione</li><li>Recupero</li><li>Urgente</li></ul> Applicazioni <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Programmazione</li></ul>|
|Ospedale| `healthcareHospital` |Canali <ul><li>Generale</li><li>Annunci</li><li>Conformità</li><li>Custodia</li><li>Risorse umane</li><li>Farmacia</li></ul> Applicazioni <ul><li>Wiki</li><li>Elenchi  </li></ul>|
|Organizzare uno Store| `retailStore` |Canali <ul><li>Generale<li>Cambio di consegna</li><li>Apprendimento</li></ul> Applicazioni <ul><li>Wiki</li><li>Programmazione</li></ul>|
|Qualità e sicurezza |`com.microsoft.teams.template.QualitySafety`|Canali <ul><li>Generale<li>Annunci</li><li>Riga 1</li><li>Linea 2</li><li>Linea 3</li><li>Sicurezza</li><li>Formazione</li><li>Manutenzione</li><li>Cose divertenti</li></ul> Applicazioni <ul><li>Wiki</li><li>Programmazione</li></ul>|
|Collaborazione al dettaglio-Manager| `retailManagerCollaboration` |Canali <ul><li>Generale<li>Operazioni</li><li>Apprendimento</li></ul> Applicazioni <ul><li>Wiki</li><li>Programmazione</li></ul>|
||||

Per altre informazioni sulle categorie di modelli, vedere le categorie seguenti:

- [Modelli finanziari](financial-teams-templates-in-the-admin-console.md)
- [Modelli generali](general-teams-templates-in-the-admin-console.md)
- [Modelli governativi](government-teams-templates-in-the-admin-console.md)
- [Modelli di assistenza sanitaria](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Modelli di produzione](manufacturing-teams-templates-in-the-admin-console.md)
- [Modelli di vendita al dettaglio](retail-teams-templates-in-the-admin-console.md)

## <a name="template-size-limits"></a>Limiti per le dimensioni del modello

I modelli sono limitati a un numero specifico di canali, schede e app.

 > [!Note]
 > Dopo la creazione da un modello, è possibile aggiungere al team più canali, schede e app.

|Funzionalità | Limite|
|-|-|
|Canali per modello | 15 |
|Schede per canale in un modello | 20 |
|App per modello | 50|
|||

Per altre informazioni, vedere [limiti e specifiche dei team](limits-specifications-teams.md) .

## <a name="related-topics"></a>Argomenti correlati

- [Creare un modello di team personalizzato](create-a-team-template.md)
- [Creare un modello di team da un modello di Team esistente](create-template-from-existing-template.md)
- [Creare un modello da un team esistente](create-template-from-existing-team.md)
