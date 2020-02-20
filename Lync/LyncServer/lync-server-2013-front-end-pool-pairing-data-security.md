---
title: "Lync Server 2013: protezione dei dati per l'abbinamento del pool Front End"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26759c982723fd656ac3456aad630bc695a7343e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a><span data-ttu-id="72d2f-102">Sicurezza dei dati per l'abbinamento del pool Front end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72d2f-102">Front End pool pairing data security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72d2f-103">_**Ultimo argomento modificato:** 2014-10-07_</span><span class="sxs-lookup"><span data-stu-id="72d2f-103">_**Topic Last Modified:** 2014-10-07_</span></span>

<span data-ttu-id="72d2f-104">Il servizio di backup è un meccanismo di replica dei dati introdotto in Lync Server 2013 che trasferisce i dati degli utenti e il contenuto delle conferenze tra due pool Front End abbinati in modo continuo tra due centri dati per scopi di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="72d2f-104">The Backup Service is a data replication mechanism introduced in Lync Server 2013 that transfers user data and conference content between two paired Front End pools continuously across two data centers for disaster recovery purposes.</span></span> <span data-ttu-id="72d2f-105">I dati utente contengono gli URI SIP nonché gli elenchi contatti e le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="72d2f-105">The user data contains user SIP URIs as well as contact lists and settings.</span></span> <span data-ttu-id="72d2f-106">Il contenuto delle conferenze include i caricamenti di Microsoft PowerPoint 2010, nonché le lavagne utilizzate nelle conferenze.</span><span class="sxs-lookup"><span data-stu-id="72d2f-106">Conference content includes Microsoft PowerPoint 2010 uploads, as well as whiteboards used in conferences.</span></span> <span data-ttu-id="72d2f-107">Dal pool di origine, i dati utente e i contenuti delle conferenze vengono esportati dall'archiviazione locale, compressi e trasferiti nel pool di destinazione, dove vengono decompressi e importati nell'archiviazione locale.</span><span class="sxs-lookup"><span data-stu-id="72d2f-107">From the source pool, user data and conference content are exported from the local storage, zipped, transferred to the target Pool, where it is unzipped and imported to local storage.</span></span> <span data-ttu-id="72d2f-108">Il Servizio di backup presume che i collegamenti di comunicazione tra i due data center si trovino all'interno di una rete aziendale protetta da Internet.</span><span class="sxs-lookup"><span data-stu-id="72d2f-108">The Backup Service assumes that the communications link between the two data centers is within the corporate network that is protected from the Internet.</span></span> <span data-ttu-id="72d2f-109">I dati trasferiti tra i due data center non vengono crittografati, né è previsto l'incapsulamento nativo all'interno di un protocollo di sicurezza, quale HTTPS.</span><span class="sxs-lookup"><span data-stu-id="72d2f-109">It does not encrypt the transferred data between the two data centers, nor is it natively encapsulated within a secure protocol, such as HTTPS.</span></span> <span data-ttu-id="72d2f-110">Pertanto resta possibile un attacco man-in-the-middle compiuto da personale interno alla rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="72d2f-110">Therefore, man-in-the-middle attack from internal personnel within the corporate network is possible.</span></span>

<div>

## <a name="evaluating-security-risks"></a><span data-ttu-id="72d2f-111">Valutazione dei rischi per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="72d2f-111">Evaluating Security Risks</span></span>

<span data-ttu-id="72d2f-112">Qualsiasi organizzazione che distribuisce Lync Server 2013 su più data center e utilizza la funzionalità di ripristino di emergenza deve garantire che il traffico tra i Data Center sia protetto dalla propria Intranet aziendale.</span><span class="sxs-lookup"><span data-stu-id="72d2f-112">Any enterprise which deploys Lync Server 2013 across multiple data centers and uses the disaster recovery feature must ensure that cross-data center traffic is protected by their corporate Intranet.</span></span> <span data-ttu-id="72d2f-113">Le aziende che intendono cautelarsi dal rischio di un attacco interno, devono proteggere i collegamenti di comunicazione tra i data center.</span><span class="sxs-lookup"><span data-stu-id="72d2f-113">Enterprises which care about internal attack protection must secure the communication links among the data centers.</span></span>

<span data-ttu-id="72d2f-p103">In genere, si suppone che i data center di un'azienda siano protetti nella Intranet aziendale. Molti altri tipi di dati aziendali riservati vengono trasferiti tra questi data center. L'infrastruttura IT dell'azienda è esposta a seri pericoli se i collegamenti tra data center non sono protetti.</span><span class="sxs-lookup"><span data-stu-id="72d2f-p103">The assumption that data centers of an enterprise are protected behind the corporate Intranet is standard. There are many other types of corporate sensitive data transferred among these data centers. The enterprise’s IT infrastructure is at dire risk if these cross-data center links are not protected.</span></span>

<span data-ttu-id="72d2f-p104">Sebbene in un'azienda esista il pericolo di attacchi man-in-the-middle, è relativamente contenuto se paragonato al rischio di esporre il traffico in Internet. In particolare, i dati utente esposti dal Servizio di backup (ad esempio gli URI SIP) sono generalmente disponibili a tutti gli utenti dell'azienda con altri mezzi, quali la Rubrica globale di Exchange o altri software di directory. Quando viene utilizzato il Servizio backup per copiare dati tra due pool abbinati, è pertanto necessario concentrarsi sulla protezione della WAN tra i due data center.</span><span class="sxs-lookup"><span data-stu-id="72d2f-p104">While the risk of man-in-the-middle attacks within the corporate network exists, it is relatively contained as compared to exposing the traffic to the Internet. Specifically, the user data exposed by Backup Service (such as SIP URIs) are generally available to all employees within the company via other means such as the Global Address Book by Exchange or other directory software. Hence, the focus should be on securing the WAN between the two data centers when the Backup Service is used to copy data between the two paired Pools.</span></span>

</div>

<div>

## <a name="mitigating-security-risks"></a><span data-ttu-id="72d2f-120">Contenere i rischi per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="72d2f-120">Mitigating Security Risks</span></span>

<span data-ttu-id="72d2f-121">Esistono diversi modi per migliorare la protezione della sicurezza per il traffico dei servizi di backup, che varia da limitare l'accesso ai Data Center per garantire il trasporto WAN tra i due data center.</span><span class="sxs-lookup"><span data-stu-id="72d2f-121">There are many ways to enhance security protection for the Backup Service traffic, ranging from restricting access to the data centers to securing the WAN transport between the two data centers.</span></span> <span data-ttu-id="72d2f-122">Nella maggior parte dei casi, le aziende che distribuiscono Lync Server 2013 potrebbe già disporre dell'infrastruttura di sicurezza necessaria.</span><span class="sxs-lookup"><span data-stu-id="72d2f-122">In most cases, enterprises deploying Lync Server 2013 might already have the required security infrastructure in place.</span></span> <span data-ttu-id="72d2f-123">Per le aziende alla ricerca di linee guida, Microsoft fornisce una soluzione come esempio di come creare un'infrastruttura IT sicura.</span><span class="sxs-lookup"><span data-stu-id="72d2f-123">For enterprises looking for guidance, Microsoft provides solution as an example of how to build a secure IT infrastructure.</span></span> <span data-ttu-id="72d2f-124">Tuttavia, ciò non implica che sia l'unica soluzione, né implica che sia la soluzione preferita per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72d2f-124">However, this does not imply that it is the only solution, nor does it imply that it is the preferred solution for Lync Server.</span></span> <span data-ttu-id="72d2f-125">Si consiglia ai clienti aziendali di scegliere la soluzione adatta alle proprie esigenze specifiche, in base all'infrastruttura e ai requisiti di sicurezza IT. Nell'esempio di soluzione Microsoft vengono impiegati IPSec e criteri di gruppo per l'isolamento del server e del dominio.</span><span class="sxs-lookup"><span data-stu-id="72d2f-125">We recommend that enterprise customers choose the solution suits their specific needs, based on their IT security infrastructure and requirements.The example Microsoft solution employs IPSec and Group Policy for Server and Domain Isolation.</span></span> <span data-ttu-id="72d2f-126">Per informazioni dettagliate, [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544)vedere.</span><span class="sxs-lookup"><span data-stu-id="72d2f-126">For details, see [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544).</span></span> <span data-ttu-id="72d2f-127">Per domande e commenti, contattare secwish@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="72d2f-127">For questions and comments, contact secwish@microsoft.com.</span></span>

<span data-ttu-id="72d2f-128">Un'altra possibile soluzione consiste nell'utilizzare IPSec solo per garantire la protezione dei dati inviati dal servizio di backup stesso.</span><span class="sxs-lookup"><span data-stu-id="72d2f-128">Another possible solution is to use IPSec just to help secure the data sent by the Backup Service itself.</span></span> <span data-ttu-id="72d2f-129">Se si sceglie questo metodo, è necessario configurare le regole IPSec per il protocollo SMB per i server seguenti, in cui il pool A e il pool B sono due pool Front End abbinati.</span><span class="sxs-lookup"><span data-stu-id="72d2f-129">If you choose this method, you should configure the IPSec rules for the SMB protocol for the following servers, where Pool A and Pool B are two paired Front End pools.</span></span>

  - <span data-ttu-id="72d2f-130">Il servizio SMB (TCP/445) di ogni front end server del pool A nell'archivio file utilizzato dal pool B.</span><span class="sxs-lookup"><span data-stu-id="72d2f-130">The SMB Service (TCP/445) from each Front End Server in Pool A to the File Store used by Pool B.</span></span>

  - <span data-ttu-id="72d2f-131">Il servizio SMB (TCP/445) da ogni Front End Server nel pool B all'archivio file utilizzato dal pool A.</span><span class="sxs-lookup"><span data-stu-id="72d2f-131">The SMB Service (TCP/445) from each Front End Server in Pool B to the File Store used by Pool A.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="72d2f-132">IPsec non è destinato a essere sostituito per la sicurezza a livello di applicazione, ad esempio SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="72d2f-132">IPsec is not intended as a replacement for application-level security, such as SSL/TLS.</span></span> <span data-ttu-id="72d2f-133">Un vantaggio dell'utilizzo di IPsec è che può garantire la sicurezza del traffico di rete per le applicazioni esistenti senza dover cambiare.</span><span class="sxs-lookup"><span data-stu-id="72d2f-133">One advantage of using IPsec is that it can provide network traffic security for existing applications without having to change them.</span></span> <span data-ttu-id="72d2f-134">Le aziende che desiderano garantire solo il trasporto tra i due data center devono consultare i rispettivi fornitori di hardware di rete in merito alle modalità di configurazione delle connessioni WAN sicure tramite l'equipaggiamento del fornitore.</span><span class="sxs-lookup"><span data-stu-id="72d2f-134">Enterprises that want to just secure the transport between the two data centers should consult their respective networking hardware vendors about ways to set up secure WAN connections by using the vendor’s equipment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

