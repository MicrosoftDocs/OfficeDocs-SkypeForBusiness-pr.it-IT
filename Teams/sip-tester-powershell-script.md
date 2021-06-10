---
title: Script di PowerShell per testare le connessioni di Direct Routing Session Border Controller
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Usare questo esempio di script di PowerShell per testare le connessioni di Direct Routing Session Border Controller in Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: c52febae3d734af49d1b23c7c65ceb0c2f746f7a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834276"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="ab52c-103">Script di PowerShell per testare le connessioni di Direct Routing Session Border Controller</span><span class="sxs-lookup"><span data-stu-id="ab52c-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="ab52c-104">Il client tester SIP è uno script di PowerShell di esempio che è possibile usare per testare le connessioni SBC (Direct Routing Session Border Controller) in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ab52c-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="ab52c-105">Questo script verifica le funzionalità di base di un trunk SIP (Session Initiation Protocol) associato al cliente con il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="ab52c-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="ab52c-106">Lo script invia un test SIP al test runner, attende il risultato e lo presenta in un formato leggibile.</span><span class="sxs-lookup"><span data-stu-id="ab52c-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="ab52c-107">È possibile usare questo script per testare gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab52c-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="ab52c-108">Chiamate in uscita e in ingresso</span><span class="sxs-lookup"><span data-stu-id="ab52c-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="ab52c-109">Anello simultaneo</span><span class="sxs-lookup"><span data-stu-id="ab52c-109">Simultaneous ring</span></span>
- <span data-ttu-id="ab52c-110">Escalation multimediale</span><span class="sxs-lookup"><span data-stu-id="ab52c-110">Media escalation</span></span>
- <span data-ttu-id="ab52c-111">Trasferimento consultivo</span><span class="sxs-lookup"><span data-stu-id="ab52c-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="ab52c-112">Scaricare lo script e la documentazione</span><span class="sxs-lookup"><span data-stu-id="ab52c-112">Download the script and documentation</span></span>

<span data-ttu-id="ab52c-113">Scaricare lo [script client SIP Tester e la documentazione.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="ab52c-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>

  > [!NOTE]
  > <span data-ttu-id="ab52c-114">Lo script client di Tester SIP supporta solo adal.ps versione 3.19.8.1.</span><span class="sxs-lookup"><span data-stu-id="ab52c-114">SIP Tester client script only supports adal.ps version 3.19.8.1.</span></span> <span data-ttu-id="ab52c-115">Se viene usata una versione successiva del adal.ps viene restituito un errore.</span><span class="sxs-lookup"><span data-stu-id="ab52c-115">An error will be returned if a later version of the adal.ps is used.</span></span>
  
  
