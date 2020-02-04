---
title: 'Lync Server 2013: Definire un Survivable Branch Appliance o un Survivable Branch Server'
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
ms.openlocfilehash: df5577ff0211afd005feb8fea4788598a03d536e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Definire un Survivable Branch Appliance o un Survivable Branch Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-07_

Eseguire questa procedura nel sito centrale se non è stata definita l'appliance o il server della filiale Survivable quando è stato aggiunto alla topologia.

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a>Per definire un Survivable Branch Appliance o Survivable Branch Server

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

2.  Nell'albero della console espandere il sito centrale, espandere **siti di succursale**e quindi espandere il nome del sito della filiale in cui si prevede di distribuire il Survivable Branch Appliance o Survivable Branch Server.

3.  Fare clic con il pulsante destro del mouse su **Survivable Branch Appliances**e quindi scegliere **Nuovo Survivable Branch Appliance**.
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>Survivable Branch Appliances</STRONG> è la posizione in cui puoi definire Survivable Branch Servers e Survivable Branch Appliances.

    
    </div>

4.  Nella finestra di dialogo **Definisci Survivable Branch Appliance** fare clic su **FQDN**, digitare il nome di dominio completo (FQDN) del Survivable Branch Appliance o Survivable Branch Server che verrà distribuito in questo sito della filiale e quindi fare clic su **Avanti**.
    
    <div>
    

    > [!IMPORTANT]  
    > Se si definisce un Survivable Branch Appliance, il nome immesso in <STRONG>FQDN</STRONG> deve essere uguale a quello dell'FQDN di Survivable Branch Appliance assegnato all'attributo <STRONG>servicePrincipalName</STRONG> . Per informazioni dettagliate, vedere <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">aggiungere un Survivable Branch Appliance a Active Directory in Lync Server 2013</A>.

    
    </div>

5.  Fare clic su **pool Front End**, fare clic sul server front-end (pool di servizi utente) nel sito centrale a cui si connette questo Survivable Branch Appliance o Survivable Branch Server e quindi fare clic su **Avanti**.

6.  Fare clic su **Edge Server**, fare clic sul pool di bordi in cui questo Survivable Branch Appliance o Survivable Branch Server si connetterà per consentire la connettività PSTN agli utenti remoti del sito della filiale e quindi fare clic su **Avanti**.

7.  Fare clic su **FQDN gateway o indirizzo IP**e quindi digitare il nome di dominio completo o l'indirizzo IP del peer del gateway a cui è associato il Survivable Branch Appliance o Survivable Branch Server per il routing delle chiamate PSTN in ingresso o in uscita.
    
    <div>
    

    > [!IMPORTANT]  
    > Se si definisce un Survivable Branch Appliance, si tratta del gateway a cui il Mediation Server all'interno del Survivable Branch Appliance si connetterà per la connettività PSTN.

    
    </div>

8.  Fare clic su **porta di ascolto per gateway IP/PSTN**e quindi accettare la porta predefinita.

9.  In **protocollo di trasporto SIP**fare clic sul protocollo di trasporto che verrà usato da Survivable Branch Appliance o Survivable Branch Server e quindi fare clic su **fine**.
    
    <div>
    

    > [!NOTE]  
    > Per motivi di sicurezza, ti consigliamo vivamente di usare Transport Layer Security (TLS). Se si definisce un Survivable Branch Appliance, vedere la documentazione del fornitore di Survivable Branch Appliance per verificare che il Survivable Branch Appliance supporti il protocollo TLS.

    
    </div>

10. Nell'albero della console fare clic con il pulsante destro del mouse sul nuovo dispositivo o server Survivable Branch, scegliere **topologia**e quindi fare clic su **pubblica**.

**Passaggio successivo**: [distribuire un Survivable Branch Appliance o un server con Lync Server 2013-attività del sito succursale](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

