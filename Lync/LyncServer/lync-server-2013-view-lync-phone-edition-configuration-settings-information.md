---
title: 'Lync Server 2013: visualizzare le informazioni sulle impostazioni di configurazione di Lync Phone Edition'
description: 'Lync Server 2013: visualizzare le informazioni sulle impostazioni di configurazione di Lync Phone Edition.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62719b24920ee72a92b2f80498d5ea2a59288c2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576432"
---
# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a>Visualizzare le informazioni sulle impostazioni di configurazione di Lync Phone Edition in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

È possibile visualizzare le informazioni di configurazione relative ai dispositivi che eseguono Lync Phone Edition. Le informazioni sono organizzate in raccolte. Quando si installa Lync Server, è possibile ottenere una raccolta di impostazioni di Lync Phone Edition che si applicano a tutti i dispositivi che eseguono Lync Phone Edition nella distribuzione. È anche possibile creare nuove raccolte di impostazioni per uno specifico sito. Le impostazioni del sito hanno la precedenza sulle impostazioni globali. In ogni raccolta di impostazioni sono disponibili nome, ambito (globale o sito), impostazione per la sicurezza SIP, livello di registrazione, livello di qualità vocale del servizio (QoS), impostazione per il blocco telefono e dettagli sul blocco telefono, ovvero la lunghezza minima del PIN di sblocco e l'intervallo di tempo prima che il telefono si blocchi.

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a>Per visualizzare le informazioni di configurazione sui dispositivi che eseguono Lync Phone Edition

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Client**, quindi sul pulsante di spostamento **Configurazione dispositivo**.

4.  Nella pagina **Configurazione dispositivo** fare clic sulla raccolta di impostazioni di cui si desidera visualizzare le informazioni. Il nome, l'ambito, l'impostazione di sicurezza SIP, il livello di qualità vocale e l'impostazione di blocco telefono sono elencate nella pagina principale. Per visualizzare il livello di registrazione e i dettagli del blocco telefono, fare clic sul menu **Modifica**, quindi su **Mostra dettagli**.

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni di configurazione di Lync Phone Edition tramite i cmdlet di Windows PowerShell

È possibile visualizzare le impostazioni di configurazione di Lync Phone Edition utilizzando Lync Server Management Shell e il cmdlet **Get-CsUCPhoneConfiguration** . È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a>Per visualizzare le informazioni di configurazione di Lync Phone Edition

  - Per visualizzare informazioni su tutte le impostazioni di configurazione di Lync Phone Edition, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsUCPhoneConfiguration
    
    Verranno restituite informazioni simili alle seguenti
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

</div>

Per informazioni dettagliate, vedere [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare o modificare una raccolta di impostazioni di configurazione di Lync Phone Edition in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[Eliminare una raccolta esistente di impostazioni di configurazione di Lync Phone Edition in Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Configurare le impostazioni di sicurezza per Lync Phone Edition in Lync Server 2013](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Applicare il blocco del telefono in Lync Server 2013](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

