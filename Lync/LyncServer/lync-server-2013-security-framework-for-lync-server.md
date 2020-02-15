---
title: 'Lync Server 2013: Framework di sicurezza per Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9910b4c481ea474425cae51d7fac88a217d52e1d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048877"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a><span data-ttu-id="05725-102">Framework di sicurezza per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05725-102">Security framework for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05725-103">_**Ultimo argomento modificato:** 2013-11-08_</span><span class="sxs-lookup"><span data-stu-id="05725-103">_**Topic Last Modified:** 2013-11-08_</span></span>

<span data-ttu-id="05725-104">In questa sezione viene fornita una panoramica degli elementi fondamentali che formano il Framework di sicurezza per Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05725-104">This section provides an overview of the fundamental elements that form the security framework for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="05725-105">Comprendere il modo in cui questi elementi interagiscono è essenziale per prendere decisioni informate sulla protezione di una specifica distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05725-105">Understanding how these elements work together is essential to making informed decisions about securing your particular Lync Server 2013 deployment.</span></span>

<span data-ttu-id="05725-106">Gli elementi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="05725-106">These elements are as follows:</span></span>

  - <span data-ttu-id="05725-107">Servizi di dominio Active Directory (AD-DS) fornisce un singolo archivio back-end attendibile per gli account utente e le risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="05725-107">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>

  - <span data-ttu-id="05725-108">Il controllo di accesso basato sui ruoli (RBAC) consente di delegare le attività amministrative mantenendo standard elevati per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="05725-108">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>

  - <span data-ttu-id="05725-109">L'infrastruttura a chiave pubblica (PKI) utilizza i certificati emessi da autorità di certificazione (CAs) attendibili per autenticare i server e garantire l'integrità dei dati.</span><span class="sxs-lookup"><span data-stu-id="05725-109">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>

  - <span data-ttu-id="05725-p102">Transport Layer Security (TLS), HTTPS su SSL (HTTPS) e Mutual TLS (MTLS) consentono l'autenticazione degli endpoint e la crittografia della messaggistica istantanea. I flussi di condivisione di audio, video e applicazioni punto a punto sono crittografati mediante Secure Real-Time Transport Protocol (SRTP).</span><span class="sxs-lookup"><span data-stu-id="05725-p102">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>

  - <span data-ttu-id="05725-112">Protocolli standard di settore per l'autenticazione degli utenti, laddove possibile.</span><span class="sxs-lookup"><span data-stu-id="05725-112">Industry-standard protocols for user authentication, where possible.</span></span>

  - <span data-ttu-id="05725-113">Windows PowerShell fornisce funzionalità di sicurezza abilitate per impostazione predefinita, in modo che gli utenti non possano eseguire facilmente o involontariamente script.</span><span class="sxs-lookup"><span data-stu-id="05725-113">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>

<span data-ttu-id="05725-114">Questi elementi di sicurezza fondamentali interagiscono per definire utenti, server, connessioni e operazioni attendibili per garantire una base sicura per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05725-114">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Lync Server 2013.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="05725-115">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="05725-115">In This Section</span></span>

<span data-ttu-id="05725-116">Negli argomenti di questa sezione viene descritto il funzionamento di ognuno di questi elementi fondamentali per migliorare la sicurezza dell'infrastruttura di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05725-116">The topics in this section describe how each of these fundamental elements works to enhance the security of your Lync Server infrastructure.</span></span>

  - [<span data-ttu-id="05725-117">Servizi di dominio Active Directory per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05725-117">Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [<span data-ttu-id="05725-118">Controllo dell'accesso basato sui ruoli (RBAC) per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05725-118">Role-based access control (RBAC) for Lync Server 2013</span></span>](lync-server-2013-role-based-access-control-rbac.md)

  - [<span data-ttu-id="05725-119">Infrastruttura a chiave pubblica per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05725-119">Public Key Infrastructure for Lync Server 2013</span></span>](lync-server-2013-public-key-infrastructure.md)

  - [<span data-ttu-id="05725-120">TLS e MTLS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05725-120">TLS and MTLS for Lync Server 2013</span></span>](lync-server-2013-tls-and-mtls.md)

  - [<span data-ttu-id="05725-121">Crittografia per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05725-121">Encryption for Lync Server 2013</span></span>](lync-server-2013-encryption.md)

  - [<span data-ttu-id="05725-122">Autenticazione utente e client per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05725-122">User and client authentication for Lync Server 2013</span></span>](lync-server-2013-user-and-client-authentication.md)

  - [<span data-ttu-id="05725-123">Strumenti di gestione di Windows PowerShell e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05725-123">Windows PowerShell and Lync Server 2013 management tools</span></span>](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

