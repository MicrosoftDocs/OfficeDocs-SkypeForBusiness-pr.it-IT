---
title: "Lync Server 2013: configurazione di ADFS 2,0 per il supporto dell'autenticazione client"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8729ca803f3e3897aa9383f28a486229bf5ce33f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a><span data-ttu-id="92a63-102">Configurazione di AD FS 2,0 per il supporto dell'autenticazione client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92a63-102">Configuring AD FS 2.0 to support client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92a63-103">_**Ultimo argomento modificato:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="92a63-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="92a63-104">Esistono due tipi di autenticazione possibili che possono essere configurati in modo da consentire ad FS 2,0 di supportare l'autenticazione tramite smart card:</span><span class="sxs-lookup"><span data-stu-id="92a63-104">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

  - <span data-ttu-id="92a63-105">Autenticazione basata su form (moduli)</span><span class="sxs-lookup"><span data-stu-id="92a63-105">Forms-based authentication (FBA)</span></span>

  - <span data-ttu-id="92a63-106">Autenticazione del client di sicurezza layer di trasporto</span><span class="sxs-lookup"><span data-stu-id="92a63-106">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="92a63-107">Se si utilizza l'autenticazione basata su moduli, è possibile sviluppare una pagina Web che consenta agli utenti di autenticarsi usando il proprio nome utente/password o utilizzando la smart card e il PIN.</span><span class="sxs-lookup"><span data-stu-id="92a63-107">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="92a63-108">Questo argomento è dedicato all'implementazione dell'autenticazione del client per la sicurezza del layer di trasporto con AD FS 2,0.</span><span class="sxs-lookup"><span data-stu-id="92a63-108">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="92a63-109">Per ulteriori informazioni sui tipi di autenticazione AD FS 2,0, vedere AD FS 2,0: come modificare il tipo di autenticazione locale [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384)all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="92a63-109">For more information about AD FS 2.0 authentication types, see AD FS 2.0: How to Change the Local Authentication Type at [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384).</span></span>

<div>


<span data-ttu-id="92a63-110">**Per configurare ad FS 2,0 per il supporto dell'autenticazione client**</span><span class="sxs-lookup"><span data-stu-id="92a63-110">**To Configure AD FS 2.0 to Support Client Authentication**</span></span>

1.  <span data-ttu-id="92a63-111">Accedere al computer AD FS 2,0 utilizzando un account di amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="92a63-111">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="92a63-112">Avviare Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="92a63-112">Launch Windows Explorer.</span></span>

3.  <span data-ttu-id="92a63-113">Passare a C:\\Inetpub\\ADFS\\ls</span><span class="sxs-lookup"><span data-stu-id="92a63-113">Browse to C:\\inetpub\\adfs\\ls</span></span>

4.  <span data-ttu-id="92a63-114">Creare una copia di backup del file Web. config esistente.</span><span class="sxs-lookup"><span data-stu-id="92a63-114">Make a backup copy of the existing web.config file.</span></span>

5.  <span data-ttu-id="92a63-115">Aprire il file Web. config esistente utilizzando il blocco note.</span><span class="sxs-lookup"><span data-stu-id="92a63-115">Open the existing web.config file using Notepad.</span></span>

6.  <span data-ttu-id="92a63-116">Dalla barra dei menu, selezionare **modifica** , quindi selezionare **trova**.</span><span class="sxs-lookup"><span data-stu-id="92a63-116">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7.  <span data-ttu-id="92a63-117">Ricerca di \*\* \<localAuthenticationTypes\>\*\*.</span><span class="sxs-lookup"><span data-stu-id="92a63-117">Search for **\<localAuthenticationTypes\>**.</span></span>
    
    <span data-ttu-id="92a63-118">Tenere presente che sono presenti quattro tipi di autenticazione, uno per riga.</span><span class="sxs-lookup"><span data-stu-id="92a63-118">Note that there are four authentication types listed, one per line.</span></span>

8.  <span data-ttu-id="92a63-119">Spostare la riga contenente il tipo di autenticazione di TLSClient nella parte superiore dell'elenco della sezione.</span><span class="sxs-lookup"><span data-stu-id="92a63-119">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9.  <span data-ttu-id="92a63-120">Salvare e chiudere il file Web. config.</span><span class="sxs-lookup"><span data-stu-id="92a63-120">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="92a63-121">Avviare un prompt dei comandi con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="92a63-121">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="92a63-122">Riavviare IIS eseguendo il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="92a63-122">Restart IIS by running the following command:</span></span>
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

