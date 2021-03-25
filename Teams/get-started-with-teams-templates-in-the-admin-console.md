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
ms.openlocfilehash: ad7b25a645948bae404a890f88ab29a14150f4d5
ms.sourcegitcommit: 29646ef386f693ecb9b740a473fba4365b187210
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51188318"
---
# <a name="get-started-with-teams-templates-in-the-admin-center"></a>Introduzione ai modelli di Teams nell'interfaccia di amministrazione

**La possibilità di creare modelli personalizzati non è ancora supportata per i clienti EDU.**

> [!NOTE]
> I canali privati e le etichette di riservatezza non sono attualmente supportati nei modelli di Teams. La creazione di canali privati non è inclusa nelle definizioni dei modelli. L'opzione etichetta di riservatezza in **Crea team dal flusso del** modello non verrà applicata al team.

I modelli di Teams sono definizioni predefinite della struttura di un team progettata in base a un'esigenza aziendale o a un progetto. Usare modelli predefiniti o creare un modello personalizzato. I modelli di Teams consentono di creare rapidamente spazi di collaborazione avanzati con canali per diversi argomenti e app di preinstallazione per inserire contenuti e servizi mission-critical. I modelli di Teams offrono una struttura di team predefinita che consente di creare facilmente team coerenti in tutta l'organizzazione. Attualmente è possibile creare un team da un modello in Teams o usando [Microsoft Graph.](get-started-with-teams-templates.md)

Questo articolo descrive le caratteristiche seguenti:

- Proprietà che possono essere definite nei modelli.
- Tipi di modello di base.
- Come è possibile usare alcune richieste di esempio per creare un team da un modello.

Questo articolo è utile se si è responsabili della pianificazione, della distribuzione e della gestione di più team all'interno dell'organizzazione

## <a name="teams-template-capabilities"></a>Funzionalità dei modelli di Teams

La maggior parte delle proprietà di un team sono incluse e supportate dai modelli. Esistono però alcune proprietà e funzionalità attualmente non supportate. La tabella seguente fornisce un breve riepilogo degli elementi inclusi e di ciò che non è incluso nei modelli di Teams.

| **Proprietà del team supportate dai modelli di Teams** | **Proprietà del team non ancora supportate dai modelli di Teams** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo di modello base | Appartenenza al team |
| Nome del team | Immagine del team |
| Descrizione del team | Impostazioni dei canali |
| Visibilità del team (pubblica o privata) | Connettori |
| Impostazioni del team (ad esempio, membro, guest, @ menzioni) | File e contenuti |
| Canale autofavorite | |
| App installata | |
| Schede aggiunte | |

> [!NOTE]
> Nelle versioni future di Microsoft Teams verranno aggiunti altri modelli, quindi controllare di nuovo le informazioni più aggiornate sulle proprietà supportate.

## <a name="what-are-base-template-types"></a>Che cosa sono i tipi di modello di base

I tipi di modello di base sono modelli speciali creati da Microsoft per specifici settori. Questi modelli di base spesso contengono app proprietarie non disponibili nell'app store.

Dopo aver definito un tipo di modello di base, è possibile estendere o eseguire l'override di questi modelli speciali con altre proprietà che si desidera specificare. Alcuni tipi di modello di base contengono proprietà che non possono essere sostituite.

> [!NOTE]
> I modelli di base predefiniti disponibili in Microsoft Teams possono essere duplicati ma non modificati.

| Tipo di modello base | baseTemplateId | Proprietà incluse nel modello base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adottare Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Angolo Champions</li> <li>Moduli del team</li></ul> App: <ul><li>Wiki</li>  <li>Calendario</li> |
| Gestire un progetto |`com.microsoft.teams.template.ManageAProject`| Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Risorse</li> <li>Pianificazione</li></ul> App:<ul><li>Wiki</li><li>OneNote</li><li>Programmazione</li><li>Elenchi</li>  </ul> |
| Gestire un evento|`com.microsoft.teams.template.ManageAnEvent` | Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Budget</li> <li>Contenuto</li><li>Logistica</li> <li>Pianificazione</li> <li> Marketing e pubbliche relazioni</li></ul> App:<ul><li>Wiki</li><li>Sito Web</li> <li>YouTube</li> <li>Programmazione</li> <li>OneNote</li></ul> |
|Dipendenti a bordo|`com.microsoft.teams.template.OnboardEmployees` | Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Chat dei dipendenti</li> <li>Formazione</li></ul>App:<ul><li>Wiki</li><li>Community</li><li>Programmazione</li></ul>|
|Organizzare l'help desk| `com.microsoft.teams.template.OrganizeHelpDesk`|Canali:<ul><li>Generale</li><li>Annunci</li><li>Domande frequenti</li></ul>App:<ul><li>Wiki</li><li>OneNote</li><li>Programmazione </li><li>Complimento</li></ul> |
| Collaborare all'assistenza sanitaria| `healthcareWard`| Canali:<ul><li>Generale</li><li>Annunci</li><li>Briefing</li><li>Giri di visite</li><li>Personale</li><li>Formazione</li></ul> App: <ul><li>Wiki</li><li>Elenchi  </li></ul>|
| Collaborare alla crisi globale o all'evento |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Canali: <ul><li>Generale<li>Annunci</li><li>Notizie del mondo</li><li>Continuità aziendale</li><li>Lavorare in remoto</li><li>Messaggi interni</li><li>Comms esterni</li><li>Richiesta di approvazione</li><li>Reclami dei clienti</li><li>Complimenti</li><li>Aggiornamento per dirigenti</li></ul>App: <ul><li>Complimento</li><li>Wiki</li><li>Sito Web</li><li>Programmazione</li></ul>|
|Collaborare all'interno di una filiale bancaria| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Canali: <ul><li>Generale<li>Annunci</li><li>Briefing</li><li>Riunioni con i clienti</li><li>Richiesta di approvazione </li><li>Coaching</li><li>Sviluppo di competenze</li><li>Elaborazione dei prestiti</li><li>Reclami dei clienti</li><li>Complimenti</li><li>Cose divertenti</li><li>Conformità</li></ul>App:<ul><li>Complimento </li></ul>|
|Coordinare la risposta agli eventi imprevisti| `com.microsoft.teams.template.CoordinateIncidentResponse`|Canali: <ul><li>Generale<li>Annunci</li><li>Logistica</li><li>Pianificazione</li><li>Ripristino</li><li>Urgente</li></ul> App: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Programmazione</li></ul>|
|Ospedale| `healthcareHospital` |Canali: <ul><li>Generale</li><li>Annunci</li><li>Conformità</li><li>Pulizie</li><li>Risorse umane</li><li>Farmacia</li></ul> App: <ul><li>Wiki</li><li>Elenchi  </li></ul>|
|Organizzare un negozio| `retailStore` |Canali: <ul><li>Generale<li>Passaggio di consegne del turno</li><li>Apprendimento</li></ul> App: <ul><li>Wiki</li><li>Programmazione</li></ul>|
|Qualità e sicurezza |`com.microsoft.teams.template.QualitySafety`|Canali: <ul><li>Generale<li>Annunci</li><li>Riga 1</li><li>Riga 2</li><li>Riga 3</li><li>Sicurezza</li><li>Formazione</li><li>Manutenzione</li><li>Cose divertenti</li></ul> App: <ul><li>Wiki</li><li>Programmazione</li></ul>|
|Vendita al dettaglio: collaborazione tra responsabili| `retailManagerCollaboration` |Canali: <ul><li>Generale<li>Operazioni</li><li>Apprendimento</li></ul> App: <ul><li>Wiki</li><li>Programmazione</li></ul>|
||||

Per altre informazioni sulle categorie di modelli, vedere le categorie seguenti:

- [Modelli finanziari](financial-teams-templates-in-the-admin-console.md)
- [Modelli generali](general-teams-templates-in-the-admin-console.md)
- [Modelli per enti pubblici](government-teams-templates-in-the-admin-console.md)
- [Modelli sanitari](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Modelli di produzione](manufacturing-teams-templates-in-the-admin-console.md)
- [Modelli di vendita al dettaglio](retail-teams-templates-in-the-admin-console.md)

## <a name="template-size-limits"></a>Limiti per le dimensioni dei modelli

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
