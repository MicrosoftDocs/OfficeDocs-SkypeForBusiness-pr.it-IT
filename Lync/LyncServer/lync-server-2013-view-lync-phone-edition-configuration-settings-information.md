---
title: 'Lync Server 2013: visualizzare le informazioni sulle impostazioni di configurazione di Lync Phone Edition'
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
ms.openlocfilehash: a58450b1d69ce757f40194d179606f332e152d7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a>Visualizzare le informazioni sulle impostazioni di configurazione di Lync Phone Edition in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

È possibile visualizzare le informazioni di configurazione sui dispositivi in cui è in uso Lync Phone Edition. Le informazioni sono organizzate in raccolte. Quando si installa Lync Server, si ottiene una raccolta di impostazioni di Lync Phone Edition che si applicano a tutti i dispositivi in cui è in uso Lync Phone Edition nella distribuzione. È anche possibile creare nuove raccolte di impostazioni per un sito specifico. Le impostazioni del sito hanno la precedenza sulle impostazioni globali. Ogni raccolta di impostazioni è costituita da un nome, l'ambito (globale o del sito), l'impostazione di sicurezza SIP, il livello di registrazione, il livello di qualità del servizio (QoS) vocale, l'impostazione di blocco telefonico e i dettagli del blocco telefonico, ovvero la lunghezza minima dell'identificazione personale di sblocco numero (PIN) e ora prima che il telefono si blocchi.

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a>Per visualizzare le informazioni di configurazione sui dispositivi in cui è in uso Lync Phone Edition

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento della **configurazione del dispositivo** .

4.  Nella pagina **Configurazione dispositivo** fare clic sulla raccolta di impostazioni di cui si vogliono visualizzare le informazioni. Nella pagina principale sono elencati il nome, l'ambito, l'impostazione di sicurezza SIP, il livello di qualità vocale e l'impostazione di blocco telefonico. Per visualizzare i dettagli del livello di registrazione e del blocco telefonico, fare clic sul menu **modifica** e quindi su **Mostra dettagli**.

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni di configurazione di Lync Phone Edition tramite i cmdlet di Windows PowerShell

Per visualizzare le impostazioni di configurazione di Lync Phone Edition, è possibile usare Lync Server Management Shell e il cmdlet **Get-CsUCPhoneConfiguration** . Puoi eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a>Per visualizzare le informazioni di configurazione di Lync Phone Edition

  - Per visualizzare informazioni su tutte le impostazioni di configurazione di Lync Phone Edition, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsUCPhoneConfiguration
    
    Il comando restituisce informazioni simili a quelle seguenti:
    
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
[Applicare il blocco telefonico in Lync Server 2013](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

