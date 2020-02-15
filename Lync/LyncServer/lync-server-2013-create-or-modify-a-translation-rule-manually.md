---
title: 'Lync Server 2013: creare o modificare manualmente una regola di conversione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ae305052523c05bacb294928c1f81afd4e51931
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "41995541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a>Creare o modificare manualmente una regola di conversione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-08-06_

Eseguire questa procedura se si desidera definire una regola di conversione scrivendo un'espressione regolare per il formato e la regola. In alternativa, è possibile immettere un insieme di valori nello strumento **Costruisci una regola di conversione** e abilitare il pannello di controllo di Lync Server per generare la corrispondente regola di conversione e il modello corrispondenti. Per ulteriori informazioni, vedere [creare o modificare una regola di conversione utilizzando lo strumento Crea regola di conversione in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).

<div>

## <a name="to-define-a-translation-rule-manually"></a>Per definire manualmente una regola di conversione

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Per iniziare a definire una regola di conversione, eseguire la procedura descritta in [Configure a Trunk with media bypass in Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through Step 10 oppure [Configure a Trunk Without Media Bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through Step 9.

4.  Nel campo **Nome** della pagina **Nuova regola di conversione** o **Modifica regola di conversione** digitare un nome che descriva il formato del numero da convertire.

5.  (Facoltativo) In **Descrizione** digitare una descrizione della regola di conversione, ad esempio **Chiamate internazionali Stati Uniti**.

6.  Fare clic su **Modifica** nella parte inferiore della sezione **Crea regola di conversione**.

7.  Immettere quanto segue in **Digita espressione regolare**:
    
      - In **Trova corrispondenza per questo formato** specificare il modello di formato da utilizzare per trovare corrispondenze con i numeri da convertire.
    
      - In **Regola di conversione** specificare un modello per il formato dei numeri convertiti.
    
    Ad esempio, se si immette ** ^ \\+ (\\d{9}\\d +) $** in **corrispondenza di questo modello** e **011 $1** in **regola di conversione**, la regola verrà convertita da + 441235551010 a 011441235551010.

8.  Fare clic su **OK** per salvare la regola di conversione.

9.  Fare clic su **OK** per salvare la configurazione del trunk.

10. Nella pagina **Configurazione trunk** fare clic su **Commit** e quindi su **Salva tutto**.
    
    <div>
    

    > [!NOTE]  
    > Ogni volta che si crea o modifica una regola di conversione, è necessario eseguire il comando <STRONG>Salva tutto</STRONG> per pubblicare la modifica apportata alla configurazione. Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare o modificare una regola di conversione utilizzando lo strumento Crea regola di conversione in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[Configurare un trunk con bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurare un trunk senza bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Opzioni di bypass multimediale globale in Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

