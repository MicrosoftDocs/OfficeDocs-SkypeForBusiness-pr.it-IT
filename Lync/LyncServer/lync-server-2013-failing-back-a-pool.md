---
title: 'Lync Server 2013: failover di un pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2ad8ee15d0242a5512284e00064dfe9b49c41c5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522363"
---
# <a name="failing-back-a-pool-in-lync-server-2013"></a><span data-ttu-id="4ec1f-102">Failover di un pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ec1f-102">Failing back a pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ec1f-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4ec1f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4ec1f-104">Dopo aver riportato online il pool in cui si è verificata la situazione di emergenza (ovvero Pool1 in questo esempio), eseguire le operazioni seguenti per ripristinare uno stato di funzionamento regolare per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4ec1f-104">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="4ec1f-p101">Si noti che per il completamento del processo di failback sono richiesti vari minuti. A titolo di riferimento, sono previsti fino a 60 minuti per un pool di 20.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="4ec1f-p101">Note that the failback process takes several minute to complete.  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

1.  <span data-ttu-id="4ec1f-107">Eseguire il failback degli utenti ospitati in origine in Pool1 e di cui è stato eseguito il failover in Pool2 digitando il comando di cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="4ec1f-107">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="4ec1f-108">Non sono necessari altri passaggi.</span><span class="sxs-lookup"><span data-stu-id="4ec1f-108">No other steps are necessary.</span></span> <span data-ttu-id="4ec1f-109">Se si è verificato un errore nel server di gestione centrale, è possibile lasciarlo in Pool2.</span><span class="sxs-lookup"><span data-stu-id="4ec1f-109">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

