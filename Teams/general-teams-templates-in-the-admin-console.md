---
title: Usare modelli di team generali nell'interfaccia di amministrazione
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
description: Informazioni su come usare i modelli di team generali per creare strutture del team fornendo impostazioni predefinite, canali e app preinstallato tramite l'interfaccia di amministrazione.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c68965bb658328646b5308ad85092ce23bc0ab02
ms.sourcegitcommit: 3f1635d1915561798ea764c3e33d7db55f7e49da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2021
ms.locfileid: "53574051"
---
# <a name="use-general-team-templates-in-the-admin-center"></a>Usare modelli di team generali nell'interfaccia di amministrazione

I modelli di team consentono di creare rapidamente e facilmente team fornendo un modello predefinito di impostazioni, canali e app preinstallato.

I modelli di team hanno definizioni predefinite delle strutture del team progettate in base alle esigenze finanziarie. È anche possibile estendere i modelli di team per creare team personalizzati in base alle specifiche esigenze dell'organizzazione.

In questo articolo vengono presentati tutti i modelli di team e viene consigliato come usarli.

Questo articolo è utile se si è responsabili della pianificazione, della distribuzione e della gestione di più team all'interno dell'organizzazione. Il servizio Teams è già stato implementato nell'organizzazione. Se non è stata ancora Teams, iniziare leggendo come [implementare](./deploy-overview.md)Microsoft Teams .

Per altre informazioni sui modelli di team in generale, vedere Introduzione [ai modelli di team.](get-started-with-teams-templates-in-the-admin-console.md)

## <a name="global-crisis-or-event"></a>Crisi o evento globale

Centralizzare la collaborazione per il team di crisi tra le business unit e contribuire a creare piani di continuità aziendale, condividere suggerimenti di lavoro in remoto, tenere traccia delle comunicazioni dei clienti e tenere tutti in contatto con annunci e notizie.

| Tipologia di modello base |baseTemplateId| Proprietà del modello base |
| ------------------ |--|----------------------------------------------------------|
| Collaborare alla crisi globale o all'evento |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |Canali: <ul><li>Generale<li>Annunci</li><li>Notizie del mondo</li><li>Continuità aziendale</li><li>Comms esterni</li><li>Approvazioni richiesta</li><li>Lavorare in remoto</li><li>Messaggi interni</li><li>Comms esterni</li><li>Reclami dei clienti</li><li>Complimenti</li><li>Aggiornamento per dirigenti</li></ul>App: <ul><li>Complimenti</li><li>Wiki</li><li>Sito Web</li><li>Programmazione</li></ul>|
||||

## <a name="adopt-office-365"></a>Adottare Office 365

Aiuta a costruire, far crescere e sostenere l'implementazione della community Di Champions evangelizzando e aiutando i tuoi colleghi con la nuova tecnologia.

| Tipologia di modello base |baseTemplateId| Proprietà del modello base |
| ------------------|--|-----------------------------------------------------------|
| Adottare Office 365 | `com.microsoft.teams.template.AdoptOffice365` |  Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Angolo Champions</li> <li>Moduli del team</li></ul> App: <ul><li>Wiki</li>  <li>Calendario</li><li>Sviluppo di competenze</li><li>Elaborazione dei prestiti</li><li>Reclami dei clienti</li><li>Complimenti</li><li>Cose divertenti</li><li>Conformità</li></ul>|
||||

## <a name="manage-a-project"></a>Gestire un progetto

Questo modello consente di gestire attività, condividere documenti, condurre riunioni di progetto e documentare rischi e decisioni con questo modello per la gestione generale dei progetti.

| Tipologia di modello base| baseTemplateId| Proprietà del modello base |
| ------------------|--|-----------------------------------------------------------|
| Gestire un progetto| `com.microsoft.teams.template.ManageAProject`  | Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Risorse</li> <li>Pianificazione</li></ul> App:<ul><li>Wiki</li><li>OneNote</li><li>Programmazione</li><li>Elenchi</li> </ul> |
||||

## <a name="manage-an-event"></a>Gestire un evento

Gestire attività, documenti e collaborare su tutto ciò che serve per offrire un evento accattivante. Invitare gli utenti guest a collaborare in modo sicuro all'interno e all'esterno dell'azienda.

È possibile che non si abbia accesso a determinate app in base ai criteri di autorizzazione dell'app.

| Tipologia di modello base | baseTemplateId| Proprietà del modello base |
| ------------------ |--|-----------------------------------------------------------|
| Gestire un evento| `com.microsoft.teams.template.ManageAnEvent` | Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Budget</li> <li>Contenuto</li><li>Logistica</li> <li>Pianificazione</li> <li> Marketing e pubbliche relazioni</li></ul> App:<ul><li>Wiki</li><li>Sito Web</li> <li>YouTube</li> <li>Programmazione</li> <li>OneNote</li></ul> |
||||

## <a name="onboard-employees"></a>Dipendenti a bordo

Migliorare la cultura e semplificare l'onboarding dei dipendenti con questo team centrale per risorse, domande e un po' di divertimento.

| Tipologia di modello base |baseTemplateId| Proprietà del modello base |
| ------------------|--|-----------------------------------------------------------|
|Dipendenti a bordo|`com.microsoft.teams.template.OnboardEmployees`  | Canali: <ul><li>Generale</li> <li>Annunci</li> <li>Chat dei dipendenti</li> <li>Formazione</li></ul>App:<ul><li>Wiki</li><li>Community</li><li>Programmazione</li></ul>|
||||

## <a name="organize-a-help-desk"></a>Organizzare un help desk

Collaborare alla documentazione, ai criteri e ai processi che supportano l'helpdesk. Integrare il sistema di ticket esistente o usare il modello per gestire le richieste.

| Tipologia di modello base |baseTemplateId| Proprietà del modello base |
| ------------------|--|------------------------------------------------------------|
|Organizzare l'help desk|`com.microsoft.teams.template.OrganizeHelpDesk`| Canali:<ul><li>Generale</li><li>Annunci</li><li>Domande frequenti</li></ul>App:<ul><li>Wiki</li><li>OneNote</li><li>Programmazione </li><li>Complimenti </li></ul> |
||||