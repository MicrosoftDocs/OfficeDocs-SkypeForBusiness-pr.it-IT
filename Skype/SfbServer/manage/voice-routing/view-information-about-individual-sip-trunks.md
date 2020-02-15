---
title: Visualizzare informazioni sui singoli trunk SIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In Skype for Business Server, è possibile assegnare più trunk a un singolo gateway PSTN. Questo significa che i gateway e i trunk non sono uguali e gli amministratori devono utilizzare il cmdlet Get-CsTrunk per visualizzare le informazioni relative a un singolo trunk SIP.
ms.openlocfilehash: c5288e676f546e07504f4d8609fcea63913b6457
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048179"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="dc16c-103">Visualizzare informazioni sui singoli trunk SIP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dc16c-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="dc16c-104">In Skype for Business Server, è possibile assegnare più trunk a un singolo gateway PSTN. Questo significa che i gateway e i trunk non sono uguali e che gli amministratori devono utilizzare il cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) per visualizzare le informazioni relative a un singolo trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="dc16c-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="dc16c-105">Il cmdlet Get-CsTrunk può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc16c-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="dc16c-106">**Per visualizzare informazioni su tutti i trunk SIP**</span><span class="sxs-lookup"><span data-stu-id="dc16c-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="dc16c-107">Il comando seguente restituisce informazioni su tutti i trunk SIP in uso nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="dc16c-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="dc16c-108">**Per visualizzare le informazioni relative a uno specifico trunk SIP**</span><span class="sxs-lookup"><span data-stu-id="dc16c-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="dc16c-109">Questo comando restituisce informazioni solo sul trunk SIP con l'identità (Identity) PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="dc16c-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="dc16c-110">**Visualizzazione delle informazioni relative a tutti i trunk SIP assegnati a un pool**</span><span class="sxs-lookup"><span data-stu-id="dc16c-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="dc16c-111">In questo esempio vengono restituite le informazioni su tutti i trunk SIP assegnati al pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="dc16c-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
