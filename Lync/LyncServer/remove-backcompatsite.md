---
title: Rimuovere BackCompatSite
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccfcd48c575e300b12fe08611d6f898749041478
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a>Rimuovere BackCompatSite

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-28_

Dopo che tutti i pool sono stati disattivati e tutti i server perimetrali sono stati disinstallati, eseguire la procedura guidata unione di generatore di topologia per rimuovere **BackCompatSite**.

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a>Per rimuovere il sito BackCompat da generatore di topologie

1.  Aprire una distribuzione esistente da generatore di topologie.

2.  Nel menu **azione** fare clic su **Unisci topologia di 2007 R2**.

3.  Fare clic su **Avanti** per continuare.

4.  Nella pagina **specifica legacy Edge** verificare che l'elenco di Edge Server sia vuoto. Se l'elenco non è vuoto, usare il pulsante **Rimuovi** per rimuovere tutti i server perimetrali legacy e quindi fare clic su **Avanti**.
    
    ![Procedura guidata per l'unione delle topologie - Pagina Specificare installazione server perimetrale](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Procedura guidata per l'unione delle topologie - Pagina Specificare installazione server perimetrale")  

5.  Nella pagina **specificare l'impostazione della porta SIP interna** fare clic su **Avanti**.

6.  Nella pagina **Riepilogo** fare clic su **Avanti** per iniziare a unire le topologie per rimuovere il sito legacy.

7.  Nella colonna **stato** verificare che il valore sia **successo** e quindi fare clic su **fine** per chiudere la procedura guidata.

8.  Nel riquadro sinistro di generatore di topologia espandere il BackCompatSite e assicurarsi che nessun server sia elencato.

9.  Fare clic con il pulsante destro del mouse sul **BackCompatSite**e quindi scegliere **Elimina**.

10. In **Generatore di topologie**selezionare il più alto nodo **Lync Server**.

11. Scegliere **Pubblica topologia** dal menu **azione** e quindi fare clic su **Avanti**.

12. Al termine della **pubblicazione guidata** , fare clic su **fine** per chiudere la procedura guidata.

</div>

</div>

<span> </span>

</div>

</div>

</div>

