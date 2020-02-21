---
title: 'Lync Server 2013: creare o modificare una coda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a queue
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48185247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b805553349e6958671bc024cb862b296b74fc697
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-queue-in-lync-server-2013"></a>Creare o modificare una coda in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Per creare o modificare una coda, utilizzare una delle procedure illustrate di seguito.

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a>Per utilizzare il pannello di controllo di Lync Server per creare o modificare una coda

1.  Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.
    
    <div>
    

    > [!NOTE]  
    > Se si è uno dei responsabili di Response Group delegati per un flusso di lavoro gestito, è possibile creare o modificare le code di Response Group e assegnarle ai flussi di lavoro gestiti personalmente.

    
    </div>

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Response Group** e quindi su **Coda**.

4.  Nella pagina **Coda** eseguire una delle operazioni seguenti:
    
      - Per creare una nuova coda, fare clic su **Nuovo**. In **Seleziona un servizio** digitare nel campo di ricerca parte oppure tutto il nome del servizio **ApplicationServer** in cui si intende aggiungere la coda. Nell'elenco di servizi risultante fare clic sul servizio desiderato e quindi su **OK**.
    
      - Per modificare una coda esistente, digitare tutto o una parte del nome della coda nel campo di ricerca. Nell'elenco di code risultante fare clic sulla coda desiderata, su **Modifica** e quindi su **Mostra dettagli**.

5.  In **Nome** digitare un nome identificativo della coda.

6.  In **Descrizione** digitare una descrizione per la coda.

7.  In **Gruppi** specificare i gruppo che si desidera assegnare alla coda. Eseguire una delle operazioni seguenti:
    
      - Per aggiungere un gruppo alla coda, fare clic su **Seleziona**. Nel campo di ricerca **Seleziona gruppi** digitare tutto o parte del nome del gruppo di agenti che si intende assegnare alla coda, fare clic sul gruppo desiderato e quindi fare clic su **OK**.
    
      - Per rimuovere un gruppo dalla coda, nell'elenco di gruppi di agenti fare clic sul gruppo che si desidera rimuovere e quindi fare clic su **Rimuovi**.
    
      - Per modificare l'ordine in cui gli agenti vengono ricercati, nell'elenco di gruppi di agenti fare clic su un gruppo e quindi sulla freccia rivolta verso l'alto o verso il basso.
        
        <div>
        

        > [!NOTE]  
        > Per la ricerca di un agente disponibile per la coda, il server utilizza l'ordine dei gruppi. La ricerca pertanto viene eseguita prima nel primo gruppo, quindi nel secondo gruppo dell'elenco e così via.

        
        </div>

8.  Per specificare un periodo di tempo massimo in cui un chiamante resta in attesa prima che un agente risponda alla chiamata, selezionare la casella di controllo **Abilita timeout coda** e quindi eseguire le operazioni seguenti:
    
    1.  In **Periodo di timeout (secondi)** specificare il numero massimo di secondi che un chiamante può attendere prima che un agente risponda alla chiamata.
    
    2.  In **Azione chiamata** selezionare l'azione che deve essere eseguita quando si verifica il timeout di una chiamata, come indicato di seguito:
    
    <!-- end list -->
    
      - Per disconnettere la chiamata dopo il timeout, fare clic su **Disconnetti**.
    
      - Per inoltrare la chiamata alla segreteria telefonica, fare clic su **Inoltra a**segreteria telefonica e quindi digitare un indirizzo di segreteria telefonica nel campo **indirizzo SIP** nel\<formato\>@\<SIP:\> nomeutente DomainName (ad esempio, SIP:bob@contoso.com).
    
      - Per inoltrare la chiamata a un altro numero di telefono, fare clic su **Inoltra a numero di telefono**e quindi nel campo **indirizzo SIP** digitare il numero di telefono nel\<formato\>@\<SIP:\> number domainname (ad esempio, SIP:+14255550121@contoso.com).
    
      - Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra a indirizzo SIP**e quindi nel campo **indirizzo SIP** digitare l'URI dell'utente nel formato\<SIP: nomeutente\>@\<DomainName\>.
    
      - Per inoltrare la chiamata a un'altra coda, fare clic su **Inoltra a un'altra coda** e quindi selezionare la coda che si desidera utilizzare.

9.  Per specificare il numero massimo di chiamate che possono essere contenute nella coda, selezionare la casella di controllo **Abilita overflow coda** e quindi eseguire le operazioni seguenti:
    
    1.  In **Numero massimo di chiamate** selezionare il numero massimo di chiamate che possono essere contenute nella coda.
    
    2.  In **Inoltra la chiamata** selezionare quale chiamata dovrà essere inoltrata quando la coda è piena, ovvero **Chiamata più recente** o **Chiamata meno recente**.
    
    3.  In **Azione chiamata** selezionare l'azione che deve essere eseguita quando viene raggiunta la soglia di overflow, come indicato di seguito:
    
    <!-- end list -->
    
      - Per disconnettere la chiamata dopo il timeout, fare clic su **Disconnetti**.
    
      - Per inoltrare la chiamata alla segreteria telefonica, fare clic su **Inoltra a**segreteria telefonica e quindi digitare un indirizzo di segreteria telefonica nel campo **indirizzo SIP** nel\<formato\>@\<SIP:\> nomeutente DomainName (ad esempio, SIP:bob@contoso.com).
    
      - Per inoltrare la chiamata a un altro numero di telefono, fare clic su **Inoltra a numero di telefono**e quindi nel campo **indirizzo SIP** digitare il numero di telefono nel\<formato\>@\<SIP:\> number domainname (ad esempio, SIP:+14255550121@contoso.com).
    
      - Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra a indirizzo SIP**e quindi nel campo **indirizzo SIP** digitare l'URI dell'utente nel formato\<SIP: nomeutente\>@\<DomainName\>.
    
      - Per inoltrare la chiamata a un'altra coda, fare clic su **Inoltra a un'altra coda** e quindi selezionare la coda che si desidera utilizzare.

10. Fare clic su **Commit**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a>Per utilizzare Windows PowerShell per creare o modificare una coda

1.  Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.
    
    <div>
    

    > [!NOTE]  
    > Se si è uno dei responsabili di Response Group delegati per un flusso di lavoro gestito, è possibile creare gruppi di agenti e code, nonché assegnare i gruppi di agenti alle code.

    
    </div>

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Creare la richiesta da riprodurre quando viene raggiunta la soglia di timeout della coda e salvarla in una variabile. Nella riga di comando eseguire il comando seguente:
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Ad esempio:
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > Per utilizzare un file audio per il messaggio, eseguire il cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>. Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.

    
    </div>

4.  Definire l'azione da eseguire quando viene raggiunta la soglia di timeout della coda e salvarla in una variabile. Nella riga di comando eseguire il comando seguente:
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > Per informazioni dettagliate sulle possibili azioni e sulla relativa sintassi, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.

    
    </div>
    
    Ad esempio:
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  Creare la richiesta da riprodurre quando viene raggiunta la soglia di overflow della coda e salvarla in una variabile. Nella riga di comando eseguire il comando seguente:
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Ad esempio:
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > Per utilizzare un file audio per il messaggio, eseguire il cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>. Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.

    
    </div>

6.  Definire l'azione da eseguire quando viene raggiunta la soglia di overflow della coda e salvarla in una variabile. Nella riga di comando eseguire il comando seguente:
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > Per informazioni dettagliate sulle possibili azioni e sulla relativa sintassi, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.

    
    </div>
    
    Ad esempio:
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  Recuperare il nome del servizio Response Group e assegnarlo a una variabile. Nella riga di comando digitare il comando seguente:
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  Ottenere l'identità del gruppo di agenti da assegnare alla coda. Nella riga di comando eseguire il comando seguente:
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > Per informazioni dettagliate sulla creazione del gruppo di agenti, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A>

    
    </div>

9.  Creare la coda. Nella riga di comando eseguire il comando seguente:
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    Ad esempio:
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. Verificare che la coda sia stata creata. Eseguire il comando seguente:
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a>Vedere anche


[New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[Set-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[Get-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[Remove-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

