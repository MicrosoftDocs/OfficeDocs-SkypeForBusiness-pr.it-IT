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
description: Informazioni su come configurare un'organizzazione ibrida di Exchange per l'uso con Microsoft Teams per garantire la sincronizzazione delle appartenenze ai gruppi.
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

In generale, non dovrebbe essere necessario configurare alcuna funzionalità di Exchange Online per l'uso con Microsoft Teams. Per gli scenari ibridi di Exchange, tuttavia, sono necessari alcuni passaggi per garantire la sincronizzazione delle appartenenze ai gruppi tra Exchange Server (locale) ed Exchange Online. Questa operazione implica l'abilitazione della funzionalità writeback di gruppo in Azure AD Connect e vari script di inizializzazione: Configurare Gruppi di [Microsoft 365](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups)con una distribuzione ibrida di Exchange locale.
