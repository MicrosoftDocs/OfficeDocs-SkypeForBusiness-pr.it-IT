---
title: Framework di sicurezza per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: In questa sezione viene fornita una panoramica degli elementi fondamentali che formano il Framework di sicurezza per Skype for Business Server. Comprendere il modo in cui questi elementi interagiscono è essenziale per prendere decisioni informate sulla protezione della distribuzione di Skype for Business Server in particolare.
ms.openlocfilehash: 94d2ffac30e029ab6631557a69d6da3ec108657f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832096"
---
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="617b5-104">Framework di sicurezza per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="617b5-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="617b5-105">In questa sezione viene fornita una panoramica degli elementi fondamentali che formano il Framework di sicurezza per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="617b5-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="617b5-106">Comprendere il modo in cui questi elementi interagiscono è essenziale per prendere decisioni informate sulla protezione della distribuzione di Skype for Business Server in particolare.</span><span class="sxs-lookup"><span data-stu-id="617b5-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="617b5-107">Gli elementi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="617b5-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="617b5-108">Servizi di dominio Active Directory (AD-DS) fornisce un singolo archivio back-end attendibile per gli account utente e le risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="617b5-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="617b5-109">Role-Based controllo di accesso (RBAC) consente di delegare le attività amministrative mantenendo standard elevati per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="617b5-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="617b5-110">L'infrastruttura a chiave pubblica (PKI) utilizza i certificati emessi da autorità di certificazione (CAs) attendibili per autenticare i server e garantire l'integrità dei dati.</span><span class="sxs-lookup"><span data-stu-id="617b5-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="617b5-p103">Transport Layer Security (TLS), HTTPS su SSL (HTTPS) e Mutual TLS (MTLS) consentono l'autenticazione degli endpoint e la crittografia della messaggistica istantanea. I flussi di condivisione di audio, video e applicazioni punto a punto sono crittografati mediante Secure Real-Time Transport Protocol (SRTP).</span><span class="sxs-lookup"><span data-stu-id="617b5-p103">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="617b5-113">Protocolli standard di settore per l'autenticazione degli utenti, laddove possibile.</span><span class="sxs-lookup"><span data-stu-id="617b5-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="617b5-114">Windows PowerShell fornisce funzionalità di sicurezza abilitate per impostazione predefinita, in modo che gli utenti non possano eseguire facilmente o involontariamente script.</span><span class="sxs-lookup"><span data-stu-id="617b5-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="617b5-115">Questi elementi di sicurezza fondamentali interagiscono per definire utenti, server, connessioni e operazioni attendibili per garantire una base sicura per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="617b5-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="617b5-116">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="617b5-116">In this section</span></span>

<span data-ttu-id="617b5-117">Negli argomenti di questa sezione viene descritto il funzionamento di ognuno di questi elementi fondamentali per migliorare la sicurezza dell'infrastruttura di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="617b5-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="617b5-118">Servizi di dominio Active Directory per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="617b5-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="617b5-119">Controllo dell'accesso basato sui ruoli (RBAC) per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="617b5-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="617b5-120">Infrastruttura a chiave pubblica per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="617b5-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="617b5-121">TLS e MTLS per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="617b5-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="617b5-122">Crittografia per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="617b5-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="617b5-123">Autenticazione utente e client per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="617b5-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="617b5-124">Strumenti di gestione di Windows PowerShell e Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="617b5-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

