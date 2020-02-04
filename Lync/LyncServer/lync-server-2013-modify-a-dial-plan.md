---
title: 'Lync Server 2013: Modificare un dial plan'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a dial plan
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412797(v=OCS.15)
ms:contentKeyID: 48185099
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd4c007933eb7186e412ada1a3f4c35b241f5eff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758658"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-dial-plan-in-lync-server-2013"></a>Modificare un dial plan in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Per modificare un piano di chiamata esistente, eseguire i passaggi descritti nella procedura seguente. Se si vuole creare un nuovo piano di chiamata, vedere [creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

<div>

## <a name="to-modify-a-dial-plan"></a>Per modificare un dial plan

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **routing vocale** e quindi su **dial plan**.

4.  Nella pagina **dial plan** fare doppio clic su un nome di dial plan.
    
    <div>
    

    > [!NOTE]  
    > L'ambito e il nome del dial plan sono stati impostati quando è stato creato il dial plan. Non possono essere modificate.

    
    </div>

5.  Opzionale In **Modifica dial plan**modificare il campo **nome semplice** , che viene prepopolato con lo stesso nome visualizzato nel campo **nome** per specificare un nome più descrittivo che rispecchi il sito, il servizio o l'utente a cui si applica il dial plan.
    
    <div>
    

    > [!IMPORTANT]  
    > Il <STRONG>nome semplice</STRONG> deve essere univoco tra tutti i dial plan all'interno della distribuzione di Lync Server 2013. Non può superare i caratteri Unicode di 256, ognuno dei quali può essere un carattere alfabetico o numerico, un trattino (-), un punto (.), un segno di addizione (+) o una sottolineatura (_).<BR>Gli spazi non sono consentiti nel campo <STRONG>nome semplice</STRONG> .

    
    </div>

6.  Opzionale Nel campo **Descrizione** digitare informazioni descrittive sul dial plan.

7.  Opzionale Se si vuole usare questo dial plan come area geografica per i numeri di accesso esterno, specificare un' **area di conferenza telefonica con chiamata in**ingresso. Se non si vuole usare questo dial plan per i numeri di accesso esterno, lascia vuoto questo campo.
    
    <div>
    

    > [!NOTE]  
    > Le aree di conferenza telefonica con accesso esterno sono necessarie per associare i numeri per i servizi di conferenza telefonica con chiamata in ingresso con uno o più piani di chiamata.

    
    </div>

8.  Opzionale Nel campo **prefisso di accesso esterno** specificare un valore solo se gli utenti devono chiamare una o più cifre iniziali aggiuntive per ottenere una linea esterna, ad esempio 9. È possibile digitare un valore di prefisso composto da un massimo di quattro caratteri, \# \*ovvero, e 0-9.
    
    <div>
    

    > [!NOTE]  
    > Se si specifica un prefisso di accesso esterno, non è necessario creare una nuova regola di normalizzazione per includere il prefisso.

    
    </div>

9.  Associare e configurare le regole di normalizzazione per il dial plan:
    
      - Per scegliere una o più regole da un elenco di tutte le regole di normalizzazione disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. Nella finestra di dialogo **Seleziona regole di normalizzazione** evidenziare le regole da associare al dial plan e quindi fare clic su **OK**.
    
      - Per definire una nuova regola di normalizzazione e associarla al dial plan, fare clic su **nuovo**. Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Per modificare una regola di normalizzazione già associata al dial plan, evidenziare il nome della regola e fare clic su **Mostra dettagli**. Per informazioni dettagliate sulla modifica della regola, vedere [definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Per copiare una regola di normalizzazione esistente da usare come punto di partenza per la definizione di una nuova regola, evidenziare il nome della regola e fare clic su **copia**e quindi su **Incolla**. Per informazioni dettagliate sulla modifica della copia, vedere [definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Per rimuovere una regola di normalizzazione dal dial plan, evidenziare il nome della regola e fare clic su **Rimuovi**.
    
    <div>
    

    > [!NOTE]  
    > Ogni dial plan deve avere almeno una regola di normalizzazione associata. Per informazioni dettagliate su come determinare tutte le regole di normalizzazione richieste da un dial plan, vedere <A href="lync-server-2013-dial-plans-and-normalization-rules.md">dial plan e regole di normalizzazione in Lync Server 2013</A> nella documentazione relativa alla pianificazione.

    
    </div>

10. Verificare che le regole di normalizzazione del dial plan siano disposte nell'ordine corretto. Per modificare la posizione di una regola nell'elenco, evidenziare il nome della regola e quindi fare clic sulla freccia in su o in giù.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server attraversa l'elenco delle regole di normalizzazione dall'alto verso il basso e usa la prima regola che corrisponde al numero selezionato. Se si configura un dial plan in modo che un numero composto possa corrispondere a più regole di normalizzazione, verificare che le regole più restrittive siano ordinate sopra quelle meno restrittive.<BR>L'impostazione predefinita <STRONG>Mantieni tutte</STRONG> le regole di normalizzazione <STRONG>^ ({11}\d) $</STRONG> corrisponde a qualsiasi numero di 11 cifre. Se, ad esempio, si aggiunge una regola di normalizzazione che corrisponde a numeri di 11 cifre che iniziano con 1425, assicurarsi che <STRONG>Keep all</STRONG> sia ordinato sotto la regola più restrittiva <STRONG>^ (1425{7}\ d) $</STRONG> .

    
    </div>

11. Opzionale Immettere un numero per testare il dial plan e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **immettere un numero da testare**.
    
    <div>
    

    > [!NOTE]  
    > È possibile salvare un dial plan che non supera ancora il test e quindi riconfigurarlo in un secondo momento. Per informazioni dettagliate, vedere <A href="lync-server-2013-test-voice-routing.md">eseguire il test del routing vocale in Lync Server 2013</A>.

    
    </div>

12. Fare clic su **OK**.

13. Nella pagina **dial plan** fare clic su **commit**e quindi su **Commit all**.
    
    <div>
    

    > [!NOTE]  
    > Ogni volta che si crea o si modifica un dial plan, è necessario eseguire il comando <STRONG>Commit all</STRONG> per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A> nella documentazione Operations.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Pubblicare le modifiche in sospeso nella configurazione di routing vocale in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

