---
title: Usare i modelli generali di Teams nell'interfaccia di amministrazione
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare i modelli generali di Teams per creare strutture di team fornendo impostazioni predefinite, canali e app preinstallato utilizzando l'interfaccia di amministrazione.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: caef10a4e9b659ce18e05df65bf2a441248ec493
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662071"
---
# <a name="use-general-teams-templates-in-the-admin-center"></a>Usare i modelli generali di Teams nell'interfaccia di amministrazione

I modelli di Teams consentono di creare team in modo semplice e rapido, fornendo un modello predefinito di impostazioni, canali e app preinstallato.

I modelli teams hanno definizioni predefinite di strutture del team progettate in base alle esigenze finanziarie. È anche possibile estendere i modelli di Teams per creare team personalizzati in base alle specifiche esigenze dell'organizzazione.

In questo articolo vengono presentati tutti i modelli di Teams e viene consigliato come usarli.

Questo articolo è utile se si è responsabili della pianificazione, della distribuzione e della gestione di più team nell'intera organizzazione finanziaria. Il servizio Teams è già stato distribuito nell'organizzazione. Se Teams non è ancora stato implementazione, iniziare leggendo come [implementare Microsoft Teams.](How-to-roll-out-teams.md)

Per altre informazioni sui modelli di team in generale, vedere Introduzione ai modelli [di Teams.](get-started-with-teams-templates-in-the-admin-console.md)

## <a name="global-crisis-or-event"></a>Emergenza o evento globale

Centralizzare la collaborazione per il team di emergenza tra le unità aziendali e contribuire a creare piani di continuità aziendale, condividere suggerimenti per il lavoro remoto, tenere traccia delle comunicazioni dei clienti e tenere tutti sul campo con annunci e notizie.

| Tipo di modello di base |baseTemplateId| Proprietà disponibili in questo modello di base |
| ------------------ |--|----------------------------------------------------------|
| Collaborare in caso di emergenza o evento globale |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |Canali: <ul><li>Generale<li>Annunci</li><li>Notizie del mondo</li><li>Continuità aziendale</li><li>Comms esterni</li><li>Richiesta di approvazione</li><li>Lavoro remoto</li><li>Messaggi interni</li><li>Comms esterni</li><li>Reclami dei clienti</li><li>Kudos</li><li>Aggiornamento della dirigenzia</li></ul>App: <ul><li>Complimento</li><li>Wiki</li><li>Sito Web</li><li>Programmazione</li></ul>|
||||

## <a name="adopt-office-365"></a>Adottare Office 365

Aiuta i tuoi colleghi a costruire, sviluppare e sostenere l'implementazione della community di campioni e aiuta i tuoi colleghi nella nuova tecnologia.

| Tipo di modello di base |baseTemplateId| Proprietà disponibili in questo modello di base |
| ------------------|--|-----------------------------------------------------------|
| Adottare Office 365 | `com.microsoft.teams.template.AdoptOffice365` |  Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Angolo campioni</li> <li>Moduli del team</li></ul> App: <ul><li>Wiki</li>  <li>Calendario</li><li>Sviluppo di competenze</li><li>Elaborazione dei prestito</li><li>Reclami dei clienti</li><li>Kudos</li><li>Cose divertenti</li><li>Conformità</li></ul>|
||||

## <a name="manage-a-project"></a>Gestire un progetto

Con questo modello è possibile gestire attività, condividere documenti, condurre riunioni del progetto e documentare rischi e decisioni per la gestione generale dei progetti.

| Tipo di modello di base| baseTemplateId| Proprietà disponibili in questo modello di base |
| ------------------|--|-----------------------------------------------------------|
| Gestire un progetto| `com.microsoft.teams.template.ManageAProject`  | Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Risorse</li> <li>Pianificazione</li></ul> App:<ul><li>Wiki</li><li>OneNote</li><li>Programmazione</li><li>Elenchi</li> </ul> |
||||

## <a name="manage-an-event"></a>Gestire un evento

Gestire attività, documenti e collaborare su tutto il necessario per creare un evento accattivante. Invitare utenti guest a collaborare in modo sicuro all'interno e all'esterno dell'azienda.

In base ai criteri di autorizzazione per le app, è possibile che non si abbia accesso ad alcune app.

| Tipo di modello di base | baseTemplateId| Proprietà disponibili in questo modello di base |
| ------------------ |--|-----------------------------------------------------------|
| Gestire un evento| `com.microsoft.teams.template.ManageAnEvent` | Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Budget</li> <li>Contenuto</li><li>Logistica</li> <li>Pianificazione</li> <li> Marketing e PR</li></ul> App:<ul><li>Wiki</li><li>Sito Web</li> <li>YouTube</li> <li>Programmazione</li> <li>OneNote</li></ul> |
||||

## <a name="onboard-employees"></a>Dipendenti a bordo

Migliora la tua cultura e semplifica l'onboarding dei dipendenti con questo team centrale per risorse, domande e un po' di divertimento.

| Tipo di modello di base |baseTemplateId| Proprietà disponibili in questo modello di base |
| ------------------|--|-----------------------------------------------------------|
|Dipendenti a bordo|`com.microsoft.teams.template.OnboardEmployees`  | Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Chat per i dipendenti</li> <li>Formazione</li></ul>App:<ul><li>Wiki</li><li>Community</li><li>Programmazione</li></ul>|
||||

## <a name="organize-a-help-desk"></a>Organizzare un help desk

Collaborare alla documentazione, ai criteri e ai processi che supportano il supporto tecnico. Integrare il sistema di ticket esistente o usare il modello per gestire le richieste.

| Tipo di modello di base |baseTemplateId| Proprietà disponibili in questo modello di base |
| ------------------|--|------------------------------------------------------------|
|Organizzare l'help desk|`com.microsoft.teams.template.OrganizeHelpDesk`| Canali:<ul><li>Generale</li><li>Annunci</li><li>Domande frequenti</li></ul>App:<ul><li>Wiki</li><li>OneNote</li><li>Programmazione </li><li>Complimento </li></ul> |
||||
