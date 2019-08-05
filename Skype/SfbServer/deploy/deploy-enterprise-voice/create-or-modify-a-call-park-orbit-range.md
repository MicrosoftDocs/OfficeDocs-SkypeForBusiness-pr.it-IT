---
title: Creare o modificare un intervallo orbit di Call Park in Skype for business
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
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Creare o modificare una tabella di Orbit range di Call Park in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 77be47597e5bbb674719ac2b3192efdf4217a3dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190430"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a>Creare o modificare un intervallo orbit di Call Park in Skype for business

Creare o modificare una tabella di Orbit range di Call Park in Skype for Business Server VoIP aziendale.

Call Park USA orbite per le chiamate di parcheggio. Prima che gli utenti possano parcheggiare e recuperare le chiamate, è necessario configurare la tabella Orbit di Call Park. Devi specificare gli intervalli di numeri di interno (orbite) che l'organizzazione riserva alle chiamate di parcheggio e definire il routing per tali intervalli specificando il pool di parcheggio di chiamata che gestisce ogni intervallo. Quando definisci intervalli orbitali, l'obiettivo è quello di avere orbite sufficienti in modo che una qualsiasi orbita non venga riutilizzata troppo rapidamente, ma non così tante orbite che limiti il numero di estensioni disponibili per gli utenti o altri servizi. È possibile creare più intervalli orbit di Call Park per ogni pool di Skype for Business Server in cui è distribuita l'applicazione Parcheggio di chiamata. Ogni intervallo di Orbit di Call Park deve avere un nome univoco globale e un set di estensioni univoco.

> [!IMPORTANT]
> Un intervallo orbit include in genere 100 o meno orbite. Ogni intervallo può essere molto più grande, purché sia più piccolo del massimo di 10.000 orbite per intervallo e si hanno meno di 50.000 orbite per ogni pool. Se un intervallo è troppo piccolo, le orbite vengono riutilizzate più rapidamente.

Usare blocchi di estensioni virtuali (estensioni che non hanno un utente o un telefono assegnato) per gli intervalli di Orbit.

> [!NOTE]
> L'assegnazione di numeri DID (Direct Inward Dialing) come numeri di orbita nella tabella Orbit di parcheggio delle chiamate non è supportata.

Usare una delle procedure seguenti per creare o modificare un intervallo di orbit del parcheggio di chiamata.

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Per usare il pannello di controllo di Skype for Business Server per creare o modificare un intervallo di numeri per le chiamate di parcheggio

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere delegare le **autorizzazioni di configurazione**.

2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.

3. Sulla barra di spostamento sinistra fare clic su **caratteristiche vocali** e quindi su **Call Park**.

4. Nella pagina **Call Park** eseguire una delle operazioni seguenti:

   - Per creare un nuovo intervallo di Orbit, fare clic su **nuovo**. In **nome**Digitare un nome identificativo per l'intervallo di numeri.

     > [!NOTE]
     > Dopo aver eseguito il commit dell'intervallo di Orbit nel database, non è possibile modificare questo nome.

   - Per modificare un intervallo di orbit esistente, digitare tutto o parte del nome dell'intervallo di Orbit nel campo di ricerca. Nell'elenco risultante di orbite fare clic sull'orbita desiderata, fare clic su **modifica**e quindi su **Mostra dettagli**.

5. Nel campo primo **intervallo di numeri** Digitare il numero di inizio dell'intervallo di estensioni per l'orbita del parcheggio di chiamata, quindi digitare il numero finale dell'intervallo nel secondo campo dell' **intervallo di numeri** . Tenere presente che:

   - Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale dell'intervallo stesso.

   - Il valore del numero iniziale dell'intervallo deve avere la stessa lunghezza del numero finale.

   - L'intervallo di orbit deve essere univoco. Questo intervallo non può sovrapporsi ad altri intervalli.

   - Se l'intervallo orbit inizia con il carattere \* o #, l'intervallo deve essere maggiore di 100.

   - Valori validi: deve corrispondere alla stringa di espressione regolare (\\[* | #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}). Questo significa che il valore deve essere una stringa che inizia con il \* carattere o # o un numero da 1 a 9 (il primo carattere non può essere uno zero). Se il primo carattere è \* o #, il carattere seguente deve essere un numero da 1 a 9 (non può essere uno zero). I caratteri successivi possono essere qualsiasi numero da 0 a 9 fino a sette caratteri aggiuntivi (ad esempio, "#6000"\*, "92000"\*, "95551212" e "915551212"). Se il primo carattere non \* è o #, il primo carattere deve essere un numero da 1 a 9 (non può essere zero), seguito da un massimo di otto caratteri, ognuno dei quali è compreso tra 0 e 9, ad esempio "915551212", "41212", "300".

   - Non dovresti avere più di un totale di 50.000 orbite per ogni pool. Ogni intervallo orbit include in genere 100 o meno orbite, ma può essere molto più grande purché includa meno di 10.000 orbite. Anziché specificare un numero iniziale "7000000" e un numero finale "8000000", ad esempio, valutare la possibilità di specificare un numero iniziale "7000000" e un numero finale "7000100".

6. In **FQDN del server di destinazione**, fare clic sul nome di dominio completo (FQDN) o sull'ID servizio del servizio applicazione che ospita l'applicazione Parcheggio di chiamata. Tutte le chiamate parcheggiate in numeri compresi nell'intervallo specificato dal numero di inizio e dal numero finale nell'intervallo di Orbit verranno indirizzate a questo server o pool.

7. Fare clic su **Commit**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Per usare Skype for Business Server Management Shell per creare o modificare un intervallo di numeri per le chiamate di parcheggio

1. Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di **configurazione**Delegate.

2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

3. USA **New-CsCallParkOrbit** per creare un nuovo intervallo di numeri orbitali. Usare **set-CsCallParkOrbit** per modificare un intervallo esistente di numeri di orbita.

    Nella riga di comando eseguire:

   ```
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    Ad esempio:

   ```
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    L'esempio seguente mostra come modificare i numeri in un intervallo di orbit esistente,

   ```
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a>Vedere anche

[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Eliminare un intervallo di Orbit di Call Park](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
