---
title: 'Lync Server 2013: creare un dial plan'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a dial plan
ms:assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398909(v=OCS.15)
ms:contentKeyID: 48185424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1d4647f374fd65c0be52da111b7ef2d41c0faae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dial-plan-in-lync-server-2013"></a>Creare un dial plan in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-10-24_

Per creare un nuovo piano di chiamata, eseguire i passaggi descritti nella procedura seguente. Se si vuole modificare un dial plan, vedere [modificare un dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

<div>

## <a name="to-create-a-dial-plan"></a>Per creare un dial plan

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **routing vocale** e quindi su **dial plan**.

4.  Nella pagina **dial plan** fare clic su **nuovo** e selezionare un ambito per il dial plan:
    
      - Il **dial plan di sito** si applica a un intero sito, eccetto gli utenti o i gruppi assegnati a un dial plan utente. Se si seleziona **sito** per l'ambito di un dial plan, è necessario scegliere il sito nella finestra di dialogo **Seleziona sito** . Se è già stato creato un dial plan per un sito, il sito non viene visualizzato nella finestra di dialogo **Seleziona sito** .
    
      - Il **dial plan per pool** può essere applicato a un gateway PSTN (Public Switched Telephone Network) o a un registrar. Se si seleziona **pool** per l'ambito di un dial plan, scegliere il gateway PSTN o il registrar nella finestra di dialogo **Seleziona servizio** . Se è già stato creato un dial plan per un servizio (gateway PSTN o registrar), il servizio non viene visualizzato nell'elenco.
    
      - Il **dial plan utente** può essere applicato agli utenti o ai gruppi specificati.
    
    <div>
    

    > [!NOTE]  
    > Dopo aver selezionato l'ambito del dial plan, non è possibile modificarlo.

    
    </div>

5.  Se si sta creando un piano di chiamata utente, immettere un nome descrittivo nel campo **nome** della finestra di dialogo **nuovo piano di chiamata** . Dopo aver salvato questo nome, non è possibile modificarlo.
    
    <div>
    

    > [!NOTE]  
    > Per i piani di chiamata del sito, il campo <STRONG>nome</STRONG> viene precompilato con il nome del sito e non può essere modificato.<BR>Per i piani di chiamata in pool, il campo <STRONG>nome</STRONG> viene prepopolato con il gateway PSTN o il nome del registrar e non può essere modificato.

    
    </div>

6.  Il campo **nome semplice** viene prepopolato con lo stesso nome visualizzato nel campo **nome** . Facoltativamente, è possibile modificare questo campo per specificare un nome più descrittivo che rispecchi il sito, il servizio o l'utente a cui si applica il dial plan.
    
    <div>
    

    > [!IMPORTANT]  
    > Il <STRONG>nome semplice</STRONG> deve essere univoco tra tutti i dial plan all'interno della distribuzione di Lync Server. Non può superare i caratteri Unicode di 256, ognuno dei quali può essere un carattere alfabetico o numerico, un trattino (-), un punto (.) o uno stato di sottolineatura (_).<BR>I caratteri <STRONG>non supportati</STRONG> includono spazi e caratteri riservati come definito in RFC 3966http://www.ietf.org/rfc/rfc3966.txt)(. I caratteri riservati <STRONG>non supportati</STRONG> nel <STRONG>nome semplice</STRONG> includono i seguenti:<BR>";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","

    
    </div>

7.  Opzionale Nel campo **Descrizione** è possibile digitare ulteriori informazioni descrittive sul dial plan.

8.  Opzionale Se si vuole usare questo dial plan come area geografica per i numeri di accesso esterno, specificare un' **area di conferenza telefonica con chiamata in**ingresso. Se non si vuole usare questo dial plan per i numeri di accesso esterno, lascia vuoto questo campo.
    
    <div>
    

    > [!NOTE]  
    > Le aree di conferenza telefonica con accesso esterno sono necessarie per associare i numeri per i servizi di conferenza telefonica con chiamata in ingresso con uno o più piani di chiamata.

    
    </div>

9.  Opzionale Nel campo **prefisso di accesso esterno** specificare un valore solo se gli utenti devono chiamare una o più cifre iniziali aggiuntive (ad esempio, 9) per ottenere una linea esterna. Puoi digitare un valore di prefisso composto da un massimo di quattro caratteri\#( \*, e 0-9).
    
    <div>
    

    > [!NOTE]  
    > Se si specifica un prefisso di accesso esterno, non è necessario creare una nuova regola di normalizzazione per includere il prefisso.

    
    </div>

10. Associare e configurare le regole di normalizzazione per il dial plan nel modo seguente:
    
      - Per scegliere una o più regole da un elenco di tutte le regole di normalizzazione disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. In **Seleziona regole di normalizzazione**evidenziare le regole da associare al dial plan e quindi fare clic su **OK**.
    
      - Per definire una nuova regola di normalizzazione e associarla al dial plan, fare clic su **nuovo**. Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Per modificare una regola di normalizzazione già associata al dial plan, evidenziare il nome della regola e fare clic su **Mostra dettagli**. Per informazioni dettagliate sulla modifica della regola, vedere [definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Per copiare una regola di normalizzazione esistente da usare come punto di partenza per la definizione di una nuova regola, evidenziare il nome della regola e fare clic su **copia**e quindi su **Incolla**. Per informazioni dettagliate sulla modifica della copia, vedere [definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Per rimuovere una regola di normalizzazione dal dial plan, evidenziare il nome della regola e fare clic su **Rimuovi**.
    
    <div>
    

    > [!NOTE]  
    > Ogni dial plan deve avere almeno una regola di normalizzazione associata. Per informazioni su come determinare tutte le regole di normalizzazione richieste da un dial plan, vedere <A href="lync-server-2013-dial-plans-and-normalization-rules.md">dial plan e regole di normalizzazione in Lync Server 2013</A> nella documentazione relativa alla pianificazione.

    
    </div>

11. Verificare che le regole di normalizzazione del dial plan siano disposte nell'ordine corretto. Per modificare la posizione di una regola nell'elenco, evidenziare il nome della regola e quindi fare clic sulla freccia in su o in giù.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server attraversa l'elenco delle regole di normalizzazione dall'alto verso il basso e usa la prima regola che corrisponde al numero selezionato. Se si configura un dial plan in modo che un numero composto possa corrispondere a più regole di normalizzazione, verificare che le regole più restrittive siano ordinate sopra quelle meno restrittive.<BR>L'impostazione predefinita <STRONG>Mantieni tutte</STRONG> le regole di normalizzazione <STRONG>^ ({11}\d) $</STRONG> corrisponde a qualsiasi numero di 11 cifre. Ad esempio, se si aggiunge una regola di normalizzazione che corrisponde a numeri di 11 cifre che iniziano con 1425, assicurarsi che <STRONG>Keep all</STRONG> sia ordinato sotto la regola più restrittiva <STRONG>^ (1425{7}\ d) $</STRONG> .

    
    </div>

12. Opzionale Immettere un numero per testare il dial plan e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **immettere un numero da testare**.
    
    <div>
    

    > [!NOTE]  
    > È possibile salvare un dial plan che non supera ancora il test e quindi riconfigurarlo in un secondo momento. Per informazioni dettagliate, vedere <A href="lync-server-2013-test-voice-routing.md">eseguire il test del routing vocale in Lync Server 2013</A>.

    
    </div>

13. Fare clic su **OK**.

14. Nella pagina **dial plan** fare clic su **commit**e quindi su **Commit all**.
    
    <div>
    

    > [!NOTE]  
    > Ogni volta che si crea un dial plan, è necessario eseguire il comando <STRONG>Commit all</STRONG> per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A> nella documentazione Operations.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Modificare un dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Pubblicare le modifiche in sospeso nella configurazione di routing vocale in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

