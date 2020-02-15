---
title: 'Lync Server 2013: aprire gli strumenti di amministrazione di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1019a763647ff2bf1ec2333e3a88315c987e85ea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a>Aprire gli strumenti di amministrazione di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-28_

È possibile utilizzare le procedure descritte in questo argomento per aprire strumenti di amministrazione per la distribuzione, la configurazione o la risoluzione dei problemi relativi alla topologia di Lync Server 2013.

  - Distribuzione guidata

  - Generatore di topologie

  - Pannello di controllo di Lync Server

  - Lync Server Management Shell

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a>Distribuzione guidata

Utilizzare la procedura seguente per avviare la distribuzione guidata localmente per aggiungere o rimuovere i file dei componenti di Lync Server 2013.

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a>Per avviare la distribuzione guidata di Lync Server 2013

1.  Accedere al computer in cui è installata la Distribuzione guidata di Lync Server come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

2.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi **distribuzione guidata di Lync Server**.

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a>Strumento di generazione topologia

Utilizzare la procedura seguente per aprire il generatore di topologie per definire i server che si desidera distribuire nella topologia di Lync Server 2013.

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a>Per aprire il generatore di topologie di Lync Server 2013 per progettare la topologia

1.  Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.
    
    <div>
    

    > [!NOTE]  
    > È possibile definire una topologia utilizzando un account membro del gruppo degli utenti locali, ma per leggere, pubblicare o abilitare una topologia, necessaria per installare Lync Server 2013 in un server, è necessario utilizzare un account membro del gruppo Domain Admins e RTCUniv. gruppo ersalServerAdmins e con autorizzazioni di controllo completo (ovvero lettura, scrittura e modifica) sulla condivisione file da utilizzare per l'archivio file di archiviazione in modo che generatore di topologie possa configurare l'elenco di controllo di accesso discrezionale necessario (DACL) o un account con diritti utente equivalenti.

    
    </div>

2.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a>Pannello di controllo di Lync Server 2013

Utilizzare una delle procedure seguenti per aprire il pannello di controllo di Lync Server 2013 per gestire la configurazione di server, utenti, client e dispositivi nell'ambiente.

<div>


> [!NOTE]  
> È possibile utilizzare un account utente assegnato al ruolo CsAdministrator per eseguire tutte le attività del pannello di controllo di Lync Server 2013. È possibile utilizzare altri ruoli per accedere al pannello di controllo di Lync Server 2013 per eseguire attività amministrative specifiche, a seconda dell'attività che è necessario eseguire. Ad esempio, è possibile utilizzare CSArchivingAdministrator per amministrare l'archiviazione nel pannello di controllo di Lync Server 2013. Per informazioni dettagliate sui ruoli, vedere <A href="lync-server-2013-planning-for-role-based-access-control.md">pianificazione del controllo di accesso basato sui ruoli in Lync Server 2013</A> nella documentazione relativa alla pianificazione. Per informazioni dettagliate sui ruoli che è possibile utilizzare per eseguire un'attività specifica, vedere la documentazione relativa all'attività.



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a>Per aprire il pannello di controllo di Lync Server 2013 da qualsiasi computer all'interno del firewall dell'organizzazione

1.  Da un account utente assegnato al ruolo CsAdministrator o a un altro ruolo con autorizzazioni e diritti utente appropriate per l'attività da eseguire, accedere a qualsiasi computer nella distribuzione interna con una risoluzione minima dello schermo pari a 1024 x 768.
    
    <div>
    

    > [!IMPORTANT]  
    > Se è stato configurato un URL (Uniform Resource Locator) di amministrazione semplice, è possibile accedere al pannello di controllo di Lync Server 2013 da un browser Internet in esecuzione su qualsiasi computer all'interno del firewall dell'organizzazione. Per informazioni dettagliate sulla configurazione dell'URL semplice di amministrazione, vedere <A href="lync-server-2013-planning-for-simple-urls.md">Planning for Simple URLs in Lync server 2013</A> nella documentazione relativa alla pianificazione e <A href="lync-server-2013-edit-or-configure-simple-urls.md">modificare o configurare URL semplici in Lync Server 2013</A> nella documentazione relativa alla distribuzione.

    
    </div>

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione configurato per l'organizzazione.

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a>Per aprire il pannello di controllo di Lync Server 2013 in un computer su cui è in esecuzione Lync Server 2013

1.  Da un account utente membro del ruolo CsAdministrator o da un altro ruolo con diritti utente e autorizzazioni appropriate per l'attività da eseguire, accedere a un computer in cui è installato Lync Server 2013 o, almeno, Lync Server 2013 amministrare strumenti Ive. Per configurare le impostazioni, è necessario che il computer disponga di una risoluzione dello schermo minima di 1024 x 768.

2.  Avviare il pannello di controllo di Lync Server 2013: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**, **Microsoft Lync Server 2013**e quindi **Pannello di controllo di Lync Server 2013**.

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a>Lync Server 2013 Management Shell

Utilizzare la procedura seguente per aprire Lync Server 2013 Management Shell per l'amministrazione di server, utenti, client e dispositivi nell'ambiente utilizzando la riga di comando.

<div>


> [!NOTE]  
> È possibile utilizzare un account utente assegnato al ruolo CsAdministrator per eseguire qualsiasi attività in Lync Server 2013 Management Shell. È possibile accedere utilizzando altri ruoli per eseguire attività di amministrazione specifiche, a seconda dell'attività che è necessario eseguire. È ad esempio possibile utilizzare CSArchivingAdministrator per eseguire cmdlet correlati all'amministrazione dell'archiviazione. Per informazioni dettagliate sui ruoli, vedere <A href="lync-server-2013-planning-for-role-based-access-control.md">pianificazione del controllo di accesso basato sui ruoli in Lync Server 2013</A> nella documentazione relativa alla pianificazione. Per informazioni dettagliate sui ruoli che è possibile utilizzare per eseguire un cmdlet specifico, vedere la documentazione relativa al cmdlet.<BR>È inoltre possibile eseguire alcuni cmdlet utilizzando un account utente nel gruppo RTCUniversalServerAdmins, RTCUniversalUserAdmins o RTCUniversalReadOnlyAdmins, a seconda del cmdlet.



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a>Per aprire Lync Server 2013 Management Shell

  - Se si apre una finestra di Windows PowerShell anziché Lync Server 2013 Management Shell, per impostazione predefinita non è possibile eseguire i cmdlet di Lync Server 2013. Per eseguire i cmdlet di Lync Server 2013 dall'interno di Windows PowerShell, al prompt dei comandi di Windows PowerShell digitare quanto segue:
    
    `Import-Module Lync`

  - Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

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

