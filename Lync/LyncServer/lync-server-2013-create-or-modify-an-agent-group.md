---
title: 'Lync Server 2013: creare o modificare un gruppo di agenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an agent group
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205370(v=OCS.15)
ms:contentKeyID: 48185784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b60ba1c402a629c0a85b2bd99dc4819da3455660
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a>Creare o modificare un gruppo di agenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-07_

Utilizzare una delle procedure seguenti per creare o modificare un gruppo di agenti.

<div>


> [!NOTE]  
> Un amministratore, ad esempio CsVoiceAdministrator, deve abilitare gli utenti per VoIP aziendale e Lync Server prima che gli utenti possano essere assegnati ai gruppi di agenti. Se si è tra i delegati alla gestione di un Response Group per un flusso di lavoro gestito, è possibile creare gruppi di agenti da utilizzare nei flussi di lavoro da gestire.



</div>

<div>


> [!IMPORTANT]  
> Quando si assegnano utenti come agenti del Response Group, informarli che, se è abilitata la modalità Privacy, dovranno cercare i contatti "RGS Presence Watcher" e aggiungerli all'elenco contatti. Gli agenti con modalità privacy abilitata ma nel cui elenco contatti non sono presenti contatti "RGS Presence Watcher" non possono ricevere chiamate per il Response Group. Questa restrizione non si applica agli agenti non in modalità privacy.



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a>Per utilizzare il pannello di controllo di Lync Server per creare o modificare un gruppo di agenti

1.  Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.
    
    <div>
    

    > [!NOTE]  
    > Se si è tra i delegati alla gestione di un Response Group per un flusso di lavoro gestito, è possibile creare gruppi da utilizzare nei flussi di lavoro da gestire.

    
    </div>

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di navigazione sinistra fare clic su **Response Group** e quindi su **Gruppo**.

4.  Nella pagina **Gruppo** effettuare una delle operazioni seguenti:
    
      - Per creare un nuovo gruppo di agenti, fare clic su **Nuovo**. Nel campo di ricerca **Seleziona un servizio** digitare tutto o parte del nome del servizio **ApplicationServer** in cui si desidera aggiungere il gruppo. Nell'elenco di servizi visualizzato fare clic su quello desiderato e quindi premere **OK**.
    
      - Per modificare un gruppo di agenti esistente, digitare tutto o parte del nome del gruppo di agenti nel campo di ricerca. Nell'elenco dei risultati di ricerca fare clic sul gruppo desiderato, fare clic su **Modifica** e quindi su **Mostra dettagli**.

5.  Nel campo **Nome** digitare il nome da assegnare al gruppo di agenti.

6.  Nel campo **Descrizione** digitare una descrizione per il gruppo.

7.  Nel campo **Criteri di partecipazione** selezionare una delle opzioni indicate di seguito per impostare il comportamento di accesso per il gruppo:
    
      - Selezionare **Informale** per specificare che gli agenti del gruppo non devono connettersi e disconnettersi dal gruppo. Gli agenti vengono automaticamente connessi al gruppo quando eseguono l'accesso a Lync Server 2013.
    
      - Selezionare **Formale** per specificare che gli agenti inclusi nel gruppo devono eseguire l'accesso e la disconnessione dal gruppo. Quando si seleziona questa opzione, gli agenti fanno clic su una voce di menu in Lync per aprire Internet Explorer e visualizzare una console di pagina Web per l'accesso e la disconnessione del gruppo.

8.  In **Tempo per avviso (secondi)** specificare il numero di secondi per l'invio di uno squillo a un agente prima che la chiamata venga inoltrata al successivo agente disponibile (il valore predefinito è 20 secondi).
    
    <div>
    

    > [!IMPORTANT]  
    > L'impostazione del tempo per l'invio di un avviso all'agente non può essere superiore a 180 secondi. Se il tempo per l'invio di un avviso all'agente supera i 180 secondi, l'applicazione client respinge la chiamata perché il timer delle transazioni SIP avrà raggiunto il massimo tempo di attesa consentito.

    
    </div>

9.  In **Metodo di routing** selezionare il metodo per il routing delle chiamate agli agenti del gruppo, nel modo seguente:
    
      - Per offrire una nuova chiamata prima all'agente che è stato inattivo più a lungo (ha avuto una presenza **disponibile** o **inattivo** in Lync Server più a lungo), fare clic su **inattività più lunga**.
    
      - Per inoltrare una nuova chiamata a tutti gli agenti disponibili contemporaneamente, fare clic su **Parallelo**. La chiamata verrà inviata al primo agente che la accetta.
    
      - Per inoltrare una nuova chiamata a ogni agente a turno, fare clic su **Round robin**.
    
      - Per inoltrare sempre una nuova chiamata agli agenti in base all'ordine con cui sono elencati nell'elenco **Agente**, fare clic su **Seriale**.
    
      - Per offrire una nuova chiamata a tutti gli agenti che hanno eseguito l'accesso contemporaneamente a Lync Server 2013 e all'applicazione Response Group, indipendentemente dalla presenza corrente, fare clic su **operatore**. Gli utenti di Lync 2010 Attendant che sono configurati come agenti possono visualizzare tutte le chiamate in attesa e rispondere alle chiamate in attesa in qualsiasi ordine. La chiamata viene inviata al primo agente che lo accetta, dopo il quale gli altri utenti dell'operatore di Lync 2010 non vedranno più la chiamata.

10. In **Agenti** specificare in che modo si desidera creare l'elenco degli agenti:
    
      - Per utilizzare un elenco personalizzato di agenti, fare clic su **Definisci un gruppo di agenti personalizzato** ed eseguire una delle operazioni seguenti:
        
          - Per aggiungere un utente al gruppo di agenti, fare clic su **Seleziona**, nel campo di ricerca **Seleziona agenti** digitare tutto o parte del nome dell'utente desiderato e quindi fare clic su **Trova**. Nell'elenco di agenti risultante fare clic sull'utente e quindi su **OK**.
        
          - Per rimuovere un utente dal gruppo di agenti, nell'elenco di agenti fare clic sull'utente desiderato e quindi su **Rimuovi**.
        
          - Per modificare l'ordine in cui vengono inoltrate le chiamate agli agenti nei gruppi con il routing round robin o seriale, nell'elenco degli agenti fare clic su un utente e quindi sulla freccia verso l'alto o verso il basso.
    
      - Per utilizzare una lista di distribuzione di Microsoft Exchange Server come gruppo di agenti, fare clic su **Usa una lista di distribuzione di posta elettronica esistente** e quindi in **Indirizzo lista di distribuzione** digitare l'indirizzo di posta elettronica della lista di distribuzione, ad esempio NetworkSupport@contoso.com.
        
        Se si utilizza una lista di distribuzione di posta elettronica, verranno applicate le restrizioni seguenti:
        
          - Non è possibile selezionare più liste di distribuzione per il gruppo di agenti. Ogni gruppo supporta una sola lista di distribuzione.
        
          - Se la lista di distribuzione contiene una o più liste di distribuzione, i membri delle liste di distribuzione annidate non verranno aggiunti all'elenco di agenti.
        
          - Se è selezionato il routing seriale o round robin, il server inoltra una chiamata in arrivo all'agente appropriato in base al metodo di routing e all'ordine con cui sono elencati gli agenti nella lista di distribuzione.
        
          - Se la lista di distribuzione contiene gli utenti per i quali è abilitato Lync Server 2010 ma VoIP aziendale non è abilitato, verrà aggiunto al gruppo di agenti come agente disfunzionale. Assicurarsi che tutti i membri della lista di distribuzione abbiano abilitato VoIP aziendale per gli account utente.
        
        <div>
        

        > [!IMPORTANT]  
        > Se si utilizza una lista di distribuzione di posta elettronica, le appartenenze nascoste o gli elenchi nascosti possono diventare visibili per l'amministratore o gli utenti di Response Group.

        
        </div>
        
        Per rendere visibili le appartenenze nascoste o gli elenchi nascosti, procedere nel modo seguente:
        
          - Se una lista di distribuzione è stata configurata in modo che l'appartenenza sia nascosta e che l'amministratore di Response Group assegni la lista di distribuzione all'elenco degli agenti, gli utenti possono chiamare il gruppo per scoprire chi sono i membri.
        
          - Se una lista di distribuzione è stata configurata in modo che sia nascosta nell'elenco indirizzi globale di Exchange, l'amministratore del Response Group potrebbe essere in grado di visualizzare la lista di distribuzione e assegnarla all'elenco di agenti se il processo di Response Group ha i diritti utente e autorizzazioni, anche se l'amministratore non dispone dei diritti utente e delle autorizzazioni appropriate.

11. Fare clic su **Commit**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a>Per utilizzare Windows PowerShell per creare o modificare un gruppo di agenti

1.  Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Utilizzare **New-CsRgsAgentGroup** per creare un nuovo gruppo di agenti. Utilizzare **Set-CsRgsAgentGroup** per modificare un gruppo di agenti esistente. Nella riga di comando digitare il comando seguente:
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    Ad esempio:
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > L'impostazione del tempo per l'invio di un avviso all'agente non può essere superiore a 180 secondi. Se il tempo per l'invio di un avviso all'agente supera i 180 secondi, l'applicazione client respinge la chiamata perché il timer delle transazioni SIP avrà raggiunto il tempo massimo di attesa consentito.

    
    </div>

4.  Verificare che il gruppo di agenti sia stato creato. Eseguire:
    
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

