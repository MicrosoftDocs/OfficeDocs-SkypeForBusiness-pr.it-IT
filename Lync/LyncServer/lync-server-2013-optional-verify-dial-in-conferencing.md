---
title: 'Lync Server 2013: (facoltativo) verificare le conferenze telefoniche con accesso esterno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425905(v=OCS.15)
ms:contentKeyID: 48183941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebfebd5dceff50d7d4b7647c7709bb88b7c1fa8e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530773"
---
# <a name="optional-verify-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="441c0-102">Optional Verificare le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="441c0-102">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="441c0-103">_**Ultimo argomento modificato:** 2011-01-21_</span><span class="sxs-lookup"><span data-stu-id="441c0-103">_**Topic Last Modified:** 2011-01-21_</span></span>

<span data-ttu-id="441c0-104">Per verificare che la pagina Web Impostazioni conferenza telefonica con accesso esterno e i numeri di accesso esterno funzionino correttamente, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="441c0-104">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>

  - <span data-ttu-id="441c0-105">Testare la pagina Web Impostazioni conferenza telefonica con accesso esterno eseguendo l'accesso all'URL semplice.</span><span class="sxs-lookup"><span data-stu-id="441c0-105">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>

  - <span data-ttu-id="441c0-p101">Verificare che i numeri di accesso funzionino correttamente per un pool specifico eseguendo lo script riportato più avanti in questo argomento. Questo script simula le chiamate ai numeri di accesso. Per utilizzare lo script, sono necessari l'indirizzo SIP e le credenziali di un client per comunicazioni unificate ospitato nel pool specifico.</span><span class="sxs-lookup"><span data-stu-id="441c0-p101">Test that access numbers work correctly for a specific pool by running the script later in this topic. This script simulates calls to access numbers. You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>

<span data-ttu-id="441c0-109">Questo passaggio è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="441c0-109">This step is optional.</span></span>

<div>

## <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="441c0-110">Per testare i numeri di accesso per un pool specifico</span><span class="sxs-lookup"><span data-stu-id="441c0-110">To test access numbers for a specific pool</span></span>

1.  <span data-ttu-id="441c0-111">Eseguire l'accesso al computer come membro del gruppo RTCUniversalServerAdmins oppure del ruolo **Cs-ServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="441c0-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="441c0-112">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="441c0-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="441c0-113">Al prompt dei comandi eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="441c0-113">Run the following at the command prompt:</span></span>
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    <span data-ttu-id="441c0-p102">Nel rapporto risultante viene mostrato l'esito positivo o negativo, insieme a specifiche informazioni di diagnostica. Il flag –Verbose consente di ottenere informazioni più dettagliate su quanti numeri di accesso sono stati trovati con le relative informazioni.</span><span class="sxs-lookup"><span data-stu-id="441c0-p102">The resulting report shows either Success or Failure, along with specific diagnostic information. The –Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

