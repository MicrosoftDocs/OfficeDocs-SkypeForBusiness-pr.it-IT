---
title: Creare o modificare una regola di conversione utilizzando lo strumento Crea regola di conversione
description: Creare o modificare una regola di conversione utilizzando lo strumento Crea regola di conversione.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 116048fff834e797bca76a895f45cd0ebc83ab94
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574522"
---
# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a>Creare o modificare una regola di conversione utilizzando lo strumento Crea regola di conversione in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-05_

Se si desidera definire una regola di conversione, eseguire la procedura seguente per specificare un insieme di valori nello strumento **Crea regola di conversione** e per abilitare il pannello di controllo di Lync Server per generare la regola di conversione e il motivo corrispondente. In alternativa, è possibile scrivere manualmente un'espressione regolare per definire il formato e la regola di conversione corrispondenti. Per ulteriori informazioni, vedere [creare o modificare manualmente una regola di conversione in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Per definire una regola tramite lo strumento Crea regola di conversione

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Per iniziare a definire una regola di conversione, eseguire la procedura descritta in [Configure a Trunk with media bypass in Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through Step 10 oppure [Configure a Trunk Without Media Bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through Step 9.

4.  In **Nome** nella pagina **Nuova regola di conversione** o **Modifica regola di conversione** digitare un nome descrittivo del formato del numero da convertire.

5.  (Facoltativo) In **Descrizione** digitare una descrizione della regola di conversione, ad esempio **Chiamate interurbane internazionali**.

6.  Nella sezione **Crea regola di conversione** della finestra di dialogo immettere i valore nei campi seguenti:
    
      - **Cifre iniziali**: (facoltativo) specificare le cifre iniziali dei numeri a cui si desidera corrisponda il formato. Ad esempio, immettere **+** in questo campo per associare i numeri nel formato E. 164 (che iniziano con +).
    
      - **Lunghezza**: specificare il numero di cifre nel formato e specificare se si desidera applicare il formato ai numeri esattamente di questa lunghezza, almeno di questa lunghezza o di qualsiasi lunghezza. Ad esempio, immettere **11** e selezionare **Almeno** nell'elenco a discesa per specificare una corrispondenza con i numeri con una lunghezza di almeno 11 cifre.
    
      - **Cifre da rimuovere**: (facoltativo) specificare il numero di cifre iniziali da rimuovere. Ad esempio, immettere **1** per eliminare il **+** valore dall'inizio del numero.
    
      - **Prefisso**: (facoltativo) specificare le cifre da aggiungere all'inizio dei numeri convertiti. Ad esempio, immettere **011** se si desidera aggiungere 011 all'inizio dei numeri convertiti quando si applica questa regola.
    
    I valori immessi in questi campi vengono riportati nei campi **Formato per corrispondenza** e **Regola di conversione**. Se si specificano i valori di esempio precedenti, ad esempio, l'espressione regolare risultante nel campo **Formato per corrispondenza** sarà:
    
    **^\\+ ( \\ d {9} \\ d +) $**
    
    Nel campo **Regola di conversione** specificare un modello per il formato dei numeri convertiti. Il modello è composto da due parti:
    
      - Un valore (ad esempio **$1**) che rappresenta il numero di cifre nel formato corrispondente
    
      - (Facoltativo) Un valore che è possibile aggiungere all'inizio del numero immettendolo nel campo **Prefisso**
    
    In base ai valori di esempio precedenti, nel campo **Regola di conversione** viene visualizzato **011$1**.
    
    Con l'applicazione di questa regola di conversione il numero +441235551010 diventa 011441235551010.

7.  Fare clic su **OK** per salvare la regola di conversione.

8.  Fare clic su **OK** per salvare la configurazione del trunk.

9.  Nella pagina **Configurazione trunk** fare clic su **Commit** e quindi su **Salva tutto**.
    
    <div>
    

    > [!NOTE]
    > Ogni volta che si crea o modifica una regola di conversione, è necessario eseguire il comando <STRONG>Salva tutto</STRONG> per pubblicare la modifica apportata alla configurazione. Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare o modificare manualmente una regola di conversione in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
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

