---
title: 'Lync Server 2013: Revisione del rapporto sui certificati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a584f331deaf702305367042c6c40679ffb7099f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a><span data-ttu-id="546e2-102">Revisione del rapporto sui certificati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="546e2-102">Reviewing the Certificates Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="546e2-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="546e2-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="546e2-104">Il rapporto certificati contiene tutti i certificati necessari nella distribuzione di Lync Server 2013 consigliata.</span><span class="sxs-lookup"><span data-stu-id="546e2-104">The Certificates Report contains all certificates that are required in the recommended Lync Server 2013 deployment.</span></span> <span data-ttu-id="546e2-105">Lo strumento di pianificazione rappresenta i nomi soggetto e i nomi alternativi del soggetto immessi.</span><span class="sxs-lookup"><span data-stu-id="546e2-105">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="546e2-106">Il testo predefinito che viene lasciato inedito potrebbe rappresentare una possibile sfida per il team responsabile della richiesta e dell'emissione dei certificati.</span><span class="sxs-lookup"><span data-stu-id="546e2-106">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="546e2-107">Nelle informazioni sui certificati sono inoltre incluse informazioni sull'origine da cui in genere viene emesso il certificato.</span><span class="sxs-lookup"><span data-stu-id="546e2-107">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="546e2-108">Se l'infrastruttura non dispone di un'infrastruttura a chiave pubblica (PKI), tutti i certificati possono essere richiesti tramite un provider di certificati pubblico.</span><span class="sxs-lookup"><span data-stu-id="546e2-108">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="546e2-109">I campi relativi agli utilizzi chiave avanzati e alla destinazione del rapporto sono molto utili per comprendere lo scopo e il percorso di ogni certificato.</span><span class="sxs-lookup"><span data-stu-id="546e2-109">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

<span data-ttu-id="546e2-110">![Rapporto di amministrazione dei certificati](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Rapporto di amministrazione dei certificati")</span><span class="sxs-lookup"><span data-stu-id="546e2-110">![Certificates Admin Report](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Certificates Admin Report")</span></span>

<span data-ttu-id="546e2-111">Esaminare attentamente e assicurarsi di comprendere l'utilizzo e lo scopo di ogni certificato nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="546e2-111">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="546e2-112">Se si verifica un problema relativo a un certificato, determinare il server o il servizio a cui si sta parlando.</span><span class="sxs-lookup"><span data-stu-id="546e2-112">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="546e2-113">I certificati in Lync Server 2013 vengono utilizzati per due scopi principali:</span><span class="sxs-lookup"><span data-stu-id="546e2-113">Certificates in Lync Server 2013 are used for two primary purposes:</span></span>

  - <span data-ttu-id="546e2-114">Mutual Transport Layer Security (MTLS) – i computer coinvolti nella comunicazione presentano ciascuno un certificato che dimostra la propria identità a un altro computer.</span><span class="sxs-lookup"><span data-stu-id="546e2-114">Mutual Transport Layer Security (MTLS) – The computers involved in the communication each present a certificate that proves their identity to another computer.</span></span> <span data-ttu-id="546e2-115">Questa operazione è nota come autenticazione del server.</span><span class="sxs-lookup"><span data-stu-id="546e2-115">This is known as server authentication.</span></span> <span data-ttu-id="546e2-116">La comunicazione non può iniziare finché ogni computer non considera attendibile l'identità dell'altro computer.</span><span class="sxs-lookup"><span data-stu-id="546e2-116">Communication cannot begin until each computer trusts the other computer’s identity.</span></span>

  - <span data-ttu-id="546e2-117">Crittografia: la crittografia (Secure Sockets Layer, o SSL e Transport Layer Security, o TLS) è uno strumento fondamentale per la protezione delle comunicazioni, per assicurare la privacy e per creare un sistema di comunicazioni e collaborazione attendibile.</span><span class="sxs-lookup"><span data-stu-id="546e2-117">Encryption – Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="546e2-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="546e2-118">See Also</span></span>


[<span data-ttu-id="546e2-119">Revisione dei rapporti dell'amministratore in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="546e2-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

