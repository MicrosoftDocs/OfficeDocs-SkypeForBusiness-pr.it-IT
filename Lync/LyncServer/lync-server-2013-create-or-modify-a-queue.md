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
ms.openlocfilehash: 77bad1729c67c363dc56eaf8788e57caabd51876
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-queue-in-lync-server-2013"></a>Creare o modificare una coda in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Usare una delle procedure seguenti per creare o modificare una coda.

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a>Per usare il pannello di controllo di Lync Server per creare o modificare una coda

1.  Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.
    
    <div>
    

    > [!NOTE]  
    > Se si è uno dei responsabili del gruppo di risposte delegati per un flusso di lavoro gestito, è possibile creare o modificare code di Response Group e assegnarle ai flussi di lavoro gestiti.

    
    </div>

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Response Groups**, quindi fare clic su **Accoda**.

4.  Nella pagina **coda** eseguire una delle operazioni seguenti:
    
      - Per creare una nuova coda, fare clic su **nuovo**. In **Seleziona un servizio**Digitare parte o tutto il nome del servizio **ApplicationServer** in cui si vuole aggiungere la coda nel campo di ricerca. Nell'elenco dei servizi risultante fare clic sul servizio desiderato e quindi fare clic su **OK**.
    
      - Per modificare una coda esistente, digitare tutto o parte del nome della coda nel campo di ricerca. Nell'elenco di code risultante fare clic sulla coda desiderata, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  In **nome**Digitare un nome identificativo per la coda.

6.  In **Descrizione**Digitare una descrizione per la coda.

7.  In **gruppi**specificare i gruppi che si desidera assegnare alla coda. Esegui una delle operazioni seguenti:
    
      - Per aggiungere un gruppo alla coda, fare clic su **Seleziona**. Nel campo **Seleziona gruppi** digitare tutto o parte del nome del gruppo di agenti che si vuole assegnare alla coda, fare clic sul gruppo di agenti desiderato e quindi fare clic su **OK**.
    
      - Per rimuovere un gruppo dalla coda, nell'elenco dei gruppi di agenti fare clic sul gruppo che si desidera rimuovere e quindi fare clic su **Rimuovi**.
    
      - Per modificare l'ordine in cui vengono cercati gli agenti, nell'elenco dei gruppi di agenti fare clic su un gruppo e quindi fare clic sulla freccia su o freccia giù.
        
        <div>
        

        > [!NOTE]  
        > Quando il server Cerca un agente disponibile per la coda, usa l'ordine dei gruppi. Il primo gruppo dell'elenco viene quindi cercato per primo, seguito dal secondo gruppo nell'elenco e così via.

        
        </div>

8.  Per specificare un periodo di tempo massimo per il chiamante in attesa in attesa prima che un agente risponda alla chiamata, selezionare la casella di controllo **Abilita timeout coda** e quindi eseguire le operazioni seguenti:
    
    1.  Nel **periodo di timeout (secondi)** specificare il numero massimo di secondi in cui il chiamante attende che un agente risponda alla chiamata.
    
    2.  In **azione chiamata**selezionare l'azione che si verifica quando una chiamata ha un timeout come segue:
    
    <!-- end list -->
    
      - Per disconnettere la chiamata dopo il timeout, fare clic su **Disconnetti**.
    
      - Per inoltrare la chiamata alla segreteria telefonica, fare clic su **inoltra alla**segreteria telefonica e quindi, nel campo **indirizzo SIP** , digitare un indirizzo di segreteria\<telefonica\>@\<nel formato\> SIP: nomeutente nomedominio (ad esempio, SIP:bob@contoso.com).
    
      - Per inoltrare la chiamata a un altro numero di telefono, fare clic su **inoltra al numero**di telefono e quindi, nel campo **indirizzo SIP** , digitare il numero di\<telefono\>@\<nel formato\> SIP: Number NomeDominio (ad esempio, SIP:+14255550121@contoso.com).
    
      - Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra all'indirizzo SIP**e quindi, nel campo **indirizzo SIP** , digitare l'URI per l'utente nel formato\<SIP\>@\<: nomeutente\>NomeDominio.
    
      - Per inoltrare la chiamata a un'altra coda, fare clic su **Inoltra a un'altra coda**e quindi passare alla coda che si vuole usare.

9.  Per specificare un numero massimo di chiamate che la coda può contenere, selezionare la casella di controllo **attiva l'overflow delle code** e quindi eseguire le operazioni seguenti:
    
    1.  In **numero massimo di chiamate**selezionare il numero massimo di chiamate che la coda deve contenere.
    
    2.  In **inoltra la chiamata**selezionare la chiamata da inoltrare quando la coda è piena: chiamata più **recente** o **chiamata più vecchia**.
    
    3.  In **azione chiamata**selezionare l'azione che si verifica quando la soglia di overflow viene soddisfatta come segue:
    
    <!-- end list -->
    
      - Per disconnettere la chiamata dopo il timeout, fare clic su **Disconnetti**.
    
      - Per inoltrare la chiamata alla segreteria telefonica, fare clic su **inoltra alla**segreteria telefonica e quindi, nel campo **indirizzo SIP** , digitare un indirizzo di segreteria\<telefonica\>@\<nel formato\> SIP: nomeutente nomedominio (ad esempio, SIP:bob@contoso.com).
    
      - Per inoltrare la chiamata a un altro numero di telefono, fare clic su **inoltra al numero**di telefono e quindi, nel campo **indirizzo SIP** , digitare il numero di\<telefono\>@\<nel formato\> SIP: Number NomeDominio (ad esempio, SIP:+14255550121@contoso.com).
    
      - Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra all'indirizzo SIP**e quindi, nel campo **indirizzo SIP** , digitare l'URI per l'utente nel formato\<SIP\>@\<: nomeutente\>NomeDominio.
    
      - Per inoltrare la chiamata a un'altra coda, fare clic su **Inoltra a un'altra coda**e quindi passare alla coda che si vuole usare.

10. Fare clic su **Commit**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a>Per usare Windows PowerShell per creare o modificare una coda

1.  Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.
    
    <div>
    

    > [!NOTE]  
    > Se si è uno dei responsabili del gruppo di risposte delegati per un flusso di lavoro gestito, sarà possibile creare gruppi di agenti e code e assegnare gruppi di agenti alle code.

    
    </div>

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Creare il prompt da riprodurre quando viene soddisfatta la soglia di timeout della coda e salvarla in una variabile. Nella riga di comando eseguire:
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Ad esempio:
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > Per usare un file audio per la richiesta, usare il cmdlet <STRONG>Import-CsRgsAudioFile</STRONG> . Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.

    
    </div>

4.  Definire l'azione da intraprendere quando viene soddisfatta la soglia di timeout della coda e salvarla in una variabile. Nella riga di comando eseguire:
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > Per informazioni dettagliate sulle possibili azioni e sulla relativa sintassi, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.

    
    </div>
    
    Ad esempio:
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  Creare il prompt da riprodurre quando viene soddisfatta la soglia di overflow della coda e salvarla in una variabile. Nella riga di comando eseguire:
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Ad esempio:
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > Per usare un file audio per la richiesta, usare il cmdlet <STRONG>Import-CsRgsAudioFile</STRONG> . Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.

    
    </div>

6.  Definire l'azione da intraprendere quando viene soddisfatta la soglia di overflow della coda e salvarla in una variabile. Nella riga di comando eseguire:
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > Per informazioni dettagliate sulle possibili azioni e sulla relativa sintassi, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.

    
    </div>
    
    Ad esempio:
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  Recuperare il nome del servizio per il servizio Response Group e assegnarlo a una variabile. Nella riga di comando eseguire:
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  Ottenere l'identità del gruppo di agenti da assegnare alla coda. Nella riga di comando eseguire:
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > Per informazioni dettagliate sulla creazione del gruppo di agenti, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A>

    
    </div>

9.  Creare la coda. Nella riga di comando eseguire:
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    Ad esempio:
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. Verificare che la coda sia stata creata. Eseguire
    
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

