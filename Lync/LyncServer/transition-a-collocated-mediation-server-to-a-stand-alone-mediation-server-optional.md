---
title: Eseguire la transizione di un Mediation Server collocato a un Mediation Server autonomo (facoltativo)
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03e182bc32ba07ae22b2c14cc0a51f36ac93ba57
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a>Eseguire la transizione di un Mediation Server collocato a un Mediation Server autonomo (facoltativo)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

Eseguire la procedura seguente per la transizione del Mediation Server, collocato nel server Standard Edition o nel pool Front End, in un Mediation Server autonomo per una distribuzione a sito singolo.

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a>Per effettuare la transizione di un Mediation Server collocato in un server Mediation Server autonomo (facoltativo)

1.  Apertura di una topologia esistente da Generatore di topologie

2.  Nel riquadro sinistro passare a **Pool Mediation Server**.

3.  Fare clic con il pulsante destro del mouse su **Pool Mediation Server** e quindi scegliere **Nuovo Mediation Server**.

4.  Nella pagina **Definisci nuovo pool Mediation Server** immettere il nome di dominio completo del nuovo pool Mediation Server, specificare se sarà un pool a server singolo o a più server e quindi fare clic su **Avanti**.

5.  Selezionare il pool dell'hop Front End server successivo al quale il nuovo Mediation Server instraderà le chiamate in arrivo e quindi fare clic su **Avanti**.

6.  Selezionare il pool di server perimetrali che deve essere utilizzato dal Mediation Server e quindi fare clic su **Avanti**.

7.  Nella pagina **Specificare i gateway PSTN** associare il gateway PSTN precedente al Mediation Server. Selezionare il gateway e quindi fare clic su **Aggiungi**.

8.  Fare clic su **Fine** per chiudere la procedura guidata **Definisci nuovo pool Mediation Server**.

9.  In **Generatore di topologie**selezionare il nodo principale **Lync Server 2013**.

10. Nel riquadro **Azioni** selezionare **Pubblica topologia** e quindi completare la procedura guidata.

11. Attenersi alla procedura descritta in [Install the files for Mediation Server in Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) nella documentazione relativa alla distribuzione per installare i file nel nuovo Mediation Server.

12. Dopo l'installazione dei file nel Mediation Server, tornare al Generatore di topologie e nel riquadro sinistro passare al pool.

13. Fare clic con il pulsante destro del mouse sul pool e quindi scegliere **Modifica proprietà**.

14. In **Mediation Server** deselezionare la casella di controllo **Mediation Server nella stessa posizione abilitato** e quindi fare clic su **OK**.

15. In **Generatore di topologie**selezionare il nodo principale **Lync Server 2013**.

16. Nel menu **Azioni** selezionare **Pubblica topologia** e quindi completare la procedura guidata.

</div>

</div>

<span> </span>

</div>

</div>

</div>

