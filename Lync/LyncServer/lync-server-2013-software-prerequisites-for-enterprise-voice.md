---
title: 'Lync Server 2013: prerequisiti software per VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4b0b2e2708abbf3b92223474ec0804c1d11ac8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="1800d-102">Prerequisiti software per VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1800d-102">Software prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1800d-103">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="1800d-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="1800d-104">Verificare che l'infrastruttura in cui si intende distribuire VoIP aziendale soddisfi i prerequisiti software seguenti:</span><span class="sxs-lookup"><span data-stu-id="1800d-104">Verify that the infrastructure in which you intend to deploy Enterprise Voice meets the following software prerequisites:</span></span>

  - <span data-ttu-id="1800d-105">Lync Server 2013 Standard Edition o Enterprise Edition è installato e funzionante nella rete.</span><span class="sxs-lookup"><span data-stu-id="1800d-105">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="1800d-106">Tutti i server perimetrali sono distribuiti e operativi nella rete perimetrale, inclusi i server perimetrali che eseguono il servizio Access Edge, il servizio A/V Edge, il servizio Web Conferencing Edge e un proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="1800d-106">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers running Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="1800d-107">Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 o Microsoft Exchange Server 2013 è necessario per l'integrazione della messaggistica unificata di Exchange con Lync Server e per fornire notifiche ricche e informazioni sui registri di chiamata al Endpoint di Lync.</span><span class="sxs-lookup"><span data-stu-id="1800d-107">Either Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 or Microsoft Exchange Server 2013 is required for integrating Exchange Unified Messaging with Lync Server and to provide rich notifications and call log information to the Lync endpoints.</span></span>

  - <span data-ttu-id="1800d-108">Uno o più utenti sono stati creati e abilitati per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1800d-108">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="1800d-109">I client e i dispositivi Lync sono stati distribuiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="1800d-109">Lync clients and devices have been successfully deployed.</span></span>

  - <span data-ttu-id="1800d-110">Generatore di topologie è installato in un server della rete.</span><span class="sxs-lookup"><span data-stu-id="1800d-110">Topology Builder is installed on a server on your network.</span></span>

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a><span data-ttu-id="1800d-111">Passaggi successivi: verificare i prerequisiti della sicurezza e della configurazione</span><span class="sxs-lookup"><span data-stu-id="1800d-111">Next Steps: Verify Security and Configuration Prerequisites</span></span>

<span data-ttu-id="1800d-112">Dopo aver verificato i prerequisiti software per VoIP aziendale, è possibile utilizzare la documentazione per continuare la preparazione per la distribuzione di VoIP aziendale:</span><span class="sxs-lookup"><span data-stu-id="1800d-112">After verifying software prerequisites for Enterprise Voice, you can use the documentation to continue preparing for deploying Enterprise Voice:</span></span>

1.  <span data-ttu-id="1800d-113">Verificare la sicurezza, la configurazione utente e i componenti hardware di prerequisiti, come descritto in [prerequisiti di configurazione e sicurezza per VoIP aziendale in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="1800d-113">Verify security, user configuration, and hardware perquisites, as described in [Security and configuration prerequisites for Enterprise Voice in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span></span>

2.  <span data-ttu-id="1800d-114">Installare il Mediation Server, come descritto in [Install the files for Mediation Server in Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md), ma *solo* se si desidera distribuire un Mediation Server autonomo o un pool perché i Mediation Server vengono installati come parte del pool Front end o del processo di distribuzione del server Standard Edition durante la collocazione.</span><span class="sxs-lookup"><span data-stu-id="1800d-114">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but *only* if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

3.  <span data-ttu-id="1800d-115">Configurare le connessioni trunk per garantire la connettività PSTN per gli utenti, come descritto in [Configuring Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="1800d-115">Configure trunk connections to provide PSTN connectivity for users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

