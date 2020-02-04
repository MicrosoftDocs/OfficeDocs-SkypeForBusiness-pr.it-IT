---
title: "Lync Server 2013: configurazione di ADFS 2,0 per supportare l'autenticazione del client"
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
ms.openlocfilehash: c7fe9587e85ad300a212e4a8199fa4a8a48d1877
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a><span data-ttu-id="56303-102">Configurazione di ADFS 2,0 per supportare l'autenticazione del client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56303-102">Configuring AD FS 2.0 to support client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56303-103">_**Argomento Ultima modifica:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="56303-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="56303-104">Esistono due tipi di autenticazione possibili che possono essere configurati in modo da consentire AD FS 2,0 di supportare l'autenticazione tramite smart card:</span><span class="sxs-lookup"><span data-stu-id="56303-104">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

  - <span data-ttu-id="56303-105">Autenticazione basata su moduli (FBA)</span><span class="sxs-lookup"><span data-stu-id="56303-105">Forms-based authentication (FBA)</span></span>

  - <span data-ttu-id="56303-106">Autenticazione del client di sicurezza dei livelli di trasporto</span><span class="sxs-lookup"><span data-stu-id="56303-106">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="56303-107">Usando l'autenticazione basata su moduli, puoi sviluppare una pagina Web che consente agli utenti di autenticarsi usando il loro nome utente/password o usando la loro smart card e il PIN.</span><span class="sxs-lookup"><span data-stu-id="56303-107">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="56303-108">Questo argomento illustra come implementare l'autenticazione del client di sicurezza dei livelli di trasporto con ADFS 2,0.</span><span class="sxs-lookup"><span data-stu-id="56303-108">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="56303-109">Per altre informazioni sui tipi di autenticazione di ADFS 2,0, vedere ADFS 2,0: come modificare il tipo di autenticazione locale [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384).</span><span class="sxs-lookup"><span data-stu-id="56303-109">For more information about AD FS 2.0 authentication types, see AD FS 2.0: How to Change the Local Authentication Type at [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384).</span></span>

<div>


<span data-ttu-id="56303-110">**Per configurare ADFS 2,0 per supportare l'autenticazione del client**</span><span class="sxs-lookup"><span data-stu-id="56303-110">**To Configure AD FS 2.0 to Support Client Authentication**</span></span>

1.  <span data-ttu-id="56303-111">Accedere al computer ADFS 2,0 usando un account di amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="56303-111">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="56303-112">Avviare Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="56303-112">Launch Windows Explorer.</span></span>

3.  <span data-ttu-id="56303-113">Passare a C:\\Inetpub\\ADFS\\ls</span><span class="sxs-lookup"><span data-stu-id="56303-113">Browse to C:\\inetpub\\adfs\\ls</span></span>

4.  <span data-ttu-id="56303-114">Creare una copia di backup del file Web. config esistente.</span><span class="sxs-lookup"><span data-stu-id="56303-114">Make a backup copy of the existing web.config file.</span></span>

5.  <span data-ttu-id="56303-115">Aprire il file Web. config esistente tramite il blocco note.</span><span class="sxs-lookup"><span data-stu-id="56303-115">Open the existing web.config file using Notepad.</span></span>

6.  <span data-ttu-id="56303-116">Nella barra dei menu selezionare **modifica** e quindi **trova**.</span><span class="sxs-lookup"><span data-stu-id="56303-116">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7.  <span data-ttu-id="56303-117">Cercare \*\* \<localAuthenticationTypes\>\*\*.</span><span class="sxs-lookup"><span data-stu-id="56303-117">Search for **\<localAuthenticationTypes\>**.</span></span>
    
    <span data-ttu-id="56303-118">Tieni presente che sono presenti quattro tipi di autenticazione, uno per riga.</span><span class="sxs-lookup"><span data-stu-id="56303-118">Note that there are four authentication types listed, one per line.</span></span>

8.  <span data-ttu-id="56303-119">Posizionare la linea contenente il tipo di autenticazione TLSClient nella parte superiore dell'elenco nella sezione.</span><span class="sxs-lookup"><span data-stu-id="56303-119">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9.  <span data-ttu-id="56303-120">Salvare e chiudere il file Web. config.</span><span class="sxs-lookup"><span data-stu-id="56303-120">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="56303-121">Avviare un prompt dei comandi con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="56303-121">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="56303-122">Riavviare IIS eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="56303-122">Restart IIS by running the following command:</span></span>
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

