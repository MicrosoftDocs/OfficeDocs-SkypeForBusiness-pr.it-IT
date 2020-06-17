---
title: Configurare criteri e certificati di accesso al gateway XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'La federazione XMPP definisce una distribuzione esterna basata sul protocollo XMPP (eXtensible Messaging and Presence Protocol). Una configurazione XMPP consente agli utenti di accedere agli utenti di dominio XMPP:'
ms.openlocfilehash: f94cd3bc0a769165f6ffe8ecabea8b7f48a1ff07
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753936"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="55a91-104">Configurare criteri e certificati di accesso al gateway XMPP</span><span class="sxs-lookup"><span data-stu-id="55a91-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="55a91-105">La federazione XMPP definisce una distribuzione esterna basata sul protocollo XMPP (eXtensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="55a91-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="55a91-106">Una configurazione XMPP consente agli utenti di accedere agli utenti di dominio XMPP:</span><span class="sxs-lookup"><span data-stu-id="55a91-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="55a91-107">Messaggistica istantanea e presenza-solo persona a persona</span><span class="sxs-lookup"><span data-stu-id="55a91-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="55a91-108">Creazione di contatti federati XMPP nel client Skype for business</span><span class="sxs-lookup"><span data-stu-id="55a91-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="55a91-109">Quando si configurano i criteri per il supporto di partner federati XMPP, i criteri vengono applicati agli utenti di domini federati XMPP, ma non agli utenti di provider di servizi di messaggistica istantanea SIP (Session Initiation Protocol) o di domini federati SIP.</span><span class="sxs-lookup"><span data-stu-id="55a91-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="55a91-110">È possibile configurare un partner federato XMPP per ogni dominio federato XMPP che si desidera consentire agli utenti di aggiungere contatti e comunicare con.</span><span class="sxs-lookup"><span data-stu-id="55a91-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="55a91-111">Dopo aver configurato i criteri, è necessario configurare i certificati del gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="55a91-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="55a91-112">La funzionalità XMPP è obsoleta in Skype for Business Server 2019, ma può essere continuata in un server legacy in coesistenza con Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="55a91-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="55a91-113">Assicurarsi di aver già distribuito il gateway XMPP del server legacy (Skype for Business Server 2015/Lync Server 2013) e aver configurato i criteri di accesso per abilitare gli utenti per il gateway XMPP legacy.</span><span class="sxs-lookup"><span data-stu-id="55a91-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="55a91-114">Per informazioni dettagliate, vedere [migrazione della Federazione XMPP](migrating-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="55a91-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="55a91-115">Configurare un criterio di accesso esterno per abilitare gli utenti per il gateway XMPP legacy</span><span class="sxs-lookup"><span data-stu-id="55a91-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="55a91-116">Aprire il pannello di controllo di Skype for Business Server legacy.</span><span class="sxs-lookup"><span data-stu-id="55a91-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="55a91-117">Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Criteri di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="55a91-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="55a91-118">Fare clic su **Nuovo** e quindi su **Criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="55a91-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="55a91-119">Immettere un nome per l'impostazione dei criteri utente di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="55a91-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="55a91-120">Specificare una descrizione per l'impostazione dei criteri utente di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="55a91-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="55a91-121">Selezionare **Abilita comunicazioni con utenti federati**.</span><span class="sxs-lookup"><span data-stu-id="55a91-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="55a91-122">Selezionare **Abilita le comunicazioni con gli utenti federati XMPP**.</span><span class="sxs-lookup"><span data-stu-id="55a91-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="55a91-123">Fare clic su **Commit** per salvare le modifiche apportate ai criteri utente o sito.</span><span class="sxs-lookup"><span data-stu-id="55a91-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

