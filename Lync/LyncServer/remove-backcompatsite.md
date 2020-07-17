---
title: Rimuovere BackCompatSite
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 792fcf29033a7495a7da340decb561e25084612d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a>Rimuovere BackCompatSite

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-28_

Dopo avere disattivato tutti i pool e avere disinstallato tutti i server perimetrali, eseguire la procedura di unione guidata del Generatore di topologie per rimuovere **BackCompatSite**.

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a>Per rimuovere BackCompatSite dal Generatore di topologie

1.  Aprire una distribuzione esistente dal Generatore di topologie.

2.  Scegliere **Unisci topologia 2007 R2** dal menu **Azione**.

3.  Fare clic su **Avanti** per continuare.

4.  Nella pagina **Specifica il server perimetrale legacy** assicurarsi che l'elenco di server perimetrali sia vuoto. Se l'elenco non è vuoto, utilizzare il pulsante **Rimuovi** per rimuovere tutti i server perimetrali legacy e quindi fare clic su **Avanti**.
    
    ![Procedura guidata per la topologia di Unione, specificare la pagina installazione Edge](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Procedura guidata per la topologia di Unione, specificare la pagina installazione Edge")  

5.  Nella pagina **Specificare la porta SIP interna** fare clic su **Avanti**.

6.  Nella pagina **Riepilogo** fare clic su **Avanti** per iniziare a unire le topologie per rimuovere il sito legacy.

7.  Verificare che nella colonna **Stato** sia visualizzato il valore **Esito positivo** e quindi fare clic su **Fine** per chiudere la procedura guidata.

8.  Nel riquadro sinistro del Generatore di topologie espandere BackCompatSite e verificare che non siano elencati server.

9.  Fare clic con il pulsante destro del mouse su **BackCompatSite** e quindi scegliere **Elimina**.

10. In **Generatore di topologie** selezionare il nodo di primo livello **Lync Server**.

11. Nel menu **Azioni** selezionare **Pubblica topologia** e fare clic su **Avanti**.

12. Al termine della **Pubblicazione guidata**, fare clic su **Fine** per chiudere la procedura guidata.

</div>

</div>

<span> </span>

</div>

</div>

</div>

