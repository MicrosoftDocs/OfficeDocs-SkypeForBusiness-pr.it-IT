---
title: 'Lync Server 2013: visualizzazione delle informazioni sul profilo dei criteri di larghezza di banda di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network bandwidth policy profile information
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49733866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c497ad849135e5bdfea4a3f001e86e65c269dca8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a>Visualizzazione delle informazioni del profilo dei criteri di larghezza di banda di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Nell'ambito del controllo di ammissione di chiamata (CAC) viene usato un criterio di larghezza di banda per definire le limitazioni della larghezza di banda per determinate modalità. In Microsoft Lync Server 2013 solo le modalità audio e video possono essere assegnate alle limitazioni della larghezza di banda. Puoi impostare limitazioni generali della larghezza di banda e limitazioni della sessione. È possibile usare il pannello di controllo di Lync Server per creare, modificare o eliminare un profilo contenitore per questi criteri. Ogni profilo dei criteri di larghezza di banda può essere associato a uno o più siti di rete. Usare le procedure seguenti per visualizzare un profilo dei criteri di larghezza di banda. Per creare o modificare un profilo dei criteri di larghezza di banda, vedere [creazione o modifica dei profili dei criteri di larghezza di banda in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a>Per visualizzare un profilo dei criteri di larghezza di banda

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **criteri larghezza di banda**.

4.  Nella pagina **criteri di larghezza di banda** fare clic sul profilo dei criteri di larghezza di banda che si desidera visualizzare.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni del profilo dei criteri di larghezza di banda di rete tramite i cmdlet di Windows PowerShell

I profili di larghezza di banda di rete possono essere visualizzati usando Windows PowerShell e il cmdlet Get-CsNetworkBandwidthPolicyProfile. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a>Per visualizzare le informazioni sul profilo dei criteri di larghezza di banda

  - Per visualizzare informazioni su tutti i profili dei criteri di larghezza di banda della rete, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Questo restituirà informazioni simili alla seguente:
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creazione o modifica dei profili dei criteri di larghezza di banda in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Eliminazione dei profili dei criteri di larghezza di banda di rete in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[Configurare il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

