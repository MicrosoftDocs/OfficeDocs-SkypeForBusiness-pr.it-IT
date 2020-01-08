---
title: 'Lync Server 2013: Configurazione delle password degli account di autenticazione Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06ca8bf5d1b3dc90b1ceacbe581e0426b5c0aaa9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a><span data-ttu-id="3c809-102">Configurazione delle password degli account di autenticazione Kerberos in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c809-102">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c809-103">_**Argomento Ultima modifica:** 2010-11-03_</span><span class="sxs-lookup"><span data-stu-id="3c809-103">_**Topic Last Modified:** 2010-11-03_</span></span>

<span data-ttu-id="3c809-104">Dopo aver creato l'oggetto computer per l'account di autenticazione Kerberos, è possibile configurare la password per l'account.</span><span class="sxs-lookup"><span data-stu-id="3c809-104">After you create the computer object for the Kerberos authentication account, you can set up the password for the account.</span></span> <span data-ttu-id="3c809-105">Si esegue il cmdlet di Windows PowerShell per impostare la password dell'account Kerberos in un server.</span><span class="sxs-lookup"><span data-stu-id="3c809-105">You run the Windows PowerShell cmdlet for setting the Kerberos account password on one server.</span></span> <span data-ttu-id="3c809-106">Puoi impostare la password per l'oggetto creato per l'autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="3c809-106">You can set the password on the object that you created for the Kerberos authentication.</span></span> <span data-ttu-id="3c809-107">La password può essere impostata su un valore noto, ma per impostazione predefinita è una password casuale.</span><span class="sxs-lookup"><span data-stu-id="3c809-107">The password can be set to a known value, but by default is a random password.</span></span> <span data-ttu-id="3c809-108">La password è disponibile per tutte le origini di autenticazione Kerberos che usano l'account.</span><span class="sxs-lookup"><span data-stu-id="3c809-108">The password is available to all Kerberos authentication sources that use the account.</span></span> <span data-ttu-id="3c809-109">Puoi usare i cmdlet di Windows PowerShell per configurare e gestire le password degli account Kerberos.</span><span class="sxs-lookup"><span data-stu-id="3c809-109">You use Windows PowerShell cmdlets to set up and manage Kerberos account passwords.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3c809-110">L'oggetto account Kerberos è un oggetto computer, ma usa il parametro UserAccount per le operazioni nei cmdlet di Windows PowerShell a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="3c809-110">The Kerberos account object is a computer object, but uses the UserAccount parameter for operations in the Windows PowerShell cmdlets that are referenced.</span></span> <span data-ttu-id="3c809-111">Tieni presente che non si tratta di un errore, ma del comportamento previsto del cmdlet quando viene usato con la creazione e la manutenzione dell'account Kerberos.</span><span class="sxs-lookup"><span data-stu-id="3c809-111">Note that this is not a mistake, but the intended behavior of the cmdlet when used with the Kerberos account creation and maintenance.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3c809-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3c809-112">In This Section</span></span>

  - [<span data-ttu-id="3c809-113">Impostare la password di un account di autenticazione Kerberos in un server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c809-113">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [<span data-ttu-id="3c809-114">Sincronizzare la password di un account di autenticazione Kerberos con IIS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c809-114">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

