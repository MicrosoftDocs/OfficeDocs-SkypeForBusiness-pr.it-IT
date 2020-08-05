---
title: Configurare un'organizzazione ibrida di Exchange
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Informazioni su come configurare un'organizzazione ibrida di Exchange da usare con Microsoft teams per garantire la sincronizzazione delle appartenenze ai gruppi.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1061ce633dcd1db8f956a37143850deed9855e56
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "46551962"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Configurare un'organizzazione ibrida di Exchange per l'uso con Microsoft Teams
======================================================================

In genere, non è necessario configurare alcuna funzionalità di Exchange Online da usare con Microsoft teams. Per gli scenari ibridi di Exchange, tuttavia, sono necessari alcuni passaggi per garantire la sincronizzazione delle appartenenze dei gruppi tra Exchange Server (locale) ed Exchange Online. Questo implica l'abilitazione della funzionalità writeback del gruppo in Azure AD Connect insieme a diversi script di inizializzazione: [configurare i gruppi Microsoft 365 con Exchange ibrida locale](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups).
