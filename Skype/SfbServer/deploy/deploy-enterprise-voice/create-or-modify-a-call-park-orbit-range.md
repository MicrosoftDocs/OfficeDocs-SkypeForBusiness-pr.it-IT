---
title: Creare o modificare un intervallo di orbit del parcheggio di chiamata in Skype for Business
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
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Creare o modificare una tabella dell'intervallo di orbit del parcheggio di chiamata in Skype for Business Server VoIP aziendale.
---

# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a>Creare o modificare un intervallo di orbit del parcheggio di chiamata in Skype for Business

Creare o modificare una tabella dell'intervallo di orbit del parcheggio di chiamata in Skype for Business Server VoIP aziendale.

Parcheggio di chiamata utilizza orbit per le chiamate di parcheggio. Prima che gli utenti possano parcheggiare e recuperare le chiamate, è necessario configurare la tabella orbit del parcheggio di chiamata. È necessario specificare gli intervalli di numeri di interno (orbit) che l'organizzazione riserva per le chiamate di parcheggio e definire il routing per tali intervalli specificando quale pool di parcheggio di chiamata gestisce ogni intervallo. Quando si definiscono gli intervalli di codici orbit, l'obiettivo è quello di disporre di un numero sufficiente di codici orbit tale da evitare che uno stesso codice orbit venga riutilizzato troppo rapidamente, ma senza eccedere limitando il numero di interni disponibili per gli utenti o altri servizi. È possibile creare più intervalli di orbit del parcheggio di chiamata per ogni pool Skype for Business Server in cui viene distribuita l'applicazione Parcheggio di chiamata. Ogni intervallo di orbit del parcheggio di chiamata deve avere un nome univoco globale e un set univoco di estensioni.

> [!IMPORTANT]
> Un intervallo di codici orbit include in genere al massimo 100 codici orbit. Ogni intervallo può essere più grande, purché sia più piccolo del massimo di 10.000 codici orbit per intervallo e ogni pool includa meno di 50.000 codici orbit. Se un intervallo è troppo piccolo, i codici orbit vengono riutilizzati più rapidamente.

Utilizzare blocchi di estensioni virtuali, ovvero a cui non sono assegnati utenti o telefoni, per gli intervalli di codici orbit.

> [!NOTE]
> L'assegnazione di numeri DID (Direct Inward Dialing) come numeri orbit nella tabella orbit del parcheggio di chiamata non è supportata.

Per creare o modificare un intervallo orbit del parcheggio di chiamata, usare una delle procedure seguenti.

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Per utilizzare il Skype for Business Server di controllo per creare o modificare un intervallo di numeri per le chiamate di parcheggio

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere **Delegate Setup Permissions**.

2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo.

3. Sulla barra di spostamento sinistra fare clic su **Funzionalità vocali** e quindi su **Parcheggio di chiamata**.

4. Nella pagina **Parcheggio di chiamata** effettuare una delle operazioni seguenti:

   - Per creare un nuovo intervallo orbit, fare clic su **Nuovo**. In **Nome** digitare un nome per identificare l'intervallo di numeri.

     > [!NOTE]
     > Dopo l'esecuzione del commit dell'intervallo orbit nel database non sarà possibile modificare il nome.

   - Per modificare un intervallo orbit esistente, digitarne il nome, per intero o in parte, nel campo di ricerca. Nell'elenco dei codici orbit risultante fare clic sul codice desiderato, fare clic su **Modifica** e quindi su **Mostra dettagli**.

5. Nel primo campo **Intervallo numeri** digitare il numero iniziale dell'intervallo di estensioni per i codici orbit di parcheggio di chiamata e nel secondo campo **Intervallo numeri** digitare il numero finale dell'intervallo. Tenere presente che:

   - Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale.

   - Il valore del numero iniziale dell'intervallo deve avere la stessa lunghezza del numero finale.

   - L'intervallo di codici orbit deve essere univoco. Tale intervallo non può sovrapporsi ad altri intervalli.

   - Se l'intervallo orbit inizia con il carattere \* o #, l'intervallo deve essere maggiore di 100.

   - Valori validi: deve corrispondere alla stringa dell'espressione regolare ([\\*|#]?[ 1-9]\d{0,7})| ([1-9]\d{0,8}). Questo significa che il valore deve essere \* una stringa che inizia con il carattere o # o un numero da 1 a 9 (il primo carattere non può essere uno zero). Se il primo carattere è \* o #, il carattere seguente deve essere un numero da 1 a 9 (non può essere uno zero). I caratteri successivi possono essere da qualsiasi numero da 0 a 9 fino a sette caratteri aggiuntivi (ad esempio, "#6000", "\*92000", "\*95551212" e "915551212"). \* Se il primo carattere non è o #, il primo carattere deve essere un numero da 1 a 9 (non può essere zero), seguito da un massimo di otto caratteri, ognuno da 0 a 9 (ad esempio, "915551212", "41212", "300").

   - In totale non vi possono essere più di 50.000 codici orbit per ogni pool. Ogni intervallo di codici orbit in genere comprende al massimo 100 codici orbit, ma può essere anche molto più esteso, purché non superi i 10.000 codici orbit. Ad esempio, anziché specificare "7000000" come numero iniziale e "8000000" come numero finale, considerare la possibilità di specificare "7000000" e "7000100" rispettivamente come numero iniziale e numero finale.

6. In **FQDN del server di destinazione** fare clic sul nome di dominio completo (FQDN) o sull'ID del servizio dell'applicazione che ospita l'applicazione Parcheggio di chiamata. Tutte le chiamate parcheggiate nei numeri dell'intervallo specificato dal numero iniziale e dal numero finale dell'intervallo di codici orbit saranno instradate a tale server o pool.

7. Fare clic su **Commit**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Per utilizzare Skype for Business Server Management Shell per creare o modificare un intervallo di numeri per le chiamate di parcheggio

1. Accedere al computer in cui Skype for Business Server Management Shell è installato come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in **Delegate Setup Permissions**.

2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start****, scegliere** Tutti i programmi, **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell**.

3. Usare **New-CsCallParkOrbit** per creare un nuovo intervallo di numeri orbit. Usare **Set-CsCallParkOrbit** per modificare un intervallo di numeri orbit esistente.

    Nella riga di comando digitare il comando seguente:

   ```powershell
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    Ad esempio:

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    L'esempio seguente mostra come modificare i numeri di un intervallo orbit esistente.

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a>Vedere anche

[New-CsCallParkOrbit](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Eliminare un intervallo di codici orbit del parcheggio di chiamata](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)