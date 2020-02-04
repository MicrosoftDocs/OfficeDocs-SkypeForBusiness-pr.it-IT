---
title: 'Lync Server 2013: eseguire test di routing vocale informale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f916de228545a560c94bc45ea0a774ccc538c60
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a>Eseguire test di routing vocale informale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-08-07_

È possibile usare la finestra di dialogo **Crea informazioni per il routing vocale** per eseguire test informali prima di creare un vero e proprio test case. Quando si è soddisfatti del risultato di un test, è possibile salvarlo come test case formale.

<div>

## <a name="to-run-an-informal-voice-routing-test"></a>Per eseguire un test di routing vocale informale

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **routing vocale**e quindi fare clic su **Test routing vocale**.

4.  Nella pagina **test Voice routing** fare clic su **Crea informazioni sui casi di test per il routing vocale**.

5.  Nel campo **numero composto** Digitare il numero di telefono che si vuole usare per questo test. Questo numero verrà normalizzato e visualizzato nel campo **numero normalizzato** del riquadro **risultati** .

6.  Nell'elenco **dial plan** selezionare il dial plan da usare per testare il numero selezionato. L'impostazione predefinita è il dial plan globale.
    
    Quando si esegue il test, la prima regola di normalizzazione in questo dial plan che corrisponde al numero composto verrà visualizzata nel campo **regola di normalizzazione** del riquadro **risultati** .

7.  Nell'elenco dei **criteri vocali** selezionare il criterio vocale da usare per testare il numero selezionato. L'impostazione predefinita è il criterio vocale globale.
    
    Quando si esegue il test, il primo record di utilizzo PSTN corrispondente in questo criterio vocale verrà visualizzato nel **primo campo utilizzo PSTN** del riquadro **risultati** . Inoltre, la prima route vocale corrispondente associata a questo record di utilizzo PSTN verrà visualizzata nel campo **First Route** .

8.  Opzionale Selezionare la casella **di controllo popola da utente** se si vuole testare il numero di telefono con il criterio vocale assegnato a un determinato utente.
    
    1.  Fare clic su **Sfoglia** per visualizzare la finestra di dialogo **Seleziona utenti VoIP aziendale** .
    
    2.  Fare clic su **trova** per visualizzare l'elenco di utenti abilitati per VoIP aziendale.
    
    3.  Fare doppio clic sul nome utente di cui si vuole usare il criterio vocale assegnato per questo test. Il campo **policy** viene ora popolato con il criterio vocale assegnato all'utente selezionato.
    
    Quando si esegue il test, il primo record di utilizzo PSTN (Public Switched Telephone Network) corrispondente in questo criterio vocale verrà visualizzato nel **primo campo utilizzo PSTN** del riquadro **risultati** . Inoltre, la prima route vocale corrispondente associata a questo record di utilizzo PSTN verrà visualizzata nel campo **First Route** .

9.  Fare clic su **Esegui** per eseguire il test case. I risultati vengono visualizzati nel riquadro destro della finestra di dialogo.

10. Opzionale Fare clic su **Salva come** se si vuole salvare la configurazione di test come test case formale.
    
    1.  Nel campo **nome** della finestra di dialogo **Salva informazioni sul test case di routing vocale** digitare un nome univoco per il test case.
        
        Il nome deve essere univoco tra tutti i casi di test di routing vocale nella distribuzione vocale aziendale. Può essere di lunghezza fino a 32 caratteri e può contenere caratteri alfanumerici, oltre alla barra rovesciata (\\), punto (.) o carattere di sottolineatura\_().
    
    2.  Tieni presente che i campi rimanenti nella finestra di dialogo **Salva informazioni sul test case di routing vocale** sono di sola lettura e vengono prepopolati dalla configurazione *e* dai risultati del test informale. Verificare che questa sia la configurazione che si vuole salvare per il test case.
        
        <div>
        

        > [!NOTE]  
        > I valori dei risultati del test vengono usati per precompilare i campi nella finestra di dialogo <STRONG>Salva informazioni sul caso di test del routing vocale</STRONG> come indicato di seguito: 
        > <UL>
        > <LI>
        > <P>La <STRONG>traduzione prevista</STRONG> viene prepopolata con il valore nel campo <STRONG>numero normalizzato</STRONG> .</P>
        > <LI>
        > <P>La <STRONG>Route prevista</STRONG> viene prepopolata con il valore nel campo <STRONG>First Route</STRONG> .</P>
        > <LI>
        > <P>Il <STRONG>record di utilizzo PSTN previsto</STRONG> viene precompilato con il valore nel <STRONG>primo campo utilizzo PSTN</STRONG> .</P></LI></UL>Se non sono state trovate corrispondenze per uno di questi valori durante l'esecuzione di test, il campo corrispondente è vuoto nella finestra di dialogo <STRONG>Salva informazioni sul test case di routing vocale</STRONG> .

        
        </div>
    
    3.  Fare clic su **OK** per salvare il test case oppure fare clic su **Annulla** per tornare alla finestra di dialogo **Visualizza informazioni sul test dei casi di routing vocale** per sviluppare ulteriormente il test prima di salvarlo.

11. Fare clic su **commit**e quindi su **Commit all**.
    
    <div>
    

    > [!NOTE]  
    > Ogni volta che si crea un test case di routing vocale, è necessario eseguire il comando <STRONG>commit tutti</STRONG> per pubblicare il test case. Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A> nella documentazione Operations.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare un test case di routing vocale in Lync Server 2013](lync-server-2013-create-a-voice-routing-test-case.md)  
[Eseguire test case di routing vocale in Lync Server 2013](lync-server-2013-run-voice-routing-test-cases.md)  
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

