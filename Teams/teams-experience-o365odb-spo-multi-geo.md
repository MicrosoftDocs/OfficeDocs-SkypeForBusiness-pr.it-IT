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
description: In questo articolo verranno fornite informazioni sull'uso di team in un ambiente Microsoft 365 multigeo-Enabled.
ms.openlocfilehash: 1a1689d78f6ce4e35b2e632e4a46ff0ec23a0d15
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2021
ms.locfileid: "49757751"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Esperienza teams in un contratto di locazione multigeo di Microsoft 365

Microsoft teams è un software per la chat di gruppo, l'hub per il lavoro in team in Microsoft 365. È alimentato dal servizio Microsoft 365 groups insieme a SharePoint e OneDrive per l'esperienza di file. In un'organizzazione multi-Geo in cui il tenant è esteso a molte posizioni geografiche come il Nord America, l'Europa e l'Australia, l'esperienza dei file sottostanti è a conoscenza di più Geo, quindi l'esperienza dei team con la collaborazione di file è anche a livello geo-consapevole. In questo modo i team devono eseguire la superficie dei file ospitati in più posizioni geo nella propria esperienza di file nativi.

Ad esempio, in un contratto di locazione di Contoso con l'Europa come satellite geo e Nord America come Geo centrale, un utente satellite europeo vedrà i file di OneDrive nella scheda file nel riquadro sinistro, anche se i file sono ospitati nella posizione dati in Europa e gli Stati Uniti sono la posizione centrale del tenant. Inoltre, l'utente può accedere ai file usati più di recente sotto la lama di visualizzazione recente. I file recenti possono includere file condivisi dagli utenti in altre posizioni geo. 

Il sito di SharePoint di un team specifico è anche a livello geo-Aware. Ovvero, se un utente satellite europeo sta creando un team, il sito di SharePoint corrispondente verrà creato nella posizione Europa e i file associati al team verranno mantenuti a riposo in tale posizione. Le eventuali esperienze successive, ad esempio il caricamento di un nuovo file o la modifica del file, verranno archiviate in quella posizione europea, mantenendo la promessa di data Residency per tali file.

Tieni presente che le conversazioni nelle chat e nelle note ISTANTANEe della riunione all'interno dell'esperienza teams non sono a conoscenza di più Geo e vengono mantenute solo all'interno della posizione centrale dell'organizzazione.

Per altre informazioni su multi-Geo, Vedi [funzionalità Multigeo di Microsoft](https://aka.ms/multi-geo).
