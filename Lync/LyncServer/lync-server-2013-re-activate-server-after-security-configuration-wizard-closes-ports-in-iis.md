---
title: Riattivare il server dopo la procedura guidata per la configurazione della sicurezza chiude le porte in IIS
description: Riattivare il server dopo la procedura guidata di configurazione della sicurezza chiude le porte in IIS.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d824845a7f89c28087a7b5d180a6ed017cb47ade
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579052"
---
# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a><span data-ttu-id="64270-103">Riattivare il server dopo la procedura guidata per la configurazione della sicurezza chiude le porte in IIS</span><span class="sxs-lookup"><span data-stu-id="64270-103">Re-activate server after Security Configuration Wizard closes ports in IIS</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64270-104">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="64270-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="64270-105">Alcuni ruoli di Lync Server 2013 eseguono servizi Web su porta Internet Information Services (IIS) 4443.</span><span class="sxs-lookup"><span data-stu-id="64270-105">Some Lync Server 2013 roles run Web Services on Internet Information Services (IIS) port 4443.</span></span> <span data-ttu-id="64270-106">Se si esegue la distribuzione guidata di Lync Server, Bootstrapper.exe oppure utilizzando il cmdlet **Enable-CsComputer** viene creata un'eccezione nel firewall e viene aperta la porta.</span><span class="sxs-lookup"><span data-stu-id="64270-106">Running the Lync Server Deployment Wizard, Bootstrapper.exe, or using the **Enable-CsComputer** cmdlet creates an exception in the firewall and opens the port.</span></span> <span data-ttu-id="64270-107">Se si esegue la configurazione guidata di sicurezza di Windows Server 2008 R2 (o altri script di protezione avanzata), la porta 4443 verrà bloccata e i client esterni non potranno contattare i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="64270-107">If you then run the Windows Server 2008 R2 Security Configuration Wizard (or other hardening scripts), port 4443 will be blocked, and external clients will not be able to contact Web Services.</span></span> <span data-ttu-id="64270-108">Per riaprire la porta è possibile modificare l'eccezione del firewall direttamente o riattivare il server.</span><span class="sxs-lookup"><span data-stu-id="64270-108">To reopen the port you can either modify the firewall exception directly or re-activate the server.</span></span>

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a><span data-ttu-id="64270-109">Per riattivare il server mediante la distribuzione guidata</span><span class="sxs-lookup"><span data-stu-id="64270-109">To re-activate the server by using the Deployment Wizard</span></span>

1.  <span data-ttu-id="64270-110">Nella pagina distribuzione guidata di Lync Server, fare clic su **Esegui** accanto a **passaggio 2: installazione o rimozione componenti di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="64270-110">On the Lync Server Deployment Wizard page, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

2.  <span data-ttu-id="64270-111">Nella pagina **Installazione componenti di Lync Server** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="64270-111">On **Setup Lync Server components** page, click **Next**.</span></span>

3.  <span data-ttu-id="64270-112">Nella pagina **Esecuzione comandi in corso**, quando lo stato dell'attività risulta completato, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="64270-112">On the **Executing Commands** page, when the task status is shown as completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="64270-113">È inoltre possibile utilizzare bootstrapper.exe o <STRONG>Enable-CsComputer</STRONG> per riattivare il server.</span><span class="sxs-lookup"><span data-stu-id="64270-113">You can also use bootstrapper.exe or <STRONG>Enable-CsComputer</STRONG> to re-activate the server.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

