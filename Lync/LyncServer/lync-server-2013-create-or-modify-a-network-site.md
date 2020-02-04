---
title: 'Lync Server 2013: Creare o modificare un sito di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network site
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398218(v=OCS.15)
ms:contentKeyID: 48183488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed721a48b12a497b25d58e7ebb65ff3a91980904
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a>Creare o modificare un sito di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-24_

Le distribuzioni di controllo di ammissione alle chiamate (CAC), E9-1-1 e bypass multimediale si basano sulla configurazione dei *siti di rete* definiti all'interno e sempre associati a un'area geografica di rete. Un sito di rete rappresenta una posizione di filiale, un set di edifici o un campus. I siti di rete rappresentano insiemi di subnet con larghezza di banda simile.

Usare le procedure seguenti per creare o modificare siti di rete. Se ad esempio sono già stati creati siti di rete per una sola funzionalità vocale, non è necessario creare nuovi siti di rete. altre caratteristiche vocali useranno gli stessi siti. Può tuttavia essere necessario modificare una definizione di sito di rete esistente per applicare impostazioni specifiche delle caratteristiche. Se ad esempio è stato creato un sito di rete per E9-1-1, è necessario modificare il sito di rete durante la distribuzione del controllo di ammissione delle chiamate per applicare un profilo dei criteri di larghezza di banda.

<div>


> [!NOTE]  
> Dove esistono, è possibile trovare esempi e requisiti specifici per i siti di rete in quanto riguardano una funzionalità vocale avanzata nella documentazione di distribuzione per ogni caratteristica: 
> <UL>
> <LI>
> <P><A href="lync-server-2013-configure-network-sites-for-cac.md">Configurare i siti di rete per CAC in Lync Server 2013</A></P></LI></UL>



</div>

Per informazioni dettagliate sull'uso dei siti di rete, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:

  - [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a>Creare un sito di rete

Creare un'area di rete che può essere usata tramite il controllo di ammissione alle chiamate, E9-1-1 o bypass multimediale.

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a>Per creare un sito di rete tramite Management Shell

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il cmdlet New-CsNetworkSite per creare siti di rete:
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    Ad esempio:
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    In questo esempio è stato creato un sito di rete denominato "Chicago" che si trova nell'area di rete "NorthAmerica".
    
    <div>
    

    > [!NOTE]  
    > L'area di rete NorthAmerica deve esistere già affinché il comando venga eseguito correttamente.

    
    </div>

3.  Per completare la creazione di siti di rete per la topologia, ripetere il passaggio 2 con le impostazioni per altri siti.

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a>Per creare un sito di rete tramite il pannello di controllo di Lync Server

1.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.

3.  Fare clic sul pulsante di spostamento del **sito** .

4.  Fare clic su **nuovo**.

5.  Nella pagina **nuovo sito** fare clic su **nome** e quindi digitare un nome per il sito di rete.

6.  Fare clic su **area geografica**e quindi fare clic su un'area nell'elenco.

7.  Facoltativamente, fare clic su **criteri di larghezza di banda**e quindi fare clic su un criterio di larghezza di banda nell'elenco.
    
    <div>
    

    > [!NOTE]  
    > I criteri di larghezza di banda sono necessari solo se si distribuisce il controllo di ammissione delle chiamate nel sito.

    
    </div>

8.  Facoltativamente, fare clic su **criteri posizione**e quindi fare clic su un criterio di posizione nell'elenco.
    
    <div>
    

    > [!NOTE]  
    > I criteri di posizione sono necessari solo se si distribuisce E9-1-1 nel sito.

    
    </div>

9.  Facoltativamente, fare clic su **Descrizione**e quindi digitare altre informazioni per descrivere questo sito di rete.

10. Fare clic su **Commit**.

11. Per completare la creazione di siti di rete per la topologia, ripetere i passaggi da 4 a 10 con le impostazioni per altri siti.

</div>

</div>

<div>

## <a name="modify-a-network-site"></a>Modificare un sito di rete

Modificare un'area di rete che può essere usata tramite il controllo di ammissione alle chiamate, E9-1-1 o bypass multimediale.

<div>

## <a name="to-modify-a-network-site"></a>Per modificare un sito di rete

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il cmdlet Set-CsNetworkSite per modificare i siti di rete:
    
        Set-CsNetworkSite -Identity <string>
    
    Ad esempio:
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    In questo esempio, il sito denominato "Albuquerque" viene spostato nell'area di rete "NorthAmerica". Per modificare la configurazione del sito di rete per distribuire il controllo di ammissione alle chiamate, E9-1-1 o bypass multimediale, modificare le impostazioni del sito di rete eseguendo il cmdlet Set-CsNetworkSite rispettivamente con il parametro BWPolicyProfileID o LocationPolicy.
    
    <div>
    

    > [!NOTE]  
    > Anche se il parametro BypassID esiste per il bypass multimediale, ti consigliamo vivamente di non eseguire l'override degli ID di bypass generati automaticamente. Non è necessario specificare parametri aggiuntivi per configurare un sito di rete per il bypass multimediale.

    
    </div>

3.  Per completare la modifica dei siti di rete per la topologia, ripetere il passaggio 2 con le impostazioni per altri siti.

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a>Per modificare un sito di rete tramite il pannello di controllo di Lync Server

1.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.

3.  Fare clic sul pulsante di spostamento del **sito** .

4.  Nella tabella fare clic sul sito di rete che si desidera modificare.

5.  Fare clic su **modifica**e quindi su **Mostra dettagli.**

6.  Nella pagina **modifica sito** modificare i valori delle impostazioni del sito di rete in base alle esigenze.

7.  Fare clic su **Commit**.

8.  Per completare la modifica dei siti di rete, ripetere i passaggi da 4 a 7 con le impostazioni per altri siti.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

