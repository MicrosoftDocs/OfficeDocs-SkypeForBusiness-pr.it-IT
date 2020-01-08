---
title: Riattivare il server dopo la chiusura delle porte in IIS da parte della Configurazione guidata impostazioni di sicurezza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c939996c10c85141d3c3751ce84b0cf642007b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a><span data-ttu-id="d1625-102">Riattivare il server dopo la chiusura delle porte in IIS da parte della Configurazione guidata impostazioni di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d1625-102">Re-activate server after Security Configuration Wizard closes ports in IIS</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1625-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d1625-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d1625-104">Alcuni ruoli di Lync Server 2013 eseguono servizi Web in una porta Internet Information Services (IIS) 4443.</span><span class="sxs-lookup"><span data-stu-id="d1625-104">Some Lync Server 2013 roles run Web Services on Internet Information Services (IIS) port 4443.</span></span> <span data-ttu-id="d1625-105">Eseguendo la distribuzione guidata di Lync Server, Bootstrapper. exe oppure usando il cmdlet **Enable-CsComputer** viene creata un'eccezione nel firewall e viene aperta la porta.</span><span class="sxs-lookup"><span data-stu-id="d1625-105">Running the Lync Server Deployment Wizard, Bootstrapper.exe, or using the **Enable-CsComputer** cmdlet creates an exception in the firewall and opens the port.</span></span> <span data-ttu-id="d1625-106">Se si esegue la configurazione guidata di Windows Server 2008 R2 (o altri script di protezione avanzata), la porta 4443 verrà bloccata e i client esterni non saranno in grado di contattare i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="d1625-106">If you then run the Windows Server 2008 R2 Security Configuration Wizard (or other hardening scripts), port 4443 will be blocked, and external clients will not be able to contact Web Services.</span></span> <span data-ttu-id="d1625-107">Per riaprire la porta, è possibile modificare l'eccezione del firewall direttamente o riattivare il server.</span><span class="sxs-lookup"><span data-stu-id="d1625-107">To reopen the port you can either modify the firewall exception directly or re-activate the server.</span></span>

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a><span data-ttu-id="d1625-108">Per riattivare il server tramite la distribuzione guidata</span><span class="sxs-lookup"><span data-stu-id="d1625-108">To re-activate the server by using the Deployment Wizard</span></span>

1.  <span data-ttu-id="d1625-109">Nella pagina distribuzione guidata di Lync Server fare clic su **Esegui** accanto al **passaggio 2: configurare o rimuovere i componenti di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d1625-109">On the Lync Server Deployment Wizard page, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

2.  <span data-ttu-id="d1625-110">Nella pagina **Setup Lync Server Components** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d1625-110">On **Setup Lync Server components** page, click **Next**.</span></span>

3.  <span data-ttu-id="d1625-111">Nella pagina **esecuzione dei comandi** , quando lo stato dell'attività viene visualizzato come completato, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="d1625-111">On the **Executing Commands** page, when the task status is shown as completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d1625-112">È anche possibile usare Bootstrapper. exe o <STRONG>Enable-CsComputer</STRONG> per riattivare il server.</span><span class="sxs-lookup"><span data-stu-id="d1625-112">You can also use bootstrapper.exe or <STRONG>Enable-CsComputer</STRONG> to re-activate the server.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

