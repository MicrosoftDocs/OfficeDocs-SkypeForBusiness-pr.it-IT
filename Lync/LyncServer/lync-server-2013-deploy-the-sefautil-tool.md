---
title: 'Lync Server 2013: distribuire lo strumento SEFAUtil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcd995a99514fa54a221e17f1ea556565cbebdcb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a><span data-ttu-id="335b6-102">Distribuire lo strumento SEFAUtil in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="335b6-102">Deploy the SEFAUtil tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="335b6-103">_**Argomento Ultima modifica:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="335b6-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="335b6-104">Per distribuire e gestire il ritiro delle chiamate di gruppo, è necessario usare lo strumento SEFAUtil Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="335b6-104">To deploy and manage Group Call Pickup, you need to use the SEFAUtil resource kit tool.</span></span> <span data-ttu-id="335b6-105">Lo strumento fa parte degli strumenti di Lync Server 2013 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="335b6-105">The tool is part of the Lync Server 2013 resource kit tools.</span></span> <span data-ttu-id="335b6-106">Prima di poter installare SEFAUtil, è necessario disporre di un pool di applicazioni attendibili nella topologia, specificare SEFAUtil come applicazione attendibile e abilitare la topologia.</span><span class="sxs-lookup"><span data-stu-id="335b6-106">Before you can install SEFAUtil, you must have a trusted application pool in your topology, specify SEFAUtil as a trusted application, and enable the topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="335b6-107">Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK deve essere installato in qualsiasi computer in cui si prevede di eseguire lo strumento SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="335b6-107">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span>



</div>

<span data-ttu-id="335b6-108">È possibile eseguire SEFAUtil in qualsiasi pool Front-end della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="335b6-108">You can run the SEFAUtil in any Front End pool in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="335b6-109">Per altre informazioni sull'uso di SEFAUtil, vedere l'articolo del Blog di TechNet "come ottenere SEFAutil in corso?"</span><span class="sxs-lookup"><span data-stu-id="335b6-109">For more details about running SEFAUtil, see the Technet blog article, "How to get SEFAutil running?"</span></span> <span data-ttu-id="335b6-110">at <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>.</span><span class="sxs-lookup"><span data-stu-id="335b6-110">at <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>.</span></span>



</div>

<div>

## <a name="to-deploy-sefautil"></a><span data-ttu-id="335b6-111">Per distribuire SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="335b6-111">To deploy SEFAUtil</span></span>

1.  <span data-ttu-id="335b6-112">Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di [configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="335b6-112">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="335b6-113">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="335b6-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="335b6-114">Lo strumento SEFAUtil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibile.</span><span class="sxs-lookup"><span data-stu-id="335b6-114">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="335b6-115">Se necessario, definire un pool di applicazioni attendibili per il pool Front-end in cui si prevede di eseguire SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="335b6-115">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="335b6-116">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="335b6-116">At the command line, run:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  <span data-ttu-id="335b6-117">Definire lo strumento SEFAUtil come applicazione attendibile.</span><span class="sxs-lookup"><span data-stu-id="335b6-117">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="335b6-118">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="335b6-118">At the command line, run:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="335b6-119">Se necessario, è possibile usare una porta diversa.</span><span class="sxs-lookup"><span data-stu-id="335b6-119">You can use a different port if needed.</span></span>

    
    </div>

5.  <span data-ttu-id="335b6-120">Abilitare la topologia con le modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="335b6-120">Enable the topology with your changes.</span></span> <span data-ttu-id="335b6-121">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="335b6-121">At the command line, run:</span></span>
    
        Enable-CsTopology

6.  <span data-ttu-id="335b6-122">Installare gli strumenti del Resource Kit di Lync Server 2013 in un server front-end che si trova nel pool di applicazioni attendibile creato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="335b6-122">Install the Lync Server 2013 resource kit tools on a Front End Server that is in the trusted application pool that you created in step 3.</span></span>

7.  <span data-ttu-id="335b6-123">Verificare che lo strumento SEFAUtil sia in uso correttamente, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="335b6-123">Verify that the SEFAUtil tool is running correctly, as follows:</span></span>
    
    1.  <span data-ttu-id="335b6-124">Eseguire lo strumento dal prompt dei comandi di Windows con privilegi di amministratore per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="335b6-124">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="335b6-125">Lo strumento si trova nella cartella \Programmi\microsoft Lync Server 2013 \ reskit.</span><span class="sxs-lookup"><span data-stu-id="335b6-125">The tool is located at \Program Files\Microsoft Lync Server 2013\Reskit.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="335b6-126">Visualizzare le impostazioni di inoltro di chiamata di un utente.</span><span class="sxs-lookup"><span data-stu-id="335b6-126">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="335b6-127">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="335b6-127">At the command line, run:</span></span>
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        <span data-ttu-id="335b6-128">Verranno visualizzate le impostazioni di inoltro di chiamata per l'utente.</span><span class="sxs-lookup"><span data-stu-id="335b6-128">The call forwarding settings for the user will be displayed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

