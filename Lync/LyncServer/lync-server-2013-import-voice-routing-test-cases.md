---
title: 'Lync Server 2013: Importare test case di routing vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Import voice routing test cases
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48184325
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8b1aba05447904d4515df7ab6137743edb52ea7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a>Importare test case di routing vocale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

I casi di test consentono di testare le route vocali nell'organizzazione: si definiscono elementi come il numero da chiamare e il dial plan e il criterio vocale da utilizzare e Lync Server 2013 può quindi verificare che, in base a tali condizioni, il numero fornito possa essere succes sfully essere indirizzato alla rete PSTN.

I casi di test, che possono essere creati tramite il pannello di controllo di Lync Server, vengono in genere salvati solo nel server in cui è stato originariamente creato ed eseguito il caso. Tuttavia, questi test case possono essere esportati come file XML (con estensione vtest) e quindi importati in altri server. In questo modo è possibile eseguire gli stessi test in computer diversi situati in punti diversi della topologia.

<div>

## <a name="to-import-a-voice-routing-test-case"></a>Per importare un test case di routing vocale

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **routing vocale**.

4.  Nel menu **azioni** fare clic su **Importa test case**.

5.  Individuare il file del test case (con estensione vtest) che si vuole importare e quindi fare clic su **Apri**.

6.  Fare clic su **commit**e quindi su **Commit all**.
    
    <div>
    

    > [!NOTE]  
    > Ogni volta che si importa un file con estensione vtest, è necessario eseguire il comando <STRONG>Commit all</STRONG> per pubblicare il test case. Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A> nella documentazione Operations.

    
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

