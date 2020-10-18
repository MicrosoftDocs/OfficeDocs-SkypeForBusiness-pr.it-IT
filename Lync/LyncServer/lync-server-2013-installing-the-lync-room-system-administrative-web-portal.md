---
title: 'Lync Server 2013: installazione del portale Web amministrativo di Lync room System'
description: 'Lync Server 2013: installazione del portale Web amministrativo di Lync room System.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fba239346d75142bb4009c58e0ac67e8e1f3bcb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573872"
---
# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="2112a-103">Installazione del portale Web amministrativo di Lync room System in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2112a-103">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2112a-104">_**Ultimo argomento modificato:** 2015-04-09_</span><span class="sxs-lookup"><span data-stu-id="2112a-104">_**Topic Last Modified:** 2015-04-09_</span></span>

<span data-ttu-id="2112a-105">È possibile scaricare il portale Web amministrativo Microsoft Lync room System dall'area download Microsoft all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=324044](https://go.microsoft.com/fwlink/p/?linkid=324044) .</span><span class="sxs-lookup"><span data-stu-id="2112a-105">You can download the Microsoft Lync Room System Administrative Web Portal from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=324044](https://go.microsoft.com/fwlink/p/?linkid=324044).</span></span>

<span data-ttu-id="2112a-106">Per installare il portale Web amministrativo di Lync room System, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="2112a-106">To install the Lync Room System Administrative Web Portal, use the following steps.</span></span>

1.  <span data-ttu-id="2112a-107">Configurare la porta dell'applicazione attendibile eseguendo il cmdlet seguente in Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="2112a-107">Configure the Trusted Application Port by running the following cmdlet in Lync Server Management Shell:</span></span>
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  <span data-ttu-id="2112a-108">Per installare il portale della sala riunioni, scaricare **LyncRoomAdminPortal.exe** e quindi eseguirlo come amministratore.</span><span class="sxs-lookup"><span data-stu-id="2112a-108">To install the Meeting Room Portal, download **LyncRoomAdminPortal.exe** and then run it as an administrator.</span></span>

3.  <span data-ttu-id="2112a-109">Aprire il file Web.config dal percorso seguente:</span><span class="sxs-lookup"><span data-stu-id="2112a-109">Open the Web.config file from the following location:</span></span>
    
    <span data-ttu-id="2112a-110">% Program Files% \\ Microsoft Lync Server 2013 \\ Web Components \\ sala riunioni Portal \\ int \\ handler</span><span class="sxs-lookup"><span data-stu-id="2112a-110">%Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler</span></span>\\

4.  <span data-ttu-id="2112a-111">Nel file Web.Config cambiare PortalUserName con il nome utente creato nel passaggio 2 nella sezione "configurazione dei prerequisiti per il portale di amministrazione di Lync room System" (il nome consigliato nel passaggio è LRSApp):</span><span class="sxs-lookup"><span data-stu-id="2112a-111">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section “Configuring Prerequisites for Lync Room System Admin Portal” (the recommended name in the step is LRSApp):</span></span>
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  <span data-ttu-id="2112a-112">Poiché il portale di amministrazione di LRS è un'applicazione attendibile, non è necessario fornire la password nella configurazione del portale.</span><span class="sxs-lookup"><span data-stu-id="2112a-112">Because the LRS Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="2112a-113">Se l'utente utilizza un registrar diverso da quello locale, è necessario specificare il registrar per il servizio di registrazione aggiungendo la riga seguente nel file Web.Config:</span><span class="sxs-lookup"><span data-stu-id="2112a-113">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  <span data-ttu-id="2112a-114">Se la porta utilizzata è diversa da 5061, aggiungere la riga seguente nel file Web.Config:</span><span class="sxs-lookup"><span data-stu-id="2112a-114">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="2112a-115">Verifica dell'installazione del portale Web amministrativo di Lync room System</span><span class="sxs-lookup"><span data-stu-id="2112a-115">Verifying Installation of the Lync Room System Administrative Web Portal</span></span>

<span data-ttu-id="2112a-116">Per verificare l'installazione del portale Web amministrativo di Lync room System, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2112a-116">To verify installation of the Lync Room System Administrative Web Portal, do the following:</span></span>


1.  <span data-ttu-id="2112a-117">In un front end Server passare all'URL seguente:</span><span class="sxs-lookup"><span data-stu-id="2112a-117">On a Front End server, browse to the following URL:</span></span>
    
    <span data-ttu-id="2112a-118">https:// \<fe-server\> /LRS</span><span class="sxs-lookup"><span data-stu-id="2112a-118">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="2112a-119">Non è possibile visualizzare errori, come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="2112a-119">You should not see any errors, as shown in the following image:</span></span>
    
    <span data-ttu-id="2112a-120">![Schermata di accesso al portale di amministrazione di Lync room System](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Schermata di accesso al portale di amministrazione di Lync room System")</span><span class="sxs-lookup"><span data-stu-id="2112a-120">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

2.  <span data-ttu-id="2112a-121">Se non vengono visualizzati errori, provare a accedere all'URL seguente da qualsiasi altro computer della topologia:</span><span class="sxs-lookup"><span data-stu-id="2112a-121">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>
    
    <span data-ttu-id="2112a-122">https:// \<fe-server\> /LRS</span><span class="sxs-lookup"><span data-stu-id="2112a-122">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="2112a-123">Per accedere alla pagina, è necessario aggiungere i record DNS come descritto nella sezione "record DNS necessari per l'accesso automatico dei client" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=318056](https://go.microsoft.com/fwlink/p/?linkid=318056) .</span><span class="sxs-lookup"><span data-stu-id="2112a-123">To access the page, you will need to add the DNS records as described in “Required DNS Records for Automatic Client Sign-In” at [https://go.microsoft.com/fwlink/p/?LinkId=318056](https://go.microsoft.com/fwlink/p/?linkid=318056).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

