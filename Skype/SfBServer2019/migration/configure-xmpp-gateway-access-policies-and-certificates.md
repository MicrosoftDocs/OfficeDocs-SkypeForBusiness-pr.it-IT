---
title: Configurare criteri di accesso e certificati del gateway XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'La Federazione XMPP definisce una distribuzione esterna basata sul protocollo XMPP (eXtensible Messaging and Presence Protocol). Una configurazione XMPP consente agli utenti di accedere agli utenti del dominio XMPP:'
ms.openlocfilehash: 8182153bf3633b2392969f5870a7d5b96471d4fb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813764"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="f5980-104">Configurare criteri di accesso e certificati del gateway XMPP</span><span class="sxs-lookup"><span data-stu-id="f5980-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="f5980-105">La Federazione XMPP definisce una distribuzione esterna basata sul protocollo XMPP (eXtensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="f5980-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="f5980-106">Una configurazione XMPP consente agli utenti di accedere agli utenti del dominio XMPP:</span><span class="sxs-lookup"><span data-stu-id="f5980-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="f5980-107">Messaggistica istantanea e presenza-persona a persona</span><span class="sxs-lookup"><span data-stu-id="f5980-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="f5980-108">Creazione di contatti federati XMPP nel client Skype for business</span><span class="sxs-lookup"><span data-stu-id="f5980-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="f5980-109">Quando si configurano i criteri per il supporto di partner federati XMPP, i criteri si applicano agli utenti di domini federati XMPP, ma non agli utenti di provider di servizi messaggistica istantanea SIP (Session Initiation Protocol) o di domini federati SIP.</span><span class="sxs-lookup"><span data-stu-id="f5980-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="f5980-110">Si configura un partner federato XMPP per ogni dominio federato XMPP in cui si vuole consentire agli utenti di aggiungere contatti e comunicare.</span><span class="sxs-lookup"><span data-stu-id="f5980-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="f5980-111">Dopo aver inserito i criteri, è necessario configurare i certificati del gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="f5980-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f5980-112">La funzionalità XMPP è deprecata in Skype for Business Server 2019, ma può essere proseguita in un server legacy in coesistenza con Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f5980-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="f5980-113">Assicurarsi di avere già distribuito il gateway XMPP (Skype for Business Server 2015/Lync Server 2013) e configurare i criteri di accesso per consentire agli utenti il gateway XMPP legacy.</span><span class="sxs-lookup"><span data-stu-id="f5980-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="f5980-114">Per informazioni dettagliate, vedere [migrazione della Federazione XMPP](migrating-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="f5980-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="f5980-115">Configurare un criterio di accesso esterno per consentire agli utenti il gateway XMPP legacy</span><span class="sxs-lookup"><span data-stu-id="f5980-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="f5980-116">Aprire il pannello di controllo di Skype for Business Server legacy.</span><span class="sxs-lookup"><span data-stu-id="f5980-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="f5980-117">Nella barra di spostamento sinistra fare clic su **Federazione e accesso esterno**, quindi fare clic su **criteri di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="f5980-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="f5980-118">Fare clic su **Nuovo** e quindi su **Criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="f5980-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="f5980-119">Immettere un nome per il criterio utente di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="f5980-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="f5980-120">Specificare una descrizione per i criteri degli utenti di Access esterni.</span><span class="sxs-lookup"><span data-stu-id="f5980-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="f5980-121">Selezionare **Abilita comunicazioni con gli utenti federati**.</span><span class="sxs-lookup"><span data-stu-id="f5980-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="f5980-122">Selezionare **Abilita comunicazioni con utenti federati XMPP**.</span><span class="sxs-lookup"><span data-stu-id="f5980-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="f5980-123">Fare clic su **conferma** per salvare le modifiche apportate ai criteri per il sito o per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f5980-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

