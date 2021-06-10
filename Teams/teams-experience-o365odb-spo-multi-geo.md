---
title: Teams in un ambiente Microsoft 365 multi-geo-enabled
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
description: Questo articolo illustra come usare le Teams in un ambiente Microsoft 365 multi-geo-enabled.
ms.openlocfilehash: a1b86cf83a0eabde81331e5311561aa1600d3c7e
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760539"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Teams in una tenancy Microsoft 365 multi-geo-enabled

Microsoft Teams è il software di chat di gruppo, l'hub per il lavoro in team in Microsoft 365 e Office 365. È basato sul servizio gruppi di Microsoft 365, insieme a SharePoint Online e OneDrive for Business per l'esperienza con i file. In una tenancy OneDrive for Business/SharePoint Online Multi-Geo, in cui il tenant viene esteso a molte posizioni geografiche, ad esempio Nord America, Europa e Australia, l'esperienza dei file sottostanti è multi-geo-aware, quindi l'esperienza di Teams con la collaborazione di file è anche multi-geo-aware. Questa funzionalità è una funzionalità chiave all'avanguardia per Teams file in superficie ospitati in più geos nell'esperienza dei file nativi. Sono inclusi anche OneNote e Wiki.

Ad esempio, in una tenancy contoso con l'Europa come geo satellitare e l'America del Nord  come geo centrale, un utente satellitare europeo vede i propri file OneDrive nella scheda File nel riquadro sinistro, anche se i file sono ospitati nella posizione dati Europa e gli Stati Uniti sono la posizione centrale del tenant. Inoltre, l'utente può accedere ai file usati più di recente nel **pannello Visualizzazione** recente. I file recenti possono includere file condivisi da utenti in altre posizioni geografiche. 

Anche il sito SharePoint team specificato è multi-geo-aware. In altri, se un utente satellitare europeo sta creando un team, il sito SharePoint verrà creato nella posizione Europa. I file associati al team verranno mantenuti in quella posizione. Tutte le esperienze successive, ad esempio il caricamento di un nuovo file o la modifica del file, verranno archiviate in tale posizione europea, mantenendo la promessa di residenza dei dati per tali file.

Poiché una tenancy multi-geo è un singolo tenant globale, durante le menzioni @ gli utenti satellitari potranno vedere i colleghi di tutto il mondo, indipendentemente da dove si trovano.

Le conversazioni in chat, i messaggi dei canali e le note o le chat di messaggistica istantanea delle riunioni all'interno dell'esperienza Teams non sono multi-geo-aware e vengono mantenute solo all'interno della posizione centrale del tenant. In genere, le conversazioni chat non vengono applicate alle esigenze di residenza dei dati. Per altre informazioni, vedere [Posizione dei dati in Microsoft Teams](location-of-data-in-teams.md).

Il supporto multi-geo per Teams è in [Microsoft 365 roadmap.](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783)

Per altre informazioni su Multi-Geo, vedere la pagina delle funzionalità [Multi-Geo Microsoft.](https://aka.ms/multi-geo)
