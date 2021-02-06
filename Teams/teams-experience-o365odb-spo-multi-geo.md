---
title: Esperienza teams in un ambiente Microsoft 365 multigeo-Enabled
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
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
description: In questo articolo imparerai a usare teams in un ambiente Microsoft 365 multigeo-Enabled.
ms.openlocfilehash: 43abe221c6159e6dfed1705f5cbc4839c1ce57db
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122246"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Esperienza teams in un contratto di locazione multigeo di Microsoft 365

Microsoft teams è un software di chat di gruppo, l'hub per il lavoro in team in Microsoft 365 e Office 365. È alimentato dal servizio Microsoft 365 groups insieme a SharePoint Online e OneDrive for business per l'esperienza dei suoi file. In un OneDrive for business/SharePoint Online Multi-geo-locazione, in cui il tenant è esteso a molte posizioni geografiche come il Nord America, l'Europa e l'Australia, l'esperienza dei file sottostanti è multi-Geo-Aware, quindi l'esperienza dei team con la collaborazione di file è anche multi-Geo-Aware. Questa funzionalità è una delle principali funzionalità all'avanguardia per i team per la superficie di file ospitati in più GEOS nella sua esperienza di file nativo. Questo include anche i file di OneNote e wiki.

Ad esempio, in un contratto di locazione di Contoso con l'Europa come satellite geo e Nord America come Geo centrale, un utente satellite europeo vedrà i propri file di OneDrive nella scheda **file** nel riquadro sinistro, anche se i file sono ospitati nella posizione dati in Europa e gli Stati Uniti sono la posizione centrale del tenant. Inoltre, l'utente può accedere ai file usati più di recente sotto la lama di visualizzazione **recente** . I file recenti possono includere file condivisi dagli utenti in altre posizioni geo. 

Il sito di SharePoint di un team specifico è anche a livello geo-consapevole. Ovvero, se un utente satellite europeo sta creando un team, il sito di SharePoint corrispondente verrà creato nella posizione Europa. I file associati al team verranno mantenuti a riposo in tale posizione. Le eventuali esperienze successive, ad esempio il caricamento di un nuovo file o la modifica del file, verranno archiviate in quella posizione europea, mantenendo la promessa di data Residency per tali file.

Dato che un contratto di locazione multigeo è un unico tenant globale, durante @ menzioni gli utenti satellitari potranno vedere i loro colleghi provenienti da tutto il mondo, ovunque si trovino.

Le conversazioni in chat, nei messaggi di canale e nelle note/chat ISTANTANEe della riunione all'interno dell'esperienza teams non sono multi-Geo-Aware e vengono mantenute solo all'interno della posizione centrale del tenant. In genere, le conversazioni di chat non vengono applicate alle esigenze di residenza dei dati. Per altre informazioni, vedere la [posizione dei dati in Microsoft teams](location-of-data-in-teams.md).

Per altre info su multi-Geo, vedere la [pagina Microsoft Multi-Geo capabilities](https://aka.ms/multi-geo).
