---
title: Creare o modificare una coda in Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: Creare o modificare una coda di Response Group, in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 6a4eb09e144bd7381ababdf37a0905c4ea9bac06
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60842428"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a>Creare o modificare una coda in Skype for Business
 
Creare o modificare una coda di Response Group, in Skype for Business Server VoIP aziendale.
  
Le code contengono i chiamanti fino a quando un agente non risponde alla chiamata. Quando l'applicazione Response Group cerca un agente disponibile, cerca i gruppi di agenti nell'ordine in cui sono elencati. È possibile selezionare i gruppi di agenti assegnati alla coda e specificare il comportamento di quest'ultima, ad esempio limitando il numero di chiamate che possono essere contenute nella coda e per quanto tempo una chiamata può restare in attesa che un agente risponda.
  
Per creare o modificare una coda, utilizzare una delle procedure illustrate di seguito.
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a>Per utilizzare Skype for Business Server pannello di controllo per creare o modificare una coda

1. Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.
    
    > [!NOTE]
    > Se si è uno dei responsabili di Response Group delegati per un flusso di lavoro gestito, è possibile creare o modificare le code di Response Group e assegnarle ai flussi di lavoro gestiti personalmente. 
  
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo.  
    
3. Sulla barra di spostamento sinistra fare clic su **Response Group** e quindi su **Coda**.
    
4. Nella pagina **Coda** eseguire una delle operazioni seguenti:
    
   - Per creare una nuova coda, fare clic su **Nuovo**. In **Seleziona un servizio** digitare nel campo di ricerca parte oppure tutto il nome del servizio **ApplicationServer** in cui si intende aggiungere la coda. Nell'elenco di servizi risultante fare clic sul servizio desiderato e quindi su **OK**.
    
   - Per modificare una coda esistente, digitare tutto o una parte del nome della coda nel campo di ricerca. Nell'elenco di code risultante fare clic sulla coda desiderata, su **Modifica** e quindi su **Mostra dettagli**.
    
5. In **Nome** digitare un nome identificativo della coda.
    
6. In **Descrizione** digitare una descrizione per la coda.
    
7. In **Gruppi** specificare i gruppo che si desidera assegnare alla coda. Eseguire una delle operazioni seguenti: 
    
   - Per aggiungere un gruppo alla coda, fare clic su **Seleziona**. Nel campo di ricerca **Seleziona gruppi** digitare tutto o parte del nome del gruppo di agenti che si intende assegnare alla coda, fare clic sul gruppo desiderato e quindi fare clic su **OK**.
    
   - Per rimuovere un gruppo dalla coda, nell'elenco di gruppi di agenti fare clic sul gruppo che si desidera rimuovere e quindi fare clic su **Rimuovi**.
    
   - Per modificare l'ordine in cui gli agenti vengono ricercati, nell'elenco di gruppi di agenti fare clic su un gruppo e quindi sulla freccia rivolta verso l'alto o verso il basso.
    
     > [!NOTE]
     > Per la ricerca di un agente disponibile per la coda, il server utilizza l'ordine dei gruppi. La ricerca pertanto viene eseguita prima nel primo gruppo, quindi nel secondo gruppo dell'elenco e così via. 
  
8. Per specificare un periodo di tempo massimo in cui un chiamante resta in attesa prima che un agente risponda alla chiamata, selezionare la casella di controllo **Abilita timeout coda** e quindi eseguire le operazioni seguenti:
    
    a. In **Periodo di timeout (secondi)** specificare il numero massimo di secondi che un chiamante può attendere prima che un agente risponda alla chiamata.
    
    b. In **Azione chiamata** selezionare l'azione che deve essere eseguita quando si verifica il timeout di una chiamata, come indicato di seguito:
    
   - Per disconnettere la chiamata dopo il timeout, fare clic su **Disconnetti**.
    
   - Per inoltrare la chiamata alla segreteria telefonica, fare clic su Inoltra alla segreteria telefonica e quindi nel campo Indirizzo **SIP** digitare un indirizzo della segreteria telefonica nel formato sip: *\<username\>* @  *\<domainname\>* (ad esempio, sip:bob@contoso.com).
    
   - Per inoltrare la chiamata a un altro numero di telefono, fare clic su Inoltra a numero di telefono **e** quindi nel campo Indirizzo **SIP** digitare il numero di telefono nel formato sip: *\<number\>* @  *\<domainname\>* (ad esempio, sip:+14255550121@contoso.com).
    
   - Per inoltrare la chiamata a un altro utente, fare clic su Inoltra all'indirizzo **SIP** e quindi nel campo Indirizzo **SIP** digitare l'URI dell'utente nel formato sip: _\<username\>_ @  _\<domainname\>_ .
    
   - Per inoltrare la chiamata a un'altra coda, fare clic su **Inoltra a un'altra coda** e quindi selezionare la coda che si desidera utilizzare.
    
9. Per specificare il numero massimo di chiamate che possono essere contenute nella coda, selezionare la casella di controllo **Abilita overflow coda** e quindi eseguire le operazioni seguenti:
    
    a. In **Numero massimo di chiamate** selezionare il numero massimo di chiamate che possono essere contenute nella coda. 
    
    b. In **Inoltra la chiamata** selezionare quale chiamata dovrà essere inoltrata quando la coda è piena, ovvero **Chiamata più recente** o **Chiamata meno recente**.
    
    c. In **Azione chiamata** selezionare l'azione che deve essere eseguita quando viene raggiunta la soglia di overflow, come indicato di seguito:
    
   - Per disconnettere la chiamata dopo il timeout, fare clic su **Disconnetti**.
    
   - Per inoltrare la chiamata alla segreteria telefonica, fare clic su Inoltra alla segreteria telefonica e quindi nel campo Indirizzo **SIP** digitare un indirizzo della segreteria telefonica nel formato sip: *\<username\>* @  *\<domainname\>* (ad esempio, sip:bob@contoso.com).
    
   - Per inoltrare la chiamata a un altro numero di telefono, fare clic su Inoltra a numero di telefono **e** quindi nel campo Indirizzo **SIP** digitare il numero di telefono nel formato sip: *\<number\>* @  *\<domainname\>* (ad esempio, sip:+14255550121@contoso.com).
    
   - Per inoltrare la chiamata a un altro utente, fare clic su Inoltra all'indirizzo **SIP** e quindi nel campo Indirizzo **SIP** digitare l'URI dell'utente nel formato sip: _\<username\>_ @  _\<domainname\>_ .
    
   - Per inoltrare la chiamata a un'altra coda, fare clic su **Inoltra a un'altra coda** e quindi selezionare la coda che si desidera utilizzare.
    
10. Fare clic su **Commit**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a>Per utilizzare Skype for Business Server Management Shell per creare o modificare una coda

1. Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.
    
    > [!NOTE]
    > Se si è uno dei responsabili di Response Group delegati per un flusso di lavoro gestito, è possibile creare gruppi di agenti e code, nonché assegnare i gruppi di agenti alle code. 
  
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
3. Creare la richiesta da riprodurre quando viene raggiunta la soglia di timeout della coda e salvarla in una variabile. Nella riga di comando eseguire il comando seguente:
    
   ```powershell
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   Ad esempio:
    
   ```console
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > Per utilizzare un file audio per il messaggio, eseguire il cmdlet **Import-CsRgsAudioFile**. Per informazioni dettagliate, [vedere Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
4. Definire l'azione da eseguire quando viene raggiunta la soglia di timeout della coda e salvarla in una variabile. Nella riga di comando eseguire il comando seguente:
    
   ```powershell
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > Per informazioni dettagliate sulle possibili azioni e sulla relativa sintassi, [vedere New-CsRgsCallAction.](/powershell/module/skype/new-csrgscallaction?view=skype-ps) 
  
    Ad esempio:
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. Creare la richiesta da riprodurre quando viene raggiunta la soglia di overflow della coda e salvarla in una variabile. Nella riga di comando eseguire il comando seguente:
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   Ad esempio:
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > Per utilizzare un file audio per il messaggio, eseguire il cmdlet **Import-CsRgsAudioFile**. Per informazioni dettagliate, [vedere Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
6. Definire l'azione da eseguire quando viene raggiunta la soglia di overflow della coda e salvarla in una variabile. Nella riga di comando eseguire il comando seguente:
    
   ```powershell
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > Per informazioni dettagliate sulle possibili azioni e sulla relativa sintassi, [vedere New-CsRgsCallAction.](/powershell/module/skype/new-csrgscallaction?view=skype-ps) 
  
    Ad esempio:
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. Recuperare il nome del servizio Response Group Service e assegnarlo a una variabile. Nella riga di comando digitare il comando seguente:
    
   ```powershell
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. Ottenere l'identità del gruppo di agenti da assegnare alla coda. Nella riga di comando eseguire il comando seguente:
    
   ```powershell
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > Per informazioni dettagliate sulla creazione del gruppo di agenti, [vedere New-CsRgsAgentGroup](/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
9. Creare la coda. Nella riga di comando eseguire il comando seguente:
    
   ```powershell
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   Ad esempio:
    
   ```powershell
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. Verificare che la coda sia stata creata. Eseguire il comando seguente:
    
    ```powershell
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a>Vedere anche

[New-CsRgsQueue](/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[Set-CsRgsQueue](/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[New-CsRgsPrompt](/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[Get-CsRgsQueue](/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[Remove-CsRgsQueue](/powershell/module/skype/remove-csrgsqueue?view=skype-ps)