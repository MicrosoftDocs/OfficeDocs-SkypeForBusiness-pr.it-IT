---
title: 'Lync Server 2013: creare i criteri di routing VoIP per gli utenti di succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cc958e5f643a18c45989d5835fd786c001899db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a>Creare i criteri di routing VoIP per gli utenti di succursale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-23_

È consigliabile creare un criterio VoIP (Voice Over IP) distinto per gli utenti dei siti derivati. Questo criterio deve contenere route per l'uscita dal gateway Survivable Branch Appliance o il gateway esterno Survivable Branch Server e le route di backup per l'uscita da un gateway nel sito centrale. Indipendentemente dalla posizione in cui l'utente è registrato, sia nel registrar del Survivable Branch Appliance o Survivable Branch Server o nel cluster di registrazione di backup nel sito centrale, i criteri VoIP dell'utente sono sempre attivi.

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a>Per configurare i criteri di routing VoIP per gli utenti dei siti di succursale

1.  Creare un dial plan a livello utente e assegnarlo agli utenti dei siti di succursale. Per ulteriori informazioni, vedere [creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) nella documentazione relativa alle operazioni.

2.  Assegnare regole di normalizzazione corrispondenti alle abitudini degli utenti del sito in relazione alla composizione dei numeri di telefono. Se l'utente Survivable Branch Appliance o Survivable Branch Server non riesce a eseguire il failover del pool di registrazione di backup nel sito centrale, lo stesso dial plan sarà attivo. Per ulteriori informazioni, vedere [creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) nella documentazione relativa alle operazioni.

3.  Configurare una route vocale che egresses dal gateway Survivable Branch Appliance o dal gateway esterno Survivable Branch Server. Per ulteriori informazioni, vedere [creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md) nella documentazione relativa alle operazioni.

4.  Impostare una route di chiamata di backup nel Survivable Branch Appliance o Survivable Branch Server gateway in modo che punti al pool di registrazione di backup (collocato con Mediation Server) nel sito centrale. Vedere la documentazione relativa a Survivable Branch Appliance o Survivable Branch Server vendor.
    
    <div>
    

    > [!NOTE]  
    > Questa configurazione del percorso di chiamata di backup consente di garantire che le chiamate in ingresso all'utente di succursale funzionino quando il Survivable Branch Appliance o il Survivable Branch Server non è disponibile, ad esempio se è inattivo per la manutenzione. Se il servizio di registrazione e Mediation Server nel Survivable Branch Appliance o Survivable Branch Server non sono disponibili e l'utente è registrato con il pool di registrazione di backup nel sito centrale, le chiamate in entrata possono comunque essere instradate all'utente.

    
    </div>

**Passaggio successivo**: [configurare le impostazioni di reinstradamento della segreteria telefonica in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

