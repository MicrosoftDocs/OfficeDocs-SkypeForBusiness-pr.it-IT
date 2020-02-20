---
title: 'Lync Server 2013: testare le impostazioni di configurazione del trunk SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test SIP trunk configuration settings
ms:assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721880(v=OCS.15)
ms:contentKeyID: 49733814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 625de6144ca793ef475ec77721f8a76178a87404
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="19f3c-102">Testare le impostazioni di configurazione del trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19f3c-102">Test SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19f3c-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="19f3c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="19f3c-p101">Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi. Queste impostazioni consentono di specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="19f3c-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="19f3c-106">Se abilitare il bypass multimediale nei trunk.</span><span class="sxs-lookup"><span data-stu-id="19f3c-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="19f3c-107">Le condizioni in base alle quali vengono inviati pacchetti RTCP (Real-Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="19f3c-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="19f3c-108">Se in ogni trunk è richiesta la crittografia SRTP (Secure Real-Time Protocol).</span><span class="sxs-lookup"><span data-stu-id="19f3c-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="19f3c-109">Quando si installa Microsoft Lync Server 2013, viene creata una raccolta globale di impostazioni di configurazione del trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="19f3c-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="19f3c-110">Gli amministratori inoltre possono creare raccolte di impostazioni personalizzate nell'ambito del sito o del servizio (solo per il servizio gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="19f3c-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="19f3c-111">Gli amministratori possono anche utilizzare il cmdlet Test-CsTrunkConfiguration per verificare che un trunk sia in grado di convertire un numero composto da un utente in un numero gestibile dal gateway.</span><span class="sxs-lookup"><span data-stu-id="19f3c-111">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="19f3c-112">Le impostazioni di configurazione dei trunk possono essere verificate solo utilizzando Windows PowerShell e il cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="19f3c-112">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet.</span></span> <span data-ttu-id="19f3c-113">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19f3c-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="19f3c-114">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="19f3c-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="19f3c-115">Per testare le impostazioni di configurazione del trunk SIP</span><span class="sxs-lookup"><span data-stu-id="19f3c-115">To test SIP trunk configuration settings</span></span>

  - <span data-ttu-id="19f3c-116">Il comando seguente verifica che le impostazioni di configurazione dei trunk per il sito Redmond siano in grado di convertire correttamente il numero composto 4255551212.</span><span class="sxs-lookup"><span data-stu-id="19f3c-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
        $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
        Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk

</div>

</div>

<span> </span>

</div>

</div>

</div>

