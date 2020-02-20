---
title: 'Lync Server 2013: configurare le schede di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd2609c8b8a900b9c970943a2f24bc0462eafb85
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a>Configurare le schede di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-07_

È necessario assegnare uno o più indirizzi IP alla scheda di rete esterna e almeno un indirizzo IP alla scheda di rete interna.

Nelle procedure riportate di seguito, il server che esegue Forefront Threat Management Gateway (TMG) 2010 o il routing delle richieste di applicazioni di Internet Information Server dispone di due schede di rete:

  - Una scheda di rete pubblica, o esterna, per i client che tentano di connettersi al sito Web, in genere tramite Internet.

  - Interfaccia di rete privata o interna per i server interni che eseguono Lync Server che ospitano i servizi Web.

<div>


> [!IMPORTANT]  
> Analogamente ai server perimetrali, è possibile impostare il gateway predefinito solo nella scheda di rete esterna. Il gateway predefinito sarà l'indirizzo IP del router o del firewall esposto verso l'esterno che indirizza il traffico verso Internet. Per il traffico destinato dal proxy inverso alla scheda di rete interna, è necessario utilizzare route statiche persistenti (come il comando route in Windows Server) per tutte le subnet che contengono server a cui fanno riferimento le regole di pubblicazione Web. L'impostazione di una route persistente non determina la creazione di un router da parte del computer. Se l'inoltro IP non è abilitato, il computer agisce solo per indirizzare il traffico specifico destinato a un'altra rete all'interfaccia appropriata. Si tratta essenzialmente di impostare due gateway, uno come predefinito che punta alle reti esterne e uno per il traffico destinato all'interfaccia interna e a un router o a un'altra rete.<BR>La creazione di route persistenti per tutte le subnet, tuttavia, potrebbe non essere necessaria se i router della rete sono configurati per riepilogare le route. Creare una route persistente verso la rete in cui è stato definito il router e utilizzare il router come gateway predefinito. Se non si è sicuri della configurazione della rete e sono necessarie istruzioni sulle route persistenti che è necessario creare, rivolgersi ai tecnici di rete aziendali.<BR>Il proxy inverso deve essere in grado di risolvere i record host DNS (A) per il server Director interno o i nomi FQDN del pool di hop successivo utilizzati nelle regole di pubblicazione Web. Analogamente ai server perimetrali, per motivi di sicurezza, si consiglia di non configurare un proxy inverso per l'utilizzo di un server DNS che si trova nella rete interna. Ciò significa che sono necessari server DNS nel perimetro oppure voci di file HOSTS nel proxy inverso per la risoluzione di ognuno di questi FQDN nell'indirizzo IP interno dei server.



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a>Per configurare le schede di rete nel computer proxy inverso

1.  Nel server Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2 in esecuzione come proxy inverso, aprire **Impostazioni scheda di modifica** facendo clic sul pulsante **Start**, scegliendo **Pannello di controllo**, facendo clic su **Centro rete e condivisione**e quindi scegliendo **Cambia impostazioni scheda**.

2.  Fare clic con il pulsante destro del mouse sulla connessione di rete esterna che si desidera utilizzare per l'interfaccia interna e quindi scegliere **Proprietà**.

3.  Nella pagina **Proprietà** fare clic sulla scheda **Rete**, selezionare **Protocollo Internet versione 4 (TCP/IPv4)** nell'elenco **La connessione utilizza gli elementi seguenti** e quindi fare clic su **Proprietà**.

4.  Nella pagina **Proprietà TCP/IP** configurare gli indirizzi IP in base alla subnet di rete a cui è collegata la scheda di rete.
    
    <div>
    

    > [!NOTE]  
    > Se il proxy inverso è già utilizzato da altre applicazioni che utilizzano HTTPS/TCP/443, ad esempio, per la pubblicazione di Outlook Web Access, è necessario aggiungere un altro indirizzo IP in modo che sia possibile pubblicare i servizi Web di Lync Server 2013 su HTTPS/TCP/443 senza interferire con le regole e i listener Web esistenti oppure è necessario sostituire il certificato esistente con uno che aggiunge i nuovi nomi FQDN esterni al nome alternativo del soggetto.

    
    </div>

5.  Fare clic su **OK** e quindi nuovamente su **OK**.

6.  In **Connessioni di rete** fare clic con il pulsante destro del mouse sulla connessione di rete interna che si desidera utilizzare per l'interfaccia interna e quindi scegliere **Proprietà**.

7.  Ripetere i passaggi da 3 a 5 per configurare la connessione di rete interna.

</div>

</div>

<span> </span>

</div>

</div>

</div>

