---
title: 'Lync Server 2013: impostazione delle password degli account di autenticazione Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21ed9f0b5bd8e9aecfb39a7dd9c159857d4b240e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a><span data-ttu-id="5b1de-102">Configurazione delle password degli account di autenticazione Kerberos in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b1de-102">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b1de-103">_**Ultimo argomento modificato:** 2010-11-03_</span><span class="sxs-lookup"><span data-stu-id="5b1de-103">_**Topic Last Modified:** 2010-11-03_</span></span>

<span data-ttu-id="5b1de-104">Dopo aver creato l'oggetto computer per l'account di autenticazione Kerberos, è possibile configurare la password per l'account.</span><span class="sxs-lookup"><span data-stu-id="5b1de-104">After you create the computer object for the Kerberos authentication account, you can set up the password for the account.</span></span> <span data-ttu-id="5b1de-105">È possibile eseguire il cmdlet di Windows PowerShell per impostare la password dell'account Kerberos in un server.</span><span class="sxs-lookup"><span data-stu-id="5b1de-105">You run the Windows PowerShell cmdlet for setting the Kerberos account password on one server.</span></span> <span data-ttu-id="5b1de-106">È possibile impostare la password nell'oggetto creato per l'autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="5b1de-106">You can set the password on the object that you created for the Kerberos authentication.</span></span> <span data-ttu-id="5b1de-107">La password può essere impostata su un valore noto, ma per impostazione predefinita è una password casuale.</span><span class="sxs-lookup"><span data-stu-id="5b1de-107">The password can be set to a known value, but by default is a random password.</span></span> <span data-ttu-id="5b1de-108">La password è disponibile per tutte le origini di autenticazione Kerberos che utilizzano l'account.</span><span class="sxs-lookup"><span data-stu-id="5b1de-108">The password is available to all Kerberos authentication sources that use the account.</span></span> <span data-ttu-id="5b1de-109">È possibile utilizzare i cmdlet di Windows PowerShell per configurare e gestire le password degli account Kerberos.</span><span class="sxs-lookup"><span data-stu-id="5b1de-109">You use Windows PowerShell cmdlets to set up and manage Kerberos account passwords.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5b1de-110">L'oggetto account Kerberos è un oggetto computer, ma utilizza il parametro accountutente per le operazioni nei cmdlet di Windows PowerShell a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="5b1de-110">The Kerberos account object is a computer object, but uses the UserAccount parameter for operations in the Windows PowerShell cmdlets that are referenced.</span></span> <span data-ttu-id="5b1de-111">Si noti che questo non è un errore, ma il comportamento previsto del cmdlet quando viene utilizzato con la creazione e la manutenzione di account Kerberos.</span><span class="sxs-lookup"><span data-stu-id="5b1de-111">Note that this is not a mistake, but the intended behavior of the cmdlet when used with the Kerberos account creation and maintenance.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5b1de-112">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="5b1de-112">In This Section</span></span>

  - [<span data-ttu-id="5b1de-113">Impostare la password di un account di autenticazione Kerberos in un server di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b1de-113">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [<span data-ttu-id="5b1de-114">Sincronizzare la password di un account di autenticazione Kerberos con IIS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b1de-114">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

