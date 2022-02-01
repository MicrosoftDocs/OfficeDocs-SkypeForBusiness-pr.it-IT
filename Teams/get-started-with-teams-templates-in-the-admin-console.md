---
title: Introduzione ai modelli di team nell'interfaccia Teams di amministrazione
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: yinchang
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni sui modelli di team e su come gestirli nell'Microsoft Teams di amministrazione.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: dd07e375a35ea212bccd988395b5c1adbd721011
ms.sourcegitcommit: d3c48f0c147cf0c47d5eb4ea1128b5bca13be718
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2022
ms.locfileid: "62299051"
---
# <a name="get-started-with-team-templates-in-the-teams-admin-center"></a>Introduzione ai modelli di team nell'interfaccia Teams di amministrazione

**La possibilità di creare modelli personalizzati non è ancora supportata per i clienti EDU.**

> [!NOTE]
> I canali privati e le etichette di riservatezza non sono attualmente supportati nei modelli di team. La creazione di canali privati non è inclusa nelle definizioni dei modelli. L'opzione etichetta di riservatezza in **Crea team dal flusso del** modello non verrà applicata al team.

## <a name="overview"></a>Panoramica

Un modello di team in Microsoft Teams è una definizione della struttura di un team progettata in base a un'esigenza aziendale o a un progetto. Gli amministratori possono usare i modelli per distribuire facilmente team coerenti all'interno dell'organizzazione. Con i modelli, gli utenti possono creare rapidamente spazi di collaborazione con impostazioni, canali e app predefiniti.

È possibile gestire i modelli di team nell'Microsoft Teams di amministrazione o usando PowerShell. È possibile usare i modelli predefiniti forniti e creare [anche modelli personalizzati](#create-your-own-team-templates). È anche possibile [applicare criteri di modello](#apply-team-template-policies) per controllare quali modelli sono disponibili per gli utenti in Teams.

Questo articolo offre una panoramica dell'uso dei modelli di team nell'Teams di amministrazione. Verranno fornite informazioni sulle proprietà supportate nei modelli, sui modelli predefiniti forniti, sui limiti delle dimensioni dei modelli, su come creare e gestire i modelli e altro ancora.

> [!NOTE]
> Gli utenti possono [creare team da modelli di team](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c) predefiniti o personalizzati nell'app Teams team. Gli sviluppatori possono anche creare team a livello di programmazione da modelli di team predefiniti usando Microsoft Graph. Per altre informazioni, vedere [Introduzione ai modelli di team con Microsoft Graph](get-started-with-teams-templates.md).

## <a name="team-template-capabilities"></a>Funzionalità dei modelli di team

La maggior parte delle proprietà di un team sono incluse e supportate dai modelli di team. Esistono però alcune proprietà e funzionalità attualmente non supportate. Ecco un riepilogo di ciò che è incluso e di ciò che non è incluso nei modelli di team.

| **Proprietà del team supportate dai modelli di team** | **Proprietà del team non ancora supportate dai modelli di team** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo di modello | Appartenenza al team |
| Nome del team | Immagine del team |
| Descrizione del team | Impostazioni dei canali |
| Visibilità del team (pubblica o privata) | Connettori |
| Impostazioni del team (ad esempio, membro, guest, @ menzioni) | File e contenuti |
| Canale autofavorite | |
| App installata | |
| Schede aggiunte | |

> [!NOTE]
> Nelle versioni future di Microsoft Teams verranno aggiunti altri modelli, quindi controllare di nuovo le informazioni più aggiornate sulle proprietà supportate.

## <a name="pre-built-team-templates-in-the-teams-admin-center"></a>Modelli di team predefiniti nell'interfaccia Teams di amministrazione

Ecco i modelli di team predefiniti disponibili nell'Teams di amministrazione. I modelli predefiniti sono modelli creati per settori specifici. Per visualizzare questi modelli, nel riquadro di spostamento sinistro dell'interfaccia Teams di amministrazione **passare a** >  Teams **Modelliteam**.

È possibile duplicare i modelli predefiniti, ma non modificarli. Se si vogliono modificare le proprietà in un modello predefinito, è possibile creare un nuovo modello da un modello esistente e quindi aggiungere o rimuovere le proprietà desiderate. Tenere presente che alcune proprietà in alcuni modelli non possono essere modificate.

| Tipo di modello | TemplateId | Proprietà del modello |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adottare Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Angolo Champions</li> <li>Moduli del team</li><li>Calendario</li></ul> App: <ul><li>Wiki</li>  <li>Calendario del canale</li> <li>Attività cardine</li><li>Bollettini</li></ul>|
| Gestire un progetto |`com.microsoft.teams.template.ManageAProject`| Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Risorse</li> <li>Pianificazione</li></ul> App:<ul><li>Wiki</li><li>OneNote</li><li>Attività</li><li>Elenchi</li><li>Power Automate</li></ul> |
| Gestire un evento|`com.microsoft.teams.template.ManageAnEvent` | Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Budget</li> <li>Contenuto</li><li>Logistica</li> <li>Pianificazione</li> <li> Marketing e pubbliche relazioni</li></ul> App:<ul><li>Wiki</li><li>Sito Web</li> <li>YouTube</li> <li>Attività</li> <li>OneNote</li> <li>Idee per i dipendenti</li> <li>Segnalazione dei problemi</li><li>Power Automate</li><li>Bollettini</li><li>Attività cardine</li></ul> |
|Dipendenti a bordo|`com.microsoft.teams.template.OnboardEmployees` | Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Chat dei dipendenti</li> <li>Formazione</li></ul>App:<ul><li>Wiki</li><li>Community</li><li>Attività</li><li>Idee per i dipendenti</li><li>Power Automate</li><li>Bollettini</li><li>Attività cardine</li></ul>|
|Organizzare l'help desk| `com.microsoft.teams.template.OrganizeHelpDesk`|Canali:<ul><li>Generale</li><li>Annunci</li><li>Domande frequenti</li></ul>App:<ul><li>Wiki</li><li>OneNote</li><li>Attività </li><li>Complimento</li><li>Segnalazione dei problemi</li><li>Power Automate</li><li>Bollettini</li></ul> |
| Assistenza ai pazienti| `com.microsoft.teams.template.healthcareWard`| Canali:<ul><li>Generale</li><li>Annunci</li><li>Briefing</li><li>Giri di visite</li><li>Personale</li><li>Formazione</li></ul> App: <ul><li>Wiki</li><li>Elenchi  </li><li>Approvazioni</li><li>Bollettini</li><li>Revisione</li></ul>|
| Comunicazione di crisi |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Canali: <ul><li>Generale<li>Annunci</li><li>Notizie del mondo</li><li>Messaggi interni</li><li>Comms esterni</li><li>Richiesta di approvazioni</li><li>Escalation dei clienti</li><li>Aggiornamento per dirigenti</li><li>Pianificazione</li><li>Logistica</li></ul>App: <ul><li>Sito Web</li><li>Attività</li><li>Segnalazione dei problemi</li><li>Approvazioni</li><li>Bollettini</li><li>OneNote</li><li>Power Automate</li><li>SharePoint</li></ul>|
|Filiale bancaria| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Canali: <ul><li>Generale<li>Annunci</li><li>Briefing</li><li>Riunioni con i clienti</li><li>Approvazioni richiesta </li><li>Coaching</li><li>Sviluppo delle competenze</li><li>Elaborazione dei prestiti</li><li>Reclami dei clienti</li><li>Complimenti</li><li>Elementi divertenti</li><li>Conformità</li></ul>App:<ul><li>Complimento </li><li>Segnalazione dei problemi</li><li>Wiki</li><li>Calendario</li><li>Approvazioni</li><li>Bollettini</li><li>Idee</li></ul>|
|Risposta a un evento imprevisto| `com.microsoft.teams.template.CoordinateIncidentResponse`|Canali: <ul><li>Generale<li>Annunci</li><li>Logistica</li><li>Pianificazione</li><li>Ripristino</li><li>Urgente</li></ul> App: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Attività</li> <li>Approvazioni</li> <li>Ispezione</li> <li>Power Automate</li><li>Bollettini</li><li>Attività cardine</li></ul>|
|Ospedale| `com.microsoft.teams.template.healthcareHospital` |Canali: <ul><li>Generale</li><li>Annunci</li><li>Conformità</li><li>Pulizie</li><li>Risorse umane</li><li>Farmacia</li></ul> App: <ul><li>Wiki</li><li>Elenchi</li><li>Attività</li><li>Approvazioni</li><li>Turni</li><li>Bollettini</li><li>Revisione</li><li>Idee</li></ul>|
|Organizzare un negozio| `com.microsoft.teams.template.retailStore` |Canali: <ul><li>Generale<li>Passaggio di consegne del turno</li><li>Conformità dello Store</li><li>Apprendimento</li></ul> App: <ul><li>Wiki</li><li>Attività</li><li>Turni</li><li>Ispezione</li></ul>|
|Vendita al dettaglio per i responsabili| `com.microsoft.teams.template.retailManagerCollaboration` |Canali: <ul><li>Generale<li>Operazioni</li><li>Apprendimento</li></ul> App: <ul><li>Wiki</li><li>Attività</li><li>Ispezione</li></ul>|
|Qualità e sicurezza |`com.microsoft.teams.template.QualitySafety`|Canali: <ul><li>Generale<li>Annunci</li><li>Leadership</li><li>Manutenzione</li><li>Linea di produzione 1</li><li>Linea di produzione 2</li><li>Linea di produzione 3</li><li>Salute e sicurezza</li><li>Formazione</li><li>Elementi divertenti</li></ul> App: <ul><li>Wiki</li><li>Attività</li> <li>Segnalazione dei problemi</li> <li>Ispezione</li> </ul>|
|Gestisci i volontari| `com.microsoft.teams.template.ManageVolunteers` |Canali: <ul><li>Generale<li>Annunci</li><li>Reporting</li><li>Gestione dei volontari</li><li>Opportunità di impegno</li><li>Onboarding dei volontari</li></ul> App: <ul><li>Sito Web</li><li>YouTube</li><li>Power BI</li><li>Power Apps</li><li>Attività</li><li>SharePoint</li><li>OneNote</li></ul>|
||||

### <a name="team-templates-by-category-and-industry"></a>Modelli di team per categoria e settore

Per altre informazioni su come usare i modelli predefiniti del settore, vedere:

- [Modelli di team finanziari](financial-teams-templates-in-the-admin-console.md)
- [Modelli generali del team](general-teams-templates-in-the-admin-console.md)
- [Modelli di team per enti pubblici](government-teams-templates-in-the-admin-console.md)
- [Modelli del team sanitario](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Modelli di team di produzione](manufacturing-teams-templates-in-the-admin-console.md)
- [Modelli di team per organizzazioni no profit](team-templates-nonprofit.md)
- [Modelli di team di vendita al dettaglio](retail-teams-templates-in-the-admin-console.md)

## <a name="team-template-size-limits"></a>Limiti per le dimensioni del modello di team

I modelli sono limitati a un numero specifico di canali, schede e app.

 > [!Note]
 > È possibile aggiungere altri canali, schede e app al team dopo che è stato creato da un modello.

|Funzionalità | Limite|
|-|-|
|Canali per modello | 15 |
|Schede per canale in un modello | 20 |
|App per modello | 50|
|||

Per altre informazioni, vedere [Limiti e specifiche di Teams](limits-specifications-teams.md).

## <a name="manage-team-templates"></a>Gestire i modelli di team

### <a name="manage-team-templates-in-the-teams-admin-center"></a>Gestire i modelli di team nell’interfaccia di amministrazione di Teams

#### <a name="view-team-templates"></a>Visualizzare i modelli di team

Per visualizzare i modelli di team, nel riquadro di spostamento sinistro dell'interfaccia Teams di amministrazione passare  >  a modelli Teams **Team**. Selezionare un modello per visualizzare altri dettagli, inclusi i canali e le app in esso contenuti.

#### <a name="create-your-own-team-templates"></a>Creare modelli di team personalizzati

È possibile creare modelli personalizzati da zero, da un team esistente e da un modello esistente. Per altre informazioni, vedere:

- [Creare un modello di team personalizzato](create-a-team-template.md)
- [Creare un modello da un team esistente](create-template-from-existing-team.md)
- [Creare un modello di team da un modello di team esistente](create-template-from-existing-template.md)

#### <a name="apply-team-template-policies"></a>Applicare i criteri dei modelli di team

Per controllare i modelli visualizzati dagli utenti nelle Teams per la creazione di [team](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b), è possibile impostare i criteri dei modelli e assegnarli a utenti e gruppi dell'organizzazione. Per altre informazioni, vedere [Gestire i modelli di team nell'Teams di amministrazione](templates-policies.md).

### <a name="manage-team-templates-using-powershell"></a>Gestire i modelli di team con PowerShell

Usare i cmdlet seguenti per gestire i modelli in PowerShell.

- [Get-CsTeamTemplate](/powershell/module/teams/get-csteamtemplate?view=teams-ps)
- [Get-CsTeamTemplateList](/powershell/module/teams/get-csteamtemplatelist?view=teams-ps)
- [New-CsTeamTemplate](/powershell/module/teams/new-csteamtemplate?view=teams-ps)
- [Remove-CsTeamTemplate](/powershell/module/teams/remove-csteamtemplate?view=teams-ps)
- [Update-CsTeamTemplate](/powershell/module/teams/update-csteamtemplate?view=teams-ps)

## <a name="related-articles"></a>Articoli correlati

- [Creare un team da un modello](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Introduzione ai modelli di team con Microsoft Graph](get-started-with-teams-templates.md)
- [Clonare un team](/graph/api/team-clone?view=graph-rest-1.0&tabs=http)
