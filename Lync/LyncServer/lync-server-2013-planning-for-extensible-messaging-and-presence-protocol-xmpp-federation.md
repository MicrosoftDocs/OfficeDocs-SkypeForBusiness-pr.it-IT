---
title: Pianificazione della Federazione del protocollo XMPP (Extensible Messaging and Presence Protocol)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for extensible messaging and presence protocol (XMPP) federation
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48184892
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77884bdca8d02a29d98a2a4c2dd116abb72d8f20
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="8e1ec-102">Pianificazione della Federazione XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e1ec-102">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e1ec-103">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="8e1ec-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="8e1ec-104">Le versioni precedenti di Lync Server e Office Communications Server fornivano un gateway XMPP (Extensible Messaging and Presence Protocol) che potrebbe essere distribuito come ruolo server separato per consentire la Federazione con le distribuzioni XMPP.</span><span class="sxs-lookup"><span data-stu-id="8e1ec-104">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="8e1ec-105">In Microsoft Lync Server 2013, la funzionalità XMPP può essere distribuita come caratteristica.</span><span class="sxs-lookup"><span data-stu-id="8e1ec-105">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="8e1ec-106">La funzionalità XMPP è installata in due parti: un proxy XMPP che viene eseguito nel server perimetrale e il gateway XMPP che viene eseguito nei Front End Server.</span><span class="sxs-lookup"><span data-stu-id="8e1ec-106">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="8e1ec-107">La distribuzione e la configurazione di XMPP sono descritte in [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) si prevede di supportare XMPP nell'organizzazione definendo le regole relative alle porte e ai protocolli del firewall, alla configurazione dei certificati e all'aggiunta di record DNS.</span><span class="sxs-lookup"><span data-stu-id="8e1ec-107">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="8e1ec-108">Negli argomenti seguenti di questa sezione vengono riepilogate le informazioni necessarie per pianificare correttamente la Federazione XMPP per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8e1ec-108">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="8e1ec-p103">La funzionalità XMPP di Lync Server 2013 è testata e supportata da Microsoft per la federazione di messaggistica istantanea con Google Talk. Per altri sistemi XMPP, contattare il fornitore di terze parti per verificare l'eventuale supporto della federazione con Lync Server 2013 e per indicazioni per la distribuzione o la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="8e1ec-p103">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8e1ec-111">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="8e1ec-111">In This Section</span></span>

  - [<span data-ttu-id="8e1ec-112">Riepilogo del certificato-federazione XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e1ec-112">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="8e1ec-113">Riepilogo delle porte-Federazione di protocollo XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e1ec-113">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="8e1ec-114">Riepilogo di DNS-Federazione di protocollo XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e1ec-114">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8e1ec-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e1ec-115">See Also</span></span>


[<span data-ttu-id="8e1ec-116">Configurazione della Federazione XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e1ec-116">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="8e1ec-117">Configurare criteri per controllare l'accesso utente federato XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e1ec-117">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[<span data-ttu-id="8e1ec-118">Gestire i partner federati XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e1ec-118">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
<span data-ttu-id="8e1ec-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8e1ec-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span></span>  
<span data-ttu-id="8e1ec-120">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8e1ec-120">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span></span>  
<span data-ttu-id="8e1ec-121">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8e1ec-121">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

