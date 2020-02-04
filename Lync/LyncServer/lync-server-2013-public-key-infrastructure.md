---
title: 'Lync Server 2013: infrastruttura a chiave pubblica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b205699e9efd896a157654f5c1fb200e34087fc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="public-key-infrastructure-for-lync-server-2013"></a><span data-ttu-id="5927f-102">Infrastruttura a chiave pubblica per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5927f-102">Public Key Infrastructure for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5927f-103">_**Argomento Ultima modifica:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="5927f-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="5927f-104">Microsoft Lync Server 2013 si basa su certificati per l'autenticazione del server e stabilisce una catena di trust tra client e server e tra i diversi ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="5927f-104">Microsoft Lync Server 2013 relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles.</span></span> <span data-ttu-id="5927f-105">Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 e infrastruttura a chiave pubblica (PKI) di Windows Server 2003 fornisce l'infrastruttura per stabilire e convalidare questa catena di attendibilità.</span><span class="sxs-lookup"><span data-stu-id="5927f-105">The Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 Public Key Infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust.</span></span>

<span data-ttu-id="5927f-106">I certificati sono ID digitali.</span><span class="sxs-lookup"><span data-stu-id="5927f-106">Certificates are digital IDs.</span></span> <span data-ttu-id="5927f-107">Identificano un server per nome e ne specificano le proprietà.</span><span class="sxs-lookup"><span data-stu-id="5927f-107">They identify a server by name and specify its properties.</span></span> <span data-ttu-id="5927f-108">Per assicurarsi che le informazioni su un certificato siano valide, il certificato deve essere emesso da una CA considerata attendibile dai client o da altri server che si connettono al server.</span><span class="sxs-lookup"><span data-stu-id="5927f-108">To ensure that the information on a certificate is valid, the certificate must be issued by a CA that is trusted by clients or other servers that connect to the server.</span></span> <span data-ttu-id="5927f-109">Se il server si connette solo con altri client e server su una rete privata, la CA può essere una CA aziendale.</span><span class="sxs-lookup"><span data-stu-id="5927f-109">If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA.</span></span> <span data-ttu-id="5927f-110">Se il server interagisce con entità esterne alla rete privata, potrebbe essere richiesta una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="5927f-110">If the server interacts with entities outside the private network, a public CA might be required.</span></span>

<span data-ttu-id="5927f-111">Anche se le informazioni sul certificato sono valide, ci deve essere un modo per verificare che il server che presenta il certificato sia effettivamente quello rappresentato dal certificato stesso.</span><span class="sxs-lookup"><span data-stu-id="5927f-111">Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate.</span></span> <span data-ttu-id="5927f-112">È qui che entra in gioco la PKI di Windows.</span><span class="sxs-lookup"><span data-stu-id="5927f-112">This is where the Windows PKI comes in.</span></span>

<span data-ttu-id="5927f-113">Ogni certificato è collegato a una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="5927f-113">Each certificate is linked to a public key.</span></span> <span data-ttu-id="5927f-114">Il server indicato sul certificato contiene una chiave privata corrispondente di sua esclusiva conoscenza.</span><span class="sxs-lookup"><span data-stu-id="5927f-114">The server named on the certificate holds a corresponding private key that only it knows.</span></span> <span data-ttu-id="5927f-115">Un client o un server che si connette utilizza la chiave pubblica per crittografare una parte di informazioni casuali e la invia al server.</span><span class="sxs-lookup"><span data-stu-id="5927f-115">A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server.</span></span> <span data-ttu-id="5927f-116">Se il server decrittografa le informazioni e le restituisce come testo normale, l'entità che si connette può essere certa che il server detenga la chiave privata corrispondente al certificato e pertanto sia il server indicato sul certificato.</span><span class="sxs-lookup"><span data-stu-id="5927f-116">If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5927f-117">Non tutte le CA pubbliche soddisfano i requisiti dei certificati di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5927f-117">Not all public CAs comply with the requirements of Lync Server 2013 certificates.</span></span> <span data-ttu-id="5927f-118">Ti consigliamo di fare riferimento all'elenco dei fornitori di CA pubblici certificati per le tue esigenze per i certificati pubblici.</span><span class="sxs-lookup"><span data-stu-id="5927f-118">We recommend that you refer to the listing of certified Public CA vendors for your public certificate needs.</span></span> <span data-ttu-id="5927f-119">Per informazioni dettagliate, vedere partner per i certificati di <A href="http://go.microsoft.com/fwlink/p/?linkid=140898">http://go.microsoft.com/fwlink/p/?LinkId=140898</A>comunicazioni unificate.</span><span class="sxs-lookup"><span data-stu-id="5927f-119">For details, see Unified Communications Certificate Partners at <A href="http://go.microsoft.com/fwlink/p/?linkid=140898">http://go.microsoft.com/fwlink/p/?LinkId=140898</A>.</span></span>



</div>

<div>

## <a name="crl-distribution-points"></a><span data-ttu-id="5927f-120">Punti di distribuzione CLR</span><span class="sxs-lookup"><span data-stu-id="5927f-120">CRL Distribution Points</span></span>

<span data-ttu-id="5927f-121">Lync Server 2013 richiede che tutti i certificati server contengano uno o più punti di distribuzione dell'elenco di revoche di certificati (CRL).</span><span class="sxs-lookup"><span data-stu-id="5927f-121">Lync Server 2013 requires all server certificates to contain one or more Certificate Revocation List (CRL) distribution points.</span></span> <span data-ttu-id="5927f-122">I punti di distribuzione CRL (CDP) sono posizioni da cui è possibile scaricare i CRL per verificare che il certificato non sia stato revocato dal momento in cui è stato rilasciato e che rientri ancora nel periodo di validità.</span><span class="sxs-lookup"><span data-stu-id="5927f-122">CRL distribution points (CDPs) are locations from which CRLs can be downloaded for purposes of verifying that the certificate has not been revoked since the time it was issued and the certificate is still within the validity period.</span></span> <span data-ttu-id="5927f-123">Un punto di distribuzione CRL viene indicato nelle proprietà del certificato come URL e in genere è protetto da HTTP.</span><span class="sxs-lookup"><span data-stu-id="5927f-123">A CRL distribution point is noted in the properties of the certificate as a URL, and is typically secure HTTP.</span></span>

</div>

<div>

## <a name="enhanced-key-usage"></a><span data-ttu-id="5927f-124">Utilizzo chiavi avanzato</span><span class="sxs-lookup"><span data-stu-id="5927f-124">Enhanced Key Usage</span></span>

<span data-ttu-id="5927f-125">Lync Server 2013 richiede che tutti i certificati server supportino l'uso di chiavi avanzate (EKU) per l'autenticazione del server.</span><span class="sxs-lookup"><span data-stu-id="5927f-125">Lync Server 2013 requires all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication.</span></span> <span data-ttu-id="5927f-126">La configurazione del campo EKU per l'autenticazione del server indica che il certificato è valido ai fini dell'autenticazione dei server.</span><span class="sxs-lookup"><span data-stu-id="5927f-126">Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers.</span></span> <span data-ttu-id="5927f-127">Tale EKU è essenziale per MTLS.</span><span class="sxs-lookup"><span data-stu-id="5927f-127">This EKU is essential for MTLS.</span></span> <span data-ttu-id="5927f-128">È possibile avere più di una voce in EKU, abilitando il certificato per più di uno scopo.</span><span class="sxs-lookup"><span data-stu-id="5927f-128">It is possible to have more than one entry in the EKU, enabling the certificate for more than one purpose.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5927f-129">L'EKU di autenticazione client è necessario per le connessioni MTLS in uscita da Live Communications Server 2003 e Live Communications Server 2005, ma non è più necessario.</span><span class="sxs-lookup"><span data-stu-id="5927f-129">The Client Authentication EKU is required for outbound MTLS connections from Live Communications Server 2003 and Live Communications Server 2005, but it is no longer required.</span></span> <span data-ttu-id="5927f-130">Tuttavia, questo EKU deve essere presente in Edge Server che si connettono a AOL per mezzo della connettività di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="5927f-130">However, this EKU must be present on Edge Servers that connect to AOL by means of public IM connectivity.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

