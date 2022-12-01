---
title: Usare i modelli no profit di team
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
ms.localizationpriority: high
search.appverid: MET150
description: Informazioni su come gestire e usare il modello di team Gestisci volontari per creare in modo semplice e rapido i team per il personale dell'organizzazione no profit per comunicare e collaborare alle attività di gestione dei volontari.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1818a4eee46cca88c873af35278453ab84b1341
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198958"
---
# <a name="use-nonprofit-team-templates"></a>Usare i modelli no profit di team

I modelli di Microsoft Teams consentono di creare team in modo rapido e semplice fornendo un modello predefinito di impostazioni, canali e app preinstallate.

Per le organizzazioni no profit, i modelli di team possono rivelarsi particolarmente efficaci, in quanto consentono di distribuire rapidamente team coerenti all'interno dell’organizzazione. I modelli aiutano anche il personale a orientarsi su come usare in modo efficace Teams.

Teams include un modello di team Gestisci volontari progettato per semplificare le attività di gestione dei volontari. È possibile usare questo modello predefinito per creare rapidamente team che consentono al personale di comunicare e collaborare alle attività e alla gestione dei volontari.

In questo articolo sono contenute tutte le informazioni riguardanti il modello di team Gestisci volontari e su come usarlo per creare un team. L’articolo offre anche una panoramica sulla gestione dei modelli di team nell'interfaccia di amministrazione di Teams.

## <a name="manage-volunteers-team-template"></a>Modello di team Gestisci volontari

Riunire il personale per comunicare e collaborare alle attività e alla gestione dei volontari.

Questo modello include app e canali progettati per semplificare le attività di gestione dei volontari. Il personale può organizzare e condividere i materiali di onboarding e i documenti usati più di frequente, visualizzare i report, rimanere aggiornati sugli annunci e gli eventi importanti del team e altro ancora. Il modello integra anche [Volunteer Management](/dynamics365/industry/nonprofit/volunteer-management-use), un'app che è parte di [Microsoft Cloud per le organizzazioni no profit](/industry/nonprofit/), e che permette al personale di gestire le opportunità di coinvolgimento dei volontari all'interno di Teams.

Questi sono le app e i canali forniti con il modello di team Gestisci volontari.

| Tipo di modello |TemplateId | Proprietà del modello |
| ------------------|-- |----------------------------------------------------- |
|Gestisci i volontari| `ManageVolunteers` |Canali: <ul><li>Generale<ul><li>Sito Web&sup1;</li></ul><li>Announcements</li><li>Reporting<ul><li>Power BI&sup1;</li></ul></li><li>Gestione dei volontari<ul><li>Power Apps&sup1;</li></ul></li><li>Opportunità di impegno<ul><li>Attività&sup1;</li></ul></li><li>Onboarding dei volontari<ul><li>SharePoint&sup1;</li><li>OneNote&sup1;</li></ul></li></ul> App: <ul><li>Sito Web</li><li>YouTube</li><li>Power BI</li><li>Power Apps</li><li>Attività</li><li>SharePoint</li><li>OneNote</li></ul>|

&sup1; App aggiunta al canale come scheda.

## <a name="create-a-team-using-the-manage-volunteers-team-template"></a>Creare un team usando il modello di team Gestisci volontari

### <a name="create-the-team"></a>Creare il team

Bastano pochi rapidi passaggi per creare un team dal modello Gestisci volontari.

1. In Teams, selezionare **Teams** > **Partecipa o crea un team** > **Crea un team**.
2. Scegliere il modello di team **Gestisci volontari**.
3. Scegliere un livello di privacy:
    - **Privato**: i partecipanti necessitano dell'autorizzazione del proprietario del team per partecipare al team.
    - **Pubblico**: tutti gli utenti dell'organizzazione possono partecipare al team.
4. Assegnare un nome al team e aggiungere una descrizione. È inoltre possibile rinominare i canali per personalizzare il team.
5. Selezionare **Crea**.

Per altre informazioni, vedere [Creare un team con un modello di team](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

### <a name="add-the-volunteer-management-app-to-the-power-apps-tab"></a>Aggiungere l'app Gestione dei volontari alla scheda Power Apps

Per usare l'app Gestione volontari in Teams, aggiungerla alla scheda Power Apps nel canale Gestione dei volontari. 

1. In Teams, selezionare il team creato, scegliere il canale Gestione dei volontari, quindi selezionare la scheda **Power Apps**.
2. Nell'elenco a discesa selezionare **app basate sul modello**, quindi cercare e selezionare **Gestione dei volontari**.
3. Selezionare **Salva**.

Per altre informazioni, vedere [Incorporare un'app basata sul modello come tab app in Teams](/powerapps/teams/embed-model-driven-teams-tab).

## <a name="view-and-manage-team-templates-in-the-teams-admin-center"></a>Visualizzare e gestire i modelli di team nell'interfaccia di amministrazione di Teams

Gli amministratori possono visualizzare e gestire i modelli di team nell'interfaccia di amministrazione di Microsoft Teams. Per visualizzare il modello Gestisci volontari, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams passare a **Teams** > **modelli di team**.

È anche possibile [creare e assegnare agli utenti criteri di modelli](templates-policies.md) per controllare quali modelli visualizzano in Teams per la creazione di team.

Per altre informazioni sui modelli di team in generale, vedere Introduzione ai modelli [di team nell'Teams di amministrazione.](get-started-with-teams-templates-in-the-admin-console.md)

## <a name="related-articles"></a>Articoli correlati

- [Documentazione della Guida di Teams](https://support.microsoft.com/teams)
- [Documentazione di Microsoft Cloud per organizzazioni no profit](/industry/nonprofit/)
