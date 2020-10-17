---
title: "Lync Server 2013: Panoramica dell'ambiente ibrido di Lync Server"
description: "Lync Server 2013: Panoramica dell'ambiente ibrido di Lync Server."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95b0ae433dafad349d7ef9b6328e43dbc308579c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552392"
---
# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a><span data-ttu-id="1fd4c-103">Panoramica dell'ambiente ibrido di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fd4c-103">Overview of the Lync Server 2013 hybrid environment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fd4c-104">_**Ultimo argomento modificato:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="1fd4c-104">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="1fd4c-105">L'ambiente ibrido di Lync Server 2013 si riferisce a una distribuzione in cui alcuni utenti sono ospitati in Lync Server 2013 locale e ad altri utenti ospitati in Lync Online, ma gli utenti condividono lo stesso dominio, ad esempio user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1fd4c-105">Lync Server 2013 hybrid environment refers to a deployment in which there are some users homed to the on-premises Lync Server 2013 and other users homed to Lync Online, but users share the same domain, such as user@contoso.com.</span></span>

<div>

## <a name="about-this-guide"></a><span data-ttu-id="1fd4c-106">Informazioni su questa guida</span><span class="sxs-lookup"><span data-stu-id="1fd4c-106">About this Guide</span></span>

<span data-ttu-id="1fd4c-107">In questa guida vengono descritte le attività necessarie per configurare l'ambiente Lync Server 2013 per l'interoperabilità con Lync Online e quindi per spostare gli utenti dalla distribuzione locale per l'utilizzo di Lync Online.</span><span class="sxs-lookup"><span data-stu-id="1fd4c-107">This guide describes the tasks necessary to configure your Lync Server 2013 environment for interoperability with Lync Online, and then to move users from your on-premises deployment to use Lync Online.</span></span>

</div>

<div>

## <a name="prerequisites"></a><span data-ttu-id="1fd4c-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1fd4c-108">Prerequisites</span></span>

<span data-ttu-id="1fd4c-109">Per completare le attività di configurazione di una distribuzione ibrida, è necessario installare le applicazioni e le utilità seguenti.</span><span class="sxs-lookup"><span data-stu-id="1fd4c-109">You will need to have the following applications and utilities installed to complete the tasks for configuring a deployment for hybrid.</span></span> <span data-ttu-id="1fd4c-110">I programmi di installazione per questi file sono inclusi nei supporti di installazione forniti per la distribuzione, nonché nei collegamenti inclusi nell'elenco seguente.</span><span class="sxs-lookup"><span data-stu-id="1fd4c-110">The installers for these files are included on the installation media provided for your deployment, as well as at the links included in the following list.</span></span>

  - [<span data-ttu-id="1fd4c-111">Active Directory Federation Services (ADFS) 2.0</span><span class="sxs-lookup"><span data-stu-id="1fd4c-111">Active Directory Federation Services (AD FS) 2.0</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257305)

  - [<span data-ttu-id="1fd4c-112">Strumento di sincronizzazione della directory Microsoft 9,1</span><span class="sxs-lookup"><span data-stu-id="1fd4c-112">Microsoft Directory Synchronization Tool 9.1</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257307)

  - [<span data-ttu-id="1fd4c-113">Installazione di Windows PowerShell per Single Sign-on con AD FS</span><span class="sxs-lookup"><span data-stu-id="1fd4c-113">Install Windows PowerShell for single sign-on with AD FS</span></span>](https://go.microsoft.com/fwlink/p/?linkid=398710)

  - <span data-ttu-id="1fd4c-114">L'assistente per l'accesso ai Microsoft Online Services (msoidcli-7.0.msi) è incluso nel programma di installazione desktop per Microsoft 365, che può essere ottenuto dalla pagina dei download collegata dall'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1fd4c-114">Microsoft Online Services Sign-in Assistant (msoidcli-7.0.msi) is included with the Desktop Setup for Microsoft 365, which can be obtained from the Downloads page linked to from the Microsoft 365 admin center.</span></span>

</div>

<div>

## <a name="administrator-credentials"></a><span data-ttu-id="1fd4c-115">Credenziali di amministratore</span><span class="sxs-lookup"><span data-stu-id="1fd4c-115">Administrator Credentials</span></span>

<span data-ttu-id="1fd4c-116">Quando viene richiesto di fornire le credenziali di amministratore, utilizzare il nome utente e la password per l'account di amministratore per l'organizzazione Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="1fd4c-116">When you are asked to provide your administrator credentials, use the username and password for the administrator account for your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="1fd4c-117">Queste credenziali vengono utilizzate anche quando si configura Active Directory Federation Services (AD FS) 2,0, la sincronizzazione della directory, il servizio Single Sign-on, la Federazione e lo spostamento degli utenti in Lync Online.</span><span class="sxs-lookup"><span data-stu-id="1fd4c-117">You will also use these credentials when you configure Active Directory Federation Services (AD FS) 2.0, Directory Synchronization, Single sign-on, federation, and moving users to Lync Online.</span></span>

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a><span data-ttu-id="1fd4c-118">Connessione a PowerShell di Lync Online</span><span class="sxs-lookup"><span data-stu-id="1fd4c-118">Connecting to Lync Online PowerShell</span></span>

<span data-ttu-id="1fd4c-119">Gli amministratori hanno ora la possibilità di utilizzare Windows PowerShell per gestire Lync Online e gli account utente di Lync Online.</span><span class="sxs-lookup"><span data-stu-id="1fd4c-119">Administrators now have the ability to use Windows PowerShell to manage Lync Online and their Lync Online user accounts.</span></span> <span data-ttu-id="1fd4c-120">A tale scopo, è innanzitutto necessario scaricare e installare il modulo di Lync Online Connector dall'area download Microsoft ( https://go.microsoft.com/fwlink/?LinkId=294688) .</span><span class="sxs-lookup"><span data-stu-id="1fd4c-120">To do this, you must first download and install the Lync Online Connector Module from the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="1fd4c-121">Per ulteriori informazioni sul download, l'installazione e l'utilizzo del modulo di Lync Online Connector e per informazioni dettagliate sull'utilizzo di Windows PowerShell per la gestione di Lync Online, vedere [utilizzo di Windows PowerShell per gestire Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="1fd4c-121">For more information on downloading, installing, and using the Lync Online Connector Module, and for detailed information on using Windows PowerShell to manage Lync Online, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

