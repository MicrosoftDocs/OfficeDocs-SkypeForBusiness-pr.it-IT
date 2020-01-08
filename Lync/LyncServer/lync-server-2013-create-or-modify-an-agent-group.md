---
title: 'Lync Server 2013: creare o modificare un gruppo di agenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify an agent group
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205370(v=OCS.15)
ms:contentKeyID: 48185784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0a2765e9ba72501b148e61d0d38789a46b2c3bc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a>Creare o modificare un gruppo di agenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-07_

Per creare o modificare un gruppo di agenti, usare una delle procedure seguenti.

<div>


> [!NOTE]  
> Un amministratore, ad esempio CsVoiceAdministrator, deve abilitare gli utenti per Enterprise Voice e Lync Server prima che gli utenti possano essere assegnati a gruppi di agenti. Se si è uno dei responsabili del gruppo di risposte delegati per un flusso di lavoro gestito, è possibile creare gruppi di agenti e usare i gruppi di agenti nei flussi di lavoro gestiti.



</div>

<div>


> [!IMPORTANT]  
> Quando si assegnano gli utenti come agenti del gruppo di risposta, informarli che, se la modalità di privacy è abilitata, devono cercare i contatti "RGS Presence Watcher" e aggiungerli al proprio elenco contatti. Gli agenti che hanno abilitato la modalità privacy, ma che non hanno "Watcher presenza RGS" nell'elenco contatti, non possono ricevere chiamate al Response Group. Gli agenti che non hanno la modalità di privacy abilitata non sono interessati.



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a>Per usare il pannello di controllo di Lync Server per creare o modificare un gruppo di agenti

1.  Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.
    
    <div>
    

    > [!NOTE]  
    > Se si è uno dei responsabili del gruppo di risposte delegati per un flusso di lavoro gestito, è possibile creare gruppi e usarli nei flussi di lavoro gestiti.

    
    </div>

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **gruppi di risposte**e quindi su **raggruppa**.

4.  Nella pagina del **gruppo** eseguire una delle operazioni seguenti:
    
      - Per creare un nuovo gruppo di agenti, fare clic su **nuovo**. Nel campo **selezionare un servizio** di ricerca digitare tutto o parte del nome del servizio **ApplicationServer** in cui si vuole aggiungere il gruppo. Nell'elenco dei servizi risultante fare clic sul servizio desiderato e quindi fare clic su **OK**.
    
      - Per modificare un gruppo di agenti esistente, digitare tutto o parte del nome del gruppo di agenti nel campo di ricerca. Nell'elenco risultante fare clic sul gruppo desiderato, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  In **nome**Digitare un nome identificativo per il gruppo di agenti.

6.  In **Descrizione**Digitare una descrizione per il gruppo.

7.  Nei **criteri di partecipazione**selezionare una delle opzioni seguenti per configurare il comportamento di accesso per il gruppo:
    
      - Selezionare **informale** per specificare che gli agenti del gruppo non devono eseguire l'accesso e disconnettersi dal gruppo. Gli agenti hanno eseguito l'accesso automatico al gruppo quando accedono a Lync Server 2013.
    
      - Selezionare **formale** per specificare che gli agenti del gruppo devono accedere e disconnettersi dal gruppo. Quando si seleziona questa opzione, gli agenti fanno clic su una voce di menu in Lync per aprire Internet Explorer e visualizzare una console della pagina Web per l'accesso e la disconnessione del gruppo.

8.  In **tempo di avviso (secondi)** specificare il numero di secondi per chiamare un agente prima di offrire la chiamata al successivo agente disponibile (il valore predefinito è 20 secondi).
    
    <div>
    

    > [!IMPORTANT]  
    > L'impostazione dell'ora di avviso dell'agente non può superare 180 secondi. Se il tempo di avviso dell'agente supera 180 secondi, l'applicazione client rifiuta la chiamata perché il timer della transazione SIP raggiunge il tempo massimo di attesa.

    
    </div>

9.  In **metodo di routing**selezionare il metodo per il routing delle chiamate agli agenti nel gruppo, come indicato di seguito:
    
      - Per offrire una nuova chiamata prima all'agente che è stato inattivo più a lungo (ha avuto una presenza di **disponibile** o **inattivo** in Lync Server il più lungo), fare clic su **inattivo più lungo**.
    
      - Per offrire una nuova chiamata a tutti gli agenti disponibili simultaneamente, fare clic su **parallelo**. La chiamata verrà inviata al primo agente che la accetta.
    
      - Per offrire una nuova chiamata a ogni agente, fare clic su **Round Robin**.
    
      - Per offrire sempre una nuova chiamata agli agenti nell'ordine in cui sono elencate nell'elenco **agente** , fare clic su **seriale**.
    
      - Per offrire una nuova chiamata a tutti gli agenti che hanno effettuato l'accesso contemporaneamente a Lync Server 2013 e all'applicazione Response Group, indipendentemente dalla presenza corrente, fare clic su **Assistente**. Gli utenti di Lync 2010 Attendant configurati come agenti possono vedere tutte le chiamate in attesa e rispondere alle chiamate in attesa in qualsiasi ordine. La chiamata viene inviata al primo agente che lo accetta, dopodiché gli altri utenti del supervisore di Lync 2010 non vedranno più la chiamata.

10. In **agenti**specificare come si vuole creare l'elenco agenti:
    
      - Per usare un elenco personalizzato di agenti, fare clic su **Definisci un gruppo di agenti personalizzato**ed eseguire una delle operazioni seguenti:
        
          - Per aggiungere un utente al gruppo di agenti, fare clic su **Seleziona**e quindi nel campo **Seleziona agenti** di ricerca digitare tutto o parte del nome dell'utente che si vuole aggiungere al gruppo e quindi fare clic su **trova**. Nell'elenco di agenti risultante fare clic sull'utente e quindi fare clic su **OK**.
        
          - Per rimuovere un utente dal gruppo agente, nell'elenco di agenti fare clic sull'utente da rimuovere e quindi fare clic su **Rimuovi**.
        
          - Per modificare l'ordine in cui gli agenti vengono offerti chiamate in gruppi che usano il routing o l'instradamento seriale di Round Robin, nell'elenco di agenti fare clic su un utente e quindi fare clic sulla freccia su o freccia giù.
    
      - Per usare una lista di distribuzione di Microsoft Exchange Server come gruppo di agenti, fare clic su **Usa una lista di distribuzione di posta elettronica esistente**e quindi, nell' **indirizzo della lista di distribuzione**, digitare l'indirizzo di posta elettronica della lista di distribuzione, ad esempio NetworkSupport@contoso.com.
        
        Se si usa una lista di distribuzione di posta elettronica, si è soggetti ai vincoli seguenti:
        
          - Non è possibile selezionare più liste di distribuzione per il gruppo di agenti. Ogni gruppo supporta solo una singola lista di distribuzione.
        
          - Se la lista di distribuzione contiene una o più liste di distribuzione, i membri delle liste di distribuzione annidate non vengono aggiunti all'elenco di agenti.
        
          - Se è selezionata l'opzione routing seriale o Round Robin, il server offre una chiamata in arrivo all'agente appropriato in base al metodo di routing e in base all'ordine in cui gli agenti sono elencati nella lista di distribuzione.
        
          - Se la lista di distribuzione contiene utenti per cui è abilitato Lync Server 2010 ma VoIP aziendale non è abilitato, verranno aggiunti al gruppo agente come agenti disfunzionali. Assicurarsi che tutti i membri della lista di distribuzione abbiano abilitato VoIP aziendale per gli account utente.
        
        <div>
        

        > [!IMPORTANT]  
        > Se si usa una lista di distribuzione di posta elettronica, le appartenenze nascoste o gli elenchi nascosti potrebbero diventare visibili per l'amministratore del gruppo di risposte o per gli utenti.

        
        </div>
        
        Le appartenenze nascoste o gli elenchi nascosti possono diventare visibili come indicato di seguito:
        
          - Se è stata configurata una lista di distribuzione in modo che l'appartenenza sia nascosta e l'amministratore del gruppo di risposte assegna la lista di distribuzione all'elenco di agenti, gli utenti possono chiamare il gruppo per scoprire chi sono i membri.
        
          - Se è stata configurata una lista di distribuzione in modo che sia nascosta nell'elenco indirizzi globale di Exchange, l'amministratore del gruppo di risposte potrebbe essere in grado di vedere la lista di distribuzione e assegnarla all'elenco di agenti se il processo del gruppo di risposta ha i diritti utente appropriati e autorizzazioni, anche se l'amministratore non dispone dei diritti utente e delle autorizzazioni appropriate.

11. Fare clic su **Commit**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a>Per usare Windows PowerShell per creare o modificare un gruppo di agenti

1.  Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  USA **New-CsRgsAgentGroup** per creare un nuovo gruppo di agenti. Usare **Set-CsRgsAgentGroup** per modificare un gruppo di agenti esistente. Nella riga di comando eseguire:
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    Ad esempio:
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > L'impostazione dell'ora di avviso dell'agente non può superare 180 secondi. Se il tempo di avviso dell'agente è maggiore di 180 secondi, l'applicazione client rifiuta la chiamata perché il timer della transazione SIP raggiunge il tempo massimo di attesa.

    
    </div>

4.  Verificare che il gruppo di agenti sia stato creato. Eseguire
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Eliminare un gruppo di agenti in Lync Server 2013](lync-server-2013-delete-an-agent-group.md)  


[Gestione dei gruppi di agenti di Response Group in Lync Server 2013](lync-server-2013-managing-response-group-agent-groups.md)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

