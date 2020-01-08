---
title: Distribuire client di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 659ec7be51358e73824c322461a3e27a163dc1bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a>Distribuire client di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

Dopo aver eseguito la migrazione degli utenti a Lync Server 2013, eseguire le operazioni seguenti:

1.  Usare il filtro della versione client nel nuovo server Lync Server 2013 per consentire l'accesso solo ai client con gli aggiornamenti più recenti installati.

2.  Se necessario, configurare le impostazioni dei criteri di gruppo necessarie per l'avvio automatico del client. Per informazioni dettagliate, vedere [configurazione dei criteri di avvio del client in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) nella documentazione relativa alla distribuzione. La configurazione di queste impostazioni è necessaria solo se si vogliono modificare i criteri di avvio dei client esistenti o se si vogliono impostare nuovi criteri di avvio del client. Se non si prevede di configurare i criteri di avvio del client oppure se si vuole che i criteri di avvio del client legacy rimangano in vigore, non è necessario eseguire alcuna azione.

3.  Configurare altri criteri utente e client per utenti o gruppi di utenti specifici utilizzando il pannello di controllo di Lync Server 2013, Lync Server 2013 Management Shell o entrambi. Per informazioni dettagliate, vedere [impostazioni nuove e modificate per Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) nella documentazione relativa alla pianificazione.

4.  Distribuire la versione più recente dei client di Lync Server 2013 insieme agli aggiornamenti cumulativi più recenti. Per informazioni dettagliate, vedere [distribuzione di client e dispositivi in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) nella documentazione relativa alla distribuzione.

5.  Opzionale Se l'organizzazione richiede la modalità di privacy avanzata della presenza di Lync Server 2013, una volta completata la migrazione, definire una regola di criteri di versione client per impedire l'accesso alle versioni precedenti del client. Abilitare quindi la modalità di privacy avanzata della presenza.
    
    <div>
    

    > [!IMPORTANT]  
    > Non abilitare la modalità di privacy avanzata della presenza di Lync 2013 finché ogni utente di un pool di server specifico non ha installato le versioni client più recenti.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

