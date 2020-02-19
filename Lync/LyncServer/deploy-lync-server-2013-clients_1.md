---
title: Distribuire i client di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 331241dea4f047928913550764c995a7c6f05260
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a>Distribuire i client di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

Dopo aver eseguito la migrazione degli utenti a Lync Server 2013, eseguire le operazioni seguenti:

1.  Utilizzare il filtro versione client nel nuovo server Lync Server 2013 per consentire l'accesso solo ai client con gli aggiornamenti più recenti installati.

2.  Se necessario, configurare le impostazioni dei Criteri di gruppo necessarie per l'avvio automatico dei client. Per informazioni dettagliate, vedere [Configuring Client bootstrap Policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) nella documentazione relativa alla distribuzione. La configurazione di queste impostazioni è necessaria solo se si desidera modificare i criteri esistenti di avvio automatico dei client oppure impostare nuovi criteri. Se non si intende configurare i criteri di avvio automatico dei client o si desidera rimangano effettivi i criteri legacy, non sarà necessaria alcuna azione.

3.  Configurare gli altri criteri utente e client per utenti o gruppi di utenti specifici utilizzando il pannello di controllo di Lync Server 2013, Lync Server 2013 Management Shell o entrambi. Per ulteriori informazioni, vedere [impostazioni nuove e modificate per Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) nella documentazione relativa alla pianificazione.

4.  Distribuire la versione più recente dei client di Lync Server 2013 insieme agli aggiornamenti cumulativi più recenti. Per informazioni dettagliate, vedere [Deploying clients and Devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) nella documentazione relativa alla distribuzione.

5.  Optional Se nell'organizzazione è necessaria la modalità privacy di Lync Server 2013 Enhanced Presence, una volta completata la migrazione, definire una regola di criteri di versione client per impedire l'accesso alle versioni precedenti dei client. Quindi, abilitare la modalità privacy della presenza avanzata.
    
    <div>
    

    > [!IMPORTANT]  
    > Non abilitare la modalità privacy di Lync 2013 Enhanced Presence finché ogni utente su un determinato pool di server non dispone delle versioni client più recenti installate.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

