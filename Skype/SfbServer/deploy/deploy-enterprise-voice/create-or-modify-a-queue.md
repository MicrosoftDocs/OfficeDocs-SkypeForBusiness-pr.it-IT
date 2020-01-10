---
title: Creare o modificare una coda in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: Creare o modificare una coda di Response Group in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 9027c239c92c7c04b9de8b5579d7ebb73069b1a3
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001706"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a>Creare o modificare una coda in Skype for business
 
Creare o modificare una coda di Response Group in Skype for Business Server VoIP aziendale.
  
Le code contengono i chiamanti finché un agente non risponde alla chiamata. Quando l'applicazione Response Group cerca un agente disponibile, esegue la ricerca in gruppi di agenti nell'ordine in cui vengono elencati. È possibile selezionare i gruppi di agenti assegnati alla coda e specificare il comportamento della coda, ad esempio limitando il numero di chiamate che la coda può contenere e il periodo di tempo in cui una chiamata attende finché un agente non risponde alla chiamata.
  
Usare una delle procedure seguenti per creare o modificare una coda.
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a>Per usare il pannello di controllo di Skype for Business Server per creare o modificare una coda

1. Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.
    
    > [!NOTE]
    > Se si è uno dei responsabili del gruppo di risposte delegati per un flusso di lavoro gestito, è possibile creare o modificare code di Response Group e assegnarle ai flussi di lavoro gestiti. 
  
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.  
    
3. Nella barra di spostamento sinistra fare clic su **Response Groups**, quindi fare clic su **Accoda**.
    
4. Nella pagina **coda** eseguire una delle operazioni seguenti:
    
   - Per creare una nuova coda, fare clic su **nuovo**. In **Seleziona un servizio**Digitare parte o tutto il nome del servizio **ApplicationServer** in cui si vuole aggiungere la coda nel campo di ricerca. Nell'elenco dei servizi risultante fare clic sul servizio desiderato e quindi fare clic su **OK**.
    
   - Per modificare una coda esistente, digitare tutto o parte del nome della coda nel campo di ricerca. Nell'elenco di code risultante fare clic sulla coda desiderata, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
5. In **nome**Digitare un nome identificativo per la coda.
    
6. In **Descrizione**Digitare una descrizione per la coda.
    
7. In **gruppi**specificare i gruppi che si desidera assegnare alla coda. Esegui una delle operazioni seguenti: 
    
   - Per aggiungere un gruppo alla coda, fare clic su **Seleziona**. Nel campo **Seleziona gruppi** digitare tutto o parte del nome del gruppo di agenti che si vuole assegnare alla coda, fare clic sul gruppo di agenti desiderato e quindi fare clic su **OK**.
    
   - Per rimuovere un gruppo dalla coda, nell'elenco dei gruppi di agenti fare clic sul gruppo che si desidera rimuovere e quindi fare clic su **Rimuovi**.
    
   - Per modificare l'ordine in cui vengono cercati gli agenti, nell'elenco dei gruppi di agenti fare clic su un gruppo e quindi fare clic sulla freccia su o freccia giù.
    
     > [!NOTE]
     > Quando il server Cerca un agente disponibile per la coda, usa l'ordine dei gruppi. Il primo gruppo dell'elenco viene quindi cercato per primo, seguito dal secondo gruppo nell'elenco e così via. 
  
8. Per specificare un periodo di tempo massimo per il chiamante in attesa in attesa prima che un agente risponda alla chiamata, selezionare la casella di controllo **Abilita timeout coda** e quindi eseguire le operazioni seguenti:
    
    un. Nel **periodo di timeout (secondi)** specificare il numero massimo di secondi in cui il chiamante attende che un agente risponda alla chiamata.
    
    b. In **azione chiamata**selezionare l'azione che si verifica quando una chiamata ha un timeout come segue:
    
   - Per disconnettere la chiamata dopo il timeout, fare clic su **Disconnetti**.
    
   - Per inoltrare la chiamata alla segreteria telefonica, fare clic su **inoltra alla**segreteria telefonica e quindi, nel campo **indirizzo SIP** , digitare un indirizzo di segreteria telefonica nel formato SIP: * \<\>nomeutente*@ *\<NomeDominio\> * (ad esempio, SIP:bob@contoso.com).
    
   - Per inoltrare la chiamata a un altro numero di telefono, fare clic su **inoltra al numero**di telefono e quindi, nel campo **indirizzo SIP** , digitare il numero di telefono nel formato SIP: * \<\>Number*@ *\<\> NomeDominio* (ad esempio, SIP:+14255550121@contoso.com).
    
   - Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra all'indirizzo SIP**e quindi, nel campo **indirizzo SIP** , digitare l'URI per l'utente nel formato SIP: _ \<\>nomeutente_@ _\<NomeDominio\>_.
    
   - Per inoltrare la chiamata a un'altra coda, fare clic su **Inoltra a un'altra coda**e quindi passare alla coda che si vuole usare.
    
9. Per specificare un numero massimo di chiamate che la coda può contenere, selezionare la casella di controllo **attiva l'overflow delle code** e quindi eseguire le operazioni seguenti:
    
    un. In **numero massimo di chiamate**selezionare il numero massimo di chiamate che la coda deve contenere. 
    
    b. In **inoltra la chiamata**selezionare la chiamata da inoltrare quando la coda è piena: chiamata più **recente** o **chiamata più vecchia**.
    
    c. In **azione chiamata**selezionare l'azione che si verifica quando la soglia di overflow viene soddisfatta come segue:
    
   - Per disconnettere la chiamata dopo il timeout, fare clic su **Disconnetti**.
    
   - Per inoltrare la chiamata alla segreteria telefonica, fare clic su **inoltra alla**segreteria telefonica e quindi, nel campo **indirizzo SIP** , digitare un indirizzo di segreteria telefonica nel formato SIP: * \<\>nomeutente*@ *\<NomeDominio\> * (ad esempio, SIP:bob@contoso.com).
    
   - Per inoltrare la chiamata a un altro numero di telefono, fare clic su **inoltra al numero**di telefono e quindi, nel campo **indirizzo SIP** , digitare il numero di telefono nel formato SIP: * \<\>Number*@ *\<\> NomeDominio* (ad esempio, SIP:+14255550121@contoso.com).
    
   - Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra all'indirizzo SIP**e quindi, nel campo **indirizzo SIP** , digitare l'URI per l'utente nel formato SIP: _ \<\>nomeutente_@ _\<NomeDominio\>_.
    
   - Per inoltrare la chiamata a un'altra coda, fare clic su **Inoltra a un'altra coda**e quindi passare alla coda che si vuole usare.
    
10. Fare clic su **Commit**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a>Per usare Skype for Business Server Management Shell per creare o modificare una coda

1. Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.
    
    > [!NOTE]
    > Se si è uno dei responsabili del gruppo di risposte delegati per un flusso di lavoro gestito, sarà possibile creare gruppi di agenti e code e assegnare gruppi di agenti alle code. 
  
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Creare il prompt da riprodurre quando viene soddisfatta la soglia di timeout della coda e salvarla in una variabile. Nella riga di comando eseguire:
    
   ```powershell
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   Ad esempio:
    
   ```console
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > Per usare un file audio per la richiesta, usare il cmdlet **Import-CsRgsAudioFile** . Per informazioni dettagliate, vedere [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
4. Definire l'azione da intraprendere quando viene soddisfatta la soglia di timeout della coda e salvarla in una variabile. Nella riga di comando eseguire:
    
   ```powershell
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > Per informazioni dettagliate sulle possibili azioni e sulla relativa sintassi, vedere [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Ad esempio:
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. Creare il prompt da riprodurre quando viene soddisfatta la soglia di overflow della coda e salvarla in una variabile. Nella riga di comando eseguire:
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   Ad esempio:
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > Per usare un file audio per la richiesta, usare il cmdlet **Import-CsRgsAudioFile** . Per informazioni dettagliate, vedere [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
6. Definire l'azione da intraprendere quando viene soddisfatta la soglia di overflow della coda e salvarla in una variabile. Nella riga di comando eseguire:
    
   ```powershell
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > Per informazioni dettagliate sulle possibili azioni e sulla relativa sintassi, vedere [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Ad esempio:
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. Recuperare il nome del servizio per il servizio Response Group e assegnarlo a una variabile. Nella riga di comando eseguire:
    
   ```powershell
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. Ottenere l'identità del gruppo di agenti da assegnare alla coda. Nella riga di comando eseguire:
    
   ```powershell
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > Per informazioni dettagliate sulla creazione del gruppo di agenti, vedere [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
9. Creare la coda. Nella riga di comando eseguire:
    
   ```powershell
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   Ad esempio:
    
   ```powershell
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. Verificare che la coda sia stata creata. Eseguire
    
    ```powershell
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a>Vedere anche

[New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[Set-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[Get-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[Remove-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)
