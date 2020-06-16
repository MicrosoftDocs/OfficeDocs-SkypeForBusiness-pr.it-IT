---
title: Configurare i server applicazioni attendibili
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cbaba4f59a22de6fcee38ee51845d551033cfea
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>Configurare i server applicazioni attendibili

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-04_

In un ambiente misto, se si crea un nuovo server applicazioni attendibile dopo aver unito la topologia di Office Communications Server legacy con Lync Server 2013 e si definisce un nuovo server applicazioni attendibile tramite Generatore di topologie, è necessario impostare il pool dell'hop successivo come pool di Lync Server 2013. In un ambiente Unito, sia il pool di Office Communications Server legacy che il pool di Lync Server 2013 vengono visualizzati nell'elenco a discesa. La selezione del pool legacy *non* è supportata.

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a>Per selezionare Lync Server 2013 come hop successivo durante la creazione di un server applicazioni attendibile

1.  Aprire una topologia esistente dal Generatore di topologie.

2.  Nel riquadro di sinistra fare clic con il pulsante destro del mouse su **Server applicazioni attendibili** e quindi scegliere **Nuovo pool di applicazioni attendibili**.

3.  Immettere il nome FQDN del pool di applicazioni attendibili in **FQDN pool** e specificare se sarà una distribuzione a server singolo o a più server.

4.  Fare clic su **Avanti**.

5.  Nell'elenco nella pagina **selezionare l'hop successivo** selezionare il pool Front End di Lync Server 2013.
    
    ![Definire una nuova finestra di dialogo pool di applicazioni attendibili](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Definire una nuova finestra di dialogo pool di applicazioni attendibili")  

6.  Fare clic su **Fine**.

7.  Selezionare il nodo principale **Lync Server** e nel riquadro **Azioni** selezionare **Pubblica**.

8.  Verificare che il **Pool di applicazioni attendibili** sia stato creato e sia associato al pool Front End corretto.

</div>

</div>

<span> </span>

</div>

</div>

</div>

