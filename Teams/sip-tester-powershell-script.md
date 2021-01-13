---
title: Script di PowerShell per testare le connessioni del controller di bordo della sessione di routing diretto
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Usare questo esempio di script di PowerShell per testare le connessioni del controller di bordo della sessione di routing diretto in Microsoft teams.
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
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="625ed-103">Script di PowerShell per testare le connessioni del controller di bordo della sessione di routing diretto</span><span class="sxs-lookup"><span data-stu-id="625ed-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="625ed-104">Il client tester SIP è uno script di PowerShell di esempio che puoi usare per testare le connessioni SBC (Direct routing session border controller) in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="625ed-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="625ed-105">Questo script verifica le funzionalità di base di un trunk SIP (Session Initiation Protocol) associato al cliente con routing diretto.</span><span class="sxs-lookup"><span data-stu-id="625ed-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="625ed-106">Lo script Invia un test SIP al Runner di prova, attende il risultato e lo presenta in un formato leggibile.</span><span class="sxs-lookup"><span data-stu-id="625ed-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="625ed-107">Puoi usare questo script per testare gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="625ed-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="625ed-108">Chiamate in uscita e in ingresso</span><span class="sxs-lookup"><span data-stu-id="625ed-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="625ed-109">Squillo simultaneo</span><span class="sxs-lookup"><span data-stu-id="625ed-109">Simultaneous ring</span></span>
- <span data-ttu-id="625ed-110">Escalation multimediale</span><span class="sxs-lookup"><span data-stu-id="625ed-110">Media escalation</span></span>
- <span data-ttu-id="625ed-111">Trasferimento consultivo</span><span class="sxs-lookup"><span data-stu-id="625ed-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="625ed-112">Scaricare lo script e la documentazione</span><span class="sxs-lookup"><span data-stu-id="625ed-112">Download the script and documentation</span></span>

<span data-ttu-id="625ed-113">Scaricare lo [script e la documentazione del client del tester SIP](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="625ed-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>

  > [!NOTE]
  > <span data-ttu-id="625ed-114">Lo script client di SIP tester supporta solo adal.ps versione 3.19.8.1.</span><span class="sxs-lookup"><span data-stu-id="625ed-114">SIP Tester client script only supports adal.ps version 3.19.8.1.</span></span> <span data-ttu-id="625ed-115">Verrà restituito un errore se viene usata una versione più recente di adal.ps.</span><span class="sxs-lookup"><span data-stu-id="625ed-115">An error will be returned if a later version of the adal.ps is used.</span></span>
  
  
