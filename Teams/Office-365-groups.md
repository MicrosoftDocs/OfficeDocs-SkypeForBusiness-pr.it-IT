---
title: Microsoft 365 Groups e Microsoft Teams
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Informazioni su come i gruppi e le appartenenze di gruppo di Microsoft 365 lavorano con Microsoft teams.
ms.openlocfilehash: a4227432ab3557ca5e74ee5a769641185c1e432c
ms.sourcegitcommit: f18941b6dc17b6ea411e10970602aee271242d43
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456080"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 Groups e Microsoft Teams

Microsoft 365 groups è il servizio di appartenenza tra applicazioni in Microsoft 365. A livello di base, un gruppo Microsoft 365 è un oggetto in Azure Active Directory con un elenco di membri e un accoppiamento a carichi di lavoro correlati, tra cui un sito del team di SharePoint, una cassetta postale di Exchange condivisa, un'area di lavoro di Planner e Power BI. È possibile aggiungere o rimuovere persone al gruppo esattamente come si farebbe con qualsiasi altro oggetto di sicurezza basato su gruppo in Active Directory.

![Diagramma che mostra i gruppi e i servizi correlati di Microsoft 365](https://docs.microsoft.com/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

Per impostazione predefinita, gli utenti in Microsoft 365 possono creare e gestire gruppi. Per altre informazioni sui gruppi di Microsoft 365, vedere informazioni [sui gruppi di microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) e sui gruppi [in Microsoft 365 per i poster degli architetti it](teams-architecture-solutions-posters.md#groups-in-microsoft-365) .

## <a name="how-microsoft-365-groups-work-with-teams"></a>Funzionamento dei gruppi di Microsoft 365 con teams

Quando crei un team, viene creato un gruppo Microsoft 365 per gestire l'appartenenza al team. I servizi correlati del gruppo, ad esempio un sito di SharePoint, un'area di lavoro di Power BI e così via vengono creati contemporaneamente.

Gli utenti che creano team possono scegliere di usare un gruppo Microsoft 365 esistente se si tratta di un proprietario di tale gruppo. Ogni canale del team ha una cartella distinta nella raccolta documenti. La creazione di cartelle direttamente nella raccolta documenti non crea canali nel team.

Quando si crea un gruppo Microsoft 365 in Outlook o SharePoint, la cassetta postale del gruppo è visibile in Outlook. Quando si crea un team in teams, la cassetta postale del gruppo è nascosta per impostazione predefinita. Puoi usare il cmdlet [set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) con il parametro **HiddenFromExchangeClientsEnabled** per rendere visibile una cassetta postale.

## <a name="group-membership"></a>Appartenenza al gruppo

Se si rimuove un membro di un team, questi vengono rimossi anche dal gruppo Microsoft 365. La rimozione dal gruppo rimuove immediatamente il team e i canali dal client teams. Se si rimuove una persona da un gruppo con l'interfaccia di amministrazione di Microsoft 365, non sarà più possibile accedere agli altri aspetti della collaborazione, ad esempio la raccolta documenti di SharePoint Online, il gruppo Yammer o OneNote condiviso. Tuttavia, avranno comunque accesso alla funzionalità di chat del team per circa due ore.

Come procedura consigliata per gestire i membri del team, aggiungerli e rimuoverli dal client teams per assicurarsi che gli aggiornamenti delle autorizzazioni per altri carichi di lavoro connessi al gruppo si verifichino rapidamente. Se si aggiungono o si rimuovono membri del team all'esterno del client Teams (usando l'interfaccia di amministrazione di Microsoft 365, Azure AD o Exchange Online PowerShell), possono essere necessarie fino a 24 ore affinché le modifiche vengano applicate in teams.

## <a name="deleting-groups-and-teams"></a>Eliminazione di gruppi e team

L'eliminazione di un gruppo Microsoft 365 rimuoverà l'alias delle cassette postali per le conversazioni persistenti di Outlook/OWA e le riunioni di teams e contrassegnerà il sito di SharePoint per l'eliminazione. Tra la rimozione di un team e il relativo effetto su Outlook occorrono circa 20 minuti. L'eliminazione di un team dal client teams lo rimuove immediatamente dalla visualizzazione a tutti i membri del team. Se si rimuovono i membri di un gruppo di Microsoft 365 in cui è stata abilitata la funzionalità teams, potrebbe essere previsto un ritardo di circa due ore prima che il team venga rimosso dalla visualizzazione nel client teams per le persone interessate che sono state rimosse.

Per informazioni dettagliate sui gruppi e le opzioni di fine del ciclo di vita, vedere le  [Opzioni relative alla fine del ciclo di vita per gruppi, team e Yammer](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) e [archiviare o eliminare un team in Microsoft teams](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team).

## <a name="related-topics"></a>Argomenti correlati

[Fondazioni di Microsoft Teams (video)](https://aka.ms/teams-foundations)

[Ripristinare un gruppo eliminato](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)