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
- m365-frontline
- highpri
description: Informazioni sui modelli di team e su come gestirli nell'interfaccia di amministrazione di Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2fc4f5c88e123981ee5224a76c28996306e51ded
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046896"
---
# <a name="get-started-with-team-templates-in-the-teams-admin-center"></a>Introduzione ai modelli di team nell'interfaccia Teams di amministrazione

**La possibilità di creare modelli personalizzati non è ancora supportata per i clienti EDU.**

> [!NOTE]
> - I canali privati e condivisi non sono attualmente supportati nei modelli di team. La creazione di canali privati e condivisi non è inclusa nelle definizioni dei modelli.
>
> - Le etichette di riservatezza non sono supportate nei modelli di team negli ambienti GCC. L'opzione dell'etichetta di riservatezza nel flusso Crea team da modello non verrà applicata al team.

## <a name="overview"></a>Panoramica

Un modello di team in Microsoft Teams è una definizione della struttura di un team progettata in base a un'esigenza aziendale o a un progetto. Gli amministratori possono usare i modelli per distribuire facilmente team coerenti all'interno dell'organizzazione. Con i modelli, gli utenti possono creare rapidamente spazi di collaborazione avanzati con impostazioni, canali e app predefiniti.

È possibile gestire i modelli di team nell'interfaccia di amministrazione di Microsoft Teams o tramite PowerShell. È possibile usare i modelli predefiniti forniti da Microsoft e [anche creare modelli personalizzati](#create-your-own-team-templates). È anche possibile [applicare criteri modello](#apply-team-template-policies) per controllare quali modelli sono disponibili per gli utenti in Teams.

Questo articolo offre una panoramica dell'uso dei modelli di team nell'interfaccia di amministrazione di Teams. Vengono fornite informazioni sulle proprietà supportate nei modelli, sui modelli predefiniti forniti da Microsoft, sui limiti di dimensioni dei modelli, su come creare e gestire i modelli e altro ancora.

> [!NOTE]
> Gli utenti possono [creare team da modelli di team predefiniti o personalizzati](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c) nell'app Teams. Gli sviluppatori possono anche creare team a livello di programmazione da modelli di team predefiniti o personalizzati usando Microsoft Graph. Per altre informazioni, vedere [Introduzione ai modelli di team con Microsoft Graph](get-started-with-teams-templates.md).

## <a name="team-template-capabilities"></a>Funzionalità dei modelli di team

La maggior parte delle proprietà di un team sono incluse e supportate dai modelli di team. Tuttavia, alcune proprietà e funzionalità non sono attualmente supportate. Ecco un riepilogo delle funzionalità incluse e di ciò che non è incluso nei modelli di team.

| **Proprietà del team supportate dai modelli di team** | **Proprietà del team non ancora supportate dai modelli di team** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo di modello | Appartenenza al team |
| Nome del team | Immagine del team |
| Descrizione del team | Impostazioni del canale |
| Visibilità del team (pubblica o privata) | Connettori |
| Impostazioni del team (ad esempio membro, guest, @menzioni) | File e contenuti |
| Canale autofavorite | |
| App installata | |
| Schede aggiunte | |

> [!NOTE]
> Aggiungeremo altre funzionalità di modello nelle versioni future di Microsoft Teams, quindi ricontrollare per le informazioni più aggiornate sulle proprietà supportate.

## <a name="pre-built-team-templates-in-the-teams-admin-center"></a>Modelli di team predefiniti nell'interfaccia di amministrazione di Teams

Ecco i modelli di team predefiniti disponibili nell'interfaccia di amministrazione di Teams. I modelli predefiniti sono modelli creati per settori specifici. Per visualizzare questi modelli, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams passare a **Modelli team di** **Teams** > .

È possibile duplicare modelli predefiniti, ma non modificarli. Se si vogliono modificare le proprietà in un modello predefinito, è possibile creare un nuovo modello da uno esistente e quindi aggiungere o rimuovere le proprietà desiderate. Tenere presente che alcune proprietà di alcuni modelli non possono essere modificate.

> [!NOTE]
> Un asterisco (*) indica che il modello è *connesso a Microsoft 365*. Quando gli utenti creano un team usando il modello, il modello di SharePoint connesso viene applicato al sito e al team. I componenti di SharePoint, ad esempio pagine, elenchi e integrazioni Power Platform, vengono aggiunti e aggiunti automaticamente come schede al canale Generale nel team. Gli utenti possono modificare queste pagine ed elenchi direttamente da Teams.
>
> Per altre informazioni sui modelli di SharePoint, vedere [Applicare e personalizzare modelli di sito di SharePoint](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

>[!div class="mx-tdBreakAll"]
>| Tipo di modello | TemplateId | Proprietà del modello |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| Gestire un progetto* |`com.microsoft.teams.template.ManageAProject`| Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Risorse</li> <li>Pianificazione</li></ul> App:<ul><li>Approvazioni</li><li>Bollettini</li><li>Elenchi<ul><li>Tracciatore di progetti</li><li>Gestione problemi</li></ul></li><li>Pietre miliari</li><li>OneNote</li><li>Power Automate</li><li>Pagine SharePoint<ul><li>Il nostro sito</li></ul></li><li>Attività per Planner e To Do</li><li>Wiki</li></ul> |
| Gestire un evento*|`com.microsoft.teams.template.ManageAnEvent` | Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Budget</li> <li>Contenuto</li><li>Logistica</li> <li>Pianificazione</li> <li> Marketing e PR</li></ul> App:<ul><li>Approvazioni</li><li>Bollettini</li> <li>Idee per i dipendenti</li><li>Elenchi<ul><li>Utilità di pianificazione del contenuto</li></ul></li><li>Pietre miliari</li> <li>OneNote</li> <li>Power Automate</li> <li>Pagine SharePoint<ul><li>Il nostro sito</li><li>Informazioni sull'evento</li></ul><li>Attività per Planner e To Do</li><li>Wiki</li> |
|Dipendenti onboard*|`com.microsoft.teams.template.OnboardEmployees` | Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Chat per i dipendenti</li> <li>Formazione</li></ul>App:<ul><li>Bollettini</li><li>Idee per i dipendenti</li><li>Elenchi<ul><li>Elenco di controllo onboarding</li></ul></li><li>Pietre miliari</li><li>Power Automate</li> <li>Pagine SharePoint<ul><li>Per iniziare</li><li>Formazione</li></ul><li>Attività per Planner e To Do</li><li>Viva Engage</li><li>Wiki</li></ul>|
| Adottare Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Angolo dei campioni</li> <li>Moduli team</li><li>Calendario</li></ul> App: <ul><li>Wiki</li>  <li>Calendario del canale</li> <li>Pietre miliari</li><li>Bollettini</li></ul>
|Organizzare l'Help Desk*| `com.microsoft.teams.template.OrganizeHelpDesk`|Canali:<ul><li>Generale</li><li>Annunci</li><li>Domande frequenti</li></ul>App:<ul><li>Segnalazione problemi</li><li>Elenchi<ul><li>Dispositivi</li><li>Biglietti</li></ul></li><li>OneNote</li><li>Power Automate</li><li>Pagine SharePoint<ul><li>Il nostro sito</li><li>Domande frequenti</li></ul></li><li>Attività per Planner e To Do</li><li>Wiki</li></ul> |
|Risposta a eventi imprevisti| `com.microsoft.teams.template.CoordinateIncidentResponse`|Canali: <ul><li>Generale<li>Annunci</li><li>Logistica</li><li>Pianificazione</li><li>Recupero</li><li>Urgente</li></ul> App: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Attività</li> <li>Approvazioni</li> <li>Ispezione</li> <li>Power Automate</li><li>Bollettini</li><li>Pietre miliari</li></ul>|
| Crisis Communications* |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Canali: <ul><li>Generale<li>Annunci</li><li>Aggiornamento esecutivo</li><li>Pianificazione</li><li>Logistica</li></ul>App: <ul><li>Approvazioni</li><li>Segnalazione problemi</li><li>Elenchi<ul><li>Utilità di pianificazione del contenuto</li><li>Piano di progetto</li></ul></li><li>OneNote</li><li>Power Automate</li><li>Pagine SharePoint<ul><li>Il nostro sito</li><li>Ultimo aggiornamento</li></ul><li>Attività per Planner e To Do</li>|
| Gestisci uno Store*| `com.microsoft.teams.template.retailStore` |Canali: <ul><li>Generale<li>Shift Handoff</li><li>Preparazione negozio</li><li>Apprendimento</li></ul> App: <ul><li>Approvazioni</li><li>Ispezione</li><li>Elenchi<ul><li>Elenco inventario</li></ul></li><li>Pagine SharePoint<ul><li>Il nostro negozio</li></ul></li><li>Turni</li><li>Attività per Planner e To Do</li><li>Wiki</li></ul>|
|Bank Branch| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Canali: <ul><li>Generale<li>Annunci</li><li>Briefing</li><li>Riunioni con i clienti</li><li>Richiesta di approvazione </li><li>Coaching</li><li>Sviluppo delle competenze</li><li>Elaborazione del prestito</li><li>Reclami dei clienti</li><li>Complimenti</li><li>Cose divertenti</li><li>Conformità</li></ul>App:<ul><li>Complimento </li><li>Segnalazione dei problemi</li><li>Wiki</li><li>Calendario</li><li>Approvazioni</li><li>Bollettini</li><li>Idee</li></ul>|
| Patient Care| `com.microsoft.teams.template.healthcareWard`| Canali:<ul><li>Generale</li><li>Annunci</li><li>Briefing</li><li>Giri di visite</li><li>Personale</li><li>Formazione</li></ul> App: <ul><li>Wiki</li><li>Elenchi  </li><li>Approvazioni</li><li>Bollettini</li><li>Revisione</li></ul>|
|Ospedale| `com.microsoft.teams.template.healthcareHospital` |Canali: <ul><li>Generale</li><li>Annunci</li><li>Conformità</li><li>Pulizie</li><li>Risorse umane</li><li>Farmacia</li></ul> App: <ul><li>Wiki</li><li>Elenchi</li><li>Attività</li><li>Approvazioni</li><li>Turni</li><li>Bollettini</li><li>Revisione</li><li>Idee</li></ul>|
|Qualità e sicurezza |`com.microsoft.teams.template.QualitySafety`|Canali: <ul><li>Generale<li>Annunci</li><li>Leadership</li><li>Manutenzione</li><li>Linea di produzione 1</li><li>Linea di produzione 2</li><li>Linea di produzione 3</li><li>Salute e sicurezza</li><li>Formazione</li><li>Cose divertenti</li></ul> App: <ul><li>Wiki</li><li>Attività</li> <li>Segnalazione dei problemi</li> <li>Ispezione</li> </ul>|
|Vendita al dettaglio per manager*| `com.microsoft.teams.template.retailManagerCollaboration` |Canali: <ul><li>Generale<li>Operazioni</li><li>Apprendimento</li></ul> App: <ul><li>Approvazioni</li><li>Ispezione</li><li>Pagine SharePoint<ul><li>Il nostro negozio</li></ul></li><li>Attività per Planner e To Do</li><li>Wiki</li></ul>|
|Gestire i volontari| `com.microsoft.teams.template.ManageVolunteers` |Canali: <ul><li>Generale<li>Annunci</li><li>Reporting</li><li>Gestione dei volontari</li><li>Opportunità di impegno</li><li>Onboarding dei volontari</li></ul> App: <ul><li>Sito Web</li><li>YouTube</li><li>Power BI</li><li>Power Apps</li><li>Attività</li><li>SharePoint</li><li>OneNote</li></ul>|

### <a name="team-templates-by-category-and-industry"></a>Modelli di team per categoria e settore

Per altre informazioni su come usare i modelli predefiniti nel proprio settore, vedere:

- [Modelli generali del team](general-teams-templates-in-the-admin-console.md)
- [Modelli di team finanziari](financial-teams-templates-in-the-admin-console.md)
- [Modelli per i team di enti pubblici](government-teams-templates-in-the-admin-console.md)
- [Modelli del team sanitario](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Modelli di team di produzione](manufacturing-teams-templates-in-the-admin-console.md)
- [Modelli di team per organizzazioni no profit](team-templates-nonprofit.md)
- [Modelli del team di vendita al dettaglio](get-started-with-retail-teams-templates.md)

## <a name="team-template-size-limits"></a>Limiti per le dimensioni dei modelli di team

I modelli sono limitati a un numero specifico di canali, schede e app.

 > [!Note]
 > È possibile aggiungere altri canali, schede e app al team dopo che è stato creato da un modello.

|Funzionalità | Limite|
|-|-|
|Canali per modello | 15 |
|Schede per canale in un modello | 20 |
|App per modello | 50|

Per altre informazioni, vedere [Limiti e specifiche di Teams](limits-specifications-teams.md).

## <a name="manage-team-templates"></a>Gestire i modelli di team

### <a name="manage-team-templates-in-the-teams-admin-center"></a>Gestire i modelli di team nell’interfaccia di amministrazione di Teams

#### <a name="view-team-templates"></a>Visualizzare i modelli del team

Per visualizzare i modelli del team, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams passare a **Modelli team di** **Teams** > . Seleziona un modello per visualizzare altri dettagli, inclusi i canali e le app che contiene.

#### <a name="create-your-own-team-templates"></a>Creare modelli di team personalizzati

È possibile creare modelli personalizzati da zero, da un team esistente e da un modello esistente. Per altre informazioni, vedere:

- [Creare un modello di team personalizzato](create-a-team-template.md)
- [Creare un modello da un team esistente](create-template-from-existing-team.md)
- [Creare un modello di team da un modello di team esistente](create-template-from-existing-template.md)

#### <a name="apply-team-template-policies"></a>Applicare criteri per i modelli di team

Per controllare i modelli visualizzati dagli utenti in Teams per [la creazione di team](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b), è possibile impostare i criteri dei modelli e assegnarli a utenti e gruppi dell'organizzazione. Per altre informazioni, vedere [Gestire i modelli di team nell'interfaccia di amministrazione di Teams](templates-policies.md).

### <a name="manage-team-templates-using-powershell"></a>Gestire i modelli di team con PowerShell

Usare i cmdlet seguenti per gestire i modelli in PowerShell.

- [Get-CsTeamTemplate](/powershell/module/teams/get-csteamtemplate)
- [Get-CsTeamTemplateList](/powershell/module/teams/get-csteamtemplatelist)
- [New CsTeamTemplate](/powershell/module/teams/new-csteamtemplate)
- [Remove-CsTeamTemplate](/powershell/module/teams/remove-csteamtemplate)
- [Update-CsTeamTemplate](/powershell/module/teams/update-csteamtemplate)

## <a name="related-articles"></a>Articoli correlati

- [Creare un team da un modello](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Introduzione ai modelli di team con Microsoft Graph](get-started-with-teams-templates.md)
- [Clonare un team](/graph/api/team-clone)
- [Panoramica dell'integrazione di Teams e SharePoint](/sharepoint/teams-connected-sites)
