---
title: 'Lync Server 2013: Preparazione dello schema di Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5479bfbb0774ddd68015de470de082f0cc185b98
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a><span data-ttu-id="f2d84-102">Preparazione dello schema di Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2d84-102">Preparing the Active Directory schema in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2d84-103">_**Argomento Ultima modifica:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="f2d84-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="f2d84-104">Prima di iniziare la preparazione dei servizi di dominio Active Directory, è possibile aprire i file di schema usando un editor di testo, come il blocco note di Windows, oppure vedere le [estensioni, le classi e gli attributi di uno schema di Active Directory usati da Lync server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) per esaminare tutte le estensioni dello schema di servizi di dominio Active Directory che verranno modificate per lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f2d84-104">Before you begin preparing Active Directory Domain Services, you can open the schema files by using a text editor, such as Windows Notepad, or see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) to review all the Active Directory Domain Services schema extensions that will be modified for Lync Server 2013.</span></span> <span data-ttu-id="f2d84-105">Lync Server usa quattro file di schema:</span><span class="sxs-lookup"><span data-stu-id="f2d84-105">Lync Server uses four schema files:</span></span>

  - <span data-ttu-id="f2d84-106">ExternalSchema. ldf, usato per l'interoperabilità con Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="f2d84-106">ExternalSchema.ldf, which is used for interoperability with Microsoft Exchange Server</span></span>

  - <span data-ttu-id="f2d84-107">ServerSchema. ldf, che è il file di schema 2013 principale di Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2d84-107">ServerSchema.ldf, which is the primary Lync Server 2013 schema file</span></span>

  - <span data-ttu-id="f2d84-108">BackCompatSchema. ldf, usato per l'interoperabilità con tutti i componenti di versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="f2d84-108">BackCompatSchema.ldf, which is used for interoperability with any components from prior releases</span></span>

  - <span data-ttu-id="f2d84-109">VersionSchema. ldf, usato per le informazioni sulla versione dello schema preparato</span><span class="sxs-lookup"><span data-stu-id="f2d84-109">VersionSchema.ldf, which is used for version information of the prepared schema</span></span>

<span data-ttu-id="f2d84-110">Tutti i file con estensione ldf vengono installati durante la preparazione dello schema, indipendentemente dal fatto che si stia eseguendo la migrazione da una versione precedente o sia stata eseguita un'installazione pulita.</span><span class="sxs-lookup"><span data-stu-id="f2d84-110">All .ldf files are installed during schema preparation, regardless of whether you are migrating from a previous release or performing a clean installation.</span></span> <span data-ttu-id="f2d84-111">Questi file di schema vengono installati nella sequenza visualizzata nell'elenco precedente e si trovano nella cartella dello \\schema\\di supporto nel supporto di installazione.</span><span class="sxs-lookup"><span data-stu-id="f2d84-111">These schema files are installed in the sequence shown in the preceding list and are located in the \\Support\\schema folder on the installation media.</span></span>

<span data-ttu-id="f2d84-112">Le estensioni dello schema di Lync Server vengono replicate in tutti i domini, che influiscono sul traffico di rete.</span><span class="sxs-lookup"><span data-stu-id="f2d84-112">The Lync Server schema extensions are replicated across all domains, which impacts network traffic.</span></span> <span data-ttu-id="f2d84-113">Eseguire la preparazione dello schema in un momento in cui l'utilizzo della rete è basso.</span><span class="sxs-lookup"><span data-stu-id="f2d84-113">Run schema preparation at a time when network usage is low.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2d84-114">Se è necessario aggiungere il supporto per Microsoft® Office Communicator Mobile 2007 R2 per Java e Microsoft® Office Communicator Mobile per i client mobili Nokia 1,0 alla distribuzione di Lync Server 2013, è necessario preparare lo schema Active Directory per Microsoft Office Communications Server 2007 R2 durante l'installazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f2d84-114">If you need to add support for Microsoft® Office Communicator Mobile 2007 R2 for Java and Microsoft® Office Communicator Mobile for Nokia 1.0 mobile clients to your Lync Server 2013 deployment, you need to prepare the Active Directory schema for Microsoft Office Communications Server 2007 R2 during installation of Lync Server 2013.</span></span> <span data-ttu-id="f2d84-115">Per il software e la documentazione necessari, <A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>vedere.</span><span class="sxs-lookup"><span data-stu-id="f2d84-115">For the necessary software and documentation, see <A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>.</span></span>



</div>

<div>

## <a name="adsi-edit"></a><span data-ttu-id="f2d84-116">Modifica ADSI</span><span class="sxs-lookup"><span data-stu-id="f2d84-116">ADSI Edit</span></span>

<span data-ttu-id="f2d84-117">Active Directory Service Interfaces Editor (ADSI Edit) è uno strumento di amministrazione AD DS che puoi usare per verificare la preparazione e la replica dello schema.</span><span class="sxs-lookup"><span data-stu-id="f2d84-117">Active Directory Service Interfaces Editor (ADSI Edit) is an AD DS administration tool that you can use to verify schema preparation and replication.</span></span>

<span data-ttu-id="f2d84-118">ADSI Edit viene installato per impostazione predefinita quando si installa il ruolo di servizi di dominio Active Directory per rendere un server un domain controller.</span><span class="sxs-lookup"><span data-stu-id="f2d84-118">ADSI Edit is installed by default when you install the AD DS role to make a server a domain controller.</span></span> <span data-ttu-id="f2d84-119">Per Windows Server 2008 e Windows Server 2008 R2, ADSI Edit (ADSIEdit. msc) è incluso negli strumenti di amministrazione del server remoto.</span><span class="sxs-lookup"><span data-stu-id="f2d84-119">For Windows Server 2008 and Windows Server 2008 R2, ADSI Edit (adsiedit.msc) is included with the Remote Server Administration Tools (RSAT).</span></span> <span data-ttu-id="f2d84-120">È anche possibile installare i server di amministrazione remota in Domain Member o server autonomi.</span><span class="sxs-lookup"><span data-stu-id="f2d84-120">You can also install RSAT on domain member servers or stand-alone servers.</span></span> <span data-ttu-id="f2d84-121">Il pacchetto di amministrazione remota viene copiato in questi server per impostazione predefinita quando si installa Windows, ma non viene installato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f2d84-121">The RSAT package is copied to these servers by default when you install Windows, but it is not installed by default.</span></span> <span data-ttu-id="f2d84-122">Si installano singoli strumenti tramite Server Manager.</span><span class="sxs-lookup"><span data-stu-id="f2d84-122">You install individual tools by using Server Manager.</span></span> <span data-ttu-id="f2d84-123">ADSI Edit è incluso in **strumenti amministrazione ruoli**, **strumenti servizi di dominio Active Directory**, **strumenti Domain controller di Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="f2d84-123">ADSI Edit is included under **Role Administration Tools**, **Active Directory Domain Services Tools**, **Active Directory Domain Controller Tools**.</span></span>

<span data-ttu-id="f2d84-124">Per Windows Server 2003, ADSI Edit è incluso negli strumenti di supporto.</span><span class="sxs-lookup"><span data-stu-id="f2d84-124">For Windows Server 2003, ADSI Edit is included with the Support Tools.</span></span> <span data-ttu-id="f2d84-125">Gli strumenti di supporto sono disponibili nel CD di Windows Server 2003 nella \\cartella\\strumenti di supporto oppure è possibile scaricarli da "strumenti di supporto di Windows server 2003 Service Pack 2 32-bit [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770)" at.</span><span class="sxs-lookup"><span data-stu-id="f2d84-125">The Support Tools are available from the Windows Server 2003 CD in the \\SUPPORT\\TOOLS folder, or you can download them from “Windows Server 2003 Service Pack 2 32-bit Support Tools” at [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770).</span></span> <span data-ttu-id="f2d84-126">Le istruzioni per l'installazione degli strumenti di supporto dal CD del prodotto sono disponibili in [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771)"installare gli strumenti di supporto di Windows".</span><span class="sxs-lookup"><span data-stu-id="f2d84-126">Instructions for installing the Support Tools from the product CD are available from “Install Windows Support Tools” at [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771).</span></span> <span data-ttu-id="f2d84-127">ADSIEdit. dll viene registrato automaticamente quando si installano gli strumenti di supporto.</span><span class="sxs-lookup"><span data-stu-id="f2d84-127">Adsiedit.dll is automatically registered when you install the support tools.</span></span> <span data-ttu-id="f2d84-128">Se invece i file sono stati copiati nel computer, è necessario eseguire il comando **regsvr32** per registrare il file adsiedit. dll prima di poter eseguire lo strumento.</span><span class="sxs-lookup"><span data-stu-id="f2d84-128">If, however, you copied the files to your computer, you must run the **regsvr32** command to register the adsiedit.dll file before you can run the tool.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f2d84-129">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="f2d84-129">In This Section</span></span>

  - [<span data-ttu-id="f2d84-130">Esecuzione della preparazione dello schema in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2d84-130">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)

  - [<span data-ttu-id="f2d84-131">Verifica della replica dello schema in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2d84-131">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f2d84-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2d84-132">See Also</span></span>


[<span data-ttu-id="f2d84-133">Preparazione della foresta per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2d84-133">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="f2d84-134">Preparazione dei domini per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2d84-134">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

