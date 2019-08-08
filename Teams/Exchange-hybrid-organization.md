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
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 68b2fee13668db8ba3986302d58bc16b0fa89080
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235462"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="743ac-103">Configurare un'organizzazione ibrida di Exchange per l'uso con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="743ac-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="743ac-104">In genere, non è necessario configurare alcuna funzionalità di Exchange Online da usare con Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="743ac-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="743ac-105">Per gli scenari ibridi di Exchange, tuttavia, sono necessari alcuni passaggi per garantire la sincronizzazione delle appartenenze dei gruppi tra Exchange Server (locale) ed Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="743ac-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="743ac-106">Questo implica l'abilitazione della funzionalità writeback di gruppo in Azure AD Connect insieme a diversi script di inizializzazione: [configurare i gruppi di Office 365 con Exchange ibrida locale](https://go.microsoft.com/fwlink/?linkid=854389).</span><span class="sxs-lookup"><span data-stu-id="743ac-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389).</span></span>
