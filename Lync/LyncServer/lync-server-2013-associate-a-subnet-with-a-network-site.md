---
title: 'Lync Server 2013: associare una subnet a un sito di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate a subnet with a network site
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48185043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 929448f14fbc21781b20d3849c5b409f120c0450
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a>Associare una subnet a un sito di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

Ogni subnet della rete deve essere associata a un sito di rete specifico, perché le informazioni sulla subnet vengono utilizzate per determinare il sito di rete in cui si trova un endpoint durante l'avvio di una nuova sessione. Quando la posizione di ogni parte di una sessione è nota, le funzionalità di VoIP aziendale avanzate possono applicare queste informazioni per determinare la modalità di gestione dell'installazione o del routing delle chiamate.

<div>


> [!IMPORTANT]  
> Tutti gli indirizzi IP pubblici configurati per i server perimetrali audio/video nella distribuzione devono essere aggiunti alle impostazioni di configurazione di rete. Questi indirizzi IP vengono aggiunti come subnet con una maschera di 32. Il sito di rete associato deve corrispondere al sito di rete configurato appropriato. Ad esempio, l'indirizzo IP pubblico che corrisponde al server a/V Edge nel sito centrale Chicago sarebbe NetworkSiteID Chicago. Per informazioni dettagliate sugli indirizzi IP pubblici, vedere <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine External a/V firewall and Port requirements for Lync Server 2013</A> nella documentazione relativa alla pianificazione.



</div>

<div>


> [!NOTE]  
> Viene generato un avviso Key Health Indicator (KHI) in cui viene specificato un elenco di indirizzi IP presenti nella rete che non sono associati a una subnet oppure la cui subnet non è associata a un sito di rete. Questo avviso non verrà generato più di una volta entro un periodo di 8 ore. Di seguito vengono riportati un esempio e le informazioni rilevanti dell'avviso:<BR><STRONG>Origine:</STRONG> Servizio criteri di larghezza di banda CS (Core)<BR><STRONG>Numero evento:</STRONG> 36034<BR><STRONG>Livello:</STRONG> 2<BR><STRONG>Descrizione:</STRONG> Le subnet per gli indirizzi IP seguenti: &lt;elenco di indirizzi&gt; IP non sono configurati o le subnet non sono associate a un sito di rete.<BR><STRONG>Causa:</STRONG> Le subnet per gli indirizzi IP corrispondenti sono mancanti nelle impostazioni di configurazione di rete o le subnet non sono associate a un sito di rete.<BR><STRONG>Soluzione:</STRONG> Aggiungere le subnet corrispondenti all'elenco di indirizzi IP nelle impostazioni di configurazione di rete e associare ogni subnet a un sito di rete.<BR>Ad esempio, se l'elenco di indirizzi IP nell'avviso specifica 10.121.248.226 e 10.121.249.20, questi indirizzi IP non sono associati a una subnet o la subnet a cui sono associati non appartiene a un sito di rete. Se 10.121.248.0/24 e 10.121.249.0/24 sono le subnet corrispondenti per questi indirizzi, è possibile risolvere il problema in questo modo: 
> <OL>
> <LI>
> <P>Verificare che l'indirizzo IP 10.121.248.226 sia associato alla subnet 10.121.248.0/24 e che l'indirizzo IP 10.121.249.20 sia associato alla subnet 10.121.249.0/24.</P>
> <LI>
> <P>Verificare che le subnet 10.121.248.0/24 e 10.121.249.0/24 siano associate ognuna a un sito di rete.</P></LI></OL>



</div>

Per informazioni dettagliate sull'utilizzo delle subnet di rete, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:

  - [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> Se si utilizza un numero elevato di subnet, è consigliabile utilizzare un file con valori delimitati da virgole (CSV) per associare le subnet ai siti. Il file CSV deve avere le quattro colonne seguenti: <STRONG>IPAddress</STRONG>, <STRONG>mask</STRONG>, <STRONG>Description</STRONG>, <STRONG>NetworkSiteID</STRONG>.



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a>Per associare una subnet a un sito di rete utilizzando Management Shell

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire il cmdlet **New-CsNetworkSubnet** per associare una subnet a un sito di rete:
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    Ad esempio:
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    In questo esempio viene creata un'associazione tra la subnet 172.11.12.13 e il sito di rete "Chicago".

3.  Ripetere il passaggio 2 per tutte le subnet della topologia.

</div>

<div>

## <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>Per associare subnet a siti di rete mediante l'importazione di un file CSV

1.  Creare un file CSV che includa tutte le subnet che si desidera aggiungere. Ad esempio, creare un file denominato **subnet. csv** con il seguente contenuto:
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Eseguire il cmdlet seguente per importare **subnet. csv**e quindi archiviarne il contenuto nell'archivio di gestione di Lync Server:
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a>Per associare una subnet a un sito di rete utilizzando il pannello di controllo di Lync Server

1.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.

3.  Fare clic sul pulsante di spostamento della **subnet** .

4.  Fare clic su **Nuova regola**.

5.  Nella pagina **nuova subnet** fare clic su **ID Subnet**e quindi digitare il primo indirizzo nell'intervallo di indirizzi IP definito dalla subnet che si desidera associare a un sito di rete.

6.  Fare clic su **maschera**e quindi digitare la maschera di forma da applicare alla subnet.

7.  Fare clic su **ID sito di rete**e quindi selezionare l'ID sito del sito a cui si sta aggiungendo la subnet.
    
    <div>
    

    > [!NOTE]  
    > Se non sono ancora stati creati siti di rete, l'elenco sarà vuoto. Per informazioni dettagliate sulla procedura, vedere <A href="lync-server-2013-create-or-modify-a-network-site.md">creare o modificare un sito di rete in Lync Server 2013</A>. È inoltre possibile recuperare gli ID di sito per la distribuzione eseguendo il cmdlet <STRONG>Get-CsNetworkSite</STRONG> . Per informazioni dettagliate, vedere la documentazione relativa a Lync Server Management Shell.

    
    </div>

8.  Facoltativamente, fare clic su **Descrizione**e quindi digitare ulteriori informazioni per descrivere la subnet.

9.  Fare clic su **Commit**.

Ripetere questi passaggi per aggiungere altre subnet a un sito di rete.

</div>

</div>

<span> </span>

</div>

</div>

</div>

