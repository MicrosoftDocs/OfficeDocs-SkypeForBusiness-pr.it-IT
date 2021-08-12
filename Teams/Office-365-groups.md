---
title: Microsoft 365 Gruppi e Microsoft Teams
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
description: Informazioni su come Microsoft 365 e l'appartenenza ai gruppi con Microsoft Teams.
ms.openlocfilehash: 37668b4315f2a46a99f5d9409e395b70f5446ac0f9b0ab5fb86fdbbe644246d6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282899"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 Gruppi e Microsoft Teams

Microsoft 365 Gruppi è il servizio di appartenenza tra applicazioni in Microsoft 365. A livello di base, un gruppo di Microsoft 365 è un oggetto in Azure Active Directory con un elenco di membri e un accoppiamento a carichi di lavoro correlati, tra cui un sito del team di SharePoint, una cassetta postale di Exchange condivisa, Planner e un'area di lavoro Power BI. È possibile aggiungere o rimuovere persone al gruppo come qualsiasi altro oggetto di sicurezza basato sul gruppo in Active Directory.

![Diagramma che mostra Microsoft 365 gruppi e servizi correlati](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

Per impostazione predefinita, gli utenti Microsoft 365 creare e gestire gruppi. Per altre informazioni sui Microsoft 365, [](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) vedere Informazioni sui gruppi Microsoft 365 e sui gruppi [in Microsoft 365 per architetti IT.](teams-architecture-solutions-posters.md#groups-in-microsoft-365)

## <a name="how-microsoft-365-groups-work-with-teams"></a>Come Microsoft 365 gruppi di lavoro con Teams

Quando si crea un team, viene creato un Microsoft 365 per gestire l'appartenenza al team. I servizi correlati al gruppo, ad esempio un sito SharePoint, un'Power BI di lavoro e così via, vengono creati contemporaneamente.

Le persone che creano team possono scegliere di usare un gruppo Microsoft 365 se sono proprietari del gruppo. Ogni canale del team ha una cartella separata nella raccolta documenti. La creazione di cartelle direttamente nella raccolta documenti non crea canali nel team.

Quando si crea un Microsoft 365 gruppo Outlook o SharePoint, la cassetta postale del gruppo è visibile in Outlook. Quando si crea un team in Teams, la cassetta postale del gruppo è nascosta per impostazione predefinita. È possibile usare il cmdlet [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) con il **parametro HiddenFromExchangeClientsEnabled** per rendere visibile una cassetta postale.

## <a name="group-membership"></a>Appartenenza ai gruppi

Se si rimuove un membro di un team, vengono rimossi anche dal Microsoft 365 gruppo. La rimozione dal gruppo rimuove immediatamente il team e i canali dal Teams client. Se si rimuove una persona da un gruppo usando il interfaccia di amministrazione di Microsoft 365, non avrà più accesso ad altri aspetti della collaborazione, ad esempio raccolta documenti di SharePoint Online, gruppo di Yammer o OneNote. Tuttavia, avranno comunque accesso alla funzionalità di chat del team per circa due ore.

Come procedura consigliata per la gestione dei membri del team, aggiungerli e rimuoverli dal client di Teams per assicurarsi che gli aggiornamenti delle autorizzazioni per altri carichi di lavoro connessi al gruppo si verifichino rapidamente. Se si aggiungono o rimuovono membri del team all'esterno del client di Teams (usando powershell di interfaccia di amministrazione di Microsoft 365, Azure AD o Exchange Online), possono essere necessarie fino a 24 ore prima che le modifiche si riflettano in Teams.

## <a name="deleting-groups-and-teams"></a>Eliminazione di gruppi e team

L'eliminazione di un gruppo Microsoft 365 rimuove l'alias della cassetta postale per le conversazioni Outlook/OWA persistenti e gli inviti alle riunioni Teams e contrassegna il sito SharePoint per l'eliminazione. Sono necessari circa 20 minuti tra la rimozione di un team e il suo effetto Outlook. L'eliminazione di un team dal client Teams verrà rimosso immediatamente dalla visualizzazione per tutti i membri del team. Se si rimuovono i membri di un gruppo di Microsoft 365 in cui è abilitata la funzionalità Teams, potrebbe verificarsi un ritardo di circa due ore prima che il team venga rimosso dalla visualizzazione nel client di Teams per le persone interessate che sono state rimosse.

Per informazioni dettagliate sulle opzioni di fine del ciclo di vita di gruppi e team, vedere Opzioni di fine ciclo di vita per [gruppi,](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) team e Yammer e Archiviare o eliminare un [team in Microsoft Teams](./archive-or-delete-a-team.md).

## <a name="related-topics"></a>Argomenti correlati

[Fondamenti di Microsoft Teams (video)](https://aka.ms/teams-foundations)

[Ripristinare un gruppo eliminato](/microsoft-365/admin/create-groups/restore-deleted-group)