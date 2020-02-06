---
title: Framework di sicurezza per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Questa sezione offre una panoramica degli elementi fondamentali che costituiscono il Framework di sicurezza per Skype for Business Server. È essenziale comprendere il modo in cui questi elementi collaborano per prendere decisioni informate su come proteggere la distribuzione di Skype for Business Server in particolare.
ms.openlocfilehash: 432d4cda013e5bdec2613e3c9052f10b7d619302
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815614"
---
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="35209-104">Framework di sicurezza per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="35209-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="35209-105">Questa sezione offre una panoramica degli elementi fondamentali che costituiscono il Framework di sicurezza per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="35209-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="35209-106">È essenziale comprendere il modo in cui questi elementi collaborano per prendere decisioni informate su come proteggere la distribuzione di Skype for Business Server in particolare.</span><span class="sxs-lookup"><span data-stu-id="35209-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="35209-107">Questi elementi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="35209-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="35209-108">Active Directory Domain Services (AD DS) offre un unico repository back-end attendibile per gli account utente e le risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="35209-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="35209-109">Controllo di accesso basato sui ruoli (RBAC) consente di delegare le attività amministrative mantenendo standard elevati per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="35209-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="35209-110">Infrastruttura a chiave pubblica (PKI) USA i certificati emessi da autorità di certificazione (CAs) attendibili per autenticare i server e garantire l'integrità dei dati.</span><span class="sxs-lookup"><span data-stu-id="35209-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="35209-111">Transport Layer Security (TLS), HTTPS su SSL (HTTPS) e TLS reciproche (MTLS) abilitano l'autenticazione dell'endpoint e la crittografia della messaggistica istantanea (IM).</span><span class="sxs-lookup"><span data-stu-id="35209-111">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption.</span></span> <span data-ttu-id="35209-112">I flussi audio, video e di condivisione delle applicazioni Point-to-Point vengono crittografati usando il protocollo SRTP (Secure Real-Time Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="35209-112">Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="35209-113">Protocolli standard del settore per l'autenticazione dell'utente, ove possibile.</span><span class="sxs-lookup"><span data-stu-id="35209-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="35209-114">Windows PowerShell offre funzionalità di sicurezza abilitate per impostazione predefinita in modo che gli utenti non possano eseguire facilmente o inconsapevolmente gli script.</span><span class="sxs-lookup"><span data-stu-id="35209-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="35209-115">Questi elementi di sicurezza fondamentali collaborano per definire utenti, server, connessioni e operazioni attendibili per garantire un fondamento sicuro per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="35209-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="35209-116">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="35209-116">In this section</span></span>

<span data-ttu-id="35209-117">Gli argomenti di questa sezione descrivono il funzionamento di ognuno di questi elementi fondamentali per migliorare la sicurezza dell'infrastruttura di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="35209-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="35209-118">Servizi di dominio Active Directory per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="35209-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="35209-119">Controllo di accesso basato sui ruoli (RBAC) per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="35209-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="35209-120">Infrastruttura a chiave pubblica per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="35209-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="35209-121">TLS e MTLS per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="35209-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="35209-122">Crittografia per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="35209-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="35209-123">Autenticazione utente e client per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="35209-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="35209-124">Strumenti di gestione di Windows PowerShell e Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="35209-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

