---
title: 'Lync Server 2013: (Facoltativo) Verificare le conferenze telefoniche con accesso esterno'
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
ms.openlocfilehash: f1b5f078ccd5e95df708012b7be1527736133392
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="7b811-102">(Facoltativo) Verificare le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b811-102">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b811-103">_**Argomento Ultima modifica:** 2011-01-21_</span><span class="sxs-lookup"><span data-stu-id="7b811-103">_**Topic Last Modified:** 2011-01-21_</span></span>

<span data-ttu-id="7b811-104">Per verificare che la pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno e i numeri per le connessioni in ingresso funzionino correttamente, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b811-104">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>

  - <span data-ttu-id="7b811-105">Testare la pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno accedendo all'URL semplice.</span><span class="sxs-lookup"><span data-stu-id="7b811-105">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>

  - <span data-ttu-id="7b811-106">Verificare che i numeri di accesso funzionino correttamente per un pool specifico eseguendo lo script più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7b811-106">Test that access numbers work correctly for a specific pool by running the script later in this topic.</span></span> <span data-ttu-id="7b811-107">Questo script simula le chiamate ai numeri di accesso.</span><span class="sxs-lookup"><span data-stu-id="7b811-107">This script simulates calls to access numbers.</span></span> <span data-ttu-id="7b811-108">È necessario l'indirizzo SIP e le credenziali di un client Unified Communications (UC) ospitato nel pool specifico per l'uso di questo script.</span><span class="sxs-lookup"><span data-stu-id="7b811-108">You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>

<span data-ttu-id="7b811-109">Questo passaggio è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7b811-109">This step is optional.</span></span>

<div>

## <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="7b811-110">Per testare i numeri di accesso per un pool specifico</span><span class="sxs-lookup"><span data-stu-id="7b811-110">To test access numbers for a specific pool</span></span>

1.  <span data-ttu-id="7b811-111">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo **Cs-ServerAdministrator** o **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="7b811-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="7b811-112">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7b811-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7b811-113">Eseguire la procedura seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="7b811-113">Run the following at the command prompt:</span></span>
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    <span data-ttu-id="7b811-114">Il report risultante Mostra l'esito positivo o negativo, insieme a specifiche informazioni di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="7b811-114">The resulting report shows either Success or Failure, along with specific diagnostic information.</span></span> <span data-ttu-id="7b811-115">Il contrassegno-Verbose fornisce informazioni più dettagliate sul numero di numeri di accesso trovati e sui relativi dettagli.</span><span class="sxs-lookup"><span data-stu-id="7b811-115">The –Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

