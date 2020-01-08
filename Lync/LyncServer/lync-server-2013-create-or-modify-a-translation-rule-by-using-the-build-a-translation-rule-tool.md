---
title: Creare o modificare una regola di traduzione usando lo strumento crea una regola di traduzione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06f498af25dfd851bd2950ce08d5c66179b95ebc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a>Creare o modificare una regola di traduzione usando lo strumento crea una regola di traduzione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-05_

Seguire questa procedura se si vuole definire una regola di traduzione immettendo un set di valori nello strumento **Compila una regola di traduzione** e abilitando il pannello di controllo di Lync Server per generare il modello di corrispondenza corrispondente e la regola di traduzione. In alternativa, è possibile eseguire manualmente un'espressione regolare di scrittura per definire il modello e la regola di traduzione corrispondenti. Per informazioni dettagliate, vedere [creare o modificare manualmente una regola di traduzione in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Per definire una regola usando lo strumento crea una regola di traduzione

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Per iniziare a definire una regola di traduzione, seguire la procedura descritta in [configurare un trunk con il bypass multimediale in Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) tramite il passaggio 10 o [configurare un trunk senza bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) tramite il passaggio 9.

4.  In **nome** nella pagina **nuova** regola di traduzione o **Modifica regola di traduzione** digitare un nome che descriva il modello di numero da tradurre.

5.  Opzionale In **Descrizione**Digitare una descrizione della regola di traduzione, ad esempio le **chiamate interurbane internazionali degli Stati Uniti**.

6.  Nella sezione **genera una regola di traduzione** della finestra di dialogo immettere i valori nei campi seguenti:
    
      - **Cifre iniziali**: (facoltativo) specificare le cifre iniziali dei numeri a cui si vuole che corrisponda il motivo. Ad esempio, immetti **+** in questo campo i numeri in formato E. 164 (che iniziano con +).
    
      - **Length**: specificare il numero di cifre nel criterio di corrispondenza e selezionare se si vuole che il pattern corrisponda a numeri di lunghezza uguale a quella specificata, almeno questa lunghezza o qualsiasi lunghezza. Ad esempio, immetti **11** e **Seleziona almeno nell'elenco a discesa** per abbinare i numeri di almeno 11 cifre in lunghezza.
    
      - **Cifre da rimuovere**: (facoltativo) specificare il numero di cifre iniziali da eliminare. Ad esempio, immettere **1** per eliminare l' **+** inizio del numero.
    
      - **Cifre da aggiungere**: (facoltativo) specificare le cifre da anteporre ai numeri tradotti. Ad esempio, immetti **011** se vuoi che 011 venga anteposto ai numeri tradotti quando viene applicata la regola.
    
    I valori immessi in questi campi si riflettono nei campi della regola **per la corrispondenza** e la **traduzione** . Ad esempio, se specifichi i valori di esempio precedenti, l'espressione regolare risultante nel campo **pattern to match** è:
    
    **^\\+ (\\d{9}\\d +) $**
    
    Il campo della **regola di traduzione** specifica un modello per il formato dei numeri tradotti. Questo modello include due parti:
    
      - Un valore, ad esempio **$1**, che rappresenta il numero di cifre nel modello corrispondente
    
      - Opzionale Un valore che puoi anteporre immettendolo nel campo **cifre da aggiungere**
    
    Usando i valori di esempio precedenti, viene visualizzato **011 $1** nel campo della **regola di traduzione** .
    
    Quando viene applicata questa regola di traduzione, + 441235551010 diventa 011441235551010.

7.  Fare clic su **OK** per salvare la regola di traduzione.

8.  Fare clic su **OK** per salvare la configurazione trunk.

9.  Nella pagina **trunk Configuration** fare clic su **commit**e quindi su **Commit all**.
    
    <div>
    

    > [!NOTE]
    > Ogni volta che si crea o si modifica una regola di traduzione, è necessario eseguire il comando <STRONG>commit tutti</STRONG> per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A> nella documentazione Operations.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare o modificare manualmente una regola di traduzione in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[Configurare un trunk con il bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurare un trunk senza bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Pubblicare le modifiche in sospeso nella configurazione di routing vocale in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Opzioni di bypass multimediale globale in Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

