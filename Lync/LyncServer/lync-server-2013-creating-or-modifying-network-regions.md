---
title: 'Lync Server 2013: creazione o modifica di aree di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b3ca5d44fd2278ffee8a3e9dd4494575cc64c65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a>Creazione o modifica di aree di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Un'area geografica di rete interconnette varie parti di una rete in più aree geografiche. Ogni area di rete deve essere associata a un sito centrale. Il sito centrale è il sito centro dati in cui è in uso il servizio criteri di larghezza di banda di controllo delle chiamate (CAC). È possibile usare il pannello di controllo di Lync Server per configurare le aree di rete. Le aree di rete includono impostazioni che determinano se i percorsi alternativi tramite Internet sono consentiti per le connessioni audio e video. Dal pannello di controllo di Lync Server è possibile creare, modificare o eliminare un'area geografica di rete. Usare questo argomento per creare e modificare le aree di rete. Per informazioni dettagliate sull'eliminazione delle aree di rete esistenti, vedere [eliminazione di aree di rete esistenti in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).

<div>

## <a name="to-create-a-network-region"></a>Per creare un'area di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **area geografica**.

4.  Nella pagina **area** fare clic su **nuovo**.

5.  Nella pagina **nuova area** Digitare un valore nel campo **nome** . Questo valore deve essere univoco all'interno della distribuzione di Microsoft Lync Server 2013.

6.  Nell'elenco a discesa **sito centrale** selezionare il sito centrale per l'area di rete.

7.  La casella di controllo **Attiva percorso alternativo audio** è selezionata per impostazione predefinita. Questo campo determina se le chiamate audio verranno instradate tramite un percorso alternativo se la larghezza di banda adeguata non esiste nel percorso principale. Deselezionare questa casella di controllo solo se è necessario disattivare l'offload su Internet. Se le chiamate saranno chiamate Internet, questa casella di controllo deve essere selezionata, indipendentemente dalle impostazioni di larghezza di banda.

8.  La casella di controllo **Attiva percorso alternativo video** è selezionata per impostazione predefinita. Questo campo determina se le videochiamate verranno instradate tramite un percorso alternativo se la larghezza di banda adeguata non esiste nel percorso principale. Deselezionare questa casella di controllo solo se è necessario disattivare l'offload su Internet. Se le chiamate saranno chiamate Internet, questa casella di controllo deve essere selezionata, indipendentemente dalle impostazioni di larghezza di banda.

9.  Opzionale Digitare un valore nel campo **Description** per ottenere altre informazioni sull'area geografica che non può essere espressa solo dal nome.

10. Fare clic su **Commit**.

La tabella **siti associati** non viene usata per la creazione di un'area di rete. Quando si crea o si modifica il sito, si associa un sito a un'area geografica. Per informazioni dettagliate, vedere [creazione o modifica di siti di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).

</div>

<div>

## <a name="to-modify-a-network-region"></a>Per modificare un'area di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **area geografica**.

4.  Nella pagina **area** fare clic sull'area che si vuole modificare.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.

6.  Nella pagina **modifica area** è possibile modificare le impostazioni per l'abilitazione e la disabilitazione di percorsi alternativi audio e video e modificare la descrizione (per informazioni dettagliate, vedere la sezione "per creare un'area di rete" in questo argomento.

7.  Fare clic su **Commit**.

Non è possibile modificare i **siti associati** in questa pagina. L'elenco dei siti associati viene fornito per il riferimento, in modo da sapere quali siti verranno modificati quando si modificano le impostazioni dell'area geografica.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Eliminazione delle aree di rete esistenti in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md)  
[Configurare le aree di rete per CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)  


[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

