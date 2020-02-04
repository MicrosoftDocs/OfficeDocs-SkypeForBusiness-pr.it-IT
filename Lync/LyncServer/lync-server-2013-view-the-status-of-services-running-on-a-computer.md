---
title: 'Lync Server 2013: visualizzare lo stato dei servizi in uso in un computer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View the status of services running on a computer
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48185804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 984f85fca13704864b3cd47c83e8f6adca575705
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a>Visualizzare lo stato dei servizi in uso in un computer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-22_

È possibile usare il pannello di controllo di Lync Server 2013 per visualizzare tutti i servizi in uso in un computer specifico nella topologia di Lync Server e vedere lo stato di ogni servizio.

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a>Per visualizzare lo stato dei servizi in uso in un computer

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **topologia**.

4.  Nella pagina **stato** ordinare o cercare l'elenco, se necessario, per trovare il computer interessato e quindi fare clic sul nome del computer.

5.  Eseguire una delle operazioni seguenti:
    
      - Per visualizzare lo stato più recente dei servizi in uso nel computer, fare clic su **Ottieni stato servizio**.
    
      - Per visualizzare un elenco di servizi specifici in uso nel computer e lo stato di ogni servizio, fare clic su **Proprietà**e quindi su **Chiudi** per tornare all'elenco.

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Visualizzazione dello stato del servizio tramite i cmdlet di Windows PowerShell

È anche possibile visualizzare lo stato del servizio tramite Windows PowerShell e il cmdlet **Get-CsWindowsService** . Puoi eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-view-service-status"></a>Per visualizzare lo stato del servizio

  - Per visualizzare lo stato del servizio in un computer, digitare un comando simile a quello seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    Questo comando restituisce informazioni simili a quelle seguenti:
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

</div>

Per informazioni dettagliate, vedere [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Gestione di dispositivi, telefoni e applicazioni client in Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

