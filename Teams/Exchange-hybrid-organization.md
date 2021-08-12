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
ms.openlocfilehash: 4a0480ff8a795addb9ae322478fddb69e9aeceeed14ebca83f27cac34b01bfbb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284476"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Configurare un'Exchange ibrida per l'uso con Microsoft Teams
======================================================================

In generale, non è necessario configurare alcuna funzionalità Exchange Online per l'uso con Microsoft Teams. Tuttavia, per Exchange scenari ibridi, sono necessari passaggi per garantire che le appartenenze ai gruppi siano sincronizzate tra Exchange Server (locale) e Exchange Online. Ciò implica l'abilitazione della funzionalità di writeback di gruppo in Azure AD Connessione insieme a vari script di inizializzazione: Configurare gruppi di Microsoft 365 con gruppi locali Exchange [ibridi.](/exchange/hybrid-deployment/set-up-microsoft-365-groups)