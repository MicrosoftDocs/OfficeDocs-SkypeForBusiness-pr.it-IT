---
title: 'Lync Server 2013: creazione o modifica di siti di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bb09dfcd490d47de1bbfbbde48f538e95fc64cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a>Creazione o modifica di siti di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-08_

I siti di rete sono gli uffici o i percorsi configurati in ogni area geografica di un controllo di ammissione alle chiamate (CAC) o una distribuzione avanzata di 9-1-1. È possibile usare il pannello di controllo di Microsoft Lync Server 2013 per configurare i siti e associarli alle aree geografiche. Ad esempio, un'area di rete per il Nord America potrebbe essere associata a siti di reti come Chicago, Redmond e Vancouver. È necessario creare un sito di rete CAC per ogni sito all'interno di un'organizzazione, anche se il sito non ha limitazioni di larghezza di banda. Dal pannello di controllo di Lync Server è possibile creare, modificare ed eliminare siti di rete. Usare le procedure seguenti per creare o modificare un sito di rete. Per informazioni dettagliate sull'eliminazione di un sito di rete esistente, vedere [eliminazione di un sito di rete esistente in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).

<div>

## <a name="to-create-a-network-site"></a>Per creare un sito di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **sito**.

4.  Nella pagina del **sito** fare clic su **nuovo**.

5.  In **nuovo sito**Digitare un nome per il sito nel campo **nome** .
    
    <div>
    

    > [!NOTE]  
    > I nomi dei siti devono essere univoci all'interno della distribuzione di Lync Server 2013.

    
    </div>

6.  Nell'elenco a discesa **Region** selezionare un'area di rete da associare al sito.

7.  Opzionale Se si vogliono inserire limitazioni della larghezza di banda per le chiamate audio o video a questo sito, selezionare il profilo dei criteri di larghezza di banda con le impostazioni appropriate nell'elenco a discesa **criteri di larghezza** di banda.
    
    <div>
    

    > [!NOTE]  
    > È possibile visualizzare i dettagli dei profili di criteri di larghezza di banda disponibili oppure creare un nuovo profilo per i criteri di larghezza di banda nella pagina del <STRONG>profilo dei criteri</STRONG> del gruppo <STRONG>configurazione di rete</STRONG> . Per informazioni dettagliate, vedere <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">creazione o modifica di profili dei criteri di larghezza di banda in Lync Server 2013</A>.

    
    </div>

8.  Opzionale Per specificare le impostazioni di posizione per questo sito, selezionare un criterio di posizione dall'elenco a discesa **criteri di posizione** .
    
    <div>
    

    > [!NOTE]  
    > Il criterio posizione assegna al sito specifiche impostazioni avanzate di 9-1-1 (E9-1-1) e di posizione del client. È possibile visualizzare i dettagli dei criteri di posizione disponibili oppure creare un nuovo criterio di posizione dalla pagina <STRONG>criteri posizione</STRONG> del gruppo Configurazione di <STRONG>rete</STRONG> . Per informazioni dettagliate, vedere <A href="lync-server-2013-viewing-location-policy-information.md">visualizzazione delle informazioni sui criteri di posizione in Lync Server 2013</A>.

    
    </div>

9.  Opzionale Digitare un valore nel campo **Description** per ottenere altre informazioni su questo sito che non possono essere espresse solo dal nome.

10. Fare clic su **Commit**.
    
    <div>
    

    > [!NOTE]  
    > Quando si crea un nuovo sito di rete, non si usa la tabella <STRONG>subnet associata</STRONG> . Si associa una subnet a un sito quando si crea o si modifica la subnet. Per informazioni dettagliate, vedere <A href="lync-server-2013-create-or-modify-network-subnets.md">creare o modificare subnet di rete in Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a>Per modificare un sito di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **sito**.

4.  Nella pagina del **sito** fare clic sul sito che si desidera modificare.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.

6.  Nella pagina **modifica sito** è possibile modificare la descrizione, l'area geografica, il profilo dei criteri di larghezza di banda e i criteri di posizione associati al sito. Per informazioni dettagliate, vedere la sezione "per creare un sito di rete" più indietro in questo argomento.

7.  Fare clic su **Commit**.

Non è possibile modificare la tabella **subnet associata** in questa pagina. L'elenco delle subnet associate viene fornito come riferimento in modo da essere a conoscenza delle subnet che verranno modificate quando si modificano le impostazioni del sito.

</div>

<div>

## <a name="to-delete-a-network-site"></a>Per eliminare un sito di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **sito**.

4.  Nella pagina del **sito** fare clic sul sito che si desidera eliminare.
    
    <div>
    

    > [!NOTE]  
    > È possibile eliminare più di un sito alla volta. Per eseguire questa operazione, premere CTRL e selezionare più siti tenendo premuto il tasto CTRL. In alternativa, per selezionare tutti i siti, fare clic su <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>modifica</STRONG> .

    
    </div>

5.  Scegliere **Elimina**dal menu **modifica** .

6.  Fare clic su **OK**.
    
    <div>
    

    > [!WARNING]  
    > Non è possibile rimuovere un sito di rete se associato a una subnet di rete. Se si tenta di rimuovere un sito associato a una subnet, viene visualizzato un messaggio di errore. Per verificare se un sito è associato a qualsiasi subnet, fare clic sul sito e quindi su <STRONG>Mostra dettagli</STRONG> dal menu <STRONG>modifica</STRONG> .

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Eliminazione di un sito di rete esistente in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md)  


[New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

