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
ms.openlocfilehash: 3d7f4497fb6842befba3f5facf5de023b94b4a76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a><span data-ttu-id="423ef-102">Distribuzione di client Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="423ef-102">Deploying Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="423ef-103">_**Argomento Ultima modifica:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="423ef-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="423ef-104">Lync 2013 introduce un approccio diverso alla distribuzione del client.</span><span class="sxs-lookup"><span data-stu-id="423ef-104">Lync 2013 introduces a different approach to client deployment.</span></span> <span data-ttu-id="423ef-105">In partenza dalle versioni precedenti, Lync 2013 non ha più il proprio programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="423ef-105">In a departure from previous releases, Lync 2013 no longer has its own installer.</span></span> <span data-ttu-id="423ef-106">Lync è invece incluso nel programma di installazione di Office 2013.</span><span class="sxs-lookup"><span data-stu-id="423ef-106">Instead, Lync is included with the Office 2013 setup program.</span></span> <span data-ttu-id="423ef-107">Per distribuire Lync 2013 agli utenti, è possibile usare i metodi di installazione e gli strumenti di personalizzazione di Office 2013.</span><span class="sxs-lookup"><span data-stu-id="423ef-107">To deploy Lync 2013 to your users, you can use Office 2013 installation methods and customization tools.</span></span>

  - <span data-ttu-id="423ef-108">**Office 2013 Windows Installer** è un pacchetto di installazione basato su Windows Installer costituito da più file MSI.</span><span class="sxs-lookup"><span data-stu-id="423ef-108">**Office 2013 Windows Installer** is a Windows Installer-based installation package that consists of multiple MSI files.</span></span> <span data-ttu-id="423ef-109">Un pacchetto MSI di base indipendente dalla lingua viene combinato con uno o più pacchetti specifici della lingua per creare un prodotto completo.</span><span class="sxs-lookup"><span data-stu-id="423ef-109">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="423ef-110">La configurazione assembla i singoli pacchetti ed esegue le attività di personalizzazione e manutenzione durante e dopo l'installazione di Office nei computer degli utenti.</span><span class="sxs-lookup"><span data-stu-id="423ef-110">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="423ef-111">Negli argomenti di questa sezione viene descritto come usare e personalizzare Office 2013 Windows Installer per distribuire Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="423ef-111">The topics in this section describe how to use and customize the Office 2013 Windows Installer to deploy Lync 2013.</span></span>

  - <span data-ttu-id="423ef-112">**Office 2013** a portata di clic è un programma di installazione che esegue il flusso di file di installazione di Office per l'utente dal portale di Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="423ef-112">**Office 2013 Click-to-Run** is an installation program that streams Office setup files to the user from the Microsoft Office 365 portal.</span></span> <span data-ttu-id="423ef-113">Gli amministratori possono personalizzare l'installazione usando lo strumento di distribuzione di Office per l'esecuzione a portata di clic.</span><span class="sxs-lookup"><span data-stu-id="423ef-113">Administrators can customize installation by using the Office Deployment Tool for Click-to-Run.</span></span> <span data-ttu-id="423ef-114">Poiché Office 2013 a portata di clic viene usato principalmente nell'ambiente Microsoft Office 365, questo metodo di installazione non viene descritto in dettaglio in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="423ef-114">Because Office 2013 Click-to-Run is primarily used in the Microsoft Office 365 environment, this installation method is not described in detail in this section.</span></span> <span data-ttu-id="423ef-115">Informazioni dettagliate sull'uso e la personalizzazione dell'installazione a portata di clic sono disponibili nella documentazione di Office 2013 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="423ef-115">Detailed information about using and customizing Click-to-Run installation is available in the Office 2013 Resource Kit documentation.</span></span> <span data-ttu-id="423ef-116">Gli amministratori possono anche scaricare i file di origine del programma e della lingua di Office 2013 a portata di clic in una posizione locale, utile quando si vuole minimizzare la richiesta della rete o impedire agli utenti di installare il software da Internet a causa di requisiti di sicurezza aziendale.</span><span class="sxs-lookup"><span data-stu-id="423ef-116">Administrators can also download the Office 2013 Click-to-Run program and language source files to an on-premises location, which is useful when you want to minimize the demand on the network or prevent users from installing software from the Internet because of corporate security requirements.</span></span>

<span data-ttu-id="423ef-117">Gli argomenti di questa sezione sono incentrati su come distribuire i client tramite il programma di installazione di Office 2013 basato su MSI.</span><span class="sxs-lookup"><span data-stu-id="423ef-117">The topics in this section focus on how to deploy clients by using the Office 2013 MSI-based installer.</span></span> <span data-ttu-id="423ef-118">Il riferimento principale dovrebbe essere la documentazione di Office 2013 Resource Kit, che descrive in dettaglio come preparare l'infrastruttura, personalizzare la configurazione e distribuire Office 2013.</span><span class="sxs-lookup"><span data-stu-id="423ef-118">Your primary reference should be the Office 2013 Resource Kit documentation, which describes in detail how to prepare your infrastructure, customize setup, and deploy Office 2013.</span></span> <span data-ttu-id="423ef-119">Tuttavia, è consigliabile usare la documentazione di Office in combinazione con gli argomenti in questa sezione, che evidenziano considerazioni sulla distribuzione specifiche di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="423ef-119">However, you should use the Office documentation in conjunction with topics in this section, which point out deployment considerations that are specific to Lync 2013.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="423ef-120">Il componente aggiuntivo riunione online per Lync 2013, che supporta la gestione delle riunioni dall'interno del client di messaggistica e collaborazione di Outlook, viene installato automaticamente con Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="423ef-120">The Online Meeting Add-in for Lync 2013, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Lync 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="423ef-121">Il programma di installazione di Office 2013 non disinstalla versioni precedenti di Lync o Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="423ef-121">The Office 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="423ef-122">Il client Lync 2013 installa affiancato ad altri client Lync o Office Communicator</span><span class="sxs-lookup"><span data-stu-id="423ef-122">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="423ef-123">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="423ef-123">In This Section</span></span>

  - [<span data-ttu-id="423ef-124">Personalizzazione dell'installazione client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="423ef-124">Customizing client installation in Lync Server 2013</span></span>](lync-server-2013-customizing-client-installation.md)

  - [<span data-ttu-id="423ef-125">Personalizzazione del comportamento di Lync e dell'interfaccia utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="423ef-125">Customizing Lync behavior and the user interface in Lync Server 2013</span></span>](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [<span data-ttu-id="423ef-126">Personalizzazione del componente aggiuntivo riunione online in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="423ef-126">Customizing the Online Meeting Add-in in Lync Server 2013</span></span>](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [<span data-ttu-id="423ef-127">Configurazione della pagina di partecipazione alle riunioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="423ef-127">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)

  - [<span data-ttu-id="423ef-128">Configurazione di versioni client supportate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="423ef-128">Configuring supported client versions in Lync Server 2013</span></span>](lync-server-2013-configuring-supported-client-versions.md)

  - [<span data-ttu-id="423ef-129">Configurazione della modalità di privacy della presenza avanzata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="423ef-129">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

