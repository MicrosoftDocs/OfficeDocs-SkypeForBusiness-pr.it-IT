---
title: 'Lync Server 2013: creazione o modifica di profili di criteri di larghezza di banda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c46ec104972eff34f73825fbb384259fc6eb4ba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a>Creazione o modifica di profili di criteri di larghezza di banda in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-15_

In Controllo di ammissione di chiamata (CAC) i criteri di larghezza di banda vengono utilizzati per definire le limitazioni della larghezza di banda per alcune modalità. In Microsoft Lync Server 2013, è possibile assegnare limitazioni della larghezza di banda solo alle modalità audio e video. È possibile impostare limitazioni della larghezza di banda globali o per le sessioni. È possibile utilizzare il pannello di controllo di Lync Server per creare, modificare o eliminare un profilo contenitore per questi criteri. Ogni profilo di criteri della larghezza di banda può essere associato a uno o più siti di rete. Utilizzare le procedure seguenti per creare o modificare un profilo dei criteri di larghezza di banda. Per eliminare un profilo dei criteri di larghezza di banda, vedere [eliminazione dei profili di criteri larghezza di banda di rete in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a>Per creare un nuovo profilo di criteri di larghezza di banda

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Criteri larghezza di banda**.

4.  Nella pagina **criteri larghezza di banda** fare clic su **nuovo**.

5.  In **nuovo profilo dei criteri di larghezza di banda**Digitare un nome nel campo **nome** . Questo nome deve essere univoco tra tutti i profili dei criteri di larghezza di banda.

6.  Nel campo **limite audio** Digitare un valore numerico. Questo valore è la quantità massima di larghezza di banda da allocare per tutte le connessioni audio espresse in kbps.

7.  Immettere un valore numerico nel campo **limite sessione audio** . Questo valore è la quantità massima di larghezza di banda da allocare per una singola connessione audio, espressa in kbps. Questo valore deve essere 40 o superiore.

8.  Immettere un valore numerico nel campo **limite video** . Questo valore è la quantità massima di larghezza di banda da allocare per tutte le connessioni video espresse in kbps.

9.  Immettere un valore numerico nel campo **limite sessione video** . Questo valore è la quantità massima di larghezza di banda da allocare per una singola connessione video, espressa in kbps. Questo valore deve essere 100 o superiore.

10. Optional Digitare un valore nel campo **Descrizione** per fornire ulteriori informazioni sul profilo dei criteri di larghezza di banda che non è possibile esprimere solo con il nome.

11. Fare clic su **Commit**.
    
    <div>
    

    > [!NOTE]  
    > La creazione di un nuovo profilo di criteri di larghezza di banda non impone automaticamente restrizioni di larghezza di banda. È necessario innanzitutto associare il profilo dei criteri a un sito. Per informazioni dettagliate su come associare un profilo dei criteri a un sito, vedere <A href="lync-server-2013-creating-or-modifying-network-sites.md">creazione o modifica di siti di rete in Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a>Per modificare un profilo di criteri della larghezza di banda

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Criteri larghezza di banda**.

4.  Nella pagina **Criteri larghezza di banda** fare clic sul profilo di criteri della larghezza di banda che si desidera modificare.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

6.  Nella pagina **modifica profilo dei criteri di larghezza di banda** modificare i campi in base alle esigenze (per informazioni dettagliate, vedere la sezione "per creare un profilo dei criteri di larghezza di banda" più indietro in questo argomento).

7.  Fare clic su **Commit**.
    
    <div>
    

    > [!NOTE]  
    > Quando si modifica il profilo dei criteri di larghezza di banda, verranno aggiornate immediatamente le limitazioni della larghezza di banda di tutti i siti di rete associati al profilo del criterio di larghezza di banda.

    
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

