---
title: Configurare i certificati e i criteri di accesso del gateway XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: fac02f4e-d14d-4be3-b53c-74c82436fd93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721945(v=OCS.15)
ms:contentKeyID: 49733882
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e785b3f3df2e37bc7cdaaaccdb2e027652a0da36
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="038bf-102">Configurare i certificati e i criteri di accesso del gateway XMPP</span><span class="sxs-lookup"><span data-stu-id="038bf-102">Configure XMPP gateway access policies and certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="038bf-103">_**Ultimo argomento modificato:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="038bf-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="038bf-p101">La federazione XMPP definisce una distribuzione esterna basata sul protocollo XMPP (eXtensible Messaging and Presence Protocol). Una configurazione XMPP consente agli utenti di Lync di comunicare con gli utenti di domini XMPP mediante:</span><span class="sxs-lookup"><span data-stu-id="038bf-p101">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP). An XMPP configuration allows Lync users access to XMPP domain users by:</span></span>

  - <span data-ttu-id="038bf-106">Messaggistica istantanea e informazioni sulla presenza: solo da persona a persona.</span><span class="sxs-lookup"><span data-stu-id="038bf-106">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="038bf-107">Creazione di contatti federati XMPP nel client Lync.</span><span class="sxs-lookup"><span data-stu-id="038bf-107">Creation of XMPP federated contacts in the Lync client</span></span>

<span data-ttu-id="038bf-p102">Quando si configurano i criteri per il supporto di partner federati XMPP, tali criteri si applicano agli utenti di domini federati XMPP, ma non agli utenti di provider di servizi di messaggistica istantanea SIP (Session Initiation Protocol), ad esempio Windows Live, o di domini federati SIP. Configurare un partner federato XMPP per ogni dominio federato XMPP di cui si desidera consentire agli utenti di aggiungere contatti e con cui possono comunicare. Dopo aver configurato i criteri, è necessario configurare i certificati del gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="038bf-p102">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains. You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with. Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="038bf-111">Per avviare la migrazione del gateway XMPP, è necessario distribuire il gateway XMPP di Lync Server 2013 e configurare i criteri di accesso per abilitare gli utenti per il gateway XMPP di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="038bf-111">To begin the XMPP Gateway migration, you need to deploy the Lync Server 2013 XMPP Gateway, and configure access policies to enable users for Lync Server 2013 XMPP Gateway.</span></span> <span data-ttu-id="038bf-112">Prima di eseguire questa procedura, è necessario spostare tutti gli utenti nella distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="038bf-112">All users must be moved to the Lync Server 2013 deployment before you perform these steps.</span></span> <span data-ttu-id="038bf-113">Per ulteriori informazioni, vedere <A href="configure-xmpp-gateway-on-lync-server-2013.md">configurare il gateway XMPP in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="038bf-113">For details, see <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configure XMPP gateway on Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="038bf-114">Configurare criteri di accesso esterno in modo da abilitare gli utenti per il gateway XMPP di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="038bf-114">Configure an External Access Policy to Enable Users for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="038bf-115">Aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="038bf-115">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="038bf-116">Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Criteri di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="038bf-116">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>

3.  <span data-ttu-id="038bf-117">Fare clic su **Nuovo** e quindi su **Criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="038bf-117">Click **New** and then click **User policy**.</span></span>

4.  <span data-ttu-id="038bf-118">Immettere un nome per l'impostazione dei criteri utente di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="038bf-118">Enter a name for the external access user policy.</span></span>

5.  <span data-ttu-id="038bf-119">Specificare una descrizione per l'impostazione dei criteri utente di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="038bf-119">Provide a description for external access user policy.</span></span>

6.  <span data-ttu-id="038bf-120">Selezionare **Abilita comunicazioni con utenti federati**.</span><span class="sxs-lookup"><span data-stu-id="038bf-120">Select **Enable communications with federated users**.</span></span>

7.  <span data-ttu-id="038bf-121">Selezionare **Abilita le comunicazioni con gli utenti federati XMPP**.</span><span class="sxs-lookup"><span data-stu-id="038bf-121">Select **Enable communications with XMPP federated users**.</span></span>

8.  <span data-ttu-id="038bf-122">Fare clic su **Commit** per salvare le modifiche apportate ai criteri utente o sito.</span><span class="sxs-lookup"><span data-stu-id="038bf-122">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

