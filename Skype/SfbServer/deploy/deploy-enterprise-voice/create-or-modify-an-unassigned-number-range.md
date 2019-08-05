---
title: Creare o modificare un intervallo di numeri non assegnati in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: Creare, modificare o eliminare intervalli di numeri non assegnati per l'applicazione di annunci in Skype for Business Server VoIP aziendale. Ciò influenza il modo in cui vengono gestite le chiamate a numeri non assegnati.
ms.openlocfilehash: 5b9afa463d6eaff2f6ba3ed283d11556bd95bc03
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190412"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a>Creare o modificare un intervallo di numeri non assegnati in Skype for Business Server
 
Creare, modificare o eliminare intervalli di numeri non assegnati per l'applicazione di annunci in Skype for Business Server VoIP aziendale. Ciò influenza il modo in cui vengono gestite le chiamate a numeri non assegnati.
  
Skype for Business Server ti consente di dire cosa succede alle chiamate in arrivo ai numeri di telefono validi per l'organizzazione, ma non viene assegnato a un utente o a un telefono. Per gestire tali chiamate, è necessario configurare una tabella dei numeri non assegnati. È possibile usare la tabella per instradare le chiamate a un'applicazione di annuncio o a un server Messaggistica unificata di Exchange.
  
La configurazione della tabella dei numeri non assegnati dipende dall'utilizzo previsto di questa. È possibile configurare la tabella con tutti gli interni validi dell'organizzazione, solo con gli interni non assegnati o con una combinazione di numeri di entrambi i tipi. La tabella dei numeri non assegnati può includere sia numeri assegnati che numeri non assegnati ma viene chiamata solo se un chiamante compone un numero non assegnato. Se nella tabella dei numeri non assegnati si inseriscono tutti gli interni validi, è possibile specificare l'azione da eseguire quando un utente lascia l'organizzazione, senza alcuna necessità di riconfigurare la tabella. Se si includono estensioni non assegnate nella tabella, è possibile modificare l'azione che si verifica per i numeri specifici. Ad esempio, se si modifica l'estensione per il servizio di assistenza clienti, è possibile includere il vecchio numero di servizio clienti nella tabella e quindi assegnarlo a un annuncio che fornisce il nuovo numero.
  
## <a name="configure-unassigned-phone-numbers"></a>Configurare i numeri di telefono non assegnati

Usare una delle procedure seguenti per configurare gli intervalli di numeri non assegnati per l'applicazione di annuncio.
  
> [!IMPORTANT]
> Prima di configurare la tabella dei numeri non assegnati, è necessario che il sistema disponga già di annunci definiti o di un operatore automatico di messaggistica UNIFICAta di Exchange. 
  
> [!TIP]
> Quando qualcuno chiama un numero non assegnato, Skype for Business Server esegue la ricerca nella tabella numeri non assegnati dall'alto verso il basso e usa il primo intervallo corrispondente. Deve quindi essere specificata un'azione che si vuole eseguire come ultima risorsa per l'ultimo intervallo della tabella. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a>Per usare il pannello di controllo di Skype for Business Server per configurare i numeri di telefono non assegnati

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere delegare le **autorizzazioni di configurazione**.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **caratteristiche vocali**e quindi su **numero non assegnato**.
    
4. Nella pagina **numero non assegnati** eseguire una delle operazioni seguenti:
    
   - Per creare un nuovo intervallo di numeri, fare clic su **nuovo**. In **nome**Digitare un nome identificativo per l'intervallo di numeri.
    
     > [!NOTE]
     > Dopo aver eseguito il commit del nuovo intervallo di numeri non assegnati al database, non è possibile modificare questo nome. 
  
   - Per modificare un intervallo di numeri esistente, digitare tutto o parte del nome dell'intervallo di numeri nel campo di ricerca. Nell'elenco di intervalli di numeri risultante fare clic sul nome desiderato, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
5. Nel campo primo **intervallo di numeri** Digitare il numero iniziale dell'intervallo, quindi digitare il numero finale dell'intervallo nel secondo campo **intervallo di numeri** .
    
   - Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale dell'intervallo stesso.
    
   - Se il numero di inizio dell'intervallo o il numero finale dell'intervallo include un numero di interno, sia il numero iniziale che il numero finale dell'intervallo devono includere un'estensione e il numero di interno deve essere uguale sia per il numero iniziale che per il numero finale.
    
   - Il numero deve corrispondere all'espressione regolare (Tel:)? \+)? [1-9] \d{0,17}(; EXT = [1-9] \d{0,9})?. Questo significa che il numero può iniziare con la stringa tel: (se non specifichi quella stringa, verrà automaticamente aggiunta per te), un segno più (+) e una cifra da 1 a 9. Il numero di telefono può contenere fino a 17 cifre e può essere seguito da un interno nel formato ;ext= seguito dal numero dell'interno.
    
6. In **servizio annunci**eseguire una delle operazioni seguenti: 
    
   - Fare clic su **annuncio**.
    
   - Fare clic su **messaggistica unificata di Exchange**.
    
7. Se nel passaggio precedente è stato fatto clic su **annuncio**, eseguire le operazioni seguenti:
    
    un. In **FQDN del server di destinazione**, fare clic su **Seleziona**, fare clic sull'ID servizio del servizio applicazione che esegue l'applicazione di annuncio che gestirà le chiamate in arrivo in questo intervallo di numeri non assegnati e quindi fare clic su **OK**.
    
    b. In **annuncio**fare clic sull'annuncio da riprodurre per l'intervallo di numeri non assegnati.
    
8. Se nel passaggio precedente è stato fatto clic su **um Exchange**, in **numero di telefono operatore automatico**fare clic su **Seleziona**, fare clic sul numero di telefono da usare per l'intervallo di numeri non assegnati e quindi fare clic su **OK**.
    
9. Fare clic su **OK**.
    
10. Nella pagina **numero non assegnati** verificare che gli intervalli di numeri non assegnati siano disposti nell'ordine desiderato. Per modificare la posizione di un intervallo nella tabella, fare clic su uno o più nomi consecutivi nell'elenco di intervalli e quindi fare clic sulla freccia su o freccia giù.
    
    > [!TIP]
    > Skype for Business Server cerca nella tabella numeri non assegnati dall'alto verso il basso e usa il primo intervallo che corrisponde al numero non assegnato. Se si hanno intervalli sovrapposti e un intervallo specifica un'ultima azione di ricorso, verificare che l'intervallo sia nella parte inferiore dell'elenco. 
  
11. Quando si hanno gli intervalli di numeri non assegnati nell'ordine desiderato, fare clic su **commit tutti**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a>Per usare Skype for Business Server Management Shell per configurare i numeri di telefono non assegnati

1. Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di **configurazione**Delegate.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. USA **New-CsUnassignedNumber** per creare un nuovo intervallo di numeri non assegnati. Usare **Set-CsUnassignedNumber** per modificare un intervallo di numeri non assegnati esistente.
    
    > [!TIP]
    > Se si hanno intervalli sovrapposti e si vogliono applicare gli intervalli in un ordine specifico, includere il parametro Priority. L'intervallo con la priorità più alta verrà applicato alla chiamata. Il valore 0 rappresenta la priorità più alta.
  
    Nella riga di comando eseguire una delle operazioni seguenti:
    
   - Per creare un intervallo di numeri per un servizio di annuncio, eseguire:
    
     ```
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - In alternativa, per creare un intervallo di numeri per l'operatore automatico di messaggistica unificata di Exchange, eseguire:
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     Ad esempio:
    
     ```
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     O
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     L'esempio seguente mostra come modificare i numeri in un intervallo di numeri non assegnati esistente:
    
     ```
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a>Eliminare un intervallo di numeri unnasigned

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a>Per usare il pannello di controllo di Skype for Business Server per eliminare un intervallo di numeri non assegnati

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere delegare le **autorizzazioni di configurazione**.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **caratteristiche vocali** e quindi su **numero non assegnato**.
    
4. Nel campo di ricerca della pagina **numero non assegnato** digitare tutto o parte del nome dell'intervallo di numeri non assegnati che si desidera eliminare.
    
5. Nell'elenco risultante di intervalli di numeri fare clic sul nome, scegliere **modifica**e quindi fare clic su **Elimina**.
    
6. Fare clic su **commit tutti**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a>Per usare Skype for Business Server Management Shell per eliminare un intervallo di numeri non assegnati

1. Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di **configurazione**Delegate.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Nella riga di comando digitare:
    
   ```
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    Ad esempio:
    
   ```
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > Per informazioni dettagliate su altre opzioni, vedere [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps). 
  
## <a name="see-also"></a>Vedere anche

[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
