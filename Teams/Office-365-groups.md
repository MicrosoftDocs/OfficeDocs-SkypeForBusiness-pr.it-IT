---
title: Gruppi di Microsoft 365 e Microsoft Teams
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Informazioni su come Microsoft 365 i gruppi e le appartenenze ai gruppi con Microsoft Teams.
ms.openlocfilehash: cf84c58e05e65b187ebe9c0d5a4560cf861fb9be
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125431"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Gruppi di Microsoft 365 e Microsoft Teams

Gruppi di Microsoft 365 è il servizio di appartenenza tra applicazioni in Microsoft 365. A livello di base, un gruppo di Microsoft 365 è un oggetto in Azure Active Directory con un elenco di membri e un accoppiamento ai carichi di lavoro correlati, tra cui un sito del team di SharePoint, una cassetta postale Exchange condivisa, Planner e un blocco appunti di OneNote. È possibile aggiungere o rimuovere persone al gruppo come si farebbe con qualsiasi altro oggetto di sicurezza basato su gruppo in Active Directory.

![Diagramma che mostra Gruppi di Microsoft 365 e servizi correlati.](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

Per impostazione predefinita, gli utenti di Microsoft 365 possono creare e gestire gruppi. Per altre informazioni su Gruppi di Microsoft 365, vedere [Informazioni su Gruppi di Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) e il poster [Gruppi in Microsoft 365 per architetti IT](teams-architecture-solutions-posters.md#groups-in-microsoft-365).

## <a name="how-microsoft-365-groups-work-with-teams"></a>Come Gruppi di Microsoft 365 usare Teams

Quando si crea un team, viene creato un gruppo di Microsoft 365 per gestire l'appartenenza al team. I servizi correlati del gruppo, ad esempio un sito SharePoint, una cassetta postale e così via, vengono creati contemporaneamente.

Le persone che creano team possono scegliere di usare un gruppo di Microsoft 365 esistente se ne sono proprietari. Ogni canale del team ha una cartella separata nella raccolta documenti. La creazione di cartelle direttamente nella raccolta documenti non crea canali nel team.

Quando si crea un gruppo di Microsoft 365 in Outlook o SharePoint, la cassetta postale del gruppo è visibile in Outlook. Quando si crea un team in Teams, la cassetta postale del gruppo è nascosta per impostazione predefinita. È possibile utilizzare il cmdlet [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) con il parametro **HiddenFromExchangeClientsEnabled** per rendere visibile una cassetta postale.

## <a name="group-membership"></a>Appartenenza ai gruppi

Se si rimuove un membro di un team, questo viene rimosso anche dal gruppo Microsoft 365. La rimozione dal gruppo rimuove immediatamente il team e i canali dal client Teams. Se si rimuove una persona da un gruppo usando la interfaccia di amministrazione di Microsoft 365, non avrà più accesso ad altri aspetti della collaborazione, ad esempio SharePoint raccolta documenti online, Yammer gruppo o OneNote condivisa. Avranno comunque accesso alla funzionalità di chat del team per circa due ore.

Come procedura consigliata per la gestione dei membri del team, aggiungerli e rimuoverli dal client Teams per assicurarsi che gli aggiornamenti delle autorizzazioni per altri carichi di lavoro connessi al gruppo si verifichino rapidamente. Se si aggiungono o rimuovono membri del team all'esterno del client Teams (usando interfaccia di amministrazione di Microsoft 365, Azure AD o Exchange Online PowerShell), possono essere necessarie fino a 24 ore prima che le modifiche vengano applicate in Teams.

## <a name="deleting-groups-and-teams"></a>Eliminazione di gruppi e team

L'eliminazione di un gruppo di Microsoft 365 rimuoverà l'alias della cassetta postale per le conversazioni persistenti Outlook/OWA e Teams inviti alle riunioni e contrassegnerà il sito SharePoint per l'eliminazione. Ci vogliono circa 20 minuti tra la rimozione di un team e il suo effetto su Outlook. L'eliminazione di un team dal client Teams lo rimuoverà immediatamente dalla visualizzazione a tutti i membri del team. Se si rimuovono membri di un gruppo di Microsoft 365 con Teams funzionalità abilitata, potrebbe verificarsi un ritardo di circa due ore prima che il team venga rimosso dalla visualizzazione nel client Teams per le persone interessate che sono state rimosse.

Per informazioni dettagliate sui gruppi e sulle opzioni di fine ciclo di vita per i team, vedere [Fine delle opzioni del ciclo di vita per gruppi, team e Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) e [Archiviare o eliminare un team in Microsoft Teams](./archive-or-delete-a-team.md).

## <a name="related-topics"></a>Argomenti correlati

[Fondazioni di Microsoft Teams (video)](https://aka.ms/teams-foundations)

[Ripristinare un gruppo eliminato](/microsoft-365/admin/create-groups/restore-deleted-group)
