---
title: 'Lync Server 2013: Creare i criteri di routing VoIP per gli utenti di succursali'
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
ms.openlocfilehash: d1cc8f0a6c4d960b4dacf6f62f283d806a6dd6f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a>Creare i criteri di routing VoIP per gli utenti di succursali in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-23_

È consigliabile creare un criterio Voice over IP (VoIP) separato per gli utenti nei siti di succursale. Questo criterio deve contenere route per l'uscita dal gateway Survivable Branch Appliance o dal gateway esterno Survivable Branch Server e dalle route di backup per l'uscita da un gateway nel sito centrale. Indipendentemente dalla posizione in cui l'utente è registrato, nel registrar di Survivable Branch Appliance o Survivable Branch Server o nel cluster di registrazione del backup nel sito centrale, i criteri VoIP dell'utente sono sempre effettivi.

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a>Per configurare i criteri di routing VoIP per gli utenti di Branch

1.  Creare un dial plan a livello utente e assegnarlo agli utenti di Branch. Vedere [creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) nella documentazione Operations.

2.  Assegnare regole di normalizzazione corrispondenti alle abitudini di chiamata degli utenti in tale sito. Se il Survivable Branch Appliance o Survivable Branch Server utente non riesce più al pool di registrazione di backup presso il sito centrale, lo stesso dial plan sarà attivo. Vedere [creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) nella documentazione Operations.

3.  Configura una route vocale che egresses dal gateway Survivable Branch Appliance o dal gateway esterno Survivable Branch Server. Vedere [creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md) nella documentazione delle operazioni.

4.  Impostare una route di chiamata di backup nel gateway Survivable Branch Appliance o Survivable Branch Server in modo che punti al pool di registrar di backup (collocato con Mediation Server) nel sito centrale. Vedere la documentazione del fornitore Survivable Branch Appliance o Survivable Branch Server.
    
    <div>
    

    > [!NOTE]  
    > Questa configurazione della route delle chiamate di backup consente di verificare che le chiamate in ingresso all'utente della filiale funzionino quando il Survivable Branch Appliance o Survivable Branch Server non è disponibile, ad esempio se è in calo per la manutenzione. Se il registrar e Mediation Server in Survivable Branch Appliance o Survivable Branch Server non sono disponibili e l'utente è registrato con il pool di registrar di backup nel sito centrale, le chiamate in ingresso possono comunque essere indirizzate all'utente.

    
    </div>

**Passaggio successivo**: [configurare le impostazioni per la reinstradazione della segreteria telefonica in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

