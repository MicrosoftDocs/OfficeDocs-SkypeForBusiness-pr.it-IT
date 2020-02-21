---
title: 'Lync Server 2013: modificare un dial plan'
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
ms.openlocfilehash: f2c4f922565b5b3af5613de4a5e43c79cf573410
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-a-dial-plan-in-lync-server-2013"></a>Modificare un dial plan in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Per modificare un dial plan esistente, eseguire i passaggi illustrati nella procedura seguente. Se si desidera creare un nuovo dial plan, vedere [creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

<div>

## <a name="to-modify-a-dial-plan"></a>Per modificare un dial plan

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Dial plan**.

4.  Nella pagina **Dial plan** fare doppio clic sul nome di un dial plan.
    
    <div>
    

    > [!NOTE]  
    > L'ambito e il nome del dial plan sono stati impostati al momento della creazione del dial plan e non possono essere modificati.

    
    </div>

5.  (Facoltativo) In **Modifica dial plan** modificare il campo **Nome semplice**, in cui viene inserito automaticamente il nome visualizzato nel campo **Nome**, specificando un nome più descrittivo che rifletta il sito, il servizio o l'utente a cui si applica il dial plan.
    
    <div>
    

    > [!IMPORTANT]  
    > Il <STRONG>nome semplice</STRONG> deve essere univoco tra tutti i dial plan all'interno della distribuzione di Lync Server 2013. Sono supportati i caratteri alfabetici e numerici, il trattino (-), il punto (.), il segno più (+) o il carattere di sottolineatura (_).<BR>Il campo <STRONG>Nome semplice</STRONG> non supporta gli spazi.

    
    </div>

6.  (Facoltativo) Nel campo **Descrizione** digitare informazioni descrittive sul dial plan.

7.  (Facoltativo) Se si desidera utilizzare questo dial plan come area per i numeri di accesso esterno, specificare un'**Area conferenza telefonica con accesso esterno**. Se non si desidera utilizzare questo dial plan per i numeri di accesso esterno, lasciare vuoto il campo.
    
    <div>
    

    > [!NOTE]  
    > Le aree di conferenza telefonica con accesso esterno sono necessarie per associare i numeri di accesso alla conferenza telefonica con accesso esterno a uno o più dial plan.

    
    </div>

8.  (Facoltativo) Nel campo **Prefisso accesso esterno** specificare un valore solo se gli utenti devono comporre una o più cifre iniziali aggiuntive, ad esempio 9, per accedere a una linea esterna. È possibile digitare un valore di prefisso composto da un massimo di quattro caratteri (ovvero \# \*, e 0-9).
    
    <div>
    

    > [!NOTE]  
    > Se si specifica un prefisso di accesso esterno, non è necessario creare una nuova regola di normalizzazione per includerlo.

    
    </div>

9.  Associare e configurare le regole di normalizzazione per il dial plan:
    
      - Per scegliere una o più regole da un elenco di tutte le regole di normalizzazione disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**. Nella finestra di dialogo **Seleziona regole di normalizzazione** evidenziare le regole da associare al dial plan e fare clic su **OK**.
    
      - Per definire una nuova regola di normalizzazione e associarla al dial plan, fare clic su **Nuova**. Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Per modificare una regola di normalizzazione già associata al dial plan, evidenziare il nome della regola e fare clic su **Mostra dettagli**. Per informazioni dettagliate sulla modifica della regola, vedere [definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Per copiare una regola di normalizzazione esistente da utilizzare come punto di partenza per la definizione di una nuova regola, evidenziare il nome della regola e fare clic su **Copia** e quindi su **Incolla**. Per informazioni dettagliate sulla modifica della copia, vedere [definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Per rimuovere una regola di normalizzazione dal dial plan, evidenziarne il nome e fare clic su **Rimuovi**.
    
    <div>
    

    > [!NOTE]  
    > A ogni dial plan deve essere associata almeno una regola di normalizzazione. Per informazioni dettagliate su come determinare tutte le regole di normalizzazione richieste da un dial plan, vedere <A href="lync-server-2013-dial-plans-and-normalization-rules.md">dial plans and normalizzation Rules in Lync Server 2013</A> nella documentazione relativa alla pianificazione.

    
    </div>

10. Verificare che le regole di normalizzazione del dial plan siano disposte nell'ordine corretto. Per modificare la posizione di una regola nell'elenco, evidenziare il nome della regola e fare clic sulla freccia su o giù.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server attraversa l'elenco delle regole di normalizzazione dall'alto verso il basso e utilizza la prima regola che corrisponde al numero composto. Se si configura un dial plan in modo che un numero composto possa corrispondere a più regole di normalizzazione, assicurarsi che le regole più restrittive siano elencate prima di quelle meno restrittive.<BR>L'impostazione predefinita <STRONG>Mantieni tutte</STRONG> le regole di normalizzazione <STRONG>^ ({11}\d) $</STRONG> corrisponde a qualsiasi numero di 11 cifre. Se, ad esempio, si aggiunge una regola di normalizzazione che corrisponde a numeri a 11 cifre che iniziano con 1425, assicurarsi che la <STRONG>conservazione tutto</STRONG> sia ordinata al di sotto della regola più restrittiva <STRONG>^ (1425 \{7}d) $</STRONG> .

    
    </div>

11. (Facoltativo) Immettere un numero per testare il dial plan e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Numero composto da testare**.
    
    <div>
    

    > [!NOTE]  
    > È possibile salvare un dial plan che non ha superato ancora il test e quindi riconfigurarlo successivamente. Per ulteriori informazioni, vedere <A href="lync-server-2013-test-voice-routing.md">test Voice routing in Lync Server 2013</A>.

    
    </div>

12. Fare clic su **OK**.

13. Nella pagina **Dial plan** fare clic su **Commit** e quindi su **Salva tutto**.
    
    <div>
    

    > [!NOTE]  
    > Ogni volta che si crea o si modifica un dial plan, è necessario eseguire il comando <STRONG>Salva tutto</STRONG> per pubblicare la modifica apportata alla configurazione. Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

