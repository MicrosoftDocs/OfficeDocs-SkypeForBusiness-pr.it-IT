---
title: 'Lync Server 2013: aprire gli strumenti di amministrazione di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa84c132061cb599448b78cf7d4ffcc6bd7fa3d5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a>Aprire gli strumenti di amministrazione di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-28_

È possibile usare le procedure descritte in questo argomento per aprire gli strumenti di amministrazione per distribuire, configurare o risolvere i problemi della topologia di Lync Server 2013.

  - Distribuzione guidata

  - Generatore di topologie

  - Pannello di controllo di Lync Server

  - Lync Server Management Shell

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a>Distribuzione guidata

Usare la procedura seguente per avviare la distribuzione guidata localmente per aggiungere o rimuovere file di componenti di Lync Server 2013.

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a>Per avviare la distribuzione guidata di Lync Server 2013

1.  Accedere al computer in cui è installata la distribuzione guidata di Lync Server come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

2.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **distribuzione guidata Lync Server**.

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a>Generatore di topologie

Usare la procedura seguente per aprire il generatore di topologia per definire i server che si desidera distribuire nella topologia di Lync Server 2013.

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a>Per aprire il generatore di topologia di Lync Server 2013 per progettare la topologia

1.  Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.
    
    <div>
    

    > [!NOTE]  
    > È possibile definire una topologia usando un account che è un membro del gruppo utenti locali, ma per leggere, pubblicare o abilitare una topologia, necessaria per installare Lync Server 2013 in un server, è necessario usare un account membro del gruppo Domain Admins e RTCUniv gruppo ersalServerAdmins, con autorizzazioni controllo completo (ovvero, lettura, scrittura e modifica) nella condivisione file che si vuole usare per l'archiviazione dei file archiviati in modo che generatore di topologia possa configurare l'elenco di controllo di accesso discrezionale richiesto (DACL), o un account con diritti utente equivalenti.

    
    </div>

2.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a>Pannello di controllo di Lync Server 2013

Usare una delle procedure seguenti per aprire il pannello di controllo di Lync Server 2013 per gestire la configurazione di server, utenti, client e dispositivi nell'ambiente.

<div>


> [!NOTE]  
> È possibile usare un account utente assegnato al ruolo CsAdministrator per eseguire qualsiasi attività nel pannello di controllo di Lync Server 2013. È possibile usare altri ruoli per accedere al pannello di controllo di Lync Server 2013 per eseguire attività di amministrazione specifiche, in base all'attività che occorre eseguire. Ad esempio, puoi usare CSArchivingAdministrator per amministrare l'archiviazione nel pannello di controllo di Lync Server 2013. Per informazioni dettagliate sui ruoli, vedere <A href="lync-server-2013-planning-for-role-based-access-control.md">pianificazione per il controllo dell'accesso basato sui ruoli in Lync Server 2013</A> nella documentazione relativa alla pianificazione. Per informazioni dettagliate sui ruoli che è possibile usare per eseguire un'attività specifica, vedere la documentazione relativa all'attività.



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a>Per aprire il pannello di controllo di Lync Server 2013 da qualsiasi computer all'interno del firewall dell'organizzazione

1.  Da un account utente assegnato al ruolo CsAdministrator o da un altro ruolo che disponga dei diritti utente appropriati e delle autorizzazioni per l'attività da eseguire, accedere a qualsiasi computer della distribuzione interna con una risoluzione minima dello schermo di 1024 x 768.
    
    <div>
    

    > [!IMPORTANT]  
    > Se è stato configurato un semplice URL (Uniform Resource Locator) di amministrazione, è possibile accedere al pannello di controllo di Lync Server 2013 da un browser Internet in uso in qualsiasi computer all'interno del firewall dell'organizzazione. Per informazioni dettagliate sulla configurazione dell'URL semplice di amministrazione, vedere <A href="lync-server-2013-planning-for-simple-urls.md">pianificazione di URL semplici in Lync server 2013</A> nella documentazione di pianificazione e <A href="lync-server-2013-edit-or-configure-simple-urls.md">modifica o configurazione di URL semplici in Lync Server 2013</A> nella documentazione relativa alla distribuzione.

    
    </div>

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore configurato per l'organizzazione.

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a>Per aprire il pannello di controllo di Lync Server 2013 in un computer che gestisce Lync Server 2013

1.  Da un account utente che fa parte del ruolo CsAdministrator o di un altro ruolo che disponga dei diritti utente e delle autorizzazioni appropriate per l'attività, accedere a un computer in cui è installato Lync Server 2013 o, almeno, Lync Server 2013 amministrazione strumenti Ive. Per configurare le impostazioni, il computer deve avere una risoluzione minima dello schermo di 1024 x 768.

2.  Avviare il pannello di controllo di Lync Server 2013: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**, scegliere **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server 2013 pannello di controllo**.

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a>Lync Server 2013 Management Shell

Usare la procedura seguente per aprire Lync Server 2013 Management Shell per amministrare server, utenti, client e dispositivi nell'ambiente tramite la riga di comando.

<div>


> [!NOTE]  
> Puoi usare un account utente assegnato al ruolo CsAdministrator per eseguire qualsiasi attività in Lync Server 2013 Management Shell. È possibile accedere con altri ruoli per eseguire attività di amministrazione specifiche, a seconda dell'attività che occorre eseguire. Ad esempio, puoi usare CSArchivingAdministrator per eseguire i cmdlet correlati all'amministrazione dell'archiviazione. Per informazioni dettagliate sui ruoli, vedere <A href="lync-server-2013-planning-for-role-based-access-control.md">pianificazione per il controllo dell'accesso basato sui ruoli in Lync Server 2013</A> nella documentazione relativa alla pianificazione. Per informazioni dettagliate sui ruoli che è possibile usare per eseguire un cmdlet specifico, vedere la documentazione relativa al cmdlet.<BR>Puoi anche eseguire determinati cmdlet usando un account utente nei gruppi RTCUniversalServerAdmins, RTCUniversalUserAdmins o RTCUniversalReadOnlyAdmins, a seconda del cmdlet.



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a>Per aprire Lync Server 2013 Management Shell

  - Se si apre una finestra di Windows PowerShell anziché Lync Server 2013 Management Shell, per impostazione predefinita non è possibile eseguire i cmdlet di Lync Server 2013. Per eseguire i cmdlet di Lync Server 2013 da Windows PowerShell, digitare quanto segue al prompt dei comandi di Windows PowerShell:
    
    `Import-Module Lync`

  - Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Installare gli strumenti di amministrazione di Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)  


[Strumenti di amministrazione di Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

