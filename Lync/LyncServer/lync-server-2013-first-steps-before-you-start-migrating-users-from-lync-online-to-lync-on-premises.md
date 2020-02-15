---
title: 'Lync Server 2013: primi passaggi prima di avviare la migrazione degli utenti da Lync Online a Lync in locale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: First steps before you start migrating users from Lync Online to Lync on-premises
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62258123
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bf61b4e2f3e3a14d5e2434ff80bd5d6f612f267
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="2e554-102">Primi passaggi prima di avviare la migrazione degli utenti da Lync Online a Lync locale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e554-102">First steps before you start migrating users from Lync Online to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e554-103">_**Ultimo argomento modificato:** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="2e554-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="2e554-104">Prima di avviare lo spostamento degli utenti di Lync Online nell'ambiente locale, verificare che siano soddisfatte tutte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2e554-104">Before you start moving Lync Online users to your on-premises environment, check that all of the following are true:</span></span>

  - <span data-ttu-id="2e554-105">L'ambiente locale di Lync Server deve essere completamente distribuito e convalidato.</span><span class="sxs-lookup"><span data-stu-id="2e554-105">Your Lync Server on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="2e554-106">Per ulteriori informazioni, vedere [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="2e554-106">For more information, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md).</span></span>

  - <span data-ttu-id="2e554-107">Il tenant di Lync Online deve essere configurato per l'accesso a Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e554-107">Your Lync Online tenant must be configured for remote PowerShell Access.</span></span>
    
    <span data-ttu-id="2e554-108">A tale scopo, installare innanzitutto il modulo di Lync Online per Windows PowerShell, che è possibile ottenere qui [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911):.</span><span class="sxs-lookup"><span data-stu-id="2e554-108">To do this, first install the Lync Online module for Windows PowerShell, which you can get here: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>
    
    <span data-ttu-id="2e554-109">Dopo aver installato il modulo, è possibile stabilire una sessione remota digitando i seguenti cmdlet in Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="2e554-109">After you install the module, you can establish a remote session by typing the following cmdlets in the Lync Server Management Shell:</span></span>
    
       ```PowerShell
        Import-Module LyncOnlineConnector
       ```  
    
       ```PowerShell
        $cred = Get-Credential
       ``` 
    
       ```PowerShell
        $CSSession = New-CsOnlineSession -Credential $cred
       ```
    
       ```PowerShell
        Import-PSSession $CSSession -AllowClobber
       ```
    
    <span data-ttu-id="2e554-110">Per ulteriori informazioni su come stabilire una sessione remota di PowerShell con Lync Online, vedere [connessione a Lync Online tramite Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="2e554-110">For more information about how to establish a remote PowerShell session with Lync Online, see [Connecting to Lync Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
    <span data-ttu-id="2e554-111">Per ulteriori informazioni sull'utilizzo del modulo di Lync Online PowerShell, vedere [using Windows PowerShell to Manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="2e554-111">For more information about using the Lync Online PowerShell module, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

  - <span data-ttu-id="2e554-112">Lync Online deve essere configurato per lo spazio di indirizzi SIP condiviso.</span><span class="sxs-lookup"><span data-stu-id="2e554-112">Your Lync Online must be configured for Shared SIP Address Space.</span></span> <span data-ttu-id="2e554-113">A tale scopo, avviare innanzitutto una sessione remota di PowerShell con Lync Online.</span><span class="sxs-lookup"><span data-stu-id="2e554-113">To do this, first start a remote Powershell session with Lync Online.</span></span> <span data-ttu-id="2e554-114">Eseguire quindi il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="2e554-114">Then run the following cmdlet:</span></span>
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

<span data-ttu-id="2e554-115">Dopo aver completato questi passaggi, è possibile passare alla [migrazione degli utenti di Lync Online a Lync in locale in Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="2e554-115">After you’ve finished these steps, you can move on to [Migrating Lync Online users to Lync on-premises in Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

