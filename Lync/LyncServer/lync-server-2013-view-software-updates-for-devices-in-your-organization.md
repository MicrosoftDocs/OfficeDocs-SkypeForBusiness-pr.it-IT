---
title: "Lync Server 2013: visualizzare gli aggiornamenti software per i dispositivi dell'organizzazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06700e198dcd1923e875401b4539a0af84417c44
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a>Visualizzare gli aggiornamenti software per i dispositivi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Con Lync Server 2013 si usa servizio Web Update per visualizzare e gestire gli aggiornamenti software per i dispositivi dell'organizzazione. Questi aggiornamenti sono disponibili nei file CAB (Cabinet) dal sito Web del supporto tecnico Microsoft [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)all'indirizzo. Dopo aver scaricato il file CAB, eseguire il cmdlet **Import-CSDeviceUpdate** per importare le regole di aggiornamento dei dispositivi dal file CAB. Per informazioni dettagliate sul cmdlet **Import-CSDeviceUpdate** , vedere [Import-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) nella documentazione di Lync Server Management Shell.

<div>


> [!TIP]  
> Prima di distribuire un nuovo aggiornamento all'organizzazione, verificare che funzioni correttamente in un dispositivo di test.



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a>Per visualizzare gli aggiornamenti software per i dispositivi UC

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Dal sito Web del supporto tecnico [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)Microsoft, scaricare il file CAB in una posizione in un computer Lync Server 2013, ad esempio C:\\Updates\\UCUpdates. cab.

3.  Importare le regole di aggiornamento del dispositivo dal file\\C\\: Updates UCUpdates. cab eseguendo uno dei cmdlet seguenti:
    
      - Se il file CAB si trova nello stesso computer di quello in cui è in esecuzione il servizio da aggiornare (servizio: Redmond-websvc-2), eseguire il cmdlet seguente:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - Se il file CAB si trova in un computer diverso da quello in cui è in esecuzione il servizio da aggiornare (servizio: Redmond-websvc-3), eseguire il cmdlet seguente:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

5.  Sulla barra di spostamento sinistra fare clic su **client**e quindi su **aggiornamento dispositivi**.

6.  Nella pagina **aggiornamento dispositivi** fare clic su un aggiornamento nell'elenco e quindi eseguire una delle operazioni seguenti:
    
      - **Annullare un aggiornamento in sospeso.** Per impedire la distribuzione dell'aggiornamento selezionato nei dispositivi dell'organizzazione, fare clic sul menu **azione** e quindi su **Annulla aggiornamenti in sospeso**.
    
      - **Approvare un aggiornamento.** Per consentire la distribuzione dell'aggiornamento selezionato nei dispositivi dell'organizzazione, fare clic sul menu **azione** e quindi su **approva**.
    
      - **Ripristinare un aggiornamento.** Per consentire la distribuzione di un aggiornamento approvato in precedenza nei dispositivi dell'organizzazione, fare clic sul menu **azione** e quindi su **Ripristina**.

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

