---
title: Configurare criteri di accesso e certificati del gateway XMPP
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
ms.openlocfilehash: 5b1aab41b1a9af8c7b8df888dcb3a0c8621fa44e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="40cee-102">Configurare criteri di accesso e certificati del gateway XMPP</span><span class="sxs-lookup"><span data-stu-id="40cee-102">Configure XMPP gateway access policies and certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40cee-103">_**Argomento Ultima modifica:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="40cee-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="40cee-104">La Federazione XMPP definisce una distribuzione esterna basata sul protocollo XMPP (eXtensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="40cee-104">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="40cee-105">Una configurazione XMPP consente agli utenti di Lync di accedere agli utenti del dominio XMPP:</span><span class="sxs-lookup"><span data-stu-id="40cee-105">An XMPP configuration allows Lync users access to XMPP domain users by:</span></span>

  - <span data-ttu-id="40cee-106">Messaggistica istantanea e presenza: solo persona a persona</span><span class="sxs-lookup"><span data-stu-id="40cee-106">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="40cee-107">Creazione di contatti federati XMPP nel client Lync</span><span class="sxs-lookup"><span data-stu-id="40cee-107">Creation of XMPP federated contacts in the Lync client</span></span>

<span data-ttu-id="40cee-108">Quando si configurano i criteri per il supporto dei partner federati di Extensible Messaging and Presence Protocol (XMPP), i criteri si applicano agli utenti di domini federati XMPP, ma non agli utenti dei provider di servizi di messaggistica istantanea SIP (Session Initiation Protocol) (ad esempio, Windows Live) o i domini federati SIP.</span><span class="sxs-lookup"><span data-stu-id="40cee-108">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="40cee-109">Si configura un partner federato XMPP per ogni dominio federato XMPP in cui si vuole consentire agli utenti di aggiungere contatti e comunicare.</span><span class="sxs-lookup"><span data-stu-id="40cee-109">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="40cee-110">Dopo aver inserito i criteri, è necessario configurare i certificati del gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="40cee-110">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="40cee-111">Per avviare la migrazione del gateway XMPP, è necessario distribuire il gateway XMPP di Lync Server 2013 e configurare i criteri di accesso per consentire agli utenti il gateway XMPP di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40cee-111">To begin the XMPP Gateway migration, you need to deploy the Lync Server 2013 XMPP Gateway, and configure access policies to enable users for Lync Server 2013 XMPP Gateway.</span></span> <span data-ttu-id="40cee-112">Prima di eseguire questa procedura, tutti gli utenti devono essere spostati nella distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40cee-112">All users must be moved to the Lync Server 2013 deployment before you perform these steps.</span></span> <span data-ttu-id="40cee-113">Per informazioni dettagliate, vedere <A href="configure-xmpp-gateway-on-lync-server-2013.md">configurare il gateway XMPP in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="40cee-113">For details, see <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configure XMPP gateway on Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="40cee-114">Configurare un criterio di accesso esterno per consentire agli utenti il gateway XMPP di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40cee-114">Configure an External Access Policy to Enable Users for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="40cee-115">Aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="40cee-115">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="40cee-116">Nella barra di spostamento sinistra fare clic su **Federazione e accesso esterno**, quindi fare clic su **criteri di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="40cee-116">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>

3.  <span data-ttu-id="40cee-117">Fare clic su **nuovo** e quindi su **criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="40cee-117">Click **New** and then click **User policy**.</span></span>

4.  <span data-ttu-id="40cee-118">Immettere un nome per il criterio utente di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="40cee-118">Enter a name for the external access user policy.</span></span>

5.  <span data-ttu-id="40cee-119">Specificare una descrizione per i criteri degli utenti di Access esterni.</span><span class="sxs-lookup"><span data-stu-id="40cee-119">Provide a description for external access user policy.</span></span>

6.  <span data-ttu-id="40cee-120">Selezionare **Abilita comunicazioni con gli utenti federati**.</span><span class="sxs-lookup"><span data-stu-id="40cee-120">Select **Enable communications with federated users**.</span></span>

7.  <span data-ttu-id="40cee-121">Selezionare **Abilita comunicazioni con utenti federati XMPP**.</span><span class="sxs-lookup"><span data-stu-id="40cee-121">Select **Enable communications with XMPP federated users**.</span></span>

8.  <span data-ttu-id="40cee-122">Fare clic su **conferma** per salvare le modifiche apportate ai criteri per il sito o per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="40cee-122">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

