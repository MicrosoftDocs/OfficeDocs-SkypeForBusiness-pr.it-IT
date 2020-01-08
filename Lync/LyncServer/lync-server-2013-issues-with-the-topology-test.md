---
title: 'Lync Server 2013: problemi relativi al test della topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d416aac6460870ab14d5296bcc6c7944ecf699e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a>Problemi relativi al test della topologia in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Come il cmdlet **Test-CsTopology** , Best Practice Analyzer offre un modo per verificare che Lync Server 2013 funzioni correttamente a livello globale. Per impostazione predefinita, Best Practice Analyzer, come il cmdlet, controlla l'intera infrastruttura di Lync Server 2013, verificando che i servizi necessari siano in corso e che siano stati impostati i diritti e le autorizzazioni degli utenti appropriati per questi servizi e per l'universale gruppi di sicurezza creati durante l'installazione di Lync Server 2013.

Oltre a verificare la validità di Lync Server nel suo insieme, **Test-CsTopology** controlla anche la validità di un servizio specifico. Per informazioni dettagliate sull'uso del cmdlet per testare servizi specifici, vedere [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) nella documentazione di Lync Server Management Shell. Usare le informazioni seguenti per risolvere i problemi relativi alla topologia.

<div>


> [!NOTE]  
> A seconda della configurazione degli Edge Server e delle impostazioni di rete perimetrale correlate, incluse le impostazioni e le autorizzazioni del firewall, l'Analizzatore procedure consigliate potrebbe non essere in grado di accedere e analizzare i server perimetrali. Se si include Edge Server nella scansione e i report indicano che si è verificato un problema di accesso a Edge Server, deselezionare la casella di controllo <STRONG>Edge Server</STRONG> ed eseguire di nuovo l'analisi per evitare che il problema venga visualizzato nei report.



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a>Risoluzione dei problemi relativi alla topologia

Se il test della topologia ha rilevato problemi relativi alla topologia, questi problemi sono probabilmente causati da problemi che si sono verificati quando è stata pubblicata o abilitata la topologia.

Quando si apportano modifiche alla topologia, le modifiche hanno effetto solo quando sono state pubblicate e abilitate. Per apportare modifiche alla topologia, è necessario usare generatore di topologie. Dopo avere apportato le modifiche, è possibile pubblicarle e abilitarle usando generatore di topologie.

Quando si pubblicano le modifiche, le nuove informazioni, ad esempio un nuovo sito o un nuovo ruolo del server, vengono scritte in Central Management store. Tuttavia, questi nuovi oggetti (o appena modificati) non entrano immediatamente nella topologia. Gli oggetti si uniscono alla topologia solo quando si Abilita la topologia aggiornata. Se si seleziona l'opzione pubblica in Generatore di topologie, si verificano entrambe le operazioni seguenti: le modifiche vengono pubblicate, ovvero vengono scritte in Central Management store, quindi la nuova topologia è abilitata.

Per impostazione predefinita, i membri del gruppo RTCUniversalServerAdmins sono autorizzati a eseguire il cmdlet **Publish-CsTopology** e il cmdlet **Enable-CsTopology** . Tuttavia, se le autorizzazioni di configurazione non sono state delegate, è necessario aver effettuato l'accesso come amministratore di dominio per eseguire **Publish-CsTopology**. Per concedere a RTCUniversalServerAdmins il diritto di usare effettivamente il cmdlet **Publish-CsTopology** , è necessario eseguire il cmdlet **Grant-CsSetupPermission** in ogni contenitore di Active Directory che contiene computer che eseguono servizi Lync Server. Per assegnare a RTCUniversalServerAdmins il diritto di usare il cmdlet **Enable-CsTopology** , è necessario eseguire il cmdlet **Set-CsSetupPermission** per ogni contenitore di servizi di dominio Active Directory che contiene computer che eseguono servizi Lync Server. Tieni presente che questo si applica all'abilitazione e alla pubblicazione di una topologia usando generatore di topologie. Se non sono state delegate le autorizzazioni tramite **Set-CsSetupPermission**, solo un amministratore di dominio può abilitare e pubblicare una topologia tramite Generatore di topologia.

</div>

</div>

<span> </span>

</div>

</div>

</div>

