---
title: "Lync Server 2013: Panoramica dell'ambiente ibrido di Lync Server"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0420e4aaded9f5ae90d26c4cbdc176e7fb4c6bb5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a><span data-ttu-id="ee1ef-102">Panoramica dell'ambiente ibrido di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee1ef-102">Overview of the Lync Server 2013 hybrid environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee1ef-103">_**Argomento Ultima modifica:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="ee1ef-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="ee1ef-104">L'ambiente ibrido di Lync Server 2013 si riferisce a una distribuzione in cui ci sono alcuni utenti ospitati nel Lync Server 2013 locale e altri utenti ospitati in Lync Online, ma gli utenti condividono lo stesso dominio, ad esempio user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ee1ef-104">Lync Server 2013 hybrid environment refers to a deployment in which there are some users homed to the on-premises Lync Server 2013 and other users homed to Lync Online, but users share the same domain, such as user@contoso.com.</span></span>

<div>

## <a name="about-this-guide"></a><span data-ttu-id="ee1ef-105">Informazioni su questa guida</span><span class="sxs-lookup"><span data-stu-id="ee1ef-105">About this Guide</span></span>

<span data-ttu-id="ee1ef-106">Questa guida descrive le attività necessarie per configurare l'ambiente Lync Server 2013 per l'interoperabilità con Lync Online e quindi per trasferire gli utenti dalla distribuzione locale per l'uso di Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ee1ef-106">This guide describes the tasks necessary to configure your Lync Server 2013 environment for interoperability with Lync Online, and then to move users from your on-premises deployment to use Lync Online.</span></span>

</div>

<div>

## <a name="prerequisites"></a><span data-ttu-id="ee1ef-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ee1ef-107">Prerequisites</span></span>

<span data-ttu-id="ee1ef-108">Per completare le attività per la configurazione di una distribuzione ibrida, sarà necessario installare le applicazioni e le utilità seguenti.</span><span class="sxs-lookup"><span data-stu-id="ee1ef-108">You will need to have the following applications and utilities installed to complete the tasks for configuring a deployment for hybrid.</span></span> <span data-ttu-id="ee1ef-109">I programmi di installazione per questi file sono inclusi nel supporto di installazione fornito per la distribuzione, nonché nei collegamenti inclusi nell'elenco seguente.</span><span class="sxs-lookup"><span data-stu-id="ee1ef-109">The installers for these files are included on the installation media provided for your deployment, as well as at the links included in the following list.</span></span>

  - [<span data-ttu-id="ee1ef-110">Active Directory Federation Services (AD FS) 2,0</span><span class="sxs-lookup"><span data-stu-id="ee1ef-110">Active Directory Federation Services (AD FS) 2.0</span></span>](http://go.microsoft.com/fwlink/p/?linkid=257305)

  - [<span data-ttu-id="ee1ef-111">Strumento di sincronizzazione di Microsoft Directory 9,1</span><span class="sxs-lookup"><span data-stu-id="ee1ef-111">Microsoft Directory Synchronization Tool 9.1</span></span>](http://go.microsoft.com/fwlink/p/?linkid=257307)

  - [<span data-ttu-id="ee1ef-112">Installare Windows PowerShell per Single Sign-on con ADFS</span><span class="sxs-lookup"><span data-stu-id="ee1ef-112">Install Windows PowerShell for single sign-on with AD FS</span></span>](http://go.microsoft.com/fwlink/p/?linkid=398710)

  - <span data-ttu-id="ee1ef-113">L'assistente per l'accesso ai Microsoft Online Services (Msoidcli-7.0. msi) è incluso nella configurazione desktop di Office 365, che può essere ottenuta dalla pagina Download collegata dal portale di amministrazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="ee1ef-113">Microsoft Online Services Sign-in Assistant (msoidcli-7.0.msi) is included with the Desktop Setup for Office 365, which can be obtained from the Downloads page linked to from the Office 365 Admin portal.</span></span>

</div>

<div>

## <a name="administrator-credentials"></a><span data-ttu-id="ee1ef-114">Credenziali di amministratore</span><span class="sxs-lookup"><span data-stu-id="ee1ef-114">Administrator Credentials</span></span>

<span data-ttu-id="ee1ef-115">Quando viene richiesto di specificare le credenziali di amministratore, usare il nome utente e la password per l'account di amministratore del tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="ee1ef-115">When you are asked to provide your administrator credentials, use the username and password for the administrator account for your Office 365 tenant.</span></span> <span data-ttu-id="ee1ef-116">Queste credenziali verranno usate anche quando si configurano Active Directory Federation Services (AD FS) 2,0, la sincronizzazione della directory, Single Sign-on, Federation e lo spostamento di utenti in Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ee1ef-116">You will also use these credentials when you configure Active Directory Federation Services (AD FS) 2.0, Directory Synchronization, Single sign-on, federation, and moving users to Lync Online.</span></span>

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a><span data-ttu-id="ee1ef-117">Connessione a PowerShell di Lync Online</span><span class="sxs-lookup"><span data-stu-id="ee1ef-117">Connecting to Lync Online PowerShell</span></span>

<span data-ttu-id="ee1ef-118">Gli amministratori hanno ora la possibilità di usare Windows PowerShell per gestire Lync Online e gli account utente di Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ee1ef-118">Administrators now have the ability to use Windows PowerShell to manage Lync Online and their Lync Online user accounts.</span></span> <span data-ttu-id="ee1ef-119">A tale scopo, è necessario prima di tutto scaricare e installare il modulo di Lync Online Connector dall'area downloadhttp://go.microsoft.com/fwlink/?LinkId=294688)Microsoft (.</span><span class="sxs-lookup"><span data-stu-id="ee1ef-119">To do this, you must first download and install the Lync Online Connector Module from the Microsoft Download Center (http://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="ee1ef-120">Per altre informazioni su come scaricare, installare e usare il modulo di Lync Online Connector e per informazioni dettagliate sull'uso di Windows PowerShell per la gestione di Lync Online, vedere [uso di Windows PowerShell per gestire Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="ee1ef-120">For more information on downloading, installing, and using the Lync Online Connector Module, and for detailed information on using Windows PowerShell to manage Lync Online, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

