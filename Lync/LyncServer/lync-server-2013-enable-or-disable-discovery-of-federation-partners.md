---
title: "Lync Server 2013: abilitare o disabilitare l'individuazione dei partner federativi"
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
ms.openlocfilehash: 893f61ce972ae85bcc88f47fe83c4fde220bb5c9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a>Abilitare o disabilitare l'individuazione dei partner federativi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Al momento della distribuzione degli Edge Server e dell'abilitazione della federazione per l'organizzazione, dovrebbe essere stato specificato se supportare l'individuazione automatica dei domini partner federati. Utilizzare la procedura descritta in questo argomento per modificare tale configurazione.

<div>


> [!NOTE]  
> Nella procedura che segue si presuppone che sia stata già abilitata la federazione per l'organizzazione. Per informazioni dettagliate sull'abilitazione della Federazione, vedere <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Abilitazione o disabilitazione dell'accesso degli utenti remoti in Lync Server 2013</A> nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>Per abilitare o disabilitare l'individuazione automatica dei domini federati per l'organizzazione

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Configurazione Access Edge**.

4.  Nella pagina **Configurazione Access Edge** fare clic su **Globale**, fare clic su **Modifica** e quindi su **Mostra dettagli**.

5.  In **Modifica configurazione Access Edge**, in **Abilita comunicazioni con utenti federati** selezionare o deselezionare la casella di controllo **Abilita individuazione dominio partner** per abilitare o disabilitare l'individuazione automatica dei domini partner.

6.  Fare clic su **Commit**.

Per consentire agli utenti federati di collaborare con gli utenti nella distribuzione di Lync Server, è necessario aver configurato almeno un criterio di accesso esterno per supportare l'accesso degli utenti federati. Per ulteriori informazioni, vedere [abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni. Per informazioni dettagliate sul controllo dell'accesso per specifici domini federati, vedere [gestire i domini federati SIP per l'organizzazione in Lync server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [gestire i provider federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) e [gestire i partner federati XMPP in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) nella documentazione relativa alle operazioni.

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione dell'individuazione dei partner federativi tramite i cmdlet di Windows PowerShell

L'individuazione dei partner federativi può essere gestita utilizzando Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-enable-discovery-of-federation-partners"></a>Per abilitare l'individuazione dei partner federativi

  - Per abilitare l'individuazione dei partner federati, impostare il valore della proprietà **EnablePartnerDiscovery** su True ($True). Tenere presente che è necessario abilitare l'instradamento DNS SRV per modificare il valore di questa proprietà.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a>Per disabilitare l'individuazione dei partner federativi

  - Per disabilitare l'individuazione dei partner federati, impostare il valore della proprietà **EnablePartnerDiscovery** su False ($False).
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

