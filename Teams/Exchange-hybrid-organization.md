---
title: Configurare un'organizzazione ibrida di Exchange
author: JoanneHendrickson
ms.author: jhendr
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
description: Informazioni su come configurare un'organizzazione ibrida di Exchange da usare con Microsoft Teams per garantire la sincronizzazione delle appartenenze ai gruppi.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cb2471a2680218a69daa74d20b27c4b7642fa1d7
ms.sourcegitcommit: fc87f4300f53abf7a049936944abb21d0cade0d9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2022
ms.locfileid: "68480676"
---
# <a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Configurare un'organizzazione ibrida di Exchange per l'uso con Microsoft Teams

In generale, non è necessario configurare alcuna funzionalità di Exchange Online per l'uso con Microsoft Teams. Tuttavia, per gli scenari ibridi di Exchange sono necessari alcuni passaggi per assicurarsi che le appartenenze ai gruppi vengano sincronizzate tra Exchange Server (locale) e Exchange Online. Ciò implica l'abilitazione della funzionalità writeback di gruppo in Azure AD Connect insieme a vari script di inizializzazione: [Configurare Gruppi di Microsoft 365 con exchange ibrido locale](/exchange/hybrid-deployment/set-up-microsoft-365-groups).