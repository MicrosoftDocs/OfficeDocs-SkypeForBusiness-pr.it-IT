---
title: Esperienza teams in un sito Microsoft 365 o Office 365 OneDrive e un contratto di locazione multigeo-abilitato per SharePoint Online
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: In questo articolo verranno fornite informazioni sull'uso di team in Microsoft 365 o Office 365 OneDrive e il contratto di locazione multi-Geo abilitato a SharePoint Online.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1fdfd99494b8f65c448a2b1183a183b8cf7477af
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583243"
---
<a name="teams-experience-in-a-microsoft-365-or-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a>Esperienza teams in un sito Microsoft 365 o Office 365 OneDrive e un contratto di locazione multigeo-abilitato per SharePoint Online
===========================================

Microsoft teams è un software di chat di gruppo, l'hub per il lavoro in team in Microsoft 365 e Office 365. È alimentato dal servizio Microsoft 365 groups insieme a SharePoint Online e OneDrive for business per l'esperienza dei suoi file. In un OneDrive for business/SharePoint Online Multi-geo-locazione, in cui il tenant è esteso a molte posizioni geografiche come il Nord America, l'Europa e l'Australia, l'esperienza dei file sottostanti è a conoscenza di più Geo, quindi l'esperienza di teams con la collaborazione di file è anche a livello geo-consapevole. Questa è una delle principali funzionalità all'avanguardia per i team per la superficie di file ospitati in più GEOS nella sua esperienza di file nativo.

Ad esempio, in un contratto di locazione di Contoso con l'Europa come satellite geo e Nord America come Geo centrale, un utente satellite europeo vedrà i file di OneDrive nella scheda file nel riquadro sinistro, anche se i file sono ospitati nella posizione dati in Europa e gli Stati Uniti sono la posizione centrale del tenant. Inoltre, l'utente può accedere ai file usati più di recente sotto la lama di visualizzazione recente. I file recenti possono includere file condivisi con l'utente dagli utenti di altri GEOS e potrebbero essere padroneggiati in altre posizioni geografiche a cui il tenant è esteso. 

Il sito del gruppo di un team specifico è anche a livello di Geo-Aware. Ossia, se un utente satellite europeo sta creando un team, il sito dei gruppi corrispondenti verrà creato nella posizione Europa e i file associati al gruppo del team verranno mantenuti a riposo in tale posizione. Le eventuali esperienze successive, ad esempio il caricamento di un nuovo file o la modifica del file, saranno destinate a tale posizione europea, mantenendo la promessa di data Residency per tali file. Tutto ciò è reso possibile dai gruppi di Microsoft 365 della Fondazione sottostante che diventano più consapevoli della multigeo.

Dato che un contratto multigeo è un unico tenant globale, durante le @ menzioni gli utenti satellitari potranno vedere i loro colleghi da tutto il mondo, indipendentemente dal luogo in cui risiedono. 

Tieni presente che le conversazioni nelle chat e nelle note ISTANTANEe della riunione all'interno dell'esperienza teams non sono a conoscenza di più Geo e vengono mantenute solo all'interno della posizione centrale del tenant. In genere, le conversazioni di chat non vengono applicate alle esigenze di residenza dei dati.

Per altre informazioni su multi-Geo, vedere la [pagina Microsoft Multi-Geo capabilities](https://aka.ms/multi-geo).