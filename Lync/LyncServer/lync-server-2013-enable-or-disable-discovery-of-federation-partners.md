---
title: "Lync Server 2013: Abilitare o disabilitare l'individuazione dei partner della federazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable discovery of federation partners
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f97a6ab26a3b8b3f011a62cd92bbd0271f781a1a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a>Abilitare o disabilitare l'individuazione dei partner della federazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Al momento della distribuzione degli Edge Server e della federazione abilitata per l'organizzazione, è necessario specificare se supportare l'individuazione automatica dei domini partner federati. Usare la procedura descritta in questo argomento per modificare la configurazione.

<div>


> [!NOTE]  
> La procedura seguente presuppone che tu abbia già abilitato la Federazione per l'organizzazione. Per informazioni dettagliate sull'abilitazione della Federazione, vedere <A href="lync-server-2013-enable-or-disable-remote-user-access.md">abilitare o disabilitare l'accesso remoto agli utenti in Lync Server 2013</A> nella documentazione relativa alla distribuzione o nella documentazione delle operazioni.



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>Per abilitare o disabilitare l'individuazione automatica dei domini federati per l'organizzazione

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**, fare clic su **configurazione bordo di Access**.

4.  Nella pagina **configurazione di Access Edge** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  In **modifica configurazione di Access Edge**, in **abilitare le comunicazioni con gli utenti federati**, selezionare o deselezionare la casella di controllo **Abilita individuazione dominio partner** per abilitare o disabilitare l'individuazione automatica dei domini partner.

6.  Fare clic su **Commit**.

Per consentire agli utenti federati di collaborare con gli utenti nella distribuzione di Lync Server, è necessario avere anche configurato almeno un criterio di accesso esterno per supportare l'accesso degli utenti federati. Per informazioni dettagliate, vedere [abilitare o disabilitare la connettività per la messaggistica istantanea e la Federazione in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) nella documentazione relativa alla distribuzione o nella documentazione delle operazioni. Per informazioni dettagliate su come controllare l'accesso per specifici domini federati, vedere [gestire i domini federati SIP per l'organizzazione in Lync server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [gestire i provider federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) e [gestire i partner federati XMPP in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) nella documentazione delle operazioni.

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione dell'individuazione dei partner federativi tramite i cmdlet di Windows PowerShell

L'individuazione dei partner federativi può essere gestita tramite Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-enable-discovery-of-federation-partners"></a>Per abilitare l'individuazione dei partner federativi

  - Per abilitare l'individuazione dei partner federativi, imposta il valore della proprietà **EnablePartnerDiscovery** su True ($true). Tieni presente che devi abilitare il routing SRV DNS per cambiare il valore della proprietà.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a>Per disabilitare l'individuazione dei partner federativi

  - Per disabilitare l'individuazione dei partner federativi, imposta il valore della proprietà **EnablePartnerDiscovery** su False ($false):
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

