---
title: Creare una mappa dell'edificio per il dashboard di qualità delle chiamate (Call Quality Dashboard)
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Informazioni su come creare una mappa dell'edificio che è possibile usare per caricare i dati del tenant e della creazione in dashboard qualità chiamata (Call Quality Dashboard).
ms.openlocfilehash: 18e88c2de64d2d63589a3cd2ebddbc9643fe4522
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086102"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a><span data-ttu-id="ef1a0-103">Creare una mappa dell'edificio per il dashboard di qualità delle chiamate (Call Quality Dashboard)</span><span class="sxs-lookup"><span data-stu-id="ef1a0-103">Create a building map for Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="ef1a0-104">In una distribuzione di Microsoft teams o Skype for business online tutti i client sono esterni.</span><span class="sxs-lookup"><span data-stu-id="ef1a0-104">In a Microsoft Teams or Skype for Business Online deployment, all clients are external.</span></span> <span data-ttu-id="ef1a0-105">Di conseguenza, per impostazione predefinita, tutti i client vengono segnalati come esterni in Call Quality Dashboard (Call Quality Dashboard), indipendentemente dal fatto che il client sia connesso a una rete aziendale interna.</span><span class="sxs-lookup"><span data-stu-id="ef1a0-105">As a result, by default, all clients are reported as outside in Call Quality Dashboard (CQD), regardless of whether the client is connected on an internal corporate network.</span></span>

<span data-ttu-id="ef1a0-106">Quando si usa call Quality dashboard, è necessario conoscere la posizione di un endpoint e stabilire se si è connessi a una rete che si riesce a gestire o a una rete che non si riesce a gestire, perché è possibile migliorare solo le reti che è possibile gestire.</span><span class="sxs-lookup"><span data-stu-id="ef1a0-106">When you work with CQD, you need to know the location of an endpoint and whether it was connected to a network you can manage or a network you can't manage, the assumption being that you can only improve networks you can manage.</span></span> <span data-ttu-id="ef1a0-107">Caricando subnet e costruendo informazioni in Call Quality dashboard, puoi abilitare Call Quality dashboard per determinare se l'endpoint è connesso a una rete interna (gestita) o a una rete esterna (non gestita).</span><span class="sxs-lookup"><span data-stu-id="ef1a0-107">By uploading subnet and building information to CQD, you enable CQD to determine whether the endpoint was connected to an internal (managed) network or to an external (unmanaged) network.</span></span> <span data-ttu-id="ef1a0-108">Ecco perché è importante creare una mappa dell'edificio per l'organizzazione e [caricarla in Call Quality dashboard](CQD-upload-tenant-building-data.md).</span><span class="sxs-lookup"><span data-stu-id="ef1a0-108">That's why it's important to create a building map for your organization and [upload it to CQD](CQD-upload-tenant-building-data.md).</span></span>

## <a name="building-mapping-tools"></a><span data-ttu-id="ef1a0-109">Strumenti di mapping della creazione</span><span class="sxs-lookup"><span data-stu-id="ef1a0-109">Building mapping tools</span></span>

<span data-ttu-id="ef1a0-110">Esistono diversi modi per eseguire il mapping delle subnet dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ef1a0-110">There are many ways to map your organization's subnets.</span></span> <span data-ttu-id="ef1a0-111">Se hai bisogno di assistenza, puoi usare il modulo di PowerShell CQDTools descritto in questo [post di Blog](https://aka.ms/cqdtools).</span><span class="sxs-lookup"><span data-stu-id="ef1a0-111">If you need help, you can use the CQDTools PowerShell Module described in this [blog post](https://aka.ms/cqdtools).</span></span> <span data-ttu-id="ef1a0-112">Questi strumenti sono basati su PowerShell e usano i siti e i servizi Active Directory (AD) e i servizi DHCP Microsoft per aiutare a precompilare il file di costruzione.</span><span class="sxs-lookup"><span data-stu-id="ef1a0-112">These tools are based on PowerShell and use Active Directory (AD) Sites and Services and Microsoft DHCP services to help pre-populate your building file.</span></span> <span data-ttu-id="ef1a0-113">Questi strumenti saranno utili per le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef1a0-113">These tools will help with the following tasks:</span></span>

1. <span data-ttu-id="ef1a0-114">Eseguire query su siti e servizi di annunci e creare un file di costruzione basato sulle informazioni contenute in.</span><span class="sxs-lookup"><span data-stu-id="ef1a0-114">Query AD Sites and Services, and create a building file based on the information contained within.</span></span>
1. <span data-ttu-id="ef1a0-115">Eseguire una query su un server DHCP o server Microsoft per estrarre le informazioni sulla subnet e creare automaticamente un file di costruzione.</span><span class="sxs-lookup"><span data-stu-id="ef1a0-115">Query a Microsoft DHCP server or servers to pull subnet information and automatically create a building file.</span></span>
1. <span data-ttu-id="ef1a0-116">Convalidare un file di costruzione esistente, verificando i duplicati e le sovrapposizioni.</span><span class="sxs-lookup"><span data-stu-id="ef1a0-116">Validate an existing building file, checking for duplicates and overlaps.</span></span>
1. <span data-ttu-id="ef1a0-117">Trovare subnet non mappate in Call Quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="ef1a0-117">Find unmapped subnets in CQD.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ef1a0-118">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ef1a0-118">Related topics</span></span>

[<span data-ttu-id="ef1a0-119">Caricare i dati del tenant e della creazione in Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="ef1a0-119">Upload tenant and building data in CQD</span></span>](CQD-upload-tenant-building-data.md)