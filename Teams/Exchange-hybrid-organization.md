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
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="689a0-103">Configurare un'organizzazione ibrida di Exchange per l'uso con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="689a0-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="689a0-104">In generale, non dovrebbe essere necessario configurare alcuna funzionalità di Exchange Online per l'uso con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="689a0-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="689a0-105">Per gli scenari ibridi di Exchange, tuttavia, sono necessari alcuni passaggi per garantire la sincronizzazione delle appartenenze ai gruppi tra Exchange Server (locale) ed Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="689a0-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="689a0-106">Questa operazione implica l'abilitazione della funzionalità writeback di gruppo in Azure AD Connect e vari script di inizializzazione: Configurare Gruppi di [Microsoft 365](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups)con una distribuzione ibrida di Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="689a0-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Microsoft 365 Groups with on-premises Exchange hybrid](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups).</span></span>
