---
title: 'Lync Server 2013: creare o modificare manualmente una regola di normalizzazione'
description: 'Lync Server 2013: creare o modificare manualmente una regola di normalizzazione.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule manually
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48185943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7cc61706dd91b52822747d59693c8998d244c08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574582"
---
# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a>Creare o modificare manualmente una regola di normalizzazione in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-22_

Se si desidera creare o modificare manualmente una regola di normalizzazione, eseguire la procedura seguente. Se si desidera creare o modificare una regola di normalizzazione utilizzando crea una regola di normalizzazione nel pannello di controllo di Lync Server, vedere [creare o modificare una regola di normalizzazione utilizzando crea una regola di normalizzazione in Lync server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).

<div>

## <a name="to-define-a-normalization-rule-manually"></a>Per definire manualmente una regola di normalizzazione

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Optional Seguire la procedura illustrata in [creare un dial plan in Lync server 2013](lync-server-2013-create-a-dial-plan.md) o [modificare un dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

4.  In **nuova regola di normalizzazione** o **Modifica regola di normalizzazione**digitare un nome che descriva il tipo di numero normalizzato in **nome** (ad esempio, denominare la regola di normalizzazione **5DigitExtension**).

5.  Optional In campo **Descrizione** Digitare una descrizione della regola di normalizzazione (ad esempio, "converte le estensioni a 5 cifre").

6.  In **genera una regola di normalizzazione**fare clic su **modifica**.

7.  Immettere quanto segue in **Digita espressione regolare**:
    
      - In **corrispondenza di questo modello**specificare il modello che si desidera utilizzare per la corrispondenza con il numero di telefono composto.
    
      - In **regola di conversione**specificare un modello per il formato dei numeri di telefono E. 164 tradotti.
    
    Ad esempio, se si immette **^ ( \\ d {7} ) $** in **corrispondenza di questo modello** e **+ 1425 $1** in **regola di conversione**, la regola Normalizza 5550100 in + 14255550100.

8.  (Facoltativo) Se la regola di normalizzazione restituisce un numero di telefono interno all'organizzazione, selezionare **Estensione interna**.

9.  Optional Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Immetti numero di telefono da testare**.
    
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


[Creare o modificare una regola di normalizzazione utilizzando crea una regola di normalizzazione in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
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

