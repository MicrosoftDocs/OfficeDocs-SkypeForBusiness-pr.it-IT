---
title: 'Lync Server 2013: problemi con il test della topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 254fb591acca4f58bf27b300d5ead3e615e026ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a>Problemi relativi al test di topologia in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

Analogamente al cmdlet **Test-CsTopology** , Best Practices Analyzer consente di verificare che Lync Server 2013 funzioni correttamente a livello globale. Per impostazione predefinita, l'Analizzatore procedure consigliate, come il cmdlet, controlla l'intera infrastruttura di Lync Server 2013, verificando che i servizi necessari siano in esecuzione e che siano stati impostati i diritti utente e le autorizzazioni appropriati per questi servizi e per l'universale gruppi di sicurezza creati quando si installa Lync Server 2013.

Oltre a verificare la validità di Lync Server nel suo complesso, **Test-CsTopology** verifica anche la validità di un servizio specifico. Per informazioni dettagliate sull'utilizzo del cmdlet per testare servizi specifici, vedere [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) nella documentazione di Lync Server Management Shell. Utilizzare le seguenti informazioni per risolvere i problemi nella topologia.

<div>


> [!NOTE]  
> A seconda della configurazione dei server perimetrali e delle relative impostazioni di rete, incluse le impostazioni e le autorizzazioni per i firewall, Best Practices Analyzer potrebbe non essere in grado di accedere ai server perimetrali e analizzarli. Se si includono server perimetrali nell'analisi, e i rapporti indicano un problema di accesso, deselezionare la casella di controllo <STRONG>Server perimetrali</STRONG> ed eseguire nuovamente la scansione per evitare che il problema compaia nei rapporti.



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a>Risoluzione dei problemi nella topologia

Se l'analisi della topologia riporta errori nella stessa, è possibile che gli errori siano stati originati da problemi occorsi al momento della pubblicazione o abilitazione della topologia.

Quando si apportano modifiche alla propria topologia, queste non saranno effettive finché non saranno pubblicate e abilitate. Per apportare modifiche alla topologia, è necessario utilizzare Generatore di topologie. Dopo aver apportato le modifiche, è possibile pubblicarle e abilitarle utilizzando Generatore di topologie.

Quando si pubblicano le modifiche, le nuove informazioni, ad esempio un nuovo sito o un nuovo ruolo del server, vengono scritte nell'archivio di gestione centrale. Tuttavia, questi nuovi oggetti (o modificati di recente) non aderiscono immediatamente alla topologia. Gli oggetti si uniscono alla topologia solo quando si Abilita la topologia aggiornata. Se si seleziona l'opzione pubblica in Generatore di topologie, vengono eseguiti entrambi i passaggi seguenti: le modifiche vengono pubblicate (ovvero vengono scritte nell'archivio di gestione centrale) e quindi viene abilitata la nuova topologia.

Per impostazione predefinita, i membri del gruppo RTCUniversalServerAdmins sono autorizzati a eseguire il cmdlet **Publish-CsTopology** e il cmdlet **Enable-CsTopology**. Se però le autorizzazioni di installazione non sono state delegate, sarà possibile eseguire **Publish-CsTopology** solo se si effettua l'accesso come amministratori di dominio. Per concedere a RTCUniversalServerAdmins il diritto di utilizzare effettivamente il cmdlet **Publish-CsTopology** , è necessario eseguire il cmdlet **Grant-CsSetupPermission** su ogni contenitore di Active Directory che contiene i computer che eseguono i servizi di Lync Server. Per concedere a RTCUniversalServerAdmins il diritto di utilizzare il cmdlet **Enable-CsTopology** , è necessario eseguire il cmdlet **Set-CsSetupPermission** su ogni contenitore di servizi di dominio Active Directory che contiene i computer che eseguono i servizi di Lync Server. Si noti che questo è valido per l'abilitazione e la pubblicazione di una topologia tramite Generatore di topologie. Se non sono state delegate le autorizzazioni tramite **Set-CsSetupPermission**, solo un amministratore di dominio può abilitare e pubblicare una topologia tramite Generatore di topologie.

</div>

</div>

<span> </span>

</div>

</div>

</div>

