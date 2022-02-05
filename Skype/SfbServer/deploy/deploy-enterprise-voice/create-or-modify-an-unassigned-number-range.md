---
title: Creare o modificare un intervallo di numeri non assegnati in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ms.custom: null
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: 'Creare, modificare o eliminare intervalli di numeri non assegnati per l''applicazione Annuncio in Skype for Business Server VoIP aziendale. Ciò influisce sulla modalità di gestione delle chiamate ai numeri non assegnati.'
---

# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a>Creare o modificare un intervallo di numeri non assegnati in Skype for Business Server
 
Creare, modificare o eliminare intervalli di numeri non assegnati per l'applicazione Annuncio in Skype for Business Server VoIP aziendale. Ciò influisce sulla modalità di gestione delle chiamate ai numeri non assegnati.
  
Skype for Business Server consente di dire cosa accade alle chiamate in arrivo a numeri di telefono validi per l'organizzazione, ma non assegnati a un utente o a un telefono. Per gestire tali chiamate, è necessario impostare una tabella dei numeri non assegnati. È possibile utilizzare la tabella per instradare le chiamate a un'applicazione Annuncio o a un Exchange di messaggistica unificata.
  
La configurazione della tabella dei numeri non assegnati dipende dal modo in cui si desidera utilizzarla. È possibile configurare la tabella con tutti gli interni validi dell'organizzazione, solo con gli interni non assegnati o con una combinazione di numeri di entrambi i tipi. La tabella dei numeri non assegnati può includere sia numeri assegnati che numeri non assegnati ma viene richiamata solo se un chiamante compone un numero non assegnato. Se nella tabella dei numeri non assegnati si inseriscono tutti gli interni validi, è possibile specificare l'azione da eseguire quando un utente lascia l'organizzazione, senza alcuna necessità di riconfigurare la tabella. Se nella tabella si inseriscono interni non assegnati, è possibile modificare l'azione da eseguire per numeri specifici. Se ad esempio si modifica l'interno del servizio di assistenza clienti, è possibile inserire il vecchio numero nella tabella e quindi assegnarlo a un annuncio in cui viene indicato il nuovo numero.
  
## <a name="configure-unassigned-phone-numbers"></a>Configurare i numeri di telefono non assegnati

Utilizzare una delle procedure seguenti per configurare intervalli di numeri non assegnati per l'applicazione Annuncio.
  
> [!IMPORTANT]
> Prima di configurare la tabella dei numeri non assegnati, è necessario che nel sistema sia già stato definito Annunci o che sia stata configurata una Operatore automatico messaggistica unificata di Exchange. 
  
> [!TIP]
> Quando un utente chiama un numero non assegnato, Skype for Business Server ricerca nella tabella dei numeri non assegnati dall'alto verso il basso e utilizza il primo intervallo corrispondente. Pertanto, per l'ultimo intervallo della tabella è consigliabile specificare un'azione che si desidera venga eseguita come ultima risorsa. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a>Per utilizzare il Skype for Business Server di controllo per configurare i numeri di telefono non assegnati

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere **Delegate Setup Permissions**.
    
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo.  
    
3. Sulla barra di spostamento sinistra fare clic su **Funzionalità vocali** e quindi su **Numero non assegnato**.
    
4. Nella pagina **Numero non assegnato** eseguire una delle operazioni seguenti:
    
   - Per creare un nuovo intervallo di numeri, fare clic su **Nuovo**. In **Nome** digitare un nome che identifichi l'intervallo di numeri.
    
     > [!NOTE]
     > Dopo l'esecuzione del commit del nuovo intervallo di numeri non assegnati nel database non sarà possibile modificare il nome. 
  
   - Per modificare un intervallo di numeri esistente, digitare tutto o una parte del nome dell'intervallo di numeri nel campo di ricerca. Nell'elenco di intervalli di numeri risultante fare clic sul nome desiderato, su **Modifica** e quindi su **Mostra dettagli**.
    
5. Nel primo campo **Intervallo numeri** digitare il numero iniziale dell'intervallo e nel secondo campo **Intervallo numeri** digitare il numero finale.
    
   - Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale dell'intervallo stesso.
    
   - Se il numero iniziale o il numero finale dell'intervallo include un numero di interno, devono includerlo entrambi. Il numero di interno deve essere lo stesso per ambedue.
    
   - Il numero deve corrispondere all'espressione regolare `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?`. Questo significa che `tel:` il numero può iniziare con la stringa (se non si specifica tale stringa, verrà aggiunta automaticamente), un segno più (+) e una cifra da 1 a 9. Il numero di telefono può contenere fino a 17 cifre e può essere seguito da un interno nel formato ;ext= seguito dal numero dell'interno.
    
6. In **Servizio Annuncio** eseguire una delle operazioni seguenti: 
    
   - Fare clic su **Annuncio**.
    
   - Fare clic su **Messaggistica unificata di Exchange**.
    
7. Se nel passaggio precedente si è fatto clic su **Annuncio**, eseguire le operazioni seguenti:
    
    a. In **FQDN del server di destinazione** fare clic su **Seleziona**, sull'ID del servizio applicazione che esegue l'applicazione Annuncio che gestirà le chiamate in arrivo per questo intervallo di numeri non assegnati e quindi su **OK**.
    
    b. In **Annuncio** fare clic sull'annuncio da riprodurre per l'intervallo di numeri non assegnati.
    
8. Se nel passaggio precedente si è fatto clic su **Messaggistica unificata di Exchange**, in **Numero di telefono operatore automatico** fare clic su **Seleziona**, quindi sul numero di telefono da utilizzare per l'intervallo di numeri non assegnati e quindi fare clic su **OK**.
    
9. Fare clic su **OK**.
    
10. Nella pagina **Numero non assegnato** verificare che gli intervalli di numeri non assegnati siano disposti nell'ordine desiderato. Per modificare la posizione di un intervallo nella tabella, fare clic su uno o più nomi consecutivi nell'elenco di intervalli e quindi fare clic sulla freccia in su o sulla freccia in giù.
    
    > [!TIP]
    > Skype for Business Server ricerca nella tabella dei numeri non assegnati dall'alto verso il basso e utilizza il primo intervallo corrispondente al numero non assegnato. Se vi sono intervalli che si sovrappongono e per un intervallo è specificata un'azione da eseguire come ultimo tentativo, verificare che tale intervallo si trovi alla fine dell'elenco. 
  
11. Quando gli intervalli di numeri non assegnati si trovano nell'ordine desiderato, fare clic su **Salva tutto**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a>Per utilizzare Skype for Business Server Management Shell per configurare i numeri di telefono non assegnati

1. Accedere al computer in cui Skype for Business Server Management Shell è installato come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in **Delegate Setup Permissions**.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start****, scegliere** Tutti i programmi, **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Utilizzare **New-CsUnassignedNumber** per creare un nuovo intervallo di numeri non assegnati. Utilizzare **Set-CsUnassignedNumber** per modificare un intervallo di numeri non assegnati esistente.
    
    > [!TIP]
    > Se vi sono intervalli che si sovrappongono e si desidera che gli intervalli vengano applicati in un ordine specifico, includere il parametro Priority. Alla chiamata verrà applicato l'intervallo con la priorità più alta. Il valore 0 rappresenta la priorità più alta.
  
    Nella riga di comando eseguire una delle operazioni seguenti:
    
   - Per creare un intervallo di numeri per un servizio Annuncio, eseguire quanto segue:
    
     ```powershell
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - Per creare un intervallo di numeri per l'Operatore automatico messaggistica unificata di Exchange, eseguire quanto segue:
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     Ad esempio:
    
     ```powershell
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     Oppure
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     Nell'esempio seguente viene illustrato come modificare i numeri di un intervallo di numeri non assegnati esistente:
    
     ```powershell
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a>Eliminare un intervallo di numeri non assegnati

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a>Per utilizzare Skype for Business Server pannello di controllo per eliminare un intervallo di numeri non assegnati

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere **Delegate Setup Permissions**.
    
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo.  
    
3. Sulla barra di spostamento sinistra fare clic su **Funzionalità vocali** e quindi su **Numero non assegnato**.
    
4. Nel campo di ricerca della pagina **Numero non assegnato** digitare per intero o in parte il nome dell'intervallo di numeri non assegnati che si desidera eliminare.
    
5. Nell'elenco risultante degli intervalli di numeri fare clic sul nome, su **Modifica** e quindi su **Elimina**.
    
6. Fare clic su **Salva tutto**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a>Per utilizzare Skype for Business Server Management Shell per eliminare un intervallo di numeri non assegnati

1. Accedere al computer in cui Skype for Business Server Management Shell è installato come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in **Delegate Setup Permissions**.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start****, scegliere** Tutti i programmi, **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Nella riga di comando digitare il comando seguente:
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    Ad esempio:
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > Per informazioni dettagliate su altre opzioni, [vedere Remove-CsCallParkOrbit](/powershell/module/skype/remove-cscallparkorbit?view=skype-ps). 
  
## <a name="see-also"></a>Vedere anche

[New-CsUnassignedNumber](/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[Set-CsUnassignedNumber](/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[Get-CsUnassignedNumber](/powershell/module/skype/get-csunassignednumber?view=skype-ps)