---
title: "Lync Server 2013: sicurezza dei dati per l'abbinamento dei pool Front End"
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
ms.openlocfilehash: efe51da622107183d3dbf2897a9e2a708acd78dd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a><span data-ttu-id="e4fe8-102">Sicurezza dei dati per l'abbinamento dei pool Front End in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4fe8-102">Front End pool pairing data security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4fe8-103">_**Argomento Ultima modifica:** 2014-10-07_</span><span class="sxs-lookup"><span data-stu-id="e4fe8-103">_**Topic Last Modified:** 2014-10-07_</span></span>

<span data-ttu-id="e4fe8-104">Il servizio di backup è un meccanismo di replica dei dati introdotto in Lync Server 2013 che trasferisce i dati degli utenti e il contenuto delle conferenze tra due pool di front end associati in due centri dati per scopi di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-104">The Backup Service is a data replication mechanism introduced in Lync Server 2013 that transfers user data and conference content between two paired Front End pools continuously across two data centers for disaster recovery purposes.</span></span> <span data-ttu-id="e4fe8-105">I dati degli utenti contengono URI SIP degli utenti, nonché elenchi di contatti e impostazioni.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-105">The user data contains user SIP URIs as well as contact lists and settings.</span></span> <span data-ttu-id="e4fe8-106">Il contenuto della conferenza include gli upload di Microsoft PowerPoint 2010 e le lavagne usate nelle conferenze.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-106">Conference content includes Microsoft PowerPoint 2010 uploads, as well as whiteboards used in conferences.</span></span> <span data-ttu-id="e4fe8-107">Dal pool di origine, i dati utente e il contenuto della conferenza vengono esportati dall'archivio locale, compressi, trasferiti nel pool di destinazione, dove vengono decompressi e importati nello spazio di archiviazione locale.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-107">From the source pool, user data and conference content are exported from the local storage, zipped, transferred to the target Pool, where it is unzipped and imported to local storage.</span></span> <span data-ttu-id="e4fe8-108">Il servizio di backup presuppone che il collegamento delle comunicazioni tra i due centri dati si trovi all'interno della rete aziendale protetta da Internet.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-108">The Backup Service assumes that the communications link between the two data centers is within the corporate network that is protected from the Internet.</span></span> <span data-ttu-id="e4fe8-109">Non crittografa i dati trasferiti tra i due centri dati, né è incapsulato nativamente in un protocollo sicuro, ad esempio HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-109">It does not encrypt the transferred data between the two data centers, nor is it natively encapsulated within a secure protocol, such as HTTPS.</span></span> <span data-ttu-id="e4fe8-110">Di conseguenza, è possibile l'attacco man-in-the-Middle da parte di personale interno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-110">Therefore, man-in-the-middle attack from internal personnel within the corporate network is possible.</span></span>

<div>

## <a name="evaluating-security-risks"></a><span data-ttu-id="e4fe8-111">Valutazione dei rischi per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="e4fe8-111">Evaluating Security Risks</span></span>

<span data-ttu-id="e4fe8-112">Qualsiasi organizzazione che distribuisce Lync Server 2013 in più centri dati e usa la funzionalità di ripristino di emergenza deve garantire che il traffico tra i dati sia protetto dalla propria Intranet aziendale.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-112">Any enterprise which deploys Lync Server 2013 across multiple data centers and uses the disaster recovery feature must ensure that cross-data center traffic is protected by their corporate Intranet.</span></span> <span data-ttu-id="e4fe8-113">Le aziende che preoccupano la protezione dagli attacchi interni devono garantire i collegamenti di comunicazione tra i centri dati.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-113">Enterprises which care about internal attack protection must secure the communication links among the data centers.</span></span>

<span data-ttu-id="e4fe8-114">Il presupposto che i Data Center di un'azienda siano protetti dietro l'Intranet aziendale è standard.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-114">The assumption that data centers of an enterprise are protected behind the corporate Intranet is standard.</span></span> <span data-ttu-id="e4fe8-115">Ci sono molti altri tipi di dati sensibili aziendali trasferiti tra questi Data Center.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-115">There are many other types of corporate sensitive data transferred among these data centers.</span></span> <span data-ttu-id="e4fe8-116">L'infrastruttura IT dell'organizzazione ha un rischio grave se questi collegamenti al centro dati incrociati non sono protetti.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-116">The enterprise’s IT infrastructure is at dire risk if these cross-data center links are not protected.</span></span>

<span data-ttu-id="e4fe8-117">Mentre il rischio di attacchi man-in-the-Middle all'interno della rete aziendale esiste, è relativamente contenuto rispetto a esporre il traffico a Internet.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-117">While the risk of man-in-the-middle attacks within the corporate network exists, it is relatively contained as compared to exposing the traffic to the Internet.</span></span> <span data-ttu-id="e4fe8-118">In particolare, i dati utente esposti dal servizio di backup, ad esempio URI SIP, sono in genere disponibili per tutti i dipendenti della società tramite altri mezzi, ad esempio la Rubrica globale di Exchange o un altro software di directory.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-118">Specifically, the user data exposed by Backup Service (such as SIP URIs) are generally available to all employees within the company via other means such as the Global Address Book by Exchange or other directory software.</span></span> <span data-ttu-id="e4fe8-119">Lo stato attivo deve quindi essere la protezione della WAN tra i due centri dati quando viene usato il servizio di backup per copiare i dati tra i due pool associati.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-119">Hence, the focus should be on securing the WAN between the two data centers when the Backup Service is used to copy data between the two paired Pools.</span></span>

</div>

<div>

## <a name="mitigating-security-risks"></a><span data-ttu-id="e4fe8-120">Attenuazione dei rischi per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="e4fe8-120">Mitigating Security Risks</span></span>

<span data-ttu-id="e4fe8-121">Esistono diversi modi per migliorare la protezione della sicurezza per il traffico dei servizi di backup, che va dalla restrizione dell'accesso ai Data Center per garantire il trasporto WAN tra i due centri dati.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-121">There are many ways to enhance security protection for the Backup Service traffic, ranging from restricting access to the data centers to securing the WAN transport between the two data centers.</span></span> <span data-ttu-id="e4fe8-122">Nella maggior parte dei casi, le aziende che distribuiscono Lync Server 2013 potrebbero già disporre dell'infrastruttura di sicurezza necessaria.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-122">In most cases, enterprises deploying Lync Server 2013 might already have the required security infrastructure in place.</span></span> <span data-ttu-id="e4fe8-123">Per le aziende che cercano indicazioni, Microsoft offre una soluzione come esempio di creazione di un'infrastruttura IT sicura.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-123">For enterprises looking for guidance, Microsoft provides solution as an example of how to build a secure IT infrastructure.</span></span> <span data-ttu-id="e4fe8-124">Ciò non implica tuttavia che sia l'unica soluzione, né implichi che sia la soluzione preferita per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-124">However, this does not imply that it is the only solution, nor does it imply that it is the preferred solution for Lync Server.</span></span> <span data-ttu-id="e4fe8-125">È consigliabile che i clienti aziendali scelgano la soluzione più adatta alle proprie esigenze specifiche, in base all'infrastruttura e ai requisiti di sicurezza IT. L'esempio di soluzione Microsoft usa IPSec e criteri di gruppo per l'isolamento del server e del dominio.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-125">We recommend that enterprise customers choose the solution suits their specific needs, based on their IT security infrastructure and requirements.The example Microsoft solution employs IPSec and Group Policy for Server and Domain Isolation.</span></span> <span data-ttu-id="e4fe8-126">Per informazioni dettagliate, [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544)vedere.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-126">For details, see [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544).</span></span> <span data-ttu-id="e4fe8-127">Per domande e commenti, contattare secwish@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-127">For questions and comments, contact secwish@microsoft.com.</span></span>

<span data-ttu-id="e4fe8-128">Un'altra possibile soluzione consiste nell'usare IPSec solo per proteggere i dati inviati dal servizio di backup stesso.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-128">Another possible solution is to use IPSec just to help secure the data sent by the Backup Service itself.</span></span> <span data-ttu-id="e4fe8-129">Se si sceglie questo metodo, è necessario configurare le regole IPSec per il protocollo SMB per i server seguenti, dove pool A e pool B sono due pool Front-End associati.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-129">If you choose this method, you should configure the IPSec rules for the SMB protocol for the following servers, where Pool A and Pool B are two paired Front End pools.</span></span>

  - <span data-ttu-id="e4fe8-130">Servizio SMB (TCP/445) da ogni server front-end del pool a all'archivio di file usato dal pool B.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-130">The SMB Service (TCP/445) from each Front End Server in Pool A to the File Store used by Pool B.</span></span>

  - <span data-ttu-id="e4fe8-131">Il servizio SMB (TCP/445) di ogni server front-end nel pool B nell'archivio file usato dal pool A.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-131">The SMB Service (TCP/445) from each Front End Server in Pool B to the File Store used by Pool A.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="e4fe8-132">IPsec non è concepito come sostituzione per la sicurezza a livello di applicazione, ad esempio SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-132">IPsec is not intended as a replacement for application-level security, such as SSL/TLS.</span></span> <span data-ttu-id="e4fe8-133">Un vantaggio dell'uso di IPsec è che può assicurare la sicurezza del traffico di rete per le applicazioni esistenti senza doverle cambiare.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-133">One advantage of using IPsec is that it can provide network traffic security for existing applications without having to change them.</span></span> <span data-ttu-id="e4fe8-134">Le aziende che vogliono garantire semplicemente il trasporto tra i due centri dati devono consultare i rispettivi fornitori di hardware per la rete in merito alle modalità di configurazione delle connessioni WAN sicure tramite l'equipaggiamento del fornitore.</span><span class="sxs-lookup"><span data-stu-id="e4fe8-134">Enterprises that want to just secure the transport between the two data centers should consult their respective networking hardware vendors about ways to set up secure WAN connections by using the vendor’s equipment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

