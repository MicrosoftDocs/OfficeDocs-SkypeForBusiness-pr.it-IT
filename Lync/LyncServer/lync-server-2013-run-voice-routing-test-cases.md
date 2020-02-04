---
title: 'Lync Server 2013: esecuzione di test case di routing vocale'
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
ms.openlocfilehash: 14f2df8a04c5efbf8c62bc4e17bbdd156913daae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a>Eseguire test case di routing vocale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-24_

È possibile eseguire tutti i test case nella famiglia di test case con routing vocale oppure eseguire uno o più test case selezionati.

<div>

## <a name="to-run-all-voice-routing-test-cases"></a>Per eseguire tutti i test case di routing vocale

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **routing vocale** e quindi su **Test routing vocale**.

4.  Nella pagina **test Voice routing** fare clic su **azione** e quindi su **Esegui tutto**.
    
    Lo stato superato o non superato di ogni test case viene visualizzato nella colonna **pass/fail** . Se un test case non è ancora stato eseguito, nella colonna **pass/fail** viene visualizzato N/d.

5.  Opzionale Per visualizzare i risultati dettagliati per ogni test case, fare doppio clic sul nome del test case. I risultati vengono visualizzati nell'area ombreggiata sul lato destro della pagina **modifica test case** :
    
    1.  **Risultato del test:** Stato globale superato o non superato dell'esecuzione del test case.
    
    2.  **Regola di normalizzazione:** La prima regola di normalizzazione nel dial plan selezionato per questo test case che corrisponde al numero composto (il valore nel campo **numero da testare** ).
    
    3.  **Numero normalizzato:** Il valore del numero composto dopo che la regola di normalizzazione lo ha tradotto.
    
    4.  **Primo utilizzo PSTN:** Il primo record di utilizzo PSTN (Public Switched Telephone Network) nel criterio vocale selezionato per questo test case che corrisponde al numero composto.
    
    5.  **Prima route:** La prima route vocale nel primo record di utilizzo PSTN che corrisponde al numero selezionato.
        
        <div>
        

        > [!NOTE]  
        > Il <STRONG>record di utilizzo PSTN previsto</STRONG> e i campi <STRONG>Route previsti</STRONG> sono facoltativi nella configurazione dei test dei casi di routing vocale. Se il test case non specifica questi valori, il campo corrispondente nei risultati del test sarà vuoto.

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a>Per eseguire uno o più casi di test di routing vocale selezionati

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **routing vocale**e quindi fare clic su **Test routing vocale**.

4.  Nella pagina **test Voice routing** fare clic sui nomi dei test case che si desidera eseguire.

5.  Nel menu **azione** fare clic su **Esegui selezionato**.
    
    Lo stato superato o non superato di ogni test case viene visualizzato nella colonna **pass/fail** . Se un test case non è ancora stato eseguito, nella colonna **pass/fail** viene visualizzato N/d.

6.  Opzionale Per visualizzare i risultati dettagliati per ogni test case, fare doppio clic sul nome del test case. I risultati vengono visualizzati nell'area ombreggiata sul lato destro della pagina **modifica test case** :
    
    1.  **Risultato del test:** Stato globale superato o non superato dell'esecuzione del test case.
    
    2.  **Regola di normalizzazione:** La prima regola di normalizzazione nel dial plan selezionato per questo test case che corrisponde al numero composto (il valore nel campo **numero da testare** ).
    
    3.  **Numero normalizzato:** Il valore del numero composto dopo che la regola di normalizzazione lo ha tradotto.
    
    4.  **Primo utilizzo PSTN:** Il primo record di utilizzo PSTN nel criterio vocale selezionato per questo test case che corrisponde al numero composto.
    
    5.  **Prima route:** La prima route vocale nel primo record di utilizzo PSTN che corrisponde al numero selezionato.
        
        <div>
        

        > [!NOTE]  
        > Il <STRONG>record di utilizzo PSTN previsto</STRONG> e i campi <STRONG>Route previsti</STRONG> sono facoltativi nella configurazione dei test dei casi di routing vocale. Se il test case non specifica questi valori, il campo corrispondente nei risultati del test sarà vuoto.

        
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

