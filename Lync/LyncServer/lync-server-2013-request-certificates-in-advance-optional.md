---
title: 'Lync Server 2013: Richiedere certificati in anticipo (facoltativo)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ee4598f35bb607a9262bfeb7931e2c88e27920c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a><span data-ttu-id="c08b1-102">Richiedere certificati in anticipo (facoltativo) per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c08b1-102">Request certificates in advance (optional) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c08b1-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c08b1-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c08b1-104">I certificati sono necessari per tutti i server interni in cui è in uso Lync Server 2013, tra cui ogni server front end Enterprise Edition, server standard, Director, Edge Server e Mediation Server autonomo.</span><span class="sxs-lookup"><span data-stu-id="c08b1-104">Certificates are required for all internal servers that are running Lync Server 2013, including each Enterprise Edition Front End Server, Standard Edition server, Director, Edge Server and stand-alone Mediation Server.</span></span> <span data-ttu-id="c08b1-105">Anche se è consigliata un'autorità di certificazione (CA) interna per i server interni, è anche possibile usare una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="c08b1-105">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="c08b1-106">Per informazioni dettagliate sui requisiti dei certificati e sull'uso di una CA pubblica, vedere [requisiti di certificato per i server interni in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="c08b1-106">For details about certificate requirements and about the use of a public CA, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="c08b1-107">La configurazione di Lync Server 2013 include la creazione guidata certificato, che facilita le attività di richiesta, assegnazione e installazione dei certificati durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c08b1-107">Lync Server 2013 setup includes the Certificate Wizard, which facilitates the tasks of requesting, assigning, and installing certificates during deployment.</span></span> <span data-ttu-id="c08b1-108">Se si vogliono richiedere certificati prima di installare i server, ad esempio per risparmiare tempo durante la distribuzione effettiva dei server, è possibile usare un computer in cui sono installati gli strumenti di amministrazione di Lync Server 2013 o tramite una richiesta di certificato procedura definita nell'organizzazione, purché si assicuri che i certificati siano esportabili e contengano tutti i nomi di oggetto alternativi necessari.</span><span class="sxs-lookup"><span data-stu-id="c08b1-108">If you want to request certificates prior to installing servers (for instance, to save time during actual deployment of servers), you can do so by using a computer on which the Lync Server 2013 administrative tools are installed or by using a certificate request procedure defined in your organization, as long as you make sure that the certificates are exportable and contain all the required subject alternative names.</span></span> <span data-ttu-id="c08b1-109">La richiesta di certificati in anticipo è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="c08b1-109">Requesting certificates in advance is optional.</span></span> <span data-ttu-id="c08b1-110">Se non vengono richieste in anticipo, è necessario richiederle come parte della configurazione di ogni server che richiede un certificato.</span><span class="sxs-lookup"><span data-stu-id="c08b1-110">If you do not request them in advance, you must request them as part of the setup of each server that requires a certificate.</span></span>

<span data-ttu-id="c08b1-111">Questa documentazione di distribuzione fornisce le procedure per l'uso della creazione guidata certificati per richiedere certificati come parte del processo di configurazione, come descritto in configurare i certificati [per i server in Lync server 2013](lync-server-2013-configure-certificates-for-servers.md), [configurare i certificati per il Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md)e [installare i file per Mediation Server nelle sezioni di Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) della documentazione di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c08b1-111">This Deployment documentation provides procedures for using the Certificate Wizard to request certificates as part of the setup process, as described in the [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md), and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) sections of this Deployment documentation.</span></span> <span data-ttu-id="c08b1-112">Se si richiedono preventivamente i certificati, è necessario modificare le procedure di distribuzione dei certificati in queste sezioni, in base alle esigenze di importazione e assegnazione dei certificati invece di richiederle al momento della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c08b1-112">If you request certificates in advance, you must modify the certificate deployment procedures in those sections as appropriate to importing and assigning the certificates instead of requesting them at the time of deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c08b1-113">Lync Server 2013 include il supporto per i certificati SHA-256 per le connessioni da client che utilizzano i sistemi&nbsp;operativi Windows Vista,&nbsp;Windows&nbsp;Server 2008, Windows Server 2008 R2 e Windows 7 e Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="c08b1-113">Lync Server 2013 includes support for SHA-256 certificates for connections from clients running the Windows Vista, Windows Server&nbsp;2008, Windows Server&nbsp;2008&nbsp;R2, and Windows 7 operating systems, and Lync Phone Edition.</span></span> <span data-ttu-id="c08b1-114">Per supportare l'accesso esterno tramite SHA-256, il certificato esterno viene emesso da una CA pubblica tramite SHA-256.</span><span class="sxs-lookup"><span data-stu-id="c08b1-114">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

