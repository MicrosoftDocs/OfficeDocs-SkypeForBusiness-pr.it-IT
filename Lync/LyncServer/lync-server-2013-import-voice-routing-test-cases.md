---
title: 'Lync Server 2013: importare test case di routing vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import voice routing test cases
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48184325
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43ab26d61009683623d3c536a26c8be04a3846e1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a>Importare test case di routing vocale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

I test case consentono di testare le route vocali nell'organizzazione: è possibile definire elementi quali il numero da comporre e il dial plan e i criteri vocali da utilizzare e Lync Server 2013 può quindi verificare che, date queste condizioni, il numero fornito possa essere succes sfully essere instradato alla rete PSTN.

I test case, che possono essere creati utilizzando il pannello di controllo di Lync Server, vengono in genere salvati solo sul server in cui è stato creato ed eseguito originariamente il caso. È comunque possibile esportarli come file XML (con estensione vtest) per poi importarli in altri server. Ciò consente di eseguire gli stessi test in computer diversi in punti diversi della topologia.

<div>

## <a name="to-import-a-voice-routing-test-case"></a>Per importare un test case di routing vocale

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Routing vocale**.

4.  Scegliere **Importa test case** dal menu **Azioni**.

5.  Trovare il file del test case che si desidera importare (con estensione vtest) e quindi fare clic su **Apri**.

6.  Fare clic su **Commit** e quindi su **Salva tutto**.
    
    <div>
    

    > [!NOTE]  
    > Tutte le volte che si importa un file vtest, è necessario utilizzare il comando <STRONG>Salva tutto</STRONG> per pubblicare il test case. Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Esportare test case di routing vocale in Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

