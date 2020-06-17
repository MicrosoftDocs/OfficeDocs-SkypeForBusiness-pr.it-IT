---
title: Rimuovere server di archiviazione e di monitoraggio legacy
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Se la distribuzione legacy conteneva un server di archiviazione o un Monitoring Server, dopo la migrazione a Skype for Business Server 2019, i server possono essere rimossi dall'ambiente legacy, purché tutti gli utenti siano stati rimossi da tutti i pool legacy rimanenti. È possibile rimuovere il server di archiviazione o il Monitoring Server in qualsiasi sequenza. Il requisito fondamentale è che tutti gli utenti siano stati rimossi dai pool legacy rimanenti.
ms.openlocfilehash: f5f4da7f7ebf5772bc930d1f92ea3feb590465fd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752168"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="363c8-105">Rimuovere server di archiviazione e di monitoraggio legacy</span><span class="sxs-lookup"><span data-stu-id="363c8-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="363c8-106">Se la distribuzione legacy conteneva un server di archiviazione o un Monitoring Server, dopo la migrazione a Skype for Business Server 2019, i server possono essere rimossi dall'ambiente legacy, purché tutti gli utenti siano stati rimossi da tutti i pool legacy rimanenti.</span><span class="sxs-lookup"><span data-stu-id="363c8-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="363c8-107">È possibile rimuovere il server di archiviazione o il Monitoring Server in qualsiasi sequenza.</span><span class="sxs-lookup"><span data-stu-id="363c8-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="363c8-108">Il requisito fondamentale è che tutti gli utenti siano stati rimossi dai pool legacy rimanenti.</span><span class="sxs-lookup"><span data-stu-id="363c8-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="363c8-109">È possibile spostare gli utenti in Skype for Business Server 2019 attenendosi alle procedure descritte nella [fase 4: spostare gli utenti di test nel pool pilota](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="363c8-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="363c8-110">Dopo aver confermato che tutti gli utenti sono stati rimossi da tutti i pool rimanenti, decommision il server e rimuovere i ruoli.</span><span class="sxs-lookup"><span data-stu-id="363c8-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="363c8-111">Un esempio datato, ma pertinente, è "disinstallazione di Microsoft Lync Server e rimozione dei ruoli del server", che può essere scaricato all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227) .</span><span class="sxs-lookup"><span data-stu-id="363c8-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

