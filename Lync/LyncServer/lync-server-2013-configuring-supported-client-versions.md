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
ms.openlocfilehash: 9a262cab2145013d83cdae573d98b5db17e0e890
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a><span data-ttu-id="d37c4-102">Configurazione di versioni client supportate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d37c4-102">Configuring supported client versions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d37c4-103">_**Argomento Ultima modifica:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="d37c4-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="d37c4-104">In Lync Server 2013 è possibile configurare i criteri di versione client per specificare le versioni dei client supportate nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="d37c4-104">In Lync Server 2013, you can set up client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="d37c4-105">Inoltre, puoi usare la configurazione della versione client globale per specificare un'azione predefinita per i client che non hanno già un criterio di versione definito e, pertanto, non sono esplicitamente supportati o limitati.</span><span class="sxs-lookup"><span data-stu-id="d37c4-105">Additionally, you can use the global client version configuration to specify a default action for clients that do not already have a version policy defined and, therefore, are not explicitly supported or restricted.</span></span>

<span data-ttu-id="d37c4-106">È anche possibile usare i criteri di versione client per gestire gli aggiornamenti del client.</span><span class="sxs-lookup"><span data-stu-id="d37c4-106">You can also use client version policies to manage client updates.</span></span> <span data-ttu-id="d37c4-107">Quando si impostano criteri di versione client e si usano le opzioni **Consenti e aggiorna** e **blocca e aggiorna**, i client riceveranno il software aggiornato dal servizio Windows Server Update (se si usa questo servizio) o da Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="d37c4-107">When you set a client version policy and use the options **Allow and upgrade** and **Block and upgrade**, clients will receive updated software from the Windows Server Update Service (if you are using this service) or from Microsoft Update.</span></span>

<div>

## <a name="client-version-policy-settings"></a><span data-ttu-id="d37c4-108">Impostazioni dei criteri di versione client</span><span class="sxs-lookup"><span data-stu-id="d37c4-108">Client Version Policy Settings</span></span>

<span data-ttu-id="d37c4-109">I criteri di versione client predefiniti richiedono che tutti i client eseguano Lync.</span><span class="sxs-lookup"><span data-stu-id="d37c4-109">The default client version policy requires that all clients run Lync.</span></span> <span data-ttu-id="d37c4-110">Se i client nell'ambiente sono in esecuzione versioni precedenti di Communicator, potrebbe essere necessario riconfigurare le regole della versione client per impedire che i client e i dispositivi vengano bloccati o aggiornati in modo imprevisto durante la connessione a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d37c4-110">If clients in your environment are running earlier versions of Communicator, you may need to reconfigure the Client Version rules to prevent clients and devices from being unexpectedly blocked or updated when connecting to Lync Server 2013.</span></span> <span data-ttu-id="d37c4-111">È possibile modificare la regola predefinita oppure aggiungere una regola più alta nell'elenco dei criteri di versione client per eseguire l'override della regola predefinita.</span><span class="sxs-lookup"><span data-stu-id="d37c4-111">You can modify the default rule, or you can add a rule higher in the Client Version Policy list to override the default rule.</span></span> <span data-ttu-id="d37c4-112">Inoltre, come vengono rilasciati gli aggiornamenti cumulativi (CUs), è necessario configurare i criteri di versione client per richiedere gli aggiornamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="d37c4-112">Additionally, as Cumulative Updates (CUs) are released, you should configure the Client Version Policy to require the latest updates.</span></span> <span data-ttu-id="d37c4-113">Per informazioni dettagliate, vedere [specificare le applicazioni client che è possibile usare per accedere a Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="d37c4-113">For details, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

