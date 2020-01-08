---
title: 'Lync Server 2013: creare o modificare manualmente una regola di traduzione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 445b17b5a878e066ed0a77c725ae035101d57469
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a>Creare o modificare manualmente una regola di traduzione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-08-06_

Seguire questa procedura se si vuole definire una regola di traduzione scrivendo un'espressione regolare per il modello e la regola di traduzione corrispondenti. In alternativa, è possibile immettere un set di valori nello strumento **Compila una regola di traduzione** e abilitare il pannello di controllo di Lync Server per generare la regola di corrispondenza corrispondente e il criterio di traduzione. Per informazioni dettagliate, vedere [creare o modificare una regola di traduzione usando lo strumento crea una regola di traduzione in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).

<div>

## <a name="to-define-a-translation-rule-manually"></a>Per definire manualmente una regola di traduzione

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Per iniziare a definire una regola di traduzione, seguire la procedura descritta in [configurare un trunk con il bypass multimediale in Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) tramite il passaggio 10 o [configurare un trunk senza bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) tramite il passaggio 9.

4.  Nel campo **nome** della pagina **nuova** regola di traduzione o **Modifica regola di traduzione** digitare un nome che descriva il modello di numero da tradurre.

5.  Opzionale In **Descrizione**Digitare una descrizione della regola di traduzione, ad esempio le **chiamate interurbane internazionali degli Stati Uniti**.

6.  Fare clic su **modifica** nella parte inferiore della sezione **Compila una regola di traduzione** .

7.  Immettere le opzioni seguenti nell' **espressione regolare di tipo**:
    
      - In **Confronta questo modello**, specifica il motivo che verrà usato per corrispondere ai numeri da tradurre.
    
      - Nella **regola di traduzione**specificare un motivo per il formato dei numeri tradotti.
    
    Ad esempio, se si immette ** ^ \\+ (\\d{9}\\d +) $** in **corrisponde a questo modello** e **011 $1** nella **regola di traduzione**, la regola tradurrà + 441235551010 in 011441235551010.

8.  Fare clic su **OK** per salvare la regola di traduzione.

9.  Fare clic su **OK** per salvare la configurazione trunk.

10. Nella pagina **trunk Configuration** fare clic su **commit**e quindi su **Commit all**.
    
    <div>
    

    > [!NOTE]  
    > Ogni volta che si crea o si modifica una regola di traduzione, è necessario eseguire il comando <STRONG>commit tutti</STRONG> per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A> nella documentazione Operations.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare o modificare una regola di traduzione usando lo strumento crea una regola di traduzione in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
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

