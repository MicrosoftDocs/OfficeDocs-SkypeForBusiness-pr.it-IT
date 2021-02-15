---
title: Creare o modificare un gruppo di agenti in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: Creare o modificare un gruppo di agenti in Response Group, in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: dfa09c3341ad47f2646939738cb67db7b7f27304
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837096"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a>Creare o modificare un gruppo di agenti in Skype for Business
 
Creare o modificare un gruppo di agenti in Response Group, in Skype for Business Server VoIP aziendale.
  
Quando si crea un gruppo di agenti, è necessario selezionare gli agenti assegnati al gruppo e specificare impostazioni aggiuntive per il gruppo, ad esempio il metodo di routing e se un agente possa o meno accedere al gruppo e disconnettervisi. 
  
Un agente che deve accedere e disconnettersi dal gruppo, che è diverso dall'accesso o dalla disconnessione da Skype for Business, è chiamato agente formale. Gli agenti formali devono aver effettuato l'accesso al gruppo per poter ricevere le chiamate instradate a tale gruppo. Questo requisito può rivelarsi utile per gli agenti che rispondono alle chiamate provenienti dal gruppo a tempo parziale. Gli agenti formali eseguono l'accesso e la disconnessione dai propri gruppi facendo clic su una voce di menu in Skype for Business per aprire il browser Internet Windows Internet Explorer e visualizzare una console della pagina Web.
  
Un agente che non esegue l'accesso o la disconnessione dal gruppo viene chiamato agente informale. Gli agenti informali vengono automaticamente connessi al gruppo quando a loro volta a skype for Business e non possono disconnettersi dal gruppo.
  
Solo gli utenti che si trovano in locale possono essere agenti. Se un agente viene spostato da in locale a online, le chiamate del Response Group non gli verranno instradate.
  
Utilizzare una delle procedure seguenti per creare o modificare un gruppo di agenti.
  
> [!IMPORTANT]
> Quando si assegnano utenti come agenti del Response Group, informarli che, se è abilitata la modalità Privacy, dovranno cercare i contatti "RGS Presence Watcher" e aggiungerli all'elenco contatti. Gli agenti con modalità privacy abilitata ma nel cui elenco contatti non sono presenti contatti "RGS Presence Watcher" non possono ricevere chiamate per il Response Group. Questa restrizione non si applica agli agenti non in modalità privacy. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a>Per utilizzare il Pannello di controllo di Skype for Business Server per creare o modificare un gruppo di agenti

1. Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.
    
    > [!NOTE]
    > Se si è tra i delegati alla gestione di un Response Group per un flusso di lavoro gestito, è possibile creare gruppi da utilizzare nei flussi di lavoro da gestire. 
  
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di navigazione sinistra fare clic su **Response Group** e quindi su **Gruppo**.
    
4. Nella pagina **Gruppo** effettuare una delle operazioni seguenti:
    
   - Per creare un nuovo gruppo di agenti, fare clic su **Nuovo**. Nel campo di ricerca **Seleziona un servizio** digitare tutto o parte del nome del servizio **ApplicationServer** in cui si desidera aggiungere il gruppo. Nell'elenco di servizi visualizzato fare clic su quello desiderato e quindi premere **OK**.
    
   - Per modificare un gruppo di agenti esistente, digitare tutto o parte del nome del gruppo di agenti nel campo di ricerca. Nell'elenco dei risultati di ricerca fare clic sul gruppo desiderato, fare clic su **Modifica** e quindi su **Mostra dettagli**.
    
5. Nel campo **Nome** digitare il nome da assegnare al gruppo di agenti.
    
6. Nel campo **Descrizione** digitare una descrizione per il gruppo.
    
7. Nel campo **Criteri di partecipazione** selezionare una delle opzioni indicate di seguito per impostare il comportamento di accesso per il gruppo:
    
   - Selezionare **Informale** per specificare che gli agenti del gruppo non devono connettersi e disconnettersi dal gruppo. Gli agenti vengono automaticamente connessi al gruppo quando a loro volta a skype for Business.
    
   - Selezionare **Formale** per specificare che gli agenti inclusi nel gruppo devono eseguire l'accesso e la disconnessione dal gruppo. Quando si seleziona questa opzione, gli agenti selezionano una voce di menu in Skype for Business per aprire Internet Explorer e visualizzare una console della pagina Web per l'accesso e la disconnessione dal gruppo.
    
8. In **Tempo per avviso (secondi)** specificare il numero di secondi per l'invio di uno squillo a un agente prima che la chiamata venga inoltrata al successivo agente disponibile (il valore predefinito è 20 secondi).
    
    > [!IMPORTANT]
    > L'impostazione del tempo per l'invio di un avviso all'agente non può essere superiore a 180 secondi. Se il tempo per l'invio di un avviso all'agente supera i 180 secondi, l'applicazione client respinge la chiamata perché il timer delle transazioni SIP avrà raggiunto il massimo tempo di attesa consentito. 
  
9. In **Metodo di routing** selezionare il metodo per il routing delle chiamate agli agenti del gruppo, nel modo seguente:
    
   - Per offrire una nuova chiamata prima all'agente che è stato  inattivo più a lungo (ha avuto una presenza di Disponibile o **Inattivo** in Skype for Business più a lungo), fare clic su **Inattività più lunga.** 
    
   - Per inoltrare una nuova chiamata a tutti gli agenti disponibili contemporaneamente, fare clic su **Parallelo**. La chiamata verrà inviata al primo agente che la accetta.
    
   - Per inoltrare una nuova chiamata a ogni agente a turno, fare clic su **Round robin**. 
    
   - Per inoltrare sempre una nuova chiamata agli agenti in base all'ordine con cui sono elencati nell'elenco **Agente**, fare clic su **Seriale**. 
    
   - Per offrire una nuova chiamata a tutti gli agenti connessi contemporaneamente a Skype for Business e all'applicazione Response Group, indipendentemente dalla presenza corrente, fare clic su **Operatore.** Gli utenti configurati come agenti possono visualizzare tutte le chiamate in attesa e rispondere alle chiamate in attesa in qualsiasi ordine. La chiamata viene inviata al primo agente che la accetta, dopo di che gli altri agenti non vedono più la chiamata.
    
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
    
      - Se la lista di distribuzione contiene utenti per i quali Lync Server 2010 è abilitato, ma VoIP aziendale non è abilitato, questi verranno aggiunti al gruppo di agenti come agenti di controllo. Assicurarsi che tutti i membri della lista di distribuzione VoIP aziendale abilitati per i propri account utente.
    
    > [!IMPORTANT]
    > Se si utilizza una lista di distribuzione di posta elettronica, le appartenenze nascoste o le liste nascoste potrebbero diventare visibili all'amministratore o agli utenti di Response Group. 
  
    Per rendere visibili le appartenenze nascoste o gli elenchi nascosti, procedere nel modo seguente:
    
     - Se una lista di distribuzione è stata configurata in modo che l'appartenenza sia nascosta e l'amministratore di Response Group assegna la lista di distribuzione alla lista di agenti, gli utenti possono chiamare il gruppo per scoprire chi sono i membri. 
    
     - Se una lista di distribuzione è stata configurata in modo che sia nascosta nell'elenco indirizzi globale di Exchange, l'amministratore di Response Group potrebbe essere in grado di visualizzare la lista di distribuzione e assegnarla alla lista di agenti se il processo di Response Group dispone delle autorizzazioni e dei diritti utente appropriati, anche se l'amministratore non dispone dei diritti e delle autorizzazioni utente appropriati.
    
11. Fare clic su **Commit**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a>Per utilizzare Skype for Business Server Management Shell per creare o modificare un gruppo di agenti

1. Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**
    
3. Utilizzare **New-CsRgsAgentGroup** per creare un nuovo gruppo di agenti. Utilizzare **Set-CsRgsAgentGroup** per modificare un gruppo di agenti esistente. Nella riga di comando digitare il comando seguente:
    
   ```powershell
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    Ad esempio:
    
   ```powershell
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > L'impostazione del tempo per l'invio di un avviso all'agente non può essere superiore a 180 secondi. Se il tempo per l'invio di un avviso all'agente supera i 180 secondi, l'applicazione client respinge la chiamata perché il timer delle transazioni SIP avrà raggiunto il tempo massimo di attesa consentito. 
  
4. Verificare che il gruppo di agenti sia stato creato. Eseguire:
    
   ```powershell
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a>Vedere anche

[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)
