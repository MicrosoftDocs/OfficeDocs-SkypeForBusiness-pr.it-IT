---
title: 'Lync Server 2013: preparazione dello schema di Active Directory'
description: 'Lync Server 2013: preparazione dello schema di Active Directory.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3df7533dcbabe278fd366b441cfd8daa83f54b23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560312"
---
# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a><span data-ttu-id="7fdc7-103">Preparazione dello schema di Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fdc7-103">Preparing the Active Directory schema in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fdc7-104">_**Ultimo argomento modificato:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="7fdc7-104">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="7fdc7-105">Prima di iniziare la preparazione di servizi di dominio Active Directory, è possibile aprire i file di schema utilizzando un editor di testo, ad esempio Blocco note di Windows, oppure vedere [estensioni dello schema, classi e attributi di Active Directory utilizzati da Lync server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) per esaminare tutte le estensioni dello schema dei servizi di dominio Active Directory che verranno modificate per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7fdc7-105">Before you begin preparing Active Directory Domain Services, you can open the schema files by using a text editor, such as Windows Notepad, or see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) to review all the Active Directory Domain Services schema extensions that will be modified for Lync Server 2013.</span></span> <span data-ttu-id="7fdc7-106">Lync Server utilizza quattro file di schema:</span><span class="sxs-lookup"><span data-stu-id="7fdc7-106">Lync Server uses four schema files:</span></span>

  - <span data-ttu-id="7fdc7-107">ExternalSchema. ldf, utilizzato per l'interoperabilità con Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="7fdc7-107">ExternalSchema.ldf, which is used for interoperability with Microsoft Exchange Server</span></span>

  - <span data-ttu-id="7fdc7-108">ServerSchema. ldf, che è il file di schema principale di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fdc7-108">ServerSchema.ldf, which is the primary Lync Server 2013 schema file</span></span>

  - <span data-ttu-id="7fdc7-109">BackCompatSchema.ldf, utilizzato per l'interoperabilità con gli eventuali componenti di versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="7fdc7-109">BackCompatSchema.ldf, which is used for interoperability with any components from prior releases</span></span>

  - <span data-ttu-id="7fdc7-110">VersionSchema.ldf, utilizzato per le informazioni sulla versione dello schema preparato</span><span class="sxs-lookup"><span data-stu-id="7fdc7-110">VersionSchema.ldf, which is used for version information of the prepared schema</span></span>

<span data-ttu-id="7fdc7-111">Tutti i file con estensione ldf vengono installati durante la preparazione dello schema, indipendentemente dal fatto che si stia eseguendo la migrazione da una versione precedente o eseguendo un'installazione pulita.</span><span class="sxs-lookup"><span data-stu-id="7fdc7-111">All .ldf files are installed during schema preparation, regardless of whether you are migrating from a previous release or performing a clean installation.</span></span> <span data-ttu-id="7fdc7-112">Questi file di schema sono installati nella sequenza illustrata nell'elenco precedente e si trovano nella \\ cartella Support \\ schema sul supporto di installazione.</span><span class="sxs-lookup"><span data-stu-id="7fdc7-112">These schema files are installed in the sequence shown in the preceding list and are located in the \\Support\\schema folder on the installation media.</span></span>

<span data-ttu-id="7fdc7-113">Le estensioni dello schema di Lync Server vengono replicate in tutti i domini, che influiscono sul traffico di rete.</span><span class="sxs-lookup"><span data-stu-id="7fdc7-113">The Lync Server schema extensions are replicated across all domains, which impacts network traffic.</span></span> <span data-ttu-id="7fdc7-114">Eseguire la preparazione dello schema in un momento di scarso utilizzo della rete.</span><span class="sxs-lookup"><span data-stu-id="7fdc7-114">Run schema preparation at a time when network usage is low.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7fdc7-115">Se è necessario aggiungere il supporto per Microsoft® Office Communicator Mobile 2007 R2 per Java e Microsoft® Office Communicator Mobile per i client mobili Nokia 1,0 alla distribuzione di Lync Server 2013, è necessario preparare lo schema di Active Directory per Microsoft Office Communications Server 2007 R2 durante l'installazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7fdc7-115">If you need to add support for Microsoft® Office Communicator Mobile 2007 R2 for Java and Microsoft® Office Communicator Mobile for Nokia 1.0 mobile clients to your Lync Server 2013 deployment, you need to prepare the Active Directory schema for Microsoft Office Communications Server 2007 R2 during installation of Lync Server 2013.</span></span> <span data-ttu-id="7fdc7-116">Per il software e la documentazione necessari, vedere <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A> .</span><span class="sxs-lookup"><span data-stu-id="7fdc7-116">For the necessary software and documentation, see <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A>.</span></span>



</div>

<div>

## <a name="adsi-edit"></a><span data-ttu-id="7fdc7-117">ADSI Edit</span><span class="sxs-lookup"><span data-stu-id="7fdc7-117">ADSI Edit</span></span>

<span data-ttu-id="7fdc7-118">Active Directory Service Interfaces Editor (ADSI Edit) è uno strumento di amministrazione di Servizi di dominio Active Directory che consente di verificare la preparazione e la replica dello schema.</span><span class="sxs-lookup"><span data-stu-id="7fdc7-118">Active Directory Service Interfaces Editor (ADSI Edit) is an AD DS administration tool that you can use to verify schema preparation and replication.</span></span>

<span data-ttu-id="7fdc7-119">ADSI Edit viene installato per impostazione predefinita quando si installa il ruolo Servizi di dominio Active Directory per impostare un server come controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="7fdc7-119">ADSI Edit is installed by default when you install the AD DS role to make a server a domain controller.</span></span> <span data-ttu-id="7fdc7-120">Per Windows Server 2008 e Windows Server 2008 R2, ADSI Edit (ADSIEdit. msc) è incluso negli strumenti di amministrazione remota del server.</span><span class="sxs-lookup"><span data-stu-id="7fdc7-120">For Windows Server 2008 and Windows Server 2008 R2, ADSI Edit (adsiedit.msc) is included with the Remote Server Administration Tools (RSAT).</span></span> <span data-ttu-id="7fdc7-121">È inoltre possibile installare Strumenti di amministrazione remota del server in server membri del dominio o in server autonomi.</span><span class="sxs-lookup"><span data-stu-id="7fdc7-121">You can also install RSAT on domain member servers or stand-alone servers.</span></span> <span data-ttu-id="7fdc7-122">Il pacchetto di Strumenti di amministrazione remota del server viene copiato in tali server per impostazione predefinita durante l'installazione di Windows, ma non viene installato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7fdc7-122">The RSAT package is copied to these servers by default when you install Windows, but it is not installed by default.</span></span> <span data-ttu-id="7fdc7-123">Per installare i singoli strumenti, utilizzare Server Manager.</span><span class="sxs-lookup"><span data-stu-id="7fdc7-123">You install individual tools by using Server Manager.</span></span> <span data-ttu-id="7fdc7-124">È possibile accedere ad ADSI Edit da **Strumenti di amministrazione ruoli**, **Strumenti per Servizi di dominio Active Directory**, **Strumenti di Controller di dominio Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="7fdc7-124">ADSI Edit is included under **Role Administration Tools**, **Active Directory Domain Services Tools**, **Active Directory Domain Controller Tools**.</span></span>

<span data-ttu-id="7fdc7-125">Per Windows Server 2003, ADSI Edit è incluso negli strumenti di supporto.</span><span class="sxs-lookup"><span data-stu-id="7fdc7-125">For Windows Server 2003, ADSI Edit is included with the Support Tools.</span></span> <span data-ttu-id="7fdc7-126">Gli strumenti di supporto sono disponibili nel CD di Windows Server 2003 nella \\ \\ cartella degli strumenti di supporto oppure è possibile scaricarli da "strumenti di supporto di windows Server 2003 Service Pack 2 32-bit" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770) .</span><span class="sxs-lookup"><span data-stu-id="7fdc7-126">The Support Tools are available from the Windows Server 2003 CD in the \\SUPPORT\\TOOLS folder, or you can download them from “Windows Server 2003 Service Pack 2 32-bit Support Tools” at [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770).</span></span> <span data-ttu-id="7fdc7-127">Le istruzioni per l'installazione degli strumenti di supporto del CD del prodotto sono disponibili da "installa gli strumenti di supporto di Windows" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771) .</span><span class="sxs-lookup"><span data-stu-id="7fdc7-127">Instructions for installing the Support Tools from the product CD are available from “Install Windows Support Tools” at [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771).</span></span> <span data-ttu-id="7fdc7-128">Adsiedit.dll viene automaticamente registrata quando si installano gli strumenti di supporto.</span><span class="sxs-lookup"><span data-stu-id="7fdc7-128">Adsiedit.dll is automatically registered when you install the support tools.</span></span> <span data-ttu-id="7fdc7-129">Se, tuttavia, i file sono stati copiati nel computer in uso, è necessario eseguire il comando **regsvr32** per registrare il file adsiedit.dll prima di poter eseguire lo strumento.</span><span class="sxs-lookup"><span data-stu-id="7fdc7-129">If, however, you copied the files to your computer, you must run the **regsvr32** command to register the adsiedit.dll file before you can run the tool.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7fdc7-130">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="7fdc7-130">In This Section</span></span>

  - [<span data-ttu-id="7fdc7-131">Esecuzione della preparazione dello schema di Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fdc7-131">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)

  - [<span data-ttu-id="7fdc7-132">Verifica della replica dello schema di Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fdc7-132">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7fdc7-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fdc7-133">See Also</span></span>


[<span data-ttu-id="7fdc7-134">Preparazione della foresta per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fdc7-134">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="7fdc7-135">Preparazione dei domini per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fdc7-135">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

