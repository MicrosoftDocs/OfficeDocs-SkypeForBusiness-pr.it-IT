---
title: "Lync Server 2013: visualizzare gli aggiornamenti software per i dispositivi nell'organizzazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce1940f92860d5ccd2d66c53a0a4da16cebada24
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a>Visualizzare gli aggiornamenti software per i dispositivi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Con Lync Server 2013, è possibile utilizzare il servizio Web aggiornamento dispositivi per visualizzare e gestire gli aggiornamenti software per i dispositivi dell'organizzazione. Questi aggiornamenti sono disponibili nei file CAB (Cabinet) del sito Web del supporto tecnico Microsoft [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091)all'indirizzo. Dopo aver scaricato il file CAB, eseguire il cmdlet **Import-CSDeviceUpdate** per importare le regole di aggiornamento dei dispositivi dal file CAB. Per informazioni dettagliate sul cmdlet **Import-CSDeviceUpdate** , vedere [Import-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) nella documentazione di Lync Server Management Shell.

<div>


> [!TIP]  
> Prima di distribuire un nuovo aggiornamento nell'organizzazione, verificarne il corretto funzionamento su un dispositivo di test.



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a>Per visualizzare gli aggiornamenti software per i dispositivi per comunicazioni unificate

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Nel [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091)sito Web del supporto tecnico Microsoft, scaricare il file CAB in un percorso su un computer Lync Server 2013, ad esempio C:\\Updates\\UCUpdates. cab.

3.  Importare le regole di aggiornamento dei dispositivi dal file\\ucupdates\\. cab C: Updates eseguendo uno dei cmdlet seguenti:
    
      - Se il file CAB si trova sullo stesso computer sul quale è in esecuzione il servizio da aggiornare (service:Redmond-websvc-2), eseguire il cmdlet seguente:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - Se il file CAB si trova su un computer diverso da quello sul quale è in esecuzione il servizio da aggiornare (service:Redmond-websvc-3), eseguire il cmdlet seguente:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

5.  Sulla barra di spostamento sinistra fare clic su **Client** e quindi su **Aggiornamento dispositivi**.

6.  Nella pagina **Aggiornamento dispositivi** fare clic su un aggiornamento nell'elenco ed eseguire una delle operazioni seguenti:
    
      - **Annullare un aggiornamento in sospeso.** Per impedire che l'aggiornamento selezionato venga distribuito nei dispositivi dell'organizzazione, fare clic sul menu **Azione** e quindi su **Annulla aggiornamenti in sospeso**.
    
      - **Approvare un aggiornamento.** Per consentire la distribuzione dell'aggiornamento selezionato nei dispositivi dell'organizzazione, fare clic sul menu **Azione** e quindi su **Approva**.
    
      - **Ripristinare un aggiornamento.** Per consentire la distribuzione di un aggiornamento approvato in precedenza nei dispositivi dell'organizzazione, fare clic sul menu **Azione** e quindi su **Ripristina**.

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

