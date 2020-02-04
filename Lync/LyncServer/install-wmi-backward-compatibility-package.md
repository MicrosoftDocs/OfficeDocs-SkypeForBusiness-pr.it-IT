---
title: Installare il pacchetto di compatibilità con le versioni precedenti di WMI
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c3b8d474ff451a488124ebfbae0ff0872a6cca1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a><span data-ttu-id="6e29f-102">Installare il pacchetto di compatibilità con le versioni precedenti di WMI</span><span class="sxs-lookup"><span data-stu-id="6e29f-102">Install WMI Backward Compatibility package</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e29f-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="6e29f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="6e29f-104">Se si tenta di eseguire l'Unione guidata generatore di topologie senza installare il pacchetto di compatibilità con le versioni precedenti di WMI, viene visualizzato l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="6e29f-104">If you attempt to run the Topology Builder Merge wizard without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="6e29f-105">![Messaggio di errore WMI](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "Messaggio di errore WMI")</span><span class="sxs-lookup"><span data-stu-id="6e29f-105">![WMI error message](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI error message")</span></span>

<span data-ttu-id="6e29f-106">Se si tenta di eseguire il cmdlet **Merge-CsLegacyTopology** senza installare il pacchetto di compatibilità con le versioni precedenti di WMI, verrà visualizzato il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="6e29f-106">If you attempt to run the **Merge-CsLegacytopology** cmdlet without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="6e29f-107">![Errore del provider WMI in Windows PowerShell](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Errore del provider WMI in Windows PowerShell")</span><span class="sxs-lookup"><span data-stu-id="6e29f-107">![Windows PowerShell WMI Provider Error](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI Provider Error")</span></span>

<span data-ttu-id="6e29f-108">Per installare il pacchetto di compatibilità con le versioni precedenti di WMI</span><span class="sxs-lookup"><span data-stu-id="6e29f-108">To install the WMI Backward Compatibility Package</span></span>

1.  <span data-ttu-id="6e29f-109">Dal supporto di installazione passare \\a Setup\\amd64\\Setup\\OCSWMIBC. MSI.</span><span class="sxs-lookup"><span data-stu-id="6e29f-109">From your installation media, navigate to \\SETUP\\AMD64\\SETUP\\OCSWMIBC.MSI.</span></span>

2.  <span data-ttu-id="6e29f-110">Installare OCSWMIBC. MSI.</span><span class="sxs-lookup"><span data-stu-id="6e29f-110">Install OCSWMIBC.MSI.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6e29f-111">OCSWMIBC. msi deve essere installato nel computer in cui viene eseguita la creazione guidata generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="6e29f-111">OCSWMIBC.msi must be installed on the computer where the Topology Builder Merge wizard is run.</span></span> <span data-ttu-id="6e29f-112">Tuttavia, è consigliabile installare OCSWMIBC. msi in tutti i server front-end della topologia.</span><span class="sxs-lookup"><span data-stu-id="6e29f-112">However, we recommend installing OCSWMIBC.msi on all Front End servers in your topology.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6e29f-113">OCSWMIBC. msi può essere installato in qualsiasi computer del dominio in cui sono installati i componenti principali di Lync Server 2013 e Lync Server 2013 Management Shell e ha accesso alla topologia di Office Communications Server 2007 R2 (provider WMI per il dominio Active Directory Services (AD DS) e SQL Server).</span><span class="sxs-lookup"><span data-stu-id="6e29f-113">OCSWMIBC.msi can be installed on any computer in the domain that has the Lync Server 2013 Core Components and the Lync Server 2013 Management Shell installed, and has access to the Office Communications Server 2007 R2 topology (WMI provider to Active Directory Domain Services (AD DS) and SQL Server).</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

