---
title: Processo di migrazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La procedura di migrazione consigliata e supportata per Skype for Business Server 2019 è la migrazione affiancata. Questo argomento descrive il motivo per cui è consigliabile usare la migrazione affiancata e include anche informazioni sui test di coesistenza.
ms.openlocfilehash: 7d8ce6513535871939894092850ad0526b1b6a63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813414"
---
# <a name="migration-process"></a><span data-ttu-id="c1760-104">Processo di migrazione</span><span class="sxs-lookup"><span data-stu-id="c1760-104">Migration process</span></span>

<span data-ttu-id="c1760-105">La procedura di migrazione consigliata e supportata per Skype for Business Server 2019 è la migrazione affiancata.</span><span class="sxs-lookup"><span data-stu-id="c1760-105">The recommended and supported migration procedure for Skype for Business Server 2019 is side-by-side migration.</span></span> <span data-ttu-id="c1760-106">Questo argomento descrive il motivo per cui è consigliabile usare la migrazione affiancata e include anche informazioni sui test di coesistenza.</span><span class="sxs-lookup"><span data-stu-id="c1760-106">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>
  
## <a name="side-by-side-migration"></a><span data-ttu-id="c1760-107">Migrazione affiancata</span><span class="sxs-lookup"><span data-stu-id="c1760-107">Side-By-Side Migration</span></span>

<span data-ttu-id="c1760-108">In quasi tutte le migrazioni devi usare il percorso di migrazione affiancato.</span><span class="sxs-lookup"><span data-stu-id="c1760-108">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="c1760-109">In una migrazione affiancata si distribuisce un nuovo server con Skype for Business Server 2019 accanto a un server corrispondente che sta eseguendo una versione precedente e quindi trasferisce le operazioni nel nuovo server.</span><span class="sxs-lookup"><span data-stu-id="c1760-109">In a side-by-side migration, you deploy a new server with Skype for Business Server 2019 alongside a corresponding server that is running a previous version, and then transfer operations to the new server.</span></span> <span data-ttu-id="c1760-110">Se è necessario eseguire il rollback alla versione precedente, è necessario spostare di nuovo solo le operazioni nei server originali.</span><span class="sxs-lookup"><span data-stu-id="c1760-110">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="c1760-111">Tieni presente che in questa situazione le nuove riunioni pianificate con i client aggiornati non funzioneranno e anche i client dovranno essere declassati.</span><span class="sxs-lookup"><span data-stu-id="c1760-111">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>
  
## <a name="coexistence-testing"></a><span data-ttu-id="c1760-112">Test di coesistenza</span><span class="sxs-lookup"><span data-stu-id="c1760-112">Coexistence Testing</span></span>

<span data-ttu-id="c1760-113">Dopo aver implementato Skype for Business Server 2019 in parallelo alla versione precedente, la distribuzione rappresenta uno stato di verifica della coesistenza di Skype for Business Server 2019 e la versione precedente.</span><span class="sxs-lookup"><span data-stu-id="c1760-113">After you have deployed Skype for Business Server 2019 in parallel with the previous version, the deployment represents a coexistence testing state of Skype for Business Server 2019 and the previous version.</span></span> <span data-ttu-id="c1760-114">In questo stato è importante testare e verificare che i servizi vengano avviati, ogni sito può essere amministrato e i client possono comunicare con utenti correnti e legacy.</span><span class="sxs-lookup"><span data-stu-id="c1760-114">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="c1760-115">Prima della migrazione di tutti gli utenti, è molto importante comprendere lo stato di ogni distribuzione e verificare che ogni distribuzione sia funzionale e funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="c1760-115">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="c1760-116">In genere, la fase di test di coesistenza esiste durante il test pilota di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c1760-116">Typically, the coexistence testing phase exists throughout the pilot testing of Skype for Business Server 2019.</span></span> <span data-ttu-id="c1760-117">Gli utenti legacy vengono spostati in Skype for Business Server 2019 per un periodo di tempo per verificare che la compatibilità e le caratteristiche e le funzionalità delle applicazioni funzionino correttamente.</span><span class="sxs-lookup"><span data-stu-id="c1760-117">Legacy users are moved to Skype for Business Server 2019 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="c1760-118">Dopo il test pilota, gli utenti e le applicazioni vengono spostati nella versione di produzione di Skype for Business Server 2019 e i pool e le applicazioni legacy della versione precedente vengono ritirati.</span><span class="sxs-lookup"><span data-stu-id="c1760-118">After pilot testing, users and applications are moved to the production version of Skype for Business Server 2019, and the legacy pools and applications of the previous version are retired.</span></span>
  
