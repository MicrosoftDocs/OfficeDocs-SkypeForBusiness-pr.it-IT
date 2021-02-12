---
title: Esperienza di Teams in un ambiente Multi-Geo-enabled di Microsoft 365
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
description: In questo articolo imparerai a usare Teams in un ambiente multi-geo-abilitato per Microsoft 365.
ms.openlocfilehash: 43abe221c6159e6dfed1705f5cbc4839c1ce57db
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122246"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Esperienza di Teams in una tenancy multi-geo-enabled di Microsoft 365

Microsoft Teams è un software di chat di gruppo, l'hub per il lavoro in team in Microsoft 365 e Office 365. È basato sul servizio Gruppi di Microsoft 365 insieme a SharePoint Online e OneDrive for Business per l'esperienza con i file. In una tenancy multi-geo di OneDrive for Business/SharePoint Online, in cui il tenant viene esteso a molte aree geografiche, come Nord America, Europa e Australia, l'esperienza dei file sottostanti è con supporto multi-geo, quindi anche l'esperienza di Teams per la collaborazione dei file è multi-geo.. Questa funzionalità è una funzionalità chiave all'avanguardia che consente a Teams di visualizzare i file ospitati su più elementi geografici nell'esperienza dei file nativi. Sono inclusi anche i file di OneNote e Wiki.

Ad esempio, in una tenancy Contoso con l'Europa come geo satellitare e l'America del  Nord come geo centrale, un utente satellitare europeo vede i propri file di OneDrive nella scheda File nel riquadro sinistro, anche se i file sono ospitati nella posizione dei dati in Europa e gli Stati Uniti sono la posizione centrale del tenant. Inoltre, l'utente può accedere ai file usati più di recente nel blade **Visualizzazione** recente. I file recenti possono includere file condivisi da utenti in altre posizioni geografiche. 

Anche il sito di SharePoint di un determinato team è multi-geo-aware. In altri caso, se un utente satellitare europeo sta creando un team, il sito di SharePoint corrispondente verrà creato nella località europa. I file associati al team verranno mantenuti in quella posizione. Tutte le esperienze successive, ad esempio il caricamento di un nuovo file o la modifica del file, verranno archiviate in questa posizione europea, mantenendo la residenza dei dati per tali file.

Una tenancy multi-geo è un singolo tenant globale, quindi durante le @menzioni gli utenti satellitari potranno vedere i colleghi di tutto il mondo, indipendentemente da dove si trova.

Le conversazioni in chat, i messaggi nei canali, le note di messaggistica istantanea delle riunioni e le chat all'interno dell'esperienza Teams non sono multi-geo-aware e sono tutte conservate solo all'interno della posizione centrale del tenant. In genere, le conversazioni di chat non vengono applicate alle esigenze di residenza dei dati. Per altre informazioni, vedere [Posizione dei dati in Microsoft Teams.](location-of-data-in-teams.md)

Per altre informazioni su Multi-Geo, vedere la pagina delle funzionalità [Microsoft Multi-Geo.](https://aka.ms/multi-geo)
