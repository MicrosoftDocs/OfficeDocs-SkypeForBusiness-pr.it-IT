---
title: 'Lync Server 2013: Revisione del report certificati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a83167576746d3f90d96658b0dd3d65815f5375
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a><span data-ttu-id="779c4-102">Revisione del report sui certificati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="779c4-102">Reviewing the Certificates Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="779c4-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="779c4-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="779c4-104">Il report certificati contiene tutti i certificati necessari nella distribuzione di Lync Server 2013 consigliata.</span><span class="sxs-lookup"><span data-stu-id="779c4-104">The Certificates Report contains all certificates that are required in the recommended Lync Server 2013 deployment.</span></span> <span data-ttu-id="779c4-105">Lo strumento di pianificazione rappresenta i nomi di oggetto e i nomi alternativi oggetto immessi.</span><span class="sxs-lookup"><span data-stu-id="779c4-105">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="779c4-106">Il testo predefinito lasciato inedito può rappresentare una potenziale sfida per il team responsabile per richiedere e rilasciare i certificati.</span><span class="sxs-lookup"><span data-stu-id="779c4-106">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="779c4-107">Le informazioni sui certificati contengono anche informazioni sulla posizione in cui il certificato può in genere essere emesso.</span><span class="sxs-lookup"><span data-stu-id="779c4-107">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="779c4-108">Se l'infrastruttura non ha un'infrastruttura a chiave pubblica (PKI) interna, tutti i certificati possono essere richiesti tramite un provider di certificati pubblici.</span><span class="sxs-lookup"><span data-stu-id="779c4-108">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="779c4-109">Gli utilizzi delle chiavi estese (EKU) e i campi assegna ai nel report sono molto utili per capire qual è lo scopo e la posizione per ogni certificato.</span><span class="sxs-lookup"><span data-stu-id="779c4-109">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

<span data-ttu-id="779c4-110">![](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Report") Amministrazione certificati certificati rapporto di amministrazione</span><span class="sxs-lookup"><span data-stu-id="779c4-110">![Certificates Admin Report](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Certificates Admin Report")</span></span>

<span data-ttu-id="779c4-111">Esaminare con attenzione e assicurarsi di comprendere l'uso e lo scopo di ogni certificato nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="779c4-111">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="779c4-112">In caso di domande su cosa fa un certificato, determinare il server o il servizio a cui si sta parlando.</span><span class="sxs-lookup"><span data-stu-id="779c4-112">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="779c4-113">I certificati in Lync Server 2013 vengono usati per due scopi principali:</span><span class="sxs-lookup"><span data-stu-id="779c4-113">Certificates in Lync Server 2013 are used for two primary purposes:</span></span>

  - <span data-ttu-id="779c4-114">MTLS (Mutual Transport Layer Security): i computer coinvolti nella comunicazione presentano ognuno un certificato che ne dimostra l'identità a un altro computer.</span><span class="sxs-lookup"><span data-stu-id="779c4-114">Mutual Transport Layer Security (MTLS) – The computers involved in the communication each present a certificate that proves their identity to another computer.</span></span> <span data-ttu-id="779c4-115">Questa operazione è nota come autenticazione server.</span><span class="sxs-lookup"><span data-stu-id="779c4-115">This is known as server authentication.</span></span> <span data-ttu-id="779c4-116">La comunicazione non può iniziare finché ogni computer non considera attendibile l'identità dell'altro computer.</span><span class="sxs-lookup"><span data-stu-id="779c4-116">Communication cannot begin until each computer trusts the other computer’s identity.</span></span>

  - <span data-ttu-id="779c4-117">Crittografia: la crittografia (Secure Sockets Layer o SSL e Transport Layer Security o TLS) è un mezzo essenziale per proteggere le comunicazioni, garantire la privacy e creare un sistema di comunicazione e collaborazione attendibile.</span><span class="sxs-lookup"><span data-stu-id="779c4-117">Encryption – Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="779c4-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="779c4-118">See Also</span></span>


[<span data-ttu-id="779c4-119">Esame dei rapporti amministratore in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="779c4-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

