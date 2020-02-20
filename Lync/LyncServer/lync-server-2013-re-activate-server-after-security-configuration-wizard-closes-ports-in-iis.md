---
title: Riattivare il server dopo la procedura guidata per la configurazione della sicurezza chiude le porte in IIS
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
ms.openlocfilehash: 064a21e5ec5a324dedae29aab2fb83d16c49b258
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a><span data-ttu-id="0f5cd-102">Riattivare il server dopo la procedura guidata per la configurazione della sicurezza chiude le porte in IIS</span><span class="sxs-lookup"><span data-stu-id="0f5cd-102">Re-activate server after Security Configuration Wizard closes ports in IIS</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f5cd-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0f5cd-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0f5cd-104">Alcuni ruoli di Lync Server 2013 eseguono servizi Web su porta Internet Information Services (IIS) 4443.</span><span class="sxs-lookup"><span data-stu-id="0f5cd-104">Some Lync Server 2013 roles run Web Services on Internet Information Services (IIS) port 4443.</span></span> <span data-ttu-id="0f5cd-105">Se si esegue la distribuzione guidata di Lync Server, Bootstrapper. exe o utilizzando il cmdlet **Enable-CsComputer** , viene creata un'eccezione nel firewall e viene aperta la porta.</span><span class="sxs-lookup"><span data-stu-id="0f5cd-105">Running the Lync Server Deployment Wizard, Bootstrapper.exe, or using the **Enable-CsComputer** cmdlet creates an exception in the firewall and opens the port.</span></span> <span data-ttu-id="0f5cd-106">Se si esegue la configurazione guidata di sicurezza di Windows Server 2008 R2 (o altri script di protezione avanzata), la porta 4443 verrà bloccata e i client esterni non potranno contattare i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="0f5cd-106">If you then run the Windows Server 2008 R2 Security Configuration Wizard (or other hardening scripts), port 4443 will be blocked, and external clients will not be able to contact Web Services.</span></span> <span data-ttu-id="0f5cd-107">Per riaprire la porta è possibile modificare l'eccezione del firewall direttamente o riattivare il server.</span><span class="sxs-lookup"><span data-stu-id="0f5cd-107">To reopen the port you can either modify the firewall exception directly or re-activate the server.</span></span>

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a><span data-ttu-id="0f5cd-108">Per riattivare il server mediante la distribuzione guidata</span><span class="sxs-lookup"><span data-stu-id="0f5cd-108">To re-activate the server by using the Deployment Wizard</span></span>

1.  <span data-ttu-id="0f5cd-109">Nella pagina distribuzione guidata di Lync Server, fare clic su **Esegui** accanto a **passaggio 2: installazione o rimozione componenti di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0f5cd-109">On the Lync Server Deployment Wizard page, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

2.  <span data-ttu-id="0f5cd-110">Nella pagina **Installazione componenti di Lync Server** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0f5cd-110">On **Setup Lync Server components** page, click **Next**.</span></span>

3.  <span data-ttu-id="0f5cd-111">Nella pagina **Esecuzione comandi in corso**, quando lo stato dell'attività risulta completato, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="0f5cd-111">On the **Executing Commands** page, when the task status is shown as completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="0f5cd-112">È inoltre possibile utilizzare il programma di avvio automatico. exe o <STRONG>Enable-CsComputer</STRONG> per riattivare il server.</span><span class="sxs-lookup"><span data-stu-id="0f5cd-112">You can also use bootstrapper.exe or <STRONG>Enable-CsComputer</STRONG> to re-activate the server.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

