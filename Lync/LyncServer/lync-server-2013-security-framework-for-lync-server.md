---
title: 'Lync Server 2013: Security Framework per Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17900e0ca9db8f9dbc1bf66a1bd65aff62d9dd62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a><span data-ttu-id="5654a-102">Framework di sicurezza per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5654a-102">Security framework for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5654a-103">_**Argomento Ultima modifica:** 2013-11-08_</span><span class="sxs-lookup"><span data-stu-id="5654a-103">_**Topic Last Modified:** 2013-11-08_</span></span>

<span data-ttu-id="5654a-104">Questa sezione offre una panoramica degli elementi fondamentali che costituiscono il Framework di sicurezza per Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5654a-104">This section provides an overview of the fundamental elements that form the security framework for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="5654a-105">È essenziale comprendere il modo in cui questi elementi collaborano per prendere decisioni informate sulla protezione della specifica distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5654a-105">Understanding how these elements work together is essential to making informed decisions about securing your particular Lync Server 2013 deployment.</span></span>

<span data-ttu-id="5654a-106">Questi elementi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="5654a-106">These elements are as follows:</span></span>

  - <span data-ttu-id="5654a-107">Active Directory Domain Services (AD DS) offre un unico repository back-end attendibile per gli account utente e le risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="5654a-107">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>

  - <span data-ttu-id="5654a-108">Controllo di accesso basato sui ruoli (RBAC) consente di delegare le attività amministrative mantenendo standard elevati per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5654a-108">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>

  - <span data-ttu-id="5654a-109">Infrastruttura a chiave pubblica (PKI) USA i certificati emessi da autorità di certificazione (CAs) attendibili per autenticare i server e garantire l'integrità dei dati.</span><span class="sxs-lookup"><span data-stu-id="5654a-109">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>

  - <span data-ttu-id="5654a-110">Transport Layer Security (TLS), HTTPS su SSL (HTTPS) e TLS reciproche (MTLS) abilitano l'autenticazione dell'endpoint e la crittografia della messaggistica istantanea (IM).</span><span class="sxs-lookup"><span data-stu-id="5654a-110">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption.</span></span> <span data-ttu-id="5654a-111">I flussi audio, video e di condivisione delle applicazioni Point-to-Point vengono crittografati usando il protocollo SRTP (Secure Real-Time Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="5654a-111">Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>

  - <span data-ttu-id="5654a-112">Protocolli standard del settore per l'autenticazione dell'utente, ove possibile.</span><span class="sxs-lookup"><span data-stu-id="5654a-112">Industry-standard protocols for user authentication, where possible.</span></span>

  - <span data-ttu-id="5654a-113">Windows PowerShell offre funzionalità di sicurezza abilitate per impostazione predefinita in modo che gli utenti non possano eseguire facilmente o inconsapevolmente gli script.</span><span class="sxs-lookup"><span data-stu-id="5654a-113">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>

<span data-ttu-id="5654a-114">Questi elementi di sicurezza fondamentali collaborano per definire gli utenti, i server, le connessioni e le operazioni attendibili per garantire una base sicura per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5654a-114">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Lync Server 2013.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5654a-115">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="5654a-115">In This Section</span></span>

<span data-ttu-id="5654a-116">Negli argomenti di questa sezione viene descritto il funzionamento di ognuno di questi elementi fondamentali per migliorare la sicurezza dell'infrastruttura di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5654a-116">The topics in this section describe how each of these fundamental elements works to enhance the security of your Lync Server infrastructure.</span></span>

  - [<span data-ttu-id="5654a-117">Servizi di dominio Active Directory per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5654a-117">Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [<span data-ttu-id="5654a-118">Controllo di accesso basato sui ruoli (RBAC) per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5654a-118">Role-based access control (RBAC) for Lync Server 2013</span></span>](lync-server-2013-role-based-access-control-rbac.md)

  - [<span data-ttu-id="5654a-119">Infrastruttura a chiave pubblica per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5654a-119">Public Key Infrastructure for Lync Server 2013</span></span>](lync-server-2013-public-key-infrastructure.md)

  - [<span data-ttu-id="5654a-120">TLS e MTLS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5654a-120">TLS and MTLS for Lync Server 2013</span></span>](lync-server-2013-tls-and-mtls.md)

  - [<span data-ttu-id="5654a-121">Crittografia per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5654a-121">Encryption for Lync Server 2013</span></span>](lync-server-2013-encryption.md)

  - [<span data-ttu-id="5654a-122">Autenticazione utente e client per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5654a-122">User and client authentication for Lync Server 2013</span></span>](lync-server-2013-user-and-client-authentication.md)

  - [<span data-ttu-id="5654a-123">Strumenti di gestione di Windows PowerShell e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5654a-123">Windows PowerShell and Lync Server 2013 management tools</span></span>](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

