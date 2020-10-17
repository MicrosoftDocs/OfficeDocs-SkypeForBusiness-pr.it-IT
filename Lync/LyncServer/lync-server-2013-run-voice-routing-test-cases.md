---
title: 'Lync Server 2013: esecuzione dei test case di routing vocale'
description: 'Lync Server 2013: eseguire i test case di routing vocale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e521216a12fba6b78913e7f4a79432809bb6e252
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566792"
---
# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a>Eseguire test case di routing vocale in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-24_

È possibile eseguire tutti i test case nel gruppo di test case di routing vocale oppure è possibile eseguire uno o più test case selezionati.

<div>

## <a name="to-run-all-voice-routing-test-cases"></a>Per eseguire tutti i test case di routing vocale

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Test routing vocale**.

4.  Nella pagina **Test routing vocale** fare clic su **azione** e quindi su **Esegui tutto**.
    
    Lo stato superato o non superato di ogni test case viene visualizzato nella colonna **pass/fail** . Se un test case non è ancora stato eseguito, nella colonna **pass/fail** viene visualizzato N/a.

5.  Optional Per visualizzare i risultati dettagliati per ogni test case, fare doppio clic sul nome del test case. I risultati vengono visualizzati nell'area ombreggiata a destra della pagina **modifica test case** :
    
    1.  **Risultato del test:** Stato globale superato o non superato dell'esecuzione del test case.
    
    2.  **Regola di normalizzazione:** La prima regola di normalizzazione nel dial plan selezionato per questo test case che corrisponde al numero composto, ovvero il valore nel campo **numero da testare** .
    
    3.  **Numero normalizzato:** Il valore del numero composto dopo che la regola di normalizzazione lo ha convertito.
    
    4.  **Primo utilizzo PSTN:** Il primo record di utilizzo PSTN (Public Switched Telephone Network) nel criterio vocale selezionato per questo test case che corrisponde al numero composto.
    
    5.  **Prima route:** La prima route vocale del primo record di utilizzo PSTN che corrisponde al numero composto.
        
        <div>
        

        > [!NOTE]  
        > Il <STRONG>record di utilizzo PSTN previsto</STRONG> e i campi <STRONG>Route previsti</STRONG> sono facoltativi nella configurazione del test case di routing vocale. Se il test case non specifica questi valori, il campo corrispondente nei risultati dei test sarà vuoto.

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a>Per eseguire uno o più test case di routing vocale selezionati

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Test routing vocale**.

4.  Nella pagina **Test routing vocale** fare clic sui nomi dei test case che si desidera eseguire.

5.  Scegliere **Esegui selezionato**dal menu **azione** .
    
    Lo stato superato o non superato di ogni test case viene visualizzato nella colonna **pass/fail** . Se un test case non è ancora stato eseguito, nella colonna **pass/fail** viene visualizzato N/a.

6.  Optional Per visualizzare i risultati dettagliati per ogni test case, fare doppio clic sul nome del test case. I risultati vengono visualizzati nell'area ombreggiata a destra della pagina **modifica test case** :
    
    1.  **Risultato del test:** Stato globale superato o non superato dell'esecuzione del test case.
    
    2.  **Regola di normalizzazione:** La prima regola di normalizzazione nel dial plan selezionato per questo test case che corrisponde al numero composto, ovvero il valore nel campo **numero da testare** .
    
    3.  **Numero normalizzato:** Il valore del numero composto dopo che la regola di normalizzazione lo ha convertito.
    
    4.  **Primo utilizzo PSTN:** Il primo record di utilizzo PSTN del criterio vocale selezionato per questo test case che corrisponde al numero composto.
    
    5.  **Prima route:** La prima route vocale del primo record di utilizzo PSTN che corrisponde al numero composto.
        
        <div>
        

        > [!NOTE]  
        > Il <STRONG>record di utilizzo PSTN previsto</STRONG> e i campi <STRONG>Route previsti</STRONG> sono facoltativi nella configurazione del test case di routing vocale. Se il test case non specifica questi valori, il campo corrispondente nei risultati dei test sarà vuoto.

        
        </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Testare il routing vocale in Lync Server 2013](lync-server-2013-test-voice-routing.md)  
[Esecuzione di test del routing vocale in Lync Server 2013](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

