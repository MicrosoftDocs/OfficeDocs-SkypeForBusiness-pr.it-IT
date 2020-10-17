---
title: 'Lync Server 2013: verifica della replica dello schema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 483a8125969fffc0db2c8f72bca3fc5b8001d943
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527623"
---
# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a><span data-ttu-id="34b6d-102">Verifica della replica dello schema di Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34b6d-102">Verifying Active Directory schema replication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34b6d-103">_**Ultimo argomento modificato:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="34b6d-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="34b6d-104">Prima di eseguire la preparazione della foresta, verificare manualmente che la partizione dello schema sia stata replicata.</span><span class="sxs-lookup"><span data-stu-id="34b6d-104">Before you run forest preparation, manually verify that the schema partition has been replicated.</span></span>

<div>

## <a name="to-manually-verify-schema-replication"></a><span data-ttu-id="34b6d-105">Per verificare manualmente la replica dello schema</span><span class="sxs-lookup"><span data-stu-id="34b6d-105">To manually verify schema replication</span></span>

1.  <span data-ttu-id="34b6d-106">Accedere a un controller di dominio come membro del gruppo Enterprise Admins.</span><span class="sxs-lookup"><span data-stu-id="34b6d-106">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="34b6d-107">Aprire ADSI Edit. A tale scopo, fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione**, quindi **ADSI Edit**.</span><span class="sxs-lookup"><span data-stu-id="34b6d-107">Open ADSI Edit by clicking **Start**, clicking **Administrative Tools**, and then clicking **ADSI Edit**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="34b6d-108">In alternativa, è possibile eseguire <STRONG>adsiedit.msc</STRONG> dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="34b6d-108">Alternatively, you can run <STRONG>adsiedit.msc</STRONG> from the command line.</span></span>

    
    </div>

3.  <span data-ttu-id="34b6d-109">Nell'albero di Microsoft Management Console (MMC) fare clic su **ADSI Edit** se la voce non è già selezionata.</span><span class="sxs-lookup"><span data-stu-id="34b6d-109">In the Microsoft Management Console (MMC) tree, if it is not already selected, click **ADSI Edit**.</span></span>

4.  <span data-ttu-id="34b6d-110">Scegliere **Connetti a** dal menu **Azioni**.</span><span class="sxs-lookup"><span data-stu-id="34b6d-110">On the **Action** menu, click **Connect to**.</span></span>

5.  <span data-ttu-id="34b6d-111">Nella finestra di dialogo **Impostazioni connessione** selezionare **Schema** in **Selezionare un contesto dei nomi noto** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="34b6d-111">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>

6.  <span data-ttu-id="34b6d-112">Nel contenitore Schema individuare la voce CN=ms-RTC-SIP-SchemaVersion.</span><span class="sxs-lookup"><span data-stu-id="34b6d-112">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="34b6d-113">Se questo oggetto è presente e il valore dell'attributo **rangeUpper** è 1150 e il valore dell'attributo **rangeLower** è 3, lo schema è stato aggiornato e replicato correttamente.</span><span class="sxs-lookup"><span data-stu-id="34b6d-113">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="34b6d-114">Se l'oggetto non è presente o i valori degli attributi **rangeUpper** e **rangeLower** non sono quelli previsti, lo schema non è stato modificato o replicato.</span><span class="sxs-lookup"><span data-stu-id="34b6d-114">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="34b6d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34b6d-115">See Also</span></span>


[<span data-ttu-id="34b6d-116">Esecuzione della preparazione dello schema di Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34b6d-116">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)  


[<span data-ttu-id="34b6d-117">Preparazione dello schema di Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34b6d-117">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

