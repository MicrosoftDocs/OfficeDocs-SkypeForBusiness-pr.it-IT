---
title: 'Lync Server 2013: Creare un test case di routing vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a98e8b9400b0a268474429ad464b1aef7bbbe56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a>Creare un test case di routing vocale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-07_

<div>

## <a name="to-create-a-test-case"></a>Per creare un test case

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **routing vocale** e quindi su **Test routing vocale**.

4.  Nella pagina **test Voice routing** fare clic su **nuovo** per creare un nuovo test case.

5.  In **nome**Digitare un nome univoco per il test case.
    
    Il nome deve essere univoco tra tutti i casi di test di routing vocale nella distribuzione vocale aziendale. Può essere di lunghezza fino a 32 caratteri e può contenere caratteri alfanumerici, oltre alla barra rovesciata (\\), punto (.) o carattere di sottolineatura\_().

6.  In **numero composto da testare**Digitare il numero composto che si vuole usare per verificare la configurazione di routing specificata per il test case. In base ai criteri di dial plan, route e Voice, questo numero verrà normalizzato e visualizzato come output.

7.  Nell'elenco **dial plan** selezionare il dial plan da usare durante l'esecuzione del test. L'impostazione predefinita è il dial plan globale.

8.  Nell'elenco dei **criteri vocali** selezionare il criterio vocale da usare quando si eseguirà il test. L'impostazione predefinita è il criterio vocale globale.

9.  Nella **traduzione prevista**Digitare il numero di telefono nel formato che si prevede venga visualizzato dopo la traduzione. Questo è il valore del numero di telefono che stai testando dopo che è stato tradotto dalla prima regola di normalizzazione che corrisponde al dial plan selezionato. Quando si esegue il test case, se il numero che si sta testando non restituisce il valore nella **traduzione prevista**, il test ha esito negativo.

10. Opzionale Nell'elenco di **utilizzo PSTN previsto** , è possibile selezionare il record di utilizzo PSTN (Public Switched Telephone Network) che si prevede venga usato quando si esegue il test case, in base al piano di chiamata e al criterio vocale specificati. Se viene usato un record di utilizzo PSTN diverso, il test non riesce.

11. Opzionale Nell'elenco di **Route previsto** è possibile selezionare la route vocale che si prevede venga usata quando si esegue il test case, in base al piano di chiamata e al criterio vocale specificati. Se viene usata una route vocale diversa, il test non riesce.

12. Opzionale Fare clic su **Esegui** per eseguire il test case. I risultati vengono visualizzati nel riquadro destro della pagina.

13. Fare clic su **OK**.

14. Fare clic su **commit**e quindi su **Commit all**.
    
    <div>
    

    > [!NOTE]  
    > Ogni volta che si crea un test case di routing vocale, è necessario eseguire il comando <STRONG>commit tutti</STRONG> per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A> nella documentazione Operations.

    
    </div>
    
    Se il dial plan usato nel test normalizza i numeri di telefono che iniziano con un segno più (ad esempio + 12065551219), tale piano può causare un errore del test di routing vocale. (Il dial plan e la route vocale funzioneranno; in realtà, Test-CsDialPlan avrà successo. Tuttavia, il test di routing vocale potrebbe non riuscire.) Questo è un aspetto da ricordare durante il test delle route vocali.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Esportare test case di routing vocale in Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
[Importare test case di routing vocale in Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  


[Configurazione dei dial plan in Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Configurazione dei criteri vocali, dei record di utilizzo PSTN e delle route vocali in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

