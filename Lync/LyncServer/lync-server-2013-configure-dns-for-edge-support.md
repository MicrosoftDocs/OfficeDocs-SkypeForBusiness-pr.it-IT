---
title: 'Lync Server 2013: Configurare DNS per il supporto dei componenti perimetrali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79e1712b3425c7cce4020799b37f10aba894aeb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a>Configurare DNS per il supporto dei componenti perimetrali in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-15_

È necessario configurare i record DNS (Domain Name System) per le interfacce di Edge interne ed esterne, tra cui le interfacce Edge Server e proxy inverso. Per impostazione predefinita, i server perimetrali non vengono uniti a un dominio e non avranno un nome di dominio completo (nome di dominio completo). Il server perimetrale viene indicato solo dal nome short (computer), non da un nome di dominio completo. Tuttavia, generatore di topologie usa nomi di dominio completi, non brevi. Il nome del server perimetrale deve corrispondere all'FQDN usato da generatore di topologie. A questo scopo, devi definire un suffisso DNS che, se combinato con il nome del computer, restituisce l'FQDN previsto. Usare la procedura seguente in "per aggiungere il suffisso DNS al nome del computer in e Edge Server che non è stato aggiunto a un dominio" per aggiungere il suffisso DNS al nome del computer.

<div>


> [!NOTE]  
> Per impostazione predefinita, il DNS usa un algoritmo round robin per ruotare l'ordine dei dati del record di risorse restituiti nelle risposte alle query in cui sono presenti più record di risorse dello stesso tipo per un nome di dominio DNS interrogato. Il bilanciamento del carico DNS di Lync Server 2013 dipende dal DNS round-robin come parte del meccanismo di bilanciamento del carico DNS. Verificare che l'impostazione Round Robin non sia stata disattivata. Se si usa un server DNS che non esegue un sistema operativo Windows, verificare che l'ordinamento dei record di risorse Round Robin sia abilitato.



</div>

Usare le procedure seguenti in "**per creare un record SRV DNS**" per creare e verificare ogni record SRV DNS. Usare la procedura descritta in "**per creare un record DNS**" per definire i record DNS necessari per l'accesso degli utenti esterni. Per verificare che i record siano configurati e funzioni correttamente, vedere la sezione relativa**alla verifica di un record DNS**in questo argomento. Per informazioni dettagliate su ogni record necessario per supportare l'accesso degli utenti esterni, vedere [determinare i requisiti DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a>Per aggiungere il suffisso DNS al nome del computer in un server perimetrale che non è stato aggiunto a un dominio

1.  Nel computer fare clic su **Start**, fare clic con il pulsante destro del mouse su **computer**e quindi scegliere **proprietà**.

2.  In **Impostazioni nome computer, dominio e gruppo**di lavoro fare clic su **Cambia impostazioni**.

3.  Nella scheda **nome computer** fare clic su **Cambia**.

4.  In **nome computer/Domain Changes**fare clic su **altro**.

5.  In **suffisso DNS e nome computer NetBIOS**, in **suffisso DNS primario del computer**, digitare il nome del dominio interno, ad esempio Corp.contoso.com, e quindi fare clic su **OK** tre volte.

6.  Riavviare il computer.

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a>Per creare un record SRV DNS

1.  Nel server DNS appropriato fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, strumenti di **Amministrazione**e quindi fare clic su **DNS**.
    
    <div>
    

    > [!IMPORTANT]  
    > È necessario configurare il DNS in modo che siano presenti: 1) voci DNS esterne per le ricerche DNS esterne da parte di utenti remoti e partner federati; 2) le voci per le ricerche DNS per l'uso da parte di Edge Server all'interno della rete perimetrale (nota anche come DMZ, zona demilitarizzata e subnet schermata), inclusi i record per i server interni che usano Lync Server 2013; e 3) voci DNS interne per le ricerche dei client e dei server interni che utilizzano Lync Server 2013.

    
    </div>

2.  Nell'albero della console per il dominio SIP espandere **aree di ricerca in avanti**e quindi fare clic con il pulsante destro del mouse sul dominio in cui è installato Lync Server 2013.

3.  Fare clic su **altri nuovi record**.

4.  In **selezionare un tipo di record di risorse**digitare **posizione servizio (SRV)** e quindi fare clic su **Crea record**.

5.  Fornisci tutte le informazioni necessarie per il record SRV DNS.

</div>

<div>

## <a name="to-create-a-dns-a-record"></a>Per creare un record DNS

1.  Nel server DNS fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, strumenti di **Amministrazione**e quindi fare clic su **DNS**.

2.  Nell'albero della console per il dominio SIP espandere **aree di ricerca in avanti**e quindi fare clic con il pulsante destro del mouse sul dominio in cui è installato Lync Server 2013.

3.  Fare clic su **nuovo host (A)**.

4.  Fornisci tutte le informazioni necessarie per il record SRV DNS.

</div>

<div>

## <a name="to-verify-a-dns-record"></a>Per verificare un record DNS

1.  Accedere a un computer client nel dominio.

2.  Fare clic sul pulsante **Start**e quindi su **Esegui**.

3.  Al prompt dei comandi eseguire il comando seguente:
    
        nslookup <FQDN edge interface>

4.  Verificare di ricevere una risposta che venga risolta nell'indirizzo IP appropriato per il nome di dominio completo.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare un Record DNS SRV per l'integrazione con la messaggistica unificata di Exchange ospitata](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[Determinare i requisiti di DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

