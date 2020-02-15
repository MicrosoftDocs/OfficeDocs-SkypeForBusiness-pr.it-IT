---
title: Pianificazione dell'autenticazione moderna (ADAL) con Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: In questo articolo viene illustrato l'autenticazione moderna (basata sulla libreria di autenticazione di Active Directory (ADAL) e OAuth 2,0).
ms.openlocfilehash: 5a51b0712f33cbafc64f87f56b4d12649bfad97e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046289"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="565ee-103">Come usare l'autenticazione moderna (ADAL) con Skype for business</span><span class="sxs-lookup"><span data-stu-id="565ee-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="565ee-104">Questo articolo introduce l'autenticazione moderna (basata sulla libreria di autenticazione di Active Directory (ADAL) e OAuth 2,0) che può essere trovata nell'aggiornamento cumulativo di marzo 2016 per Skype for business per Skype for Business Server 2015 o da Initial versione per Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="565ee-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="565ee-105">Che cos'è ADAL?</span><span class="sxs-lookup"><span data-stu-id="565ee-105">What is ADAL?</span></span>

<span data-ttu-id="565ee-106">ADAL è l'acronimo della "libreria di autenticazione di Active Directory" e, insieme a OAuth 2,0, è un fondamento dell'autenticazione moderna.</span><span class="sxs-lookup"><span data-stu-id="565ee-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="565ee-107">Questa libreria di codice è progettata per rendere le risorse protette nella directory disponibili per le applicazioni client (come Skype for business) tramite token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="565ee-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="565ee-108">ADAL funziona con OAuth 2,0 per consentire più scenari di autenticazione e autorizzazione, come l'autenticazione a più fattori (AMF) e altre forme di auth SAML.</span><span class="sxs-lookup"><span data-stu-id="565ee-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="565ee-109">Un'ampia gamma di app che fungono da client possono sfruttare l'autenticazione moderna per ottenere informazioni sulle risorse protette.</span><span class="sxs-lookup"><span data-stu-id="565ee-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="565ee-110">In Skype for Business Server, questa tecnologia viene utilizzata tra i client locali e i server locali per consentire agli utenti di disporre di un livello di autorizzazione adeguato alle risorse.</span><span class="sxs-lookup"><span data-stu-id="565ee-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="565ee-111">Le conversazioni di autenticazione moderne (basate su ADAL e OAuth 2,0) presentano alcuni elementi in comune.</span><span class="sxs-lookup"><span data-stu-id="565ee-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="565ee-112">C'è un client che effettua una richiesta per una risorsa, in questo caso, il client è Skype for business.</span><span class="sxs-lookup"><span data-stu-id="565ee-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="565ee-113">Esiste una risorsa a cui il client ha bisogno di un livello di accesso specifico e questa risorsa è protetta da un servizio directory, in questo caso la risorsa è Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="565ee-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="565ee-114">Vi è una connessione OAuth, in altre parole, una connessione dedicata all' *autorizzazione* di un utente per l'accesso a una risorsa.</span><span class="sxs-lookup"><span data-stu-id="565ee-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="565ee-115">(OAuth è conosciuto anche con il nome più descrittivo, l'autenticazione da server a server, ed è spesso abbreviato in S2S).</span><span class="sxs-lookup"><span data-stu-id="565ee-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="565ee-116">Nelle conversazioni di Skype for Business Server Modern Authentication (ADAL), Skype for Business Server comunica tramite ADFS (ADFS 3,0 in Windows Server 2012 R2).</span><span class="sxs-lookup"><span data-stu-id="565ee-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="565ee-117">L'autenticazione può essere eseguita utilizzando un altro provider di identità (IdP), ma è necessario configurare Skype for Business Server per comunicare direttamente con ADFS.</span><span class="sxs-lookup"><span data-stu-id="565ee-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="565ee-118">Se non è stato configurato ADFS per l'utilizzo con Skype for Business Server, completare l' [installazione di ADFS](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="565ee-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span></span>
  
<span data-ttu-id="565ee-119">ADAL è incluso nell'aggiornamento cumulativo di marzo 2016 per Skype for Business Server 2015 e l'aggiornamento cumulativo di marzo 2016 per Skype for business **deve** essere installato ed è necessario per una corretta configurazione.</span><span class="sxs-lookup"><span data-stu-id="565ee-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="565ee-120">Per Skype for Business Server 2019, è disponibile dalla versione iniziale del prodotto.</span><span class="sxs-lookup"><span data-stu-id="565ee-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="565ee-121">Durante la versione iniziale, l'autenticazione moderna in un ambiente locale è supportata solo se non è coinvolta una topologia di Skype mista.</span><span class="sxs-lookup"><span data-stu-id="565ee-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="565ee-122">Ad esempio, se l'ambiente è puramente Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="565ee-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="565ee-123">Questa dichiarazione può essere soggetta a modifiche.</span><span class="sxs-lookup"><span data-stu-id="565ee-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="565ee-124">È necessario scaricare un pacchetto di PowerShell che include i file con estensione ps1 con i comandi utilizzati da ADAL per una corretta configurazione.</span><span class="sxs-lookup"><span data-stu-id="565ee-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="565ee-125">Per informazioni su come implementare l'autenticazione moderna in Skype for business, fare riferimento a: [come usare l'autenticazione moderna (adal) con Skype for business](../../manage/authentication/use-adal.md)</span><span class="sxs-lookup"><span data-stu-id="565ee-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](../../manage/authentication/use-adal.md)</span></span>
