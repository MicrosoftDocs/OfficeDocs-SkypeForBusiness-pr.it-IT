---
title: 'Lync Server 2013: Definire un gateway PSTN per un sito di succursale'
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
ms.openlocfilehash: e4445647e6ffcbfc2cfc137bd120d0aced6a9908
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a>Definire un gateway PSTN per un sito di succursale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Eseguire questa procedura nel sito centrale, che contiene almeno un pool Front-end o un server Standard Edition.

<div>


> [!IMPORTANT]  
> Prima di eseguire la procedura, è necessario che siano presenti le condizioni seguenti: 
> <UL>
> <LI>
> <P>Il software di&nbsp;comunicazione di Lync Server 2013 deve essere configurato nel sito centrale.</P>
> <LI>
> <P>Mediation Server deve essere distribuito nel sito centrale.</P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a>Per definire un gateway PSTN

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Microsoft Lync Server**e quindi su **Generatore di topologia di Lync Server**.

2.  Nell'albero della console espandere il sito centrale, espandere **siti di filiale**, espandere il nome del sito della filiale per la definizione di un gateway PSTN (Public Switched Telephone Network), quindi espandere i **componenti condivisi**.

3.  Fare clic con il pulsante destro del mouse su **gateway PSTN**e quindi scegliere **nuovo gateway IP/PSTN**.

4.  Nella finestra di dialogo **Definisci nuovo gateway IP/PSTN** fare clic su **FQDN gateway o indirizzo IP**e quindi digitare il nome di dominio completo (FQDN) o l'indirizzo IP del gateway che si sta distribuendo nel sito della filiale.

5.  Fare clic su **porta di ascolto per gateway IP/PSTN**e quindi accettare i valori predefiniti.

6.  Nell'elenco **protocollo di trasporto SIP** fare clic sul protocollo di trasporto usato dal gateway e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Per motivi di sicurezza, ti consigliamo vivamente di usare un gateway PSTN che supporta TLS (Transport Layer Security).

    
    </div>

<div>


> [!TIP]  
> Utilizzare il cmdlet <STRONG>Set-CsPstnGateway</STRONG> per modificare le proprietà di un gateway PSTN. Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>, nella Guida di Lync Server Management Shell.



</div>

**Passaggio successivo** per la resilienza del sito di succursale: [configurazione degli utenti per la resilienza del sito di succursale in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

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

