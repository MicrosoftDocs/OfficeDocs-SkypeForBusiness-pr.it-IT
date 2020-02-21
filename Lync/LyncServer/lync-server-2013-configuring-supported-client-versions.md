---
title: 'Lync Server 2013: configurazione delle versioni client supportate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34d74de1ae5e25c372e51783d8321ebc8699eaef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a><span data-ttu-id="78264-102">Configurazione delle versioni client supportate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78264-102">Configuring supported client versions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78264-103">_**Ultimo argomento modificato:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="78264-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="78264-104">In Lync Server 2013, è possibile configurare i criteri versione client per specificare le versioni dei client supportati nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="78264-104">In Lync Server 2013, you can set up client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="78264-105">È inoltre possibile utilizzare la configurazione della versione client globale per specificare un'azione predefinita per i client che non dispongono già di criteri di versione definiti e che pertanto non sono esplicitamente supportati o esclusi.</span><span class="sxs-lookup"><span data-stu-id="78264-105">Additionally, you can use the global client version configuration to specify a default action for clients that do not already have a version policy defined and, therefore, are not explicitly supported or restricted.</span></span>

<span data-ttu-id="78264-p102">È inoltre possibile utilizzare i criteri di versione client per gestire gli aggiornamenti client. Quando si impostano i criteri di versione client e si utilizzano le opzioni **Consenti e aggiorna** e **Blocca e aggiorna**, i client riceveranno il software aggiornato da Windows Server Update Service, se si utilizza tale servizio, o da Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="78264-p102">You can also use client version policies to manage client updates. When you set a client version policy and use the options **Allow and upgrade** and **Block and upgrade**, clients will receive updated software from the Windows Server Update Service (if you are using this service) or from Microsoft Update.</span></span>

<div>

## <a name="client-version-policy-settings"></a><span data-ttu-id="78264-108">Impostazioni dei criteri di versione client</span><span class="sxs-lookup"><span data-stu-id="78264-108">Client Version Policy Settings</span></span>

<span data-ttu-id="78264-109">I criteri di versione client predefiniti richiedono che tutti i client eseguano Lync.</span><span class="sxs-lookup"><span data-stu-id="78264-109">The default client version policy requires that all clients run Lync.</span></span> <span data-ttu-id="78264-110">Se i client nell'ambiente eseguono versioni precedenti di Communicator, potrebbe essere necessario riconfigurare le regole di versione client per impedire che i client e i dispositivi vengano bloccati o aggiornati in modo imprevisto durante la connessione a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="78264-110">If clients in your environment are running earlier versions of Communicator, you may need to reconfigure the Client Version rules to prevent clients and devices from being unexpectedly blocked or updated when connecting to Lync Server 2013.</span></span> <span data-ttu-id="78264-111">È possibile modificare la regola predefinita oppure aggiungere una regola più in alto nell'elenco Criteri versione client per ignorare la regola predefinita.</span><span class="sxs-lookup"><span data-stu-id="78264-111">You can modify the default rule, or you can add a rule higher in the Client Version Policy list to override the default rule.</span></span> <span data-ttu-id="78264-112">Inoltre, con il rilascio di aggiornamenti cumulativi (UC), è necessario configurare i criteri di versione client per richiedere gli aggiornamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="78264-112">Additionally, as Cumulative Updates (CUs) are released, you should configure the Client Version Policy to require the latest updates.</span></span> <span data-ttu-id="78264-113">Per ulteriori informazioni, vedere [impostazione delle applicazioni client che è possibile utilizzare per accedere a Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="78264-113">For details, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

