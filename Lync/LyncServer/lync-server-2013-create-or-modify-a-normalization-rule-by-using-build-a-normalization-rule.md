---
title: Creare o modificare una regola di normalizzazione tramite genera una regola di normalizzazione
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
ms.openlocfilehash: 519d4d8ee00e0922d40155c541b0f869df095ab1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a>Creare o modificare una regola di normalizzazione tramite Build una regola di normalizzazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Se si vuole creare o modificare una regola di normalizzazione nel pannello di controllo di Lync Server, eseguire la procedura seguente. In alternativa, se si vuole creare o modificare manualmente una regola di normalizzazione, vedere [creare o modificare manualmente una regola di normalizzazione in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a>Per definire una regola utilizzando una regola di normalizzazione

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Opzionale Seguire i passaggi descritti in [creare un dial plan in Lync server 2013](lync-server-2013-create-a-dial-plan.md) tramite il passaggio 11 o [modificare un dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) tramite il passaggio 10.

4.  Nella **nuova regola di normalizzazione** o **Modifica regola di normalizzazione**digitare un nome che descriva il criterio di numerazione normalizzato in **nome** , ad esempio **5DigitExtension**.

5.  Opzionale In **Descrizione**Digitare una descrizione della regola di normalizzazione, ad esempio "converte le estensioni a 5 cifre".

6.  In **genera una regola di normalizzazione**immettere i valori nei campi seguenti:
    
      - **Cifre iniziali (**   facoltativo) specificare le cifre iniziali dei numeri composti per cui si vuole che il motivo corrisponda. Ad esempio, digitare **425** se si vuole che il motivo corrisponda ai numeri composti che iniziano con 425.
    
      - **Lunghezza**   specificare il numero di cifre nel modello corrispondente e selezionare se si vuole che il motivo corrisponda esattamente a questa lunghezza, corrispondere a numeri composti con almeno questa lunghezza o corrispondere a numeri composti di qualsiasi lunghezza.
    
      - **Cifre da rimuovere**   (facoltativo) specificare il numero di cifre iniziali che devono essere rimosse dai numeri composti per cui si vuole che il motivo corrisponda.
    
      - **Le cifre da aggiungere**   (facoltativo) specificano le cifre che devono essere aggiunte ai numeri composti per cui si vuole che il motivo corrisponda.
    
    I valori immessi in questi campi si riflettono in **pattern per la corrispondenza** e la **regola di traduzione**. Ad esempio, se si lasciano vuote le **cifre iniziali** , digitare **7** nel campo **lunghezza** e selezionare **esattamente**e specificare **0** in **cifre da rimuovere**, l'espressione regolare risultante nel **pattern da corrispondere** è:
    
    **^ (\\d{7}) $**

7.  Nella **regola di traduzione**specificare un motivo per il formato dei numeri di telefono E. 164 tradotti come indicato di seguito:
    
      - Valore che rappresenta il numero di cifre specificato nel criterio di corrispondenza. Ad esempio, se il criterio di corrispondenza è **^\\({7}d) $** quindi **$1** nella regola di traduzione rappresenta numeri composti da 7 cifre.
    
      - Opzionale Digitare un valore nel campo **cifre da aggiungere** per specificare le cifre da anteporre al numero tradotto, ad esempio **+ 1425**.
    
    Ad esempio, se **pattern per la corrispondenza** contiene **^\\({7}d) $** come modello per i numeri composti e la **regola di traduzione** contiene **+ 1425 $1** come modello per i numeri di telefono e. 164, la regola Normalizza 5550100 in + 14255550100.

8.  Opzionale Se la regola di normalizzazione genera un numero di telefono interno all'organizzazione, selezionare **estensione interna**.

9.  Opzionale Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **immettere un numero da testare**.
    
    <div>
    

    > [!NOTE]
    > È possibile salvare una regola di normalizzazione che non supera ancora il test e quindi riconfigurarla in un secondo momento. Per informazioni dettagliate, vedere <A href="lync-server-2013-test-voice-routing.md">eseguire il test del routing vocale in Lync Server 2013</A>.

    
    </div>

10. Fare clic su **OK** per salvare la regola di normalizzazione.

11. Fare clic su **OK** per salvare il dial plan.

12. Nella pagina **dial plan** fare clic su **commit**e quindi su **Commit all**.
    
    <div>
    

    > [!NOTE]
    > Ogni volta che si crea o si modifica una regola di normalizzazione, è necessario eseguire il comando <STRONG>commit tutti</STRONG> per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A> nella documentazione Operations.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare o modificare manualmente una regola di normalizzazione in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[Creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modificare un dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Pubblicare le modifiche in sospeso nella configurazione di routing vocale in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Testare il routing vocale in Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

