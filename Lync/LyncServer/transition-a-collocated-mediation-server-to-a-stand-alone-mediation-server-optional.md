---
title: Transizione di un Mediation Server collocato a un Mediation Server autonomo (facoltativo)
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c49b75845bb9a673872c5f08225dd6e1c96b69a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a>Transizione di un Mediation Server collocato a un Mediation Server autonomo (facoltativo)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

Usare la procedura seguente per eseguire la transizione del server di mediazione, collocato nel server standard o nel pool Front-End, in un Mediation Server autonomo per una distribuzione a sito singolo.

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a>Per eseguire la transizione di un Mediation Server collocato a un Mediation Server autonomo

1.  Aprire una topologia esistente da generatore di topologie.

2.  Nel riquadro sinistro passare a pool di **mediazione**.

3.  Fare clic con il pulsante destro del mouse su **pool di mediazione** e scegliere **nuovo Mediation**

4.  Nella pagina **Definisci nuovo pool di mediazione** specificare il nome di dominio completo del nuovo pool di Mediation Server. Selezionare inoltre se questo pool sarà un pool a server singolo o a più server e quindi fare clic su **Avanti**.

5.  Selezionare il pool di server front-end hop successivo in cui il nuovo Mediation Server instraderà le chiamate in ingresso e quindi fare clic su **Avanti**.

6.  Selezionare il pool di bordi da usare per Mediation Server e quindi fare clic su **Avanti**.

7.  Nella pagina **specifica gateway PSTN** associare il gateway PSTN precedente al Mediation Server. Selezionare il gateway e quindi fare clic su **Aggiungi**.

8.  Fare clic su **fine** per chiudere la procedura guidata **Definisci nuovo gruppo di mediazione** .

9.  In **Generatore di topologie**selezionare il nodo superiore **Lync Server 2013**.

10. Nel riquadro **azioni** selezionare **Pubblica topologia** e completare la procedura guidata.

11. Seguire la procedura descritta in [installare i file per Mediation Server in Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) nella documentazione relativa alla distribuzione per installare i file nel nuovo Mediation Server.

12. Dopo aver installato i file nel server Mediation, tornare a Generatore di topologie e nel riquadro sinistro passare al pool.

13. Fare clic con il pulsante destro del mouse sul pool e scegliere **modifica proprietà**.

14. In **Mediation Server**deselezionare la casella di controllo **Mediation Server collocata abilitata** e quindi fare clic su **OK**.

15. In **Generatore di topologie**selezionare il nodo superiore **Lync Server 2013**.

16. Nel menu **azione** selezionare **Pubblica topologia** e completare la procedura guidata.

</div>

</div>

<span> </span>

</div>

</div>

</div>

