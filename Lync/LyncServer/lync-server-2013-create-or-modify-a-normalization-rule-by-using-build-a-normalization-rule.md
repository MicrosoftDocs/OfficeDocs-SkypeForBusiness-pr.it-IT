---
title: Creare o modificare una regola di normalizzazione utilizzando crea una regola di normalizzazione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 138fe6b55f82b451fee12d4159e147f73160c741
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a>Creare o modificare una regola di normalizzazione utilizzando crea una regola di normalizzazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Se si desidera creare o modificare una regola di normalizzazione nel pannello di controllo di Lync Server, eseguire la procedura seguente. In alternativa, se si desidera creare o modificare manualmente una regola di normalizzazione, vedere [creare o modificare manualmente una regola di normalizzazione in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a>Per definire una regola mediante Crea regola di normalizzazione

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Optional Seguire la procedura illustrata in [creare un dial plan in Lync server 2013](lync-server-2013-create-a-dial-plan.md) tramite il passaggio 11 o [modificare un dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) tramite il passaggio 10.

4.  In **Nuova regola di normalizzazione** o **Modifica regola di normalizzazione** digitare un nome descrittivo del formato del numero da normalizzare in **Nome**, ad esempio **Prefisso5Cifre**.

5.  (Facoltativo) In **Descrizione** digitare una descrizione della regola di normalizzazione, ad esempio "Converte prefissi a 5 cifre".

6.  In **Crea regola di normalizzazione** immettere valori nei campi seguenti:
    
      - **Cifre iniziali (**   facoltativo) specificare le cifre iniziali dei numeri composti che si desidera che il modello corrisponda. Digitare ad esempio **425** se si desidera che il formato corrisponda ai numeri composti che iniziano con 425.
    
      - **Lunghezza**   specificare il numero di cifre nel criterio di corrispondenza e selezionare se si desidera che il motivo corrisponda esattamente a questa lunghezza, corrispondere ai numeri composti almeno per questa lunghezza o corrispondere a numeri composti di qualsiasi lunghezza.
    
      - **Cifre da rimuovere**   (facoltativa) specificare il numero di cifre iniziali che devono essere rimosse dai numeri composti che si desidera che il modello corrisponda.
    
      - **Cifre da aggiungere**   (facoltativa) specificare le cifre che devono essere aggiunte ai numeri composti che si desidera corrispondano al modello.
    
    I valori immessi in questi campi vengono riportati nei campi **Formato per corrispondenza** e **Regola di conversione**. Se ad esempio il campo **Cifre iniziali** viene lasciato vuoto, si digita **7** nel campo **Lunghezza** e si seleziona **Esattamente**, quindi si specifica **0** in **Cifre da rimuovere**, l'espressione regolare risultante nel campo **Formato per corrispondenza** sarà:
    
    **^ (\\d{7}) $**

7.  In **Regola di conversione** specificare un modello per il formato dei numeri di telefono E.164 convertiti, come indicato di seguito:
    
      - Un valore che rappresenta il numero di cifri specificato nel formato della corrispondenza. Ad esempio, se il motivo corrispondente è **^ (\\d{7}) $** quindi **$1** nella regola di conversione rappresenta numeri composti a 7 cifre.
    
      - (Facoltativo) Digitare un valore nel campo **Prefisso** per specificare le cifre da anteporre al numero convertito (ad esempio **+1425**).
    
    Ad esempio, se **pattern to match** contiene **^ (\\d{7}) $** come modello per i numeri composti e la **regola di conversione** contiene **+ 1425 $1** come modello per i numeri di telefono e. 164, la regola Normalizza 5550100 in + 14255550100.

8.  (Facoltativo) Se la regola di normalizzazione restituisce un numero di telefono interno all'organizzazione, selezionare **Estensione interna**.

9.  (Facoltativo) Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Immetti numero di telefono da testare**.
    
    <div>
    

    > [!NOTE]
    > È possibile salvare una regola di normalizzazione che non passa ancora il test e quindi riconfigurarla successivamente. Per ulteriori informazioni, vedere <A href="lync-server-2013-test-voice-routing.md">test Voice routing in Lync Server 2013</A>.

    
    </div>

10. Fare clic su **OK** per salvare la regola di normalizzazione.

11. Fare clic su **OK** per salvare il dial plan.

12. Nella pagina **Dial plan** fare clic su **Commit** e quindi su **Salva tutto**.
    
    <div>
    

    > [!NOTE]
    > Ogni volta che si crea o si modifica una regola di normalizzazione, è necessario eseguire il comando <STRONG>Salva tutto</STRONG> per pubblicare la modifica apportata alla configurazione. Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare o modificare manualmente una regola di normalizzazione in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[Creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modificare un dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Testare il routing vocale in Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

