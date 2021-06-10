---
title: Configurare un'Exchange ibrida
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Informazioni su come configurare un'Exchange ibrida per l'uso con Microsoft Teams per garantire la sincronizzazione delle appartenenze ai gruppi.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 90250b3d3f3593990d356843bebea324060d6f8b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094608"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Configurare un'Exchange ibrida per l'uso con Microsoft Teams
======================================================================

In generale, non è necessario configurare alcuna funzionalità Exchange Online per l'uso con Microsoft Teams. Tuttavia, per Exchange scenari ibridi, sono necessari passaggi per garantire che le appartenenze ai gruppi siano sincronizzate tra Exchange Server (locale) e Exchange Online. Ciò implica l'abilitazione della funzionalità di writeback di gruppo in Azure AD Connessione insieme a vari script di inizializzazione: Configurare gruppi di Microsoft 365 con gruppi locali Exchange [ibridi.](/exchange/hybrid-deployment/set-up-microsoft-365-groups)