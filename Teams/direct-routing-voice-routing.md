---
title: Configurare il routing vocale per il routing diretto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informazioni su come configurare il routing vocale con il routing diretto di Microsoft Phone System.
ms.openlocfilehash: e87d7d04f9b2477d65e08f461ac3ff113b4d0e7c
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530993"
---
# <a name="configure-voice-routing-for-direct-routing"></a>Configurare il routing vocale per il routing diretto

Questo articolo descrive come configurare il routing vocale per il routing diretto del sistema telefonico.  Questo è il passaggio 3 dei passaggi seguenti per la configurazione del routing diretto:

- Passaggio 1. [Connettere il SBC con il sistema telefonico Microsoft e convalidare la connessione](direct-routing-connect-the-sbc.md) 
- Passaggio 2. [Abilitare gli utenti per il routing diretto, la voce e la segreteria telefonica](direct-routing-enable-users.md)
- **Passaggio 3. Configurare il routing vocale** (questo articolo)
- Passaggio 4. [Tradurre i numeri in un formato alternativo](direct-routing-translate-numbers.md) 

Per informazioni su tutti i passaggi necessari per la configurazione del routing diretto, vedere [configurare il routing diretto](direct-routing-configure.md).

## <a name="voice-routing-overview"></a>Panoramica del routing vocale

Microsoft Phone System include un meccanismo di routing che consente di inviare una chiamata a un SBC (Session Border Controller) specifico basato su: 

- Modello di numero definito 
- Il modello di numero chiamato più l'utente specifico che effettua la chiamata
 
SBCs può essere designato come attivo e backup. Quando l'SBC configurato come attivo non è disponibile per una route di chiamata specifica, la chiamata verrà instradata a un SBC di backup.
 
Il routing vocale è costituito dagli elementi seguenti: 

- **Criteri di routing vocale** : un contenitore per gli usi PSTN, che può essere assegnato a un utente o a più utenti. 

- **Usi PSTN** : un contenitore per le route vocali e gli usi PSTN, che possono essere condivisi in criteri di routing vocale diversi. 

- **Route vocali** : uno schema numerico e un set di gateway PSTN online da usare per le chiamate in cui il numero chiamante corrisponde allo schema.

- **Gateway PSTN online** : puntatore a un SBC che memorizza anche la configurazione applicata quando viene inserita una chiamata tramite SBC, ad esempio inoltra P-Asserted-Identity (PAI) o codec preferiti; possono essere aggiunte alle route vocali.

## <a name="voice-routing-policy-considerations"></a>Considerazioni sui criteri di routing vocale

Se un utente ha una licenza per il piano di chiamata, le chiamate in uscita dell'utente vengono instradate automaticamente tramite l'infrastruttura PSTN del piano di chiamata Microsoft. Se si configurano e si assegnano criteri di routing vocale online a un utente del piano chiamante, le chiamate in uscita dell'utente vengono controllate per determinare se il numero composto corrisponde a uno schema numerico definito nel criterio di routing vocale online. Se c'è una corrispondenza, la chiamata viene instradata tramite il trunk di routing diretto. Se non è presente alcuna corrispondenza, la chiamata viene instradata tramite l'infrastruttura PSTN del piano di chiamata.

> [!CAUTION]
> Se si configurano e si applicano i criteri di routing vocale online globali (a livello di organizzazione), tutti gli utenti abilitati per la voce della società erediteranno tali criteri, che potrebbero causare chiamate PSTN da parte di utenti del piano chiamante inavvertitamente indirizzati a un trunk di routing diretto. Se non si vuole che tutti gli utenti usino i criteri di routing vocale globale online, configurare un criterio di routing vocale online personalizzato e assegnarlo ai singoli utenti abilitati per la voce.

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>Esempio 1: routing vocale con un solo utilizzo PSTN

Il diagramma seguente mostra due esempi di criteri di routing vocale in un flusso di chiamata.

**Flusso di chiamata 1 (a sinistra):** Se un utente effettua una chiamata a + 1 425 XXX XX XX o + 1 206 XXX XX XX, la chiamata viene instradata a SBC sbc1.contoso.biz o sbc2.contoso.biz. Se non sono disponibili né sbc1.contoso.biz né sbc2.contoso.biz, la chiamata viene eliminata. 

**Chiamata flusso 2 (a destra):** Se un utente effettua una chiamata a + 1 425 XXX XX XX o + 1 206 XXX XX XX, la chiamata viene prima indirizzata a SBC sbc1.contoso.biz o sbc2.contoso.biz. Se non è disponibile alcun SBC, verrà provata la route con priorità inferiore (sbc3.contoso.biz e sbc4.contoso.biz). Se nessuna delle SBCs è disponibile, la chiamata viene eliminata. 

![Esempi di criteri di routing vocale](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

In entrambi gli esempi, mentre la route vocale è assegnata alle priorità, il SBCs nelle route viene provato in ordine casuale. Quando due SBC sono configurati in una sola route, il traffico di rete deve essere instradabile tra SBC o media non verrà stabilito nei trasferimenti, perché è possibile che il nuovo invito per il trasferimento venga inviato a un altro SBC nella route.

  > [!NOTE]
  > A meno che l'utente non disponga anche di una licenza per il piano di chiamata Microsoft, le chiamate a qualsiasi numero eccetto i numeri corrispondenti ai pattern + 1 425 XXX XX XX o + 1 206 XXX XX XX nella configurazione di esempio vengono eliminati. Se l'utente ha una licenza per il piano di chiamata, la chiamata viene instradata automaticamente in base ai criteri del piano di chiamata Microsoft. Il piano di chiamate Microsoft si applica automaticamente come ultima route a tutti gli utenti con la licenza per il piano di chiamata Microsoft e non richiede ulteriori configurazioni di routing delle chiamate.

Nell'esempio illustrato nel diagramma seguente viene aggiunta una route vocale per inviare chiamate a tutti gli altri numeri di Stati Uniti e canadesi (chiamate che vanno alla sequenza numerica chiamata + 1 XXX XXX XX XX).

![Mostra i criteri di routing vocale con una terza Route](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Per tutte le altre chiamate, se un utente ha entrambe le licenze (Microsoft Phone System e Microsoft Calling Plan), viene usata la route automatica. Se non corrisponde agli schemi di numero nelle route vocali online create dall'amministratore, la chiamata viene instradata tramite il piano di chiamata Microsoft. Se l'utente ha solo un sistema telefonico Microsoft, la chiamata viene eliminata perché non sono disponibili regole di corrispondenza.

  > [!NOTE]
  > Il valore di priorità per la route "altro + 1" non ha importanza in questo caso perché esiste una sola route che corrisponde al modello + 1 XXX XXX XX XX. Se un utente effettua una chiamata a + 1 324 567 89 89 e sia sbc5.contoso.biz che sbc6.contoso.biz non sono disponibili, la chiamata viene eliminata.

La tabella seguente riepiloga la configurazione usando tre route vocali. In questo esempio, tutte e tre le route fanno parte dello stesso utilizzo PSTN "USA e Canada".  Tutte le route sono associate all'utilizzo PSTN "Stati Uniti e Canada" e l'utilizzo della rete PSTN è associato al criterio di routing vocale "solo USA".

|**Utilizzo PSTN**|**Route vocale**|**Schema numerico**|**Priorità**|**SBC**|**Descrizione**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Stati Uniti e Canada|"Redmond 1"|^\\+ 1 (425 \| 206) (\d {7} ) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Route attiva per i numeri denominati + 1 425 XXX XX XX o + 1 206 XXX XX XX|
|Stati Uniti e Canada|"Redmond 2"|^\\+ 1 (425 \| 206) (\d {7} ) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Percorso di backup per numeri denominati + 1 425 XXX XX XX o + 1 206 XXX XX XX|
|Stati Uniti e Canada|"Altro + 1"|^\\+ 1 (\d {10} ) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Route per i numeri chiamati + 1 XXX XXX XX XX (eccetto + 1 425 XXX XX XX o + 1 206 XXX XX XX)|
|||||||

## <a name="example-1-configuration-steps"></a>Esempio 1: passaggi di configurazione

L'esempio seguente illustra come:

1. Creare un singolo utilizzo PSTN.
2. Configurare tre route vocali.
3. Creare un criterio di routing vocale.
4. Assegnare il criterio a un utente di nome Spencer low.

Per eseguire questa procedura, è possibile usare l'interfaccia di [amministrazione di Microsoft teams](#admincenterexample1) o [PowerShell](#powershellexample1) .

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Passaggio 1: creare l'utilizzo PSTN "Stati Uniti e Canada"

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**, passa a  >  **routing diretto** vocale e quindi nell'angolo in alto a destra selezionare **Gestisci record utilizzo PSTN**.
2. Fare clic su **Aggiungi**, digitare **Stati Uniti e Canada** e quindi fare clic su **applica**.

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Passaggio 2: creare tre route vocali (Redmond 1, Redmond 2 e altre + 1)

La procedura seguente descrive come creare una route vocale. Seguire questa procedura per creare le tre route vocali denominate Redmond 1, Redmond 2 e altre + 1 per questo esempio usando le impostazioni descritte nella tabella precedente.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**, passa a  >  **routing diretto** vocale e quindi seleziona la scheda **route vocali** .
2. Fare clic su **Aggiungi** e quindi immettere un nome e una descrizione per la route vocale.
3. Impostare la priorità e specificare il modello di numero composto.
4. Per registrare un SBC con la route vocale, in **SBCS registrato (facoltativo)**, fare clic su **Aggiungi SBCS**, selezionare il SBCS che si vuole registrare e quindi fare clic su **applica**.
5. Per aggiungere record di utilizzo PSTN, in **record utilizzo PSTN (facoltativo)**, fare clic su **Aggiungi utilizzo PSTN**, selezionare i record PSTN da aggiungere e quindi fare clic su **applica**.
6. Fare clic su **Salva**.

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>Passaggio 3: creare un criterio di routing vocale denominato "solo Stati Uniti" e aggiungere l'utilizzo PSTN "Stati Uniti e Canada" al criterio

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, **passa a**  >  **criteri di routing** vocale e quindi fai clic su **Aggiungi**.
2. Digitare **US solo** come nome e aggiungere una descrizione.
3. In **record utilizzo** PSTN fare clic su **Aggiungi utilizzo PSTN**, selezionare il record di utilizzo PSTN "Stati Uniti e Canada" e quindi fare clic su **applica**.
4. Fare clic su **Salva**.

Per altre informazioni, vedere [gestire i criteri di routing vocale](manage-voice-routing-policies.md).

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Passaggio 4: assegnare i criteri di routing vocale a un utente di nome Spencer low

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.
2. Fare clic su **criteri** e quindi fare clic su **modifica** accanto a **criteri assegnati**.
3. In **criteri di routing vocale** selezionare il criterio "solo Stati Uniti" e quindi fare clic su **Salva**.

Per altre informazioni, vedere [gestire i criteri di routing vocale](manage-voice-routing-policies.md).

### <a name="using-powershell"></a>Utilizzo di PowerShell
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Passaggio 1: creare l'utilizzo PSTN "Stati Uniti e Canada"

In una sessione remota di PowerShell in Skype for business online digitare:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

Verificare che l'utilizzo sia stato creato immettendo:

```PowerShell
Get-CSOnlinePSTNUsage
``` 

Che restituisce un elenco di nomi che possono essere troncati:

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

L'esempio seguente mostra il risultato dell'eseguire il `(Get-CSOnlinePSTNUsage).usage` comando di PowerShell per visualizzare i nomi completi (non troncati):

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Passaggio 2: creare tre route vocali (Redmond 1, Redmond 2 e altre + 1)

Per creare la route "Redmond 1", in una sessione di PowerShell in Skype for business online, immettere:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

Che restituisce:
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>

Per creare la route Redmond 2, immettere:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Per creare l'altra route + 1, immettere:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Verificare che l'espressione regolare nell'attributo NumberPattern sia valida. Puoi testarlo usando questo sito Web: [https://www.regexpal.com](https://www.regexpal.com)

In alcuni casi, è necessario instradare tutte le chiamate allo stesso SBC; usare-NumberPattern ". *"

Instradare tutte le chiamate allo stesso SBC.

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

Verificare di aver configurato correttamente la route eseguendo il comando di `Get-CSOnlineVoiceRoute` PowerShell usando le opzioni come illustrato:

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
Che dovrebbe restituire:
<pre>
Identity            : Redmond 1 
Priority               : 1
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc1.contoso.biz, sbc2.contoso.biz}
Name             : Redmond 1
Identity        : Redmond 2 
Priority               : 2
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc3.contoso.biz, sbc4.contoso.biz}
Name             : Redmond 2
    
Identity        : Other +1 
Priority               : 4
Description         : 
NumberPattern         : ^\+1(\d{10})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc5.contoso.biz, sbc6.contoso.biz}
Name             : Other +1
</pre>

Nell'esempio, la route "altro + 1" è stata assegnata automaticamente la priorità 4. 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>Passaggio 3: creare un criterio di routing vocale denominato "solo Stati Uniti" e aggiungere l'utilizzo PSTN "Stati Uniti e Canada" al criterio

In una sessione di PowerShell in Skype for business online digitare:

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

Il risultato è illustrato in questo esempio:

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Passaggio 4: assegnare i criteri di routing vocale a un utente di nome Spencer low

In una sessione di PowerShell in Skype for business online digitare:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

Convalidare l'assegnazione dei criteri immettendo questo comando:

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

Il comando restituisce quanto segue:
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>Esempio 2: routing vocale con più usi PSTN

Il criterio di routing vocale creato nell'esempio 1 consente solo le chiamate ai numeri di telefono negli Stati Uniti e in Canada, a meno che l'utente non venga assegnato anche alla licenza per il piano di chiamata Microsoft.

Nell'esempio seguente puoi creare il criterio di routing vocale "nessuna restrizione". Il criterio riutilizza l'utilizzo PSTN "Stati Uniti e Canada" creato nell'esempio 1, nonché il nuovo utilizzo PSTN "internazionale". Questo criterio instrada tutte le altre chiamate a SBCs sbc2.contoso.biz e sbc5.contoso.biz.

Gli esempi illustrati assegnano il criterio solo USA all'utente Spencer low e il criterio nessuna restrizione per l'utente John Woods in modo che il routing si verifichi come segue:

- Solo criteri di Spencer low-US.  Le chiamate sono consentite solo ai numeri Stati Uniti e canadesi. Quando si chiama l'intervallo di numeri Redmond, deve essere usato il set specifico di SBCs. I numeri non Stati Uniti non verranno instradati, a meno che non venga assegnata all'utente la licenza per il piano chiamante.

- John Woods-politica internazionale.  Le chiamate sono consentite a qualsiasi numero. Quando si chiama l'intervallo di numeri Redmond, deve essere usato il set specifico di SBCs. I numeri non Stati Uniti verranno instradati usando sbc2.contoso.biz e sbc5.contoso.biz.

![Mostra il criterio di routing vocale assegnato all'utente Spencer low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Per tutte le altre chiamate, se un utente ha entrambe le licenze (Microsoft Phone System e Microsoft Calling Plan), viene usata la route automatica. Se non corrisponde agli schemi di numero nelle route vocali online create dall'amministratore, la chiamata viene instradata tramite il piano di chiamata Microsoft.  Se l'utente ha solo sistema telefonico Microsoft, la chiamata viene eliminata perché non sono disponibili regole di corrispondenza.

![Mostra il criterio di routing vocale assegnato all'utente John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

Nella tabella seguente vengono riepilogati i criteri di routing "nessuna restrizione" denominazioni di utilizzo e route vocali. 

|**Utilizzo PSTN**|**Route vocale**|**Schema numerico**|**Priorità**|**SBC**|**Descrizione**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Stati Uniti e Canada|"Redmond 1"|^\\+ 1 (425 \| 206) (\d {7} ) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Route attiva per i numeri dei chiamanti + 1 425 XXX XX XX o + 1 206 XXX XX XX|
|Stati Uniti e Canada|"Redmond 2"|^\\+ 1 (425 \| 206) (\d {7} ) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Percorso di backup per i numeri dei chiamanti + 1 425 XXX XX XX o + 1 206 XXX XX XX|
|Stati Uniti e Canada|"Altro + 1"|^\\+ 1 (\d {10} ) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Route per i numeri dei chiamanti + 1 XXX XXX XX XX (eccetto + 1 425 XXX XX XX o + 1 206 XXX XX XX)|
|Internazionale|Internazionale|\d +|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|Route per qualsiasi modello di numero |

  > [!NOTE]
  > - L'ordine degli usi PSTN nei criteri di routing vocale è fondamentale. Gli usi vengono applicati in ordine e se viene trovata una corrispondenza nel primo utilizzo, gli altri usi non vengono mai valutati. L'utilizzo PSTN "internazionale" deve essere posizionato dopo l'utilizzo PSTN "Stati Uniti e Canada". Per modificare l'ordine degli usi PSTN, eseguire il `Set-CSOnlineVoiceRoutingPolicy` comando. <br/>Ad esempio, per cambiare l'ordine da "Stati Uniti e Canada" prima e "internazionale" in secondo luogo, eseguire l'ordine inverso:<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - La priorità per le route vocali "altro + 1" e "internazionale" viene assegnata automaticamente. Gli utenti non hanno importanza se hanno priorità più basse rispetto a "Redmond 1" e "Redmond 2".

## <a name="example-2-configuration-steps"></a>Esempio 2: passaggi di configurazione

L'esempio seguente illustra come:

1. Creare un nuovo utilizzo PSTN denominato internazionale.
2. Creare una nuova route vocale denominata internazionale.
3. Creare un criterio di routing vocale denominato nessuna restrizione.
4. Assegnare il criterio all'utente John Woods.

Per eseguire questa procedura, è possibile usare l'interfaccia di [amministrazione di Microsoft teams](#admincenterexample2) o [PowerShell](#powershellexample2) .

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Passaggio 1: creare l'utilizzo PSTN "internazionale"

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**, passa a  >  **routing diretto** vocale e quindi nell'angolo in alto a destra selezionare **Gestisci record utilizzo PSTN**.
2. Fare clic su **Aggiungi**, digitare **internazionale** e quindi fare clic su **applica**.

#### <a name="step-2-create-the-international-voice-route"></a>Passaggio 2: creare la route vocale "internazionale"

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**, passa a  >  **routing diretto** vocale e quindi seleziona la scheda **route vocali** .
2. Fare clic su **Aggiungi**, immettere "internazionale" come nome e quindi aggiungere la descrizione.
3. Imposta la priorità su 4 e quindi imposta il modello di numero composto su \d +.
4. In **SBCS registrato (facoltativo)** fare clic su **Aggiungi SBCs**, selezionare sbc2.contoso.biz e sbc5.contoso.biz e quindi fare clic su **applica**.
5. In **record utilizzo PSTN (facoltativo)** fare clic su **Aggiungi utilizzo PSTN**, selezionare il record di utilizzo PSTN "internazionale" e quindi fare clic su **applica**.
6. Fare clic su **Salva**.

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>Passaggio 3: creare un criterio di routing vocale denominato "nessuna restrizione" e aggiungere gli utilizzi PSTN "Stati Uniti e Canada" e "internazionale" al criterio

Gli usi PSTN "Stati Uniti e Canada" vengono riutilizzati in questo criterio di routing vocale per mantenere una gestione speciale per le chiamate al numero "+ 1 425 XXX XX XX" e "+ 1 206 XXX XX XX" come chiamate locali o in locale.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, **passa a**  >  **criteri di routing** vocale e quindi fai clic su **Aggiungi**.
2. Digitare **Nessuna restrizione** come nome e aggiungere una descrizione.
3. In **record utilizzo** PSTN fare clic su **Aggiungi utilizzo PSTN**, selezionare il record di utilizzo PSTN "Stati Uniti e Canada" e quindi selezionare il record di utilizzo PSTN "internazionale". Fare clic su **applica**.

    Prendere nota dell'ordine degli usi PSTN:

    - Se una chiamata effettuata al numero "+ 1 425 XXX XX XX" con gli usi configurati come in questo esempio, la chiamata segue la route impostata nell'uso "USA e Canada" e viene applicata la logica di routing speciale. La chiamata viene quindi instradata tramite sbc1.contoso.biz e sbc2.contoso.biz prima, quindi sbc3.contoso.biz e sbc4.contoso.biz come route di backup.

    - Se l'utilizzo PSTN "internazionale" è prima di "Stati Uniti e Canada", le chiamate a + 1 425 XXX XX XX vengono instradate a sbc2.contoso.biz e sbc5.contoso.biz come parte della logica di routing.

4. Fare clic su **Salva**.

Per altre informazioni, vedere [gestire i criteri di routing vocale](manage-voice-routing-policies.md).

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>Passaggio 4: assegnare i criteri di routing vocale a un utente di nome John Woods

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.
2. Fare clic su **criteri** e quindi fare clic su **modifica** accanto a **criteri assegnati**.
3. In **criteri di routing vocale** selezionare il criterio "nessuna restrizione" e quindi fare clic su **Salva**.

Il risultato è che il criterio vocale applicato alle chiamate di John Woods è senza restrizioni e seguirà la logica di routing delle chiamate disponibile per gli Stati Uniti, il Canada e la chiamata internazionale.

### <a name="using-powershell"></a>Utilizzo di PowerShell
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Passaggio 1: creare l'utilizzo PSTN "internazionale"

In una sessione remota di PowerShell in Skype for business online, immettere:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a>Passaggio 2: creare una nuova route vocale denominata "internazionale"

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
Che restituisce:

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a>Passaggio 3: creare un criterio di routing vocale denominato "nessuna restrizione"

L'utilizzo PSTN "Redmond 1" e "Redmond" vengono riutilizzati in questo criterio di routing vocale per mantenere una gestione speciale per le chiamate al numero "+ 1 425 XXX XX XX" e "+ 1 206 XXX XX XX" come chiamate locali o in locale.

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Prendere nota dell'ordine degli usi PSTN:

  - Se una chiamata effettuata al numero "+ 1 425 XXX XX XX" con gli usi configurati come nell'esempio seguente, la chiamata segue la route impostata nell'uso "USA e Canada" e viene applicata la logica di routing speciale. La chiamata viene quindi instradata tramite sbc1.contoso.biz e sbc2.contoso.biz prima, quindi sbc3.contoso.biz e sbc4.contoso.biz come route di backup.

  - Se l'utilizzo PSTN "internazionale" è prima di "Stati Uniti e Canada", le chiamate a + 1 425 XXX XX XX vengono instradate a sbc2.contoso.biz e sbc5.contoso.biz come parte della logica di routing. Immettere il comando:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Che restituisce:

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a>Passaggio 4: assegnare i criteri di routing vocale all'utente di nome John Woods

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

Verificare quindi l'assegnazione usando il comando: 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

Che restituisce:

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

Il risultato è che il criterio vocale applicato alle chiamate di John Woods è illimitato e seguirà la logica di routing delle chiamate disponibile per gli Stati Uniti, il Canada e la chiamata internazionale.

## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)
