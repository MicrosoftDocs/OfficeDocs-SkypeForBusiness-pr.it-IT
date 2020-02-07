---
title: Configurare un'organizzazione ibrida di Exchange per l'uso con Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Informazioni su come configurare un'organizzazione ibrida di Exchange per l'uso con Microsoft teams.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb81460a5a3d388bc9634cb53ce15655933534c5
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834446"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Configurare un'organizzazione ibrida di Exchange per l'uso con Microsoft Teams
======================================================================

In genere, non è necessario configurare alcuna funzionalità di Exchange Online da usare con Microsoft teams. Per gli scenari ibridi di Exchange, tuttavia, sono necessari alcuni passaggi per garantire la sincronizzazione delle appartenenze dei gruppi tra Exchange Server (locale) ed Exchange Online. Questo implica l'abilitazione della funzionalità writeback di gruppo in Azure AD Connect insieme a diversi script di inizializzazione: [configurare i gruppi di Office 365 con Exchange ibrida locale](https://go.microsoft.com/fwlink/?linkid=854389).
