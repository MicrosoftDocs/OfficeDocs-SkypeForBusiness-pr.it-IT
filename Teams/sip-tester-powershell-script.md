---
title: Script di PowerShell per testare le connessioni del controller dei confini della sessione di routing diretto
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Usare questo esempio di script di PowerShell per testare le connessioni del controller dei confini della sessione di routing diretto in Microsoft Teams.
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
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="d4d56-103">Script di PowerShell per testare le connessioni del controller dei confini della sessione di routing diretto</span><span class="sxs-lookup"><span data-stu-id="d4d56-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="d4d56-104">Il client Tester SIP è uno script di PowerShell di esempio che è possibile usare per testare le connessioni SBC (Direct Routing Session Border Controller) in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d4d56-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="d4d56-105">Questo script verifica le funzionalità di base di un trunk SIP (Session Initiation Protocol) associato al cliente con routing diretto.</span><span class="sxs-lookup"><span data-stu-id="d4d56-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="d4d56-106">Lo script invia un test SIP al test runner, attende il risultato e quindi lo presenta in un formato leggibile.</span><span class="sxs-lookup"><span data-stu-id="d4d56-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="d4d56-107">È possibile usare questo script per testare gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4d56-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="d4d56-108">Chiamate in entrata e in uscita</span><span class="sxs-lookup"><span data-stu-id="d4d56-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="d4d56-109">Squillo simultaneo</span><span class="sxs-lookup"><span data-stu-id="d4d56-109">Simultaneous ring</span></span>
- <span data-ttu-id="d4d56-110">Riassegnazione dei supporti</span><span class="sxs-lookup"><span data-stu-id="d4d56-110">Media escalation</span></span>
- <span data-ttu-id="d4d56-111">Trasferimento consultivo</span><span class="sxs-lookup"><span data-stu-id="d4d56-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="d4d56-112">Scaricare lo script e la documentazione</span><span class="sxs-lookup"><span data-stu-id="d4d56-112">Download the script and documentation</span></span>

<span data-ttu-id="d4d56-113">Scaricare lo [script client tester SIP e la documentazione.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="d4d56-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>

  > [!NOTE]
  > <span data-ttu-id="d4d56-114">Solo script client tester SIP adal.ps versione 3.19.8.1.</span><span class="sxs-lookup"><span data-stu-id="d4d56-114">SIP Tester client script only supports adal.ps version 3.19.8.1.</span></span> <span data-ttu-id="d4d56-115">Se si usa una versione successiva del adal.ps viene restituito un errore.</span><span class="sxs-lookup"><span data-stu-id="d4d56-115">An error will be returned if a later version of the adal.ps is used.</span></span>
  
  
