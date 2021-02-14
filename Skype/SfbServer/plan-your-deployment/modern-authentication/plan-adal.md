---
title: Pianificazione dell'autenticazione moderna (ADAL) con Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Questo articolo spiega cos'è l'autenticazione moderna (basata su Active Directory Authentication Library (ADAL) e OAuth 2.0.
ms.openlocfilehash: bd5d172fe4589cbd28c5b22507ad8603695ed62f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816226"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="1cbf2-103">Come usare l'autenticazione moderna (ADAL) con Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1cbf2-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="1cbf2-104">Questo articolo introduce l'autenticazione moderna (basata su Active Directory Authentication Library (ADAL) e OAuth 2.0, disponibile nell'aggiornamento cumulativo di marzo 2016 per Skype for Business per Skype for Business Server 2015 o dalla versione iniziale per Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1cbf2-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="1cbf2-105">Che cos'è ADAL?</span><span class="sxs-lookup"><span data-stu-id="1cbf2-105">What is ADAL?</span></span>

<span data-ttu-id="1cbf2-106">ADAL è l'acronimo di "Active Directory Authentication Library" e, insieme a OAuth 2.0, è alla base dell'autenticazione moderna.</span><span class="sxs-lookup"><span data-stu-id="1cbf2-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="1cbf2-107">Questa libreria di codice è progettata per rendere le risorse protette nella directory disponibili per le applicazioni client (come Skype for Business) tramite token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1cbf2-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="1cbf2-108">ADAL funziona con OAuth 2.0 per abilitare più scenari di autenticazione e autorizzazione, come l'autenticazione a più fattori (MFA) e più forme di autenticazione SAML.</span><span class="sxs-lookup"><span data-stu-id="1cbf2-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="1cbf2-109">Un'ampia gamma di app che fungono da client può sfruttare l'autenticazione moderna per ottenere risorse protette.</span><span class="sxs-lookup"><span data-stu-id="1cbf2-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="1cbf2-110">In Skype for Business Server, questa tecnologia viene utilizzata tra i client locali e i server locali per fornire agli utenti un livello appropriato di autorizzazione per le risorse.</span><span class="sxs-lookup"><span data-stu-id="1cbf2-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="1cbf2-111">Le conversazioni con autenticazione moderna (basate su ADAL e OAuth 2.0) hanno alcuni elementi in comune.</span><span class="sxs-lookup"><span data-stu-id="1cbf2-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="1cbf2-112">C'è un client che effettua una richiesta per una risorsa, in questo caso, il client è Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="1cbf2-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="1cbf2-113">Esiste una risorsa a cui il client necessita di un livello di accesso specifico e questa risorsa è protetta da un servizio directory, in questo caso la risorsa è Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1cbf2-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="1cbf2-114">Esiste una connessione OAuth, in altre parole, una connessione dedicata all'autorizzazione  *di*  un utente ad accedere a una risorsa.</span><span class="sxs-lookup"><span data-stu-id="1cbf2-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="1cbf2-115">OAuth è anche noto con il nome più descrittivo, l'autenticazione "Da server a server" e spesso è abbreviato come S2S.</span><span class="sxs-lookup"><span data-stu-id="1cbf2-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="1cbf2-116">Nelle conversazioni di Skype for Business Server Modern Authentication (ADAL), Skype for Business Server comunica tramite ADFS (ADFS 3.0 in Windows Server 2012 R2).</span><span class="sxs-lookup"><span data-stu-id="1cbf2-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="1cbf2-117">L'autenticazione può avvenire utilizzando un altro provider di identità (IdP), ma il server Skype for Business deve essere configurato per comunicare direttamente con ADFS.</span><span class="sxs-lookup"><span data-stu-id="1cbf2-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="1cbf2-118">Se ADFS non è stato configurato per l'utilizzo con Skype for Business Server, completare [l'installazione di ADFS.](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1cbf2-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span></span>
  
<span data-ttu-id="1cbf2-119">ADAL è incluso nell'aggiornamento cumulativo di marzo 2016 per Skype for Business Server 2015 e l'aggiornamento cumulativo di marzo 2016 per Skype for **Business** deve essere installato ed è necessario per la corretta configurazione.</span><span class="sxs-lookup"><span data-stu-id="1cbf2-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="1cbf2-120">Per Skype for Business Server 2019, è disponibile dalla versione iniziale del prodotto.</span><span class="sxs-lookup"><span data-stu-id="1cbf2-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1cbf2-121">Durante la versione iniziale, l'autenticazione moderna in un ambiente locale è supportata solo se non è coinvolta una topologia di Skype mista.</span><span class="sxs-lookup"><span data-stu-id="1cbf2-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="1cbf2-122">Ad esempio, se l'ambiente è esclusivamente Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1cbf2-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="1cbf2-123">Questa dichiarazione può essere soggetta a modifiche.</span><span class="sxs-lookup"><span data-stu-id="1cbf2-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="1cbf2-124">Per una corretta configurazione, è necessario scaricare un pacchetto di PowerShell che include i file ps1 con i comandi utilizzati da ADAL.</span><span class="sxs-lookup"><span data-stu-id="1cbf2-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="1cbf2-125">Per informazioni su come implementare l'autenticazione moderna in Skype for Business, vedere: Come usare l'autenticazione [moderna (ADAL) con Skype for Business](../../manage/authentication/use-adal.md)</span><span class="sxs-lookup"><span data-stu-id="1cbf2-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](../../manage/authentication/use-adal.md)</span></span>
