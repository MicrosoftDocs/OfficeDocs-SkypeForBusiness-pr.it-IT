---
title: 'Lync Server 2013: creazione o modifica dei profili dei criteri di larghezza di banda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38f44d759a77fea03b285d2e1af10838d508a6ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a>Creazione o modifica dei profili dei criteri di larghezza di banda in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-15_

Nell'ambito del controllo di ammissione di chiamata (CAC) viene usato un criterio di larghezza di banda per definire le limitazioni della larghezza di banda per determinate modalità. In Microsoft Lync Server 2013 solo le modalità audio e video possono essere assegnate alle limitazioni della larghezza di banda. Puoi impostare limitazioni generali della larghezza di banda e limitazioni della sessione. È possibile usare il pannello di controllo di Lync Server per creare, modificare o eliminare un profilo contenitore per questi criteri. Ogni profilo dei criteri di larghezza di banda può essere associato a uno o più siti di rete. Usare le procedure seguenti per creare o modificare un profilo dei criteri di larghezza di banda. Per eliminare un profilo dei criteri di larghezza di banda, vedere [eliminazione dei profili dei criteri di larghezza di banda in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a>Per creare un nuovo profilo dei criteri di larghezza di banda

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **criteri larghezza di banda**.

4.  Nella pagina **criteri di larghezza di banda** fare clic su **nuovo**.

5.  In **nuovo profilo dei criteri di larghezza di banda**Digitare un nome nel campo **nome** . Questo nome deve essere univoco tra tutti i profili dei criteri di larghezza di banda.

6.  Nel campo **limite audio** Digitare un valore numerico. Questo valore è la quantità massima di larghezza di banda da allocare per tutte le connessioni audio espresse in kbps.

7.  Immettere un valore numerico nel campo **limite della sessione audio** . Questo valore è la quantità massima di larghezza di banda da allocare per una singola connessione audio, espressa in kbps. Questo valore deve essere 40 o superiore.

8.  Immettere un valore numerico nel campo **limite video** . Questo valore è la quantità massima di larghezza di banda da allocare per tutte le connessioni video espresse in kbps.

9.  Immettere un valore numerico nel campo **limite sessione video** . Questo valore è la quantità massima di larghezza di banda da allocare per una singola connessione video, espressa in kbps. Questo valore deve essere 100 o superiore.

10. Opzionale Digitare un valore nel campo **Description** per ottenere altre informazioni su questo profilo dei criteri di larghezza di banda che non può essere espresso solo dal nome.

11. Fare clic su **Commit**.
    
    <div>
    

    > [!NOTE]  
    > La creazione di un nuovo profilo dei criteri di larghezza di banda non applica automaticamente restrizioni della larghezza di banda. È prima di tutto necessario associare il profilo dei criteri a un sito. Per informazioni dettagliate su come associare un profilo dei criteri a un sito, vedere <A href="lync-server-2013-creating-or-modifying-network-sites.md">creazione o modifica di siti di rete in Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a>Per modificare un profilo dei criteri di larghezza di banda

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **criteri larghezza di banda**.

4.  Nella pagina **criteri di larghezza di banda** fare clic sul profilo dei criteri di larghezza di banda che si desidera modificare.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.

6.  Nella pagina **modifica profilo dei criteri di larghezza di banda** modificare i campi in modo necessario (per informazioni dettagliate, vedere la sezione "per creare un profilo dei criteri di larghezza di banda" in questo argomento).

7.  Fare clic su **Commit**.
    
    <div>
    

    > [!NOTE]  
    > Quando si modifica il profilo dei criteri di larghezza di banda, verranno immediatamente aggiornate le limitazioni della larghezza di banda di tutti i siti di rete associati al profilo del criterio di larghezza di banda.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Eliminazione dei profili dei criteri di larghezza di banda di rete in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[Configurare il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

