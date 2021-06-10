---
title: Creare una mappa dell'edificio per Call Quality Dashboard (CQD)
ms.author: serdars
author: SerdarSoysal
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
description: Informazioni su come creare una mappa dell'edificio che è possibile usare per caricare i dati del tenant e della creazione in Call Quality Dashboard (CQD).
ms.openlocfilehash: 890e5e9b394cf8b600e635014c90ebb9053a1e07
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584035"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a><span data-ttu-id="6456e-103">Creare una mappa dell'edificio per Call Quality Dashboard (CQD)</span><span class="sxs-lookup"><span data-stu-id="6456e-103">Create a building map for Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="6456e-104">In una Microsoft Teams o Skype for Business online tutti i client sono esterni.</span><span class="sxs-lookup"><span data-stu-id="6456e-104">In a Microsoft Teams or Skype for Business Online deployment, all clients are external.</span></span> <span data-ttu-id="6456e-105">Di conseguenza, per impostazione predefinita, tutti i client vengono segnalati come esterni in Call Quality Dashboard (CQD), indipendentemente dal fatto che il client sia connesso a una rete aziendale interna.</span><span class="sxs-lookup"><span data-stu-id="6456e-105">As a result, by default, all clients are reported as outside in Call Quality Dashboard (CQD), regardless of whether the client is connected on an internal corporate network.</span></span>

<span data-ttu-id="6456e-106">Quando si lavora con CQD, è necessario conoscere la posizione di un endpoint e se è stato connesso a una rete che è possibile gestire o a una rete che non è possibile gestire, presupponendo che sia possibile migliorare solo le reti che è possibile gestire.</span><span class="sxs-lookup"><span data-stu-id="6456e-106">When you work with CQD, you need to know the location of an endpoint and whether it was connected to a network you can manage or a network you can't manage, the assumption being that you can only improve networks you can manage.</span></span> <span data-ttu-id="6456e-107">Caricando le informazioni sulla subnet e sull'edificio in CQD, si abilita CQD per determinare se l'endpoint era connesso a una rete interna (gestita) o a una rete esterna (non gestita).</span><span class="sxs-lookup"><span data-stu-id="6456e-107">By uploading subnet and building information to CQD, you enable CQD to determine whether the endpoint was connected to an internal (managed) network or to an external (unmanaged) network.</span></span> <span data-ttu-id="6456e-108">Ecco perché è importante creare una mappa dell'edificio per l'organizzazione e [caricarla in CQD.](CQD-upload-tenant-building-data.md)</span><span class="sxs-lookup"><span data-stu-id="6456e-108">That's why it's important to create a building map for your organization and [upload it to CQD](CQD-upload-tenant-building-data.md).</span></span>

## <a name="building-mapping-tools"></a><span data-ttu-id="6456e-109">Strumenti di mappatura dell'edificio</span><span class="sxs-lookup"><span data-stu-id="6456e-109">Building mapping tools</span></span>

<span data-ttu-id="6456e-110">Esistono molti modi per eseguire il mapping delle subnet dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6456e-110">There are many ways to map your organization's subnets.</span></span> <span data-ttu-id="6456e-111">Se serve assistenza, è possibile usare il modulo di PowerShell CQDTools descritto in questo [post di blog.](https://aka.ms/cqdtools)</span><span class="sxs-lookup"><span data-stu-id="6456e-111">If you need help, you can use the CQDTools PowerShell Module described in this [blog post](https://aka.ms/cqdtools).</span></span> <span data-ttu-id="6456e-112">Questi strumenti si basano su PowerShell e usano Siti e servizi di Active Directory (AD) e i servizi MICROSOFT DHCP per precompilare il file di edificio.</span><span class="sxs-lookup"><span data-stu-id="6456e-112">These tools are based on PowerShell and use Active Directory (AD) Sites and Services and Microsoft DHCP services to help pre-populate your building file.</span></span> <span data-ttu-id="6456e-113">Questi strumenti consentono di eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="6456e-113">These tools will help with the following tasks:</span></span>

1. <span data-ttu-id="6456e-114">Eseguire query su Siti e servizi di Active Directory e creare un file di edificio in base alle informazioni contenute all'interno.</span><span class="sxs-lookup"><span data-stu-id="6456e-114">Query AD Sites and Services, and create a building file based on the information contained within.</span></span>
1. <span data-ttu-id="6456e-115">Eseguire una query su uno o più server MICROSOFT DHCP per estrarre le informazioni sulla subnet e creare automaticamente un file di edificio.</span><span class="sxs-lookup"><span data-stu-id="6456e-115">Query a Microsoft DHCP server or servers to pull subnet information and automatically create a building file.</span></span>
1. <span data-ttu-id="6456e-116">Convalidare un file di edificio esistente, verificando la presenza di duplicati e sovrapposizioni.</span><span class="sxs-lookup"><span data-stu-id="6456e-116">Validate an existing building file, checking for duplicates and overlaps.</span></span>
1. <span data-ttu-id="6456e-117">Trovare subnet non mappate in CQD.</span><span class="sxs-lookup"><span data-stu-id="6456e-117">Find unmapped subnets in CQD.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6456e-118">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6456e-118">Related topics</span></span>

[<span data-ttu-id="6456e-119">Upload tenant e creazione di dati in CQD</span><span class="sxs-lookup"><span data-stu-id="6456e-119">Upload tenant and building data in CQD</span></span>](CQD-upload-tenant-building-data.md)