---
title: 'Lync Server 2013: configurare DNS per il supporto di Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9ccf25c2bbaf6c77c72d35f1fa5ac82fd67d011
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537153"
---
# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a>Configurare DNS per il supporto Edge in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-15_

È necessario configurare record DNS (Domain Name System) per le interfacce perimetrali interne ed esterne, incluse le interfacce di server perimetrali e proxy inversi. Per impostazione predefinita, i server perimetrali non vengono aggiunti a un dominio e non avranno un nome di dominio completo (Fully Qualified Domain Name). Il server perimetrale è denominato solo dal nome breve (computer) e non da un nome di dominio completo. Tuttavia, il generatore di topologie utilizza FQDN e non nomi brevi. Il nome del server perimetrale deve corrispondere all'FQDN utilizzato dal generatore di topologie. A tale scopo, è possibile definire un suffisso DNS che, se combinato con il nome del computer, comporta l'FQDN previsto. Utilizzare la procedura seguente in "per aggiungere il suffisso DNS al nome del computer nel server perimetrale che non è aggiunto a un dominio" per aggiungere il suffisso DNS al nome del computer.

<div>


> [!NOTE]  
> Per impostazione predefinita, il DNS utilizza un algoritmo round robin per ruotare l'ordine dei dati del record di risorse restituiti nelle risposte di query in cui sono presenti più record di risorse dello stesso tipo per un nome di dominio DNS sottoposto a query. Il bilanciamento del carico DNS di Lync Server 2013 dipende dal Round Robin DNS come parte del meccanismo di bilanciamento del carico DNS. Verificare che l'impostazione Round Robin non sia stata disattivata. Se si utilizza un server DNS che non esegue un sistema operativo Windows, verificare che l'ordinamento dei record di risorse Round Robin sia abilitato.



</div>

Utilizzare le procedure seguenti in "**per creare un record DNS SRV**" per creare e verificare ogni record DNS SRV. Utilizzare la procedura descritta in "**per creare un record a DNS**" per definire i record DNS necessari per l'accesso degli utenti esterni. Per verificare che i record siano configurati e funzionino correttamente, vedere la sezione relativa**alla verifica di un record DNS**in questo argomento. Per informazioni dettagliate su ogni record necessario per supportare l'accesso degli utenti esterni, vedere [determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a>Per aggiungere un suffisso DNS al nome del computer in un server perimetrale che non fa parte di un dominio

1.  Nel computer fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Computer** e quindi scegliere **Proprietà**.

2.  In **Impostazioni relative a nome computer, dominio e gruppo di lavoro** fare clic su **Cambia impostazioni**.

3.  Nella scheda **Nome computer** fare clic su **Cambia**.

4.  In **Cambiamenti dominio/nome computer** fare clic su **Altro**.

5.  In **Suffisso DNS e nome NetBIOS del computer** digitare il nome del dominio interno (ad esempio corp.contoso.com) in **Suffisso DNS primario del computer** e quindi fare clic su **OK** tre volte.

6.  Riavviare il computer.

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a>Per creare un record SRV DNS

1.  Nel server DNS appropriato fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, **Strumenti di amministrazione** e quindi **DNS**.
    
    <div>
    

    > [!IMPORTANT]  
    > È necessario configurare DNS in modo che vi siano: 1) voci DNS esterne per le ricerche DNS esterne da parte degli utenti remoti e dei partner federati; 2) le voci per le ricerche DNS per l'utilizzo da parte dei server perimetrali all'interno della rete (noto anche come DMZ, area demilitarizzata e subnet schermata), inclusi i record per i server interni che eseguono Lync Server 2013; e 3) le voci DNS interne per le ricerche eseguite dai client e dai server interni che eseguono Lync Server 2013.

    
    </div>

2.  Nell'albero della console per il dominio SIP espandere **zone di ricerca diretta**e quindi fare clic con il pulsante destro del mouse sul dominio in cui è installato Lync Server 2013.

3.  Scegliere **Altri nuovi record**.

4.  In **Selezionare tipo di record di risorsa** digitare **Posizione servizio (SRV)** e quindi su fare clic su **Crea record**.

5.  Specificare tutte le informazioni necessarie per il record SRV DNS.

</div>

<div>

## <a name="to-create-a-dns-a-record"></a>Per creare un record A DNS

1.  Nel server DNS fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, **Strumenti di amministrazione** e quindi **DNS**.

2.  Nell'albero della console per il dominio SIP espandere **zone di ricerca diretta**e quindi fare clic con il pulsante destro del mouse sul dominio in cui è installato Lync Server 2013.

3.  Scegliere **Nuovo host (A o AAAA)**.

4.  Specificare tutte le informazioni necessarie per il record SRV DNS.

</div>

<div>

## <a name="to-verify-a-dns-record"></a>Per verificare un record DNS

1.  Accedere a un computer client nel dominio.

2.  Fare clic sul pulsante **Start** e quindi scegliere **Esegui**.

3.  Al prompt dei comandi eseguire il comando seguente:
    
        nslookup <FQDN edge interface>

4.  Verificare che la risposta ricevuta venga risolta nell'indirizzo IP appropriato per l'FQDN.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare un record DNS SRV per l'integrazione con la messaggistica unificata di Exchange ospitata](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[Determinare i requisiti DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

