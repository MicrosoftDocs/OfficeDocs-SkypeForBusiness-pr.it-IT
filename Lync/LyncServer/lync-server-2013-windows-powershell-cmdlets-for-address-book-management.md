---
title: 'Lync Server 2013: cmdlet di Windows PowerShell per la gestione della Rubrica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets for Address Book management
ms:assetid: 73bfa949-5628-4156-ad20-fe07a0dc6216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429708(v=OCS.15)
ms:contentKeyID: 48184512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 170936c8ca4445a7dc4e816c2300176d9b730f80
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535323"
---
# <a name="windows-powershell-cmdlets-for-address-book-services-in-lync-server-2013"></a><span data-ttu-id="4ad8c-102">Cmdlet di Windows PowerShell per i servizi della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ad8c-102">Windows PowerShell cmdlets for Address Book Services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ad8c-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4ad8c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4ad8c-104">Lync Server fornisce una serie di cmdlet dell'interfaccia della riga di comando di Windows PowerShell per la gestione e la configurazione del servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="4ad8c-104">Lync Server provides a number of Windows PowerShell command-line interface cmdlets to manage and configure the Address Book service.</span></span> <span data-ttu-id="4ad8c-105">Alcuni di questi cmdlet sono sostituzioni per i comandi di ABServer.exe utilizzati nelle versioni precedenti di Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="4ad8c-105">Some of these cmdlets are replacements for the ABServer.exe commands used in previous versions of Office Communications Server.</span></span> <span data-ttu-id="4ad8c-106">Negli argomenti seguenti sono indicati i cmdlet utilizzati per impostare, creare e recuperare informazioni sul Servizio Rubrica e la configurazione e le informazioni sui servizi Web utilizzati dal Servizio Rubrica quando i client recuperano i file e le impostazioni del Servizio Rubrica stesso.</span><span class="sxs-lookup"><span data-stu-id="4ad8c-106">In the following topics are the cmdlets that are used to set, create, and retrieve information about the Address Book service, its configuration and information about the Web services that the Address Book service uses when clients retrieve Address Book service files and settings.</span></span>

<span data-ttu-id="4ad8c-107">Tutti questi cmdlet vengono emessi tramite Lync Server Management Shell disponibile negli strumenti di Lync Server in un server o una workstation in cui sono stati installati gli strumenti di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="4ad8c-107">All of these cmdlets are issued through the Lync Server Management Shell found in the Lync Server tools on a server or workstation where the administration tools have been installed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4ad8c-108">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="4ad8c-108">In This Section</span></span>

  - [<span data-ttu-id="4ad8c-109">New-CsAddressBookConfiguration per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ad8c-109">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsAddressBookConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="4ad8c-110">Set-CsAddressBookConfiguration per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ad8c-110">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="4ad8c-111">Get-CsAddressBookConfiguration per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ad8c-111">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="4ad8c-112">Remove-CsAddressBookConfiguration per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ad8c-112">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="4ad8c-113">Test-CsAddressBookService per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ad8c-113">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookservice-for-address-book-management.md)

  - [<span data-ttu-id="4ad8c-114">Test-CsAddressBookWebQuery per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ad8c-114">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookwebquery-for-address-book-management.md)

  - [<span data-ttu-id="4ad8c-115">Update-CsAddressBook per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ad8c-115">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>](lync-server-2013-update-csaddressbook-for-address-book-management.md)

  - [<span data-ttu-id="4ad8c-116">New-CsClientPolicy per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ad8c-116">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-new-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="4ad8c-117">Set-CsClientPolicy per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ad8c-117">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="4ad8c-118">Get-CsService per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ad8c-118">Get-CsService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csservice-for-address-book-management.md)

  - [<span data-ttu-id="4ad8c-119">New-CsWebServiceConfiguration per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ad8c-119">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsWebServiceConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="4ad8c-120">Get-CsWebServiceConfiguration per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ad8c-120">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="4ad8c-121">Set-CsWebServiceConfiguration per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ad8c-121">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="4ad8c-122">Remove-CsWebServiceConfiguration per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ad8c-122">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-cswebserviceconfiguration-for-address-book-management.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="4ad8c-123">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="4ad8c-123">Related Sections</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4ad8c-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ad8c-124">See Also</span></span>


[https://go.microsoft.com/fwlink/p/?linkId=205826](https://go.microsoft.com/fwlink/p/?linkid=205826)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

