---
title: 'Lync Server 2013: definire un gateway PSTN per un sito di succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8a47e395e74dae1eb6ec454e63fb343dcea7872
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a>Definire un gateway PSTN per un sito di succursale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

Eseguire questa procedura nel sito centrale, che contiene almeno un pool Front end o un server Standard Edition.

<div>


> [!IMPORTANT]  
> Prima di eseguire la procedura, è necessario che vengano soddisfatte le condizioni seguenti: 
> <UL>
> <LI>
> <P>Il software di&nbsp;comunicazione Lync Server 2013 deve essere configurato nel sito centrale.</P>
> <LI>
> <P>Il Mediation Server deve essere distribuito nel sito centrale.</P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a>Per definire un gateway PSTN

1.  Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server** e quindi **Generatore di topologie di Lync Server**.

2.  Nell'albero della console espandere il sito centrale, espandere **Siti di succursale** e quindi espandere il nome del sito derivato per il quale si desidera definire un gateway PSTN. Espandere quindi **Componenti condivisi**.

3.  Fare clic con il pulsante destro del mouse su **Gateway PSTN** e quindi scegliere **Nuovo gateway IP/PSTN**.

4.  Nella finestra di dialogo **Definisci nuovo gateway IP/PSTN** fare clic su **FQDN gateway o indirizzo IP** e quindi digitare il nome di dominio completo (FQDN) o l'indirizzo IP del gateway che si sta distribuendo nel sito derivato.

5.  Fare clic su **Porta di attesa per gateway IP/PSTN** e quindi accettare i valori predefiniti.

6.  Nell'elenco **Protocollo trasporto SIP** fare clic sul protocollo di trasporto utilizzato dal gateway e quindi su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Per motivi di sicurezza, è consigliabile utilizzare un gateway PSTN che supporti TLS (Transport Layer Security).

    
    </div>

<div>


> [!TIP]  
> Utilizzare il cmdlet <STRONG>Set-CsPstnGateway</STRONG> per modificare le proprietà di un gateway PSTN. Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>, nella Guida di Lync Server Management Shell.



</div>

**Passaggio successivo** per la resilienza dei siti di succursale: [configurazione degli utenti per la resilienza dei siti di succursale in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Opzioni di distribuzione di gateway PSTN in Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

