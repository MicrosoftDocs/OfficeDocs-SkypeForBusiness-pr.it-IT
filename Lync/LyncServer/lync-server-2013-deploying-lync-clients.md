---
title: 'Lync Server 2013: distribuzione di client Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0004e3ce0b3e00cb90fc93cee148844ebc5d4d7e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a><span data-ttu-id="f8620-102">Distribuzione di client Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8620-102">Deploying Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8620-103">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="f8620-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="f8620-104">Lync 2013 introduce un approccio diverso alla distribuzione del client.</span><span class="sxs-lookup"><span data-stu-id="f8620-104">Lync 2013 introduces a different approach to client deployment.</span></span> <span data-ttu-id="f8620-105">In una partenza dalle versioni precedenti, Lync 2013 non ha più un proprio programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="f8620-105">In a departure from previous releases, Lync 2013 no longer has its own installer.</span></span> <span data-ttu-id="f8620-106">Lync, invece, è incluso nel programma di installazione di Office 2013.</span><span class="sxs-lookup"><span data-stu-id="f8620-106">Instead, Lync is included with the Office 2013 setup program.</span></span> <span data-ttu-id="f8620-107">Per distribuire Lync 2013 agli utenti, è possibile utilizzare i metodi di installazione e gli strumenti di personalizzazione di Office 2013.</span><span class="sxs-lookup"><span data-stu-id="f8620-107">To deploy Lync 2013 to your users, you can use Office 2013 installation methods and customization tools.</span></span>

  - <span data-ttu-id="f8620-108">**Office 2013 Windows Installer** è un pacchetto di installazione basato su Windows Installer costituito da più file MSI.</span><span class="sxs-lookup"><span data-stu-id="f8620-108">**Office 2013 Windows Installer** is a Windows Installer-based installation package that consists of multiple MSI files.</span></span> <span data-ttu-id="f8620-109">La creazione di un prodotto completo si basa sulla combinazione di un pacchetto MSI principale indipendente dalla lingua con uno o più pacchetti specifici della lingua.</span><span class="sxs-lookup"><span data-stu-id="f8620-109">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="f8620-110">I singoli pacchetti vengono assemblati durante l'installazione mentre le attività di personalizzazione e manutenzione vengono eseguite durante e dopo l'installazione di Office nei computer degli utenti.</span><span class="sxs-lookup"><span data-stu-id="f8620-110">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="f8620-111">Negli argomenti di questa sezione viene descritto come utilizzare e personalizzare il programma di installazione di Windows di Office 2013 per la distribuzione di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f8620-111">The topics in this section describe how to use and customize the Office 2013 Windows Installer to deploy Lync 2013.</span></span>

  - <span data-ttu-id="f8620-112">**Office 2013 a** portata di clic è un programma di installazione che consente di eseguire il flusso dei file di installazione di Office all'utente dal portale di Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="f8620-112">**Office 2013 Click-to-Run** is an installation program that streams Office setup files to the user from the Microsoft Office 365 portal.</span></span> <span data-ttu-id="f8620-113">Gli amministratori possono personalizzare l'installazione utilizzando lo strumento di distribuzione di Office per la funzione a portata di clic.</span><span class="sxs-lookup"><span data-stu-id="f8620-113">Administrators can customize installation by using the Office Deployment Tool for Click-to-Run.</span></span> <span data-ttu-id="f8620-114">Poiché la funzione a portata di clic di Office 2013 viene utilizzata principalmente nell'ambiente Microsoft Office 365, questo metodo di installazione non viene descritto in dettaglio in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="f8620-114">Because Office 2013 Click-to-Run is primarily used in the Microsoft Office 365 environment, this installation method is not described in detail in this section.</span></span> <span data-ttu-id="f8620-115">Per informazioni dettagliate sull'utilizzo e la personalizzazione dell'installazione a portata di clic, vedere la documentazione di Office 2013 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="f8620-115">Detailed information about using and customizing Click-to-Run installation is available in the Office 2013 Resource Kit documentation.</span></span> <span data-ttu-id="f8620-116">Gli amministratori possono anche scaricare il programma di Office 2013 a portata di clic e i file di origine della lingua in una posizione locale, che è utile quando si desidera ridurre al minimo la richiesta sulla rete o impedire agli utenti di installare il software da Internet a causa di requisiti di sicurezza aziendale.</span><span class="sxs-lookup"><span data-stu-id="f8620-116">Administrators can also download the Office 2013 Click-to-Run program and language source files to an on-premises location, which is useful when you want to minimize the demand on the network or prevent users from installing software from the Internet because of corporate security requirements.</span></span>

<span data-ttu-id="f8620-117">Negli argomenti di questa sezione vengono illustrate le modalità di distribuzione dei client tramite il programma di installazione di Office 2013 basato su MSI.</span><span class="sxs-lookup"><span data-stu-id="f8620-117">The topics in this section focus on how to deploy clients by using the Office 2013 MSI-based installer.</span></span> <span data-ttu-id="f8620-118">Il riferimento primario dovrebbe essere la documentazione di Office 2013 Resource Kit, in cui vengono descritti in dettaglio la modalità di preparazione dell'infrastruttura, la personalizzazione dell'installazione e la distribuzione di Office 2013.</span><span class="sxs-lookup"><span data-stu-id="f8620-118">Your primary reference should be the Office 2013 Resource Kit documentation, which describes in detail how to prepare your infrastructure, customize setup, and deploy Office 2013.</span></span> <span data-ttu-id="f8620-119">Tuttavia, è consigliabile utilizzare la documentazione di Office in combinazione con gli argomenti di questa sezione, in cui vengono indicate le considerazioni relative alla distribuzione specifiche di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f8620-119">However, you should use the Office documentation in conjunction with topics in this section, which point out deployment considerations that are specific to Lync 2013.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="f8620-120">Il componente aggiuntivo per riunioni online per Lync 2013, che supporta la gestione delle riunioni dall'interno del client di messaggistica e collaborazione di Outlook, viene installato automaticamente con Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f8620-120">The Online Meeting Add-in for Lync 2013, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Lync 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="f8620-121">Il programma di installazione di Office 2013 non disinstalla le versioni precedenti di Lync o Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="f8620-121">The Office 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="f8620-122">Il client Lync 2013 installa affiancati con altri client Lync o Office Communicator</span><span class="sxs-lookup"><span data-stu-id="f8620-122">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f8620-123">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="f8620-123">In This Section</span></span>

  - [<span data-ttu-id="f8620-124">Personalizzazione dell'installazione client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8620-124">Customizing client installation in Lync Server 2013</span></span>](lync-server-2013-customizing-client-installation.md)

  - [<span data-ttu-id="f8620-125">Personalizzazione del comportamento di Lync e dell'interfaccia utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8620-125">Customizing Lync behavior and the user interface in Lync Server 2013</span></span>](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [<span data-ttu-id="f8620-126">Personalizzazione del componente aggiuntivo per riunioni online in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8620-126">Customizing the Online Meeting Add-in in Lync Server 2013</span></span>](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [<span data-ttu-id="f8620-127">Configurazione della pagina di partecipazione alle riunioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8620-127">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)

  - [<span data-ttu-id="f8620-128">Configurazione delle versioni client supportate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8620-128">Configuring supported client versions in Lync Server 2013</span></span>](lync-server-2013-configuring-supported-client-versions.md)

  - [<span data-ttu-id="f8620-129">Configurazione della modalità privacy della presenza avanzata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8620-129">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

