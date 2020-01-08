---
title: 'Lync Server 2013: Creare o modificare manualmente una regola di normalizzazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a normalization rule manually
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48185943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e4bff312dda32aea118f91c1e5e54f2c8334698
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a>Creare o modificare manualmente una regola di normalizzazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-22_

Se si vuole creare o modificare manualmente una regola di normalizzazione, eseguire i passaggi seguenti. Se si vuole creare o modificare una regola di normalizzazione usando la creazione di una regola di normalizzazione nel pannello di controllo di Lync Server, vedere [creare o modificare una regola di normalizzazione tramite Build una regola di normalizzazione in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).

<div>

## <a name="to-define-a-normalization-rule-manually"></a>Per definire manualmente una regola di normalizzazione

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Opzionale Seguire i passaggi descritti in [creare un dial plan in Lync server 2013](lync-server-2013-create-a-dial-plan.md) o [modificare un dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

4.  Nella **nuova regola di normalizzazione** o **Modifica regola di normalizzazione**digitare un nome che descriva il criterio di numerazione normalizzato in **nome** , ad esempio denominare la regola di normalizzazione **5DigitExtension**.

5.  Opzionale In campo **Descrizione** Digitare una descrizione della regola di normalizzazione, ad esempio "converte le estensioni a 5 cifre".

6.  In **genera una regola di normalizzazione**fare clic su **modifica**.

7.  Immettere le opzioni seguenti nell' **espressione regolare di tipo**:
    
      - In **corrispondenza di questo modello**specificare il motivo che si vuole usare per corrispondere al numero di telefono chiamato.
    
      - Nella **regola di traduzione**specificare un motivo per il formato dei numeri di telefono E. 164 tradotti.
    
    Ad esempio, se si digita **^ (\\d{7}) $** in **corrispondenza di questo modello** e **+ 1425 $1** nella **regola di traduzione**, la regola Normalizza 5550100 in + 14255550100.

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


[Creare o modificare una regola di normalizzazione tramite Build una regola di normalizzazione in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
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

