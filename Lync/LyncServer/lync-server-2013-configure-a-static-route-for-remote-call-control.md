---
title: 'Lync Server 2013: configurare una route statica per il controllo delle chiamate remote'
description: 'Lync Server 2013: configurare una route statica per il controllo delle chiamate remote.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ecf6478d4fb7ab4f04f8a452d4837b327ba254a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551692"
---
# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="6feaf-103">Configurare una route statica per il controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6feaf-103">Configure a static route for remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6feaf-104">_**Ultimo argomento modificato:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="6feaf-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="6feaf-105">Il controllo delle chiamate remote richiede che ogni pool di Lync Server sia configurato con un percorso da tale pool al gateway SIP/CSTA che si connette al sistema PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="6feaf-105">Remote call control requires that every Lync Server pool is configured with a path from that pool to the SIP/CSTA gateway that connects to the private branch exchange (PBX).</span></span> <span data-ttu-id="6feaf-106">Questo percorso richiede che ogni pool disponga di una route statica per ogni gateway che verrà utilizzato dal pool come proxy per i messaggi di controllo delle chiamate SIP associati alle chiamate al PBX.</span><span class="sxs-lookup"><span data-stu-id="6feaf-106">This path requires that each pool has one static route for each gateway to which the pool will proxy SIP call control messages associated with calls to the PBX.</span></span> <span data-ttu-id="6feaf-107">Se si configura una route statica globale per il controllo delle chiamate remote, ogni pool che non è configurato con una route statica a livello del pool utilizzerà la route statica globale.</span><span class="sxs-lookup"><span data-stu-id="6feaf-107">If you configure a global static route for remote call control, each pool that is not configured with a static route at the pool level will use the global static route.</span></span>

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a><span data-ttu-id="6feaf-108">Per configurare una route statica per il controllo delle chiamate remote</span><span class="sxs-lookup"><span data-stu-id="6feaf-108">To configure a static route for remote call control</span></span>

1.  <span data-ttu-id="6feaf-109">Accedere a un computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o di un ruolo di controllo di accesso basato sui ruoli a cui è stato assegnato il cmdlet **New-CsStaticRoute** .</span><span class="sxs-lookup"><span data-stu-id="6feaf-109">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsStaticRoute** cmdlet.</span></span>

2.  <span data-ttu-id="6feaf-110">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="6feaf-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6feaf-111">Per creare una route statica e inserirla nella variabile $TLSRoute o $TCPRoute, effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6feaf-111">To create a static route and put it in the variable $TLSRoute or $TCPRoute, do one of the following:</span></span>
    
    <div class="">
    

    > [!TIP]  
    > <span data-ttu-id="6feaf-p102">Per includere tutti i domini figlio di un dominio, è possibile specificare un valore con caratteri jolly nel parametro MatchUri, ad esempio <STRONG>\*.contoso.net</STRONG>. Tale valore consente di includere qualsiasi dominio che termina con il suffisso <STRONG>contoso.net</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="6feaf-p102">To match child domains of a domain, you can specify a wildcard value in the MatchUri parameter. For example, <STRONG>\*.contoso.net</STRONG>. That value matches any domain that ends with the suffix <STRONG>contoso.net</STRONG>.</span></span>

    
    </div>
    
      - <span data-ttu-id="6feaf-115">Per una connessione TLS (Transport Layer Security), al prompt dei comandi digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="6feaf-115">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        <span data-ttu-id="6feaf-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6feaf-116">For example:</span></span>
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        <span data-ttu-id="6feaf-117">Se UseDefaultCertificate è impostato su False, è necessario specificare i parametri TLSCertIssuer e TLSCertSerialNumber.</span><span class="sxs-lookup"><span data-stu-id="6feaf-117">If UseDefaultCertificate is set to False, you must specify TLSCertIssuer and TLSCertSerialNumber parameters.</span></span> <span data-ttu-id="6feaf-118">Questi parametri indicano rispettivamente il nome dell'Autorità di certificazione che ha emesso il certificato utilizzato nella route statica e il numero di serie di tale certificato.</span><span class="sxs-lookup"><span data-stu-id="6feaf-118">These parameters indicate the name of the certification authority (CA) that issued the certificate used in the static route, and the serial number of that TLS certificate, respectively.</span></span> <span data-ttu-id="6feaf-119">Per informazioni dettagliate su questi parametri, vedere la Guida di Lync Server Management Shell digitando quanto segue al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="6feaf-119">For details about these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - <span data-ttu-id="6feaf-120">Per una connessione TCP (Transmission Control Protocol), digitare il comando seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="6feaf-120">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
        <div class="">
        

        > [!NOTE]  
        > <span data-ttu-id="6feaf-121">Se si specifica un nome di dominio completo (FQDN), è necessario configurare precedentemente un record DNS (Domain Name System) A.</span><span class="sxs-lookup"><span data-stu-id="6feaf-121">If you specify a fully qualified domain name (FQDN), you must configure a Domain Name System (DNS) A record first.</span></span>

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        <span data-ttu-id="6feaf-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6feaf-122">For example:</span></span>
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        <span data-ttu-id="6feaf-123">Di seguito sono riportati i valori predefiniti per parametri facoltativi per route statiche:</span><span class="sxs-lookup"><span data-stu-id="6feaf-123">The following are default values for optional parameters for static routes:</span></span>
        
          - <span data-ttu-id="6feaf-124">Enabled = True</span><span class="sxs-lookup"><span data-stu-id="6feaf-124">Enabled = True</span></span>
        
          - <span data-ttu-id="6feaf-125">MatchOnlyPhoneUri = False</span><span class="sxs-lookup"><span data-stu-id="6feaf-125">MatchOnlyPhoneUri = False</span></span>
        
          - <span data-ttu-id="6feaf-126">ReplaceHostInRequestUri = False</span><span class="sxs-lookup"><span data-stu-id="6feaf-126">ReplaceHostInRequestUri = False</span></span>
        
        <span data-ttu-id="6feaf-127">È consigliabile non modificare questi valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="6feaf-127">We strongly recommend that you do not change these default values.</span></span> <span data-ttu-id="6feaf-128">Tuttavia, se è necessario modificare uno qualsiasi di questi parametri, vedere la Guida di Lync Server Management Shell digitando quanto segue al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="6feaf-128">However, if you must change any of these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  <span data-ttu-id="6feaf-129">Per mantenere una route statica appena creata nell'archivio di gestione centrale, eseguire una delle operazioni seguenti, a seconda dei casi:</span><span class="sxs-lookup"><span data-stu-id="6feaf-129">To persist a newly created static route in the Central Management store, run one of the following, as appropriate:</span></span>
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6feaf-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6feaf-130">See Also</span></span>


[<span data-ttu-id="6feaf-131">Configurare una voce di applicazione attendibile per il controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6feaf-131">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[<span data-ttu-id="6feaf-132">Definire un indirizzo IP del gateway SIP/CSTA in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6feaf-132">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

