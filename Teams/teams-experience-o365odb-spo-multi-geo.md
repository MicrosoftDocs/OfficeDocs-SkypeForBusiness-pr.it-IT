---
title: Esperienza teams in una locazione di Office 365 OneDrive e SharePoint Online Multi-Geo-Enabled
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: Informazioni sull'uso di team in un contratto di locazione di Office 365 OneDrive e SharePoint Online Multi-Geo-Enabled.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d81554517a42fd05b8f81097dc01f8dc72977c72
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243832"
---
<a name="teams-experience-in-an-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a>Esperienza teams in una locazione di Office 365 OneDrive e SharePoint Online Multi-Geo-Enabled
===========================================

Microsoft teams è un software per la chat di gruppo, l'hub per il lavoro in team in Office 365. È alimentato dal servizio gruppi di Office 365 insieme a SharePoint Online e OneDrive for business per l'esperienza dei suoi file. In un OneDrive for business/SharePoint Online Multi-geo-locazione, in cui il tenant è esteso a molte posizioni geografiche come il Nord America, l'Europa e l'Australia, l'esperienza dei file sottostanti è a conoscenza di più Geo, quindi l'esperienza dei team con file la collaborazione è anche multi-Geo-Aware. Questa è una delle principali funzionalità all'avanguardia per i team per la superficie di file ospitati in più GEOS nella sua esperienza di file nativo.

Ad esempio, in un contratto di locazione di Contoso con l'Europa come satellite geo e Nord America come Geo centrale, un utente satellite europeo vedrà i propri file di OneDrive nella scheda file nel riquadro sinistro, anche se i file sono ospitati nella posizione dati in Europa e in United Stat es è la posizione centrale del tenant. Inoltre, l'utente può accedere ai file usati più di recente sotto la lama di visualizzazione recente. I file recenti possono includere file condivisi con l'utente dagli utenti di altri GEOS e potrebbero essere padroneggiati in altre posizioni geografiche a cui il tenant è esteso. 

Il sito del gruppo di un team specifico è anche a livello di Geo-Aware. Ossia, se un utente satellite europeo sta creando un team, il sito dei gruppi corrispondenti verrà creato nella posizione Europa e i file associati al gruppo del team verranno mantenuti a riposo in tale posizione. Le eventuali esperienze successive, ad esempio il caricamento di un nuovo file o la modifica del file, saranno destinate a tale posizione europea, mantenendo la promessa di data Residency per tali file. Tutto ciò è reso possibile dai gruppi della Fondazione sottostante Office 365 che diventano più consapevoli della multigeo.

Dato che un contratto multigeo è un unico tenant globale, durante le @ menzioni gli utenti satellitari potranno vedere i loro colleghi da tutto il mondo, indipendentemente dal luogo in cui risiedono. 

Tieni presente che le conversazioni nelle chat e nelle note ISTANTANEe della riunione all'interno dell'esperienza teams non sono a conoscenza di più Geo e vengono mantenute solo all'interno della posizione centrale del tenant. In genere, le conversazioni di chat non vengono applicate alle esigenze di residenza dei dati.

Per altre informazioni su Office 365 multi-Geo, vedere la [pagina Microsoft Multi-Geo capabilities](https://aka.ms/multi-geo).