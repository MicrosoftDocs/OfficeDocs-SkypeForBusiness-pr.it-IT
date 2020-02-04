---
title: 'Lync Server 2013: Configurare le schede di rete'
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
ms.openlocfilehash: 30889a6b145e7256a313c4deedafc74d99499719
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a>Configurare le schede di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-07_

È necessario assegnare uno o più indirizzi IP alla scheda di rete esterna e almeno un indirizzo IP alla scheda di rete interna.

Nelle procedure seguenti il server che utilizza Forefront Threat Management Gateway (TMG) 2010 o Internet Information Server Request Routing richiede due schede di rete:

  - Una scheda di rete pubblica o esterna, per i client che tentano di connettersi al sito Web, ovvero in genere tramite Internet.

  - Interfaccia di rete privata o interna per i server interni che esegue Lync Server che ospitano servizi Web.

<div>


> [!IMPORTANT]  
> Analogamente agli Edge Server, è possibile impostare il gateway predefinito solo sulla scheda di rete esterna. Il gateway predefinito sarà l'indirizzo IP del router o del firewall di fronte esterno che indirizza il traffico a Internet. Per il traffico destinato al proxy inverso alla scheda di rete interna, è necessario usare route statiche permanenti, ad esempio il comando instrada in Windows Server, per tutte le subnet che contengono server a cui fanno riferimento le regole di pubblicazione Web. L'impostazione di una route persistente non fa sì che il computer diventi un router. Se l'inoltro IP non è abilitato, il computer agisce solo per indirizzare il traffico specifico destinato a un'altra rete all'interfaccia appropriata. Si tratta essenzialmente di impostare due gateway, uno come predefinito che punta alle reti esterne e uno per il traffico destinato all'interfaccia interna e a un router o a un'altra rete.<BR>Tuttavia, potrebbe non essere necessario creare route permanenti per tutte le subnet se i router della rete sono configurati per riepilogare le route. Creare una route persistente per la rete in cui è definito il router e usare il router come gateway predefinito. Se non si sa in che modo la rete è configurata e occorrono indicazioni su quali route permanenti devono essere create, consultare gli ingegneri di rete della società.<BR>Il proxy inverso deve essere in grado di risolvere i record host DNS (A) per il Director interno o i nomi FQDN del pool hop successivo usati nelle regole di pubblicazione Web. Come per i server perimetrali, per motivi di sicurezza, è consigliabile non configurare un proxy inverso per l'uso di un server DNS nella rete interna. Questo significa che è necessario disporre di server DNS nel perimetro oppure che occorrono voci di file HOSTs nel proxy inverso che risolve ognuno di questi FQDN nell'indirizzo IP interno dei server.



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a>Per configurare le schede della scheda di rete nel computer proxy inverso

1.  Nel server Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2 in uso come proxy inverso, aprire **le impostazioni della scheda Modifica** facendo clic sul pulsante **Start**, scegliendo il **Pannello di controllo**, facendo clic su **Centro rete e condivisione**e quindi scegliendo **Cambia impostazioni adattatore**.

2.  Fare clic con il pulsante destro del mouse sulla connessione di rete esterna che si vuole usare per l'interfaccia esterna e quindi scegliere **Proprietà**.

3.  Nella pagina **Proprietà** fare clic sulla scheda **rete** , fare clic su **protocollo Internet versione 4 (TCP/IPv4)** nella finestra di dialogo **questa connessione usa l'elenco elementi seguenti** e quindi fare clic su **Proprietà**.

4.  Nella pagina delle **proprietà del protocollo Internet (TCP/IP)** configurare gli indirizzi IP appropriati per la subnet di rete a cui è collegata la scheda di rete.
    
    <div>
    

    > [!NOTE]  
    > Se il proxy inverso viene già usato da altre applicazioni che usano HTTPS/TCP/443, ad esempio, per la pubblicazione di Outlook Web Access, è necessario aggiungere un altro indirizzo IP in modo da poter pubblicare i servizi Web di Lync Server 2013 in HTTPS/TCP/443 senza interferire con le regole e i listener Web esistenti oppure sostituire il certificato esistente con uno che aggiunge i nuovi nomi FQDN esterni al nome alternativo dell'oggetto.

    
    </div>

5.  Fare clic su **OK**e quindi su **OK**.

6.  In **connessioni di rete**fare clic con il pulsante destro del mouse sulla connessione di rete interna che si vuole usare per l'interfaccia interna e quindi scegliere **Proprietà**.

7.  Ripetere i passaggi da 3 a 5 per configurare la connessione di rete interna.

</div>

</div>

<span> </span>

</div>

</div>

</div>

