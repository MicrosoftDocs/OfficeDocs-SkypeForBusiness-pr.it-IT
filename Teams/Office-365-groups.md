---
title: Gruppi di Microsoft 365 e Microsoft Teams
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
description: Informazioni sul funzionamento dei gruppi e delle appartenenze ai gruppi di Microsoft 365 con Microsoft Teams.
ms.openlocfilehash: a4227432ab3557ca5e74ee5a769641185c1e432c
ms.sourcegitcommit: f18941b6dc17b6ea411e10970602aee271242d43
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456080"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Gruppi di Microsoft 365 e Microsoft Teams

Gruppi di Microsoft 365 è il servizio di appartenenza tra applicazioni in Microsoft 365. A livello di base, un gruppo di Microsoft 365 è un oggetto in Azure Active Directory con un elenco di membri e un collegamento ai carichi di lavoro correlati, tra cui un sito del team di SharePoint, una cassetta postale di Exchange condivisa, Planner e l'area di lavoro di Power BI. È possibile aggiungere o rimuovere persone al gruppo come qualsiasi altro oggetto di sicurezza basato sul gruppo in Active Directory.

![Diagramma che illustra i gruppi di Microsoft 365 e i servizi correlati](https://docs.microsoft.com/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

Per impostazione predefinita, gli utenti di Microsoft 365 possono creare e gestire i gruppi. Per altre informazioni sui gruppi di Microsoft 365, vedere informazioni sui gruppi di [Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) e sui gruppi nel poster [Microsoft 365 per](teams-architecture-solutions-posters.md#groups-in-microsoft-365) architetti IT.

## <a name="how-microsoft-365-groups-work-with-teams"></a>Funzionamento dei gruppi di Microsoft 365 con Teams

Quando si crea un team, viene creato un gruppo di Microsoft 365 per gestire l'appartenenza al team. I servizi correlati del gruppo, ad esempio un sito di SharePoint, un'area di lavoro di Power BI e così via, vengono creati contemporaneamente.

Gli utenti che creano team possono scegliere di usare un gruppo di Microsoft 365 esistente, se sono proprietari del gruppo. Ogni canale del team ha una cartella separata nella raccolta documenti. La creazione di cartelle direttamente nella raccolta documenti non crea canali nel team.

Quando si crea un gruppo di Microsoft 365 in Outlook o SharePoint, la cassetta postale del gruppo è visibile in Outlook. Quando si crea un team in Teams, la cassetta postale del gruppo è nascosta per impostazione predefinita. È possibile usare il cmdlet [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) con il parametro **HiddenFromExchangeClientsEnabled** per rendere visibile una cassetta postale.

## <a name="group-membership"></a>Appartenenza ai gruppi

Se si rimuove un membro di un team, questo viene rimosso anche dal gruppo di Microsoft 365. La rimozione dal gruppo rimuove immediatamente il team e i canali dal client di Teams. Se si rimuove una persona da un gruppo tramite l'interfaccia di amministrazione di Microsoft 365, questa non avrà più accesso ad altri aspetti della collaborazione, ad esempio la raccolta documenti di SharePoint Online, il gruppo di Yammer o OneNote condiviso. Tuttavia, avranno comunque accesso alla funzionalità di chat del team per circa due ore.

Come procedura consigliata per la gestione dei membri del team, aggiungerli e rimuoverli dal client di Teams per assicurarsi che gli aggiornamenti delle autorizzazioni per altri carichi di lavoro connessi al gruppo siano eseguiti rapidamente. Se si aggiungono o rimuovono membri del team all'esterno del client Teams (usando l'interfaccia di amministrazione di Microsoft 365, Azure AD o PowerShell di Exchange Online), possono essere necessarie fino a 24 ore prima che le modifiche siano riflesse in Teams.

## <a name="deleting-groups-and-teams"></a>Eliminazione di gruppi e team

L'eliminazione di un gruppo di Microsoft 365 rimuove l'alias della cassetta postale per le conversazioni persistenti di Outlook/OWA e gli inviti alle riunioni di Teams e contrassegna il sito di SharePoint per l'eliminazione. Tra la rimozione di un team e il suo effetto su Outlook sono necessari circa 20 minuti. L'eliminazione di un team dal client Teams lo rimuoverà immediatamente dalla visualizzazione a tutti i membri del team. Se si rimuovono i membri di un gruppo di Microsoft 365 in cui è abilitata la funzionalità di Teams, potrebbe verificarsi un ritardo di circa due ore prima che il team venga rimosso dalla visualizzazione nel client di Teams per le persone interessate che sono state rimosse.

Per informazioni dettagliate sulle opzioni per la fine del ciclo di vita dei team e dei gruppi, vedere Le opzioni per la fine del ciclo di vita per [gruppi, team, Yammer](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) e Archiviazione oppure eliminare un [team in Microsoft Teams.](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team)

## <a name="related-topics"></a>Argomenti correlati

[Basi di Microsoft Teams (video)](https://aka.ms/teams-foundations)

[Ripristinare un gruppo eliminato](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)