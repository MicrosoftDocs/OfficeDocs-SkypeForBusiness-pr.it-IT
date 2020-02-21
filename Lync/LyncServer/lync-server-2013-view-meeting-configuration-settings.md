---
title: 'Lync Server 2013: visualizzare le impostazioni di configurazione delle riunioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 076c3a13f1cbc6519a0af4c0ee8b587a7f5d83ca
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a>Visualizzare le impostazioni di configurazione delle riunioni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Nel pannello di controllo di Lync Server 2013, è possibile utilizzare le impostazioni di configurazione delle riunioni per controllare la modalità di implementazione delle riunioni nella distribuzione. Sono incluse le configurazioni di riunione seguenti:

  - Una configurazione globale creata per impostazione predefinita quando si distribuisce Lync Server 2013.

  - Configurazioni facoltative a livello di sito e di utente che possono essere create e utilizzate per specificare come devono essere implementate le riunioni per siti o utenti specifici.

<div>

## <a name="to-view-meeting-configuration-settings"></a>Per visualizzare le impostazioni di configurazione di riunione

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Configurazione riunione**.

4.  Nella pagina **Configurazione riunione** fare clic sulla configurazione di riunione che si desidera visualizzare.

5.  In **Modifica filtro file** selezionare la casella di controllo **Mostra dettagli…**
    
    **Modifica configurazione riunione- \<viene\> ** visualizzato il criterio per visualizzare le impostazioni per il criterio selezionato. Per informazioni dettagliate sulla configurazione delle impostazioni, vedere [creare o modificare una raccolta di impostazioni di configurazione delle riunioni in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni sulla configurazione delle riunioni tramite i cmdlet di Windows PowerShell

È possibile visualizzare le impostazioni di configurazione delle riunioni utilizzando Windows PowerShell e il cmdlet Get-CsMeetingConfiguration. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-view-meeting-configuration-information"></a>Per visualizzare le informazioni sulla configurazione delle riunioni

  - Per visualizzare informazioni su tutte le impostazioni di configurazione delle riunioni, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsMeetingConfiguration
    
    Verranno restituite informazioni simili alle seguenti:
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

