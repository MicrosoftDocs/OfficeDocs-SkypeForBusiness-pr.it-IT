---
title: Unione mediante l'Unione guidata generatore di topologie
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4760dcd8810d12b112c3bb042e0f28a039683a08
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a>Unione mediante l'Unione guidata generatore di topologie

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-02_

1.  Eseguire il download della distribuzione esistente utilizzando Generatore di topologie.

2.  Scegliere **Unisci Office Communications Server 2007 R2** dal menu **Azione**.

3.  Fare clic su **Avanti**.

4.  In **Specificare installazione server perimetrale** fare clic su **Aggiungi**.
    
    ![Procedura guidata per la topologia di Unione, specificare la pagina installazione Edge](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Procedura guidata per la topologia di Unione, specificare la pagina installazione Edge")  

5.  In **Specificare il tipo di server perimetrale** immettere il tipo di configurazione del server perimetrale e quindi fare clic su **Avanti**. In questo esempio viene utilizzata l'opzione **Server perimetrale singolo**.
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>Distribuzione server perimetrale espanso</STRONG> non è una configurazione supportata. Un <STRONG>Server perimetrale espanso</STRONG> deve essere prima convertito in un <STRONG>Server perimetrale singolo</STRONG> o in un <STRONG>Server perimetrale consolidato con carico bilanciato</STRONG>.

    
    </div>

6.  In **specificare le impostazioni del perimetro interno** immettere le informazioni rilevanti per le porte e l'FQDN interno del pool di server perimetrali in base alle esigenze e quindi fare clic su **Avanti**.
    
    ![Specificare la finestra di dialogo Impostazioni perimetro interno](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Specificare la finestra di dialogo Impostazioni perimetro interno")  

7.  In **Specificare il perimetro esterno** immettere le informazioni relative all'FQDN di Web Conferencing per il server perimetrale.
    
    <div>
    

    > [!IMPORTANT]  
    > Prima di fare clic su <STRONG>Avanti</STRONG>, eseguire il passaggio successivo di questa procedura. È molto importante non ignorare questo passaggio.

    
    </div>

8.  Selezionare la casella di controllo **questo pool di server perimetrali viene utilizzato per la Federazione e la connettività per la messaggistica istantanea pubblica** se si prevede di utilizzare il server perimetrale di Office Communications 2007 R2 legacy per la Federazione. Se sono distribuiti più server perimetrali, solo uno di essi sarà abilitato per la federazione. Se non si seleziona questa casella di controllo e si decide successivamente di abilitare la federazione, sarà necessario eseguire l'unione guidata di Generatore di topologie e ripubblicare la topologia.
    
    ![Finestra di dialogo server perimetrale, specificare la pagina perimetro esterno](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Finestra di dialogo server perimetrale, specificare la pagina perimetro esterno")  

9.  In **Specificare hop successivo** immettere il nome di dominio completo (FQDN) della posizione dell'hop successivo nell'ambiente. Fare clic su **Fine**.
    
    ![Finestra di dialogo server perimetrale, specificare la pagina hop successivo](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Finestra di dialogo server perimetrale, specificare la pagina hop successivo")  

10. In **specifica installazione perimetrale**, se sono stati aggiunti tutti i server perimetrali di Office Communications Server 2007 R2, fare clic su **Avanti**. Se si dispone di più server perimetrali di Office Communications Server 2007 R2 da aggiungere, ripetere questa procedura a partire dal passaggio 4.

11. In **specifica porta SIP interna** selezionare l'impostazione predefinita, ovvero se non è stata modificata la porta SIP predefinita. Se invece non si sta utilizzando la porta predefinita 5061, modificare l'impostazione in base alle proprie esigenze e quindi fare clic su **Avanti**.

12. In **Riepilogo** fare clic su **Avanti** per iniziare a unire le topologie.

13. Nella pagina della procedura guidata viene confermato l'esito positivo dell'unione delle topologie.

14. Nella colonna **Stato** verificare che il valore sia **Esito positivo** e quindi fare clic su **Fine**.

15. Nel riquadro sinistro di generatore di topologie, è ora possibile visualizzare **BackCompatSite**, che indica che l'ambiente Office Communications Server 2007 R2 è stato unito a Lync Server 2013.
    
    ![Generatore di topologie che mostra una topologia unita](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Generatore di topologie che mostra una topologia unita")  

16. Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.

17. Al termine della Pubblicazione guidata **** fare clic su  **Fine **.
    
    <div>
    

    > [!NOTE]  
    > È importante completare l'argomento successivo, <A href="import-policies-and-settings.md">Import Policies and Settings</A>, per assicurarsi che le impostazioni dei criteri legacy vengano importate in Lync Server 2013.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

