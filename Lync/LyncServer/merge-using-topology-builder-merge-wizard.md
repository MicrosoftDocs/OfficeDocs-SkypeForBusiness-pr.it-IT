---
title: Unione tramite la creazione guidata generatore di topologia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61981ae875fef9976377644a9b67f0a329581a90
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a>Unione tramite la creazione guidata generatore di topologia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-02_

1.  Scaricare la distribuzione esistente tramite Generatore di topologia.

2.  Nel menu **azione** selezionare **Unisci Office Communications Server 2007 R2**.

3.  Fare clic su **Avanti**.

4.  In **specifica configurazione del bordo**fare clic su **Aggiungi**.
    
    ![Procedura guidata per l'unione delle topologie - Pagina Specificare installazione server perimetrale](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Procedura guidata per l'unione delle topologie - Pagina Specificare installazione server perimetrale")  

5.  In **Specifica tipo di bordo**immettere il tipo di configurazione del server perimetrale e quindi fare clic su **Avanti**. Questo esempio usa l'opzione **Single Edge Server** .
    
    <div>
    

    > [!IMPORTANT]  
    > La <STRONG>distribuzione di Edge espansa</STRONG> non è una configurazione supportata. Un <STRONG>server perimetrale espanso</STRONG> deve prima essere convertito in un <STRONG>singolo Edge Server</STRONG> o in un server <STRONG>perimetrale consolidato con bilanciamento del carico</STRONG> .

    
    </div>

6.  In **specificare le impostazioni dei bordi interni** immettere le informazioni rilevanti per il nome di dominio completo e le porte interne del pool Edge in base alle esigenze e quindi fare clic su **Avanti**.
    
    ![Finestra di dialogo Specificare le impostazioni del perimetro interno](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Finestra di dialogo Specificare le impostazioni del perimetro interno")  

7.  In **specifica bordo esterno**immettere le informazioni di dominio completo per le conferenze Web per il server perimetrale.
    
    <div>
    

    > [!IMPORTANT]  
    > Prima di fare clic su <STRONG>Avanti</STRONG>, eseguire il passaggio successivo di questa procedura. È molto importante non perdere questo passaggio.

    
    </div>

8.  Selezionare la casella di controllo **questo pool di bordi viene usato per la Federazione e la connettività di messaggistica istantanea pubblica** se si prevede di usare il server perimetrale legacy di Office Communications Server 2007 R2 per la Federazione. Se sono distribuiti più server perimetrali, solo uno di essi verrà abilitato per la Federazione. Se non si seleziona questa casella e si decide in seguito che si vuole abilitare la Federazione, è necessario eseguire la procedura guidata unione generatore di topologia e pubblicare di nuovo la topologia.
    
    ![Finestra di dialogo Server perimetrale - Pagina Specificare il perimetro esterno](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Finestra di dialogo Server perimetrale - Pagina Specificare il perimetro esterno")  

9.  In **specifica hop successivo**immettere il nome di dominio completo (FQDN) della posizione dell'hop successivo nell'ambiente. Fare clic su **fine**.
    
    ![Finestra di dialogo Server perimetrale - Pagina Specificare hop successivo](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Finestra di dialogo Server perimetrale - Pagina Specificare hop successivo")  

10. In **specifica configurazione di Edge**, se sono stati aggiunti tutti i server Edge di Office Communications Server 2007 R2, fare clic su **Avanti**. Se sono presenti più server Edge di Office Communications Server 2007 R2 da aggiungere, ripetere questa procedura a partire dal passaggio 4.

11. In **specifica porta SIP interna** selezionare l'impostazione predefinita, ovvero se non è stata modificata la porta SIP predefinita. Modificare il valore appropriato se non si usa una porta predefinita di 5061 e quindi fare clic su **Avanti**.

12. In **Riepilogo**, fare clic su **Avanti** per iniziare a unire le topologie.

13. La pagina della procedura guidata verifica che l'Unione delle topologie abbia avuto esito positivo.

14. Nella colonna **stato** verificare che il valore sia **successo**e quindi fare clic su **fine**.

15. Nel riquadro sinistro di generatore di topologia è ora necessario vedere il **BackCompatSite**, che indica che l'ambiente Office Communications Server 2007 R2 è stato unito a Lync Server 2013.
    
    ![Unione di topologie visualizzata nel Generatore di topologie](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Unione di topologie visualizzata nel Generatore di topologie")  

16. Nel menu **azione** fare clic su **Pubblica topologia**e quindi su **Avanti**.

17. Al termine della **pubblicazione guidata** , fare clic su **fine**.
    
    <div>
    

    > [!NOTE]  
    > È importante completare l'argomento successivo, <A href="import-policies-and-settings.md">importare criteri e impostazioni</A>per verificare che le impostazioni dei criteri legacy vengano importate in Lync Server 2013.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

