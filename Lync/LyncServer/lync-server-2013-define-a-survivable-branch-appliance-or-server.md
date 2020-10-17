---
title: 'Lync Server 2013: define a Survivable Branch Appliance o server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee83a532f3e378cf0beb0d9d09a08e935cf56247
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516373"
---
# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Definire un Survivable Branch Appliance o un server di succursale in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-07_

Eseguire questa procedura presso il sito centrale se la Survivable Branch Appliance o il Survivable Branch Server non è stato definito quando è stato aggiunto alla topologia.

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a>Per definire un Survivable Branch Appliance o un Survivable Branch Server

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**, quindi fare clic su **Generatore di topologie di Lync Server**.

2.  Nell'albero della console espandere il sito centrale, espandere **siti di succursale**e quindi espandere il nome del sito di succursale in cui si intende distribuire il Survivable Branch Appliance o il Survivable Branch Server.

3.  Fare clic con il pulsante destro del mouse su **Survivable Branch Appliance**e quindi scegliere **Nuovo Survivable Branch Appliance**.
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>Survivable Branch Appliances</STRONG> è il luogo in cui vengono definiti Survivable Branch Server e Survivable Branch Appliance.

    
    </div>

4.  Nella finestra di dialogo **Definisci Survivable Branch Appliance** fare clic su **FQDN**, digitare il nome di dominio completo (FQDN) del Survivable Branch Appliance o Survivable Branch Server che si desidera distribuire in questo sito di succursale e quindi fare clic su **Avanti**.
    
    <div>
    

    > [!IMPORTANT]  
    > Se si sta definendo un Survivable Branch Appliance, il nome immesso in <STRONG>FQDN</STRONG> deve corrispondere a quello dell'FQDN di Survivable Branch Appliance assegnato all'attributo <STRONG>servicePrincipalName</STRONG> . Per ulteriori informazioni, vedere <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">aggiungere un Survivable Branch Appliance a Active Directory in Lync Server 2013</A>.

    
    </div>

5.  Fare clic su **pool Front End**, fare clic sul front end server (pool di servizi utente) nel sito centrale in cui si connetterà il Survivable Branch Appliance o il Survivable Branch Server e quindi fare clic su **Avanti**.

6.  Fare clic su **server perimetrale**, fare clic sul pool perimetrale che è possibile connettere a Survivable Branch Appliance o Survivable Branch Server per garantire la connettività PSTN agli utenti remoti del sito di succursale e quindi fare clic su **Avanti**.

7.  Fare clic su **FQDN gateway o indirizzo IP**e quindi digitare il nome di dominio completo o l'indirizzo IP del peer gateway a cui è associato il Survivable Branch Appliance o il Survivable Branch Server per il routing delle chiamate PSTN in ingresso o in uscita.
    
    <div>
    

    > [!IMPORTANT]  
    > Se si sta definendo un Survivable Branch Appliance, questo è il gateway a cui il Mediation Server all'interno del Survivable Branch Appliance si connetterà per la connettività PSTN.

    
    </div>

8.  Fare clic su **Porta di attesa per gateway IP/PSTN** e quindi accettare la porta predefinita.

9.  In **Protocollo trasporto SIP**fare clic sul protocollo di trasporto che verrà utilizzato dal Survivable Branch Appliance o Survivable Branch Server e quindi fare clic su **fine**.
    
    <div>
    

    > [!NOTE]  
    > Per motivi di sicurezza, è consigliabile utilizzare Transport Layer Security (TLS). Se si sta definendo un Survivable Branch Appliance, consultare la documentazione del relativo fornitore per verificare che supporti il protocollo TLS.

    
    </div>

10. Nell'albero della console fare clic con il pulsante destro del mouse sul nuovo Survivable Branch Appliance o Survivable Branch Server, scegliere **Topologia** e quindi fare clic su **Pubblica**.

**Passaggio successivo**: [distribuire un Survivable Branch Appliance or Server with Lync Server 2013-Branch site Task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

